--- 
title: "Egy helyre vonatkozó terv létrehozása"
description: "A termeléstervező kiszámítja az anyag és a kapacitásszükségletét egy adott cikk termelésére vonatkozóan."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 8c44579df2f844bcd4668a218df2ebdca37fa0cc
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-plan-for-a-site"></a><span data-ttu-id="0cc25-103">Egy helyre vonatkozó terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="0cc25-103">Create a plan for a site</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0cc25-104">A termeléstervező kiszámítja az anyag és a kapacitásszükségletét egy adott cikk termelésére vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="0cc25-104">The production planner calculates the material and capacity requirements for the production of a specific item.</span></span> <span data-ttu-id="0cc25-105">A Forrás javaslatok létrehozása után a rendeléseket azon a telephelyen találja, amelyre vonatkozóan eltervezi és megerősíti a rendeléseket, kezdve a sürgős esetektől.</span><span class="sxs-lookup"><span data-stu-id="0cc25-105">After the sourcing suggestions are created, he finds the orders at the site for which he is planning and firms the orders, starting from the urgent ones.</span></span> <span data-ttu-id="0cc25-106">A legtöbb sürgős rendelések azok a rendelések, amelyeket meg kell erősíteni az aktuális napon.</span><span class="sxs-lookup"><span data-stu-id="0cc25-106">The most urgent orders are the ones that need to be firmed on the current date.</span></span> <span data-ttu-id="0cc25-107">Az USMF bemutató vállalati adatainak használatával elvégezheti ezeket a műveleteket.</span><span class="sxs-lookup"><span data-stu-id="0cc25-107">Use the demo data company USMF to perform these tasks.</span></span>


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a><span data-ttu-id="0cc25-108">Hozzon létre Anyag- és Kapacitástervet egy cikkre vonatkozóan</span><span class="sxs-lookup"><span data-stu-id="0cc25-108">Create a materials and capacity plan for an item</span></span>
1. <span data-ttu-id="0cc25-109">Kattintson az Alaptervezés parancsra.</span><span class="sxs-lookup"><span data-stu-id="0cc25-109">Click Master planning.</span></span>
    * <span data-ttu-id="0cc25-110">Keresse meg az alapértelmezett irányítópultot.</span><span class="sxs-lookup"><span data-stu-id="0cc25-110">You need to navigate to the default Dashboard.</span></span>  
2. <span data-ttu-id="0cc25-111">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="0cc25-111">Click Run.</span></span>
3. <span data-ttu-id="0cc25-112">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="0cc25-112">Expand the Records to include section.</span></span>
4. <span data-ttu-id="0cc25-113">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="0cc25-113">Click Filter.</span></span>
5. <span data-ttu-id="0cc25-114">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0cc25-114">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="0cc25-115">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0cc25-115">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="0cc25-116">Példa: D0001</span><span class="sxs-lookup"><span data-stu-id="0cc25-116">Example: D0001</span></span>  
7. <span data-ttu-id="0cc25-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0cc25-117">Click OK.</span></span>
8. <span data-ttu-id="0cc25-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0cc25-118">Click OK.</span></span>
    * <span data-ttu-id="0cc25-119">Ez a folyamat eltarthat néhány percig.</span><span class="sxs-lookup"><span data-stu-id="0cc25-119">This may take a few minutes.</span></span>  
9. <span data-ttu-id="0cc25-120">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="0cc25-120">Refresh the page.</span></span>

## <a name="identify-the-urgent-planned-orders-for-the-item"></a><span data-ttu-id="0cc25-121">Határozza meg a sürgős tervezett rendeléseket a cikkre vonatkozóan</span><span class="sxs-lookup"><span data-stu-id="0cc25-121">Identify the urgent planned orders for the item</span></span>
1. <span data-ttu-id="0cc25-122">Nyissa meg a cikkszám oszlop szűrőt.</span><span class="sxs-lookup"><span data-stu-id="0cc25-122">Open Item number column filter.</span></span>
2. <span data-ttu-id="0cc25-123">Alkalmazzon szűrőt a „Cikkszám” mezőn „D0001” értékkel, az „Ezzel kezdődik” szűrési operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="0cc25-123">Apply a filter on the "Item number" field, with a value of "D0001", using the "begins with" filter operator.</span></span>
3. <span data-ttu-id="0cc25-124">Megrendelési dátum oszlopszűrőjének megnyitása.</span><span class="sxs-lookup"><span data-stu-id="0cc25-124">Open Order date column filter.</span></span>
4. <span data-ttu-id="0cc25-125">Szűrő alkalmazása a „Rendelés dátuma” mezőben, az aktuális dátum értékével, a „pontosan” szűrési operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="0cc25-125">Apply a filter on the "Order date" field, with a value of current date, using the "is exactly" filter operator.</span></span>

## <a name="firm-all-the-urgent-orders-for-the-item"></a><span data-ttu-id="0cc25-126">Erősítse meg az összes sürgős tervezett rendelést a cikkre vonatkozóan</span><span class="sxs-lookup"><span data-stu-id="0cc25-126">Firm all the urgent orders for the item</span></span>
1. <span data-ttu-id="0cc25-127">A listában jelölje meg az összes sort, vagy törölje a jelölésüket.</span><span class="sxs-lookup"><span data-stu-id="0cc25-127">In the list, mark or unmark all rows.</span></span>
2. <span data-ttu-id="0cc25-128">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="0cc25-128">Click Firm.</span></span>
3. <span data-ttu-id="0cc25-129">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0cc25-129">Click OK.</span></span>


