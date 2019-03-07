---
title: Tervezett rendelések karbantartása
description: Ez a témakör a tervezett rendelések kezelésével kapcsolatban nyújt információkat. Leírja, hogyan frissítheti a tervezett rendelések állapotát, erősítheti meg őket, és hogy hogyan szűrheti a kijelölttel azonos állapotú tervezett rendeléseket.
author: roxanadiaconu
manager: AnnBe
ms.date: 10/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bf578d98abc4825c5607ec031da6ab6737c3183a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "360463"
---
# <a name="maintain-planned-orders"></a><span data-ttu-id="18166-104">Tervezett rendelések karbantartása</span><span class="sxs-lookup"><span data-stu-id="18166-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="18166-105">Ez a témakör a tervezett rendelések kezelésével kapcsolatban nyújt információkat.</span><span class="sxs-lookup"><span data-stu-id="18166-105">This topic provides information about how to manage planned orders.</span></span> <span data-ttu-id="18166-106">Leírja, hogyan frissítheti a tervezett rendelések állapotát, erősítheti meg őket, és hogy hogyan szűrheti a kijelölttel azonos állapotú tervezett rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="18166-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="18166-107">A tervezett rendeléseket kezelheti az **Alaptervezés** munkaterületen, a **Tervezett rendelés** listában, vagy a **Tervezett termelési rendelések**, **Tervezett beszerzési rendelések**, és **Tervezett átmozgatás** listákban.</span><span class="sxs-lookup"><span data-stu-id="18166-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> <span data-ttu-id="18166-108">Használhatja az **Állapot** mezőt, ami segít nyomon követni folyamatot.</span><span class="sxs-lookup"><span data-stu-id="18166-108">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="18166-109">A következő értékek kerülnek felhasználásra:</span><span class="sxs-lookup"><span data-stu-id="18166-109">The following values are used:</span></span>

-   <span data-ttu-id="18166-110">Amikor az alaptervezés tervezett rendeléseket készít, akkor a tervezett rendelések állapota **Feldolgozatlan**.</span><span class="sxs-lookup"><span data-stu-id="18166-110">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="18166-111">Ha úgy dönt, hogy nem erősíti meg a tervezett rendelést, akkor hozzárendelheti a **Befejezett** állapotot.</span><span class="sxs-lookup"><span data-stu-id="18166-111">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="18166-112">Ha úgy dönt, hogy megerősít egy tervezett rendelést, akkor hozzárendelheti a **Jóváhagyva** állapotot.</span><span class="sxs-lookup"><span data-stu-id="18166-112">When you decide to firm a planned order, you can give it a status of **Approved**.</span></span> <span data-ttu-id="18166-113">Ez az állapot jelzi, hogy jóváhagyja a tervezett rendelés megerősítését, de még nincs megerősítve.</span><span class="sxs-lookup"><span data-stu-id="18166-113">This status indicates that you approve firming of the planned order, but it isn't firmed yet.</span></span>

<span data-ttu-id="18166-114">**Megjegyzés:** Egy jóváhagyott tervezett rendelés a jelenlegi állapotában kerül átvitelre kerül a következő alaptervezési számításba.</span><span class="sxs-lookup"><span data-stu-id="18166-114">**Note:** An approved planned order is transferred, in its current state, to the next master planning calculation.</span></span> <span data-ttu-id="18166-115">Tervezett rendelések megerősítéséhez kattintson a **Megerősítés** gombra.</span><span class="sxs-lookup"><span data-stu-id="18166-115">You can firm planned orders by clicking **Firm**.</span></span> <span data-ttu-id="18166-116">A következő tervezett megrendeléseket lehet megerősíteni:</span><span class="sxs-lookup"><span data-stu-id="18166-116">You can firm the following planned orders:</span></span>

-   <span data-ttu-id="18166-117">A kijelölt tervezett rendelés.</span><span class="sxs-lookup"><span data-stu-id="18166-117">The planned order that is selected.</span></span>
-   <span data-ttu-id="18166-118">Több tervezett megrendelést.</span><span class="sxs-lookup"><span data-stu-id="18166-118">Multiple planned orders.</span></span>
-   <span data-ttu-id="18166-119">Azon tervezett rendelések, amelyek egy **Alábontások** lapon szereplő alábontás által jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="18166-119">Planned orders that are generated by an explosion from the **Explosion** page.</span></span> <span data-ttu-id="18166-120">Kattintson a **Tervezett rendelések** elemre, válassza ki a tervezett rendelést, majd kattintson a **Megerősítés** gombra.</span><span class="sxs-lookup"><span data-stu-id="18166-120">Click **Planned orders**, select the planned order, and then click **Firm**.</span></span>

<span data-ttu-id="18166-121">Amikor egy tervezett rendelést megerősít, akkor az a megfelelő modul rendelések szakaszába kerül.</span><span class="sxs-lookup"><span data-stu-id="18166-121">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span> 

<a name="additional-resources"></a><span data-ttu-id="18166-122">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="18166-122">Additional resources</span></span>
--------

[<span data-ttu-id="18166-123">Alaptervek</span><span class="sxs-lookup"><span data-stu-id="18166-123">Master plans</span></span>](master-plans.md)



