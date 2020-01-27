---
title: Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből
description: Ez a témakör az elektronikus jelentési (ER) konfiguráció Microsoft Dynamics Lifecycle Services (LCS) rendszerből történő letöltési folyamatát mutatja be.
author: NickSelin
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 4cc14860bd969048c4378b40d97a7940a8710e89
ms.sourcegitcommit: 4d77d06a07ec9e7a3fcbd508afdffaa406fd3dd8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934654"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Az elektronikus jelentéskészítési beállítások letöltése a Lifecycle Services rendszerből

[!include [banner](../includes/banner.md)]

Ez a témakör az elektronikus jelentési (ER) konfiguráció Microsoft Dynamics Lifecycle Services (LCS) rendszerből történő letöltési folyamatát mutatja be.

Ez az oktatóanyag bemutatja az elektronikus jelentési (ER) konfiguráció legújabb verziójának a Microsoft Dynamics Lifecycle Services (LCS) rendszerből történő letöltési folyamatát.

1. Bejelentkezés az alkalmazásba az alábbi szerepkörök egyikének használatával:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

2. Ugorjon a **Szervezeti adminisztráció** &gt; **Munkaterületek** &gt; **Elektronikus jelentés** pontra.
3. Jelölje be a **Microsoft** lapot a **Konfigurációs szolgáltatók** részben.
4. Kattintson a **Tárházak** lehetőségre a **Microsoft** lapon.

    [![Az ER frissítése az MS LCS rendszerből - MS tárházak lista megnyitása](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)

5. A **Konfigurációs tárházak** lapon lévő rácson jelölje ki az **LCS** meglévő tárházát. Ha a tárház nem jelenik meg a rácson, tegye a következőket:

    1. Kattintson a **Hozzáadás** lehetőségre egy új tárház hozzáadásához.
    2. Válassza ki az **LCS** lehetőséget a tárház típusaként.
    3. Kattintson a **Tárház létrehozása** lehetőségre.
    4. Ha a rendszer rákérdez, kövesse engedélyezési útmutatásokat.
    5. Írja be a tárház nevét és leírását.
    6. Kattintson az **OK** lehetőségre az új tárház bejegyzés megerősítéséhez.
    7. A rácsban jelölje be az **LCS** típus új tárházát.

6. Kattintson a **Megnyitás** lehetőségre a kijelölt tárház ER-konfigurációk listájának megtekintéséhez.

    [![Az ER frissítése az MS LCS rendszerből - LCS-tárház készítése](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)

7. A bal oldali ablaktáblában jelölje ki a konfigurációkban jelölje ki a szükséges ER-konfigurációt.
8. A **Verziók** gyorslapon válassza ki a kijelölt ER-konfiguráció szükséges verzióját.
9. Kattintson az **Importálás** lehetőségre a kiválasztott verzió LCS rendszerből az aktuális példányba történő letöltéséhez.

    > [!NOTE]
    > Az **Importálás** gomb nem érhető el azon ER konfigurációs verziókhoz, amelyek már szerepelnek az aktuális példányban.

    [![Az ER frissítése az MS LCS rendszerből - Konfiguráció letöltése](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

> [!NOTE]
> Az ER beállításoktól függ a konfigurációk érvényesítése azok importálását követően. Előfordulhat, hogy bármilyen észlelt ellentmondásos problémáról értesítést kap. Ezeket a problémákat meg kell oldania az importált konfiguráció verziójának használata előtt. További információkért nézze meg a jelen témakörrel kapcsolatos cikkek listáját.

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
