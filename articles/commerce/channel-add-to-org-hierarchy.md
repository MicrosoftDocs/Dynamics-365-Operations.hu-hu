---
title: Csatorna hozzáadása a szervezeti hierarchiához
description: Ez a témakör azt mutatja be, hogyan lehet egy csatornát hozzáadni egy szervezeti hierarchiához a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: 4212797d2959c4f8b0d60e6b45de76ffc3ee0dc2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216752"
---
# <a name="add-a-channel-to-an-organizational-hierarchy"></a><span data-ttu-id="bd993-103">Csatorna hozzáadása a szervezeti hierarchiához</span><span class="sxs-lookup"><span data-stu-id="bd993-103">Add a channel to an organizational hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="bd993-104">Ez a témakör azt mutatja be, hogyan lehet egy csatornát hozzáadni egy szervezeti hierarchiához a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="bd993-104">This topic describes how to add a channel to an organizational hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="bd993-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="bd993-105">Overview</span></span>

<span data-ttu-id="bd993-106">A csatornáknak egy vagy több szervezeti hierarchiához kell tartozniuk.</span><span class="sxs-lookup"><span data-stu-id="bd993-106">Channels need to be associated with one or more organizational hierarchies.</span></span> <span data-ttu-id="bd993-107">A csatornák létrehozása előtt győződjön meg arról, hogy be van állítva a szervezeti hierarchiák.</span><span class="sxs-lookup"><span data-stu-id="bd993-107">Before creating channels, you need to confirm that your organizational hierarchies have been set up.</span></span>  

<span data-ttu-id="bd993-108">Lásd: [Szervezeti hierarchiák](channels-org-hierarchies.md) a szervezeti hierarchiák létrehozásával kapcsolatos további információkért.</span><span class="sxs-lookup"><span data-stu-id="bd993-108">See [Organizational hierarchies](channels-org-hierarchies.md) for more details on how to create organizational hierarchies.</span></span>

## <a name="select-a-hierarchy"></a><span data-ttu-id="bd993-109">Hierarchia kiválasztása</span><span class="sxs-lookup"><span data-stu-id="bd993-109">Select a hierarchy</span></span>

<span data-ttu-id="bd993-110">Hierarchia kiválasztásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="bd993-110">To select a hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="bd993-111">A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Szervezeti hierarchiák** részhez.</span><span class="sxs-lookup"><span data-stu-id="bd993-111">In the navigation pane, go to **Modules \> Retail and commerce \> Channel Setup \> Organization hierarchies**.</span></span>
1. <span data-ttu-id="bd993-112">A listából válassza ki azt a szervezeti hierarchiát, amelyhez a csatornáját hozzá szeretné adni.</span><span class="sxs-lookup"><span data-stu-id="bd993-112">From the list, select the organization hierarchy that you'll be adding the channel to.</span></span>
1. <span data-ttu-id="bd993-113">A művelet ablaktáblán a hierarchia részleteinek megtekintéséhez kattintson a **nézet** parancsra.</span><span class="sxs-lookup"><span data-stu-id="bd993-113">On the action pane, select **View** to view hierarchy details.</span></span>

<span data-ttu-id="bd993-114">A következő kép a szervezeti hierarchia részletes adatait jeleníti meg a kiválasztott hierarchiában.</span><span class="sxs-lookup"><span data-stu-id="bd993-114">The following image shows organizational hierarchy details for the selected hierarchy.</span></span>

![Szervezeti hierarchia részletes adatai a kiválasztott hierarchiában](media/channel-add-to-org-hierarchy-1.png)

## <a name="add-a-channel-to-a-hierachy-node"></a><span data-ttu-id="bd993-116">Csatorna hozzáadása egy hierarchia-csomóponthoz</span><span class="sxs-lookup"><span data-stu-id="bd993-116">Add a channel to a hierachy node</span></span>

<span data-ttu-id="bd993-117">Csatorna hozzáadásához egy hierarchia-csomóponthoz tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="bd993-117">To add a channel to a hierachy node, follow these steps.</span></span>

1. <span data-ttu-id="bd993-118">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bd993-118">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="bd993-119">Válassza ki azt a hierachia-csomópontot, amelyhez hozzá szeretné adni a csatornát, majd a **Beszúrás** legördülő listából válassza a **Kiskereskedelmi csatorna** elemet.</span><span class="sxs-lookup"><span data-stu-id="bd993-119">Select the hierachy node you want the channel added to, then from the **Insert** drop-down list, select **Retail Channel**.</span></span> 
1. <span data-ttu-id="bd993-120">Válassza ki a hozzáadni kívánt csatornát, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="bd993-120">Select the channel to add, then select the **OK** button.</span></span>
1. <span data-ttu-id="bd993-121">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bd993-121">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="bd993-122">A művelet ablaktáblán válassza a **közzététel** lehetőséget, és adjon meg egy **Érvényességi dátumot** a múltban, hogy ez a művelet azonnal érvénybe lépjen.</span><span class="sxs-lookup"><span data-stu-id="bd993-122">On the action pane, select **Publish** and provide an **Effective date** in the past to have this action go into effect immediately.</span></span>

<span data-ttu-id="bd993-123">A következő képen látható a hierarchia-csomóponthoz hozzáadni kívánt csatorna kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="bd993-123">The following image shows how to select a channel to add to a hierarchy node.</span></span>

![Csatorna kiválasztása a hierarchia-csomóponthoz való hozzáadásra](media/channel-add-to-org-hierarchy-2.png)

<span data-ttu-id="bd993-125">A következő kép egy olyan hierarchiát mutat, amelyben különböző csatornák kerültek hozzáadásra.</span><span class="sxs-lookup"><span data-stu-id="bd993-125">The following image shows a hierarchy with various channels added.</span></span>

![Hierarchia különböző hozzáadott csatornákkal](media/channel-add-to-org-hierarchy-3.png)

## <a name="additional-resources"></a><span data-ttu-id="bd993-127">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="bd993-127">Additional resources</span></span>

[<span data-ttu-id="bd993-128">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="bd993-128">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="bd993-129">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="bd993-129">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="bd993-130">Szervezetek és szervezeti hierarchiák áttekintése</span><span class="sxs-lookup"><span data-stu-id="bd993-130">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="bd993-131">Szervezeti hierarchia megtervezése</span><span class="sxs-lookup"><span data-stu-id="bd993-131">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="bd993-132">Szervezeti hierarchiák</span><span class="sxs-lookup"><span data-stu-id="bd993-132">Organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="bd993-133">Kiskereskedelmi csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="bd993-133">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="bd993-134">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="bd993-134">Set up an online channel</span></span>](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]