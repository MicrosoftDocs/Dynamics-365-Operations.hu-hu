---
title: Toborzócsapat létrehozása a Dynamics 365 Talent – Onboard használatával
description: Ez a témakör bemutatja, hogyan használhatja a Microsoft Dynamics 365 Talent – Onboard alkalmazást arra, hogy felvételi csoportokat hozzon létre.
author: andreabichsel
manager: ''
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7057c5b24ee3ae03574ec106a0c7d268dfffb98e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461412"
---
# <a name="create-a-hiring-team"></a><span data-ttu-id="2c25f-103">Toborzócsapat létrehozása</span><span class="sxs-lookup"><span data-stu-id="2c25f-103">Create a hiring team</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2c25f-104">A Microsoft Dynamics 365 Talent: Onboard alkalmazásban létrehozhat toborzócsapatokat is</span><span class="sxs-lookup"><span data-stu-id="2c25f-104">In Microsoft Dynamics 365 Talent: Onboard, you can create hiring teams.</span></span> <span data-ttu-id="2c25f-105">Ezután minden csapatnak kioszthat felvételi útmutatókat és sablonokat nekik.</span><span class="sxs-lookup"><span data-stu-id="2c25f-105">You can then assign onboarding guides and templates to each team.</span></span>

## <a name="create-a-hiring-team"></a><span data-ttu-id="2c25f-106">Toborzócsapat létrehozása</span><span class="sxs-lookup"><span data-stu-id="2c25f-106">Create a hiring team</span></span>

1. <span data-ttu-id="2c25f-107">A bal oldali menüben válassza a **Csapatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2c25f-107">On the left menu, select **Teams**.</span></span>
2. <span data-ttu-id="2c25f-108">A **Csapatok** területen válassza a **Hozzáadás** (plusz jel \[**+**\]) csempét.</span><span class="sxs-lookup"><span data-stu-id="2c25f-108">Under **Teams**, select the **Add** (plus sign \[**+**\]) tile.</span></span>
3. <span data-ttu-id="2c25f-109">Az **Új csapat** létrehozása párbeszédpanel **Csapat neve** mezőjében adjon meg egy nevet a toborzócsapatnak.</span><span class="sxs-lookup"><span data-stu-id="2c25f-109">In the **Create a new team** dialog box, under **Team name**, enter a name for the hiring team.</span></span>

    ![[<span data-ttu-id="2c25f-110">Új csapat létrehozása az Onboardban</span><span class="sxs-lookup"><span data-stu-id="2c25f-110">Creating a new team in Onboard</span></span>](./media/onboard-create-team.png)](./media/onboard-create-team.png)

4. <span data-ttu-id="2c25f-111">A **Csapattagok kiválasztása** területen adja meg az egyes csapattagok nevét vagy e-mail címét.</span><span class="sxs-lookup"><span data-stu-id="2c25f-111">Under **Choose team members**, enter the name or email address of each team member.</span></span>

    <span data-ttu-id="2c25f-112">A csapattagok eltávolításához jelölje ki azt **X** jelet, amely a neve mellett jelenik meg a mező alatt.</span><span class="sxs-lookup"><span data-stu-id="2c25f-112">To remove team members, select the **X** that appears next to their name under the box.</span></span>

5. <span data-ttu-id="2c25f-113">Ha új csapattagoknak szeretne e-mailt küldeni, kapcsolja be az **E-mail küldése az új tagoknak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2c25f-113">To email new team members, turn on the **Send an email to the new members** option.</span></span>
6. <span data-ttu-id="2c25f-114">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2c25f-114">Select **Create**.</span></span>
7. <span data-ttu-id="2c25f-115">Ha azt jelezte, hogy új csapattagokkal kíván e-mailt küldeni, szerkessze az e-mailt a következő párbeszédpanelen, majd válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2c25f-115">If you indicated that you want to email new team members, edit the email in the next dialog box, and then select **Done**.</span></span>

## <a name="assign-onboarding-guides-to-a-hiring-team"></a><span data-ttu-id="2c25f-116">Felvételi útmutatók hozzárendelése egy toborzócsapathoz</span><span class="sxs-lookup"><span data-stu-id="2c25f-116">Assign onboarding guides to a hiring team</span></span>

1. <span data-ttu-id="2c25f-117">A bal oldali menüben válassza a **Csapatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2c25f-117">On the left menu, select **Teams**.</span></span>
2. <span data-ttu-id="2c25f-118">Válassza a csapat lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2c25f-118">Select the team.</span></span>
3. <span data-ttu-id="2c25f-119">Az **Útmutatók** lapon válassza az **Útmutatók hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2c25f-119">On the **Guides** tab, select **Add guides**.</span></span>

    ![[<span data-ttu-id="2c25f-120">Felvételi útmutatók hozzáadása egy csapathoz</span><span class="sxs-lookup"><span data-stu-id="2c25f-120">Adding onboarding guides to a team</span></span>](./media/onboard-add-guides-to-team.png)](./media/onboard-add-guides-to-team.png)

4. <span data-ttu-id="2c25f-121">Jelölje be az összes olyan felvételi útmutatóhoz tartozó jelölőnégyzetet, amelyet hozzá kíván rendelni a csapathoz, majd válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2c25f-121">Select the check box for each onboarding guide that you want to assign to the team, and then select **Add**.</span></span>

    ![[<span data-ttu-id="2c25f-122">A csapatba felvenni kívánt felvételi útmutatók kiválasztása</span><span class="sxs-lookup"><span data-stu-id="2c25f-122">Selecting the onboarding guides to add to the team</span></span>](./media/onboard-select-guides.png)](./media/onboard-select-guides.png)

## <a name="assign-onboarding-templates-to-a-hiring-team"></a><span data-ttu-id="2c25f-123">Felvételi sablonok hozzárendelése egy toborzócsapathoz</span><span class="sxs-lookup"><span data-stu-id="2c25f-123">Assign onboarding templates to a hiring team</span></span>

1. <span data-ttu-id="2c25f-124">A bal oldali menüben válassza a **Csapatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2c25f-124">On the left menu, select **Teams**.</span></span>
2. <span data-ttu-id="2c25f-125">Válassza a csapat lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2c25f-125">Select the team.</span></span>
3. <span data-ttu-id="2c25f-126">A **Sablonok** lapon válassza a **Sablonok hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2c25f-126">On the **Templates** tab, select **Add templates**.</span></span>

    ![[<span data-ttu-id="2c25f-127">Sablonok hozzáadása a csapathoz</span><span class="sxs-lookup"><span data-stu-id="2c25f-127">Adding templates to a team</span></span>](./media/onboard-add-templates-to-team.png)](./media/onboard-add-templates-to-team.png)

4. <span data-ttu-id="2c25f-128">Jelölje be az összes olyan sablonhoz tartozó jelölőnégyzetet, amelyet hozzá kíván rendelni a csapathoz, majd válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2c25f-128">Select the check box for each template that you want to assign to the team, and then select **Add**.</span></span>

    ![[<span data-ttu-id="2c25f-129">A csapatba felvenni kívánt sablonok kiválasztása</span><span class="sxs-lookup"><span data-stu-id="2c25f-129">Selecting the templates to add to the team</span></span>](./media/onboard-select-templates.png)](./media/onboard-select-templates.png)

### <a name="see-also"></a><span data-ttu-id="2c25f-130">Lásd még</span><span class="sxs-lookup"><span data-stu-id="2c25f-130">See also</span></span>

- [<span data-ttu-id="2c25f-131">Próbálja ki vagy vásárolja meg az Onboard alkalmazást</span><span class="sxs-lookup"><span data-stu-id="2c25f-131">Try or buy the Onboard app</span></span>](https://dynamics.microsoft.com/talent/onboard/)
- [<span data-ttu-id="2c25f-132">Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="2c25f-132">What's new or changed in Dynamics 365 Talent</span></span>](./whats-new.md)
- [<span data-ttu-id="2c25f-133">Kiadási tervek</span><span class="sxs-lookup"><span data-stu-id="2c25f-133">Release plans</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="2c25f-134">Támogatás kérése a Microsoft Dynamics 365 Talent alkalmazáshoz</span><span class="sxs-lookup"><span data-stu-id="2c25f-134">Get support for Microsoft Dynamics 365 Talent</span></span>](./talent-support.md)
