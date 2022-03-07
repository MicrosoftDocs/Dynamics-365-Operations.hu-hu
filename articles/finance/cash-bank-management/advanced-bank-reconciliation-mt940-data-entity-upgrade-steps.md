---
title: Speciális banki egyeztetés MT940 importálása - összetett adatentitás frissítése
description: Egy sorszámot kell hozzáadni a banki kivonat importálási entitásához az MT940 formátum támogatásához.
author: panolte
ms.date: 06/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c891a5139ff7de85e6762513f57236e24f1644529d7825c9ce5e1dfda50fbad8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739383"
---
# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a>Speciális banki egyeztetés MT940 importálása - összetett adatentitás frissítése

[!include [banner](../includes/banner.md)]

Egy sorszámot kell hozzáadni a banki kivonat importálási entitásához az MT940 formátum támogatásához. 

A következő lépések segítségével adja hozzá a banki kivonat importálási entitását az MT940 formátum támogatásához.

1.  Állítsa össze és szinkronizálja a következőket:
    -   Összetett entitás\\BankStatementImportEntity
    -   Entitás\\BankStatementBalanceEntity
    -   Entitás\\BankStatementDocumentEntity
    -   Entitás\\BankStatementEntity
    -   Entitás\\BankStatementLineEntity
    -   Táblázatok\\BankStatementStaging

2.  Adatok kezelése\\adatprojektek.
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
            6.  Győződjön meg róla, hogy a S **orszám** hozzárendelése kész van-e.
                -   Kattintson a **Térkép megtekintése** menüpontra az entitás kivonatán.
                -   Ellenőrizze, hogy a **sorszám** hozzá van-e rendelve a forrásból az előkészítéshez.

3.  Importálja az új kivonatot.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]