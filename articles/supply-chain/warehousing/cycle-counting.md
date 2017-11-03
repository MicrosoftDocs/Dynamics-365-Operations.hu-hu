---
title: "Ciklikus leltározás"
description: "Ez a cikk leírja, hogyan használhatja a ciklikus leltározást a raktározási megoldással, amely a Raktárkezelésben érhető el. A cikk nem vonatkozik a raktározási megoldásra, amely a Készletkezelés modulból érhető el."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSCycleCountThreshold, WHSWorkTableListPage
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 50671
ms.assetid: 49f5c431-b043-4170-aa24-b7d5d1ee063e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2437d3efe7841021ff4bd35f307fddddc76eb4c6
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="cycle-counting"></a>Ciklikus leltározás

[!include[banner](../includes/banner.md)]


Ez a cikk leírja, hogyan használhatja a ciklikus leltározást a raktározási megoldással, amely a Raktárkezelésben érhető el. A cikk nem vonatkozik a raktározási megoldásra, amely a Készletkezelés modulból érhető el.

A ciklikus leltározás egy olyan raktározási folyamat, amelyet az aktuális készlet cikkeinek ellenőrzésére használhat. A ciklikus leltározás folyamata három lépésben írható le:

1.  **Ciklikus leltározási munka létrehozása** – A ciklikus leltározási munka automatikusan létrehozható a cikkek küszöbértékeinek paraméterei alapján, vagy a ciklikus leltározási terv használatával. Másik megoldásként létrehozhatja a ciklikus leltározási munkát manuálisan, a cikk vagy a raktár paramétereinek segítségével a **Ciklikus leltározási munka cikk szerint** vagy a **Ciklikus leltározási munka hely szerint** oldalakról.
2.  **A ciklikus leltár feldolgozása** – Miután létrehozott egy ciklikus leltározási munkát, a raktárhelyen található cikkek számlálásával végezheti el a ciklikus leltározási munkát, majd mobileszközén rögzítheti az eredményt a Microsoft Dynamics 365 Finance and Operations rendszerbe. Ciklikus leltározási munka létrehozása nélkül is megszámlálhatja a raktározási helyen található cikkeket. Ennek a folyamatnak *eseti ciklikus leltározás*a neve.
3.  **A ciklikus leltárérték különbségeinek feloldása** – Azok a cikkek, amelyek számlált értékeiben a ciklikus leltár után eltérés mutatkozik, **Ellenőrzése függőben** munkaállapotúvá válnak az **Összes munka** oldalon. Ezeket a különbségek feloldhatja a **Ciklikus leltározási munka ellenőrzése függőben** oldalon.

Az alábbi ábra a ciklikus leltározás folyamatát mutatja be. ![Ciklikus leltározás végrehajtása azonnal](./media/performcyclecountinginawarehouselocation.jpg)

## <a name="cycle-counting-prerequisites"></a>A ciklikus leltározás előfeltételei
Az alábbi táblázat bemutatja a ciklikus leltár megkezdése előtt biztosítandó előfeltételeket.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Előfeltételek</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Cikk</td>
<td>A cikknek elérhetőnek kell lennie a raktárkezelő folyamathoz.</td>
</tr>
<tr class="even">
<td>Raktár</td>
<td>A raktárnak elérhetőnek kell lennie a raktárkezelő folyamathoz. A raktárt a <strong>Raktárak</strong> oldalon a raktár kiválasztásával, majd a <strong>Raktárkezelési folyamatok alkalmazása</strong> lehetőség kijelölésével tudja a raktárkezelési folyamatokhoz elérhetővé tenni. Hogy engedélyezze a ciklikus leltár idejére a dolgozóknak a raklapok mozgatását, akkor jelölje ki a <strong>Raklapmozgatás engedélyezése ciklikus leltározás közben</strong> lehetőséget a <strong>Raktárkezelés</strong> gyorslapon.</td>
</tr>
<tr class="odd">
<td>Munkagyűjtők</td>
<td>Választható: Hozzon létre munkagyűjtőket, hogy elkülönítse a raktári munkákat a munka típusa alapján (ebben az esetben a ciklikus leltározási munka).</td>
</tr>
<tr class="even">
<td>Helyek</td>
<td>Helyi ciklikus leltározásos engedélyezése. A ciklikus leltározás engedélyezéséhez egy raktárban válassza ki a <strong>Ciklikus leltározás engedélyezése</strong> lehetőséget a <strong>Helyprofilok</strong> oldalon.</td>
</tr>
<tr class="odd">
<td>Raktárkezelési paraméterek</td>
<td>Ciklikus leltározás paramétereinek beállítása. A <strong>Raktárkezelési paraméterek</strong> oldalon határozza meg az alapértelmezett helyesbítéstípus-kódot, a munkaosztály azonosítóját, valamint a ciklikus leltár munkaprioritásait.</td>
</tr>
<tr class="even">
<td>Mobileszköz</td>
<td><ul>
<li>Hozzon létre egy menüpontot a <strong>Mobileszköz menüpontok</strong> oldalon a következő módszerek valamelyikéhez:
<ul>
<li>Irányított ciklikus leltározás használata</li>
<li>Rendszer által irányított ciklikus leltározás</li>
<li>Ciklikus leltározás csoportosítása</li>
<li>Eseti ciklikus leltár</li>
</ul>
</li>
<li>Mobileszközök menüpontjainak beállítása.</li>
<li>Hozzon létre egy munkafelhasználói fiókot, és társítson mobileszköz-menüt a munkafelhasználó azonosítójához.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Kapcsolódó beállítási feladatok</td>
<td>Ciklikus leltározási terv beállítása raktári helyhez.</td>
</tr>
</tbody>
</table>

## <a name="automatically-create-cycle-counting-work"></a>Ciklikus leltározási munka automatikus létrehozása
Kétféle módon lehet ütemezni a ciklikus leltározási munka ismétlődő létrehozását: ciklikus leltározási küszöbértékek beállítása vagy ciklikus leltározási tervek beállítása.

-   A ciklikus leltározási küszöbérték azt jelzi, hogy a készleten lévő cikkek mennyiség vagy százalék korlátot. Ciklikus leltározási munkát automatikusan létrejön, amikor eléri a küszöbértéket korlátot.
-   A ciklikus leltározási terv vagy azonnal hozza létre a ciklikus leltározási munkát, vagy időszakosan, egy kötegelt feladaton keresztül. Ciklikus leltározási munka létrehozása esetén a leltári munkasor tartalmazza a leltár helyével kapcsolatos információt. Az ezen helyhez társított aktuális készlet nincsen blokkolva, és ezáltal elérhető foglalási és kimenő folyamatokhoz akkor is, ha már létezik megnyitott leltári munka.

### <a name="create-cycle-counting-work-based-on-threshold-parameters-for-items"></a>Ciklikus leltározási munka létrehozása, a cikkek küszöbérték paraméterei alapján

Ciklikus leltározási munka létrehozható, ha a cikkek száma egy adott küszöbérték alá esik egy helyen. Például 60 cikk van egy olyan helyen, amelynek ciklikus leltározási küszöbértéke 40. Egy értékesítési rendelés tranzakciója közben 25 cikket kitárolnak a helyről, majd betárolják egy előkészítő helyre. Mivel a cikkek új száma 35, és ez kisebb a küszöbérték mennyiségénél, a helyen automatikusan létrejön a ciklikus leltározási munka.

### <a name="schedule-cycle-counting-work"></a>Ciklikus leltározás ütemezése

Beütemezhet ciklikus leltározási terveket, hogy a leltározási munkát azonnal, vagy időszakosan hozza létre. Ciklikus leltározási tervek beállításával szabályozható a ciklikus leltári munkához létrehozott munkagyűjtő, a különböző helyeken lévő cikkekhez létrehozott ciklikus leltárok maximális száma, és a következő leltárig hátralévő napok száma egy raktárban. Például egy cikk rendelkezésre áll három helyen a raktárban, és ciklikus leltárok maximális számának beállítása **2**. Ebben az esetben amikor futtatja a leltározási tervet, akkor az két ciklikus leltározást hoz létre azon két helyhez, ahol jelen van a cikk. Másik példa lehet a ciklikus leltárok közötti napok számának megadása **5** értékre. Ebben az esetben a ciklikus leltári munka öt naponként jön létre. Azonban ha a ciklikus leltározási munka feldolgozása megtörténik a 3. napon, akkor a következő ciklikus leltározási munka öt nappal az utolsó ciklikus leltár után jön létre, a 8. napon.

## <a name="create-cycle-counting-work-manually"></a>Ciklikus leltár manuális létrehozása
Ciklikus leltározási munka manuális létrehozásához használhatja a **Ciklikus leltározási munka cikk szerint** vagy a **Ciklikus leltározási munka hely szerint** oldalakat. Megadhatja a létrehozandó ciklikus leltárok maximális számát. Például, ha a raktárvezető **5** értéket határoz meg, akkor a ciklikus leltározási munka öt helyen fog létrejönni, akkor is, ha a cikk tíz helyen található meg. Kiválaszthat továbbá egy munkagyűjtő azonosítót, amelyet a ciklikus leltározási munka azonosítóihoz rendel. Miután egy munkagyűjtő azonosítója fel lett dolgozva a ciklikus leltározáshoz, a munkagyűjtőhöz rendelt ciklikus leltározási munka azonosítói csoportosan lesznek feldolgozva.

## <a name="perform-a-cycle-count-by-using-a-mobile-device"></a>Ciklikus leltár végrehajtása mobileszköz használatával
A ciklikus leltározási munkát többféle módszerrel is fel lehet dolgozni a Finance and Operations használatával egy mobileszközön:

-   **Felhasználó által irányított** – A dolgozó megadhatja egy **Nyitott** állapotú ciklikus leltározási munka azonosítóját.
-   **Rendszer által irányított** – A Finance and Operations hozzárendeli egy ciklikus leltározási munka azonosítóját a dolgozóhoz.
-   **Ciklikus leltározás csoportosítása** – A dolgozó csoportosíthatja az adott helyhez, zónához vagy munkagyűjtőhöz rendelt ciklikus leltári munkák azonosítóit.
-   **Eseti ciklikus leltár** – A dolgozó ciklikus leltározási munka létrehozása nélkül is bármikor megszámolhatja a raktárhelyen lévő cikkeket. Az eseti ciklikus leltározás végrehajtásához egy helyen, a dolgozó megadja a hely azonosítóját.

Az alábbi példa azt mutatja be, hogyan tud eseti ciklikus leltározást végrehajtani mobileszköz segítségével. Az eszköz képernyőjén megjelenített utasítások eltérőek lehetnek, a menüelem eseti leltárra vonatkozó beállításaitól függően.

1.  A mobileszközön válassza ki a menüelemet az eseti ciklikus leltározási munka feldolgozásához.
2.  Regisztrálja a helyet, amelyen végre akarja hajtani az eseti leltárt.
3.  Regisztrálja, majd erősítse meg a cikkszámot és a leltározott cikkek mennyiségét. **Megjegyzés:** A **Dolgozó** oldalon meghatározott paraméterektől függően, a ciklikus leltározási munka **Ellenőrzésre vár** vagy **Zárt** állapotúra frissül a **Minden munka** oldalon.
4.  Választható: Ismételje meg a 3. lépést a helyen fennmaradó további cikkekre, és erősítse meg, hogy nincsenek további megszámolandó cikkek.

## <a name="resolve-cycle-counting-differences"></a>A leltározási eltérések feloldása
A leltározási eltérés akkor fordul elő a következő esetekben, ha a **ciklikusleltár-felügyelő** beállítás **Nem** értékre van állítva a munkafelhasználó azonosítójában:

-   A számolt érték nincs a **Munka felhasználók** oldalon lévő **Maximális százalékarány korlátja** vagy **Maximális mennyiségi korlát** mezőben megadott eltérési határokon belül. Tegyük fel például, hogy egy helyen az aktuális készletmennyiség 50, a munkafelhasználóhoz tartozó eltérési határérték pedig 10. Ha a munkafelhasználó nem 40 és 60 közötti értéket ír be, akkor eltérés keletkezik.
-   A számolt érték eltér az aktuális készlet mennyiségétől, és nincsenek eltérési határértékek beállítva.

A számolt érték eltéréseit módosíthatja, majd elfogadhatja a számolt értéket a **Ciklikus leltározás ellenőrzése függőben** oldalon. A cikkmennyiség módosított száma jóváhagyható az **Aktuális készlet hely szerint** oldalon. Ha az eltérés nem hagyható jóvá, akkor a számolt érték elutasításra kerül.

# <a name="see-also"></a>Lásd még
[Mobileszköz konfigurálása raktári munkához](configure-mobile-devices-warehouse.md)




