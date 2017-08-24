--- 
title: "Elektronikus jelentéskészítési (ER) konfiguráció importálása a Lifecycle Services rendszerből"
description: "A következő lépések leírják, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként importálhat új Elektronikus jelentés (ER) konfigurációt a Microsoft Lifecycle Services (LCS) rendszerből."
author: NickSelin
manager: AnnBe
ms.date: 05/13/2016
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ab453d3ee44e206aea148de8dc3b428dc5056576
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="import-a-configuration-from-lifecycle-services-for-electronic-reporting-er"></a>Elektronikus jelentéskészítési (ER) konfiguráció importálása a Lifecycle Services rendszerből

[!include[task guide banner](../../includes/task-guide-banner.md)]

A következő lépések leírják, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként importálhat új Elektronikus jelentés (ER) konfigurációt a Microsoft Lifecycle Services (LCS) rendszerből.

Az alábbi példában kiválasztja az ER konfiguráció kívánt verzióját, majd importálja a Litware, Inc. minta vállalatra vonatkozóan. Ezeket a lépéseket a vállalat között megosztott ER konfigurációjaként bármely vállalatnál végrehajthatja. A lépések végrehajtásához el kell végeznie először a „Töltse fel az ER konfigurációt a Lifecycle Services rendszerbe” eljárás lépéseit. Az LCS rendszerbe való hozzáféréshez végre kell hajtani ezeket a lépéseket.

1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. Kattintson a Konfigurációk lehetőségre.

## <a name="delete-a-shared-version-of-data-model-configuration"></a>Az adatmodell megosztott verziójának törlése
1. A fastruktúrában válassza ki a „Minta modell beállítása” lehetőséget.
    * A rendszer létrehozott egy minta adatmodell konfigurációjának első verzióját és közzé tette az LCS-ben a számára létrehozva és a „Töltse fel az ER konfigurációt a Lifecycle Services rendszerbe eljárás“ során. Ebben az eljárásban törli az ER-konfiguráció ezen verzióját. A minta adatmodell konfigurációjának verzióját később importálják az LCS-ből.  
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a „Megosztott” állapotú konfiguráció verzióját. Ez az állapot azt jelzi, hogy a konfigurációt közzétették az LCS-ben.  
3. Kattintson az Állapot módosítása elemre.
4. Kattintson a Megszüntetés gombra.
    * Módosítsa a kiválasztott verzió állapotát „Megosztott” állapotról „Kifutott” állapotra annak érdekében, hogy lehetővé váljon a törlése.  
5. Kattintson az OK gombra.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a „Kifutott” állapotú konfiguráció verzióját.  
7. Kattintson a Törlés gombra.
8. Kattintson az Igen gombra.
    * Ne feledje, hogy a kijelölt adatmodell konfigurációjának csak a 2-es verziója érhető el.  
9. Zárja be a lapot.

## <a name="import-a-shared-version-of-data-model-configuration-from-lcs"></a>Az adatmodell konfigurációjának megosztott verziójának importálása az LCS-rendszerből
1. A listában jelölje meg a kiválasztott sort.
    * Nyissa meg a „Litware, Inc.” vállalatra vonatkozó tárházak listáját. konfigurációszolgáltató.  
2. Kattintson a Tárházak gombra.
3. Kattintson a Megnyitás gombra.
    * Válassza ki a LCS tárházat és nyissa meg.  
4. A listában jelölje meg a kiválasztott sort.
    * Válassza ki a „Minta modell konfiguráció” első verzióját a verziók listájában.  
5. Kattintson az Importálás gombra.
6. Kattintson az Igen gombra.
    * Erősítse meg a kiválasztott változatot az LCS rendszerből.  
    * Vegye figyelembe, hogy az információs üzenet (a képernyő fölött) megerősíti a kiválasztott verzió importálásának sikeres elvégzését.  
7. Zárja be a lapot.
8. Zárja be a lapot.
9. Kattintson a Konfigurációk lehetőségre.
10. A fastruktúrában válassza ki a „Minta modell beállítása” lehetőséget.
11. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a „Megosztott” állapotú konfiguráció verzióját.  
    * Ne feledje, hogy már a kijelölt adatmodell konfigurációjának 1-es verziója is elérhető.  


