---
title: "A banki egyeztetés MT940 behozatali – speciális entitás összetett adatok frissítése"
description: "Egy sorszámot kell hozzáadni a banki kivonat importálási entitásához az MT940 formátum támogatásához."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer
ms.search.scope: Operations, Core
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: bec019d218d80ba059d5a1c232072f46b1ae3ee2
ms.openlocfilehash: 3a4868045a12f7210a4d3924b4a335a52206341a
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a>A banki egyeztetés MT940 behozatali – speciális entitás összetett adatok frissítése

Egy sorszámot kell hozzáadni a banki kivonat importálási entitásához az MT940 formátum támogatásához. 

A következő lépések segítségével adja hozzá a banki kivonat importálási entitását az MT940 formátum támogatásához.

1.  Állítsa össze és szinkronizálja a következőket:
    -   Összetett entitás\\BankStatementImportEntity
    -   Entitás\\BankStatementBalanceEntity
    -   Entitás\\BankStatementDocumentEntity
    -   Entitás\\BankStatementEntity
    -   Entitás\\BankStatementLineEntity
    -   Táblák\\BankStatementStaging

2.  Adatkezelés\\adatok projektek.
    1.  MT940 importálás projekt(ek) betöltése
        1.  XLST megváltoztatása.
            -   Kattintson a **Térkép megtekintése** menüpontra.
            -   Kattintson a **Térkép megtekintése** menüpontra a banki kivonat dokumentumán.
            -   Kattintson az **Átalakítások** lehetőségre.
            -   Törölje a BankReconiliation-to-Composite.xslt fájlt.
            -   Adja hozzá a BankReconiliation-to-Composite.xslt új verzióját.

        2.  Jelenítse meg a **Sorszámot** a **Forrásadatok** elrendezésben.
            1.  Forrásoldali adatformátum = XML-elem.
            2.  Entitás neve = banki kivonat
            3.  Feltöltési adatfájl = SampleBankCompositeEntity.xml új verziója.
            4.  Kattintson az **Igen** gombra a meglévő fájl felülírásához.
            5.  Kattintson az **Igen** egy új hozzárendelés létrehozásához.
            6.  Győződjön meg róla, hogy a S**orszám** hozzárendelése kész van-e.
                -   Kattintson a **Térkép megtekintése** menüpontra az entitás kivonatán.
                -   Ellenőrizze, hogy a **sorszám** hozzá van-e rendelve a forrásból az előkészítéshez.

3.  Importálja az új kivonatot.



