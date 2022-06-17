---
title: Üzleti tranzakciók ellenőrzése kimutatásszámításhoz
description: Ez a cikk az üzleti tranzakciók ellenőrzésével kapcsolatos funkciókat ismerteti a Microsoft Dynamics 365 Commerce alkalmazásban.
author: analpert
ms.date: 01/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: analpert
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4be40189777a37495f185467050b61af47b684d7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890513"
---
# <a name="validate-store-transactions-for-statement-calculation"></a>Üzleti tranzakciók ellenőrzése kimutatásszámításhoz

[!include [banner](includes/banner.md)]

Ez a cikk az üzleti tranzakciók ellenőrzésével kapcsolatos funkciókat ismerteti a Microsoft Dynamics 365 Commerce alkalmazásban. Az ellenőrzési folyamat a feladási hibákat okozó tranzakciókat azonosítja és jelöli meg, mielőtt a kimutatásfeladási-folyamat feldolgozná azokat.

Amikor kimutatást próbál feladni, az ellenőrzési folyamat sikertelen lehet, ha inkonzisztens adatok találhatók a kereskedelmi tranzakciók tábláiban. Íme néhány példa olyan tényezőkre, amelyek a ezeket az inkonzisztenciákat okozhatják:

- A fejléctáblában szereplő tranzakciós végösszeg nem egyezik meg a sorokban található tranzakciók összegével.
- A fejléctáblában megadott cikkek száma nem egyezik meg a tranzakciós táblában lévő cikkek számával.
- A fejléctáblában szereplő adók nem egyeznek meg a sorokban szereplő adó összegével. 

Ha a kimutatásfeladási folyamat feldolgozza az inkonzisztens tranzakciókat, akkor értékesítési számlák és fizetési naplók keletkeznek, és emiatt a feladási folyamat sikertelen lehet. Az **Üzleti tranzakciók ellenőrzése** folyamat kiküszöböli ezeket a problémákat, azáltal, hogy csak a tranzakcióellenőrzési szabályoknak megfelelő tranzakciókat adja át a tranzakciókimutatás számítási folyamatának.

A következő ábra a tranzakciók feltöltésére, a tranzakciók ellenőrzésére, a tranzakció-kimutatások kiszámítására és feladására, valamint a pénzügyi kimutatások nap végi kiszámítására és feladására vonatkozó ismétlődő napi folyamatokat mutatja be.

![A tranzakciók feltöltésére, a tranzakciók ellenőrzésére, a tranzakció-kimutatások kiszámítására és feladására, valamint a pénzügyi kimutatások nap végi kiszámítására és feladására vonatkozó ismétlődő napi folyamatokat bemutató ábra](./media/valid-checker-statement-posting-flow.png)

## <a name="store-transaction-validation-rules"></a>Üzleti tranzakció ellenőrzési szabályai

Az **Üzleti tranzakciók ellenőrzése** kötegfolyamat ellenőrzi a kereskedelmi tranzakciók tábláinak konzisztenciáját a következő ellenőrzési szabályok alapján.

> [!NOTE]
> Az ellenőrzési szabályok hozzáadása a későbbi verziókban is folytatódik.

### <a name="transaction-header-validation-rules"></a>Tranzakciófejléc ellenőrzési szabályai

Az alábbi táblázat felsorolja azokat a tranzakciófejléc-ellenőrzési szabályokat, amelyekkel szemben ellenőrizve vannak a kereskedelmi tranzakciók fejlécei, mielőtt a tranzakciók át lennének adva kimutatás-feladásra.

| Szabály | Leírás |
|-------|-------------|
| Üzleti dátum | Ez a szabály ellenőrzi, hogy a tranzakció üzleti dátuma egy nyitott pénzügyi időszakhoz van-e társítva a főkönyvben. |
| Pénznemkerekítés | Ez a szabály ellenőrzi, hogy a tranzakcióösszegek kerekítése a pénznemkerekítési szabály szerint történik-e. |
| Vevői számla | Ez a szabály azt ellenőrzi, hogy a tranzakcióban használt vevő létezik-e az adatbázisban. |
| Engedmény összege | Ez a szabály azt ellenőrzi, hogy a fejlécben szereplő engedményösszeg megfelel-e a sorokban található engedményösszegek összesítésével. |
| Pénzügyi bizonylat feladási állapota (Brazília) | Ez a szabály azt ellenőrzi, hogy a pénzügyi bizonylat sikeresen feladható-e. |
| Bruttó összeg | Ez a szabály azt ellenőrzi, hogy a tranzakció fejlécében szereplő bruttó összeg megfelel-e a nettó összegnek a tranzakciósorok adójával, plusz a költségekkel együtt. |
| Nettó | Ez a szabály azt ellenőrzi, hogy a tranzakció fejlécében szereplő nettó összeg megfelel-e a nettó összegnek a tranzakciósorok adója nélkül és költségekkel. |
| Nettó+adó | Ez a szabály azt ellenőrzi, hogy a tranzakció fejlécében szereplő bruttó összeg megfelel-e a nettó összegnek a tranzakciósorok adója nélkül, plusz az összes adó és költség. |
| Cikkek száma | Ez a szabály ellenőrzi, hogy a tranzakció fejlécében megadott cikkek száma megegyezik-e a tranzakciósorok mennyiségeinek összegével. |
| Kifizetett összeg | Ez a szabály ellenőrzi, hogy a tranzakció fejlécében található kifizetett összeg megegyezik-e az összes fizetési tranzakció összegével. |
| Adómentesség számítása | Ez a szabály ellenőrzi, hogy a számított összeg és a költségsorok adómentességi összeg megegyezik-e az eredeti számított összeggel. |
| Díjszabás adóval együtt | Ez a szabály ellenőrzi, hogy az **Ár tartalmazza az adót** jelölő konzisztens-e a tranzakciófejlécben és az adótranzakciókban. |
| A tranzakció nem üres | Ez a szabály ellenőrzi, hogy a tranzakció tartalmaz-e sorokat, és hogy legalább egy olyan sor van-e, ami nincsen érvénytelenítve. |
| Alulfizetés/túlfizetés | Ez a szabály ellenőrzi, hogy a fejlécben található bruttó összeg és a kifizetett összeg közti különbség nem nagyobb, mint a maximális alulfizetés/túlfizetés konfigurációja. |

### <a name="transaction-line-validation-rules"></a>Tranzakciósor ellenőrzési szabályai

Az alábbi táblázat felsorolja azokat a tranzakciósor-ellenőrzési szabályokat, amelyekkel szemben ellenőrizve vannak a kereskedelmi tranzakciók sorainak részletei, mielőtt a tranzakciók át lennének adva kimutatás-feladásra.

| Szabály | Leírás |
|-------|-------------|
| Vonalkód | Ez a szabály ellenőrzi, hogy a tranzakciósorok minden cikkvonalkódja létezik-e az adatbázisban. |
| Költségsorok | Ez a szabály ellenőrzi, hogy a számított összeg és a költségsorok adómentességi összeg megegyezik-e az eredeti számított összeggel. |
| Ajándékutalvány-visszáruk | Ez a szabály ellenőrzi, hogy a tranzakcióban nincsenek-e ajándékutalványok visszárui. |
| Cikkváltozat | Ez a szabály ellenőrzi, hogy a tranzakciósorok minden cikke és változata létezik-e az adatbázisban. |
| Sorengedmény | Ez a szabály azt ellenőrzi, hogy a sorengedmény összege megfelel-e az engedménytranzakciók összegének. |
| Sor adója | Ez a szabály azt ellenőrzi, hogy a sor adóösszege megfelel-e az adótranzakciók összegének. |
| Negatív ár | Ez a szabály azt ellenőrzi, hogy nincsenek negatív árak használva a tranzakciós sorokban. |
| Sorozatszámmal vezérelt | Ez a szabály ellenőrzi, hogy azon cikkekhez tartozó tranzakciósorokban, amelyek ellenőrzése sorozatszámmal történik szerepeljen a sorozatszám. |
| Sorozatszám dimenziója | Ez a szabály ellenőrzi, hogy ne legyen megadva sorozatszám, ha a cikk sorozatszám-dimenziója inaktív. |
| Előjel ellentmondása | Ez a szabály, hogy a mennyiség és a nettó összeg előjele megegyezik-e az összes tranzakciós sorban. |
| Adómentes | Ez a szabály ellenőrzi, hogy a sorcikk ára és a költségsorok adómentességi összege megegyezik-e az eredeti árral. |
| Adócsoport-hozzárendelés | Ez a szabály ellenőrzi, hogy az áfacsoport és a cikkáfacsoport kombinációja érvényes adómetszetet hoz-e létre. |
| Mértékegység-átváltások | Ez a szabály ellenőrzi, hogy az összes sor mértékegységének érvényes átváltása van-e a készlet mértékegységére. |

## <a name="enable-the-store-transaction-validation-process"></a>Az üzleti tranzakció ellenőrzési folyamatának engedélyezése

Konfigurálja az **Üzleti tranzakciók ellenőrzése** feladatot időszakos futásokhoz a Commerce központban (**Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem IT \> Pénztárfeladás**). A kötegelt feladat ütemezése az üzlet szervezeti hierarchiája alapján történik. Javasoljuk, hogy ezt a kötegfolyamatot ugyanolyan gyakorisággal futtassa, mint a **P-feladat** és a **Tranzakciós kimutatások számítása** feladat kötegelt feladatokat.

## <a name="results-of-the-validation-process"></a>Az ellenőrzési folyamat eredményei

Az **Üzleti tranzakciók ellenőrzése** kötegfolyamat eredménye megtekinthető minden kiskereskedelmi üzleti tranzakcióban. A tranzakciórekord **Ellenőrzés állapota** mezőjének beállítása **Sikeres**, **Hiba** vagy **Nincs**. A **Legutóbbi ellenőrzés időpontja** mező a legutóbbi ellenőrzés futtatásának dátumát mutatja.

A következő táblázat az egyes ellenőrzési állapotokat ismerteti.

| Ellenőrzés állapota | Leírás |
|-------------------|-------------|
| Sikeres | Minden engedélyezett ellenőrzési szabály teljesült. |
| Hiba | Egy engedélyezett ellenőrzési szabály hibát észlelt. A hibával kapcsolatos további részleteket a Művelet panel **Ellenőrzési hibák** elemének kiválasztásával lehet megtekinteni. |
| Nincs | A tranzakciótípushoz nem szükséges ellenőrzési szabályokat alkalmazni. |

![Az Ellenőrzés állapota mezőt és az Ellenőrzési hibák gombot megjelenítő Üzleti tranzakciók lap.](./media/valid-checker-validation-status-errors.png)

Csak a **Sikeres** ellenőrzési állapotú tranzakciók lesznek feléve a tranzakciós kimutatásokba. A **Hiba** állapotú tranzakciók megtekintéséhez tekintse át a **Készpénzzel fizetett, azonnal átvett ellenőrzési hibák** csempét az **Üzlet pénzügyi adatai** munkaterületen.

![Csempék az Üzlet pénzügyi adatai munkaterületen.](./media/valid-checker-cash-carry-validation-failures.png)

A Készpénzzel fizetett, azonnal átvett ellenőrzési hibák javításával kapcsolatos további tudnivalókat lásd: [Készpénzzel fizetett, azonnal átvett és készpénzkezelési tranzakciók szerkesztése és auditálása](edit-cash-trans.md).

## <a name="additional-resources"></a>További erőforrások

[Készpénzzel fizetett, azonnal átvett és készpénzkezelési tranzakciók szerkesztése és auditálása](edit-cash-trans.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
