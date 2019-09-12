---
title: Cikk használati helye
description: Ez a témakör azt mutatja be, hogyan lehet áttekintést kapni arról, hogy egy cikk hol van használva Eszközkezelésben.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 84ab803aedf5b803b6c5f39ff1907726335cb45d
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918326"
---
# <a name="item-where-used"></a><span data-ttu-id="42c00-103">Cikk használati helye</span><span class="sxs-lookup"><span data-stu-id="42c00-103">Item where used</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="42c00-104">Egy adott cikkhez számítást készíthet, amely áttekintést nyújt arról, hogy hol volt használatban a cikk az Eszközkezelésben.</span><span class="sxs-lookup"><span data-stu-id="42c00-104">You can make a calculation for a specific item to get an overview of where in Asset Management the item has been used.</span></span> <span data-ttu-id="42c00-105">Az eredmények megmutatják a kontextust, amelyben a cikk használva volt az élettartama során.</span><span class="sxs-lookup"><span data-stu-id="42c00-105">The results show the context in which the item has been used during its lifetime.</span></span> <span data-ttu-id="42c00-106">A **Hol van az eszköz használva** lapot a fő Eszközkezelés menüből lehet megnyitni, és a következő oldalakról is elérhető:</span><span class="sxs-lookup"><span data-stu-id="42c00-106">The **Item where used** page can be opened from the main Asset management menu, and it can also be accessed from the following pages:</span></span>

[<span data-ttu-id="42c00-107">Eszköz DBJ</span><span class="sxs-lookup"><span data-stu-id="42c00-107">Asset BOM</span></span>](../objects/object-BOM.md)

[<span data-ttu-id="42c00-108">Pótalkatrészek az eszköztípus alapértelmezéseken</span><span class="sxs-lookup"><span data-stu-id="42c00-108">Spare parts on asset type defaults</span></span>](../setup-for-objects/object-types.md)

[<span data-ttu-id="42c00-109">A karbantartási feladattípus alapértelmezett előrejelzések cikkekelőrejelzései</span><span class="sxs-lookup"><span data-stu-id="42c00-109">Item forecast on Maintenance job type defaults forecast</span></span>](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

[<span data-ttu-id="42c00-110">Munkarendelés karbantartási előrejelzése</span><span class="sxs-lookup"><span data-stu-id="42c00-110">Work order maintenance forecast</span></span>](../work-orders/maintenance-forecasts.md)

[<span data-ttu-id="42c00-111">Munkarendelés beszerzési igénylése</span><span class="sxs-lookup"><span data-stu-id="42c00-111">Work order purchase requisition</span></span>](../work-orders/procurement.md)

[<span data-ttu-id="42c00-112">Munkarendelés beszerzése</span><span class="sxs-lookup"><span data-stu-id="42c00-112">Work order purchase</span></span>](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a><span data-ttu-id="42c00-113">Cikk használati helye számítás létrehozása</span><span class="sxs-lookup"><span data-stu-id="42c00-113">Make an item-where-used calculation</span></span>

1. <span data-ttu-id="42c00-114">Kattintson az **Eszközkezelés** > **Lekérdezések** > **Cikk használati helye** elemre, és válassza ki a **Cikk használati helye** gombot a fent említett oldalak valamelyikén.</span><span class="sxs-lookup"><span data-stu-id="42c00-114">Click **Asset management** > **Inquiries** > **Item where used**, or select the **Item where used** button on one of the pages mentioned above.</span></span>

2. <span data-ttu-id="42c00-115">A **Cikk használati helye** párbeszédpanelen válassza ki, hogy melyik elemhez szeretné elvégezni a számítást **Cikk száma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="42c00-115">In the **Item where used** dialog, select the item for which you want to make the calculation in the **Item number** field.</span></span>

3. <span data-ttu-id="42c00-116">A **Szint** mezőben megadhatja, hogy a cikksorok milyen részletesen jelenítsék meg a munkavégzési helyszíneket.</span><span class="sxs-lookup"><span data-stu-id="42c00-116">You can use the **Level** field to indicate how detailed you want the item lines to be regarding functional locations.</span></span> <span data-ttu-id="42c00-117">Ha például beszúrja az „1ö számot a mezőbe, és a többszintű munkavégzési helyszínszerkezete van, akkor a legfelső szinten jelenik megy egy munkavégzési helyszín minden sora.</span><span class="sxs-lookup"><span data-stu-id="42c00-117">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all item lines for a functional location will be shown on the top level.</span></span> <span data-ttu-id="42c00-118">Ennek megfelelően a sorban szereplő kapcsolat/mennyiség az alacsonyabb szinten található munkavégzési helyszínekről összeadódhat.</span><span class="sxs-lookup"><span data-stu-id="42c00-118">Therefore, relation/quantity on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="42c00-119">Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely minden cikksort megjelenít az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="42c00-119">If you insert the number "0" in the **Level** field, you will see a detailed result showing all item lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="42c00-120">Ha a számításban szerepeltetni szeretné a munkarendelés feladatokat, válassza az „Igen” beállítást a **Belefoglalás** szakaszban.</span><span class="sxs-lookup"><span data-stu-id="42c00-120">In the **Include** section, select "Yes" on the toggle buttons that you want to include in the calculation.</span></span>

5. <span data-ttu-id="42c00-121">Kattintson az **OK** gombra az számítás indításához.</span><span class="sxs-lookup"><span data-stu-id="42c00-121">Click **OK** to start the calculation.</span></span>

6. <span data-ttu-id="42c00-122">A **Cikk használati helye** lapon a **Csoportosítási szempont...** műveleti ablaktáblacsoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="42c00-122">On the **Item where used** tab > **Group by...** action pane groups, select the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="42c00-123">A kiválasztott műveleti ablaktábla gombjai ki vannak emelve.</span><span class="sxs-lookup"><span data-stu-id="42c00-123">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="42c00-124">A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.</span><span class="sxs-lookup"><span data-stu-id="42c00-124">Click on a button to activate or deactivate it.</span></span>

7. <span data-ttu-id="42c00-125">Ha meg szeretné jeleníteni a cikkel kapcsolatos dimenziókat, kattintson a **Dimenziók megjelenítése** lehetőségre majd válassza ki a megjelenítendő dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="42c00-125">If you want to show dimensions related to the item, click **Display dimensions**, and select the dimensions to be shown.</span></span>

<span data-ttu-id="42c00-126">A lenti ábra egy példát mutat be, amely az „1000” cikkszám használatára vonatkozó Cikk használati helye számítást tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="42c00-126">In the figure below, you see an example of an item-where-used calculation for item number "1000".</span></span>

![1. ábra](media/12-controlling-and-reporting.png)

