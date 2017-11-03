---
title: "Tervezett rendelések karbantartása"
description: "Ez a cikk a tervezett rendelések kezelésével kapcsolatban nyújt információkat. Leírja, hogyan frissítheti a tervezett rendelések állapotát, erősítheti meg őket, és hogy hogyan szűrheti a kijelölttel azonos állapotú tervezett rendeléseket."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 8931908fbf643a8154da70d2ad065ea47d2aa4e6
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="maintain-planned-orders"></a><span data-ttu-id="6bd1f-104">Tervezett rendelések karbantartása</span><span class="sxs-lookup"><span data-stu-id="6bd1f-104">Maintain planned orders</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="6bd1f-105">Ez a cikk a tervezett rendelések kezelésével kapcsolatban nyújt információkat.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-105">This article provides information about how to manage planned orders.</span></span> <span data-ttu-id="6bd1f-106">Leírja, hogyan frissítheti a tervezett rendelések állapotát, erősítheti meg őket, és hogy hogyan szűrheti a kijelölttel azonos állapotú tervezett rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="6bd1f-107">A tervezett rendeléseket kezelheti az **Alaptervezés** munkaterületen, a **Tervezett rendelés** listában, vagy a **Tervezett termelési rendelések**, **Tervezett beszerzési rendelések**, és **Tervezett átmozgatás** listákban.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> <span data-ttu-id="6bd1f-108">Használhatja az **Állapot** mezőt, ami segít nyomon követni folyamatot.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-108">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="6bd1f-109">A következő értékek kerülnek felhasználásra:</span><span class="sxs-lookup"><span data-stu-id="6bd1f-109">The following values are used:</span></span>

-   <span data-ttu-id="6bd1f-110">Amikor az alaptervezés tervezett rendeléseket készít, akkor a tervezett rendelések állapota **Feldolgozatlan**.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-110">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="6bd1f-111">Ha úgy dönt, hogy nem erősíti meg a tervezett rendelést, akkor hozzárendelheti a **Befejezett** állapotot.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-111">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="6bd1f-112">Ha úgy dönt, hogy megerősít egy tervezett rendelést, akkor hozzárendelheti a **Jóváhagyva** állapotot.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-112">When you decide to firm a planned order, you can give it a status of **Approved**.</span></span> <span data-ttu-id="6bd1f-113">Ez az állapot jelzi, hogy jóváhagyja a tervezett rendelés megerősítését, de még nincs megerősítve.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-113">This status indicates that you approve firming of the planned order, but it isn't firmed yet.</span></span>

<span data-ttu-id="6bd1f-114">**Megjegyzés:** Egy jóváhagyott tervezett rendelés a jelenlegi állapotában kerül átvitelre kerül a következő alaptervezési számításba.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-114">**Note:** An approved planned order is transferred, in its current state, to the next master planning calculation.</span></span> <span data-ttu-id="6bd1f-115">Tervezett rendelések megerősítéséhez kattintson a **Megerősítés** gombra.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-115">You can firm planned orders by clicking **Firm**.</span></span> <span data-ttu-id="6bd1f-116">A következő tervezett megrendeléseket lehet megerősíteni:</span><span class="sxs-lookup"><span data-stu-id="6bd1f-116">You can firm the following planned orders:</span></span>

-   <span data-ttu-id="6bd1f-117">A kijelölt tervezett rendelés.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-117">The planned order that is selected.</span></span>
-   <span data-ttu-id="6bd1f-118">Több tervezett megrendelést.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-118">Multiple planned orders.</span></span>
-   <span data-ttu-id="6bd1f-119">Azon tervezett rendelések, amelyek egy **Alábontások** lapon szereplő alábontás által jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-119">Planned orders that are generated by an explosion from the **Explosion** page.</span></span> <span data-ttu-id="6bd1f-120">Kattintson a **Tervezett rendelések** elemre, válassza ki a tervezett rendelést, majd kattintson a **Megerősítés** gombra.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-120">Click **Planned orders**, select the planned order, and then click **Firm**.</span></span>

<span data-ttu-id="6bd1f-121">Amikor egy tervezett rendelést megerősít, akkor az a megfelelő modul rendelések szakaszába kerül.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-121">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span> <span data-ttu-id="6bd1f-122">**Megjegyzés:** Ha a jobb gombbal egy tervezett rendelésre kattint, amelynek adott állapota és szűrője van, akkor elérheti a többi ugyanazon állapottal rendelkező tervezett rendelést.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-122">**Note:** You can right-click a planned order that has a particular status and filter for other planned orders that have the same status.</span></span> <span data-ttu-id="6bd1f-123">Ez a funkció akkor hasznos, ha például ki akarja szűrni az olyan tervezett rendeléseket, amelyek állapota **Jóváhagyva**, hogy megerősíthesse őket.</span><span class="sxs-lookup"><span data-stu-id="6bd1f-123">This functionality is useful if, for example, you want to filter for all planned orders that have a status of **Approved**, so that you can then firm them.</span></span>

<a name="see-also"></a><span data-ttu-id="6bd1f-124">Lásd még</span><span class="sxs-lookup"><span data-stu-id="6bd1f-124">See also</span></span>
--------

[<span data-ttu-id="6bd1f-125">Alaptervek</span><span class="sxs-lookup"><span data-stu-id="6bd1f-125">Master plans</span></span>](master-plans.md)




