---
title: ER - A konfiguráció feltöltése a Lifecycle Services szolgáltatásba
description: A következő lépések leírják, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre új Elektronikus jelentés (ER) konfigurációt és hogyan töltheti fel a Microsoft Lifecycle Services (LCS) rendszerbe.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 19ae8820e5d4a798a5789e9632edb431fe9fede4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "335094"
---
# <a name="er-upload-a-configuration-into-lifecycle-services"></a>ER - A konfiguráció feltöltése a Lifecycle Services szolgáltatásba

[!include [task guide banner](../../includes/task-guide-banner.md)]

A következő lépések leírják, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre új Elektronikus jelentés (ER) konfigurációt és hogyan töltheti fel a Microsoft Lifecycle Services (LCS) rendszerbe.

Ebben a példában a mintavállalatra, a Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót, és feltölti az LCS rendszerbe. Ezeket a lépéseket a vállalatok között megosztott ER konfigurációkként hajthatók végre az egyes vállalatoknál. Hajtsa végre az alábbi lépéseket: Először hajtsa végre a „Konfiguráció szolgáltatói létrehozása és aktívként történő megjelölése” eljárás lépéseit. Az LCS rendszerbe való hozzáféréshez végre kell hajtani ezeket a lépéseket.

1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. Válassza ki a Litware, Inc. lehetőséget, és állítsa be aktívként.
3. Kattintson a Konfigurációk lehetőségre.

## <a name="create-a-new-data-model-configuration"></a>Új adatmodell-konfiguráció létrehozása
1. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
    * Egy olyan konfigurációt hoz létre, amely tartalmazza az elektronikus dokumentumokra vonatkozó minta adatmodellt. Később az LCS-be töltik fel ezen adatmodell konfigurációját.  
2. A név mezőben írja be a „Minta modell beállítása” szöveget.
    * Minta modell beállítása  
3. A Leírás mezőben írja be a „Minta modell beállítása” szöveget.
    * Minta modell beállítása  
4. Kattintson a Konfiguráció létrehozása lehetőségre.
5. Kattintson a Modelltervező lehetőségre.
6. Kattintson az Új lehetőségre.
7. A Név mezőbe írja be az „Belépési pont” szöveget.
    * Belépési pont  
8. Kattintson a Hozzáadás gombra.
9. Kattintson a Mentés gombra.
10. Zárja be a lapot.
11. Kattintson az Állapot módosítása elemre.
12. Kattintson a Befejezés gombra.
13. Kattintson az OK gombra.

## <a name="register-a-new--repository"></a>Új tárház regisztrálása
1. Zárja be a lapot.
2. Kattintson a Tárházak gombra.
    * Ez lehetővé teszi a Litware, Inc. tárházak listájának megnyitását. Konfigurációszolgáltató.  
3. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
    * Ez lehetővé teszi az új tárház hozzáadását.  
4. A Konfiguráció tárházának típusa mezőben válassza ki az LCS lehetőséget.
5. Kattintson a Tárház létrehozása lehetőségre.
6. A Projekt mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a kívánt LCS projektet. Hozzáféréssel kell rendelkeznie a projekthez.  
7. Kattintson az OK gombra.
    * Fejezze be az új tárház bejegyzést.  
8. A listában jelölje meg a kiválasztott sort.
    * Válassza ki az LCS tárházrekordot.  
    * Vegye figyelembe, hogy azon jelenlegi szolgáltatói jelentés jelölte meg a regisztrált tárházat, amely a tárházban megadható szolgáltató konfigurációját képezik és ennek megfelelően vannak feltöltve a kiválasztott LCS projektbe.  
9. Kattintson a Megnyitás gombra.
    * Nyissa meg a tárházat az ER konfigurációk listájának megtekintéséhez. Üres lesz, ha a projektet még nem használta az ER-konfigurációk megosztásához.  
10. Zárja be a lapot.
11. Zárja be a lapot.

## <a name="upload-configuration-into-lcs"></a>Konfigurációs feltöltése az LCS rendszerbe
1. Kattintson a Konfigurációk lehetőségre.
2. A fastruktúrában válassza ki a „Minta modell beállítása” lehetőséget.
    * Válassza ki a létrehozott, és már befejezett konfigurációt.  
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a „Befejezett” állapotú kijelölt konfiguráció verzióját.  
4. Kattintson az Állapot módosítása elemre.
5. Kattintson a Megosztás lehetőségre.
    * A konfiguráció állapota „Kész” állapotról „Megosztott” állapotra változik az LCS-ben történő közzétételkor.  
6. Kattintson az OK gombra.
7. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a „Megosztott” állapotú konfiguráció verziót.  
    * Vegye figyelembe, hogy a kiválasztott verzió állapota „Kész” állapotról „Megosztott” állapotra változott.  
8. Zárja be a lapot.
9. Kattintson a Tárházak gombra.
    * Ez lehetővé teszi a Litware, Inc. tárházak listájának megnyitását. Konfigurációszolgáltató.  
10. Kattintson a Megnyitás gombra.
    * Válassza ki a LCS tárházat és nyissa meg.  
    * Vegye figyelembe, hogy a kijelölt konfiguráció a kiválasztott projekt LCS eszközeként jelenik meg.  
    * Nyissa meg az LCS-t a következővel: https://lcs.dynamics.com. Nyissa meg a korábban a tárház regisztrálásához használt projektet, majd nyissa meg a projekt „Eszköztár” lehetőségét, és bontsa ki a „GER konfiguráció” eszköztár tartalmát - Elérhető lesz a feltöltött ER-konfiguráció. Vegye figyelembe, hogy a feltöltött LCS konfigurációt egy másik Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás példányába importálhatja, ha a szolgáltatók rendelkeznek hozzáféréssel ehhez az LCS projekthez.  

