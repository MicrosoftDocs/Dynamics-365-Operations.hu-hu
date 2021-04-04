---
title: Rakománysablonok
description: Ez a témakör leírja a rakománysablonok beállításának és új rakományhoz való hozzárendelésének folyamatát.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 80004b5d22e1cf81c1ffa9f74c2c479e1561df72
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247214"
---
# <a name="load-templates"></a><span data-ttu-id="642cf-103">Rakománysablonok</span><span class="sxs-lookup"><span data-stu-id="642cf-103">Load templates</span></span>

<span data-ttu-id="642cf-104">Új rakomány létrehozásakor hozzárendelhet egy rakománysablont.</span><span class="sxs-lookup"><span data-stu-id="642cf-104">When you create a new load, you can assign a load template.</span></span> <span data-ttu-id="642cf-105">A rakománysablon információkat tartalmaz a berendezésekről, valamint az olyan mértékekről, mint a rakomány magassága, szélessége, mélysége és térfogata.</span><span class="sxs-lookup"><span data-stu-id="642cf-105">The load template contains information about equipment, and about measures such as the height, width, depth, and volume of the load.</span></span>

<span data-ttu-id="642cf-106">Ez a témakör leírja a rakománysablonok beállításának és új rakományhoz való hozzárendelésének folyamatát.</span><span class="sxs-lookup"><span data-stu-id="642cf-106">This topic describes how to set up load templates, and how to associate a load template with a new load.</span></span>

## <a name="set-up-a-load-template"></a><span data-ttu-id="642cf-107">Rakománysablon beállítása</span><span class="sxs-lookup"><span data-stu-id="642cf-107">Set up a load template</span></span>

1. <span data-ttu-id="642cf-108">Lépjen a **Szállításkezelés \> Beállítás \> Rakomány-összeállítás \> Rakománysablon** pontra.</span><span class="sxs-lookup"><span data-stu-id="642cf-108">Go to **Transportation management \> Setup \> Load Building \> Load template**.</span></span>
1. <span data-ttu-id="642cf-109">A művelet ablakban válassza az **Új** lehetőséget új sablon hozzáadásához, vagy a **Szerkesztés** lehetőséget egy meglévő sablon szerkesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="642cf-109">On the Action Pane, select **New** to add a new template or **Edit** to edit an existing template.</span></span>
1. <span data-ttu-id="642cf-110">Az új vagy meglévő sablon sorában állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="642cf-110">In the row for the new or existing template, set the following fields:</span></span>

    - <span data-ttu-id="642cf-111">**Rakománysablon azonosítója** – Írja be a rakománysablon egyedi azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="642cf-111">**Load template ID** – Enter a unique identifier (ID) for the load template.</span></span>
    - <span data-ttu-id="642cf-112">**Berendezés** – Válassza ki a rakomány szállításához használandó berendezést.</span><span class="sxs-lookup"><span data-stu-id="642cf-112">**Equipment** – Select the equipment that should be used to ship the load.</span></span>
    - <span data-ttu-id="642cf-113">**Rakomány magassága**, **Rakomány szélessége** és **Rakomány mélysége** – Adja meg a rakomány méreteit.</span><span class="sxs-lookup"><span data-stu-id="642cf-113">**Load height**, **Load width**, and **Load depth** – Enter the dimensions of the load.</span></span>
    - <span data-ttu-id="642cf-114">**Rakomány max. megengedett térfogata** és **Rakomány max. megengedett súlya** – Adja meg a rakomány megengedett legnagyobb térfogatát és súlyát.</span><span class="sxs-lookup"><span data-stu-id="642cf-114">**Max. allowed load volume** and **Max. allowed load weight** – Enter the maximum allowed volume and weight of the load.</span></span>
    - <span data-ttu-id="642cf-115">**Legnagyobb megengedett bruttó tömeg** – Adja meg a rakomány megengedett legnagyobb bruttó tömegét.</span><span class="sxs-lookup"><span data-stu-id="642cf-115">**Maximum allowed gross weight** – Enter the maximum allowed gross weight of the load.</span></span> <span data-ttu-id="642cf-116">A rakomány bruttó tömege magába foglalja a göngyöleg súlyát és a raksúlyt is.</span><span class="sxs-lookup"><span data-stu-id="642cf-116">A load's gross weight includes both its tare weight and its loading weight.</span></span>
    - <span data-ttu-id="642cf-117">**A megengedett fuvardarabok maximális száma** – Adja meg a rakomány által tartalmazható fuvardarabok maximális számát.</span><span class="sxs-lookup"><span data-stu-id="642cf-117">**Maximum number of freight pieces allowed** – Enter the maximum number of freight pieces that the load can contain.</span></span>
    - <span data-ttu-id="642cf-118">**Rakomány halmozása a padlón** – Jelölje be ezt a jelölőnégyzetet a padlóra rakodás használatához.</span><span class="sxs-lookup"><span data-stu-id="642cf-118">**Stack load on floor** – Select this check box to use floor loading.</span></span> <span data-ttu-id="642cf-119">Padlószinti rakodás esetben a dobozok padlótól mennyezetig, faltól falig töltik ki a tárolót, hogy optimálisan kihasználják annak kapacitását.</span><span class="sxs-lookup"><span data-stu-id="642cf-119">In a floor loading scenario, boxes are stacked floor to ceiling and wall to wall inside the container, to maximize capacity.</span></span>

1. <span data-ttu-id="642cf-120">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="642cf-120">On the Action Pane, select **Save**.</span></span>

## <a name="associate-a-load-template-with-a-new-load"></a><span data-ttu-id="642cf-121">Rakománysablon társítása egy új rakományhoz</span><span class="sxs-lookup"><span data-stu-id="642cf-121">Associate a load template with a new load</span></span>

1. <span data-ttu-id="642cf-122">Ugorjon a **Szállításkezelés \> Tervezés \> Rakománytervező munkaterület** elemre.</span><span class="sxs-lookup"><span data-stu-id="642cf-122">Go to **Transportation management \> Planning \> Load planning workbench**.</span></span>
1. <span data-ttu-id="642cf-123">A lap felső részén válasszon az alábbi lapok egyikéből, attól függően, hogy milyen típusú forrásbizonylathoz hoz létre rakományt: **Szállítások**, **Értékesítési sorok**, **Átmozgatási sorok** vagy **Beszerzésirendelés-sorok**.</span><span class="sxs-lookup"><span data-stu-id="642cf-123">In the upper part of the page, select one of the following tabs, depending on the type of source document that you're creating a load for: **Shipments**, **Sales lines**, **Transfer lines**, or **Purchase order lines**.</span></span> 
1. <span data-ttu-id="642cf-124">Válassza ki azt a dokumentumot, amelyhez a rakományt meg szeretné tervezni.</span><span class="sxs-lookup"><span data-stu-id="642cf-124">Select the specific document to plan the load for.</span></span>
1. <span data-ttu-id="642cf-125">A műveleti ablaktáblán a **Kínálat és kereslet** lapon, a **Hozzáadás** csoportban válassza az **Új rakományba** elemet.</span><span class="sxs-lookup"><span data-stu-id="642cf-125">On the Action Pane, on the **Supply and demand** tab, in the **Add** group, select **To new load**.</span></span>
1. <span data-ttu-id="642cf-126">A **Rakománysablon** párbeszédpanelen, a **Rakománysablon azonosítója** mezőben válassza ki az alkalmazni kívánt sablont.</span><span class="sxs-lookup"><span data-stu-id="642cf-126">In the **Load template** dialog box, in the **Load template ID** field, select the template to apply.</span></span>
1. <span data-ttu-id="642cf-127">A sablon alkalmazásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="642cf-127">Select **OK** to apply the template.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]