---
title: "A Talent nem jelenik meg a Microsoft Dynamics 365 alkalmazások között (CDS1.0)"
description: "Ez a témakör bemutatja, mi a teendő, ha a vevő nem látja a Microsoft Dynamics 365 for Talent alkalmazást a Microsoft Dynamics 365 alkalmazások között."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 32ae0ab807e953bd811a557e6878b9bee79d293c
ms.contentlocale: hu-hu
ms.lasthandoff: 12/04/2018

---

# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-cds10"></a><span data-ttu-id="590b9-103">A Talent nem jelenik meg a Microsoft Dynamics 365 alkalmazások között (CDS1.0)</span><span class="sxs-lookup"><span data-stu-id="590b9-103">Talent doesn't appear among the Microsoft Dynamics 365 apps (CDS1.0)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="590b9-104">**Probléma**</span><span class="sxs-lookup"><span data-stu-id="590b9-104">**Issue**</span></span>

<span data-ttu-id="590b9-105">A vevő nem látja a Microsoft Dynamics 365 for Talent alkalmazást a Microsoft Dynamics 365 alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="590b9-105">The customer doesn't see the Microsoft Dynamics 365 for Talent app among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="590b9-106">**Felbontás**</span><span class="sxs-lookup"><span data-stu-id="590b9-106">**Resolution**</span></span>

<span data-ttu-id="590b9-107">A felhasználót hozzá kell adni a környezet Környezetkészítő szerepköréhez a Microsoft PowerApps szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="590b9-107">The user must be added to the Environment Maker role for the environment in Microsoft PowerApps.</span></span>

1. <span data-ttu-id="590b9-108">A rendszergazdának, aki a PowerApps csomag 2 licenccel rendelkezik, meg kell nyitnia a [PowerApps felügyeleti központot](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="590b9-108">The admin user who has a PowerApps Plan 2 license must open the [PowerApps Admin portal](https://preview.admin.powerapps.com/).</span></span>
2. <span data-ttu-id="590b9-109">Válassza a **Környezetek** lehetőséget, majd válassza ki a megfelelő környezetet a Talent számára.</span><span class="sxs-lookup"><span data-stu-id="590b9-109">Select **Environments**, and select the correct environment for Talent.</span></span>
3. <span data-ttu-id="590b9-110">A **Biztonság** lapon a **Környezeti szerepkörök** lapon válassza a **Környezetkészítő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="590b9-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Környezeti szerepkörök lap](media/environment-roles.png)

4. <span data-ttu-id="590b9-112">A **Felhasználók** lapon adja hozzá a felhasználót vagy a szervezetet.</span><span class="sxs-lookup"><span data-stu-id="590b9-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Felhasználók lap](media/environment-maker.png)

5. <span data-ttu-id="590b9-114">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="590b9-114">Select **Save**.</span></span>
6. <span data-ttu-id="590b9-115">A felhasználónak most be kell jelentkeznie a [Microsoft Dynamics 365](https://home.dynamics.com/) szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="590b9-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>
7. <span data-ttu-id="590b9-116">Válassza a **Szinkronizálás** elemet a felhasználói alkalmazások frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="590b9-116">Select **Sync** to update the user apps.</span></span>

    ![Szinkronizálás gomb](media/get-more.png)

    <span data-ttu-id="590b9-118">A szinkronizálás befejezése után a Talent megjelenik a kezdőlapon.</span><span class="sxs-lookup"><span data-stu-id="590b9-118">After synchronization is completed, Talent will appear on the home page.</span></span>

