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
ms.openlocfilehash: a1fac239524d4873a782e6a3d177a573a382d0f6
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/03/2019
ms.locfileid: "2552038"
---
# <a name="create-an-onboarding-template-by-using-dynamics-365-talent---onboard"></a><span data-ttu-id="342a7-104">Felvételi sablon létrehozása a Dynamics 365 Talent – Onboard használatával</span><span class="sxs-lookup"><span data-stu-id="342a7-104">Create an onboarding template by using Dynamics 365 Talent - Onboard</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="342a7-105">A Microsoft Dynamics 365 Talent: Onboard – Onboard számos olyan sablont kínál, amelyek segítségével a lehető leggyorsabban létrehozhatja felvételi útmutatóját.</span><span class="sxs-lookup"><span data-stu-id="342a7-105">Microsoft Dynamics 365 Talent: Onboard provides various templates that can help you create an onboarding guide as quickly as possible.</span></span> <span data-ttu-id="342a7-106">Felhasználhat egyet vagy többet ezen sablonok közül, vagy létrehozhatja a saját sablonjait.</span><span class="sxs-lookup"><span data-stu-id="342a7-106">You can use one or more of these templates, or you can create your own templates.</span></span> <span data-ttu-id="342a7-107">Az Onboard mintaszöveget is kínál, amelyet felhasználhat a saját sablonjai létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="342a7-107">Onboard provides sample text that you can use when you create your own templates.</span></span> <span data-ttu-id="342a7-108">Emitatt a folyamat még akkor is könnyű, ha a nulláról kezdi az útmutató létrehozását.</span><span class="sxs-lookup"><span data-stu-id="342a7-108">Therefore, the process is easy even if you start from scratch.</span></span>

## <a name="create-an-onboarding-template-from-an-existing-template"></a><span data-ttu-id="342a7-109">Felvételi sablon létrehozása meglévő sablonból</span><span class="sxs-lookup"><span data-stu-id="342a7-109">Create an onboarding template from an existing template</span></span>

1. <span data-ttu-id="342a7-110">A bal oldali menüben válassza a **Sablonok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="342a7-110">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="342a7-111">A **Népszerű sablonok a tárból** vagy a **Saját sablonok** alatt válasszon sablont.</span><span class="sxs-lookup"><span data-stu-id="342a7-111">Under **Popular templates from the gallery** or **My templates**, select a template.</span></span> <span data-ttu-id="342a7-112">További sablonokat úgy jeleníthet meg, hogy **A sablontárban továbbiak találhatók** lehetőségre kattint.</span><span class="sxs-lookup"><span data-stu-id="342a7-112">To view more templates, select **More in template gallery**.</span></span>
3. <span data-ttu-id="342a7-113">Tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="342a7-113">Follow one of these steps:</span></span>

    - <span data-ttu-id="342a7-114">Ha a sablon a galériából származik, válassza a **Mentés sablonként** parancsot, adjon meg egy új nevet a sablonnak, majd válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="342a7-114">If the template is from the gallery, select **Save as my template**, enter a new name for the template, and select **Save**.</span></span>
    - <span data-ttu-id="342a7-115">Ha a sablon a **Saját sablonok** közül származik, válassza a **Mentés sablonként** parancsot, adjon meg egy új nevet a sablonnak, majd válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="342a7-115">If the template is from **My templates**, select **Save as template**, enter a new name for the template, and select **Save**.</span></span>

    <span data-ttu-id="342a7-116">[![Sablon létrehozása meglévő sablonból](./media/onboard-save-template.png)](./media/onboard-save-template.png)</span><span class="sxs-lookup"><span data-stu-id="342a7-116">[![Creating a template from an existing template](./media/onboard-save-template.png)](./media/onboard-save-template.png)</span></span>

## <a name="create-a-new-onboarding-template"></a><span data-ttu-id="342a7-117">Új felvételi sablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="342a7-117">Create a new onboarding template</span></span>

1. <span data-ttu-id="342a7-118">A bal oldali menüben válassza a **Sablonok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="342a7-118">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="342a7-119">A **Saját sablonok** területen válassza a **Hozzáadás** (plusz jel \[**+**\]) csempét.</span><span class="sxs-lookup"><span data-stu-id="342a7-119">Under **My templates**, select the **Add** (plus sign \[**+**\]) tile.</span></span>

    <span data-ttu-id="342a7-120">[![Új sablon létrehozása](./media/onboard-create-new-template.png)](./media/onboard-create-new-template.png)</span><span class="sxs-lookup"><span data-stu-id="342a7-120">[![Creating a new template](./media/onboard-create-new-template.png)](./media/onboard-create-new-template.png)</span></span>

3. <span data-ttu-id="342a7-121">Adja meg a sablon nevét az **Útmutatósablon létrehozása** párbeszédpanelen, majd kattintson a **Mentés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="342a7-121">In the **Create a guide template** dialog box, enter a name for the template, and then select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="342a7-122">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="342a7-122">Next steps</span></span>

- [<span data-ttu-id="342a7-123">Bevezetési útmutatók és sablonok szerkesztése</span><span class="sxs-lookup"><span data-stu-id="342a7-123">Edit onboarding guides and templates</span></span>](./onboard-edit-guides-templates.md)
- [<span data-ttu-id="342a7-124">Osszon meg tartalmakat más közreműködőkkel</span><span class="sxs-lookup"><span data-stu-id="342a7-124">Share content with other contributors</span></span>](./onboard-share-template.md)
- [<span data-ttu-id="342a7-125">A feladatok és az alkalmazottak és bevezetési állapotának megtekintése</span><span class="sxs-lookup"><span data-stu-id="342a7-125">View the status of tasks and onboarding employees</span></span>](./onboard-view-status.md)
- [<span data-ttu-id="342a7-126">Toborzócsoportok létrehozása az Onboard alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="342a7-126">Create hiring teams in Onboard</span></span>](./onboard-create-team.md)

### <a name="see-also"></a><span data-ttu-id="342a7-127">Lásd még</span><span class="sxs-lookup"><span data-stu-id="342a7-127">See also</span></span>

- [<span data-ttu-id="342a7-128">Próbálja ki vagy vásárolja meg az Onboard alkalmazást</span><span class="sxs-lookup"><span data-stu-id="342a7-128">Try or buy the Onboard app</span></span>](https://dynamics.microsoft.com/talent/onboard/)
- [<span data-ttu-id="342a7-129">Újdonságok</span><span class="sxs-lookup"><span data-stu-id="342a7-129">What's new</span></span>](./whats-new.md)
- [<span data-ttu-id="342a7-130">Programverzióra vonatkozó megjegyzések</span><span class="sxs-lookup"><span data-stu-id="342a7-130">Release notes</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="342a7-131">Támogatás kérése</span><span class="sxs-lookup"><span data-stu-id="342a7-131">Get support</span></span>](./talent-support.md)
