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
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a><span data-ttu-id="71b80-103">Az elektronikus jelentéskészítési konfigurációk letöltése a Lifecycle Services rendszerből</span><span class="sxs-lookup"><span data-stu-id="71b80-103">Download Electronic reporting configurations from Lifecycle Services</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="71b80-104">Ez a témakör azt mutatja be, hogyan lehet letölteni az [Elektronikus jelentéskészítési (ER) konfigurációk](general-electronic-reporting.md#Configuration) legújabb verzióját az [Közös eszközök könyvtárából](../lifecycle-services/asset-library.md) a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="71b80-104">This topic explains how to download the newest version of [Electronic reporting (ER) configurations](general-electronic-reporting.md#Configuration) from the [Shared asset library](../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71b80-105">Az LCS tárolási adattárként való használata az ER-konfigurációknál [elavult](../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span><span class="sxs-lookup"><span data-stu-id="71b80-105">The use of LCS as a storage repository for ER configurations is being [deprecated](../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span></span> <span data-ttu-id="71b80-106">További információért lásd a [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) tárhely elavulása](../../../finance/localizations/rcs-lcs-repo-dep-faq.md) részt.</span><span class="sxs-lookup"><span data-stu-id="71b80-106">For more information, see [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation](../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span></span>

1. <span data-ttu-id="71b80-107">Bejelentkezés az alkalmazásba az alábbi szerepkörök egyikének használatával:</span><span class="sxs-lookup"><span data-stu-id="71b80-107">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="71b80-108">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="71b80-108">Electronic reporting developer</span></span>
    - <span data-ttu-id="71b80-109">Elektronikus jelentések funkcióival foglalkozó konzulens</span><span class="sxs-lookup"><span data-stu-id="71b80-109">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="71b80-110">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="71b80-110">System administrator</span></span>

2. <span data-ttu-id="71b80-111">Ugorjon a **Szervezeti adminisztráció** &gt; **Munkaterületek** &gt; **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="71b80-111">Go to **Organization administration** &gt; **Workspaces** &gt; **Electronic reporting**.</span></span>
3. <span data-ttu-id="71b80-112">Jelölje be a **Microsoft** lapot a **Konfigurációs szolgáltatók** részben.</span><span class="sxs-lookup"><span data-stu-id="71b80-112">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
4. <span data-ttu-id="71b80-113">Kattintson a **Tárak** lehetőségre a **Microsoft** lapon.</span><span class="sxs-lookup"><span data-stu-id="71b80-113">On the **Microsoft** tile, select **Repositories**.</span></span>

    <span data-ttu-id="71b80-114">[![Microsoft csempe a Honosítási konfigurációk oldalon](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span><span class="sxs-lookup"><span data-stu-id="71b80-114">[![Microsoft tile on the Localization configurations page](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span></span>

5. <span data-ttu-id="71b80-115">A **Konfigurációs tárházak** lapon lévő rácson jelölje ki az **LCS** meglévő tárházát.</span><span class="sxs-lookup"><span data-stu-id="71b80-115">On the **Configuration repositories** page, in the grid, select the existing repository of the **LCS** type.</span></span> <span data-ttu-id="71b80-116">Ha a tárház nem jelenik meg a rácson, tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="71b80-116">If this repository doesn't appear in the grid, follow these steps:</span></span>

    1. <span data-ttu-id="71b80-117">Kattintson a **Hozzáadás** lehetőségre egy tárház hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="71b80-117">Select **Add** to add a repository.</span></span>
    2. <span data-ttu-id="71b80-118">Válassza ki az **LCS** lehetőséget a tárház típusaként.</span><span class="sxs-lookup"><span data-stu-id="71b80-118">Select **LCS** as the repository type.</span></span>
    3. <span data-ttu-id="71b80-119">Válassza a **Tárház létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="71b80-119">Select **Create repository**.</span></span>
    4. <span data-ttu-id="71b80-120">Ha a program rákérdez az engedélyezésre, kövesse a képernyőn megjelenő utasításokat.</span><span class="sxs-lookup"><span data-stu-id="71b80-120">If you're prompted about authorization, follow the on-screen instructions.</span></span>
    5. <span data-ttu-id="71b80-121">Írja be a tárház nevét és leírását.</span><span class="sxs-lookup"><span data-stu-id="71b80-121">Enter a name and description for the repository.</span></span>
    6. <span data-ttu-id="71b80-122">Válassza az **OK** lehetőséget az új adattárbejegyzés megerősítéséhez.</span><span class="sxs-lookup"><span data-stu-id="71b80-122">Select **OK** to confirm the new repository entry.</span></span>
    7. <span data-ttu-id="71b80-123">A rácsban jelölje be az **LCS** típus új tárházát.</span><span class="sxs-lookup"><span data-stu-id="71b80-123">In the grid, select the new repository of the **LCS** type.</span></span>

6. <span data-ttu-id="71b80-124">Kattintson a **Megnyitás** lehetőségre a kijelölt tárház ER-konfigurációk listájának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="71b80-124">Select **Open** to view the list of ER configurations for the selected repository.</span></span>

    <span data-ttu-id="71b80-125">[![Konfigurációs tárak oldal](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span><span class="sxs-lookup"><span data-stu-id="71b80-125">[![Configuration repositories page](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span></span>

    > [!TIP]
    > <span data-ttu-id="71b80-126">Ha nem sikerül elérnie az LCS-adattárat az LCS közös eszköz könyvtár konfigurációinak letöltéséhez, akkor helyette a [Globális adattárból](er-download-configurations-global-repo.md) is letöltheti a konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="71b80-126">If you have trouble accessing the LCS repository to download configurations from the Shared asset library in LCS, you can download configurations from the [Global repository](er-download-configurations-global-repo.md) instead.</span></span>

7. <span data-ttu-id="71b80-127">A bal oldali ablaktáblában jelölje ki a konfigurációkban jelölje ki a szükséges ER-konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="71b80-127">In the configurations tree in the left pane, select the required ER configuration.</span></span>
8. <span data-ttu-id="71b80-128">A **Verziók** gyorslapon válassza ki a kijelölt ER-konfiguráció szükséges verzióját.</span><span class="sxs-lookup"><span data-stu-id="71b80-128">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
9. <span data-ttu-id="71b80-129">Válassza az **Importálás** lehetőséget a kiválasztott verzió LCS rendszerből az aktuális példányba történő letöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="71b80-129">Select **Import** to download the selected version from LCS to the current instance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="71b80-130">Az **Importálás** gomb nem érhető el azon ER konfigurációs verziókhoz, amelyek már szerepelnek az aktuális példányban.</span><span class="sxs-lookup"><span data-stu-id="71b80-130">The **Import** button is unavailable for ER configuration versions that are already present in the current instance.</span></span>

    <span data-ttu-id="71b80-131">[![Konfigurációk tárháza oldal](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="71b80-131">[![Configuration repository page](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span></span>

> [!NOTE]
> <span data-ttu-id="71b80-132">Az ER beállításoktól függ a konfigurációk érvényesítése azok importálását követően.</span><span class="sxs-lookup"><span data-stu-id="71b80-132">Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="71b80-133">Előfordulhat, hogy bármilyen észlelt ellentmondásos problémáról értesítést kap.</span><span class="sxs-lookup"><span data-stu-id="71b80-133">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="71b80-134">Ezeket a problémákat meg kell oldania az importált konfiguráció verziójának használata előtt.</span><span class="sxs-lookup"><span data-stu-id="71b80-134">You must resolve those issues before you can use the imported configuration version.</span></span> <span data-ttu-id="71b80-135">További információkért nézze meg a jelen témakörrel kapcsolatos témakörök listáját.</span><span class="sxs-lookup"><span data-stu-id="71b80-135">For more information, see the list of related topics for this topic.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="71b80-136">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="71b80-136">Additional resources</span></span>

[<span data-ttu-id="71b80-137">Elektronikus jelentéskészítés (ER) áttekintése</span><span class="sxs-lookup"><span data-stu-id="71b80-137">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="71b80-138">ER-konfigurációk letöltése a konfigurációs szolgáltatás globális tárából</span><span class="sxs-lookup"><span data-stu-id="71b80-138">Download ER configurations from the Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
