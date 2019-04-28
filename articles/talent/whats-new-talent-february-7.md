---
title: Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. február 7.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b89fc15130755a80b56f26cf7c61674a26f43e36
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "858928"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-february-7-2019"></a><span data-ttu-id="86f01-103">Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. február 7.)</span><span class="sxs-lookup"><span data-stu-id="86f01-103">What's new or changed in Dynamics 365 for Talent (February 7, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="86f01-104">Ez a témakör a Talent új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="86f01-104">This topic describes features that are either new or changed in Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="86f01-105">Változások az Attract-ben</span><span class="sxs-lookup"><span data-stu-id="86f01-105">Changes in Attract</span></span>

### <a name="interview-scheduling-enhancements"></a><span data-ttu-id="86f01-106">Interjú ütemezésével kapcsolatos fejlesztések</span><span class="sxs-lookup"><span data-stu-id="86f01-106">Interview scheduling enhancements</span></span>
<span data-ttu-id="86f01-107">Javítások történtek a végponttól végpontig tartó interjúütemezési élményben.</span><span class="sxs-lookup"><span data-stu-id="86f01-107">Improvements have been made to the end-to-end interview scheduling experience.</span></span> <span data-ttu-id="86f01-108">Ezután láthatja egy belső jelölt naptárelérhetőségét, és használhatja a belső jelölt naptárát ütemezés ajánlásokhoz.</span><span class="sxs-lookup"><span data-stu-id="86f01-108">You can now see the calendar availability of an internal candidate and use the internal candidate’s calendar for schedule recommendations.</span></span> <span data-ttu-id="86f01-109">További tudnivalókért lásd: [Interjú ütemezése és visszajelzés](interview-scheduling-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="86f01-109">For more information, see [Interview scheduling and feedback](interview-scheduling-feedback.md).</span></span>

### <a name="job-posting-to-linkedin--company-mismatch-issue-fixed"></a><span data-ttu-id="86f01-110">Állás közzététele a LinkedIn-en – vállalati eltérési hiba javítva.</span><span class="sxs-lookup"><span data-stu-id="86f01-110">Job posting to LinkedIn – company mismatch issue fixed</span></span>
<span data-ttu-id="86f01-111">Egy hiba lett javítva, ahol az Attract alkalmazásból a LinkedIn-en közzétett állások rossz vállalatnéven jelentek meg.</span><span class="sxs-lookup"><span data-stu-id="86f01-111">An issue has been fixed where jobs posted to LinkedIn from Attract were appearing under the wrong company name.</span></span> <span data-ttu-id="86f01-112">További tudnivalókért lásd: [Állás létrehozása, jóváhagyása és közzététele az Attract alkalmazásban](creating-jobs-attract.md).</span><span class="sxs-lookup"><span data-stu-id="86f01-112">For more information, see [Create, approve, and post jobs in Attract](creating-jobs-attract.md).</span></span>

### <a name="career-site-url-displayed-in-admin-settings"></a><span data-ttu-id="86f01-113">A karrierwebhely URL-címének megjelenítése a felügyeleti beállításokban</span><span class="sxs-lookup"><span data-stu-id="86f01-113">Career site URL displayed in Admin settings</span></span>
<span data-ttu-id="86f01-114">A karrierwebhely kezdőlapjának URL-címe mostantól megjelenik a **Felügyeleti beállításokban** a **Karrierwebhely kezelése** alatt.</span><span class="sxs-lookup"><span data-stu-id="86f01-114">The career site home page URL is now displayed in **Admin Settings** under **Career Site management**.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="86f01-115">A Core HR módosításai</span><span class="sxs-lookup"><span data-stu-id="86f01-115">Changes in Core HR</span></span>

<span data-ttu-id="86f01-116">**Build 8.1.2134**</span><span class="sxs-lookup"><span data-stu-id="86f01-116">**Build 8.1.2134**</span></span>

### <a name="multiple-compensation-levels-supported-on-jobs"></a><span data-ttu-id="86f01-117">Többféle kompenzációszint támogatott az állásoknál</span><span class="sxs-lookup"><span data-stu-id="86f01-117">Multiple compensation levels supported on jobs</span></span>
<span data-ttu-id="86f01-118">Ez a változtatás lehetővé teszi egynél több kompenzációs szint definiálásár egy munkánál engedélyezve az alkalmazotti fix kompenzációs tartományokat, amelyek eltérőek lehetnek az ugyanazon munkához tartozó tervek között.</span><span class="sxs-lookup"><span data-stu-id="86f01-118">This change allows for more than one compensation level to be defined on a job, enabling employee fixed compensation ranges which may differ between plans when using the same job.</span></span> 

<span data-ttu-id="86f01-119">Példa:</span><span class="sxs-lookup"><span data-stu-id="86f01-119">For example:</span></span>    
<span data-ttu-id="86f01-120">*Feladat* -Ügyfélfelelős *Kapcsolódó kompenzációs szintek:* B1 és B2 - Minden szinthez tartozik egy meghatározott értéktartomány.</span><span class="sxs-lookup"><span data-stu-id="86f01-120">*Job* - Account Manager *Associated compensation levels:* B1 and B2 - Each level has a defined range of values.</span></span> <span data-ttu-id="86f01-121">B1 = Min. 50 000, közép 60 000, Max. 75 000 és B2 = Min. 65 000, közép 74 000, Max. 85 000.</span><span class="sxs-lookup"><span data-stu-id="86f01-121">B1 = Min 50,000, Mid 60,000, Max 75,000 and B2 = Min 65,000, Mid 74,000, Max 85,000.</span></span> <span data-ttu-id="86f01-122">Fix kompenzáció létrehozásakor az alkalmazottakhoz a meghatározott jogosultsági szabályok alapján, az egyes tervek mutathatnak ugyanazon munkára, és a munka különböző szintjeire.</span><span class="sxs-lookup"><span data-stu-id="86f01-122">When creating fixed compensation for employees, based on the eligibility rules defined, each fixed plan can now point to the same job and to different levels on the job.</span></span> <span data-ttu-id="86f01-123">Ez lehetővé teszi tervek meghatározását a különböző régiókhoz/vállalatokhoz , és azt, hogy ugyanazon munkára mutassanak, de más tartományokra a munkák duplikálása nélkül ezen eltérések figyelembevételéhez.</span><span class="sxs-lookup"><span data-stu-id="86f01-123">This allows for plans to be defined in different regions/companies and point to the same job but different ranges without duplicating jobs to account for these differences.</span></span>

### <a name="compensation-level-field-has-been-added-to-the-employee-fixed-compensation-entity"></a><span data-ttu-id="86f01-124">Kompenzációs szint mező hozzá lett adva az Alkalmazott fix kompenzáció entitáshoz</span><span class="sxs-lookup"><span data-stu-id="86f01-124">Compensation level field has been added to the Employee fixed compensation entity</span></span> 
<span data-ttu-id="86f01-125">A frissítéssel az alkalmazotti fix kompenzációs entitás frissítve lett, és tartalmazza a **Kompenzációs szint** mezőt.</span><span class="sxs-lookup"><span data-stu-id="86f01-125">With this update, the employee fixed compensation entity has been updated to include the **Compensation level** field.</span></span> <span data-ttu-id="86f01-126">A kiegészítés megkönnyíti az alkalmazott fix kompenzációs konstrukciók frissítését.</span><span class="sxs-lookup"><span data-stu-id="86f01-126">This addition makes it easier to update employee fixed compensation plans.</span></span> 

### <a name="update-job-family-when-updating-and-creating-new-positions"></a><span data-ttu-id="86f01-127">Munkacsalád frissítése a frissítés és új beosztások létrehozása során</span><span class="sxs-lookup"><span data-stu-id="86f01-127">Update Job family when updating and creating new positions</span></span>
<span data-ttu-id="86f01-128">Amikor frissíti a munkát egy beosztáshoz, a **Munkacsalád** az kiválasztott munka alapján lesz alapértelmezett.</span><span class="sxs-lookup"><span data-stu-id="86f01-128">When changing the job on a position, **Job family** will now default based on the job selected.</span></span>

### <a name="performance-improvements-when-rendering-workspaces"></a><span data-ttu-id="86f01-129">Teljesítménynövelő fejlesztések a munkaterületek megjelenítésekor</span><span class="sxs-lookup"><span data-stu-id="86f01-129">Performance improvements when rendering workspaces</span></span>
<span data-ttu-id="86f01-130">Munkaterületek analitika lapjai csak a lapok elérésekor töltenek be.</span><span class="sxs-lookup"><span data-stu-id="86f01-130">Analytics tabs on workspaces will now load only when accessing those pages.</span></span> <span data-ttu-id="86f01-131">A lap bal felső sarkában egy jelölő jelenik meg az első megjelenítés során.</span><span class="sxs-lookup"><span data-stu-id="86f01-131">An indicator will display during the initial rendering of the page in the upper-left corner of the page.</span></span>
