---
title: Készlet rendelkezésre állása kettős írásban
description: Ez a témakör a készlet rendelkezésre állásának ellenőrzéséről a kettős írásban tartalmaz tájékoztatást.
author: RamaKrishnamoorthy
ms.date: 05/26/2020
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
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 0fded78134b1427e6faea9656e1d3b02b467ae91
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193407"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="fdfa3-103">Készlet rendelkezésre állása kettős írásban</span><span class="sxs-lookup"><span data-stu-id="fdfa3-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fdfa3-104">A készlet elérhetőségét használva ellenőrizheti a készletet, mielőtt terméket ad hozzá az **Ajánlatok**, **Rendelések** vagy **Számlák** oldalakhoz a Microsoft Dynamics 365 Sales alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations**, **Orders**, or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="fdfa3-105">Például a készlet ellenőrzése és a teljesítés dátuma egy kulcsfeladat a [potenciális vevők készpénzre váltása](dual-write-prospect-to-cash.md) folyamatban.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="fdfa3-106">Ha nincs elég készlete, megbecsülheti a várható szállítási dátumot az előrejelzett készletbevételezés és -kiadás alapján.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="fdfa3-107">Megtekintheti a termék ígérethez rendelkezésre áll információit is, ahol megtalálhatja az ígért mennyiséget az előre meghatározott időkorláton belül.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="fdfa3-108">Aktuális készlet</span><span class="sxs-lookup"><span data-stu-id="fdfa3-108">On-hand inventory</span></span>

<span data-ttu-id="fdfa3-109">A Dynamics 365 Sales alkalmazásban egy új **Rendelkezésre álló készlet** gomb lett hozzáadva az **Ajánlatok**, **Rendelések** és **Számlák** űrlapjainak fejlécében.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="fdfa3-110">Amikor a gombra kattint, megjelenik egy párbeszédpanel, ahol megadhatja azt a vállalatot és terméket, amelynek az aktuális készletét ellenőrizni szeretné.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="fdfa3-111">Ez a párbeszédpanel ugyanazokat az adatokat jeleníti meg, mint az [Aktuális készlet](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="fdfa3-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="fdfa3-112">A párbeszédpanel a Dynamics 365 Supply Chain Management készletadatait jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="fdfa3-113">Ez az információ az alábbi mennyiségeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="fdfa3-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="fdfa3-114">Aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="fdfa3-114">On-hand quantity</span></span>
- <span data-ttu-id="fdfa3-115">Lefoglalt aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="fdfa3-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="fdfa3-116">Elérhető aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="fdfa3-116">Available on-hand quantity</span></span>
- <span data-ttu-id="fdfa3-117">Megrendelt mennyiség</span><span class="sxs-lookup"><span data-stu-id="fdfa3-117">Ordered quantity</span></span>
- <span data-ttu-id="fdfa3-118">Rendelésben lévő mennyiség</span><span class="sxs-lookup"><span data-stu-id="fdfa3-118">On-order quantity</span></span>
- <span data-ttu-id="fdfa3-119">Lefoglalt rendelt mennyiség</span><span class="sxs-lookup"><span data-stu-id="fdfa3-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="fdfa3-120">Teljes elérhető mennyiség</span><span class="sxs-lookup"><span data-stu-id="fdfa3-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="fdfa3-121">Információk az ígérethez rendelkezésre álló készletről</span><span class="sxs-lookup"><span data-stu-id="fdfa3-121">ATP information</span></span>

<span data-ttu-id="fdfa3-122">A Sales alkalmazásban az **Árajánlatok** , **Rendelések** és **Számlák** oldalain egy új, **ATP-információ** gombbal bővült a cikkek sora.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="fdfa3-123">Amikor ezt a gombot választja, megjelenik egy párbeszédpanel, amelyen megadhatja a vállalatot, terméket, helyet, készletraktárat és rendelési mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="fdfa3-124">Ez a párbeszédpanel ugyanolyan beállításokat tartalmaz, mint a [Rendelési ígéret](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="fdfa3-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="fdfa3-125">A párbeszédpanel a Supply Chain Management „ígérethez rendelkezésre áll” adatait adja vissza.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="fdfa3-126">Ez az információ az alábbi mennyiségeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="fdfa3-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="fdfa3-127">Ígérethez rendelkezésre álló mennyiség</span><span class="sxs-lookup"><span data-stu-id="fdfa3-127">ATP quantity</span></span>
- <span data-ttu-id="fdfa3-128">Bevételezés mennyisége</span><span class="sxs-lookup"><span data-stu-id="fdfa3-128">Receipt quantity</span></span>
- <span data-ttu-id="fdfa3-129">Kiadás mennyisége</span><span class="sxs-lookup"><span data-stu-id="fdfa3-129">Issue quantity</span></span>
- <span data-ttu-id="fdfa3-130">Aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="fdfa3-130">On-hand quantity</span></span>

## <a name="how-it-works"></a><span data-ttu-id="fdfa3-131">Hogyan működik?</span><span class="sxs-lookup"><span data-stu-id="fdfa3-131">How it works</span></span>

<span data-ttu-id="fdfa3-132">Ha az **Árajánlatok**, **Rendelések** vagy **Számlák** lapon az **Aktuális készlet** gombot választja, a rendszer élő, kettős írásos hívást küld az **Aktuális készlet** API-jának.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-132">When you select the **On-hand Inventory** button on the **Quotes**, **Orders**, or **Invoices** page, a live dual-write call is made to the **Onhand inventory** API.</span></span> <span data-ttu-id="fdfa3-133">Az API kiszámítja az adott termék aktuális készletét.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-133">The API calculates the on-hand inventory for the given product.</span></span> <span data-ttu-id="fdfa3-134">A rendszer az eredményt az **InventCDSInventoryOnHandRequestEntity** és az **InventCDSInventoryOnHandEntryEntity** táblákban tárolja, majd Dataverse kettős írással írja.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-134">The result is stored in the **InventCDSInventoryOnHandRequestEntity** and **InventCDSInventoryOnHandEntryEntity** tables, and then is written to Dataverse by dual-write.</span></span> <span data-ttu-id="fdfa3-135">A funkció használatához a következő kettős írású leképezések futtatására van szükség.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-135">To use this functionality, you need to run the following dual-write maps.</span></span> <span data-ttu-id="fdfa3-136">Hagyja ki a kezdeti szinkronizálást a leképezések futtatásakor.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-136">Skip initial synchronization when you run the maps.</span></span>

- <span data-ttu-id="fdfa3-137">CDS aktuális készlettel kapcsolatos bejegyzések (msdyn_inventoryonhandentries)</span><span class="sxs-lookup"><span data-stu-id="fdfa3-137">CDS inventory on-hand entries (msdyn_inventoryonhandentries)</span></span>
- <span data-ttu-id="fdfa3-138">CDS aktuális készlettel kapcsolatos kérések (msdyn_inventoryonhandrequests)</span><span class="sxs-lookup"><span data-stu-id="fdfa3-138">CDS inventory on-hand requests (msdyn_inventoryonhandrequests)</span></span>

## <a name="templates"></a><span data-ttu-id="fdfa3-139">Sablonok</span><span class="sxs-lookup"><span data-stu-id="fdfa3-139">Templates</span></span>
<span data-ttu-id="fdfa3-140">Az aktuális készletadatok közzététele érdekében a következő sablonok állnak rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-140">The following templates are available for the exposing the onhand inventory data.</span></span>

<span data-ttu-id="fdfa3-141">Finance and Operations-alkalmazásoknak</span><span class="sxs-lookup"><span data-stu-id="fdfa3-141">Finance and Operations apps</span></span> | <span data-ttu-id="fdfa3-142">Customer Engagement alkalmazás</span><span class="sxs-lookup"><span data-stu-id="fdfa3-142">Customer engagement app</span></span> | <span data-ttu-id="fdfa3-143">Leírás</span><span class="sxs-lookup"><span data-stu-id="fdfa3-143">Description</span></span> 
---|---|---
[<span data-ttu-id="fdfa3-144">Aktuális bejegyzések CDS-készlete</span><span class="sxs-lookup"><span data-stu-id="fdfa3-144">CDS inventory on-hand entries</span></span>](#145) | <span data-ttu-id="fdfa3-145">msdyn_inventoryonhandentries</span><span class="sxs-lookup"><span data-stu-id="fdfa3-145">msdyn_inventoryonhandentries</span></span> |
[<span data-ttu-id="fdfa3-146">CDS-készlet aktuális kérelmei</span><span class="sxs-lookup"><span data-stu-id="fdfa3-146">CDS inventory on-hand requests</span></span>](#147) | <span data-ttu-id="fdfa3-147">msdyn_inventoryonhandrequests</span><span class="sxs-lookup"><span data-stu-id="fdfa3-147">msdyn_inventoryonhandrequests</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

###  <a name="cds-inventory-on-hand-entries-msdyn_inventoryonhandentries"></a><a name="145"></a><span data-ttu-id="fdfa3-148">CDS aktuális készlettel kapcsolatos bejegyzések (msdyn_inventoryonhandentries)</span><span class="sxs-lookup"><span data-stu-id="fdfa3-148">CDS inventory on-hand entries (msdyn_inventoryonhandentries)</span></span>

<span data-ttu-id="fdfa3-149">Ez a sablon szinkronizálja az adatokat az Finance and Operations alkalmazások és a(z) Dataverseközött.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-149">This template synchronizes data between Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="fdfa3-150">Finance and Operations mező</span><span class="sxs-lookup"><span data-stu-id="fdfa3-150">Finance and Operations field</span></span> | <span data-ttu-id="fdfa3-151">Térkép típusa</span><span class="sxs-lookup"><span data-stu-id="fdfa3-151">Map type</span></span> | <span data-ttu-id="fdfa3-152">Customer Engagement mező</span><span class="sxs-lookup"><span data-stu-id="fdfa3-152">Customer engagement field</span></span> | <span data-ttu-id="fdfa3-153">Alapértelmezett érték</span><span class="sxs-lookup"><span data-stu-id="fdfa3-153">Default value</span></span>
---|---|---|---
`REQUESTID` | = | `msdyn_request.msdyn_requestid` |
`INVENTORYSITEID` | = | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | = | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`AVAILABLEONHANDQUANTITY` | > | `msdyn_availableonhandquantity` |
`AVAILABLEORDEREDQUANTITY` | > | `msdyn_availableorderedquantity` |
`ONHANDQUANTITY` | > | `msdyn_onhandquantity` |
`ONORDERQUANTITY` | > | `msdyn_onorderquantity` |
`ORDEREDQUANTITY` | > | `msdyn_orderedquantity` |
`RESERVEDONHANDQUANTITY` | > | `msdyn_reservedonhandquantity` |
`RESERVEDORDEREDQUANTITY` | > | `msdyn_reservedorderedquantity` |
`TOTALAVAILABLEQUANTITY` | > | `msdyn_totalavailablequantity` |
`ATPDATE` | = | `msdyn_atpdate` |
`ATPQUANTITY` | > | `msdyn_atpquantity` |
`PROJECTEDISSUEQUANTITY` | > | `msdyn_projectedissuequantity` |
`PROJECTEDONHANDQUANTITY` | > | `msdyn_projectedonhandquantity` |
`PROJECTEDRECEIPTQUANTITY` | > | `msdyn_projectedreceiptquantity` |
`ORDERQUANTITY` | > | `msdyn_orderquantity` |
`UNAVAILABLEONHANDQUANTITY` | > | `msdyn_unavailableonhandquantity` |

###  <a name="cds-inventory-on-hand-requests-msdyn_inventoryonhandrequests"></a><a name="147"></a><span data-ttu-id="fdfa3-154">CDS aktuális készlettel kapcsolatos kérések (msdyn_inventoryonhandrequests)</span><span class="sxs-lookup"><span data-stu-id="fdfa3-154">CDS inventory on-hand requests (msdyn_inventoryonhandrequests)</span></span>

<span data-ttu-id="fdfa3-155">Ez a sablon szinkronizálja az adatokat az Finance and Operations alkalmazások és a(z) Dataverseközött.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-155">This template synchronizes data between Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="fdfa3-156">Finance and Operations mező</span><span class="sxs-lookup"><span data-stu-id="fdfa3-156">Finance and Operations field</span></span> | <span data-ttu-id="fdfa3-157">Térkép típusa</span><span class="sxs-lookup"><span data-stu-id="fdfa3-157">Map type</span></span> | <span data-ttu-id="fdfa3-158">Customer Engagement mező</span><span class="sxs-lookup"><span data-stu-id="fdfa3-158">Customer engagement field</span></span> | <span data-ttu-id="fdfa3-159">Alapértelmezett érték</span><span class="sxs-lookup"><span data-stu-id="fdfa3-159">Default value</span></span>
---|---|---|---
`REQUESTID` | = | `msdyn_requestid` |
`PRODUCTNUMBER` | < | `msdyn_product.msdyn_productnumber` |
`ISATPCALCULATION` | << | `msdyn_isatpcalculation` |
`ORDERQUANTITY` | < | `msdyn_orderquantity` |
`INVENTORYSITEID` | < | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | < | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`REFERENCENUMBER` | < | `msdyn_referencenumber` |
`LINECREATIONSEQUENCENUMBER` | < | `msdyn_linecreationsequencenumber` |






[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]