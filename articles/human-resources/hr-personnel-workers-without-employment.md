---
title: Foglalkoztatás nélküli dolgozók
description: A jövőbeli, aktív vagy múltbeli Munkanélküli dolgozók a szervezetnél megjelennek a Munkanélküli dolgozók űrlapon.
author: andreabichsel
ms.date: 04/06/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f6fbada6feb55b8627b1aa1ddfe367177edb7a0a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051713"
---
# <a name="workers-without-employment"></a><span data-ttu-id="61a4e-103">Foglalkoztatás nélküli dolgozók</span><span class="sxs-lookup"><span data-stu-id="61a4e-103">Workers without employment</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="61a4e-104">A jövőbeli, aktív vagy múltbeli Munkanélküli dolgozók a szervezetnél megjelennek a **Munkanélküli dolgozók** űrlapon.</span><span class="sxs-lookup"><span data-stu-id="61a4e-104">Workers with no future, active, or historical employment with your organization appear in the **Workers without employment** form.</span></span> <span data-ttu-id="61a4e-105">Az ilyen állapotú dolgozók akkor is megjelenhetnek, ha alkalmazásrekord nélküli dolgozókat importál, vagy ha a dolgozók munkaviszonyát a **Dolgozók > Foglalkoztatási előzmények** segítségével törli.</span><span class="sxs-lookup"><span data-stu-id="61a4e-105">Workers with this status can appear when you import workers without an employment record, or when you delete a worker's employment via **Workers > Employment history**.</span></span>

<span data-ttu-id="61a4e-106">Alapértelmezés szerint a **Munkanélküli dolgozók** űrlap a következő szerepkörök számára érhető el:</span><span class="sxs-lookup"><span data-stu-id="61a4e-106">By default, the **Workers without employment** form is available to the following roles:</span></span>

- <span data-ttu-id="61a4e-107">Emberi erőforrás asszisztens</span><span class="sxs-lookup"><span data-stu-id="61a4e-107">Human Resources Assistant</span></span>
- <span data-ttu-id="61a4e-108">Emberi erőforrás vezető</span><span class="sxs-lookup"><span data-stu-id="61a4e-108">Human Resources Manager</span></span>
- <span data-ttu-id="61a4e-109">Toborzó</span><span class="sxs-lookup"><span data-stu-id="61a4e-109">Recruiter</span></span>
- <span data-ttu-id="61a4e-110">Kompenzáció és juttatások vezető</span><span class="sxs-lookup"><span data-stu-id="61a4e-110">Comp and Benefits Manager</span></span>
- <span data-ttu-id="61a4e-111">Bérszámfejtő</span><span class="sxs-lookup"><span data-stu-id="61a4e-111">Payroll Administrator</span></span>
- <span data-ttu-id="61a4e-112">Bérszámfejtési vezető</span><span class="sxs-lookup"><span data-stu-id="61a4e-112">Payroll Manager</span></span>
- <span data-ttu-id="61a4e-113">Képzési vezető</span><span class="sxs-lookup"><span data-stu-id="61a4e-113">Training Manager</span></span>

<span data-ttu-id="61a4e-114">A **Munkanélküli dolgozók** listájáról törölheti a felsorolt személyeket.</span><span class="sxs-lookup"><span data-stu-id="61a4e-114">In the **Workers without employment** list, you can delete the individuals listed.</span></span> <span data-ttu-id="61a4e-115">Alapértelmezés szerint ez a jogosultság az Emberi erőforrások asszisztens szerepköre.</span><span class="sxs-lookup"><span data-stu-id="61a4e-115">By default, this privilege is given to the Human Resources Assistant role.</span></span> <span data-ttu-id="61a4e-116">Ezt a jogosultságot a következő lépésekkel más szerepköröknek adhatja át:</span><span class="sxs-lookup"><span data-stu-id="61a4e-116">You can give this privilege to other roles with the following steps:</span></span>

1. <span data-ttu-id="61a4e-117">Válassza a **Rendszerfelügyelet** elemet, majd a **Biztonság konfigurálása** lapot.</span><span class="sxs-lookup"><span data-stu-id="61a4e-117">Select **System administration**, and then select **Security configuration**.</span></span>

2. <span data-ttu-id="61a4e-118">A **Jogosultságok** lapon szűrje a **Jogosultságok** listáját a **Dolgozók karbantartása** céljából.</span><span class="sxs-lookup"><span data-stu-id="61a4e-118">In the **Privileges** tab, filter the **Privileges** list to **Maintain workers**.</span></span>

   <span data-ttu-id="61a4e-119">[![Jogosultságok listájának szűrése](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)</span><span class="sxs-lookup"><span data-stu-id="61a4e-119">[![Filter Privileges list](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)</span></span>

3. <span data-ttu-id="61a4e-120">Válassza a **Hivatkozások** oszlopban a **Megjelenítendő menüelemek** elemet.</span><span class="sxs-lookup"><span data-stu-id="61a4e-120">In the **References** column, select **Display menu items**.</span></span>

4. <span data-ttu-id="61a4e-121">A **Megjelenítendő menüelemek** közül válassza ki a **HcmWorkersWithoutEmployment** elemet.</span><span class="sxs-lookup"><span data-stu-id="61a4e-121">In **Display menu items**, select **HcmWorkersWithoutEmployment**.</span></span>

   <span data-ttu-id="61a4e-122">[![Kiválasztás (képernyő)](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)</span><span class="sxs-lookup"><span data-stu-id="61a4e-122">[![Select form](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)</span></span>

5. <span data-ttu-id="61a4e-123">A **Törlési** engedélyt módosítsa **Engedélyezre**.</span><span class="sxs-lookup"><span data-stu-id="61a4e-123">Set the **Delete** permission to **Grant**.</span></span>

6. <span data-ttu-id="61a4e-124">Válassza ki a **Nem közzétett objektumok** lapot.</span><span class="sxs-lookup"><span data-stu-id="61a4e-124">Select the **Unpublished objects** tab.</span></span>

7. <span data-ttu-id="61a4e-125">Válassza az **Összes közzététele** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="61a4e-125">Select **Publish all**.</span></span>

   <span data-ttu-id="61a4e-126">[![Változások közzététele](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)</span><span class="sxs-lookup"><span data-stu-id="61a4e-126">[![Publish changes](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]