---
title: "Termelési rendelés befejezése"
description: "Ez az eljárás bemutatja, hogyan lehet termelési rendelést befejezni."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 1cc586f804a072ca5499c73ecdf7d37778cbf067
ms.contentlocale: hu-hu
ms.lasthandoff: 02/06/2018

---
# <a name="end-a-production-order"></a><span data-ttu-id="c5541-103">Termelési rendelés befejezése</span><span class="sxs-lookup"><span data-stu-id="c5541-103">End a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c5541-104">Ez az eljárás bemutatja, hogyan lehet termelési rendelést befejezni.</span><span class="sxs-lookup"><span data-stu-id="c5541-104">This procedure shows how to end a production order.</span></span> <span data-ttu-id="c5541-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="c5541-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c5541-106">Ez az utolsó eljárás abból a hétből, amely bemutatja a termelési rendelés életciklusát.</span><span class="sxs-lookup"><span data-stu-id="c5541-106">This is the final procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="end-a-production-order"></a><span data-ttu-id="c5541-107">Termelési rendelés befejezése</span><span class="sxs-lookup"><span data-stu-id="c5541-107">End a production order</span></span>
1. <span data-ttu-id="c5541-108">Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="c5541-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="c5541-109">Válasszon egy Késznek jelentett termelési rendelést.</span><span class="sxs-lookup"><span data-stu-id="c5541-109">Select a production order that has the status Reported as finished.</span></span>  
2. <span data-ttu-id="c5541-110">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="c5541-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="c5541-111">Kattintson a Vége gombra.</span><span class="sxs-lookup"><span data-stu-id="c5541-111">Click End.</span></span>
    * <span data-ttu-id="c5541-112">Ezen a lapon erősítse meg a termelési rendelés befejezését.</span><span class="sxs-lookup"><span data-stu-id="c5541-112">On this page, you can confirm that you want to end the production order.</span></span>  
4. <span data-ttu-id="c5541-113">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="c5541-113">Click the General tab.</span></span>
5. <span data-ttu-id="c5541-114">Adja meg a dátumot a Dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="c5541-114">In the Date field, enter a date.</span></span>
6. <span data-ttu-id="c5541-115">A Selejtkezelés módja mezőben válassza a „Felosztás” elemet.</span><span class="sxs-lookup"><span data-stu-id="c5541-115">In the Scrap method field, select 'Allocation'.</span></span>
    * <span data-ttu-id="c5541-116">Ha az Elosztási módszert választja, a selejtezett anyagok költségét a késztermékekhez adja hozzá a rendszer.</span><span class="sxs-lookup"><span data-stu-id="c5541-116">When you select the Allocation method, costs from the scrapped materials are added to the finished goods.</span></span>  
7. <span data-ttu-id="c5541-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c5541-117">Click OK.</span></span>

## <a name="validate-calculation-results"></a><span data-ttu-id="c5541-118">A számítási eredmények ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="c5541-118">Validate calculation results</span></span>
1. <span data-ttu-id="c5541-119">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="c5541-119">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="c5541-120">Kattintson a Költség összehasonlítására.</span><span class="sxs-lookup"><span data-stu-id="c5541-120">Click View cost comparison.</span></span>
    * <span data-ttu-id="c5541-121">A termelési rendelés befejezése után összehasonlíthatja a becsült önköltségi árat és a realizált önköltségi árat a termelési különbözetek áttekintése érdekében.</span><span class="sxs-lookup"><span data-stu-id="c5541-121">After you have ended the production order, you can compare the estimated cost price against the realized cost price to get an overview of the production variances.</span></span>  

