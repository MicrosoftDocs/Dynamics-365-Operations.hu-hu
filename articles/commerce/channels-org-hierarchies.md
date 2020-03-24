---
title: Szervezeti hierarchiák létrehozása
description: Ez a témakör a szervezeti hierarchia beállítását írja le a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 29d4b686cbb66715196fca06e4642fbb8a337ace
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/10/2020
ms.locfileid: "3113851"
---
# <a name="set-up-organization-hierarchies"></a><span data-ttu-id="c01b3-103">Szervezeti hierarchiák létrehozása</span><span class="sxs-lookup"><span data-stu-id="c01b3-103">Set up organization hierarchies</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="c01b3-104">Ez a témakör a szervezeti hierarchia beállítását írja le a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="c01b3-104">This topic describes how to set up organization hierarchies in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c01b3-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="c01b3-105">Overview</span></span>

<span data-ttu-id="c01b3-106">A csatornák létrehozása előtt győződjön meg arról, hogy be van állítva a szervezeti hierarchiák.</span><span class="sxs-lookup"><span data-stu-id="c01b3-106">Before creating channels, you'll want to ensure you have set up your organization hierarchies.</span></span>

<span data-ttu-id="c01b3-107">A szervezeti hierarchiák segítségével több nézőpontból is megtekintheti vállalatát, és jelentést is készíthet róla.</span><span class="sxs-lookup"><span data-stu-id="c01b3-107">You can use organization hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="c01b3-108">Például beállíthat egy hierarchiát adózási, jogi, illetve kötelezően előírt jelentésekhez.</span><span class="sxs-lookup"><span data-stu-id="c01b3-108">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="c01b3-109">Utána beállíthat egy másik hierarchiát olyan pénzügyi információkat tartalmazó jelentéshez, mely jogilag nem kötelező, de a belső jelentésekhez használható.</span><span class="sxs-lookup"><span data-stu-id="c01b3-109">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span>

<span data-ttu-id="c01b3-110">A szervezeti hierarchia létrehozása előtt létre kell hoznia a szervezeteket.</span><span class="sxs-lookup"><span data-stu-id="c01b3-110">Before you create an organization hierarchy, you must create organizations.</span></span> <span data-ttu-id="c01b3-111">További tudnivalókért lásd a [Jogi személyek létrehozása](channels-legal-entities.md) vagy [Üzemi egységek létrehozása](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json) feladatokat.</span><span class="sxs-lookup"><span data-stu-id="c01b3-111">For more information, see [Create legal entities](channels-legal-entities.md) or [Create operating units](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).</span></span>


<span data-ttu-id="c01b3-112">További információért tekintse át az alábbi témaköröket.</span><span class="sxs-lookup"><span data-stu-id="c01b3-112">For more information, see the following topics.</span></span>
- [<span data-ttu-id="c01b3-113">Szervezetek és szervezeti hierarchiák áttekintése</span><span class="sxs-lookup"><span data-stu-id="c01b3-113">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="c01b3-114">Szervezeti hierarchia megtervezése</span><span class="sxs-lookup"><span data-stu-id="c01b3-114">Plan your organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="c01b3-115">Szervezeti hierarchia létrehozása</span><span class="sxs-lookup"><span data-stu-id="c01b3-115">Create an organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy.md?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a><span data-ttu-id="c01b3-116">Szervezeti hierarchia létrehozása</span><span class="sxs-lookup"><span data-stu-id="c01b3-116">Create an organizational hierarchy</span></span>

<span data-ttu-id="c01b3-117">A szervezeti hierarchia létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c01b3-117">To create an organizational hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="c01b3-118">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Szervezeti hierarchiák** részhez.</span><span class="sxs-lookup"><span data-stu-id="c01b3-118">In the navigation pane, go to **Modules \> Retail and commerce \> Channel Setup \> Organization hierarchies**.</span></span>
1. <span data-ttu-id="c01b3-119">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="c01b3-119">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="c01b3-120">A **Név** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c01b3-120">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="c01b3-121">A **Cél** területen kattintson a **Cél hozzárendelése** elemre.</span><span class="sxs-lookup"><span data-stu-id="c01b3-121">In the **Purpose** section, select **Assign purpose**.</span></span>
1. <span data-ttu-id="c01b3-122">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="c01b3-122">In the list, find and select the desired record.</span></span> <span data-ttu-id="c01b3-123">Cél kiválasztása a szervezeti hierarchia hozzárendeléséhez.</span><span class="sxs-lookup"><span data-stu-id="c01b3-123">Select a purpose to assign to your organization hierarchy.</span></span>
1. <span data-ttu-id="c01b3-124">A **Hozzárendelt hierarchiák** szakaszban kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="c01b3-124">In the **Assigned hierarchies** section, select **Add**.</span></span>
1. <span data-ttu-id="c01b3-125">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="c01b3-125">In the list, mark the selected row.</span></span> <span data-ttu-id="c01b3-126">A most létrehozott hierarchia keresése.</span><span class="sxs-lookup"><span data-stu-id="c01b3-126">Find the hierarchy you just created.</span></span>
1. <span data-ttu-id="c01b3-127">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c01b3-127">Select **OK**.</span></span>

<span data-ttu-id="c01b3-128">A következő kép egy fiktív "Adventure Works" üzletcsoport számára létrehozott példa szervezeti hierarchiát mutat be.</span><span class="sxs-lookup"><span data-stu-id="c01b3-128">The following image shows an example organizational hierarchy created for a fictitious "Adventure Works" set of stores.</span></span>

![Szervezeti hierarchia - példa](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a><span data-ttu-id="c01b3-130">Szervezetek felvétele a hierarchiába</span><span class="sxs-lookup"><span data-stu-id="c01b3-130">Add organizations to a hierarchy</span></span>

<span data-ttu-id="c01b3-131">A szervezetek hierarchiához való hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c01b3-131">To add organizations to a hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="c01b3-132">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="c01b3-132">In the list, find and select the desired record.</span></span> <span data-ttu-id="c01b3-133">A hierarchia kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="c01b3-133">Select your hierarchy.</span></span>
1. <span data-ttu-id="c01b3-134">A műveleti ablaktáblán válassza a **Megtekintés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c01b3-134">On the action pane, select **View**.</span></span>
1. <span data-ttu-id="c01b3-135">Szükség szerint adjon hozzá szervezeteket.</span><span class="sxs-lookup"><span data-stu-id="c01b3-135">Add organizations, as necessary.</span></span>
1. <span data-ttu-id="c01b3-136">Szervezet hozzáadásához válassza a **Szerkesztés** parancsot, majd válassza a **Beszúrás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="c01b3-136">To add an organization, select **Edit** and then select **Insert**.</span></span> <span data-ttu-id="c01b3-137">Amikor befejezte a módosításokat elmentheti a vázlatot és közzé teheti a módosításokat.</span><span class="sxs-lookup"><span data-stu-id="c01b3-137">When you are done making changes you can save a draft and publish the changes.</span></span>

<span data-ttu-id="c01b3-138">A következő kép azt jeleníti meg, hogy milyen jogi személy van hozzáadva a hierarchia gyökerében, négy költséghely hozzáadásával a "Áruház", "Kifutó", "online" és a "Hívásközpont" csatornákhoz.</span><span class="sxs-lookup"><span data-stu-id="c01b3-138">The following image shows a legal entity added at the hierarchy root with four cost centers added for "Mall", "Outlet", "Online" and "Call Center" channels.</span></span> <span data-ttu-id="c01b3-139">Ezután a különböző kiskereskedelmi, hívásközponti és online csatornák mindegyikhez hozzáadhatók.</span><span class="sxs-lookup"><span data-stu-id="c01b3-139">Various retail, call center and online channels can then be added to each.</span></span>

![Hierarchiatervező - példa](media/hierarchy-designer.png)

## <a name="additional-resources"></a><span data-ttu-id="c01b3-141">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c01b3-141">Additional resources</span></span>

[<span data-ttu-id="c01b3-142">Szervezetek és szervezeti hierarchiák áttekintése</span><span class="sxs-lookup"><span data-stu-id="c01b3-142">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="c01b3-143">Szervezeti hierarchia megtervezése</span><span class="sxs-lookup"><span data-stu-id="c01b3-143">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="c01b3-144">Jogi személyek létrehozása</span><span class="sxs-lookup"><span data-stu-id="c01b3-144">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="c01b3-145">Üzemi egységek létrehozása</span><span class="sxs-lookup"><span data-stu-id="c01b3-145">Create operating units</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="c01b3-146">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="c01b3-146">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="c01b3-147">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="c01b3-147">Channel setup prerequisites</span></span>](channels-prerequisites.md)
