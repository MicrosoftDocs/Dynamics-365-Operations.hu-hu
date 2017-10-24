--- 
title: "Termelési jelentés készként jelenítése"
description: "Ez az eljárás bemutatja, hogyan lehet készre jelenteni egy termelési rendelést."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 17b2285e4669f1ad8fa6cea1250693a2a70c7dfa
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="report-a-production-order-as-finished"></a><span data-ttu-id="fb7cd-103">Termelési jelentés készként jelenítése</span><span class="sxs-lookup"><span data-stu-id="fb7cd-103">Report a production order as finished</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fb7cd-104">Ez az eljárás bemutatja, hogyan lehet készre jelenteni egy termelési rendelést.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-104">This procedure shows how to report a production order as finished.</span></span> <span data-ttu-id="fb7cd-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="fb7cd-106">Ez a hatodik eljárás abból a hétből, amely bemutatja a termelési rendelés életciklusát.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-106">This is the sixth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="report-a-production-order-as-finished"></a><span data-ttu-id="fb7cd-107">Termelési jelentés készként jelenítése</span><span class="sxs-lookup"><span data-stu-id="fb7cd-107">Report a production order as finished</span></span>
1. <span data-ttu-id="fb7cd-108">Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="fb7cd-109">Válasszon ki egy Elindítva állapotú termelési rendelést.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-109">Select a production order that has the Started status.</span></span>  
2. <span data-ttu-id="fb7cd-110">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="fb7cd-111">Kattintson a Jelentés készként lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-111">Click Report as finished.</span></span>
    * <span data-ttu-id="fb7cd-112">Ezen a lapon megerősítheti a készre jelentendő késztermékek mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-112">On this page, you can confirm the quantity of the finished product to be reported as finished.</span></span>  
4. <span data-ttu-id="fb7cd-113">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-113">Click the General tab.</span></span>
5. <span data-ttu-id="fb7cd-114">Állítsa a Jó mennyiséget a „18” értékre.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-114">Set Good quantity to '18'.</span></span>
6. <span data-ttu-id="fb7cd-115">Állítsa a Hiba mennyiséget a „2” értékre.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-115">Set Error quantity to '2'.</span></span>
7. <span data-ttu-id="fb7cd-116">A Hibaok mezőben válassza az „Anyag” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-116">In the Error cause field, select 'Material'.</span></span>
8. <span data-ttu-id="fb7cd-117">Válassza ki vagy törölje a Záró feladat jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-117">Select or clear the End job check box.</span></span>
9. <span data-ttu-id="fb7cd-118">Válassza ki vagy törölje a Hiba elfogadása jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-118">Select or clear the Accept error check box.</span></span>
10. <span data-ttu-id="fb7cd-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-119">Click OK.</span></span>

## <a name="verify-the-report-as-finished-journal"></a><span data-ttu-id="fb7cd-120">A Készre jelentés napló ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="fb7cd-120">Verify the Report as finished journal</span></span>
1. <span data-ttu-id="fb7cd-121">A Művelet panelen kattintson a Nézet elemre.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-121">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="fb7cd-122">Kattintson a Készre jelentett lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-122">Click Reported as finished.</span></span>
3. <span data-ttu-id="fb7cd-123">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="fb7cd-124">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="fb7cd-125">A Készre jelentés napló feladásra kerül.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-125">The Report as finished journal is posted.</span></span> <span data-ttu-id="fb7cd-126">Ha módosítani szeretné a naplót, akkor manuálisan létrehozhat egy új naplót, ahol elvégezheti a módosításokat.</span><span class="sxs-lookup"><span data-stu-id="fb7cd-126">If you want to make adjustments to the journal, you can manually create  a new journal where you can make changes.</span></span>  

