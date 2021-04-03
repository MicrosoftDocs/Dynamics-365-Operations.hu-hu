---
title: Kanbanállapot frissítése
description: Amikor a rendszer tévedésből kiüríti a kanbant vagy a kapott kanbant ki kell üríteni, frissítenie kell a kanban állapotát.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 055765452579b1de74f1c2158de9c6cb4ee80f16
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252822"
---
# <a name="update-kanban-status"></a><span data-ttu-id="b947d-103">Kanbanállapot frissítése</span><span class="sxs-lookup"><span data-stu-id="b947d-103">Update kanban status</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b947d-104">Amikor a rendszer tévedésből kiüríti a kanbant vagy a kapott kanbant ki kell üríteni, frissítenie kell a kanban állapotát.</span><span class="sxs-lookup"><span data-stu-id="b947d-104">When a kanban is emptied by mistake or a received kanban needs to be emptied, you need to update kanban status.</span></span> <span data-ttu-id="b947d-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="b947d-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="b947d-106">Ezt az eljárást a Művezető használja.</span><span class="sxs-lookup"><span data-stu-id="b947d-106">This procedure is intended for the shop supervisor.</span></span>


## <a name="find-the-kanban"></a><span data-ttu-id="b947d-107">A kanban keresése.</span><span class="sxs-lookup"><span data-stu-id="b947d-107">Find the kanban.</span></span>
1. <span data-ttu-id="b947d-108">Ugorjon a Gyártásvezérlés > Kanban > Kanbanok pontra.</span><span class="sxs-lookup"><span data-stu-id="b947d-108">Go to Production control > Kanban > Kanbans.</span></span>
2. <span data-ttu-id="b947d-109">Nyissa meg az Anyagkezelési egység állapota oszlopszűrőt.</span><span class="sxs-lookup"><span data-stu-id="b947d-109">Open Handling unit status column filter.</span></span>
3. <span data-ttu-id="b947d-110">Kattintás a Törlés gombra.</span><span class="sxs-lookup"><span data-stu-id="b947d-110">Click Clear.</span></span>
    * <span data-ttu-id="b947d-111">Ez visszaállítja a szűrőket.</span><span class="sxs-lookup"><span data-stu-id="b947d-111">This resets the filters.</span></span>  
4. <span data-ttu-id="b947d-112">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="b947d-112">Use the Quick Filter to find records.</span></span> <span data-ttu-id="b947d-113">Például végezzen szűrést a „000149” értékkel a Kártyaszám mezőben.</span><span class="sxs-lookup"><span data-stu-id="b947d-113">For example, filter on the Card number field with a value of '000149'.</span></span>

## <a name="change-emptied-status-to-received-status"></a><span data-ttu-id="b947d-114">Módosítsa a kiürített állapotot beérkezett állapotra</span><span class="sxs-lookup"><span data-stu-id="b947d-114">Change emptied status to received status</span></span>
1. <span data-ttu-id="b947d-115">Kattintson az Üres anyagkezelési egység sztornírozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b947d-115">Click Reverse empty handling unit.</span></span>
2. <span data-ttu-id="b947d-116">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b947d-116">Click OK.</span></span>
    * <span data-ttu-id="b947d-117">Vegye figyelembe, hogy az Anyagkezelési egység állapota Bevételezett.</span><span class="sxs-lookup"><span data-stu-id="b947d-117">Notice that the Handling unit status is Received.</span></span>  

## <a name="change-received-status-to-emptied-status"></a><span data-ttu-id="b947d-118">Módosítsa a beérkezett állapotot kiürített állapotra</span><span class="sxs-lookup"><span data-stu-id="b947d-118">Change received status to emptied status</span></span>
1. <span data-ttu-id="b947d-119">Kattintson az Üres kanban lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b947d-119">Click Empty kanban.</span></span>
2. <span data-ttu-id="b947d-120">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="b947d-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="b947d-121">Vegye figyelembe, hogy az Anyagkezelési egység állapota Kiürítve.</span><span class="sxs-lookup"><span data-stu-id="b947d-121">Notice that the Handling unit status is Emptied.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]