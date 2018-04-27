--- 
title: "Számlálási és összegzési formátumának létrehozása"
description: "Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7613b78d4a9ab63f5be9773a8699fe3ed94636eb
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="create-format-for-counting-and-summing"></a>Számlálási és összegzési formátumának létrehozása 

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján. Ezeket a lépéseket bármely vállalatban végrehajthatja.

Hajtsa végre az alábbi lépéseket: Először hajtsa végre a „Konfiguráció szolgáltatói létrehozása és aktívként történő megjelölése” eljárás lépéseit.

Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Hozzáférés a Microsoft által biztosított konfigurációk listájához
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
    * Győződjön meg róla, hogy a Litware, Inc. szolgáltató elérhető és aktívként megjelölt legyen.  
2. Válassza ki a Litware, Inc. szolgáltatót.
3. Kattintson a Tárházak gombra.
    * Ha már létezik egy „Üzemi erőforrások” típusú tár, hagyja ki az aktuális altevékenység többi lépését.  
4. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
5. A Konfiguráció tárházának típusa mezőbe írja be az „Üzemi erőforrások” szöveget.
6. Kattintson a Tárház létrehozása lehetőségre.
7. Kattintson az OK gombra.

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a>A Microsoft által biztosított Intrastat konfigurációk beszerzése
1. Kattintson a Megnyitás gombra.
2. A fastruktúrában jelölje ki a következőt: „Intrastat modell\Intrastat (DE)”.
3. Kattintson az Importálás gombra.
    * Kattintson az Importálás gombra a kijelölt konfiguráció 1.1-es verziójának esetében.  
4. Kattintson az Igen gombra.
5. Zárja be a lapot.
6. Zárja be a lapot.
7. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
8. A fastruktúrában bontsa ki az „Instrastat modell” elemet.
9. A fastruktúrában jelölje ki a következőt: „Intrastat modell\Intrastat (DE)”.


