---
title: RCS/globális tárak ER-konfigurációinak megosztása külső szervezetekkel
description: Ez a témakör azt mutatja be, hogyan oszthatók meg a Microsoft Regulatory Configuration Services (RCS)/a globális tár elektronikus jelentéskészítési (ER) konfigurációi közvetlenül a külső szervezetekkel.
author: JaneA07
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 0973d36a8fddd16d02776ac6567d424ac6ebc3ae
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994307"
---
# <a name="share-electronic-reporting-er-configurations-in-regulatory-configuration-services-rcs-global-repository-with-external-organizations"></a><span data-ttu-id="5d2ce-103">A Regulatory Configuration Services (RCS) globális tár elektronikus jelentéskészítési (ER) konfigurációinak megosztása külső szervezetekkel.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-103">Share Electronic reporting (ER) configurations in Regulatory Configuration Services (RCS) Global repository with external organizations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5d2ce-104">A Microsoft Regulatory Configuration Services (RCS) segítségével megoszthatók az elektronikus jelentéskészítési (ER) konfigurációk, majd közzétehetők külső szervezetek számára.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-104">You can use Microsoft Regulatory Configuration Services (RCS) to share Electronic reporting (ER) configurations and then publish them to external organizations.</span></span>

<span data-ttu-id="5d2ce-105">A következő lépések leírják, hogy hogyan oszthatja meg egy RCS-felhasználó egy RCS-példányban konfigurált ER-konfiguráció egy verzióját egy külső szervezettel.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-105">The following procedures explain how an RCS user can share a version of an ER configuration that has been configured in an RCS instance with an external organization.</span></span> <span data-ttu-id="5d2ce-106">Mielőtt teljesítené ezeket az eljárásokat, végre kell hajtania a következő előfeltételeket:</span><span class="sxs-lookup"><span data-stu-id="5d2ce-106">Before you can complete those procedures, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="5d2ce-107">Nyisson meg egy RCS-példányt.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-107">Access an RCS instance.</span></span>
- <span data-ttu-id="5d2ce-108">Hozzon létre egy aktív konfigurációszolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-108">Create an active configuration provider.</span></span> <span data-ttu-id="5d2ce-109">További információért tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-109">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
- <span data-ttu-id="5d2ce-110">Hozzon létre és töltsön fel egy új verziót egy ER-konfigurációból.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-110">Create and upload a new version of an ER configuration.</span></span> <span data-ttu-id="5d2ce-111">További információ: [Elektronikus jelentéskészítési (ER) konfiguráció új verziójának létrehozása és feltöltése](rcs-global-repo-upload.md).</span><span class="sxs-lookup"><span data-stu-id="5d2ce-111">For more information, see [Create and upload a new version of an Electronic reporting (ER) configuration](rcs-global-repo-upload.md).</span></span>

<span data-ttu-id="5d2ce-112">Arról is meg kell győződnie, hogy a vállalatnál RCS-környezet van kiépítve.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-112">You must also make sure that an RCS environment is provisioned for your company.</span></span>

1. <span data-ttu-id="5d2ce-113">A Finance and Operations alkalmazásban lépjen a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-113">In a Finance and Operations app, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="5d2ce-114">Ha nincs RCS környezete a vállalathoz, kattintson a **Regulatory services – Külső konfiguráció** lehetőségre, és kövesse az RCS-környezet létrehozására vonatkozó instrukciókat.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-114">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration external**, and then follow the instructions to provision one.</span></span>

<span data-ttu-id="5d2ce-115">Ha van már RCS-környezet létesítve a vállalat számára, akkor az oldal URL-címével érheti el a bejelentkezési beállítást.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-115">If an RCS environment has been already provisioned for your company, use the page URL to access it by selecting the sign-in option.</span></span>

## <a name="verify-the-configuration-that-you-want-to-share"></a><span data-ttu-id="5d2ce-116">A megosztani kívánt konfiguráció ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="5d2ce-116">Verify the configuration that you want to share</span></span>

<span data-ttu-id="5d2ce-117">Hajtsa végre az alábbi lépéseket, és győződjön meg arról, hogy a megosztani kívánt konfiguráció már fel van töltve a globális tárba.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-117">Follow these steps to verify that the configuration that you want to share has already been uploaded to the Global repository.</span></span>

1. <span data-ttu-id="5d2ce-118">Az **Elektronikus jelentés** munkaterületen válassza ki a **Tárak** lehetőséget a konfigurációszolgáltatój esetében.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-118">In the **Electronic reporting** workspace, select **Repositories** for your configuration provider.</span></span>

    ![Konfigurációszolgáltatók](media/1_RCS_Repo_for_config_provider.JPG)

2. <span data-ttu-id="5d2ce-120">Válassza ki a **Globális tár** \> **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-120">Select **Global repository** \> **Open**.</span></span>
3. <span data-ttu-id="5d2ce-121">Keresse meg a megosztani kívánt konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-121">Search for the configuration that you want to share.</span></span> <span data-ttu-id="5d2ce-122">A szűrő mező segítségével tovább szűkítheti a keresés eredményeit.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-122">You can use the filter field to narrow your search.</span></span> <span data-ttu-id="5d2ce-123">Ha nem találja a konfigurációt a globális tárban, hajtsa végre az [Elektronikus jelentéskészítési (ER) konfiguráció új verziójának létrehozása és feltöltése](rcs-global-repo-upload.md) rész lépéseit.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-123">If you can't find the configuration in the Global repository, follow the steps in [Create and upload a new version of an Electronic reporting (ER) configuration](rcs-global-repo-upload.md).</span></span>

## <a name="share-er-configurations-with-external-organizations"></a><span data-ttu-id="5d2ce-124">ER-konfigurációk megosztása külső szervezetekkel</span><span class="sxs-lookup"><span data-stu-id="5d2ce-124">Share ER configurations with external organizations</span></span>

<span data-ttu-id="5d2ce-125">Miután létrehozta a konfigurációt a konfigurációszolgáltatója alatt, a **Globális konfigurációtár** oldalon található **Megosztva a következővel:** gyorslappal megoszthatja azt közvetléenül egy külső szervezettel.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-125">After a configuration has been created under your configuration provider, you can share it directly with external organizations by using the **Shared with** FastTab on the **Global configuration repository** page.</span></span>

1. <span data-ttu-id="5d2ce-126">Az **Elektronikus jelentés** munkaterületen válassza ki a **Tárak** lehetőséget a konfigurációszolgáltatój esetében.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-126">In the **Electronic reporting** workspace, select **Repositories** for your configuration provider.</span></span>
2. <span data-ttu-id="5d2ce-127">Válassza ki a **Globális tár** \> **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-127">Select **Global repository** \> **Open**.</span></span> 
3. <span data-ttu-id="5d2ce-128">Válassza ki a megosztani kívánt konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-128">Select the configuration that you want to share.</span></span>
4. <span data-ttu-id="5d2ce-129">Az **Megosztva a következővel:** gyorslapon válassza a **Szervezet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-129">On the **Shared with** FastTab, select **Organization**.</span></span>

    ![Megosztás gyorslappal](media/1_RCS_Repo_for_Share_with_org.JPG)

5. <span data-ttu-id="5d2ce-131">A párbeszédpanelen írja be a külső szervezet domainnevét, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-131">In the dialog box, enter the domain name for the external organization, and then select **OK**.</span></span>

    ![Mentse a konfiguráció verzióját a külső szervezet párbeszédpanellel](media/1_RCS_Repo_for_Share_with_form.JPG)

<span data-ttu-id="5d2ce-133">A konfiguráció megosztásra kerül a külső szervezettel, és a szervezet számára elérhető a globális tárban.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-133">The configuration is shared with the external organization and is available to that organization in the Global repository.</span></span> <span data-ttu-id="5d2ce-134">Innen importálható a szervezet RCS-példányába vagy Finance and Operations alkalmazásainak példányaiba.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-134">From there, it can be imported into the organization's instance of RCS or into its instances of Finance and Operations apps.</span></span>

6. <span data-ttu-id="5d2ce-135">Ha egy külső szervezettel korábban megosztott konfigurációt megosztását vissza szeretné vonni, válassza ki a konfigurációt, majd kattintson a **Megosztás visszavonása** elemre , majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="5d2ce-135">To unshare a configuration that has been previously shared with an external organization, select the configuration and click **Unshare**, and then select **OK**</span></span>
