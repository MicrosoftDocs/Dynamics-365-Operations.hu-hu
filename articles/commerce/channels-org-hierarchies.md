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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 490d466c10cfe0640f8fbcf8fe2298536e499d9b
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477996"
---
# <a name="set-up-organization-hierarchies"></a><span data-ttu-id="3b6f0-103">Szervezeti hierarchiák létrehozása</span><span class="sxs-lookup"><span data-stu-id="3b6f0-103">Set up organization hierarchies</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3b6f0-104">Ez a témakör a szervezeti hierarchia beállítását írja le a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-104">This topic describes how to set up organization hierarchies in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="3b6f0-105">A csatornák létrehozása előtt győződjön meg arról, hogy be van állítva a szervezeti hierarchiák.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-105">Before creating channels, you'll want to ensure you have set up your organization hierarchies.</span></span>

<span data-ttu-id="3b6f0-106">A szervezeti hierarchiák segítségével több nézőpontból is megtekintheti vállalatát, és jelentést is készíthet róla.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-106">You can use organization hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="3b6f0-107">Például beállíthat egy hierarchiát adózási, jogi, illetve kötelezően előírt jelentésekhez.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-107">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="3b6f0-108">Utána beállíthat egy másik hierarchiát olyan pénzügyi információkat tartalmazó jelentéshez, mely jogilag nem kötelező, de a belső jelentésekhez használható.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-108">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span>

<span data-ttu-id="3b6f0-109">A szervezeti hierarchia létrehozása előtt létre kell hoznia a szervezeteket.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-109">Before you create an organization hierarchy, you must create organizations.</span></span> <span data-ttu-id="3b6f0-110">További tudnivalókért lásd a [Jogi személyek létrehozása](channels-legal-entities.md) vagy [Üzemi egységek létrehozása](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json) feladatokat.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-110">For more information, see [Create legal entities](channels-legal-entities.md) or [Create operating units](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).</span></span>


<span data-ttu-id="3b6f0-111">További információért tekintse át az alábbi témaköröket.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-111">For more information, see the following topics.</span></span>
- [<span data-ttu-id="3b6f0-112">Szervezetek és szervezeti hierarchiák áttekintése</span><span class="sxs-lookup"><span data-stu-id="3b6f0-112">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="3b6f0-113">Szervezeti hierarchia megtervezése</span><span class="sxs-lookup"><span data-stu-id="3b6f0-113">Plan your organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="3b6f0-114">Szervezeti hierarchia létrehozása</span><span class="sxs-lookup"><span data-stu-id="3b6f0-114">Create an organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy.md?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a><span data-ttu-id="3b6f0-115">Szervezeti hierarchia létrehozása</span><span class="sxs-lookup"><span data-stu-id="3b6f0-115">Create an organizational hierarchy</span></span>

<span data-ttu-id="3b6f0-116">A szervezeti hierarchia létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-116">To create an organizational hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="3b6f0-117">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Szervezeti hierarchiák** részhez.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-117">In the navigation pane, go to **Modules \> Retail and commerce \> Channel Setup \> Organization hierarchies**.</span></span>
1. <span data-ttu-id="3b6f0-118">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-118">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="3b6f0-119">A **Név** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-119">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="3b6f0-120">A **Cél** területen kattintson a **Cél hozzárendelése** elemre.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-120">In the **Purpose** section, select **Assign purpose**.</span></span>
1. <span data-ttu-id="3b6f0-121">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-121">In the list, find and select the desired record.</span></span> <span data-ttu-id="3b6f0-122">Cél kiválasztása a szervezeti hierarchia hozzárendeléséhez.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-122">Select a purpose to assign to your organization hierarchy.</span></span>
1. <span data-ttu-id="3b6f0-123">A **Hozzárendelt hierarchiák** szakaszban kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-123">In the **Assigned hierarchies** section, select **Add**.</span></span>
1. <span data-ttu-id="3b6f0-124">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-124">In the list, mark the selected row.</span></span> <span data-ttu-id="3b6f0-125">A most létrehozott hierarchia keresése.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-125">Find the hierarchy you just created.</span></span>
1. <span data-ttu-id="3b6f0-126">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-126">Select **OK**.</span></span>

<span data-ttu-id="3b6f0-127">A következő kép egy fiktív "Adventure Works" üzletcsoport számára létrehozott példa szervezeti hierarchiát mutat be.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-127">The following image shows an example organizational hierarchy created for a fictitious "Adventure Works" set of stores.</span></span>

![Szervezeti hierarchia - példa](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a><span data-ttu-id="3b6f0-129">Szervezetek felvétele a hierarchiába</span><span class="sxs-lookup"><span data-stu-id="3b6f0-129">Add organizations to a hierarchy</span></span>

<span data-ttu-id="3b6f0-130">A szervezetek hierarchiához való hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-130">To add organizations to a hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="3b6f0-131">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-131">In the list, find and select the desired record.</span></span> <span data-ttu-id="3b6f0-132">A hierarchia kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-132">Select your hierarchy.</span></span>
1. <span data-ttu-id="3b6f0-133">A műveleti ablaktáblán válassza a **Megtekintés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-133">On the action pane, select **View**.</span></span>
1. <span data-ttu-id="3b6f0-134">Szükség szerint adjon hozzá szervezeteket.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-134">Add organizations, as necessary.</span></span>
1. <span data-ttu-id="3b6f0-135">Szervezet hozzáadásához válassza a **Szerkesztés** parancsot, majd válassza a **Beszúrás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-135">To add an organization, select **Edit** and then select **Insert**.</span></span> <span data-ttu-id="3b6f0-136">Amikor befejezte a módosításokat elmentheti a vázlatot és közzé teheti a módosításokat.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-136">When you are done making changes you can save a draft and publish the changes.</span></span>

<span data-ttu-id="3b6f0-137">A következő kép azt jeleníti meg, hogy milyen jogi személy van hozzáadva a hierarchia gyökerében, négy költséghely hozzáadásával a "Áruház", "Kifutó", "online" és a "Hívásközpont" csatornákhoz.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-137">The following image shows a legal entity added at the hierarchy root with four cost centers added for "Mall", "Outlet", "Online" and "Call Center" channels.</span></span> <span data-ttu-id="3b6f0-138">Ezután a különböző kiskereskedelmi, hívásközponti és online csatornák mindegyikhez hozzáadhatók.</span><span class="sxs-lookup"><span data-stu-id="3b6f0-138">Various retail, call center and online channels can then be added to each.</span></span>

![Hierarchiatervező - példa](media/hierarchy-designer.png)

## <a name="additional-resources"></a><span data-ttu-id="3b6f0-140">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="3b6f0-140">Additional resources</span></span>

[<span data-ttu-id="3b6f0-141">Szervezetek és szervezeti hierarchiák áttekintése</span><span class="sxs-lookup"><span data-stu-id="3b6f0-141">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="3b6f0-142">Szervezeti hierarchia megtervezése</span><span class="sxs-lookup"><span data-stu-id="3b6f0-142">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="3b6f0-143">Jogi személyek létrehozása</span><span class="sxs-lookup"><span data-stu-id="3b6f0-143">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="3b6f0-144">Üzemi egységek létrehozása</span><span class="sxs-lookup"><span data-stu-id="3b6f0-144">Create operating units</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="3b6f0-145">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="3b6f0-145">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="3b6f0-146">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="3b6f0-146">Channel setup prerequisites</span></span>](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
