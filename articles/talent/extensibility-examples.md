---
title: Talent bővítése a Power Apps és Power Automate szolgáltatásokkal
description: Ez a cikk néhány bővítési forgatókönyvet ír le a Microsoft Dynamics 365 Talent – Attract alkalmazáshoz, amelyek a Microsoft Power Apps és Microsoft Power Automate megoldásokat használják.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: cfdf36e9486aa4853d3bf674afa73ec3a4d1c161
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529634"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a><span data-ttu-id="a8701-103">Talent bővítése a Power Apps és Power Automate szolgáltatásokkal</span><span class="sxs-lookup"><span data-stu-id="a8701-103">Extend Talent with Power Apps and Power Automate</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a8701-104">Ez a cikk néhány bővítési forgatókönyvet ír le a Microsoft Dynamics 365 Talent: Attract alkalmazáshoz, amelyek a Microsoft Power Apps és Microsoft Power Automate megoldásokat használják.</span><span class="sxs-lookup"><span data-stu-id="a8701-104">This article describes some examples of extensibility scenarios for Microsoft Dynamics 365 Talent: Attract that use Microsoft Power Apps and Microsoft Power Automate.</span></span> <span data-ttu-id="a8701-105">Az egyes példákhoz társított megoldáscsomagot importálhatja a Power Apps környezetébe.</span><span class="sxs-lookup"><span data-stu-id="a8701-105">You can import the solution package that is associated with each example into your Power Apps environment.</span></span> <span data-ttu-id="a8701-106">Majd használhatja a csomagokat iránymutatásként vagy kiindulási pontként a szervezetre vonatkozó forgatókönyvek végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="a8701-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8701-107">Ha a cikkben bemutatott sablonokat és alkalmazást „adott” állapotukban szeretné használni, ügyeljen arra, hogy tesztelje az összeset, és győződjön meg arról minden az Ön implementációjához tartozó forgatókönyvet.</span><span class="sxs-lookup"><span data-stu-id="a8701-107">If you want to use the templates and app that are described in this article "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="a8701-108">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="a8701-108">Prerequisites</span></span>

- <span data-ttu-id="a8701-109">Csomagok importálásához felhasználóknak rendelkezniük kell a **Környezetkészítő** engedéllyel.</span><span class="sxs-lookup"><span data-stu-id="a8701-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="a8701-110">Az alkalmazások exportálásához vagy importálásához a felhasználóknak Power Apps Plan 2 licenccel, vagy Power Apps Plan 2 próbalicenccel kell rendelkezniük.</span><span class="sxs-lookup"><span data-stu-id="a8701-110">To export or import apps, users must have a Power Apps Plan 2 license or a Power Apps Plan 2 trial license.</span></span>

## <a name="power-automate--form-connect"></a><span data-ttu-id="a8701-111">Power Automate – Form Connect</span><span class="sxs-lookup"><span data-stu-id="a8701-111">Power Automate – Form Connect</span></span>

<span data-ttu-id="a8701-112">A **Power Automate – Form Connect** sablon adatok beolvasására használható Microsoft Forms űrlapokból illetve azok tárolására a Common Data Service entitásban.</span><span class="sxs-lookup"><span data-stu-id="a8701-112">The **Power Automate – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="a8701-113">Ez a sablonnal kiterjeszthető, hogy egyéb forgatókönyvekben is használható legyen.</span><span class="sxs-lookup"><span data-stu-id="a8701-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="a8701-114">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="a8701-114">Here are some examples:</span></span>

- <span data-ttu-id="a8701-115">Pályázó értékelések rögzítése.</span><span class="sxs-lookup"><span data-stu-id="a8701-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="a8701-116">Tanfolyami kérdőív eredményeinek rögzítése.</span><span class="sxs-lookup"><span data-stu-id="a8701-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="a8701-117">Interjú kérdések tárházának összeállítása Emberi erőforrások (HR) rendszergazdáknak.</span><span class="sxs-lookup"><span data-stu-id="a8701-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="a8701-118">A jelentkező értékelésének rögzítése az interjúfolyamatból</span><span class="sxs-lookup"><span data-stu-id="a8701-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="a8701-119">A Microsoft Dynamics 365: Attract alkalmazásban űrlapokat használhat a Pályázói portálon, ahol a pályázók kitölthetik adataikat.</span><span class="sxs-lookup"><span data-stu-id="a8701-119">In Microsoft Dynamics 365: Attract, you can use forms in the candidate portal, where candidates fill in details.</span></span> <span data-ttu-id="a8701-120">Azonfelül tevékenységként űrlapokat ágyazhat be egy beosztássablonba.</span><span class="sxs-lookup"><span data-stu-id="a8701-120">You can also embed forms as activities in a job template.</span></span>

<span data-ttu-id="a8701-121">Amikor a jelentkező egy elküld egy űrlapot, a Microsoft Power Automate rögzíti az űrlap benyújtását, beolvassa az adatokat, és tárolja azt a Common Data Service entitásban.</span><span class="sxs-lookup"><span data-stu-id="a8701-121">When a candidate submits a form, Microsoft Power Automate captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="a8701-122">A **Power Automate – Form Connect** sablon és az egyéni entitásstruktúra letöltéséhez nyissa meg a [Power Automate – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) elemet a Microsoft letöltőközpontban.</span><span class="sxs-lookup"><span data-stu-id="a8701-122">To download the **Power Automate – Form Connect** template and Custom Entity Structure, go to [Power Automate – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sharepoint-integration"></a><span data-ttu-id="a8701-123">Power Automate – SharePoint-integráció</span><span class="sxs-lookup"><span data-stu-id="a8701-123">Power Automate – SharePoint Integration</span></span>

<span data-ttu-id="a8701-124">A **Power Automate – SharePoint-integráció** sablon használható adatok beolvasására egy Microsoft SharePoint-listát, a lista mezőértékeinek összehasonlításához bármely Common Data Service entitással, és az összehasonlítás eredményéről egy értesítő e-mail küldéséhez.</span><span class="sxs-lookup"><span data-stu-id="a8701-124">The **Power Automate – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="a8701-125">Előfordulhat, hogy a szervezetnek sürgősen szüksége van egy szakértelemre.</span><span class="sxs-lookup"><span data-stu-id="a8701-125">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="a8701-126">A szakértelmek tárolható SharePoint megoldásban, egy SharePoint listában.</span><span class="sxs-lookup"><span data-stu-id="a8701-126">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="a8701-127">Ha egy jelölt olyan munkára jelentkezik, amelyhez szakértelmek vannak felsorolva, ha jelentős egyezés figyelhető meg a jelentkező szakértelme és a SharePoint megoldásban tárolt szakértelem között, egy értesítő e-mail érkezik.</span><span class="sxs-lookup"><span data-stu-id="a8701-127">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="a8701-128">Ezzel a módszerrel a sürgősen szükséges pozíciókat gyorsabban be lehet tölteni, mivel az értesítések lehetővé teszik a toborzóknak, hogy a szervezetből más jelölteket vegyenek fel.</span><span class="sxs-lookup"><span data-stu-id="a8701-128">This helps fill positions that are urgently required faster, because the notifications help recruiters cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="a8701-129">Ezzel a sablon bővíthető, így minden a SharePoint integrációt érintő forgatókönyvhöz használható.</span><span class="sxs-lookup"><span data-stu-id="a8701-129">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="a8701-130">A **Power Automate – SharePoint integráció** sablon letöltéséhez ugorjon a [Power Automate – SharePoint integráció](https://go.microsoft.com/fwlink/?linkid=2082109) oldalra a Microsoft Letöltőközpontban.</span><span class="sxs-lookup"><span data-stu-id="a8701-130">To download the **Power Automate – SharePoint Integration** template, go to [Power Automate – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>

## <a name="referral-app"></a><span data-ttu-id="a8701-131">Referral alkalmazás</span><span class="sxs-lookup"><span data-stu-id="a8701-131">Referral App</span></span>

<span data-ttu-id="a8701-132">A Referral alkalmazás segítségével jelölteket adhat hozzá egy közös tehetségállományhoz.</span><span class="sxs-lookup"><span data-stu-id="a8701-132">You can use the Referral App to add candidates to a shared talent pool.</span></span> <span data-ttu-id="a8701-133">Az ajánló megadhat **Utónevet**, **Vezetéknevet**, **E-mail-címet** és **LinkedIn URL-t** a jelölt beküldésekor.</span><span class="sxs-lookup"><span data-stu-id="a8701-133">The referrer can enter **Firstname**, **Lastname**, **Email**, and **LinkedIn URL** when submitting a candidate.</span></span> <span data-ttu-id="a8701-134">A pályázó forrásmetaadatai ezt követően lesznek generálva az ajánló adataival</span><span class="sxs-lookup"><span data-stu-id="a8701-134">The candidate source metadata is then populated with the referrer’s information.</span></span>

<span data-ttu-id="a8701-135">Ez az alkalmazás beágyazható az Alkalmazotti önkiszolgáló rendszerbe, vagy használhatja azt hiperhivatkozásként a vállalati portálon, vagy futtathatja különálló alkalmazásként is.</span><span class="sxs-lookup"><span data-stu-id="a8701-135">You can embed this app in Employee self service for submitting referrals, or you can use it as a hyperlink in the corporate portal and run it as a stand-alone app.</span></span>

<span data-ttu-id="a8701-136">A **Referral alkalmazás** letöltéséhez látogasson le a [Dynamics 365 Talent bővíthetőségi megoldás Referral App](https://www.microsoft.com/download/details.aspx?id=58497) oldalra a Microsoft letöltőközpontban.</span><span class="sxs-lookup"><span data-stu-id="a8701-136">To download **Referral App**, go to [Dynamics 365 Talent extensibility solution: Referral App](https://www.microsoft.com/download/details.aspx?id=58497) on the Microsoft Download Center.</span></span> <span data-ttu-id="a8701-137">Ezt az alkalmazást importálhatja, és testreszabhatja további funkciók hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="a8701-137">You can import this app and customize it to add additional functionality.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a8701-138">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a8701-138">Additional resources</span></span>

[<span data-ttu-id="a8701-139">A Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="a8701-139">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[<span data-ttu-id="a8701-140">Alkalmazás bérlők és környezetek közötti áttelepítése</span><span class="sxs-lookup"><span data-stu-id="a8701-140">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
