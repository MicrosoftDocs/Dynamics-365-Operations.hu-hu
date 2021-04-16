---
title: A konfiguráció importálása a Lifecycle Services szolgáltatásból
description: Ez a témakör azt ismerteti, hogyan lehet importálni egy Elektronikus jelentéskészítési (ER) konfiguráció új verzióját a Microsoft Dynamics Lifecycle Services (LCS) alkalmazásból.
author: NickSelin
ms.date: 09/14/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 674d0dc02b4a53e455a15a06fdb7f24ca3036ba3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752364"
---
# <a name="import-a-configuration-from-lifecycle-services"></a>A konfiguráció importálása a Lifecycle Services szolgáltatásból

[!include [banner](../../includes/banner.md)]

Ez a témakör leírja, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként importálhat új [Elektronikus jelentés (ER) konfigurációt](../general-electronic-reporting.md#Configuration) a [projektszintű Eszközkönyvtárból](../../lifecycle-services/asset-library.md) a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.

Az alábbi példában kiválasztja az ER konfiguráció kívánt verzióját, majd importálja a Litware, Inc. nevű minta vállalatra vonatkozóan. Ezeket a lépéseket a vállalat között megosztott ER konfigurációjaként bármely vállalatnál elvégezheti. A lépések végrehajtásához el kell végeznie először a [Töltse fel az ER konfigurációt a Lifecycle Services rendszerbe](er-upload-configuration-into-lifecycle-services.md) eljárás lépéseit. Az LCS-hez való hozzáférés is szükséges.

1. Bejelentkezés az alkalmazásba az alábbi szerepkörök egyikének használatával:

    - Elektronikus jelentések fejlesztője
    - Rendszergazda

2. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
3. Válassza a **Konfigurációk** lehetőséget.

<a name="accessconditions"></a>
> [!NOTE]
> Győződjön meg róla, hogy az aktuális Dynamics 365 Finance felhasználó tagja annak az LCS projektnek, amely tartalmazza azt az Eszköztárat, amelyet a felhasználó [elérni](../../lifecycle-services/asset-library.md#asset-library-support) szeretne az ER-konfigurációk importálásához.
>
> Nem férhet hozzá egy LCS-projekthez egy olyan ER-adattárból, amely egy másik tartományt képvisel, mint a Finance-ben használt tartomány. Ha megpróbálja, akkor az LCS-projektek üres listája jelenik meg, és nem fogja tudni importálni a projekt-szintű Eszközökkönyvtár ER-konfigurációit az LCS-ben. Ahhoz, hogy a projekt-szintű Eszköztárakat egy olyan ER-adattárból elérje, amely ER-konfigurációk importálására szolgál, a Finance alkalmazásba való bejelentkezéshez olyan felhasználó hitelesítő adatait használja, aki olyan bérlőhöz (tartomány) tartozik, amelyhez az aktuális Finance-példány ki lett építve.

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a>Az adatmodell-konfiguráció megosztott verziójának törlése

1. A **Konfigurációk** oldalon található konfigurációk fájában válassza ki a **Mintamodell-konfiguráció** elemet.

    A rendszer létrehozott egy minta adatmodell konfigurációjának első verzióját és közzé tette az LCS-ben, amikro elvégezte [A konfiguráció feltöltése a Lifecycle Services szolgáltatásba](er-upload-configuration-into-lifecycle-services.md) eljárás lépéseit. Ebben az eljárásban törli az ER-konfiguráció azon verzióját. Ezt a verziót később, ebben a témakörben importálja az LCS-ből.

2. Keresse meg és jelölje ki a kívánt rekordot a listán.

    Ebben a példában válassza ki a **Megosztott** állapotú konfiguráció verzióját. Ez az állapot azt jelzi, hogy a konfigurációt közzétették az LCS-ben.

3. Válassza az **Állapot módosítása** lehetőséget.
4. Válassza a **Megszüntetés** parancsot.

    A kiválasztott verzió állapotának módosításával **Megosztott** állapotról **Megszüntetett** állapotra annak érdekében, hogy lehetővé váljon a verzió törlése.

5. Válassza ki az **OK** lehetőséget.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.

    Ebben a példában válassza ki a **Megszüntetett** állapotú konfiguráció verzióját.

7. Válassza a **Törlés** lehetőséget.
8. Válassza ki az **Igen** lehetőséget.

    Ne feledje, hogy a most a kijelölt adatmodell konfigurációjának csak a 2-es verziója érhető el.

9. Zárja be a lapot.

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a>Egy adatmodell konfiguráció megosztott verziójának importálása az LCS-rendszerből

1. Ugorjon a **Szervezeti adminisztráció \> Munkaterületek \> Elektronikus jelentés** pontra.

2. Jelölje be a **Litware, Inc.** csempét a **Konfigurációs szolgáltatók** részben.

3. Kattintson a **Tárak** lehetőségre a **Litware, Inc.** lapon.

    Ez lehetővé teszi a Litware, Inc. tárházak listájának megnyitását. Konfigurációszolgáltató.

4. Válassza ki a **Megnyitás** lehetőséget.

    A példa esetében válassza ki a **LCS** tárházat, majd nyissa meg. [Hozzá kell férnie](#accessconditions) az LCS-projekthez és a kijelölt Eszköztárhoz, amit elér az ER-adattár.

5. A listában jelölje meg a kiválasztott sort.

    Ehhez a példához válassza ki a **Minta modell konfiguráció** első verzióját a verziók listájában.

6. Válassza az **Importálás** lehetőséget.
7. Válassz az **Igen** lehetőséget, hogy megerősítse a kiválasztott verzió importálását az LCS-ből.

    Egy tájékoztató üzenet megerősíti, hogy a program sikeresen importálta a kiválasztott verziót.

8. Zárja be a lapot.
9. Zárja be a lapot.
10. Válassza a **Konfigurációk** lehetőséget.
11. A fastruktúrában válassza ki a **Minta modell beállítása** lehetőséget.
12. Keresse meg és jelölje ki a kívánt rekordot a listán.

    Ebben a példában válassza ki a **Megosztott** állapotú konfiguráció verzióját.

    Ne feledje, hogy már a kijelölt adatmodell konfigurációjának 1-es verziója is elérhető.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]