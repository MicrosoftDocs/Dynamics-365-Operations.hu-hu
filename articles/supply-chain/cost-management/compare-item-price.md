---
title: Cikkárak tárhelyének összehasonlítása jelentés
description: Útmutató a Cikkárak tárhelyének összehasonlítása jelentés létrehozásához, majd az eredmény böngészéséhez és/vagy exportálásához.
author: AndersGirke
manager: tfehr
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, InventItemPriceCompareStorage, InventItemPriceCompareStorageDetailsChart, InventItemPriceCompareStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 6554aec1991080f4a14aedb3440ff3dfd32e9b61
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983967"
---
# <a name="compare-item-prices-storage-report"></a>Cikkárak tárhelyének összehasonlítása jelentés

[!include [banner](../includes/banner.md)]

Ez a témakör mutatja be a **Cikkárak tárhelyének összehasonlítása** jelentés futtatását, és a kimenet digitális elérhetővé tételét, vagy interaktív oldalként a Dynamics 365 Supply Chain Management szolgáltatásban, vagy exportált dokumentumként számos formátum egyikében.

Ha a jelentést a böngészőben tekinti meg, az oszlopok és az összesítő egyenlegek dinamikusan módosulnak, attól függően, hogy milyen elrendezés van beállítva. Lehetőség van az eredmények rendezésére, szűrésére, az adatok leásására és további részletekre.

A jelentés eredményeit a rendszer a **Cikkárak összehasonlítása** adatentitásban tárolja, amelyet szűrhet és exportálhatja az eredményeket CSV vagy Microsoft Excel-formátumban.

A **Cikkárak tárhelyének összehasonlítása** jelentése olyan esetekben hasznos, amikor a kimenet sok sort tartalmaz. Például a kimenet számos sort tartalmaz, ha több mint 40 000 cikk van, amelynek cikkára függőben van a költségszámítási verzióban.

## <a name="enable-compare-item-prices-storage"></a>Cikkárak tárhelyének összehasonlításának engedélyezése

A funkció használata előtt engedélyeznie kell azt saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén engedélyezéséhez. Itt a funkció a következőként szerepel:

- **Modul** – Költségkezelés
- **Funkció neve** – Cikkárak tárhelyének összehasonlítása

## <a name="generate-a-compare-item-prices-storage-report"></a>Cikkárak tárhelyének összehasonlítása jelentés létrehozása

A következő lépéseket követve létrehozhatja és tárolhatja a **Cikkárak tárhelyének összehasonlítása** jelentést:

1. Lépjen a **Költségkezelés > Lekérdezések és jelentések > Előre megadott költségjelentések > Cikkárak tárhelyének összehasonlítása** pontra.

1. Válassza az **Új** parancsot a **cikkek árának összehasonlítása** panel megnyitásához. A következő beállítások megadásával meghatározhatja, hogy mely árakat kell összehasonlítani a jelentésben:

    - A **Paraméterek** gyorslapon adjon meg egy egyedi **nevet** a jelentésnek, és használja a **Összehasonlítandó függő árak** és az **Összehasonlításban használt árak** szakaszok mezőit, és határozza meg, hogy mely árak és dátumok összehasonlíthatók.
    - A **szerepeltetni kívánt rekordok** gyorslapján állítson be szűrőket és korlátokat a jelentésben szerepeltetni kívánt adatok meghatározásához.
    - A **Futtatás a háttérben** gyorslapon állítsa be a jelentés létrehozásának módját, idejét és gyakoriságát.
    > [!NOTE]
    > Ez a jelentés mindig a kötegelt feladat részeként hajtható végre.

1. Az **ok** gombra kattintva alkalmazza a beállításokat, és zárja be az ablakot.

1. A kötegelt feladat befejezése után megjelenik a **Cikkárak tárhelyének összehasonlítása** oldal listájában. A jelentés megtekintéséhez előfordulhat, hogy frissítenie kell a lapot.

## <a name="explore-the-compare-item-prices-storage-report"></a>Cikkárak összehasonlítása tárolási jelentés megismerése

Miután létrehozta a jelentést, a következők szerint bármikor megtekintheti és kivizsgálhatja:

1. Lépjen a **Költségkezelés > Lekérdezések és jelentések > Előre megadott költségjelentések > Cikkárak tárhelyének összehasonlítása** pontra.

1. Válasszon ki egy jelentést a listából.

1. Válasszon az alábbi lehetőségek közül:

    - Ha áttekintést szeretne kapni a jelentés eredményeiről, válassza az **áttekintés** elemet.
    - Válassza a **Részletek megtekintése** elemet a jelentés részletesebb nézetéhez.

1. A kijelölt nézet megnyitása után a következőket teheti:

    - Válassza ki majdnem bármely oszlop fejlécét úgy, hogy az adott oszlopban szereplő értékek alapján rendezze vagy szűrje a táblát, ugyanúgy, mint az Supply Chain Management legtöbb szabványos képernyőjén. Ne feledje, hogy a **nettó módosítási ár %** oszlopot nem lehet rendezni vagy szűrni, mert egy számított mező.
    - A **dimenziók megjelenítésének** kiválasztásával megnyithatja azt a képernyőt, ahol megadhatja, hogy mely dimenzió oszlop szerepeljen a képernyőn. Ha menteni szeretné ezeket a beállításokat, állítsa **Igen** értékre a **Mentés beállítását**, hogy a rendszer a jelentés következő megnyitásakor megőrződik. Az **ok** gombra kattintva alkalmazza a beállításokat, és zárja be.
    - Jelöljön ki egy sort a képernyőn, majd válassza a **Részletek megtekintése** parancsot a kiválasztott cikk további adatainak megtekintéséhez. Innen leáshat az adatokba.
    - Jelöljön ki egy sort a képernyőn, majd válassza az **Összehasonlítási diagram megtekintése** lehetőséget, ha a kiválasztott cikkhez kapcsolódóan az eredmények interaktív grafikus ábrázolását szeretné látni. Ezek az eredmények a diagramok és diagramok jelmagyarázatának különböző grafikus elemeinek kiválasztásával tekinthetők meg.
    - Jelöljön ki egy sort a képernyőn, majd válassza a **Számítási részletek megtekintése** parancsot a kiválasztott cikkhez kapcsolódó számítások megtekintéséhez. Innen leáshat az adatokba.

## <a name="export-the-compare-item-prices-storage-report"></a>Cikkárak összehasonlítása tárolási jelentés exportálása

A rendszer minden létrehozott jelentést a **Cikkárak összehasonlítása** adatentitásban tárol. A Supply Chain Management szabványos adatkezelési funkcióival exportálhat adatokat ebből az entitásból bármely támogatott adatformátumba, például CSV- vagy Microsoft Excel-formátumba.

A következő példa bemutatja, hogyan lehet exportálni egy **Cikkárak tárhelyének összehasonlítása** jelentést:

1. Lépjen a **Rendszerfelügyelet > Munkaterületek > Adatkezelés** elemre.

1. Válassza az **exportálás** gombot az **Adatkezelés** részben.

1. Megjelenik az **Exportálás** lap, amelyen beállíthatja az exportálási feladatot. A kezdő művelet a **csoport nevének** megadása.

1. A **Kiválasztott entitások** szakaszban válassza az **Entitás hozzáadása** lehetőséget a párbeszédpanel megnyitásához, amelyen beállíthatja a következő beállításokat:

    - **Entitás neve** – Válassza a **Cikkárak összehasonlítása** lehetőséget.
    - **Cél-adatformátum** – válassza ki az exportáláshoz használni kívánt formátumot.

1. A **Hozzáadás** gomb kiválasztásával új sort adhat hozzá, majd a **Bezárás** paranccsal bezárhatja a párbeszédpanelt.

1. Általában egyszerre csak egy jelentést exportál. Ehhez be kell állítania egy **Szűrőt** a **Lekérdezés** ablaktáblához hozzáadott sorhoz. Ezzel megadhatja, hogy mely jelentések szerepeljenek az exportban szerepeltetni kívánt **Cikkárak összehasonlítása** entitásban. Egyetlen jelentés exportálásához adja meg a következő szűrőbeállításokat:

    - A **tartomány** lapon válassza a **Hozzáadás** lehetőséget új sor hozzáadásához.
    - A **Tábla** beállítást állítsa **Cikkárak összehasonlítása** értékre.
    - A **Származtatott tábla** beállítást állítsa **Cikkárak összehasonlítása** értékre.
    - Állítsa a **Mező** értékét a szűréshez használt mezőre. Általában a **Végrehajtási nevet** vagy a **Végrehajtási időt** fogja használni.
    - Állítsa a **Feltétel** értékét a megfigyelni kívánt értékre a kiválasztott mezőből (vagy a jelentés neve, vagy a jelentés létrehozási ideje).
    - Ha szükséges, vegyen fel több sort a **Tartomány** táblába addig, amíg nem egyedileg azonosította a keresett jelentést.

1. Az **ok** gombra kattintva mentse a beállításokat, és zárja be.

1. Az exportálási beállítások mentéséhez válassza a **Mentés** elemet.

1. Nyissa meg az **Exportálási beállítások** lapot, és válassza az **Exportálás most** lehetőséget az exportfájl létrehozásához.

1. Megjelenik a **Végrehajtási összesítés** lap, amelyen megtekintheti az exportálási feladat állapotát, valamint az exportált entitások listáját. Válassza a **Cikkárak összehasonlítása** entitást az **Entitás feldolgozási állapota** terület listájából, majd válassza a **Fájl letöltése** elemet az adott entitásból exportált adatok letöltéséhez.

Ha további tájékoztatást szeretne arról, hogyan lehet az adatkezelést az adatok exportálására használni, akkor lásd: [Adatimportálási és-exportálási feladatok – áttekintés](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]