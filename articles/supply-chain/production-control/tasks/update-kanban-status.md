---
title: Kanbanállapot frissítése
description: Amikor a rendszer tévedésből kiüríti a kanbant vagy a kapott kanbant ki kell üríteni, frissítenie kell a kanban állapotát.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1d069414829518c8c952a0e7a74cd0ae4f24c450
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571381"
---
# <a name="update-kanban-status"></a><span data-ttu-id="0a525-103">Kanbanállapot frissítése</span><span class="sxs-lookup"><span data-stu-id="0a525-103">Update kanban status</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0a525-104">Amikor a rendszer tévedésből kiüríti a kanbant vagy a kapott kanbant ki kell üríteni, frissítenie kell a kanban állapotát.</span><span class="sxs-lookup"><span data-stu-id="0a525-104">When a kanban is emptied by mistake or a received kanban needs to be emptied, you need to update kanban status.</span></span> <span data-ttu-id="0a525-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="0a525-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0a525-106">Ezt az eljárást a Művezető használja.</span><span class="sxs-lookup"><span data-stu-id="0a525-106">This procedure is intended for the shop supervisor.</span></span>


## <a name="find-the-kanban"></a><span data-ttu-id="0a525-107">A kanban keresése.</span><span class="sxs-lookup"><span data-stu-id="0a525-107">Find the kanban.</span></span>
1. <span data-ttu-id="0a525-108">Ugorjon a Gyártásvezérlés > Kanban > Kanbanok pontra.</span><span class="sxs-lookup"><span data-stu-id="0a525-108">Go to Production control > Kanban > Kanbans.</span></span>
2. <span data-ttu-id="0a525-109">Nyissa meg az Anyagkezelési egység állapota oszlopszűrőt.</span><span class="sxs-lookup"><span data-stu-id="0a525-109">Open Handling unit status column filter.</span></span>
3. <span data-ttu-id="0a525-110">Kattintás a Törlés gombra.</span><span class="sxs-lookup"><span data-stu-id="0a525-110">Click Clear.</span></span>
    * <span data-ttu-id="0a525-111">Ez visszaállítja a szűrőket.</span><span class="sxs-lookup"><span data-stu-id="0a525-111">This resets the filters.</span></span>  
4. <span data-ttu-id="0a525-112">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="0a525-112">Use the Quick Filter to find records.</span></span> <span data-ttu-id="0a525-113">Például végezzen szűrést a „000149” értékkel a Kártyaszám mezőben.</span><span class="sxs-lookup"><span data-stu-id="0a525-113">For example, filter on the Card number field with a value of '000149'.</span></span>

## <a name="change-emptied-status-to-received-status"></a><span data-ttu-id="0a525-114">Módosítsa a kiürített állapotot beérkezett állapotra</span><span class="sxs-lookup"><span data-stu-id="0a525-114">Change emptied status to received status</span></span>
1. <span data-ttu-id="0a525-115">Kattintson az Üres anyagkezelési egység sztornírozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0a525-115">Click Reverse empty handling unit.</span></span>
2. <span data-ttu-id="0a525-116">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0a525-116">Click OK.</span></span>
    * <span data-ttu-id="0a525-117">Vegye figyelembe, hogy az Anyagkezelési egység állapota Bevételezett.</span><span class="sxs-lookup"><span data-stu-id="0a525-117">Notice that the Handling unit status is Received.</span></span>  

## <a name="change-received-status-to-emptied-status"></a><span data-ttu-id="0a525-118">Módosítsa a beérkezett állapotot kiürített állapotra</span><span class="sxs-lookup"><span data-stu-id="0a525-118">Change received status to emptied status</span></span>
1. <span data-ttu-id="0a525-119">Kattintson az Üres kanban lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0a525-119">Click Empty kanban.</span></span>
2. <span data-ttu-id="0a525-120">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0a525-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0a525-121">Vegye figyelembe, hogy az Anyagkezelési egység állapota Kiürítve.</span><span class="sxs-lookup"><span data-stu-id="0a525-121">Notice that the Handling unit status is Emptied.</span></span>  

