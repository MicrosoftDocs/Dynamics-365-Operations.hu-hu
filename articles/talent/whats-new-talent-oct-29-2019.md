---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. október 29.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 10/29/2019
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
ms.search.validFrom: 2019-10-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 09d53c82b4244f20d0d7f301691b01263258a32f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529684"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-29-2019"></a><span data-ttu-id="69f3e-103">Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. október 29.)</span><span class="sxs-lookup"><span data-stu-id="69f3e-103">What's new or changed in Dynamics 365 Talent (October 29, 2019)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="69f3e-104">Ez a témakör a Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="69f3e-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="69f3e-105">Változások az Attract-ben</span><span class="sxs-lookup"><span data-stu-id="69f3e-105">Changes in Attract</span></span>

<span data-ttu-id="69f3e-106">A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="69f3e-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="69f3e-107">Változások az Onboard alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="69f3e-107">Changes in Onboard</span></span>

<span data-ttu-id="69f3e-108">A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="69f3e-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="69f3e-109">A Core HR módosításai</span><span class="sxs-lookup"><span data-stu-id="69f3e-109">Changes in Core HR</span></span>

<span data-ttu-id="69f3e-110">A szakaszban ismertetett módosítások a 8.1.2586-ös buildre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="69f3e-110">Changes described in this section apply to build number 8.1.2586.</span></span> <span data-ttu-id="69f3e-111">A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="69f3e-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="delete-parties-with-no-roles-should-be-on-by-default-371233"></a><span data-ttu-id="69f3e-112">A szerepkörökkel nem rendelkező felek törlésének alapértelmezés szerint bekapcsolt állapotban kell lennie (371233)</span><span class="sxs-lookup"><span data-stu-id="69f3e-112">Delete parties with no roles should be on by default (371233)</span></span>

<span data-ttu-id="69f3e-113">Ha egy új környezetet hoz létre a Talent programban, akkor a **Felek törlése, ha nem találhatók szerepkörök** alapértelmezett módon be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="69f3e-113">When you provision a new environment in Talent, **Delete parties if no roles exist** is turned on by default.</span></span> <span data-ttu-id="69f3e-114">Dolgozó törlésekor a dolgozóhoz társított fél nem kerül eltávolításra, csak akkor, ha ez a beállítás bekapcsolt állapotban van.</span><span class="sxs-lookup"><span data-stu-id="69f3e-114">When you delete a worker, the party associated with the worker is not removed unless this setting is on.</span></span> <span data-ttu-id="69f3e-115">Ez a módosítás korlátozza a globális címjegyzék ismétlődő rekordjait, amikor a dolgozókat importálni, módosítani vagy újraimportálni szeretné.</span><span class="sxs-lookup"><span data-stu-id="69f3e-115">This change limits duplicate records in the global address book when you need to import, change, or reimport workers.</span></span>

### <a name="draft-and-cancelled-leave-requests-should-be-allowed-to-be-deleted-in-common-data-service-376999"></a><span data-ttu-id="69f3e-116">A Common Data Service szolgáltatásban a tervezet állapotú és a visszavont szabadságkérelmeket tudni kell törölni (376999)</span><span class="sxs-lookup"><span data-stu-id="69f3e-116">Draft and cancelled leave requests should be allowed to be deleted in Common Data Service (376999)</span></span>

<span data-ttu-id="69f3e-117">Ezzel a módosítással most már kitörölheti a **Tervezet** vagy **Visszavont** állapotú szabadságkérelmeket a Common Data Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="69f3e-117">With this change, you can now delete leave requests with a status of **Draft** or **Cancelled** in Common Data Service.</span></span>

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a><span data-ttu-id="69f3e-118">Az egyéni mezőkben szereplő további listaelemek nem jelennek meg a Common Data Service szolgáltatásban az egyéni mezők képernyőjén az alkalmazás gombra történő kattintás után (379599)</span><span class="sxs-lookup"><span data-stu-id="69f3e-118">Additional list values in custom fields aren't reflected in Common Data Service after clicking Apply on the Custom fields form (379599)</span></span>

<span data-ttu-id="69f3e-119">Amikor új listaértékeket ad hozzá olyan meglévő egyéni mezőhöz, amelyet már szinkronizált a Common Data Service szolgáltatással, ezek elérhetővé válnak a a Common Data Service szolgáltatásban, miután elvégzi a módostásokat az **Egyéni mezők** űrlapon.</span><span class="sxs-lookup"><span data-stu-id="69f3e-119">When you add new list values to an existing custom field that has already synchronized with Common Data Service, they're now available in Common Data Serivce after you apply your changes in the **Custom fields** form.</span></span>

### <a name="apply-onboarding-checklists-across-legal-entities-when-more-than-one-employment-exists-371270"></a><span data-ttu-id="69f3e-120">Toborzási ellenőrzőlisták alkalmazása több jogi személyen, amikor több foglalkoztatás található (371270)</span><span class="sxs-lookup"><span data-stu-id="69f3e-120">Apply onboarding checklists across legal entities when more than one employment exists (371270)</span></span>

<span data-ttu-id="69f3e-121">Az e heti kiadásban ellenőrzőlistákat alkalmazhat olyan alkalmazottakra, akik egynél több foglalkoztatással rendelkeznek a **Dolgozói űrlap > Ellenőrzőlista** pontban.</span><span class="sxs-lookup"><span data-stu-id="69f3e-121">In this week's release, you can apply checklists to employees with more than one employment in **Worker form > Checklists**.</span></span>

### <a name="benefits-open-enrollment-preview-feature-has-been-removed"></a><span data-ttu-id="69f3e-122">A juttatásokra való nyitott jelentkezés előzetes funkciót eltávolították</span><span class="sxs-lookup"><span data-stu-id="69f3e-122">Benefits open enrollment preview feature has been removed</span></span>

<span data-ttu-id="69f3e-123">A [Stratégiai befektetések a Core HR-ben a működési kiválóság elősegítése érdekében](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence) bejelentése blogbejegyzés mellett a Microsoft eltávolította a juttatásokra való nyitott jelentkezés funkciót a nyilvános előzetesből.</span><span class="sxs-lookup"><span data-stu-id="69f3e-123">In conjunction with our announcement in the [Strategic investments in core HR drive operational excellence](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence) blog post, Microsoft has removed the benefits open enrollment feature from public preview.</span></span> <span data-ttu-id="69f3e-124">A jövőben új funkciók lesznek kiadva.</span><span class="sxs-lookup"><span data-stu-id="69f3e-124">New functionality will be released in the future.</span></span> <span data-ttu-id="69f3e-125">A juttatásokra való nyitott jelentkezés funkciójának működési használatát nem támogatja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="69f3e-125">Production use of the benefits open enrollment feature isn't be supported.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="69f3e-126">Hamarosan</span><span class="sxs-lookup"><span data-stu-id="69f3e-126">Coming soon</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="69f3e-127">Teljesítményértékelések nyomtatása</span><span class="sxs-lookup"><span data-stu-id="69f3e-127">Print performance reviews</span></span>

<span data-ttu-id="69f3e-128">Lásd [Teljesítményértékelések nyomtatása](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) a Dynamics 365: 2019 release wave 2 tervben.</span><span class="sxs-lookup"><span data-stu-id="69f3e-128">See [Print performance reviews](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) in the Dynamics 365: 2019 release wave 2 plan.</span></span>

### <a name="feature-management-workspace"></a><span data-ttu-id="69f3e-129">A Funkciókezelés munkaterület</span><span class="sxs-lookup"><span data-stu-id="69f3e-129">Feature management workspace</span></span>

<span data-ttu-id="69f3e-130">Minden kiadásban új szolgáltatások és frissítések jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="69f3e-130">Features are added and updated in every release.</span></span> <span data-ttu-id="69f3e-131">A funkció-kezelési élmény olyan munkaterületet tartalmaz, amelyen megtekintheti az egyes kiadásokban elérhetővé tett szolgáltatások listáját.</span><span class="sxs-lookup"><span data-stu-id="69f3e-131">The feature management experience provides a workspace where you can view a list of features that have been delivered in each release.</span></span> <span data-ttu-id="69f3e-132">Alapértelmezés szerint az új szolgáltatások ki vannak kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="69f3e-132">By default, new features are turned off.</span></span> <span data-ttu-id="69f3e-133">A munkaterületen bekapcsolhatja a szolgáltatásokat, és megtekintheti a rájuk vonatkozó dokumentációt.</span><span class="sxs-lookup"><span data-stu-id="69f3e-133">You can use the workspace to turn them on and view the documentation for them.</span></span>

<span data-ttu-id="69f3e-134">További információ a szolgáltatások kezelésével kapcsolatos változásokról: [Funkciókezelés áttekintése](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="69f3e-134">To learn more about the changes coming with feature management, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>
