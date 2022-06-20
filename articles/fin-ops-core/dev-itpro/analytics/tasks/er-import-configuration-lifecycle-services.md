---
title: A konfiguráció importálása a Lifecycle Services szolgáltatásból
description: Ez a témakör azt ismerteti, hogyan lehet importálni az elektronikus jelentéskészítési (ER) konfigurációk új verzióját a Lifecycle Services (LCS) Microsoft Dynamics alkalmazásból.
author: NickSelin
ms.date: 06/17/2021
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
ms.openlocfilehash: 2aae59334828a5636f35051d50cf2ea392074b71
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886672"
---
# <a name="import-a-configuration-from-lifecycle-services"></a>A konfiguráció importálása a Lifecycle Services szolgáltatásból

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja, hogy a rendszergazdai vagy elektronikus jelentéskészítő fejlesztői szerepkörű felhasználók hogyan importálhatják az elektronikus jelentéskészítési (ER) konfiguráció új verzióját a [Lifecycle Services (LCS)](../general-electronic-reporting.md#Configuration)[...](../../lifecycle-services/asset-library.md)Microsoft Dynamics projektszintű eszköztárából.

> [!IMPORTANT]
> Az LCS tárolási adattárként való használata az ER-konfigurációknál [elavult](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). További információért lásd a [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) tárhely elavulása](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md) részt.

Az alábbi példában kiválasztja az ER konfiguráció kívánt verzióját, majd importálja a Litware, Inc. nevű minta vállalatra vonatkozóan. Ezeket a lépéseket a vállalat között megosztott ER konfigurációjaként bármely vállalatnál elvégezheti. A lépések végrehajtásához el kell végeznie először a [Töltse fel az ER konfigurációt a Lifecycle Services rendszerbe](er-upload-configuration-into-lifecycle-services.md) eljárás lépéseit. Az LCS-hez való hozzáférés is szükséges.

1. Bejelentkezés az alkalmazásba az alábbi szerepkörök egyikének használatával:

    - Elektronikus jelentések fejlesztője
    - Rendszergazda

2. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
3. Válassza a **Konfigurációk** lehetőséget.

<a name="accessconditions"></a>
> [!NOTE]
> Győződjön meg róla, hogy az aktuális Dynamics 365 Pénzügyi felhasználó tagja annak az LCS-projektnek [...](../../lifecycle-services/asset-library.md#asset-library-support), amely azt az eszköztárat tartalmazza, amelybe a felhasználó er-konfigurációkat szeretne importálni.
>
> Nem férhet hozzá egy LCS-projekthez egy olyan ER-adattárból, amely egy másik tartományt képvisel, mint a Finance-ben használt tartomány. Ha megpróbálja, akkor az LCS-projektek üres listája jelenik meg, és nem fogja tudni importálni a projekt-szintű Eszközökkönyvtár ER-konfigurációit az LCS-ben. Ahhoz, hogy a projekt-szintű Eszköztárakat egy olyan ER-adattárból elérje, amely ER-konfigurációk importálására szolgál, a Finance alkalmazásba való bejelentkezéshez olyan felhasználó hitelesítő adatait használja, aki olyan bérlőhöz (tartomány) tartozik, amelyhez az aktuális Finance-példány ki lett építve.

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a>Az adatmodell-konfiguráció megosztott verziójának törlése

1. A **Konfigurációk** oldalon található konfigurációk fájában válassza ki a **Mintamodell-konfiguráció** elemet.

    A rendszer létrehozott egy minta adatmodell konfigurációjának első verzióját és közzé tette az LCS-ben, amikro elvégezte [A konfiguráció feltöltése a Lifecycle Services szolgáltatásba](er-upload-configuration-into-lifecycle-services.md) eljárás lépéseit. Ebben az eljárásban törli az ER-konfiguráció azon verzióját. Ezt követően a cikket később importálja az LCS-ről.

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
