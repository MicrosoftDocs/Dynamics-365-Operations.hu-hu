---
title: Kiskereskedelmi tranzakció konzisztencia-ellenőrzése
description: Ebben a témakörben részletes leírást találhat a Dynamics 365 Commerce tranzakció konzisztencia-ellenőrzésre használatos funkciójáról.
author: josaw1
ms.date: 10/07/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: c8ba0f99743984860119deb96c889f5d62e1728c8772b9e6786d371690b61489
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741732"
---
# <a name="retail-transaction-consistency-checker"></a>Kiskereskedelmi tranzakció konzisztencia-ellenőrzése

[!include [banner](includes/banner.md)]

Ebben a témakörben részletes leírást találhat a Microsoft Dynamics 365 Commerce tranzakció konzisztencia-ellenőrzésre használatos funkciójáról. A konzisztencia-ellenőrző azonosítja és elkülöníti az inkonzisztens tranzakciókat, mielőtt a kimutatásfeladási folyamat kezeli őket.

Egy kimutatás feladása során a szolgáltatásban a feladás sikertelen lehet, ha inkonzisztens adatok találhatók a kereskedelmi tranzakciók táblájában. Az adatokkal kapcsolatos problémákat a pénztár (POS) alkalmazás előre nem látható problémái okozhatják, vagy ha a tranzakciók importálása nem megfelelően történt egy külső fél pénztárrendszeréből. Az alábbiakban az inkonzisztenciák megjelenésére mutatunk be példákat: 

- A fejléctáblában szereplő tranzakciós végösszeg nem egyezik meg a sorokban található tranzakciók összegével.
- A fejléctábla sorainak száma nem egyezik meg a tranzakciós tábla sorainak számával.
- A fejléctáblában szereplő adók nem egyeznek meg a sorokban szereplő adó összegével. 

Ha a kimutatásfeladási folyamat feldolgozza az inkonzisztens tranzakciókat, akkor inkonzisztens értékesítési számlák és fizetési naplók keletkeznek, és emiatt a teljes kimutatásfeladási folyamat sikertelen lesz. Ha a kimutatásokat ebből az állapotból szeretné helyreállítani, ahhoz számos tranzakciós táblát érintő, komplex adathelyesbítési művelet szükséges. A tranzakció konzisztencia-ellenőrzője megelőzi az ehhez hasonló problémák létrejöttét.

Az alábbi ábrán a tranzakció konzisztencia-ellenőrzőjével végrehajtott feladási folyamat látható.

![Kimutatás feladási folyamata a tranzakció konzisztenciájának ellenőrzőjével.](./media/validchecker.png "Kimutatás feladási folyamata a kiskereskedelmi tranzakció konzisztenciájának ellenőrzőjével")

Az **Üzleti tranzakciók ellenőrzése** kötegfolyamat ellenőrzi a kereskedelmi tranzakciós táblázatok konzisztenciáját az alábbi esetekben.

- **Vevői számla** – Ellenőrzi, hogy a kereskedelmi tranzakciós táblában szereplő vevői számla létezik a HQ-ban a vevői alapadatok között.
- **Sorok száma** – Ellenőrzi, hogy a tranzakciós fejléctáblában rögzített sorok száma megegyezik az értékesítési tranzakciók táblájában található sorok számával.
- **Az ár tartalmazza az adót** – Ellenőrzi, hogy az **Ár tartalmazza az adót** paraméter konzisztens-e a tranzakció soraiban, és az értékesítési soron szereplő ár egyezik-e az adót tartalmazó ár és az adómentesség konfigurációjával.
- **Kifizetett összeg** – Ellenőrzi, hogy a kifizetési rekordok megegyeznek-e a fejlécben található kifizetett összeggel, miközben figyelembe veszik a főkönyvben szereplő fillérkerekítési konfigurációt.
- **Bruttó összeg** – Ellenőrzi, hogy a fejlécben szereplő bruttó összeg megfelel-e a sorokban található nettó összegek és az adó összegének összesítésével, miközben figyelembe veszi a főkönyvben szereplő fillérkerekítési konfigurációt is.
- **Nettó összeg** – Ellenőrzi, hogy a fejlécben szereplő nettó összeg megfelel-e a sorokban található nettó összegeknek, miközben figyelembe veszi a főkönyvben szereplő fillérkerekítési konfigurációt is.
- **Alulfizetés/Túlfizetés** – Ellenőrzi, hogy a fejlécben található bruttó összeg és a kifizetett összeg közti különbség nem haladja meg a maximális alulfizetés/túlfizetés konfigurációját, miközben figyelembe veszi a főkönyvben szereplő fillérkerekítési konfigurációt.
- **Engedmény összege** – Ellenőrzi, hogy az engedménytáblákban szereplő engedmény összege és a kiskereskedelmi tranzakció sorában szereplő engedmény összege konzisztens-e, és hogy a fejlécben található engedmény összege egyenlő-e a sorok engedményeinek összegével, miközben figyelembe veszi a főkönyvben szereplő fillérkerekítési konfigurációt.
- **Sorengedmény** – Ellenőrzi, hogy a tranzakciós sorban található sorengedmény megegyezik-e az adott tranzakciós sorhoz kapcsolódó engedménytábla összes sorának összegével.
- **Ajándékutalvány-cikk** – A Commerce alkalmazás nem támogatja az ajándékutalvány-cikkek visszaküldését. Azonban az ajándékutalvány egyenlegét ki lehet fizetni készpénzben. Ha az ajándékutalványcikket visszárusorként dolgozzák fel készpénzes kifizetési sor helyett, akkor a kimutatás feladási folyamata sikertelen lesz. Az ajándékutalvány-cikkek ellenőrzési folyamata segítségével garantálható, hogy a tranzakciós táblákban szereplő, ajándékutalvány-cikkek visszaküldésére vonatkozó sorok ajándékutalvány készpénzes kifizetési sorok legyenek.
- **Negatív ár** – Ellenőrzi, hogy nincsenek negatív árt tartalmazó tranzakciós sorok.
- **Cikk és változat** – Ellenőrzi, hogy a tranzakciós sorban szereplő cikkek és változatok léteznek a cikk és a változat törzsadatfájljában.
- **Adó összege** – Ellenőrzi, hogy az adórekordok megegyeznek-e a sorokban szereplő adók összegével.
- **Sorozatszám** – Ellenőrzi, hogy azon cikkekhez tartozó tranzakciósorokban szerepeljen a sorozatszám, amelyek ellenőrzése sorozatszámmal történik.
- **Előjel** – Ellenőrzi, hogy a mennyiség és a nettó összeg előjele megegyezik-e az összes tranzakciós sorban.
- **Üzleti dátum** – Ellenőrzi, hogy a tranzakciókhoz tartozó összes üzleti dátum pénzügyi időszaka nyitott-e.
- **Költségek** – ellenőrzi, hogy a fejléc és a sor költségösszege megfelel-e az adót tartalmazó ár és az adómentesség konfigurációjának.

## <a name="set-up-the-consistency-checker"></a>Konzisztencia-ellenőrző beállítása

Konfigurálja az „Üzleti tranzakciók ellenőrzése” kötegfolyamatot időszakos futásokhoz a **Retail és Commerce \> Retail és Commerce IT \> Pénztárfeladás** menüpontban. A kötegelt feladat az üzlet szervezeti hierarchiája alapján ütemezhető, hasonlóan a „Kimutatások kötegelt kiszámítása” és a „Kimutatások kötegelt feladása” folyamatok beállításához. Javasoljuk, hogy úgy konfigurálja ezt a kötegfolyamatot, hogy az naponta többször fusson, és úgy ütemezze, hogy minden P-feladat végrehajtása végén fusson.

## <a name="results-of-validation-process"></a>Ellenőrzési folyamat eredményei

A kötegfolyamat által végzett ellenőrzés eredményeit a rendszer felcímkézi a megfelelő tranzakcióra. A tranzakció rekordján található **Ellenőrzés állapota** mező vagy **Sikeres** vagy **Hiba** értékre van beállítva, és az utolsó ellenőrzés futásának dátuma a **Legutóbbi ellenőrzés időpontja** mezőben látható.

Ha további, ellenőrzési hibához kapcsolódó leíróbb jellegű hibaüzenetet szeretne megtekinteni, válassza ki a megfelelő üzlet tranzakciós rekordját, majd kattintson az **Ellenőrzési hibák** gombra.

Azokat a tranzakciókat, amelyek nem feleltek meg az ellenőrzésen, valamint a még nem ellenőrzött tranzakciókat a rendszer nem szerepelteti a kimutatásokban. A „Kimutatás számítása” folyamat során a felhasználók értesítést kapnak, ha olyan tranzakciók találhatók, amelyeknek szerepelniük kellett volna a kimutatásban, de mégsem szerepeltek.

Ha ellenőrzési probléma merül fel, a hiba javítása csak a Microsoft ügyfélszolgálata segítségével lehetséges. A jövőbeli kiadások egyikében hozzáadásra kerül majd a lehetőség, amely segítségével a felhasználók maguk is kijavíthatják a rekordokat a felhasználói felületen, amelyek sikertelenek voltak. A később hozzáférhetővé váló naplózási és auditálási lehetőségek segítségével a módosítások előzményei is nyomon követhetők lesznek.

> [!NOTE]
> A jövőbeli kiadásokban olyan további ellenőrzési szabályokat adunk hozzá, amellyel még több eset ellenőrzése válik lehetővé.


[!INCLUDE[footer-include](../includes/footer-banner.md)]