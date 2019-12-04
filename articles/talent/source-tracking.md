---
title: Jelöltek forrásainak nyomon követése az Attract szolgáltatásban
description: Ez a témakör a jelölt profilok jelentkezések forráskövetésével kapcsolatban tartalmaz tájékoztatást.
author: hachandr
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 8860f508eebc377042c4e101eeb08a14a737ba0c
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832658"
---
# <a name="track-candidate-sources-in-attract"></a><span data-ttu-id="bd6fa-103">Jelöltek forrásainak nyomon követése az Attract szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="bd6fa-103">Track candidate sources in Attract</span></span>

[!include [banner](includes/banner.md)]

> [!NOTE] 
> <span data-ttu-id="bd6fa-104">A témakörben megjegyzett funkciók rendelkezésére állnak egy előzetes kiadás részeként.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-104">Functionality noted in this topic is available as part of a preview review release.</span></span> <span data-ttu-id="bd6fa-105">A tartalom és a funkciók megváltozhatnak.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-105">The content and the functionality are subject to change.</span></span> <span data-ttu-id="bd6fa-106">Ez a funkció használatához kérje meg a rendszergazdát az engedélyezésére az **Adminisztratív beállításokban** az Attract megoldásban.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-106">To use this feature, ask an administrator to enable it using the **Admin settings** in Attract.</span></span> <span data-ttu-id="bd6fa-107">Egy későbbi verzió forráskövetési jelentéseket is kínál majd.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-107">A future release will provide source tracking reports.</span></span> <span data-ttu-id="bd6fa-108">További tudnivalókért lásd: [Talent – előnézeti funkciók elérése](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="bd6fa-108">For more information, see [Access preview features in Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

<span data-ttu-id="bd6fa-109">Amikor a pályázók egy állásra jelentkeznek, az Attract automatikusan nyomon követi a pályázatok forrását így értékes információkat nyújt a toborzás célzásához.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-109">When candidates apply for a job, Attract automatically tracks the source of their applications, providing you with valuable information to help you target your recruiting efforts.</span></span> <span data-ttu-id="bd6fa-110">A toborzók és felvételi vezető kiválaszthatják egy jelentkezés forrását amikor manuálisan hozzáadnak egy jelentkezőt egy álláshoz vagy tehetségállományhoz.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-110">Recruiters and hiring managers can also select an application source while manually adding a candidate to a job or talent pool.</span></span>

<span data-ttu-id="bd6fa-111">A pályázat forrását a pályázati tevékenység részleteiben tekintheti meg a **Tevékenység** lapon, valamint a pályázati előzmények is elérhetők a **Profil** alatt a tehetségállományokban.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-111">You can view the application source in the application activity details under the **Activity** tab, as well as in the application history available under **Profile** in talent pools.</span></span> <span data-ttu-id="bd6fa-112">A jelentkező profiljának forrását a jelentkező adatainál találja a **Profil** lapon jelentkezésekben és a tehetségállományokban is.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-112">You can find a candidate's profile source in the candidate details under the **Profile** tab in both applications and talent pools.</span></span>

> [!NOTE] 
> <span data-ttu-id="bd6fa-113">A folyamatsablonokat az [Átfogó felvételi bővítményben](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring) találja.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-113">You can find process templates in the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>

## <a name="pre-configured-sources"></a><span data-ttu-id="bd6fa-114">Előre konfigurált források</span><span class="sxs-lookup"><span data-stu-id="bd6fa-114">Pre-configured sources</span></span>

<span data-ttu-id="bd6fa-115">Az alapértelmezett forráslista gyakori pályázatforrásokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-115">The default source list contains common application sources.</span></span> <span data-ttu-id="bd6fa-116">Bizonyos forrástípusok pl **Hirdetőfelület** és **Közösségi hálózat** további adatokat tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-116">Some source types, like **Job board** and **Social Network**, have additional source details.</span></span> <span data-ttu-id="bd6fa-117">Péládul a **Közösségi hálózat** tartalmazza Facebook és Twitter oldalakat.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-117">For example, **Social Network** includes Facebook and Twitter.</span></span> <span data-ttu-id="bd6fa-118">Az **Ajánlás** forrástípus lehetővé teszi egy belső alkalmazott megadását ajánlóként.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-118">The **Referral** source type allows you to specify an internal employee as the referrer.</span></span> <span data-ttu-id="bd6fa-119">Az alapértelmezett forráslista a következő előre beállított forrásokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="bd6fa-119">The default source list includes the following pre-configured sources:</span></span>

-   <span data-ttu-id="bd6fa-120">Attract karrierwebhely</span><span class="sxs-lookup"><span data-stu-id="bd6fa-120">Attract career site</span></span>

-   <span data-ttu-id="bd6fa-121">Iroda</span><span class="sxs-lookup"><span data-stu-id="bd6fa-121">Agency</span></span>

-   <span data-ttu-id="bd6fa-122">Állásbörze</span><span class="sxs-lookup"><span data-stu-id="bd6fa-122">Career Fair</span></span>

-   <span data-ttu-id="bd6fa-123">Vállalati marketing</span><span class="sxs-lookup"><span data-stu-id="bd6fa-123">Company Marketing</span></span>

-   <span data-ttu-id="bd6fa-124">Konferenciák és kereskedelmi bemutatók</span><span class="sxs-lookup"><span data-stu-id="bd6fa-124">Conferences & Trade shows</span></span>

-   <span data-ttu-id="bd6fa-125">Szakmai egyesület</span><span class="sxs-lookup"><span data-stu-id="bd6fa-125">Professional Association</span></span>

-   <span data-ttu-id="bd6fa-126">Hirdetőfelület</span><span class="sxs-lookup"><span data-stu-id="bd6fa-126">Job board</span></span>

    -   <span data-ttu-id="bd6fa-127">Indeed</span><span class="sxs-lookup"><span data-stu-id="bd6fa-127">Indeed</span></span>

    -   <span data-ttu-id="bd6fa-128">Seek</span><span class="sxs-lookup"><span data-stu-id="bd6fa-128">Seek</span></span>

    -   <span data-ttu-id="bd6fa-129">CareerBuilder</span><span class="sxs-lookup"><span data-stu-id="bd6fa-129">CareerBuilder</span></span>

    -   <span data-ttu-id="bd6fa-130">Google Jobs</span><span class="sxs-lookup"><span data-stu-id="bd6fa-130">Google Jobs</span></span>

    -   <span data-ttu-id="bd6fa-131">Xing</span><span class="sxs-lookup"><span data-stu-id="bd6fa-131">Xing</span></span>

    -   <span data-ttu-id="bd6fa-132">Glassdoor</span><span class="sxs-lookup"><span data-stu-id="bd6fa-132">Glassdoor</span></span>

    -   <span data-ttu-id="bd6fa-133">Monster Jobs</span><span class="sxs-lookup"><span data-stu-id="bd6fa-133">Monster Jobs</span></span>

-   <span data-ttu-id="bd6fa-134">Magazinok és kiadványok</span><span class="sxs-lookup"><span data-stu-id="bd6fa-134">Magazines & Publications</span></span>

-   <span data-ttu-id="bd6fa-135">Közösségi hálózat</span><span class="sxs-lookup"><span data-stu-id="bd6fa-135">Social Network</span></span>

    -   <span data-ttu-id="bd6fa-136">Facebook</span><span class="sxs-lookup"><span data-stu-id="bd6fa-136">Facebook</span></span>

    -   <span data-ttu-id="bd6fa-137">Twitter</span><span class="sxs-lookup"><span data-stu-id="bd6fa-137">Twitter</span></span>

-   <span data-ttu-id="bd6fa-138">Egyetem toborzás</span><span class="sxs-lookup"><span data-stu-id="bd6fa-138">University Recruiting</span></span>

-   <span data-ttu-id="bd6fa-139">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="bd6fa-139">LinkedIn</span></span>

-   <span data-ttu-id="bd6fa-140">Apróhirdetések</span><span class="sxs-lookup"><span data-stu-id="bd6fa-140">Classifieds</span></span>

-   <span data-ttu-id="bd6fa-141">Javaslat</span><span class="sxs-lookup"><span data-stu-id="bd6fa-141">Referral</span></span>

-   <span data-ttu-id="bd6fa-142">Toborzó által hozzáadva</span><span class="sxs-lookup"><span data-stu-id="bd6fa-142">Added by Recruiter</span></span>

-   <span data-ttu-id="bd6fa-143">Egyéb</span><span class="sxs-lookup"><span data-stu-id="bd6fa-143">Other</span></span>

## <a name="customize-the-source-list"></a><span data-ttu-id="bd6fa-144">Forráslista testreszabása</span><span class="sxs-lookup"><span data-stu-id="bd6fa-144">Customize the source list</span></span> 

<span data-ttu-id="bd6fa-145">Az további jelentkezési források is szerepeltethetők a forráslistában.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-145">You can extend the source list to include additional application sources.</span></span> <span data-ttu-id="bd6fa-146">Ez a lista testreszabásához kövesse [Beállításkészletek kiterjesztése az Attract alkalmazásban](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract) utasításait.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-146">To customize this list, follow the instructions in [Extending Option Sets in Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract).</span></span> <span data-ttu-id="bd6fa-147">Szerkessze a **TalentSource** entitást további források felvételéhez.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-147">Edit the **TalentSource** entity to include additional sources.</span></span> 

<span data-ttu-id="bd6fa-148">A felhasználói felület negatív befolyásolása elkerülésére nem szerkessze vagy törölje a **TalentCategory** enumerációs értékeket (nem nevek) a következőkhöz:</span><span class="sxs-lookup"><span data-stu-id="bd6fa-148">To avoid negatively impacting the user interface (UI), don't edit or delete the **TalentCategory** enum values (not names) for the following:</span></span>

- <span data-ttu-id="bd6fa-149">**Javaslat**</span><span class="sxs-lookup"><span data-stu-id="bd6fa-149">**Referral**</span></span>
- <span data-ttu-id="bd6fa-150">**LinkedIn**</span><span class="sxs-lookup"><span data-stu-id="bd6fa-150">**LinkedIn**</span></span>
- <span data-ttu-id="bd6fa-151">**Egyéb**</span><span class="sxs-lookup"><span data-stu-id="bd6fa-151">**Other**</span></span>

<span data-ttu-id="bd6fa-152">Ehelyett bővítheti a **TalentSource** enumeárciós értékeket más típusú adatforrások hozzáadásával.</span><span class="sxs-lookup"><span data-stu-id="bd6fa-152">Instead, you can extend the **TalentSource** enum to add other types of sources.</span></span>
