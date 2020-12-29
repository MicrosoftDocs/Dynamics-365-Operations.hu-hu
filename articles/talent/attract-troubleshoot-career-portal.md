---
title: Az Attract-felhasználók nem tudnak állásokra jelentkezni a karrierportálon
description: Ez a témakör azt mutatja be, hogyan lehet elhárítani azt a hibát, amely miatt a felhasználók nem tudnak állásokra jelentkezni a karrier portálról.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: e1d72bef6d8bbe15e27326f66341915ba44a09b4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461366"
---
# <a name="attract-users-cant-apply-for-jobs-from-career-portal"></a><span data-ttu-id="ae4b6-103">Az Attract-felhasználók nem tudnak állásokra jelentkezni a karrierportálon</span><span class="sxs-lookup"><span data-stu-id="ae4b6-103">Attract users can't apply for jobs from career portal</span></span>

[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="ae4b6-104">Kiadás</span><span class="sxs-lookup"><span data-stu-id="ae4b6-104">Issue</span></span>

<span data-ttu-id="ae4b6-105">Az Attract-felhasználók nem tudnak állásokra jelentkezni a karrierportálon.</span><span class="sxs-lookup"><span data-stu-id="ae4b6-105">Attract users can't apply for jobs from the career portal.</span></span> <span data-ttu-id="ae4b6-106">Amikor egy olyan munkára próbálnak jelentkezni, amely a Dynamics 365 Talent: Attract alkalmazásban lett létrehozva, a böngésző folyamatosan betölti az oldalt, és nem teljesíti a műveletet.</span><span class="sxs-lookup"><span data-stu-id="ae4b6-106">When they try to apply for a job that was created in Dynamics 365 Talent: Attract, the browser loads the page continuously and doesn't complete the action.</span></span>

## <a name="cause"></a><span data-ttu-id="ae4b6-107">Ok</span><span class="sxs-lookup"><span data-stu-id="ae4b6-107">Cause</span></span>

<span data-ttu-id="ae4b6-108">Ez a probléma akkor fordul elő, ha a Talent kapcsolati csoport nem rendelkezik a Talent felhasználói szerepkörrel.</span><span class="sxs-lookup"><span data-stu-id="ae4b6-108">This problem occurs when the Talent Relationship Team doesn't have the Talent user role.</span></span>

## <a name="resolution"></a><span data-ttu-id="ae4b6-109">Felbontás</span><span class="sxs-lookup"><span data-stu-id="ae4b6-109">Resolution</span></span>

<span data-ttu-id="ae4b6-110">Rendelje hozzá a Talent felhasználói szerepkört a Talent kapcsolati csapathoz.</span><span class="sxs-lookup"><span data-stu-id="ae4b6-110">Assign the Talent user role to the Talent Relationship Team.</span></span>

1. <span data-ttu-id="ae4b6-111">Jelentkezzen be az [Power Platform felügyeleti központba](https://admin.powerplatform.microsoft.com) a következő adminisztrátori hitelesítő adatokkal:</span><span class="sxs-lookup"><span data-stu-id="ae4b6-111">Sign in to the [Power Platform admin center](https://admin.powerplatform.microsoft.com) with any of the following admin credentials:</span></span>

   - <span data-ttu-id="ae4b6-112">Dynamics 365 adminisztrátor</span><span class="sxs-lookup"><span data-stu-id="ae4b6-112">Dynamics 365 admin</span></span>
   - <span data-ttu-id="ae4b6-113">Globális adminisztrátor</span><span class="sxs-lookup"><span data-stu-id="ae4b6-113">Global admin</span></span>
   - <span data-ttu-id="ae4b6-114">Power Platform adminisztrátor</span><span class="sxs-lookup"><span data-stu-id="ae4b6-114">Power Platform admin</span></span>

2. <span data-ttu-id="ae4b6-115">Válassza ki a navigációs ablak **Környezetek** elemét, majd válassza ki azt a környezetet, amelyben a Talent felhasználói szerepkört társítani szeretné a Talent-kapcsolati csapathoz.</span><span class="sxs-lookup"><span data-stu-id="ae4b6-115">In the navigation pane, select **Environments**, and then select the environment in which to assign the Talent user role to the Talent Relationship Team.</span></span>

   ![Környezet kiválasztása](./media/attract-troubleshoot-career-portal-select-environment.png)

3. <span data-ttu-id="ae4b6-117">A **Környezetek** ablaktáblán válassza ki a **Környezet URL-címét**, és jelentkezzen be a környezet adminisztrátori portálján (például https:<orgname>.crm.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="ae4b6-117">In the **Environments** pane, select the **Environment URL** and sign in to the environment's admin portal (for example, https:<orgname>.crm.dynamics.com).</span></span>

4. <span data-ttu-id="ae4b6-118">Válassza a **Beállítások** lehetőséget, válassza a **Rendszer** elemet , majd válassza a **Biztonság** elemet.</span><span class="sxs-lookup"><span data-stu-id="ae4b6-118">Select **Settings**, select **System**, and then select **Security**.</span></span>

   ![Navigálás a Biztonság részhez](./media/attract-troubleshoot-career-portal-security.png)

5. <span data-ttu-id="ae4b6-120">Válassza a **Csapatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ae4b6-120">Select **Teams**.</span></span>

   ![Csapatok kiválasztása](./media/attract-troubleshoot-career-portal-security-teams.png)

6. <span data-ttu-id="ae4b6-122">Keressen a **Talent kapcsolati csapat** kifejezésre a keresőmezőben, majd válassza ki a csapatot a keresési eredmények közül.</span><span class="sxs-lookup"><span data-stu-id="ae4b6-122">Search for **Talent Relationship Team** in the search box, and then select the team from the search results.</span></span>

7. <span data-ttu-id="ae4b6-123">Válassza a menüszalag **SZEREPKÖRÖK KEZELÉSE** elemét.</span><span class="sxs-lookup"><span data-stu-id="ae4b6-123">Select **MANAGE ROLES** from the ribbon.</span></span>

8. <span data-ttu-id="ae4b6-124">A **Csapatszerepkörök kezelése** párbeszédablakban válassza ki a **Talent felhasználó** elemet a választható szerepkörök listájából, majd válassza az **OK** lehetőséget a szerepkör alkalmazásához.</span><span class="sxs-lookup"><span data-stu-id="ae4b6-124">In the **Manage Team Roles** dialog, select **Talent user** from the list of available roles, and then select **OK** to apply the role.</span></span>

   ![Szerepkör alkalmazása](./media/attract-troubleshoot-career-portal-apply-role.png)

9. <span data-ttu-id="ae4b6-126">Tesztelje a módosításokat:</span><span class="sxs-lookup"><span data-stu-id="ae4b6-126">Test your changes:</span></span>

   1. <span data-ttu-id="ae4b6-127">Jelentkezzen be a karrierportálra egy új böngészőablakból.</span><span class="sxs-lookup"><span data-stu-id="ae4b6-127">Sign in to the career portal from a new browser window.</span></span>
   2. <span data-ttu-id="ae4b6-128">Pályázzon állásra a karrierportálról.</span><span class="sxs-lookup"><span data-stu-id="ae4b6-128">Apply for the job from the career portal.</span></span> 