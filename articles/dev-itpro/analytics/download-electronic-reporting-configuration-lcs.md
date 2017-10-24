---
title: "Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből"
description: "Ez a témakör az elektronikus jelentési (ER) konfiguráció Microsoft Dynamics Lifecycle Services (LCS) rendszerből történő letöltési folyamatát mutatja be."
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a4411b25285128c849a715fdc7a2f5fe51580a3b
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a><span data-ttu-id="a16d9-103">Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből</span><span class="sxs-lookup"><span data-stu-id="a16d9-103">Download Electronic reporting configurations from Lifecycle Services</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="a16d9-104">Ez a témakör az elektronikus jelentési (ER) konfiguráció Microsoft Dynamics Lifecycle Services (LCS) rendszerből történő letöltési folyamatát mutatja be.</span><span class="sxs-lookup"><span data-stu-id="a16d9-104">This topic explains how to download Electronic reporting (ER) configurations from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="a16d9-105">Ez az oktatóanyag bemutatja az elektronikus jelentési (ER) konfiguráció legújabb verziójának a Microsoft Dynamics Lifecycle Services (LCS) rendszerből történő letöltési folyamatát.</span><span class="sxs-lookup"><span data-stu-id="a16d9-105">This tutorial guides you through the process of downloading the newest version of Electronic reporting (ER) configurations from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1.  <span data-ttu-id="a16d9-106">Bejelentkezés a Finance and Operations rendszerbe az alábbi szerepkörök egyikének használatával:</span><span class="sxs-lookup"><span data-stu-id="a16d9-106">Sign in to Finance and Operations by using one of the following roles:</span></span>
    -   <span data-ttu-id="a16d9-107">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="a16d9-107">Electronic reporting developer</span></span>
    -   <span data-ttu-id="a16d9-108">Elektronikus jelentések funkcióival foglalkozó konzulens</span><span class="sxs-lookup"><span data-stu-id="a16d9-108">Electronic reporting functional consultant</span></span>
    -   <span data-ttu-id="a16d9-109">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="a16d9-109">System administrator</span></span>

2.  <span data-ttu-id="a16d9-110">Ugorjon a **Szervezeti adminisztráció** &gt; **Elektronikus jelentés** elemre.</span><span class="sxs-lookup"><span data-stu-id="a16d9-110">Go to **Organization administration** &gt; **Electronic reporting**.</span></span>
3.  <span data-ttu-id="a16d9-111">Jelölje be a **Microsoft** lapot a **Konfigurációs szolgáltatók** részben.</span><span class="sxs-lookup"><span data-stu-id="a16d9-111">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
4.  <span data-ttu-id="a16d9-112">Kattintson a **Tárházak** lehetőségre a **Microsoft** lapon.</span><span class="sxs-lookup"><span data-stu-id="a16d9-112">On the **Microsoft** tile, click **Repositories**.</span></span> <span data-ttu-id="a16d9-113">[![Az ER frissítése az MS LCS rendszerből - MS tárházak lista megnyitása](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span><span class="sxs-lookup"><span data-stu-id="a16d9-113">[![update-er-from-lcs-for-ms-open-ms-repositories-list](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span></span>
5.  <span data-ttu-id="a16d9-114">A **Konfigurációs tárházak** lapon lévő rácson jelölje ki az **LCS** meglévő tárházát.</span><span class="sxs-lookup"><span data-stu-id="a16d9-114">On the **Configuration repositories** page, in the grid, select the existing repository of the **LCS** type.</span></span> <span data-ttu-id="a16d9-115">Ha a tárház nem jelenik meg a rácson, tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="a16d9-115">If this repository doesn't appear in the grid, follow these steps:</span></span>
    1.  <span data-ttu-id="a16d9-116">Kattintson a **Hozzáadás** lehetőségre egy új tárház hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="a16d9-116">Click **Add** to add a new repository.</span></span>
    2.  <span data-ttu-id="a16d9-117">Válassza ki az **LCS** lehetőséget a tárház típusaként.</span><span class="sxs-lookup"><span data-stu-id="a16d9-117">Select **LCS** as the repository type.</span></span>
    3.  <span data-ttu-id="a16d9-118">Kattintson a **Tárház létrehozása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a16d9-118">Click **Create repository**.</span></span>
    4. <span data-ttu-id="a16d9-119">Ha a rendszer rákérdez, kövesse engedélyezési útmutatásokat.</span><span class="sxs-lookup"><span data-stu-id="a16d9-119">If prompted, follow the authorization instructions.</span></span>
    5.  <span data-ttu-id="a16d9-120">Írja be a tárház nevét és leírását.</span><span class="sxs-lookup"><span data-stu-id="a16d9-120">Enter a name and description for the repository.</span></span>
    6.  <span data-ttu-id="a16d9-121">Kattintson az **OK** lehetőségre az új tárház bejegyzés megerősítéséhez.</span><span class="sxs-lookup"><span data-stu-id="a16d9-121">Click **OK** to confirm the new repository entry.</span></span>
    7.  <span data-ttu-id="a16d9-122">A rácsban jelölje be az **LCS** típus új tárházát.</span><span class="sxs-lookup"><span data-stu-id="a16d9-122">In the grid, select the new repository of the **LCS** type.</span></span>

6.  <span data-ttu-id="a16d9-123">Kattintson a **Megnyitás** lehetőségre a kijelölt tárház ER-konfigurációk listájának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="a16d9-123">Click **Open** to view the list of ER configurations for the selected repository.</span></span> <span data-ttu-id="a16d9-124">[![Az ER frissítése az MS LCS rendszerből - LCS-tárház készítése](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span><span class="sxs-lookup"><span data-stu-id="a16d9-124">[![update-er-from-lcs-for-ms-make-lcs-repository](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span></span>
7.  <span data-ttu-id="a16d9-125">A bal oldali ablaktáblában jelölje ki a konfigurációkban jelölje ki a szükséges ER-konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="a16d9-125">In the configurations tree in the left pane, select the ER configuration that you require.</span></span>
8.  <span data-ttu-id="a16d9-126">A **Verziók** gyorslapon válassza ki a kijelölt ER-konfiguráció szükséges verzióját.</span><span class="sxs-lookup"><span data-stu-id="a16d9-126">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
9.  <span data-ttu-id="a16d9-127">Kattintson az **Importálás** lehetőségre a kiválasztott verzió LCS rendszerből a jelenlegi Finance and Operations példányba történő letöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="a16d9-127">Click **Import** to download the selected version from LCS to the current Finance and Operations instance.</span></span> <span data-ttu-id="a16d9-128">**Megjegyzés:** Az **Importálás** gomb nem érhető el azon ER konfigurációs verziókhoz, amelyek már szerepelnek a Finance and Operations aktuális példányában.</span><span class="sxs-lookup"><span data-stu-id="a16d9-128">**Note:** The **Import** button is unavailable for ER configuration versions that are already present in the current Finance and Operations instance.</span></span> <span data-ttu-id="a16d9-129">[![Az ER frissítése az MS LCS rendszerből - Konfiguráció letöltése](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="a16d9-129">[![update-er-from-lcs-for-ms-download-configuration](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span></span>

<span data-ttu-id="a16d9-130">**Megjegyzés:** Az ER beállításoktól függ a konfigurációk érvényesítése azok importálását követően.</span><span class="sxs-lookup"><span data-stu-id="a16d9-130">**Note:** Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="a16d9-131">Előfordulhat, hogy bármilyen észlelt ellentmondásos problémáról értesítést kap.</span><span class="sxs-lookup"><span data-stu-id="a16d9-131">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="a16d9-132">Ezeket a problémákat meg kell oldania az importált konfiguráció verziójának használata előtt.</span><span class="sxs-lookup"><span data-stu-id="a16d9-132">You must resolve those issues before you can use the imported configuration version.</span></span> <span data-ttu-id="a16d9-133">További információkért nézze meg a jelen témakörrel kapcsolatos cikkek listáját.</span><span class="sxs-lookup"><span data-stu-id="a16d9-133">For more information, see the list of related articles for this topic.</span></span>

<a name="see-also"></a><span data-ttu-id="a16d9-134">Lásd még</span><span class="sxs-lookup"><span data-stu-id="a16d9-134">See also</span></span>
--------

[<span data-ttu-id="a16d9-135">Elektronikus jelentések áttekintése</span><span class="sxs-lookup"><span data-stu-id="a16d9-135">Electronic reporting overview</span></span>](general-electronic-reporting.md)




