---
title: Cikk használati helye
description: Ez a témakör azt mutatja be, hogyan lehet áttekintést kapni arról, hogy egy cikk hol van használva Eszközkezelésben.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: aa1f00ba6b8259221aa2b1ee460be43ee9a311b2
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205471"
---
# <a name="item-where-used"></a><span data-ttu-id="c4585-103">Cikk használati helye</span><span class="sxs-lookup"><span data-stu-id="c4585-103">Item where used</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="c4585-104">Egy adott cikkhez számítást készíthet, amely áttekintést nyújt arról, hogy hol volt használatban a cikk az Eszközkezelésben.</span><span class="sxs-lookup"><span data-stu-id="c4585-104">You can make a calculation for a specific item to get an overview of where in Asset Management the item has been used.</span></span> <span data-ttu-id="c4585-105">Az eredmények megmutatják a kontextust, amelyben a cikk használva volt az élettartama során.</span><span class="sxs-lookup"><span data-stu-id="c4585-105">The results show the context in which the item has been used during its lifetime.</span></span> <span data-ttu-id="c4585-106">A **Hol van az eszköz használva** lapot a fő Eszközkezelés menüből lehet megnyitni, és a következő oldalakról is elérhető:</span><span class="sxs-lookup"><span data-stu-id="c4585-106">The **Item where used** page can be opened from the main Asset Management menu, and it can also be accessed from the following pages:</span></span>

- [<span data-ttu-id="c4585-107">Eszköz DBJ-k</span><span class="sxs-lookup"><span data-stu-id="c4585-107">Asset BOMs</span></span>](../objects/object-BOM.md)

- [<span data-ttu-id="c4585-108">Pótalkatrészek az eszköztípus alapértelmezéseken</span><span class="sxs-lookup"><span data-stu-id="c4585-108">Spare parts on asset type defaults</span></span>](../setup-for-objects/object-types.md#spare-parts-on-the-asset-type-setup)

- [<span data-ttu-id="c4585-109">Karbantartásifeladat-típusok kategóriái és karbantartásifeladat-típusok, karbantartásifeladat-típusok változatai, karbantartási szakmák és karbantartási ellenőrző listák</span><span class="sxs-lookup"><span data-stu-id="c4585-109">Maintenance job type categories and maintenance job types, maintenance job type variants, maintenance job trades, and maintenance checklists</span></span>](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [<span data-ttu-id="c4585-110">Karbantartási előrejelzés</span><span class="sxs-lookup"><span data-stu-id="c4585-110">Maintenance forecast</span></span>](../work-orders/maintenance-forecasts.md)

- [<span data-ttu-id="c4585-111">Beszerzés</span><span class="sxs-lookup"><span data-stu-id="c4585-111">Procurement</span></span>](../work-orders/procurement.md)

- [<span data-ttu-id="c4585-112">Munkarendelés beszerzése</span><span class="sxs-lookup"><span data-stu-id="c4585-112">Work order purchase</span></span>](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a><span data-ttu-id="c4585-113">Cikk használati helye számítás létrehozása</span><span class="sxs-lookup"><span data-stu-id="c4585-113">Make an item-where-used calculation</span></span>

1. <span data-ttu-id="c4585-114">Kattintson az **Eszközkezelés** > **Lekérdezések** > **Cikk használati helye** elemre, és válassza ki a **Cikk használati helye** gombot a fent említett oldalak valamelyikén.</span><span class="sxs-lookup"><span data-stu-id="c4585-114">Click **Asset management** > **Inquiries** > **Item where used**, or select the **Item where used** button on one of the pages mentioned above.</span></span>

2. <span data-ttu-id="c4585-115">A **Cikk használati helye** párbeszédpanelen válassza ki, hogy melyik elemhez szeretné elvégezni a számítást **Cikk száma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c4585-115">In the **Item where used** dialog, select the item for which you want to make the calculation in the **Item number** field.</span></span>

3. <span data-ttu-id="c4585-116">A **Szint** mezőben megadhatja, hogy a cikksorok milyen részletesen jelenítsék meg a munkavégzési helyszíneket.</span><span class="sxs-lookup"><span data-stu-id="c4585-116">You can use the **Level** field to indicate how detailed you want the item lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="c4585-117">Ha például beszúrja az „1ö számot a mezőbe, és a többszintű munkavégzési helyszínszerkezete van, akkor a legfelső szinten jelenik megy egy munkavégzési helyszín minden sora.</span><span class="sxs-lookup"><span data-stu-id="c4585-117">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all item lines for a functional location will be shown on the top level.</span></span> <span data-ttu-id="c4585-118">Ennek megfelelően a sorban szereplő kapcsolat/mennyiség az alacsonyabb szinten található munkavégzési helyszínekről összeadódhat.</span><span class="sxs-lookup"><span data-stu-id="c4585-118">Therefore, relation/quantity on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="c4585-119">Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely minden cikksort megjelenít az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="c4585-119">If you insert the number "0" in the **Level** field, you will see a detailed result showing all item lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="c4585-120">Ha a számításban szerepeltetni szeretné a munkarendelés feladatokat, válassza az „Igen” beállítást a **Belefoglalás** szakaszban.</span><span class="sxs-lookup"><span data-stu-id="c4585-120">In the **Include** section, select "Yes" on the toggle buttons that you want to include in the calculation.</span></span>

5. <span data-ttu-id="c4585-121">Kattintson az **OK** gombra az számítás indításához.</span><span class="sxs-lookup"><span data-stu-id="c4585-121">Click **OK** to start the calculation.</span></span>

6. <span data-ttu-id="c4585-122">A **Cikk használati helye** lapon kattintson a megfelelő **Csoportosítási szempont...** gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="c4585-122">On the **Item where used** tab, select the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="c4585-123">A kiválasztott **Csoportosítási szempont…** ablaktáblacsoport gombjai ki vannak emelve.</span><span class="sxs-lookup"><span data-stu-id="c4585-123">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="c4585-124">A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.</span><span class="sxs-lookup"><span data-stu-id="c4585-124">Click on a button to activate or deactivate it.</span></span>

7. <span data-ttu-id="c4585-125">Ha meg szeretné jeleníteni a cikkel kapcsolatos dimenziókat, kattintson a **Dimenziók megjelenítése** lehetőségre majd válassza ki a megjelenítendő dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="c4585-125">If you want to show dimensions related to the item, click **Display dimensions**, and select the dimensions to be shown.</span></span>

## <a name="example"></a><span data-ttu-id="c4585-126">Példa</span><span class="sxs-lookup"><span data-stu-id="c4585-126">Example</span></span>

<span data-ttu-id="c4585-127">A lenti képernyőfotó egy példát mutat be, amely az „1000” cikkszám használatára vonatkozó Cikk használati helye számítást tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="c4585-127">In the screenshot below, you see an example of an item-where-used calculation for item number "1000".</span></span>

![Cikk használati helye számítás példája](media/12-controlling-and-reporting.png)

