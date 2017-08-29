--- 
title: "Formátum létrehozása számláláshoz és összegzéshez az elektronikus jelentéskészítéshez (ER)"
description: "Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: a52aade62b0d05a41e22aa9e9a474999af725606
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="create-formate-for-counting-and-summing-for-electronic-reporting-er"></a>Formátum létrehozása számláláshoz és összegzéshez az elektronikus jelentéskészítéshez (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


