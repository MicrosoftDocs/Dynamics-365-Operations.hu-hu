---
title: Projekt alapú értékesítési rendelések idő és anyag projektekhez.
description: Ez a témakör ismerteti az idő-és anyagelszámolású projekteknél a projekt alapú értékesítési rendelések létrehozását.
author: KimANelson
manager: AnnBe
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2019-04-05
ms.dyn365.ops.version: AX 10.0.2
ms.openlocfilehash: d19ee9de70cd14c78a997b7a87c10b53ab3917b0
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249093"
---
# <a name="project-sales-orders-for-time-and-material-projects"></a><span data-ttu-id="6518b-103">Projekt alapú értékesítési rendelések idő és anyag projektekhez.</span><span class="sxs-lookup"><span data-stu-id="6518b-103">Project sales orders for time and material projects</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="6518b-104">Ez a témakör bemutatja hogyan hozhat létre értékesítési rendelést egy projekthez.</span><span class="sxs-lookup"><span data-stu-id="6518b-104">This topic describes how to create a sales order for a project.</span></span> <span data-ttu-id="6518b-105">Értékesítési rendelések csak **idő- és anyag** típusú projektekhez használhatók.</span><span class="sxs-lookup"><span data-stu-id="6518b-105">Sales orders can only be created for projects of type **time and material**.</span></span>

<span data-ttu-id="6518b-106">Ha az idő- és anyagalapú projektnél több finanszírozási forrás is engedélyezve van a **Projektvezetési paraméterek** beállítás **Több finanszírozási forrással rendelkező projekthez tartozó értékesítési rendelések engedélyezése** értékével.</span><span class="sxs-lookup"><span data-stu-id="6518b-106">If a time and material project has multiple funding sources on the project contract, you must enable the **Allow sales orders for projects with multiple funding sources** parameter on the **Project management and accounting parameters** page.</span></span> 

> [!NOTE]
> - <span data-ttu-id="6518b-107">Projekt értékesítési rendelések támogatása több finanszírozási forrással támogatása a 10.0.2 alkalmazáskiadástól kezdődően érhető el.</span><span class="sxs-lookup"><span data-stu-id="6518b-107">Support for project sales orders with multiple funding sources is available starting with application release 10.0.2 and higher.</span></span>
> - <span data-ttu-id="6518b-108">A paraméter, amely lehetővé teszi a több finanszírozási forrással rendelkező projekt értékesítési rendeléseket a 2020 április hullámban kivezetésre kerül, amely után a funkció mindig engedélyezve lesz.</span><span class="sxs-lookup"><span data-stu-id="6518b-108">The parameter to enable the support for project sales orders with multiple funding sources will be removed in the April 2020 release wave, after which the functionality will always be enabled.</span></span>

<span data-ttu-id="6518b-109">Értékesítési rendelések alapján kétféleképpen hozhat létre projektet:</span><span class="sxs-lookup"><span data-stu-id="6518b-109">You can create project-based sales orders in two ways:</span></span>

- <span data-ttu-id="6518b-110">Magából a projektből.</span><span class="sxs-lookup"><span data-stu-id="6518b-110">Go to the project itself.</span></span> <span data-ttu-id="6518b-111">A Művelet panelen válassza a **Kezelés > Cikkfeladatok > Értékesítési rendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6518b-111">On the Action Pane, select **Manage > Item tasks > Sales order**.</span></span> <span data-ttu-id="6518b-112">A projektadatok a projekt értékesítési rendeléséből érkeznek.</span><span class="sxs-lookup"><span data-stu-id="6518b-112">The project information will default to the sales order from the project.</span></span> <span data-ttu-id="6518b-113">Ha a projektszerződés egynél több finanszírozási forrást tartalmaz, szükséges lesz a finanszírozási forrás beállítása a vevő beállításához az értékesítési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="6518b-113">If the project contract has more than one funding source, you will need to select the funding source to set the customer for the sales order.</span></span> <span data-ttu-id="6518b-114">Ha a projekthez csak egy finanszírozási forrás tartozik, a vevő automatikusan lesz beállítva.</span><span class="sxs-lookup"><span data-stu-id="6518b-114">If there is only one funding source for the project, the customer will be automatically set.</span></span>
- <span data-ttu-id="6518b-115">Menjen az **Összes értékesítési rendelés** listaoldalra, és hozzon létre egy új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="6518b-115">Go to the **All sales order** list page and create a new sales order.</span></span> <span data-ttu-id="6518b-116">Ki kell választania a projektet az értékesítési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="6518b-116">You will need to select the project for the sales order.</span></span> <span data-ttu-id="6518b-117">A projekt kiválasztása után, a vevő a finanszírozási forrásból lesz beállítva, vagy Önnek kell kiválasztania a finanszírozási forrást, ha a projekt több finanszírozási forrással rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="6518b-117">After the project is selected, the customer will be set from the funding source or you will need to select the funding source if the project contract has multiple funding sources.</span></span>

