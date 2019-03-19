---
title: Kiskereskedelmi tranzakció konzisztencia-ellenőrzése
description: Ebben a témakörben részletes leírást találhat a Microsoft Dynamics 365 for Retail kiskereskedelmi tranzakció konzisztencia-ellenőrzésére használatos funkciójáról.
author: josaw1
manager: AnnBe
ms.date: 01/08/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 8b373ce3cfd1183a082e2b1ebaf8c907b16e581e
ms.sourcegitcommit: ca4562fafa33b3512f0a5e246b15545fcf53e834
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2019
ms.locfileid: "379993"
---
# <a name="retail-transaction-consistency-checker"></a>Kiskereskedelmi tranzakció konzisztencia-ellenőrzése


[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

Ebben a témakörben részletes leírást találhat a Microsoft Dynamics 365 for Finance and Operations 8.1.3 verziójában bemutatott kiskereskedelmi tranzakció konzisztencia-ellenőrzésére használatos funkcióról. A konzisztencia-ellenőrző azonosítja és elkülöníti az inkonzisztens tranzakciókat, mielőtt a kimutatásfeladási folyamat kezeli őket.

Egy kimutatás feladása során a Retail szolgáltatásban a feladás sikertelen lehet, ha inkonzisztens adatok találhatók a kiskereskedelmi tranzakciók táblájában. Az adatokkal kapcsolatos problémákat a pénztár (POS) alkalmazás előre nem látható problémái okozhatják, vagy ha a tranzakciók importálása nem megfelelően történt egy külső fél pénztárrendszeréből. Az alábbiakban az inkonzisztenciák megjelenésére mutatunk be példákat: 

  - A fejléctáblában szereplő tranzakciós végösszeg nem egyezik meg a sorokban található tranzakciók összegével.
  - A fejléctábla sorainak száma nem egyezik meg a tranzakciós tábla sorainak számával.
  - A fejléctáblában szereplő adók nem egyeznek meg a sorokban szereplő adó összegével. 
  
Ha a kimutatásfeladási folyamat feldolgozza az inkonzisztens tranzakciókat, akkor inkonzisztens értékesítési számlák és fizetési naplók keletkeznek, és emiatt a teljes kimutatásfeladási folyamat sikertelen lesz. Ha a kimutatásokat ebből az állapotból szeretné helyreállítani, ahhoz számos tranzakciós táblát érintő, komplex adathelyesbítési művelet szükséges. A kereskedelmi tranzakció konzisztencia-ellenőrzője megelőzi az ehhez hasonló problémák létrejöttét.

Az alábbi ábrán a tranzakció konzisztencia-ellenőrzőjével végrehajtott feladási folyamat látható.

![Kimutatásfeladási folyamat kiskereskedelmi tranzakció konzisztencia-ellenőrzőjével](./media/validchecker.png "Kimutatásfeladási folyamat kiskereskedelmi tranzakció konzisztencia-ellenőrzőjével")

Az **Üzleti tranzakciók ellenőrzése** kötegfolyamat ellenőrzi a kiskereskedelmi tranzakciós táblázatok konzisztenciáját az alábbi esetekben.

- Vevői számla – Ellenőrzi, hogy a kiskereskedelmi tranzakciós táblában szereplő vevői számla létezik a HQ-ban a vevői alapadatok között.
- Sorok száma – Ellenőrzi, hogy a tranzakciós fejléctáblában rögzített sorok száma megegyezik az értékesítési tranzakciók táblájában található sorok számával.

## <a name="set-up-the-consistency-checker"></a>Konzisztencia-ellenőrző beállítása
Konfigurálja az „Üzleti tranzakciók ellenőrzése” kötegfolyamatot időszakos futás esetén a **Kiskereskedelem \> Kiskereskedelem IT \> POS-feladás** menüpontban. A kötegelt feladat az üzlet szervezeti hierarchiája alapján ütemezhető, hasonlóan a „Kimutatások kötegelt kiszámítása” és a „Kimutatások kötegelt feladása” folyamatok beállításához. Javasoljuk, hogy úgy konfigurálja ezt a kötegfolyamatot, hogy az naponta többször fusson, és úgy ütemezze, hogy minden P-feladat végrehajtása végén fusson.

## <a name="results-of-validation-process"></a>Ellenőrzési folyamat eredményei
A kötegfolyamat által végzett ellenőrzés eredményeit a rendszer felcímkézi a megfelelő kiskereskedelmi tranzakcióra. A kiskereskedelmi tranzakció rekordján található **Ellenőrzés állapota** mező vagy **Sikeres** vagy **Hiba** értékre van beállítva, és az utolsó ellenőrzés futásának dátuma a **Legutóbbi ellenőrzés időpontja** mezőben látható.

Ha további, ellenőrzési hibához kapcsolódó leíróbb jellegű hibaüzenetet szeretne megtekinteni, válassza ki a megfelelő kiskereskedelmi üzlet tranzakciós rekordját, majd kattintson az **Ellenőrzési hibák** gombra.

Azokat a tranzakciókat, amelyek nem feleltek meg az ellenőrzésen, valamint a még nem ellenőrzött tranzakciókat a rendszer nem szerepelteti a kimutatásokban. A „Kimutatás számítása” folyamat során a felhasználók értesítést kapnak, ha olyan tranzakciók találhatók, amelyeknek szerepelniük kellett volna a kimutatásban, de mégsem szerepeltek.

Ha ellenőrzési probléma merül fel, a hiba javítása csak a Microsoft ügyfélszolgálata segítségével lehetséges. A jövőbeli kiadások egyikében hozzáadásra kerül majd a lehetőség, amely segítségével a felhasználók maguk is kijavíthatják a rekordokat a felhasználói felületen, amelyek sikertelenek voltak. A később hozzáférhetővé váló naplózási és auditálási lehetőségek segítségével a módosítások előzményei is nyomon követhetők lesznek.

> [!NOTE]
> A jövőbeli kiadásokban olyan további ellenőrzési szabályokat adunk hozzá, amellyel még több eset ellenőrzése válik lehetővé.
