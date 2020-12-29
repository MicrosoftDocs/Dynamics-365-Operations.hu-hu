---
title: Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. szeptember 17.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 9/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b7bdbbee7468eba100dedc96b5bcee7e03f249e1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461392"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-september-17-2019"></a><span data-ttu-id="d2143-103">Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. szeptember 17.)</span><span class="sxs-lookup"><span data-stu-id="d2143-103">What's new or changed in Dynamics 365 for Talent (September 17, 2019)</span></span>

<span data-ttu-id="d2143-104">Ez a témakör a Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="d2143-104">This topic describes features that are either new or changed in Dynamics 365 for Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="d2143-105">Változások az Attract-ben</span><span class="sxs-lookup"><span data-stu-id="d2143-105">Changes in Attract</span></span>
<span data-ttu-id="d2143-106">A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="d2143-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="d2143-107">Változások az Onboard alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="d2143-107">Changes in Onboard</span></span>
<span data-ttu-id="d2143-108">A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="d2143-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="d2143-109">A Core HR módosításai</span><span class="sxs-lookup"><span data-stu-id="d2143-109">Changes in Core HR</span></span>
<span data-ttu-id="d2143-110">A szakaszban ismertetett módosítások a 8.1.2492-ös buildre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="d2143-110">Changes described in this section apply to build number 8.1.2492.</span></span> <span data-ttu-id="d2143-111">A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="d2143-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="you-can-enable-preview-features-in-sandbox-and-trial-environments"></a><span data-ttu-id="d2143-112">Az előzetes funkciókat tesztkörnyezetekben és próbakörnyezetekben is engedélyezheti</span><span class="sxs-lookup"><span data-stu-id="d2143-112">You can enable preview features in Sandbox and Trial environments</span></span>

<span data-ttu-id="d2143-113">Amikor új Talent-példányt hoz létre, megadhatja, hogy a példány Termelési vagy Védőfal típusú legyen-e.</span><span class="sxs-lookup"><span data-stu-id="d2143-113">When you provision a new instance of Talent, you can specify whether the instance type is Production or Sandbox.</span></span> <span data-ttu-id="d2143-114">A Védőfal típusú példányokkal az új szolgáltatások próbatesztelése végezhető el.</span><span class="sxs-lookup"><span data-stu-id="d2143-114">Instances of the Sandbox type allow for early trial of new features.</span></span> <span data-ttu-id="d2143-115">Ha a meglévő példányokat Védőfal típusúra szeretné frissíteni, kérje az ügyfélszolgálat segítségét.</span><span class="sxs-lookup"><span data-stu-id="d2143-115">If you want one of your existing instances to be updated to the Sandbox instance type, contact Support to initiate the change request.</span></span>

<span data-ttu-id="d2143-116">További információ a módosítások közzétételéről: [A Talent létesítése](./provisioning-talent.md).</span><span class="sxs-lookup"><span data-stu-id="d2143-116">For more information about how changes are published, see [Provision Talent](./provisioning-talent.md).</span></span>

### <a name="human-resources-staff-cant-see-performance-review-details-once-assigned-to-them-by-workflow-370308"></a><span data-ttu-id="d2143-117">Az emberi erőforrás személyzeti nem látja a teljesítményértékelés részleteit, miután a munkafolyamat hozzájuk rendelte (370308)</span><span class="sxs-lookup"><span data-stu-id="d2143-117">Human Resources staff can't see performance review details once assigned to them by workflow (370308)</span></span>

<span data-ttu-id="d2143-118">A heti frissítéssel a HR szakemberek láthatják a teljesítményértékelési részleteket, amelyeket a munkafolyamaton keresztül rendeltek hozzájuk.</span><span class="sxs-lookup"><span data-stu-id="d2143-118">With this week's update, HR professionals will be able to see performance review details that have been assigned to them through workflow processing.</span></span> <span data-ttu-id="d2143-119">Az értékelések megtekintéséhez navigáljon az **Alkalmazotti önkiszolgáló rendszer > Hozzám rendelt munkaelemek** pontra.</span><span class="sxs-lookup"><span data-stu-id="d2143-119">To view reviews, navigate to **Employee self-service > Work items assigned to me**.</span></span>

### <a name="job-family-field-missing-in-the-manage-changes-page-for-job-details-346031"></a><span data-ttu-id="d2143-120">Hiányzik a Feladatcsalád mező a Módosítások kezelése oldalról a feladat részleteinél (346031)</span><span class="sxs-lookup"><span data-stu-id="d2143-120">Job family field missing in the Manage changes page for job details (346031)</span></span>

<span data-ttu-id="d2143-121">Ebben a kiadásban a feladatcsalád mező hozzáadásra került a feladatrészletek **Módosítások kezelése** oldalához.</span><span class="sxs-lookup"><span data-stu-id="d2143-121">In this release, the job family field has been added to the **Manage changes** page for job details.</span></span>

## <a name="in-preview"></a><span data-ttu-id="d2143-122">Előnézetben</span><span class="sxs-lookup"><span data-stu-id="d2143-122">In preview</span></span>

### <a name="streamlined-employee-entry-and-navigation"></a><span data-ttu-id="d2143-123">Korszerű alkalmazotti belépés és navigálás</span><span class="sxs-lookup"><span data-stu-id="d2143-123">Streamlined employee entry and navigation</span></span>

<span data-ttu-id="d2143-124">Ez a funkció jelenleg a sandbox környezetekben érhető el.</span><span class="sxs-lookup"><span data-stu-id="d2143-124">This functionality is now available in sandbox environments.</span></span> <span data-ttu-id="d2143-125">A funkció bekapcsolásához navigáljon a **Rendszer-adminisztráció > Hivatkozások > Beállítás > Rendszerparaméterek > előnézeti funkciók** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="d2143-125">To turn this feature on, navigate to **System administration > Links > Setup > System parameters > Preview features**.</span></span> <span data-ttu-id="d2143-126">Válassza a **Továbbfejlesztett dolgozói képernyő és navigáció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d2143-126">Select **Enhanced worker form and navigation**.</span></span> <span data-ttu-id="d2143-127">Ez minden felhasználó számára engedélyezi a változtatásokat.</span><span class="sxs-lookup"><span data-stu-id="d2143-127">This will enable these changes for all users.</span></span> <span data-ttu-id="d2143-128">Ezt a beállítást bármikor ki lehet kapcsolni.</span><span class="sxs-lookup"><span data-stu-id="d2143-128">You can turn this option off at any time.</span></span>

<span data-ttu-id="d2143-129">További tájékoztatás: [Korszerű alkalmazotti belépés és navigálás](./streamlined-employee-entry.md).</span><span class="sxs-lookup"><span data-stu-id="d2143-129">For more information, see [Streamlined employee entry and navigation](./streamlined-employee-entry.md).</span></span> <span data-ttu-id="d2143-130">Ha meg szeretné tekinteni a változásokat, tekintse meg a következő videót: [Dynamics 365 for Talent 2019. második kiadási hullám áttekintése](https://aka.ms/ROGT19RW2ROV).</span><span class="sxs-lookup"><span data-stu-id="d2143-130">To see the changes, watch the video [Dynamics 365 for Talent 2019 release wave 2 overview](https://aka.ms/ROGT19RW2ROV).</span></span>
