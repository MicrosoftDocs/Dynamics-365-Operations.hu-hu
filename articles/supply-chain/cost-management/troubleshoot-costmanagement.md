---
title: Költségkezelés – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet javítani a költségkezelés használata során felmerülő problémákat.
author: riluan
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: dceaca64132857d796a16c2450a372ba05712cf5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262453"
---
# <a name="troubleshoot-cost-management"></a>Költségkezelés – hibaelhárítás

Ez a témakör azt mutatja be, hogyan lehet javítani a költségkezelés használata során felmerülő problémákat.

## <a name="functional-gaps-between-the-inventory-valueaging-reports-and-their-storage-versions"></a>A készletérték/korosítási jelentések és tárolási verzióik közötti működési hézagok

A [kKészletkorosítási jelentés tárolása](inventory-aging-report-storage.md) és a [Készletérték-tárolási jelentés](inventory-value-report-storage.md) funkció lehetővé teszik a Supply Chain Management számára, hogy megjelenítse a készlettranzakciók nagy mennyiségét. Minden esetben a jelentés eredményei a böngészés és az exportálás esetében kerülnek mentésre, ellentétben a jelentések nem tárolt verzióival. Előfordulhat azonban, hogy a jelentések nem tárolt verzióiban létező funkciók nem szerepelnek a tárolási verziókban. A következő alszakaszok összefoglalják a különbségeket, és megoldásokat kínálnak.

### <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>A tárolási jelentések nem tartalmazzák a részösszegeket, még akkor sem, ha engedélyezve vannak a jelentés elrendezésében.

A részösszegek problémákat okozhatnak az eredmény exportálásakor, különösen akkor, ha a felhasználók módosítják a rekordsorozatot.

A részösszegek ellenőrzéséhez exportálni lehet az eredményt Microsoft Excel. Ha azt szeretné, hogy a Supply Chain Managementen belül ellenőrizze a részösszegeket, használja [Funkciókezelést](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) és engedélyezze az *Új rácsvezérlő* és az *(előzetes verzió) csoportosítás a rácsokban* funkciókat, amelyek sokkal rugalmasabban használhatók a csoportosítási oszlop részösszegeinak megjelenítéséhez. További információkért lásd az [Rácsfunkciók](../../fin-ops-core/fin-ops/get-started/grid-capabilities.md) részt.

### <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>A készletérték-tárolási jelentés nem támogatja a főkönyvi fiók adatait

A főkönyvi kivonatot úgy futtathatja, hogy beolvassa a készletfiókok egyenlegét, és összehasonlítja a **Készletérték-tárolás** jelentéssel.

## <a name="warnings-or-errors-are-shown-when-changing-a-ledger-period-status-without-closing-inventory"></a>A figyelmeztetések és a hibák akkor jelennek meg, ha a főkönyvi időszaki állapotot a készlet zárása nélkül módosítja

A Microsoft a következő ellenőrzéseket vezette be annak érdekében, hogy megakadályozza a nem megfelelő időszakvégi feldolgozást a költségszámítással kapcsolatban. Ha a következő hibaüzenetek valamelyikét észleli, akkor a problémák megoldásával kapcsolatos további tudnivalókat lásd a [KB 4561987](https://fix.lcs.dynamics.com/Issue/Details?kb=4561987&bugId=445351&dbType=3&qc=f514f2adcddcddceec43af58c26ae8a9020effdc7cdfe085d9d0deeb8cc7b6a3) részben.

- Újraszámítást készül végrehajtani %1 (2019.02.10.). A rendszer az utolsó regisztrált újraszámítást egy előző időszakban, %2 (2019.01.20.) dátummal futtatta. Az %3 (2019.01.31.) egyeztetési időszak végén nem sikerült lezárni egy készlet végrehajtását. Ne felejtse el az %3 (2019.01.31.) időszak végének megfelelő készletet lezárni. A készletekre, az eladott áruk beszerzési értékére és az eltérésekre vonatkozó becslések nem lehetnek helyesek az alfőkönyv vagy a főkönyv modulban mindaddig, amíg nem történt meg a végrehajtás.

- A főkönyvi időszak állapotának módosítása erről: %1 erre: %2. Az %3 egyeztetési időszak végén nem sikerült lezárni a készlet végrehajtását. Az állapot módosítása előtt végre kell hajtania egy készletlezárást, amely az %3 időszak végével való egyeztetés előtt van. A készletekre, az eladott áruk beszerzési értékére és az eltérésekre vonatkozó becslések nem lehetnek helyesek az alfőkönyv vagy a főkönyv modulban mindaddig, amíg nem történt meg a végrehajtás. Jogi személy jelentette %4. Egyelőre ez csak tájékoztatási jellegű, de a jövőben ilyen műveletet kell végrehajtania.

- A %1 számlastruktúra módosult. Egy vagy több fő számla már %2 nem létezik. Ezeket a fő számlákat a %3 dátumra %4 dátummal van szükség. A %3 feladat folytatása előtt adja hozzá ezeket a fő számlákat a %1 számlastruktúrába. Egyelőre ez csak tájékoztatási jellegű, de a jövőben ilyen műveletet kell végrehajtania.

- Készletzárást készül végrehajtani %1 (2019.01.31.). Az %2 (2019.01.31.) egyeztetési időszak végén nem sikerült visszavezetéses költségelszámolás kiszámítását végrehajtani. Ne felejtse el végrehajtani az %3 (2019.01.31.) egyeztetési időszak végén végrehajtani a visszavezetéses költségelszámolás kiszámítását. A készletekre, az eladott áruk beszerzési értékére és az eltérésekre vonatkozó becslések nem lehetnek helyesek az alfőkönyv vagy a főkönyv modulban mindaddig, amíg nem történt meg a végrehajtás.

- Egy visszavezetéses költségelszámolás kiszámítását készül elvégezni %1 (2019.02.28.). A rendszer az utolsó regisztrált visszavezetéses költségelszámolási kiszámítást egy előző időszakban, %2 (2019.01.31.) dátummal futtatta. Az %3 (2019.01.31.) egyeztetési időszak végén nem sikerült lezárni egy készlet végrehajtását.
Ne felejtsen el egy %3 (2019.01.31.) időszak végének megfelelő készletet lezárni. A készletekre, az eladott áruk beszerzési értékére és az eltérésekre vonatkozó becslések nem lehetnek helyesek az alfőkönyv vagy a főkönyv modulban mindaddig, amíg nem történt meg a készletzárás.

## <a name="inventory-aging-report-discrepancies"></a>Készletkorosítási jelentés eltérései

A **Készletkorosítási jelentés** különböző értékeket jelenít meg különböző tárolási dimenziókban (például hely vagy raktár). A jelentési logikával kapcsolatos további tudnivalókat lásd: [Készletkorosítási jelentés példák és logika](inventory-aging-report.md).

## <a name="an-update-conflict-occurs-when-the-inventory-valuation-method-is-either-standard-cost-or-moving-average"></a>Frissítési ütközés történik, ha a készletellenőrző módszer elszámolóáras vagy mozgóátlag

Ha párhuzamosan ad fel olyan dokumentumokat, mint a készletnaplók, a beszerzési rendelési számlák vagy az értékesítési rendelés számlái a skálázhatóság és a teljesítmény érdekében, hibaüzenetet kaphat egy frissítési ütközésről, és előfordulhat, hogy néhány dokumentum nem lesz feladva. Ez a hiba akkor fordulha elő, ha a készletellenőrző módszer *elszámolóáras* vagy *mozgóátlag*. Mindkét módszer végleges költségszámítási módszer. Más szóval a végső költséget a feladáskor határozzák meg.

Ha a *Mozgóátlag* módszert használja, akkor a hibaüzenet hasonló ehhez a példához:

> Az arányos költségszámítás után nem várható xx.xx készletérték

Ha az *Elszámolóáras* módszert használja, akkor a hibaüzenet hasonló ehhez a példához:

> Az elszámolóár nem egyezik meg a frissítés utáni pénzügyi készletértékkel. Érték = xx.xx, mennyiség = yy.yy, elszámolóár = zz.zz

Amíg a Microsoft nem ad ki megoldást a probléma kiküszöbölésére, a hibák elkerüléséhez vagy csökkentéséhez fontolja meg a következő megoldások használatát:

- Adja fel újra a sikertelen dokumentumokat.
- Hozzon létre olyan dokumentumokat, amelyekhez kevesebb sor tartozik.
- Kerülje a decimális értékeket az elszámolóárban. Próbálja meg meghatározni az elszámolóárat úgy, hogy az **Ár mennyisége** mező *1-re* van állítva. Ha *1*-nél több **Ármennyiség** értéket kell megadnia, próbálja meg minimálisra csökkenteni a tizedesjegyek számát az elszámolóáron. (Ideális esetben kevesebb mint két tizedesjegynek kell lennie.) Például ne definiálja az olyan elszámolóár-beállításokat, mint például **Ár** = *10* és **Ármennyiség** = *3*, mivel a készletegység elszámolóárát 3.333333 értékben fogják létrehozni (ahol a tizedesérték ismétlődik).
- A dokumentumok többsége esetében lehetőleg ne legyen több olyan sor, amely a termék- és pénzügyi készletdimenziók ugyanazon kombinációját tartalmazza.
- Csökkentse a párhuzamos futások mértékét. (Ebben az esetben a rendszer gyorsabb lehet, mert kevesebb frissítési ütközés és újraküldés fordulhat elő.)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]