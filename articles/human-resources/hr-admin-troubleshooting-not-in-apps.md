---
title: A Human Resources szolgáltatás nem jelenik meg a Microsoft Dynamics 365 alkalmazásai között
description: Ez a cikk bemutatja, mi a teendő, ha a vevő nem látja a Microsoft Dynamics 365 Human Resources alkalmazást a Microsoft Dynamics 365 alkalmazások között.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cbf47b4673e1c97965bba7728e5669b7639c4d56
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431084"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a><span data-ttu-id="ff8ee-103">A Human Resources szolgáltatás nem jelenik meg a Microsoft Dynamics 365 alkalmazásai között</span><span class="sxs-lookup"><span data-stu-id="ff8ee-103">Human Resources doesn't appear in Microsoft Dynamics 365 apps</span></span>

<span data-ttu-id="ff8ee-104">**Kibocsátás**</span><span class="sxs-lookup"><span data-stu-id="ff8ee-104">**Issue**</span></span>

<span data-ttu-id="ff8ee-105">A vevő nem látja a Dynamics 365 Human Resources alkalmazást a Microsoft Dynamics 365-alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="ff8ee-105">The customer doesn't see Dynamics 365 Human Resources among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="ff8ee-106">**Feloldás**</span><span class="sxs-lookup"><span data-stu-id="ff8ee-106">**Resolution**</span></span>

<span data-ttu-id="ff8ee-107">A felhasználót hozzá kell adni a környezet Környezetkészítő szerepköréhez a Microsoft Power Apps szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="ff8ee-107">The user must be added to the Environment Maker role for the environment in Microsoft Power Apps.</span></span>

1. <span data-ttu-id="ff8ee-108">A rendszergazdának, aki a Power Apps 2. csomag licenccel rendelkezik, meg kell nyitnia a [Power Apps felügyeleti központot](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="ff8ee-108">The admin user who has a Power Apps Plan 2 license must open the [Power Apps Admin portal](https://preview.admin.powerapps.com/).</span></span>

2. <span data-ttu-id="ff8ee-109">Válassza a **Környezetek** lehetőséget, majd válassza ki a megfelelő környezetet a Human Resources számára.</span><span class="sxs-lookup"><span data-stu-id="ff8ee-109">Select **Environments**, and select the correct environment for Human Resources.</span></span>

3. <span data-ttu-id="ff8ee-110">A **Biztonság** lapon a **Környezeti szerepkörök** lapon válassza a **Környezetkészítő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ff8ee-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Környezeti szerepkörök lap](media/environment-roles.png)

4. <span data-ttu-id="ff8ee-112">A **Felhasználók** lapon adja hozzá a felhasználót vagy a szervezetet.</span><span class="sxs-lookup"><span data-stu-id="ff8ee-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Felhasználók lap](media/environment-maker.png)

5. <span data-ttu-id="ff8ee-114">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ff8ee-114">Select **Save**.</span></span>

6. <span data-ttu-id="ff8ee-115">A felhasználónak most be kell jelentkeznie a [Microsoft Dynamics 365](https://home.dynamics.com/) szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="ff8ee-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>

7. <span data-ttu-id="ff8ee-116">Válassza a **Szinkronizálás** elemet a felhasználói alkalmazások frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="ff8ee-116">Select **Sync** to update the user apps.</span></span>

    ![Szinkronizálás gomb](media/get-more.png)

    <span data-ttu-id="ff8ee-118">A szinkronizálás befejezése után a Human Resources szolgáltatás megjelenik a kezdőlapon.</span><span class="sxs-lookup"><span data-stu-id="ff8ee-118">After synchronization is completed, Human Resources will appear on the home page.</span></span>
