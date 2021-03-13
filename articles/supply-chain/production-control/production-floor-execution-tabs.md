---
title: A termelési üzem végrehajtási felületének tervezése
description: Ez a témakör azt mutatja be, hogyan lehet megtervezni az egyes konfigurációk felhasználói felületének tartalmát.
author: johanhoffmann
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 786ea9a3da98e9f1812b007d4301cb47680e6894
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/28/2021
ms.locfileid: "5077578"
---
# <a name="design-the-production-floor-execution-interface"></a><span data-ttu-id="212ad-103">A termelési üzem végrehajtási felületének tervezése</span><span class="sxs-lookup"><span data-stu-id="212ad-103">Design the production floor execution interface</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="212ad-104">A felhasználói felület tartalmát a termelési üzem végrehajtási felülete által használt minden konfigurációhoz megtervezheti.</span><span class="sxs-lookup"><span data-stu-id="212ad-104">You can design the content of the user interface for each configuration used by the production floor execution interface.</span></span> <span data-ttu-id="212ad-105">Előfordulhat például, hogy egy munkacellában dolgozóknak meg kell tudniuk nyitni a termelési üzemben a feladatra vonatkozó utasításokat, míg egy másik munkacellában nem szükségesek az utasítások.</span><span class="sxs-lookup"><span data-stu-id="212ad-105">For example, workers in one work cell might need to be able to open job instructions on the production floor, while in another work cell, instructions are not needed.</span></span> <span data-ttu-id="212ad-106">Ebben az esetben két konfigurációt kell létrehozni, egyet egy gombbal a dokumentumok mellékleteinek megnyitásához és egyet a gomb nélkül.</span><span class="sxs-lookup"><span data-stu-id="212ad-106">In that case, two configurations should be created, one with a button for opening document attachments and one without this button.</span></span>

## <a name="design-a-tab"></a><span data-ttu-id="212ad-107">Lap tervezése</span><span class="sxs-lookup"><span data-stu-id="212ad-107">Design a tab</span></span>

<span data-ttu-id="212ad-108">A **Termelési üzem végrehajtásának konfigurálása** lapon létrehozhatja és konfigurálhatja a lapokat a műveleti ablak **Lapok tervezése** elemének kiválasztásával.</span><span class="sxs-lookup"><span data-stu-id="212ad-108">On the **Configure production floor execution** page, you can create and configure tabs by selecting **Design tabs** on the Action Pane.</span></span>

<span data-ttu-id="212ad-109">Mindegyik lap négy részre van osztva, ahogy az a következő ábrán látható.</span><span class="sxs-lookup"><span data-stu-id="212ad-109">Each tab is divided into four sections, as shown in the following illustration.</span></span>

<span data-ttu-id="212ad-110">![Lap elrendezése](media/pfe-tab-layout.png "Lap elrendezése")</span><span class="sxs-lookup"><span data-stu-id="212ad-110">![Tab layout](media/pfe-tab-layout.png "Tab layout")</span></span>

<span data-ttu-id="212ad-111">A következő elemek jelennek meg az ábrán:</span><span class="sxs-lookup"><span data-stu-id="212ad-111">The following elements are shown in the illustration:</span></span>

1. <span data-ttu-id="212ad-112">Elsődleges eszköztár</span><span class="sxs-lookup"><span data-stu-id="212ad-112">Primary toolbar</span></span>
1. <span data-ttu-id="212ad-113">Másodlagos eszköztár</span><span class="sxs-lookup"><span data-stu-id="212ad-113">Secondary toolbar</span></span>
1. <span data-ttu-id="212ad-114">Fő nézet</span><span class="sxs-lookup"><span data-stu-id="212ad-114">Main view</span></span>
1. <span data-ttu-id="212ad-115">Részletes nézet</span><span class="sxs-lookup"><span data-stu-id="212ad-115">Detailed view</span></span>

<span data-ttu-id="212ad-116">Új lap létrehozásához és konfigurálásához kövesse ezeket a lépéseket:</span><span class="sxs-lookup"><span data-stu-id="212ad-116">To create and configure a new tab, follow these steps:</span></span>

1. <span data-ttu-id="212ad-117">Ugrás a **Gyártásvezérlés &gt; Beállítás &gt; Gyártási végrehajtás** részre.</span><span class="sxs-lookup"><span data-stu-id="212ad-117">Go to **Production control &gt; Setup &gt; Manufacturing execution**.</span></span>

1. <span data-ttu-id="212ad-118">Válassza a **Lapok tervezése** elemet a műveleti panelen a **Lapok tervezése** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="212ad-118">Select **Design tabs** on the Action Pane to open the **Design tabs** page.</span></span>

    <span data-ttu-id="212ad-119">![A Lapok tervezése oldal](media/pfe-design-tabs.png "A Lapok tervezése oldal")</span><span class="sxs-lookup"><span data-stu-id="212ad-119">![The Design tabs page](media/pfe-design-tabs.png "The Design tabs page")</span></span>

1. <span data-ttu-id="212ad-120">A Művelet panelen válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="212ad-120">Select **New** on the Action Pane.</span></span>

1. <span data-ttu-id="212ad-121">Végezze el a következő beállításokat a lap fejlécében:</span><span class="sxs-lookup"><span data-stu-id="212ad-121">Make the following settings in the header of the page:</span></span>

    - <span data-ttu-id="212ad-122">**Lap neve** – adja meg a lap nevét.</span><span class="sxs-lookup"><span data-stu-id="212ad-122">**Tab name** - Specify a name for the tab.</span></span>
    - <span data-ttu-id="212ad-123">**Fő nézet** – Válasszon a két előre meghatározott munkalista (*Aktív feladatok*, *Összes feladat* vagy *Saját gép*) között.</span><span class="sxs-lookup"><span data-stu-id="212ad-123">**Main view** - Select between the two pre-defined job lists (*Active jobs*, *All jobs*, or *My machine*).</span></span>
    - <span data-ttu-id="212ad-124">**Részletes nézet** – válassza ki az üres értéket vagy a **feladat adatait**.</span><span class="sxs-lookup"><span data-stu-id="212ad-124">**Details view** - Select between a blank value or **Job details**.</span></span> <span data-ttu-id="212ad-125">Ha az üres értéket választja, akkor a lapon nem jelenik meg részletes nézet. Ha a **Feladat adatait** választja, akkor a részletes nézet a főnézetben a feladatlistában kiválasztott feladat részletes leírását tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="212ad-125">If you select the blank value, there will be no detailed view in the tab. If you select **Job details**, the detailed view will contain a detailed description of the job selected in the job list in the main view.</span></span>

1. <span data-ttu-id="212ad-126">Az **Elsődleges eszköztár** szakaszban válassza ki, hogy mely gombokat kell elérhetővé tenni az elsődleges eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="212ad-126">In the **Primary toolbar** section, choose which buttons should be available in the primary toolbar.</span></span> <span data-ttu-id="212ad-127">A **Választható műveletek** oszlop felsorolja az összes olyan gombot, amelyet fel lehet venni.</span><span class="sxs-lookup"><span data-stu-id="212ad-127">The **Available actions** column shows a list of all the buttons that can be added.</span></span> <span data-ttu-id="212ad-128">A **Kiválasztott műveletek** oszlopai az aktuális konfigurációban szereplő összes gomb listáját jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="212ad-128">The **Selected actions** columns shows a list of all the buttons that are included in the current configuration.</span></span> <span data-ttu-id="212ad-129">Az oszlopok között látható gombokkal lehet áthelyezni a kiválasztott elemeket a szükséges oszlopok között.</span><span class="sxs-lookup"><span data-stu-id="212ad-129">Use the buttons between the columns to move selected items between the columns as needed.</span></span> <span data-ttu-id="212ad-130">A **Kiválasztott műveletek** oszlop melletti fel és le gombbal lehet szabályozni, hogy milyen sorrendben jelenjenek meg a gombok a felhasználói felületen.</span><span class="sxs-lookup"><span data-stu-id="212ad-130">Use the up and down buttons next to the **Selected actions** column to control the order in which the buttons are presented in the user interface.</span></span>

1. <span data-ttu-id="212ad-131">A **Másodlagos** **eszköztár** szakaszban válassza ki, hogy mely gombokat kell elérhetővé tenni a másodlagos eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="212ad-131">In the **Secondary** **toolbar** section, choose which buttons should be available in the secondary toolbar.</span></span> <span data-ttu-id="212ad-132">A **Választható műveletek** oszlop felsorolja az összes olyan gombot, amelyet fel lehet venni.</span><span class="sxs-lookup"><span data-stu-id="212ad-132">The **Available actions** column shows a list of all the buttons that can be added.</span></span> <span data-ttu-id="212ad-133">A **Kiválasztott műveletek** oszlopai az aktuális konfigurációban szereplő összes gomb listáját jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="212ad-133">The **Selected actions** columns shows a list of all the buttons that are included in the current configuration.</span></span> <span data-ttu-id="212ad-134">Az oszlopok között látható gombokkal lehet áthelyezni a kiválasztott elemeket a szükséges oszlopok között.</span><span class="sxs-lookup"><span data-stu-id="212ad-134">Use the buttons between the columns to move selected items between the columns as needed.</span></span> <span data-ttu-id="212ad-135">A **Kiválasztott műveletek** oszlop melletti fel és le gombbal lehet szabályozni, hogy milyen sorrendben jelenjenek meg a gombok a felhasználói felületen.</span><span class="sxs-lookup"><span data-stu-id="212ad-135">Use the up and down buttons next to the **Selected actions** column to control the order in which the buttons are presented in the user interface.</span></span>

## <a name="associate-a-tab-with-a-configuration"></a><span data-ttu-id="212ad-136">Lap társítása konfigurációval</span><span class="sxs-lookup"><span data-stu-id="212ad-136">Associate a tab with a configuration</span></span>

<span data-ttu-id="212ad-137">Miután megtervezte az összes szükséges lapot, hozzárendelheti őket egy konfigurációhoz.</span><span class="sxs-lookup"><span data-stu-id="212ad-137">After you designed all the tabs you need, you can associate them with a configuration.</span></span>

1. <span data-ttu-id="212ad-138">Lépjen a **Gyártásvezérlés &gt; Beállítás &gt; Termelési üzem végrehajtásának konfigurálása** részre.</span><span class="sxs-lookup"><span data-stu-id="212ad-138">Go to **Production control &gt; Setup &gt; Configure production floor execution**.</span></span>

    <span data-ttu-id="212ad-139">![Termelési üzem végrehajtásának konfigurálása](media/pfe-config-prod-floor-execution.png "Termelési üzem végrehajtásának konfigurálása")</span><span class="sxs-lookup"><span data-stu-id="212ad-139">![Configure production floor execution](media/pfe-config-prod-floor-execution.png "Configure production floor execution")</span></span>

1. <span data-ttu-id="212ad-140">A **Lapválasztás** gyorslapon válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="212ad-140">On the **Tab selection** FastTab, select **Add**.</span></span>

1. <span data-ttu-id="212ad-141">A program új sort ad hozzá a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="212ad-141">A new row is added to the grid.</span></span> <span data-ttu-id="212ad-142">Ehhez az új sorhoz válassza ki a konfigurációhoz hozzáadni kívánt lap nevét.</span><span class="sxs-lookup"><span data-stu-id="212ad-142">For this new row, select the name of a tab that you want to add to the configuration.</span></span>

1. <span data-ttu-id="212ad-143">Szükség esetén folytassa a további lapok hozzáadását.</span><span class="sxs-lookup"><span data-stu-id="212ad-143">Continue to add additional tabs as needed.</span></span>

1. <span data-ttu-id="212ad-144">Az eszköztáron található **Mozgatás felfelé** és **Mozgatás lefelé** gombokkal igény szerint átrendezheti a lapokat.</span><span class="sxs-lookup"><span data-stu-id="212ad-144">Use the **Move up** and **Move down** buttons on the toolbar to arrange the tabs as needed.</span></span> <span data-ttu-id="212ad-145">A lapok balról jobbra haladva jelennek meg a fenti képernyőképen látható sorrendben (a felső lap a bal oldalon látható).</span><span class="sxs-lookup"><span data-stu-id="212ad-145">The tabs will be displayed from left to right in the order shown in the above screenshot (the tab at the top is shown on the left).</span></span>
