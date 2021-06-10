---
title: BYOD ütemezett kötegelt feladatok optimalizálása
description: Ez a témakör azt mutatja be, hogyan lehet optimalizálni a teljesítményt a saját adatbázis használata (BYOD) szolgáltatás használata során a Microsoft Dynamics 365 Human Resources alkalmazással.
author: andreabichsel
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: Platform update 36
ms.openlocfilehash: ed3ebbf09403090a1173c3cda1a4b11b74419b90
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052673"
---
# <a name="optimize-byod-scheduled-batch-jobs"></a>BYOD ütemezett kötegelt feladatok optimalizálása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör azt mutatja be, hogyan lehet optimalizálni a teljesítményt a saját adatbázis használata (BYOD) szolgáltatás használata során. A BYOD-funkcióval kapcsolatos további tudnivalókat lásd: [Használja saját adatbázisát (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

## <a name="performance-considerations-for-data-export"></a>Az adatexportálással kapcsolatos teljesítményszempontok

Az entitások a céladatbázisba történő közzététele után az **Adatkezelés** munkaterületen az Exportálási funkció segítségével mozgathatja az adatokat. Az Exportálás funkció segítségével definiálhat egy vagy több entitást tartalmazó adatáthelyezési feladatot. Az adatexportálással kapcsolatos további tudnivalókat lásd: [Adatimportálási és -exportálási feladatok áttekintése](../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

Az **Exportálás** lapon különböző adatformátumokba, például vesszővel tagolt (CSV-fájl) exportálhat adatokat. Ez a lap más célhelyként is támogatja az SQL-adatbázisokat is.

Olyan adatprojektet hozhat létre, amely több entitással rendelkezik, és kötegelt feladattal ütemezheti az adatprojekt futtatását. Ha bejelöli a **Kötegelt exportálás** beállítást, akkor az adatexportálási feladatot ütemezésheti periodikus futtatáshoz.

A BYOD-export teljes megbízhatóságának megőrzéséhez elővigyázatosnak kell lennie, amikor több entitást ad hozzá egy exportálási projekthez. Amikor meghatározza az ugyanahhoz a projekthez hozzáadandó entitások számát, vegye figyelembe a következő paramétereket:

- Az entitások összetettsége
- A várható adatmennyiség entitásonként
- A munka szintjén történő exportálás befejezéséhez szükséges teljes idő

A legjobb teljesítmény érdekében ne adjon több száz entitást egyetlen projekthez. Javasoljuk, hogy több feladatot hozzon létre, amelyek mindegyike kevesebb entitást tartalmaz.

## <a name="scheduling-byod-batch-jobs"></a>BYOD kötegelt feladatok ütemezése

A Microsoft Dynamics 365 Human Resources felhasználóira gyakorolt hatás csökkentéséhez futtassa a BYOD kötegelt feladatait éjszaka vagy munkaidő után. Ellenőrizze az ismétlődő kötegelt feladatok időzónáját. Előfordulhat, hogy egyes kötegelt feladatok a Pacific standard Time (PST) időzónát használják.

A teljesítménnyel kapcsolatos problémák elkerüléséhez vegye figyelembe a következő tényezőket, amikor beállítja a BYOD kötegelt feladatok ütemezési gyakoriságát:

- Az egyes kötegelt feladatok végrehajtásához szükséges idő
- A BYOD adatokkal kapcsolatos üzleti igény

Állítsa be a kötegelt feladat gyakoriságát olyan értékre, amely biztosítja, hogy a feladat a következő ütemezett futási idő előtt jóval befejeződjön. Ne futtasson párhuzamosan több feladatot, mert ez a megközelítés negatívan befolyásolhatja a Human Resources teljesítményét.

A legjobb teljesítmény érdekében a BYOD kötegelt feladatait mindig az **Exportálás** lap **Kötegelt exportálás** beállításával ütemezze. Ne ütemezzen ismétlődő exportokat a **Kezelés \> Ismétlődő adatfeladatok kezelése** helyen.

## <a name="incremental-export"></a>Növekményes exportálás

Ha hozzáad egy entitást az adatexportáláshoz, akkor lehetősége van egy növekményes küldés (export) vagy egy teljes küldés elemre. A teljes küldés törli a BYOD-adatbázis egy entitásának összes meglévő rekordját. Ezután beszúrja a rekordok aktuális készletét az Emberi erőforrások entitásból.

A növekményes küldés végrehajtásához az egyes entitásokhoz be kell kapcsolni a változtatások nyomon követését az **Entitások** lapon. A további tudnivalókat lásd [A változások nyomon követésének engedélyezése az entitásokhoz](../fin-ops-core/dev-itpro/data-entities/entity-change-track.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

Ha kiválaszt egy növekményes küldést akkor az első küldés mindig egy teljes küldés. Az SQL ehhez az első küldéséhez képest követi nyomon a változásokat. Új rekord beillesztésekor, illetve rekord frissítésekor vagy törlésekor a változás a cél entitásban is megjelenik.

## <a name="time-outs"></a>Időtúllépések

Itt láthatók az BYOD-exportok alapértelmezett időtúllépései:

- Tíz perc a csonkolási műveletekhez
- Egy óra a bulk insert műveletekhez

Amikor a mennyiségek nagyok, előfordulhat, hogy az időtúllépési beállítások nem elegendőek. Ezek frissítéséhez nyissa meg az **Adatkezelés \> Keretrendszer paraméterei \> Saját adatbázis használata** menüpontot. Ezek a időtúllépések vállalatra jellemzőek, és az egyes vállalatoknál külön kell megadni.

## <a name="known-limitations"></a>Ismert korlátozások

A BYOD-funkciónak a következő korlátai vannak:

- A szinkronizálás során nem lehetnek aktív zárolások az adatbázishoz. Az aktív zárolások lassítják az írást, vagy az adatok nem exportálhatók a Azure SQL-adatbázisba.
- Összetett entitások nem exportálhatók saját adatbázisba. Jelenleg az összetett entitások nem támogatottak. Az összetett entitást alkotó egyéni entitásokat kell exportálnia. Ugyanakkor mindkét entitást ugyanabban az adatprojektben exportálhatja.
- Az egyedi kulcsokkal nem rendelkező entitások nem exportálhatók növekményes küldés használatával. Ezzel a korlátozással leginkább akkor találkozhat, ha néhány előre elkészített entitásból próbálja fokozatosan exportálni a rekordokat. Mivel ezeket az entitásokat úgy alakították ki, hogy engedélyezzék az adatok importálását, nem rendelkeznek egyedi kulccsal.

## <a name="troubleshooting"></a>Hibaelhárítás

### <a name="incremental-push-doesnt-work-correctly"></a>A növekményes küldés nem működik megfelelően

**Probléma:** Ha egy entitáshoz teljes küldést hajt végre, akkor a rekordok nagy készlete jelenik meg a BYOD,-ban amikor egy **kiválasztás** működési utasítást alkalmaz. Ha viszont egy növekményes küldést hajt végre, akkor csak néhány rekord jelenik meg a BYOD-ben. Úgy tűnik, mintha a növekményes küldés törölte az összes rekordot, és csak a módosított rekordokat adta volna hozzá a BYOD-hez.

**Megoldás:** Előfordulhat, hogy az SQL változáskövetési táblák nem a várt állapotban vannak. Ilyen típusú esetekben ajánlott kikapcsolni az entitás módosításának nyomon követését, majd újra bekapcsolni azt. A további tudnivalókat lásd [A változások nyomon követésének engedélyezése az entitásokhoz](../fin-ops-core/dev-itpro/data-entities/entity-change-track.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

### <a name="staging-tables-arent-clearing"></a>Az előkészítő táblák nem törlődnek

**Probléma**: A projekt előkészítésének használatakor az előkészítési táblák nem törlődnek megfelelően. Ezután a táblák adatai tovább nőnek, és teljesítménybeli problémákat okoznak.

**Megoldás:** Az előző hét nap előzményeinek száma az előkészítési táblákban van karbantartva. Az **Importálás, exportálása előkészítésének törlése** kötegelt feladat automatikusan törli a hét napnál régebbi előzményadatokat az előkészítési táblákból. Ha a feladat beragad, a táblák nem fognak megfelelően törlődni. A kötegelt feladat újraindítása folytatja az előkészítési táblák automatikus törlését.

## <a name="see-also"></a>Lásd még

[Adatkezelés – áttekintés](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)<br>
[Használja saját adatbázisát (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)<br>
[Adatimportálási és -exportálási feladatok áttekintése](../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)<br>
[Változáskövetés engedélyezése az entitások esetében](../fin-ops-core/dev-itpro/data-entities/entity-change-track.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
