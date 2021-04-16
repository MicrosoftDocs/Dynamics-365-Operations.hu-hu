---
title: Igény szerinti szinkronizálás a Supply Chain Management árképzés motorral
description: Ez a témakör azt mutatja be, hogyan kell használni a Microsoft Dynamics 365 Supply Chain Management árképzési motorját a Dynamics 365 Sales alkalmazásból.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: bf4154816f01040a236dde77b92ee69396158614
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750764"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a><span data-ttu-id="06d9f-103">Igény szerinti szinkronizálás a Supply Chain Management árképzés motorral</span><span class="sxs-lookup"><span data-stu-id="06d9f-103">Sync on-demand with the Supply Chain Management pricing engine</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="06d9f-104">A Microsoft Dynamics 365 Supply Chain Management tartalmaz egy árképzési motort, amely a kereskedelmi megállapodásokat, árlistákat, törzsvásárlói programokat, promóciókat és kedvezményeket kezel.</span><span class="sxs-lookup"><span data-stu-id="06d9f-104">Microsoft Dynamics 365 Supply Chain Management includes a pricing engine that handles trade agreements, price lists, customer loyalty programs, promotions, and discounts.</span></span> <span data-ttu-id="06d9f-105">Az árképzési motor összetett szabályokat használ egy adott árajánlat vagy rendelés legjobb árának megállapításához.</span><span class="sxs-lookup"><span data-stu-id="06d9f-105">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span> <span data-ttu-id="06d9f-106">Kettős írás használata esetén a Dynamics 365 Sales ajánlati és rendelési oldalain a Dynamics 365 Supply Chain Management alkalmazásból származó statikus árképzési vagy árképzési motor használható.</span><span class="sxs-lookup"><span data-stu-id="06d9f-106">When you use dual-write, you use either static pricing or the pricing engine from Dynamics 365 Supply Chain Management on the Quote and Order pages in Dynamics 365 Sales.</span></span>

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a><span data-ttu-id="06d9f-107">A Supply Chain Management árképzési motorjának használata a Sales alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="06d9f-107">Use the pricing engine from Supply Chain Management in Sales</span></span>

1. <span data-ttu-id="06d9f-108">Az Sales alkalmazásban területen nyissa meg a **Sales \> Rendelések** elemet.</span><span class="sxs-lookup"><span data-stu-id="06d9f-108">In Sales, go to **Sales \> Orders**.</span></span>
2. <span data-ttu-id="06d9f-109">Válassza az **Új** lehetőséget egy új rendelés létrehozásához vagy válasszon egy meglévő rendelést a **Saját rendelések** listából.</span><span class="sxs-lookup"><span data-stu-id="06d9f-109">Select **New** to create a new order, or select an existing order in the **My Orders** list.</span></span>
3. <span data-ttu-id="06d9f-110">Adjon hozzá egy új rendelési sort.</span><span class="sxs-lookup"><span data-stu-id="06d9f-110">Add a new order line.</span></span>
4. <span data-ttu-id="06d9f-111">Ha új rendelést hoz létre, akkor a műveleti ablaktáblán válassza a **Rendelés árazása** elemet.</span><span class="sxs-lookup"><span data-stu-id="06d9f-111">If you're creating a new order, select **Price Order** on the Action Pane.</span></span> <span data-ttu-id="06d9f-112">Ha egy meglévő rendelést frissít e, akkor a műveleti ablaktáblán válassza az **Újraszámítás** elemet.</span><span class="sxs-lookup"><span data-stu-id="06d9f-112">If you're updating an existing order, select **Recalculate** on the Action Pane.</span></span>

    <span data-ttu-id="06d9f-113">A program automatikusan kitölti a következő oszlopokat:</span><span class="sxs-lookup"><span data-stu-id="06d9f-113">The following columns are automatically filled in:</span></span>

    + <span data-ttu-id="06d9f-114">Részletes összeg</span><span class="sxs-lookup"><span data-stu-id="06d9f-114">Detail Amount</span></span>
    + <span data-ttu-id="06d9f-115">Engedmény (%)</span><span class="sxs-lookup"><span data-stu-id="06d9f-115">Discount %</span></span>
    + <span data-ttu-id="06d9f-116">Kedvezmény</span><span class="sxs-lookup"><span data-stu-id="06d9f-116">Discount</span></span>
    + <span data-ttu-id="06d9f-117">Szállítás előtti összeg</span><span class="sxs-lookup"><span data-stu-id="06d9f-117">Pre-Freight Amount</span></span>
    + <span data-ttu-id="06d9f-118">Szállítási összeg</span><span class="sxs-lookup"><span data-stu-id="06d9f-118">Freight Amount</span></span>
    + <span data-ttu-id="06d9f-119">Adó összesen</span><span class="sxs-lookup"><span data-stu-id="06d9f-119">Total Tax</span></span>
    + <span data-ttu-id="06d9f-120">Teljes összeg</span><span class="sxs-lookup"><span data-stu-id="06d9f-120">Total Amount</span></span>
    
5. <span data-ttu-id="06d9f-121">Annak biztosítására, hogy a rendszer a kereskedelmi és értékesítési szerződéseket figyelembe vegye az ár kiszámításához:</span><span class="sxs-lookup"><span data-stu-id="06d9f-121">To ensure that the system considers trade and sales agreements to calculate the price:</span></span>
    1. <span data-ttu-id="06d9f-122">Navigáljon a Supply Chain Management környezetébe.</span><span class="sxs-lookup"><span data-stu-id="06d9f-122">Navigate to your Supply Chain Management environment.</span></span>
    2. <span data-ttu-id="06d9f-123">Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.</span><span class="sxs-lookup"><span data-stu-id="06d9f-123">Navigate to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
    3. <span data-ttu-id="06d9f-124">Válassza ki az **Árak** lapot az oldalsó navigációs sávon.</span><span class="sxs-lookup"><span data-stu-id="06d9f-124">Select the **Prices** tab in the side navigation bar.</span></span>
    4. <span data-ttu-id="06d9f-125">A **Kereskedelmi szerződés értékelése** gyorslapon törölje a **Manuális bejegyzés** beállítás jelölését.</span><span class="sxs-lookup"><span data-stu-id="06d9f-125">Under the **Trade agreement evaluation** fastab, uncheck the **Manual entry** option.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="06d9f-126">Hogyan működik?</span><span class="sxs-lookup"><span data-stu-id="06d9f-126">How it works</span></span>

<span data-ttu-id="06d9f-127">Amikor kiválasztja a **Rendelés árazása** lehetőséget a Sales alkalmazásban az **Összeg** funkció az **Értékesítési rendelés \> Nézet** lapon a Supply Chain Management alkalmazásban meg lesz hívva a társított rendelésért..</span><span class="sxs-lookup"><span data-stu-id="06d9f-127">When you select **Price Order** in Sales, the **Totals** function on the **Sales Order \> View** tab in Supply Chain Management is called for the associated sales order.</span></span> <span data-ttu-id="06d9f-128">A rendelés teljes összege az Sales alkalmazásból lesz felhasználva a Supply Chain Management megfelelő oszlopainak kitöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="06d9f-128">The values in the order total in Sales are used to fill in the corresponding columns in Supply Chain Management.</span></span>

<span data-ttu-id="06d9f-129">Amikor az értékesítési rendelés összesítése a Supply Chain Management alkalmazásban van kiszámítva a számítás a vevőre vonatkozó meglévő kereskedelmi megállapodásokat és értékesítési szerződéseket, valamint az értékesítési rendelésben felsorolt termékeket értékeli.</span><span class="sxs-lookup"><span data-stu-id="06d9f-129">When the sales order total is calculated in Supply Chain Management, the calculation evaluates the existing trade agreements and sales agreements for the customer and the products that are listed in the sales order.</span></span> <span data-ttu-id="06d9f-130">Ezek az adatok lesznek felhasználva a végösszeg számításához.</span><span class="sxs-lookup"><span data-stu-id="06d9f-130">This information is used to calculate the totals.</span></span> <span data-ttu-id="06d9f-131">Ha a **Rendelés árazása** van kiválasztva, akkor a Sales automatikusan tükrözi a Supply Chain Management alkalmazásban elvégzett összes beállítást.</span><span class="sxs-lookup"><span data-stu-id="06d9f-131">When **Price Order** is selected, Sales automatically reflects all the setup that has been done in Supply Chain Management.</span></span>

## <a name="limitations"></a><span data-ttu-id="06d9f-132">Korlátozások</span><span class="sxs-lookup"><span data-stu-id="06d9f-132">Limitations</span></span>

<span data-ttu-id="06d9f-133">Amikor az Értékesítés oszlopai ki vannak töltve, a következő korlátozások érvényesek:</span><span class="sxs-lookup"><span data-stu-id="06d9f-133">When the columns in Sales are filled in, the following limitations apply:</span></span>

+ <span data-ttu-id="06d9f-134">A Supply Chain Management alkalmazásben végzett költség-és költség-felosztási beállítások nem lesznek másolva a Sales alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="06d9f-134">The setup of charges and charge allocations in Supply Chain Management isn't replicated in Sales.</span></span>
+ <span data-ttu-id="06d9f-135">Az árképzés nem veszi figyelembe a különleges kiskereskedelmi árazást, ami a Supply Chain Management értékesítési rendelés sora oldalán van meghatározva a **Kiskereskedelmi csatorna** oszlopban.</span><span class="sxs-lookup"><span data-stu-id="06d9f-135">Pricing doesn't consider special retail pricing that is specified in the **Retail Channel** column on the sales order line page in Supply Chain Management.</span></span>
+ <span data-ttu-id="06d9f-136">A rendszer nem veszi figyelembe a Supply Chain Management **Promóciós engedmény kezelése** részében meghatározott engedményeket.</span><span class="sxs-lookup"><span data-stu-id="06d9f-136">Discounts that are defined in the **Trade Allowance Management** section of Supply Chain Management aren't considered.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]