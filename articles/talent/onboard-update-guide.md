---
title: Felvételi útmutatók frissítése a Dynamics 365 Talent – Onboard szolgáltatásban
description: Ez a témakör azt ismerteti, hogy miként frissíthetők a Microsoft Dynamics 365 Talent – Onboard felvételi útmutatói, illetve hogyan lehet a meglévő útmutatók módosításait leküldeni.
author: andreabichsel
manager: ''
ms.date: 06/21/2019
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
ms.search.validFrom: 2019-06-21
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 071aa79ea75e9a94187dd74dabab940e2cce0f92
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551956"
---
# <a name="update-onboarding-guides-in-dynamics-365-talent---onboard"></a><span data-ttu-id="244dc-103">Felvételi útmutatók frissítése a Dynamics 365 Talent – Onboard szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="244dc-103">Update onboarding guides in Dynamics 365 Talent - Onboard</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="244dc-104">Ha módosítania kell a felvételi útmutatókat a Microsoft Dynamics 365 Talent: Onboard szolgáltatásban, frissítheti őket, és érvényesítheti a változtatásokat, még akkor is, ha már kiküldte az útmutatókat.</span><span class="sxs-lookup"><span data-stu-id="244dc-104">If you must make changes to onboarding guides in Microsoft Dynamics 365 Talent: Onboard, you can update them and push the changes, even if you've already sent the guides.</span></span> <span data-ttu-id="244dc-105">A felvételi útmutató frissítéséhez két lehetőség közül választhat:</span><span class="sxs-lookup"><span data-stu-id="244dc-105">You have two options for updating an onboarding guide:</span></span>

- <span data-ttu-id="244dc-106">Szerkessze közvetlenül a felvételi útmutatót, és mentse a változtatásokat.</span><span class="sxs-lookup"><span data-stu-id="244dc-106">Edit the onboarding guide directly, and save your changes.</span></span>
- <span data-ttu-id="244dc-107">Szerkessze a felvételi sablont, majd érvényesítse a változtatásokat az abból létrehozott összes felvételi útmutatóban.</span><span class="sxs-lookup"><span data-stu-id="244dc-107">Edit the onboarding template, and then push the changes to all the onboarding guides that were created from it.</span></span>

## <a name="edit-an-onboarding-guide-directly"></a><span data-ttu-id="244dc-108">Felvételi útmutató szerkesztése közvetlenül</span><span class="sxs-lookup"><span data-stu-id="244dc-108">Edit an onboarding guide directly</span></span>

1. <span data-ttu-id="244dc-109">A bal oldali menüben válassza a **Guides** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="244dc-109">On the left menu, select **Guides**.</span></span>
2. <span data-ttu-id="244dc-110">Jelölje ki a szerkeszteni kívánt útmutatót.</span><span class="sxs-lookup"><span data-stu-id="244dc-110">Select the guide that you want to edit.</span></span>
3. <span data-ttu-id="244dc-111">Végezze el az összes kívánt változtatást, majd válassza a **Mentés** gombra (a lemez szimbólumra).</span><span class="sxs-lookup"><span data-stu-id="244dc-111">Make all the desired changes, and then select the **Save** button (the disk symbol).</span></span>

    ![[<span data-ttu-id="244dc-112">A felvételi útmutató módosításainak mentéése</span><span class="sxs-lookup"><span data-stu-id="244dc-112">Saving changes to an onboarding guide</span></span>](./media/onboard-save.png)](./media/onboard-save.png)

<span data-ttu-id="244dc-113">Az Onboard automatikusan e-mailt küld az újonnan felvett személynek, amelyben bemutatja a változtatásokat.</span><span class="sxs-lookup"><span data-stu-id="244dc-113">Onboard will automatically send the new hire an email that indicates what the changes are.</span></span> <span data-ttu-id="244dc-114">Az egyszerű azonosítás érdekében egy piros **Új** címke jelenik meg minden egyes változtatás mellett.</span><span class="sxs-lookup"><span data-stu-id="244dc-114">For easy identification, a red **New** tag will appear next to each change.</span></span>

## <a name="update-multiple-guides-by-editing-the-onboarding-template"></a><span data-ttu-id="244dc-115">Több útmutató frissítése a felvételi sablon szerkesztésével</span><span class="sxs-lookup"><span data-stu-id="244dc-115">Update multiple guides by editing the onboarding template</span></span>

1. <span data-ttu-id="244dc-116">A bal oldali menüben válassza a **Sablonok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="244dc-116">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="244dc-117">A **Saját sablonok** területen válassza ki a szerkeszteni kívánt sablont.</span><span class="sxs-lookup"><span data-stu-id="244dc-117">Under **My templates**, select the template that you want to edit.</span></span>
3. <span data-ttu-id="244dc-118">Végezze el az összes kívánt változtatást, majd válassza a **Mentés** gombra (a lemez szimbólumra).</span><span class="sxs-lookup"><span data-stu-id="244dc-118">Make all the desired changes, and then select the **Save** button (the disk symbol).</span></span>
4. <span data-ttu-id="244dc-119">Ha azt szeretné, hogy a módosítások a sablonon alapuló összes útmutatóban érvényesüljenek, válassza a **Módosítások áttolása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="244dc-119">To push your changes to all the guides that are based on the template, select **Push these changes**.</span></span>

    ![[<span data-ttu-id="244dc-120">A felvételi sablon változtatásainak érvényesítése az abból létrehozott összes felvételi útmutatóban</span><span class="sxs-lookup"><span data-stu-id="244dc-120">Pushing the changes in an onboarding template to all guides that were created from it</span></span>](./media/onboard-push-changes.png)](./media/onboard-push-changes.png)

<span data-ttu-id="244dc-121">A módosítások láthatóvá válnak az új dolgozóknak, akik megnyitják a felvételi útmutatókat.</span><span class="sxs-lookup"><span data-stu-id="244dc-121">The changes will be visible to new hires who open the onboarding guides.</span></span> <span data-ttu-id="244dc-122">Az Onboard azonban nem küld e-mail-értesítést az új dolgozók számára, hogy tudassa velük, hogy a felvételi útmutató módosult.</span><span class="sxs-lookup"><span data-stu-id="244dc-122">However, Onboard won't send email alerts to new hires to let them know that their onboarding guide has changed.</span></span> <span data-ttu-id="244dc-123">Az egyszerű azonosítás érdekében egy piros **Új** címke jelenik meg minden egyes változtatás mellett.</span><span class="sxs-lookup"><span data-stu-id="244dc-123">For easy identification, a red **New** tag will appear next to each change.</span></span> 
