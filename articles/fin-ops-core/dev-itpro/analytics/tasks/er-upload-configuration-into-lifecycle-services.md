---
title: A konfiguráció feltöltése a Lifecycle Services szolgáltatásba
description: Ez a témakör leírja, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre új Elektronikus jelentés (ER) konfigurációt, és töltheti fel a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásba.
author: NickSelin
manager: AnnBe
ms.date: 09/14/2020
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
ms.openlocfilehash: c43bad3ee2530a454de718a0a7da4d1e468a4af4
ms.sourcegitcommit: 9857d5cbdc0ab2fc9db049ac5ad118fc2b29bedc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/14/2020
ms.locfileid: "3810691"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a>A konfiguráció feltöltése a Lifecycle Services szolgáltatásba

[!include [banner](../../includes/banner.md)]

Ez a témakör leírja, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre új [Elektronikus jelentés (ER) konfigurációt](../general-electronic-reporting.md#Configuration) , és hogyan töltheti fel a [projektszintű Eszközkönyvtárba](../../lifecycle-services/asset-library.md) a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.

Ebben a példában a mintavállalatra, a Litware-ra, Inc.-re vonatkozóan létrehoz egy konfigurációs szolgáltatót, és feltölti az LCS rendszerbe. Ezek a lépések bármely vállalatnál elvégezhetők, mivel az ER-konfigurációk meg vannak osztva a vállalatok között. Az alábbi lépések végrehajtásához először hajtsa végre a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) témakör lépéseit. Az LCS-hez való hozzáférés is szükséges.

1. Bejelentkezés az alkalmazásba az alábbi szerepkörök egyikének használatával:

    - Elektronikus jelentések fejlesztője
    - Rendszergazda

2. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
3. Válassza ki a **Litware, Inc.**, és jelölje meg **Aktív** állapotúként.
4. Válassza a **Konfigurációk** lehetőséget.

<a name="accessconditions"></a>
> [!NOTE]
> Győződjön meg róla, hogy az aktuális Dynamics 365 Finance felhasználó tagja annak az LCS projektnek, amely tartalmazza azt az [Eszköztárat](../../lifecycle-services/asset-library.md#asset-library-support), amely az ER-konfigurációk importálásához használatos.
>
> Nem férhet hozzá egy LCS-projekthez egy olyan ER-adattárból, amely egy másik tartományt képvisel, mint a Finance-ben használt tartomány. Ha megpróbálja, akkor az LCS-projektek üres listája jelenik meg, és nem fogja tudni importálni a projekt-szintű Eszközökkönyvtár ER-konfigurációit az LCS-ben. Ahhoz, hogy a projekt-szintű Eszköztárakat egy olyan ER-adattárból elérje, amely ER-konfigurációk importálására szolgál, a Finance alkalmazásba való bejelentkezéshez olyan felhasználó hitelesítő adatait használja, aki olyan bérlőhöz (tartomány) tartozik, amelyhez az aktuális Finance-példány ki lett építve.

## <a name="create-a-new-data-model-configuration"></a>Új adatmodell-konfiguráció létrehozása

1. Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.
2. A **Konfiguráció** oldalon a **Konfiguráció létrehozása** kiválasztásával megnyithatja a legördülő párbeszédablakot.

    Ebben a példában olyan konfigurációt hoz létre, amely tartalmazza az elektronikus dokumentumokra vonatkozó minta adatmodellt. Később az LCS-be töltik fel ezen adatmodell konfigurációját.

3. A **Név** mezőben írja be a **Minta modellkonfiguráció** szöveget.
4. A **Leírás** mezőbe írja be a **Minta modellkonfiguráció** szöveget.
5. Válassza a **Konfiguráció létrehozása** lehetőséget.
6. Válassza ki a **Modelltervező** lehetőséget.
7. Válassza az **Új** lehetőséget.
8. A **Név** mezőbe írja be a következőt: **Belépési pont**.
9. Válassza a **Hozzáadás** lehetőséget.
10. Válassza a **Mentés** lehetőséget.
11. Zárja be a lapot.
12. Válassza az **Állapot módosítása** lehetőséget.
13. Válassza a **Kész** lehetőséget.
14. Válassza ki az **OK** lehetőséget.
15. Zárja be a lapot.

## <a name="register-a-new-repository"></a>Új tárház regisztrálása

1. Ugorjon a **Szervezeti adminisztráció \> Munkaterületek \> Elektronikus jelentés** pontra.

2. Jelölje be a **Litware, Inc.** csempét a **Konfigurációs szolgáltatók** részben.

3. Kattintson a **Tárak** lehetőségre a **Litware, Inc.** lapon.

    Ez lehetővé teszi a Litware, Inc. tárházak listájának megnyitását. Konfigurációszolgáltató.

4. A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.

    Most hozzáadhatja az adattárat.

5. A **Konfiguráció tárházának megadása** mezőbe írja be az **LCS** értéket.
6. Válassza a **Tárház létrehozása** lehetőséget.
7. A **Projekt** mezőben adjon meg vagy válasszon ki egy értéket.

    Ebben a példában válassza a kívánt LCS-projektet. [Hozzáféréssel](#accessconditions) kell rendelkeznie a projekthez.

8. Válassza ki az **OK** lehetőséget.

    Fejezze be az új tárház bejegyzést.

9. A listában jelölje meg a kiválasztott sort.

    A példa esetében válassza ki a **LCS** tárház rekordját.

    Ne feledje, hogy a regisztrált tárházat az aktuális szolgáltató megjelöli. Más szóval csak a szolgáltató tulajdonát képező konfigurációk vihetők be ebbe a tárházba, tehát tölthetők fel a kiválasztott LCS-projektbe.

10. Válassza ki a **Megnyitás** lehetőséget.

    Nyissa meg a tárházat az ER konfigurációk listájának megtekintéséhez. Ha a kiválasztott projektet még nem használta az ER-konfigurációk megosztásához, a lista üres lesz.

11. Zárja be a lapot.
12. Zárja be a lapot.

## <a name="upload-a-configuration-into-lcs"></a>Egy konfiguráció feltöltése az LCS-be

1. Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.
2. A **Konfigurációk** oldalon található konfigurációk fájában válassza ki a **Mintamodell-konfiguráció** elemet.

    Ki kell választania a létrehozott konfigurációt, ami már be lett fejezve.

3. Keresse meg és jelölje ki a kívánt rekordot a listán.

    Ebben a példában válassza ki a konfiguráció **Befejeződött** állapotú verzióját.

4. Válassza az **Állapot módosítása** lehetőséget.
5. Válassza ki a **Megosztás** elemet.

    A konfiguráció állapotát a program az LCS modulban **Befejezett** állapotúról **Megosztott** állapotúra módosítja.

6. Válassza ki az **OK** lehetőséget.
7. Keresse meg és jelölje ki a kívánt rekordot a listán.

    Ebben a példában válassza ki a konfiguráció **Megosztott** állapotú verzióját.

    Vegye figyelembe, hogy a kiválasztott verzió állapota **Kész** állapotról **Megosztott** állapotra változott.

8. Zárja be a lapot.
9. Válassza ki a **Tárházak** lehetőséget.

    Ez lehetővé teszi a Litware, Inc. tárházak listájának megnyitását. Konfigurációszolgáltató.

10. Válassza ki a **Megnyitás** lehetőséget.

    A példa esetében válassza ki a **LCS** tárházat, majd nyissa meg.

    Vegye figyelembe, hogy a kijelölt konfiguráció a kiválasztott projekt LCS eszközeként jelenik meg.

11. Az LCS-t a <https://lcs.dynamics.com> cím meglátogatásával nyithatja meg.
12. A tárház regisztrálásához korábban használt projektet nyissa meg.
13. Nyissa meg a projekt eszköztárát.
14. Válassza a **GER-konfiguráció** eszköztípust.

    A feltöltött ER-konfigurációnak listázva kell lennie.

    Vegye figyelembe, hogy a feltöltött LCS konfigurációt egy másik példányába importálhatja, ha a szolgáltatók rendelkeznek hozzáféréssel ehhez az LCS projekthez.
