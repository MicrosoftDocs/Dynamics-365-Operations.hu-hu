---
title: ER-konfigurációk letöltése a konfigurációs szolgáltatás globális tárából
description: Ez a témakör azt mutatja be, hogyan lehet letölteni az elektronikus jelentéskészítési (ER) konfigurációkat a konfigurációs szolgáltatás globális tárából.
author: NickSelin
manager: AnnBe
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: a96e78a64fe0559ae5f3bfddabf3fe1cad8a3dcb
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679558"
---
# <a name="download-er-configurations-from-the-global-repository-of-configuration-service"></a>ER-konfigurációk letöltése a konfigurációs szolgáltatás globális tárából

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet letölteni az [Elektronikus jelentéskészítési (ER) konfigurációkat](general-electronic-reporting.md#Configuration) a konfigurációs szolgáltatás globális tárából. A további tudnivalókat lásd: [Microsoft Dynamics 365 for Finance and Operations - Regulatory services, konfigurációs szolgáltatás](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).

## <a name="open-configurations-repository"></a>Konfigurációs tár megnyitása

1. Jelentkezzen be a Dynamics 365 Finance alkalmazásba az alábbi szerepkörök egyikének használatával:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

2. Ugorjon a **Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés** pontra.
3. Jelölje be a **Microsoft** lapot a **Konfigurációs szolgáltatók** részben.
3. Kattintson a **Tárak** lehetőségre a **Microsoft** lapon.

    ![Elektronikus jelentések munkaterülete](./media/er-download-configurations-global-repo-er-workspace.png)

4. A **Konfigurációs tárak** lapon lévő rácson jelölje ki a **Globális** meglévő tárházát. Ha a tárház nem jelenik meg a rácson, tegye a következőket:

    1. Kattintson a **Hozzáadás** lehetőségre egy új tárház hozzáadásához.
    2. Válassza a **Globális** lehetőséget a tár típusaként, majd válassza a **Tár létrehozása** elemet.
    3. Ha a rendszer rákérdez, kövesse engedélyezési útmutatásokat.
    4. Adjon nevet és leírást a tárhoz, majd kattintson az **OK** gombra a tár új bejegyzésének jóváhagyásához.
    5. A rácsban válassza ki a **Globális** típusú új tárat.

5. Kattintson a **Megnyitás** lehetőségre a kijelölt tárház ER-konfigurációk listájának megtekintéséhez.

    ![Konfigurációs tárak oldal](./media/er-download-configurations-global-repo-repositories-list.png)

## <a name="import-a-single-configuration"></a>Egyetlen konfiguráció importálása

1. A **Konfigurációs tárak** oldal konfigurációs fájában válassza ki a kívánt ER-konfigurációt.
2. A **Verziók** gyorslapon válassza ki a kijelölt ER-konfiguráció szükséges verzióját.
3. Kattintson az **Importálás** lehetőségre a kiválasztott verzió Globális tárból a jelenlegi Finance and Operations példányba történő letöltéséhez.

    > [!NOTE]
    > Az **Importálás** gomb nem érhető el azon ER konfigurációs verziókhoz, amelyek már szerepelnek az aktuális Finance-példányban.

    ![Konfigurációk tárháza oldal](./media/er-download-configurations-global-repo-repository-content.png)

## <a name="import-filtered-configurations"></a>Szűrt konfigurációk importálása

1. A **Konfigurációs tárak** oldalon bontsa ki a **Szűrő** gyorslapot a konfigurációs fán.
2. A **Címkék** rácsban adja meg a szükséges címkéket.
3. Az **Ország/terület alkalmazhatósága** mezőben válassza ki a megfelelő ország-/régiókódokat, majd válassza a **Szűrő alkalmazása** parancsot.

    > [!NOTE]
    > A **Konfigurációk** gyorslapon a megadott kiválasztási feltételeknek megfelelő összes konfigurációt jeleníti meg.

4. Válassza a **Konfigurációk** gyorslap **Importálás** parancsát a szűrt konfigurációknak a globális tárból a jelenlegi példányra történő letöltéséhez.
5. Válassza a **Konfigurációk** gyorslap **Szűrő alaphelyzetbe állítása** parancsát a megadott kiválasztási feltételek törléséhez.

    ![Konfigurációk tárháza oldal](./media/er-download-configurations-global-repo-filtered-configurations.png)

> [!NOTE]
> Az ER beállításoktól függ a konfigurációk érvényesítése azok importálását követően. Előfordulhat, hogy bármilyen észlelt ellentmondásos problémáról értesítést kap. Ezeket a problémákat meg kell oldania az importált konfiguráció verziójának használata előtt. További információkért nézze meg a jelen témakörrel kapcsolatos erőforrások listáját.

> [!NOTE]
> Az ER-konfigurációk konfigurálható úgy, hogy más konfigurációktól függjenek. Ezért a kiválasztott konfigurációval együtt előfordulhat, hogy más konfigurációk is automatikusan importálódnak. A konfiguráció függőségeivel kapcsolatos további tudnivalókat lásd: [Az ER-konfigurációk függőségének meghatározása más összetevőknél](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
