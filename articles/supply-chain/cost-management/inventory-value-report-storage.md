---
title: Készletérték-tárolási jelentés
description: Ez a témakör mutatja be a Készletérték-tárolási jelentés futtatását, és a kimenet digitális elérhetővé tételét, vagy interaktív oldalként a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban, vagy exportált dokumentumként számos formátum egyikében.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventValueProcess, InventValueReportSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: f50318e0a955d8244ba854aa1fd73ad7532b9198
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759568"
---
# <a name="inventory-value-storage-report"></a>Készletérték-tárolási jelentés

Ez a témakör mutatja be a **Készletérték-tárolási** jelentés futtatását, és a kimenet digitális elérhetővé tételét, vagy interaktív oldalként a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban, vagy exportált dokumentumként számos formátum egyikében.

Ha a jelentést a böngészőben tekinti meg, az oszlopok és az összesítő egyenlegek dinamikusan módosulnak a konfigurált elrendezéstől függően. Lehetőség van az eredmények rendezésére, szűrésére, az adatok leásására és további részletekre.

A jelentés eredményeit a rendszer a **Készletérték** adatentitásban tárolja. Ezért az eredményeket a következő formátumra szűrheti, illetve exportálhatja: vesszővel tagolt értékek (CSV) vagy Microsoft Excel-formátum.

A **készletérték-tárolási** jelentés akkor hasznos, ha a kimenet számos sort tartalmaz. Tegyük fel például, hogy 50 000 cikket tartalmaz, és a 300 üzleteket raktárakként hozták létre. Ebben az esetben, ha a készletzáró egyenlegeket cikkek, telephely és raktár szerint állítja be, akkor a kimenet számos sort tartalmaz.

> [!NOTE]
> A jelentés nem tartalmaz a jelentés elrendezésében megadott részösszegeket. Nem fogja tartalmazni a főkönyvi egyenlegeket, még akkor sem, ha a jelentés elrendezésében meg vannak határozva. A főkönyvvel való egyeztetést a főkönyvi kivonatok segítségével kell végrehajtani.

## <a name="turn-on-the-inventory-value-storage-feature"></a>A készletérték-tárolási funkció bekapcsolása

A **készletérték-tárolási** jelentés létrehozása előtt be kell kapcsolni a rendszerben a funkciót. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul** – Költségkezelés
- **Funkció neve** – A készletérték-tárolás

## <a name="generate-an-inventory-value-storage-report"></a>Készletérték-tárolási jelentés létrehozása

A következő lépéseket követve létrehozhatja és tárolhatja a **Készletérték-tárolási** jelentést.

1. Lépjen a **Költséggazdálkodás \> Lekérdezések és jelentések \> Készletérték jelentés tárhelye**.
1. Válassza az **Új** lehetőséget.
1. A megjelenő **Készletérték** párbeszédpanelen állítsa be a következő értékeket a jelentésben szerepeltetni kívánt rekordok meghatározásához:

    - A **paraméterek** gyorslapon adjon meg egy egyedi nevet a jelentéshez, és használja a **dátumtartomány** szakasz mezőit a jelentésben szerepeltetni kívánt rekordok meghatározásához. A dátumtartomány meghatározásához válasszon egyelőre beállított tartományt (a jelentés létrehozási dátumához képest) a **Dátumtartomány kódja** mezőben, vagy válasszon meghatározott dátumokat a **Kezdő dátum** és **Záró dátum** mezőkben.
    - A **szerepeltetni kívánt rekordok** gyorslapján állítson be szűrőket és korlátokat a jelentésben szerepeltetni kívánt adatok meghatározásához.
    - A **Futtatás a háttérben** gyorslapon adja meg hogyan, mikor és milyen gyakran jöjjön létre a jelentés.

    > [!NOTE]
    > Ez a jelentés mindig a kötegelt feladat részeként futtatható.

1. Az **OK** gombra kattintva alkalmazza a beállításokat, és zárja be a párbeszédpanelt.

A kötegelt feladat befejezése után a jelentés megjelenik a **készletérték jelentés tárhelye** lapján. A jelentés megtekintéséhez előfordulhat, hogy frissíteni kell az oldalt.

## <a name="explore-an-inventory-value-storage-report"></a>Készletérték-tárolási jelentés megismerése

Miután létrehozta a jelentést, a következő lépések végrehajtásával bármikor megtekintheti és kivizsgálhatja:

1. Lépjen a **Költséggazdálkodás \> Lekérdezések és jelentések \> Készletérték jelentés tárhelye**.
1. A listában válasszon ki egy jelentést.
1. A jelentés tartalmának megjelenítéséhez jelölje be a **Részletek megtekintése** elemet.
1. A jelentés a következő lépések bármelyikével vizsgálható:

    - A Supply Chain Management legtöbb szabványos képernyőjén válassza ki majdnem bármely oszlop fejlécét úgy, hogy az adott oszlopban szereplő értékek alapján rendezze vagy szűrje a rácsot.
    - A **szűrő** mező használatával a jelentés tetszőleges értékkel szűrheti a különböző elérhető oszlopok bármelyikét.
    - Használja a Nézet menüt (a **szűrő** mező felett) a rendezési és szűrési beállítások kedvenc kombinációinak mentéséhez és betöltéséhez.

## <a name="export-an-inventory-value-storage-report"></a>Készletérték-tárolási jelentés exportálása

A rendszer minden létrehozott jelentést a **Készletérték** adatentitásban tárol. A Supply Chain Management szabványos adatkezelési funkcióival exportálhat adatokat ebből az entitásból bármely támogatott adatformátumba, például CSV- vagy Excel-formátumba.

A következő példa bemutatja, hogyan lehet exportálni egy **készletérték jelentés** jelentését.

1. Ugrás a **Rendszerfelügyelet \> Munkaterületek \> Adatkezelés** elemre.
1. Az **Importálás és exportálás** területen válassza az **exportálás** csempét. 
1. A megjelenő **exportálás** oldalon be kell állítani az exportálási feladatot. Először adjon nevet a feladatnak.
1. A **kiválasztott entitások** területen válassza az **entitás hozzáadása** elemet.
1. A megjelenő párbeszédpanelen a következő mezőket állítsa be:

    - **Entitás neve** – Válassza a **Készletérték** elemet.
    - **Cél-adatformátum** – válassza ki azt a formátumot, amelybe az adatokat exportálni szeretné.

1. A **Hozzáadás** gomb kiválasztásával új sort adhat hozzá, majd a **Bezárás** paranccsal bezárhatja a párbeszédpanelt.
1. Általában egyszerre csak egy jelentést exportál. Egyetlen jelentés exportálásához állítsa be azt a sort, amelyet a **lekérdezés** párbeszédpaneléhez hozzáadott. Ily módon meghatározhatja, hogy melyik jelentés szerepeljen a **készletérték** entitásból az exportálásban. Kövesse ezeket a lépéseket, hogy egyetlen jelentés exportálásához adja meg a következő szűrőbeállításokat:

    1. A **tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához.
    2. A **Tábla** mezőt állítsa **Készletérték** értékre.
    3. A **Származtatott tábla** mezőt állítsa **Készletérték** értékre.
    4. Állítsa a **Mező** mező értékét a szűréshez használt mezőre. Általában a **végrehajtás neve** mezőt és/vagy a **végrehajtási idő** mezőt fogja használni.
    5. A **feltételek** mezőt a kiválasztott mezőben keresendő értékre állíthatja. (Ha az előző lépésben bejelölte a **Végrehajtás neve** mezőt, ez az érték lesz a jelentés neve. Ha bejelölte a **végrehajtási idő** mezőt, akkor ez az az időpont, amikor a jelentés létrejött.)
    6. Vegyen fel több sort szükség szerint a **Tartomány** lapra addig, amíg nem egyedileg azonosította a keresett jelentést.

1. Az **OK** gombra kattintva mentse a beállításokat, és zárja be a párbeszédpanelt.
1. Az exportálási beállítások mentéséhez válassza a **Mentés** elemet.
1. Az **Exportálási beállítások** lapon válassza az **Exportálás most** lehetőséget az exportfájl létrehozásához.
1. Megjelenik a **Végrehajtási összesítés** lap, amelyen megtekintheti az exportálási feladat állapotát, valamint az exportált entitások listáját. Válassza az **Entitásfeldolgozái állapot** szakaszban a **Készletérték** entitást a listájából, majd válassza a **Fájl letöltése** elemet az adott entitásból exportált adatok letöltéséhez.

Ha további tájékoztatást szeretne arról, hogyan lehet az adatkezelést az adatok exportálására használni, akkor lásd: [Adatimportálási és-exportálási feladatok – áttekintés](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).
