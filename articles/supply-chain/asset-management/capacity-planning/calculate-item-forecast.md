---
title: Cikkelőrejelzés kiszámítása
description: Ez a témakör azt mutatja be, hogyan lehet kiszámítani a cikkelőrejelzést az Eszközkezelés modulban.
author: johanhoffmann
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetItemForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9392245abe5858b03b8324dcb471f5652aed7cd6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813893"
---
# <a name="calculate-item-forecast"></a><span data-ttu-id="69b33-103">Cikkelőrejelzés kiszámítása</span><span class="sxs-lookup"><span data-stu-id="69b33-103">Calculate item forecast</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="69b33-104">Csakúgy, mint a kapacitásterhelési számításoknál, amelyek leírása az előző részben szerepel, a cikkek előrejelzési számításait is megteheti:</span><span class="sxs-lookup"><span data-stu-id="69b33-104">Just as you can make capacity load calculations, which are described in the previous section, you can also make item forecast calculations on:</span></span>

- <span data-ttu-id="69b33-105">karbantartási ütemezési sorok</span><span class="sxs-lookup"><span data-stu-id="69b33-105">maintenance schedule lines</span></span>  
- <span data-ttu-id="69b33-106">még nem ütemezett munkarendelések</span><span class="sxs-lookup"><span data-stu-id="69b33-106">work orders that have not yet been scheduled</span></span>  
- <span data-ttu-id="69b33-107">ütemezett munkarendelések</span><span class="sxs-lookup"><span data-stu-id="69b33-107">scheduled work orders</span></span>

<span data-ttu-id="69b33-108">Ez akkor lehet hasznos, ha egy adott időszakra vonatkozóan áttekintést szeretne kapni a várható cikkfelhasználásról (pótalkatrészek, valamint a munkarendelések befejezéséhez szükséges egyéb cikkek).</span><span class="sxs-lookup"><span data-stu-id="69b33-108">This is useful if you want to get an overview of expected item consumption (spare parts as well as other items required for completing work orders) for a specific period.</span></span> <span data-ttu-id="69b33-109">A kapacitás terhelésének számítása a cikkelőrejelzéseknél minden eszközön vagy a kiválasztott eszközökön végezhető el.</span><span class="sxs-lookup"><span data-stu-id="69b33-109">Calculation of item forecast can be done on all assets or selected assets.</span></span> <span data-ttu-id="69b33-110">Számítás végezhető a karbantartási állásidővel kapcsolatos tevékenységekről (**Összes karbantartási állásidő tevékenység** vagy **Aktív karbantartási állásidő tevékenységek**), vagy egy munkarendelési gyűjtőkről (**Minden munkarendelési gyűjtő** vagy **Aktív munkavégzési gyűjtők**).</span><span class="sxs-lookup"><span data-stu-id="69b33-110">You can also make a calculation on a maintenance downtime activity (**All maintenance downtime activities** or **Active maintenance downtime activities**), or on a work order pool (**All work order pools** or **Active work order pools**).</span></span>

1. <span data-ttu-id="69b33-111">Kattintson az **Eszközkezelés** > **Lekérdezések** > **Cikkelőrejelzés**, vagy az **Eszközkezelés** > **Közös** > **Munkavégzési gyűjtők** > **Összes munkarendelési gyűjtő** / **Aktív munkarendelés-gyűjtők** > válassza a munkarendelés-gyűjtőt a listában > **Cikkelőrejelzés** gomb, vagy **Eszközkezelés** > **Közös** > **Karbantartás miatti üzemkimaradás tevékenységek** > **Minden karbantartás miatti üzemkimaradás tevékenység** / **Aktív karbantartás miatti üzemkimaradás tevékenységek** > a karbantartás miatti üzemkimaradás tevékenység kiválasztása a listában > **Cikkelőrejelzés** gomb.</span><span class="sxs-lookup"><span data-stu-id="69b33-111">Click **Asset management** > **Inquiries** > **Item forecast**, or **Asset management** > **Common** > **Work order pools** > **All work order pools** / **Active work order pools** > select work order pool in the list > **Item forecast** button, or **Asset management** > **Common** > **Maintenance downtime activities** > **All maintenance downtime activities** / **Active maintenance downtime activities** > select maintenance downtime activity in the list > **Item forecast** button.</span></span>

2. <span data-ttu-id="69b33-112">A **Cikkelőrejelzés kiszámítása** párbeszédablakban válasszon ki egy időszakot a számításhoz a **Kezdő dátum/idő** és a **Záró dátum/idő** mezőben.</span><span class="sxs-lookup"><span data-stu-id="69b33-112">In the **Calculate item forecast** dialog, select a period for the calculation in the **Start date/time** and **End date/time** fields.</span></span>

3. <span data-ttu-id="69b33-113">Ha az előrejelzési számításban szerepeltetni szeretné a karbantartási ütemezés sorait, válassza az „Igen” beállítást a **Karbantartási ütemezés befoglalása** gombbal.</span><span class="sxs-lookup"><span data-stu-id="69b33-113">Select "Yes" on the **Include maintenance schedule** toggle button if you want to include maintenance schedule lines in the forecast calculation.</span></span>

4. <span data-ttu-id="69b33-114">Ha az előrejelzési számításban szerepeltetni szeretné a munkarendelés feladatokat, válassza az „Igen” beállítást a **Munkarendelés befoglalása** gombbal.</span><span class="sxs-lookup"><span data-stu-id="69b33-114">Select "Yes" on the **Include work order** toggle button if you want to include work order jobs in the forecast calculation.</span></span>

5. <span data-ttu-id="69b33-115">A **Szint** mezőben adhatja meg, hogy a cikkelőrejelzési sorok milyen részletesen jelenítse meg a munkavégzési helyszíneket.</span><span class="sxs-lookup"><span data-stu-id="69b33-115">You can use the **Level** field to indicate how detailed you want the item forecast lines to be regarding functional locations.</span></span> 

      <span data-ttu-id="69b33-116">Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a karbantartási ütemezés minden munkavégzési helyszínhez tartozó sora és munkarendelése a legfelső szinten jelenik meg, így a sorban szereplő óraszámok hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből.</span><span class="sxs-lookup"><span data-stu-id="69b33-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines and work orders for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
  
      <span data-ttu-id="69b33-117">Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely a karbantartási ütemezési minden sorát és minden munkarendelést megjelenít az összes olyan munkavégzési helyszín szintnél, amelyhez a sor kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="69b33-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines and all work orders on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="69b33-118">Kattintson az **OK** gombra az számítás indításához.</span><span class="sxs-lookup"><span data-stu-id="69b33-118">Click **OK** to start the calculation.</span></span>

7. <span data-ttu-id="69b33-119">A **Csoportosítási szempont...** csoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="69b33-119">In the **Group by...** groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="69b33-120">A lenti képen a kiválasztott **Csoportosítási szempont** gombokat kék színnel kiemeli a program.</span><span class="sxs-lookup"><span data-stu-id="69b33-120">In the screenshot below, the selected **Group by** buttons are highlighted in blue color.</span></span> <span data-ttu-id="69b33-121">A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.</span><span class="sxs-lookup"><span data-stu-id="69b33-121">Click on a button to activate or deactivate it.</span></span>

8. <span data-ttu-id="69b33-122">Kattintson a **Dimenziók megjelenítése** gombra, ha meg szeretné tekinteni a cikkekhez kapcsolódó terméket, tárolóhelyet vagy nyomon követési dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="69b33-122">Click the **Display dimensions** button if you want to see the product, storage, or tracking dimensions related to the items.</span></span> <span data-ttu-id="69b33-123">Jelölje be a megfelelő jelölőmezőket, és kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="69b33-123">Select the relevant check boxes, and click **OK**.</span></span>

![1. ábra](media/02-capacity-planning.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]