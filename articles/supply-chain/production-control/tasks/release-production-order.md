---
title: Termelési rendelés kiadása
description: Ez az eljárás a termelési rendelések kiadását mutatja be.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmRelease, SrsReportViewerForm, ProdSetupRelease
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: beef850e7e58fb58db545c0be5990b52619070d3
ms.sourcegitcommit: 175f9394021322c685c5b37317c2f649c81a731a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826574"
---
# <a name="release-a-production-order"></a><span data-ttu-id="9aad5-103">Termelési rendelés kiadása</span><span class="sxs-lookup"><span data-stu-id="9aad5-103">Release a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9aad5-104">Ez az eljárás a termelési rendelések kiadását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="9aad5-104">This procedure shows how to release a production order.</span></span> <span data-ttu-id="9aad5-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="9aad5-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="9aad5-106">Ez a negyedik eljárás abból a hétből, amely bemutatja a termelési rendelés életciklusát.</span><span class="sxs-lookup"><span data-stu-id="9aad5-106">This is the fourth procedure out of seven which explains the production order lifecycle.</span></span>

1. <span data-ttu-id="9aad5-107">Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="9aad5-107">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="9aad5-108">A rácson belül válasszon ki egy Ütemezett állapotú termelési rendelést.</span><span class="sxs-lookup"><span data-stu-id="9aad5-108">In the grid, select a production order that has the Scheduled status.</span></span>  
2. <span data-ttu-id="9aad5-109">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="9aad5-109">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="9aad5-110">Kattintson a Kiadás elemre.</span><span class="sxs-lookup"><span data-stu-id="9aad5-110">Click Release.</span></span>
    * <span data-ttu-id="9aad5-111">Ezen a lapon tudja megerősíteni a termelési rendelések kiválasztott tartományának kiadását.</span><span class="sxs-lookup"><span data-stu-id="9aad5-111">On this page, you can confirm the release of the selected range of production orders.</span></span> <span data-ttu-id="9aad5-112">Kattintson a Kijelölés gombra rendelések hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="9aad5-112">Click Select if you want to add orders.</span></span>  
    * <span data-ttu-id="9aad5-113">A Kiadási lépés azt a termelési rendelés, a termelési üzem részére történő kiadását jelzi annak érdekében, hogy az üzemi dolgozók jelentést tudjanak küldeni a termelési feladatok előrehaladásáról.</span><span class="sxs-lookup"><span data-stu-id="9aad5-113">The Release step indicates when the production order is released to the production shop floor so that the shop floor operators can report progress on the production jobs.</span></span> <span data-ttu-id="9aad5-114">A feladatok feldolgozása vonatkozó lényeges információkat tartalmazó termelési papírokat tud kiállítani.</span><span class="sxs-lookup"><span data-stu-id="9aad5-114">Production papers that contain relevant information about processing the jobs can be issued.</span></span> <span data-ttu-id="9aad5-115">A rendszer nyersanyag kitárolással kapcsolatos raktári munkát generál a raktározási folyamatra előkészített cikkeket kapcsán.</span><span class="sxs-lookup"><span data-stu-id="9aad5-115">The warehouse work for raw material picking is generated for the items that are set up for the warehouse process.</span></span>  
4. <span data-ttu-id="9aad5-116">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="9aad5-116">Click the General tab.</span></span>
    * <span data-ttu-id="9aad5-117">Válassza ki, hogy melyik termelési jelentések kerüljenek kinyomtatásra.</span><span class="sxs-lookup"><span data-stu-id="9aad5-117">Select which production reports should be printed.</span></span> <span data-ttu-id="9aad5-118">A Feladatkártya-jelentés minden ütemezett feladat kapcsán kinyomtat egy oldalt, valamint előírja a termelési rendelés feladat szinten történő ütemezését.</span><span class="sxs-lookup"><span data-stu-id="9aad5-118">The Job card report prints a page for each scheduled job and requires the production order to be scheduled at the job level.</span></span> <span data-ttu-id="9aad5-119">A jelentés az ütemezett kezdési és befejezési időponttal, az előállítandó mennyiséggel és a feladatot feldolgozó erőforrással kapcsolatos információkat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="9aad5-119">The report contains information about the scheduled start and end time, the quantity to produce, and which resource processes the job.</span></span> <span data-ttu-id="9aad5-120">Az Útvonal-feladat jelentése ugyanezeket az információkat gyűjti össze egyazon oldalon, de nem nyomtat önálló oldalt minden egyes feladat kapcsán.</span><span class="sxs-lookup"><span data-stu-id="9aad5-120">The Route job report collects the same information on the same page, but does not print a page for each job.</span></span> <span data-ttu-id="9aad5-121">Az Útvonalkártya-jelentés csak a műveletek jeleníti meg, a feladatokat azonban nem.</span><span class="sxs-lookup"><span data-stu-id="9aad5-121">The Route card report only shows the operations but not the jobs.</span></span> <span data-ttu-id="9aad5-122">Ez a jelentés tehát nem igényel feladatütemezést, hanem abban az esetben használható, ha a termelési rendelések ütemezése műveleti szinten történik.</span><span class="sxs-lookup"><span data-stu-id="9aad5-122">Therefore, this report does not require job scheduling, but can be used when production orders are scheduled at the operation level.</span></span>  
5. <span data-ttu-id="9aad5-123">Jelölje be az Útvonalkártya nyomtatása jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="9aad5-123">Click the Print route card checkbox.</span></span>
6. <span data-ttu-id="9aad5-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9aad5-124">Click OK.</span></span>
7. <span data-ttu-id="9aad5-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9aad5-125">Close the page.</span></span>

