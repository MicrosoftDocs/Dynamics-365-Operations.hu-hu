---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. november 5.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 11/05/2019
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
ms.search.validFrom: 2019-11-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c4068cf81782d2f9559179b91da31e049c006059
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527120"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-5-2019"></a><span data-ttu-id="efa77-103">Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. november 5.)</span><span class="sxs-lookup"><span data-stu-id="efa77-103">What's new or changed in Dynamics 365 Talent (November 5, 2019)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="efa77-104">Ez a témakör a Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="efa77-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="efa77-105">Változások az Attract-ben</span><span class="sxs-lookup"><span data-stu-id="efa77-105">Changes in Attract</span></span>

<span data-ttu-id="efa77-106">A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="efa77-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="efa77-107">Változások az Onboard alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="efa77-107">Changes in Onboard</span></span>

<span data-ttu-id="efa77-108">A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="efa77-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="efa77-109">A Core HR módosításai</span><span class="sxs-lookup"><span data-stu-id="efa77-109">Changes in Core HR</span></span>

<span data-ttu-id="efa77-110">A szakaszban ismertetett módosítások a 8.1.2598-ös buildre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="efa77-110">Changes described in this section apply to build number 8.1.2598.</span></span> <span data-ttu-id="efa77-111">A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="efa77-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="copy-a-core-hr-instance"></a><span data-ttu-id="efa77-112">Core HR példány másolása</span><span class="sxs-lookup"><span data-stu-id="efa77-112">Copy a Core HR instance</span></span>

<span data-ttu-id="efa77-113">A heti kiadásban az Microsoft Dynamics Lifecycle Services (LCS) szolgáltatással átmásolhat egy Microsoft Dynamics 365 Talent: Core HR adatbázist egy tesztkörnyezetbe.</span><span class="sxs-lookup"><span data-stu-id="efa77-113">In this week's release, you can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Talent: Core HR database to a sandbox environment.</span></span> <span data-ttu-id="efa77-114">Ha van másik tesztkörnyezete, akkor abból a környezetből is másolható az adatbázis a célként kiválasztott tesztkörnyezetbe.</span><span class="sxs-lookup"><span data-stu-id="efa77-114">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span> <span data-ttu-id="efa77-115">További tájékoztatás:</span><span class="sxs-lookup"><span data-stu-id="efa77-115">For more information, see:</span></span>

- <span data-ttu-id="efa77-116">[Tágabb környezetkezelés](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) a Dynamics 365: 2019 Release Wave 2 tervben</span><span class="sxs-lookup"><span data-stu-id="efa77-116">[Broader environment management](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) in the Dynamics 365: 2019 release wave 2 plan</span></span>

- <span data-ttu-id="efa77-117">[Core HR-példány másolása](hr-copy-instance.md) a Talent dokumentációba</span><span class="sxs-lookup"><span data-stu-id="efa77-117">[Copy a Core HR instance](hr-copy-instance.md) in Talent documentation</span></span>

### <a name="common-data-service-integration-batch-jobs-arent-created-when-common-data-service-integration-is-enabled-388030"></a><span data-ttu-id="efa77-118">Nem jönnek létre Common Data Service-integrációs kötegelt feladatok, amikor a Common Data Service-integráció engedélyezve van (388030)</span><span class="sxs-lookup"><span data-stu-id="efa77-118">Common Data Service integration batch jobs aren't created when Common Data Service integration is enabled (388030)</span></span>

<span data-ttu-id="efa77-119">A módosítással kötegelt feladatok jönnek létre a Common Data Service szolgáltatáshoz, amikor engedélyezve van az integráció.</span><span class="sxs-lookup"><span data-stu-id="efa77-119">This change will create batch jobs for Common Data Service integration when it's enabled.</span></span>

### <a name="the-hcmpersonimageentity-doesnt-resize-the-person-image-when-uploaded-369469"></a><span data-ttu-id="efa77-120">A HcmPersonImageEntity nem méretezi át a személy képét feltöltéskor (369469)</span><span class="sxs-lookup"><span data-stu-id="efa77-120">The HcmPersonImageEntity doesn't resize the person image when uploaded (369469)</span></span>

<span data-ttu-id="efa77-121">Ez a heti kiadás megváltoztatja a képek átméretezését a jobb teljesítmény érdekében, amikor az adatkezelésen keresztül importálják.</span><span class="sxs-lookup"><span data-stu-id="efa77-121">This week's release changes how images are resized for better performance when imported through data management.</span></span>

### <a name="a-positions-available-for-assignment-date-can-be-earlier-than-the-activation-date-340103"></a><span data-ttu-id="efa77-122">A beosztás Elérhető hozzárendelésre dátuma az Aktiválási dátumnál korábbi lehet (340103)</span><span class="sxs-lookup"><span data-stu-id="efa77-122">A position's Available for assignment date can be earlier than the Activation date (340103)</span></span>

<span data-ttu-id="efa77-123">Ezzel a módosítással megjelenik egy figyelmeztetés, ha olyan **Elérhetőség dátuma a hozzárendeléshez** dátumot választ ki, amely korábbi, mint a beosztás **Aktiválási dátuma**.</span><span class="sxs-lookup"><span data-stu-id="efa77-123">With this change, a warning will appear if you select an **Available for assignment date** that's earlier than the position's **Activation date**.</span></span>

### <a name="cant-create-a-compensation-change-request-in-employee-self-service-for-step-based-plans-376872"></a><span data-ttu-id="efa77-124">Nem hozható létre kompenzációs módosítási kérelem az Alkalmazotti önkiszolgáló szolgáltatásban a lépésalapú tervekhez (376872)</span><span class="sxs-lookup"><span data-stu-id="efa77-124">Can't create a compensation change request in employee self-service for step-based plans (376872)</span></span>

<span data-ttu-id="efa77-125">Ez a kiadás javítja azt a hibát, amely a kompenzáció módosítására vonatkozó kérelem alkalmazotti önkiszolgáló rendszeren keresztül való elküldése során merül fel lépésalapú tervek esetén.</span><span class="sxs-lookup"><span data-stu-id="efa77-125">This release corrects an issue when requesting compensation changes through employee self-service for step-based plans.</span></span> 

### <a name="reason-code-doesnt-sync-to-common-data-service-if-the-description-is-longer-than-30-characters-core-hr-allows-60-352682"></a><span data-ttu-id="efa77-126">Az okkód nem szinkronizálódik a Common Data Service szolgáltatással, ha a leírás 30 karakternél hosszabb, a Core HR megengedett értéke 60 (352682)</span><span class="sxs-lookup"><span data-stu-id="efa77-126">Reason code doesn't sync to Common Data Service if the description is longer than 30 characters, Core HR allows 60 (352682)</span></span>

<span data-ttu-id="efa77-127">ezzel a módosítással a 30 karakternél hosszabb okkódok frissítése is megtörténik a Common Data Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="efa77-127">with this change, reason codes with more than 30 characters will be updated in Common Data Service.</span></span> <span data-ttu-id="efa77-128">A Common Data Service szolgáltatásban végrehajtott változtatások a Talent szolgáltatásban is megjelennek.</span><span class="sxs-lookup"><span data-stu-id="efa77-128">Changes made in Common Data Service will also be reflected back in Talent.</span></span>

### <a name="address-integration-from-talent-to-finance-and-operations-351961"></a><span data-ttu-id="efa77-129">Címintegráció a Talent és a Finance and Operations között (351961)</span><span class="sxs-lookup"><span data-stu-id="efa77-129">Address integration from Talent to Finance and Operations (351961)</span></span>

<span data-ttu-id="efa77-130">Ez a kiadás javít egy olyan problémát, amelynél a Talentben frissített címek nem frissültek a Finance and Operations szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="efa77-130">This release fixes an issue where addresses updated in Talent weren't updating in Finance and Operations.</span></span> <span data-ttu-id="efa77-131">A rendszer most már frissíti a címblokkok módosításait.</span><span class="sxs-lookup"><span data-stu-id="efa77-131">Changes to address blocks will now update.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="efa77-132">Hamarosan</span><span class="sxs-lookup"><span data-stu-id="efa77-132">Coming soon</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="efa77-133">Teljesítményértékelések nyomtatása</span><span class="sxs-lookup"><span data-stu-id="efa77-133">Print performance reviews</span></span>

<span data-ttu-id="efa77-134">Lásd [Teljesítményértékelések nyomtatása](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) a Dynamics 365: 2019 release wave 2 tervben.</span><span class="sxs-lookup"><span data-stu-id="efa77-134">See [Print performance reviews](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) in the Dynamics 365: 2019 release wave 2 plan.</span></span>

### <a name="feature-management-workspace"></a><span data-ttu-id="efa77-135">A Funkciókezelés munkaterület</span><span class="sxs-lookup"><span data-stu-id="efa77-135">Feature management workspace</span></span>

<span data-ttu-id="efa77-136">Minden kiadásban új szolgáltatások és frissítések jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="efa77-136">Features are added and updated in every release.</span></span> <span data-ttu-id="efa77-137">A funkció-kezelési élmény olyan munkaterületet tartalmaz, amelyen megtekintheti az egyes kiadásokban elérhetővé tett szolgáltatások listáját.</span><span class="sxs-lookup"><span data-stu-id="efa77-137">The feature management experience provides a workspace where you can view a list of features that have been delivered in each release.</span></span> <span data-ttu-id="efa77-138">Alapértelmezés szerint az új szolgáltatások ki vannak kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="efa77-138">By default, new features are turned off.</span></span> <span data-ttu-id="efa77-139">A munkaterületen bekapcsolhatja a szolgáltatásokat, és megtekintheti a rájuk vonatkozó dokumentációt.</span><span class="sxs-lookup"><span data-stu-id="efa77-139">You can use the workspace to turn them on and view the documentation for them.</span></span>

<span data-ttu-id="efa77-140">További információ a szolgáltatások kezelésével kapcsolatos változásokról: [Funkciókezelés áttekintése](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="efa77-140">To learn more about the changes coming with feature management, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>
