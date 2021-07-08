---
title: Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből
description: Ez a témakör az elektronikus jelentési (ER) konfiguráció Microsoft Dynamics Lifecycle Services (LCS) rendszerből történő letöltési folyamatát mutatja be.
author: NickSelin
ms.date: 08/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 14f0f2b1a4d63101d432b1361379c61a70ac9345
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271183"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Az elektronikus jelentéskészítési konfigurációk letöltése a Lifecycle Services rendszerből

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet letölteni az [Elektronikus jelentéskészítési (ER) konfigurációk](general-electronic-reporting.md#Configuration) legújabb verzióját az [Közös eszközök könyvtárából](../lifecycle-services/asset-library.md) a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.

> [!IMPORTANT]
> Az LCS tárolási adattárként való használata az ER-konfigurációknál [elavult](../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). További információért lásd a [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) tárhely elavulása](../../../finance/localizations/rcs-lcs-repo-dep-faq.md) részt.

1. Bejelentkezés az alkalmazásba az alábbi szerepkörök egyikének használatával:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

2. Ugorjon a **Szervezeti adminisztráció** &gt; **Munkaterületek** &gt; **Elektronikus jelentés** pontra.
3. Jelölje be a **Microsoft** lapot a **Konfigurációs szolgáltatók** részben.
4. Kattintson a **Tárak** lehetőségre a **Microsoft** lapon.

    [![Microsoft csempe a Honosítási konfigurációk oldalon](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)

5. A **Konfigurációs tárházak** lapon lévő rácson jelölje ki az **LCS** meglévő tárházát. Ha a tárház nem jelenik meg a rácson, tegye a következőket:

    1. Kattintson a **Hozzáadás** lehetőségre egy tárház hozzáadásához.
    2. Válassza ki az **LCS** lehetőséget a tárház típusaként.
    3. Válassza a **Tárház létrehozása** lehetőséget.
    4. Ha a program rákérdez az engedélyezésre, kövesse a képernyőn megjelenő utasításokat.
    5. Írja be a tárház nevét és leírását.
    6. Válassza az **OK** lehetőséget az új adattárbejegyzés megerősítéséhez.
    7. A rácsban jelölje be az **LCS** típus új tárházát.

6. Kattintson a **Megnyitás** lehetőségre a kijelölt tárház ER-konfigurációk listájának megtekintéséhez.

    [![Konfigurációs tárak oldal](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)

    > [!TIP]
    > Ha nem sikerül elérnie az LCS-adattárat az LCS közös eszköz könyvtár konfigurációinak letöltéséhez, akkor helyette a [Globális adattárból](er-download-configurations-global-repo.md) is letöltheti a konfigurációkat.

7. A bal oldali ablaktáblában jelölje ki a konfigurációkban jelölje ki a szükséges ER-konfigurációt.
8. A **Verziók** gyorslapon válassza ki a kijelölt ER-konfiguráció szükséges verzióját.
9. Válassza az **Importálás** lehetőséget a kiválasztott verzió LCS rendszerből az aktuális példányba történő letöltéséhez.

    > [!NOTE]
    > Az **Importálás** gomb nem érhető el azon ER konfigurációs verziókhoz, amelyek már szerepelnek az aktuális példányban.

    [![Konfigurációk tárháza oldal](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

> [!NOTE]
> Az ER beállításoktól függ a konfigurációk érvényesítése azok importálását követően. Előfordulhat, hogy bármilyen észlelt ellentmondásos problémáról értesítést kap. Ezeket a problémákat meg kell oldania az importált konfiguráció verziójának használata előtt. További információkért nézze meg a jelen témakörrel kapcsolatos témakörök listáját.

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)

[ER-konfigurációk letöltése a konfigurációs szolgáltatás globális tárából](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
