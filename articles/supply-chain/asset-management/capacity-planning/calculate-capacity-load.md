---
title: Kapacitásterhelés kiszámítása
description: Ez a témakör azt mutatja be, hogyan lehet kiszámítani a kapacitásterhelést az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCapacityLoad, EntAssetWorkOrderCapacityLoadCalculate, EntAssetWorkOrderCapacityLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7a9b235ecedf3399c79ee081a9fe7e2423045fa5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260058"
---
# <a name="calculate-capacity-load"></a><span data-ttu-id="67ebf-103">Kapacitásterhelés kiszámítása</span><span class="sxs-lookup"><span data-stu-id="67ebf-103">Calculate capacity load</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="67ebf-104">Az Eszközkezelés modulban kiszámíthatja a kapacitás terhelését a következőn:</span><span class="sxs-lookup"><span data-stu-id="67ebf-104">In Asset Management, you can calculate capacity load on:</span></span>

- <span data-ttu-id="67ebf-105">karbantartási ütemezési sorok</span><span class="sxs-lookup"><span data-stu-id="67ebf-105">maintenance schedule lines</span></span>  
- <span data-ttu-id="67ebf-106">még nem ütemezett munkarendelések</span><span class="sxs-lookup"><span data-stu-id="67ebf-106">work orders that have not yet been scheduled</span></span>  
- <span data-ttu-id="67ebf-107">ütemezett munkarendelések</span><span class="sxs-lookup"><span data-stu-id="67ebf-107">scheduled work orders</span></span>

<span data-ttu-id="67ebf-108">Ez akkor lehet hasznos, ha egy adott időszakra vonatkozóan szeretne áttekintést kapni a várható kapacitáskihasználásról.</span><span class="sxs-lookup"><span data-stu-id="67ebf-108">This is useful if you want to get an overview of expected capacity load for a specific period.</span></span> <span data-ttu-id="67ebf-109">A kapacitás terhelésének számítása minden tárgyi eszköznél vagy a kiválasztott tárgyi eszközön végezhető el.</span><span class="sxs-lookup"><span data-stu-id="67ebf-109">Calculation of capacity load can be done on all assets or selected assets.</span></span> <span data-ttu-id="67ebf-110">Számításokat végezhet a karbantartási állásidők vagy a munkavégzési gyűjtők esetében is.</span><span class="sxs-lookup"><span data-stu-id="67ebf-110">You can also make a calculation on maintenance downtime activities or work order pools.</span></span>

1. <span data-ttu-id="67ebf-111">Kattintson az **Eszközkezelés** > **Lekérdezések** > **Kapacitásterhelés**, vagy az **Eszközkezelés** > **Közös** > **Munkavégzési gyűjtők** > **Összes munkarendelési gyűjtő** / **Aktív munkarendelés-gyűjtők** > válassza a munkarendelés-gyűjtőt a listában > **Kapacitásterhelés** gomb, vagy **Eszközkezelés** > **Közös** > **Karbantartás miatti üzemkimaradás tevékenységek** > **Minden karbantartás miatti üzemkimaradás tevékenység** / **Aktív karbantartás miatti üzemkimaradás tevékenységek** > a karbantartási tevékenységet kiválasztása a listában > **Kapacitásterhelés** gomb.</span><span class="sxs-lookup"><span data-stu-id="67ebf-111">Click **Asset management** > **Inquiries** > **Capacity load**, or **Asset management** > **Common** > **Work order pools** > **All work order pools** / **Active work order pools** > select work order pool in the list > **Capacity load** button, or **Asset management** > **Common** > **Maintenance downtime activities** > **All maintenance downtime activities** / **Active maintenance downtime activities** > select maintenance activity in the list > **Capacity load** button.</span></span>

2. <span data-ttu-id="67ebf-112">A **Kapacitásterhelés kiszámítása** párbeszédablakban válasszon ki egy időszakot a számításhoz a **Kezdő dátum/idő** és a **Záró dátum/idő** mezőben.</span><span class="sxs-lookup"><span data-stu-id="67ebf-112">In the **Calculate capacity load** dialog, select a period for the calculation in the **Start date/time** and **End date/time** fields.</span></span>

3. <span data-ttu-id="67ebf-113">Ha a számításban szerepeltetni szeretné a karbantartási ütemezés sorait, válassza az „Igen” beállítást a **Karbantartási ütemezés befoglalása** gombbal.</span><span class="sxs-lookup"><span data-stu-id="67ebf-113">Select "Yes" on the **Include maintenance schedule** toggle button if you want to include maintenance schedule lines in the calculation.</span></span>

4. <span data-ttu-id="67ebf-114">Ha a számításban szerepeltetni szeretné a munkarendelés feladatokat, válassza az „Igen” beállítást a **Munkarendelés befoglalása** gombbal.</span><span class="sxs-lookup"><span data-stu-id="67ebf-114">Select "Yes" on the **Include work order** toggle button if you want to include work order jobs in the calculation.</span></span>

5. <span data-ttu-id="67ebf-115">A **Szint** mezőben adhatja meg, hogy a kapacitásterhelési sorok milyen részletesen jelenítse meg a munkavégzési helyszíneket.</span><span class="sxs-lookup"><span data-stu-id="67ebf-115">You can use the **Level** field to indicate how detailed you want the capacity load lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="67ebf-116">Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a karbantartási ütemezés minden munkavégzési helyszínhez tartozó sora és munkarendelése a legfelső szinten jelenik meg, így a sorban szereplő óraszámok hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből.</span><span class="sxs-lookup"><span data-stu-id="67ebf-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines and work orders for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="67ebf-117">Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely a karbantartási ütemezési minden sorát és minden munkarendelést megjelenít az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="67ebf-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines and all work orders on all the functional location levels to which they are related.</span></span>

6. <span data-ttu-id="67ebf-118">Kattintson az **OK** gombra az számítás indításához.</span><span class="sxs-lookup"><span data-stu-id="67ebf-118">Click **OK** to start the calculation.</span></span>

7. <span data-ttu-id="67ebf-119">A **Csoportosítási szempont...** csoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="67ebf-119">In the **Group by...** groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="67ebf-120">A lenti képen a kiválasztott **Csoportosítási szempont** gombokat kék színnel kiemeli a program.</span><span class="sxs-lookup"><span data-stu-id="67ebf-120">In the screenshot below, the selected **Group by** buttons are highlighted in blue color.</span></span> <span data-ttu-id="67ebf-121">A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.</span><span class="sxs-lookup"><span data-stu-id="67ebf-121">Click on a button to activate or deactivate it.</span></span>

    ![1. ábra](media/01-capacity-planning.png)

>[!NOTE]
><span data-ttu-id="67ebf-123">Ha csak az ütemezett munkarendelésekre vonatkozó kapacitástervezésre szeretne koncentrálni, lásd: [Kapacitásterhelés számítása ütemezett munkarendeléseken](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).</span><span class="sxs-lookup"><span data-stu-id="67ebf-123">If you want to focus only on capacity planning regarding scheduled work orders, see [Calculate capacity load on scheduled work orders](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]