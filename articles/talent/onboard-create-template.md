---
title: Felvételi sablon létrehozása a Dynamics 365 Talent – Onboard használatával
description: Ez a témakör bemutatja, hogyan használhatja a Dynamics 365 Talent – Onboard alkalmazást arra, hogy sablont hozzon létre egy bevezető útmutatóhoz az újonnan felvettek számára. Ez a feladat fontos első lépés a humánerőforrás-kezelési szolgáltatás (HCM) nyugdíjazásig történő felvétel stratégiájában.
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
ms.openlocfilehash: 55853418eacd179b7bb50b7e4385300bdcb27abe
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812902"
---
# <a name="create-an-onboarding-template-by-using-dynamics-365-talent---onboard"></a><span data-ttu-id="285bf-104">Felvételi sablon létrehozása a Dynamics 365 Talent – Onboard használatával</span><span class="sxs-lookup"><span data-stu-id="285bf-104">Create an onboarding template by using Dynamics 365 Talent - Onboard</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="285bf-105">A Microsoft Dynamics 365 Talent: Onboard – Onboard számos olyan sablont kínál, amelyek segítségével a lehető leggyorsabban létrehozhatja felvételi útmutatóját.</span><span class="sxs-lookup"><span data-stu-id="285bf-105">Microsoft Dynamics 365 Talent: Onboard provides various templates that can help you create an onboarding guide as quickly as possible.</span></span> <span data-ttu-id="285bf-106">Felhasználhat egyet vagy többet ezen sablonok közül, vagy létrehozhatja a saját sablonjait.</span><span class="sxs-lookup"><span data-stu-id="285bf-106">You can use one or more of these templates, or you can create your own templates.</span></span> <span data-ttu-id="285bf-107">Az Onboard mintaszöveget is kínál, amelyet felhasználhat a saját sablonjai létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="285bf-107">Onboard provides sample text that you can use when you create your own templates.</span></span> <span data-ttu-id="285bf-108">Emitatt a folyamat még akkor is könnyű, ha a nulláról kezdi az útmutató létrehozását.</span><span class="sxs-lookup"><span data-stu-id="285bf-108">Therefore, the process is easy even if you start from scratch.</span></span>

## <a name="create-an-onboarding-template-from-an-existing-template"></a><span data-ttu-id="285bf-109">Felvételi sablon létrehozása meglévő sablonból</span><span class="sxs-lookup"><span data-stu-id="285bf-109">Create an onboarding template from an existing template</span></span>

1. <span data-ttu-id="285bf-110">A bal oldali menüben válassza a **Sablonok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="285bf-110">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="285bf-111">A **Népszerű sablonok a tárból** vagy a **Saját sablonok** alatt válasszon sablont.</span><span class="sxs-lookup"><span data-stu-id="285bf-111">Under **Popular templates from the gallery** or **My templates**, select a template.</span></span> <span data-ttu-id="285bf-112">További sablonokat úgy jeleníthet meg, hogy **A sablontárban továbbiak találhatók** lehetőségre kattint.</span><span class="sxs-lookup"><span data-stu-id="285bf-112">To view more templates, select **More in template gallery**.</span></span>
3. <span data-ttu-id="285bf-113">Tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="285bf-113">Follow one of these steps:</span></span>

    - <span data-ttu-id="285bf-114">Ha a sablon a galériából származik, válassza a **Mentés sablonként** parancsot, adjon meg egy új nevet a sablonnak, majd válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="285bf-114">If the template is from the gallery, select **Save as my template**, enter a new name for the template, and select **Save**.</span></span>
    - <span data-ttu-id="285bf-115">Ha a sablon a **Saját sablonok** közül származik, válassza a **Mentés sablonként** parancsot, adjon meg egy új nevet a sablonnak, majd válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="285bf-115">If the template is from **My templates**, select **Save as template**, enter a new name for the template, and select **Save**.</span></span>

    <span data-ttu-id="285bf-116">[![Sablon létrehozása meglévő sablonból](./media/onboard-save-template.png)](./media/onboard-save-template.png)</span><span class="sxs-lookup"><span data-stu-id="285bf-116">[![Creating a template from an existing template](./media/onboard-save-template.png)](./media/onboard-save-template.png)</span></span>

## <a name="create-a-new-onboarding-template"></a><span data-ttu-id="285bf-117">Új felvételi sablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="285bf-117">Create a new onboarding template</span></span>

1. <span data-ttu-id="285bf-118">A bal oldali menüben válassza a **Sablonok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="285bf-118">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="285bf-119">A **Saját sablonok** területen válassza a **Hozzáadás** (plusz jel \[**+**\]) csempét.</span><span class="sxs-lookup"><span data-stu-id="285bf-119">Under **My templates**, select the **Add** (plus sign \[**+**\]) tile.</span></span>

    <span data-ttu-id="285bf-120">[![Új sablon létrehozása](./media/onboard-create-new-template.png)](./media/onboard-create-new-template.png)</span><span class="sxs-lookup"><span data-stu-id="285bf-120">[![Creating a new template](./media/onboard-create-new-template.png)](./media/onboard-create-new-template.png)</span></span>

3. <span data-ttu-id="285bf-121">Adja meg a sablon nevét az **Útmutatósablon létrehozása** párbeszédpanelen, majd kattintson a **Mentés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="285bf-121">In the **Create a guide template** dialog box, enter a name for the template, and then select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="285bf-122">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="285bf-122">Next steps</span></span>

- [<span data-ttu-id="285bf-123">Bevezetési útmutatók és sablonok szerkesztése</span><span class="sxs-lookup"><span data-stu-id="285bf-123">Edit onboarding guides and templates</span></span>](./onboard-edit-guides-templates.md)
- [<span data-ttu-id="285bf-124">Osszon meg tartalmakat más közreműködőkkel</span><span class="sxs-lookup"><span data-stu-id="285bf-124">Share content with other contributors</span></span>](./onboard-share-template.md)
- [<span data-ttu-id="285bf-125">A feladatok és az alkalmazottak és bevezetési állapotának megtekintése</span><span class="sxs-lookup"><span data-stu-id="285bf-125">View the status of tasks and onboarding employees</span></span>](./onboard-view-status.md)
- [<span data-ttu-id="285bf-126">Toborzócsoportok létrehozása az Onboard alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="285bf-126">Create hiring teams in Onboard</span></span>](./onboard-create-team.md)

### <a name="see-also"></a><span data-ttu-id="285bf-127">Lásd még</span><span class="sxs-lookup"><span data-stu-id="285bf-127">See also</span></span>

- [<span data-ttu-id="285bf-128">Próbálja ki vagy vásárolja meg az Onboard alkalmazást</span><span class="sxs-lookup"><span data-stu-id="285bf-128">Try or buy the Onboard app</span></span>](https://dynamics.microsoft.com/talent/onboard/)
- [<span data-ttu-id="285bf-129">Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="285bf-129">What's new or changed in Dynamics 365 Talent</span></span>](./whats-new.md)
- [<span data-ttu-id="285bf-130">Kiadási tervek</span><span class="sxs-lookup"><span data-stu-id="285bf-130">Release plans</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="285bf-131">Támogatás kérése a Microsoft Dynamics 365 Talent alkalmazáshoz</span><span class="sxs-lookup"><span data-stu-id="285bf-131">Get support for Microsoft Dynamics 365 Talent</span></span>](./talent-support.md)
