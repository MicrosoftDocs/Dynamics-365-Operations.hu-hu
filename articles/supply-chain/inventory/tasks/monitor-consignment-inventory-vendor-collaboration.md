---
title: Bizományosi készlet figyelése szállítói együttműködéssel
description: Ez az eljárás bemutatja, hogyan használható a szállítói együttműködés információk megtekintésére az olyan termékek készletszintjével kapcsolatban, amelyeket bizományba helyeztek a vevőnél.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, PurchVendorPortalConfirmedOrders, DefaultDashboard, ConsignmentVendorPortalOnhand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f2e782bed4cd9f2f13e2ee45afffaef277279131
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020129"
---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a><span data-ttu-id="bb7d8-103">Bizományosi készlet figyelése szállítói együttműködéssel</span><span class="sxs-lookup"><span data-stu-id="bb7d8-103">Monitor consignment inventory using vendor collaboration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bb7d8-104">Ez az eljárás bemutatja, hogyan használható a szállítói együttműködés információk megtekintésére az olyan termékek készletszintjével kapcsolatban, amelyeket bizományba helyeztek a vevőnél.</span><span class="sxs-lookup"><span data-stu-id="bb7d8-104">This procedure shows how to use vendor collaboration to see information about the stock level of product that you have placed in consignment with a customer.</span></span> <span data-ttu-id="bb7d8-105">A készlet fogyasztása is megfigyelhető, amikor a vevő átveszi a készlet tulajdonjogát.</span><span class="sxs-lookup"><span data-stu-id="bb7d8-105">You can also monitor the consumption of the stock when the customer takes ownership of the inventory.</span></span> <span data-ttu-id="bb7d8-106">Az USMF bemutatócég adataiban használhatja ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="bb7d8-106">You can use this procedure in the USMF demo data company.</span></span> <span data-ttu-id="bb7d8-107">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="bb7d8-107">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="view-consumed-inventory"></a><span data-ttu-id="bb7d8-108">Felhasznált készlet megjelenítése</span><span class="sxs-lookup"><span data-stu-id="bb7d8-108">View consumed inventory</span></span>
1. <span data-ttu-id="bb7d8-109">Ugrás a Szállítói együttműködés > Bizományosi készlet > Bizományosi készletből kapott termékek elemre.</span><span class="sxs-lookup"><span data-stu-id="bb7d8-109">Go to Vendor collaboration > Consignment inventory > Products received from consignment inventory.</span></span>
    * <span data-ttu-id="bb7d8-110">A lista azokat a termékbevételezési sorokat tartalmazza, amelyek akkor jöttek létre, amikor a bizományosi készlet tulajdonjoga átszállt a szállítóról a vevőre.</span><span class="sxs-lookup"><span data-stu-id="bb7d8-110">The list shows the product receipt lines that were generated when ownership of the consignment inventory was changed from the vendor to the customer.</span></span> <span data-ttu-id="bb7d8-111">Előfordulhat, hogy jobbra kell görgetnie a mennyiségek és az egyéb információk megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="bb7d8-111">You might have to scroll to the right to see quantities and other information.</span></span> <span data-ttu-id="bb7d8-112">A listában található információ számlák létrehozására használható a vevő számára.</span><span class="sxs-lookup"><span data-stu-id="bb7d8-112">You can use the information in this list to generate invoices for your customer.</span></span> <span data-ttu-id="bb7d8-113">Az adatok a Microsoft Excel programba is exportálhatók.</span><span class="sxs-lookup"><span data-stu-id="bb7d8-113">You can also export the data to Microsoft Excel.</span></span>   
2. <span data-ttu-id="bb7d8-114">Kattintson a Beszerzési rendelés megtekintése elemre.</span><span class="sxs-lookup"><span data-stu-id="bb7d8-114">Click View purchase order.</span></span>
3. <span data-ttu-id="bb7d8-115">Bontsa ki a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="bb7d8-115">Expand the Line details section.</span></span>
    * <span data-ttu-id="bb7d8-116">A sor Bizományosként van megjelölve, és a fejléc szakasz azt mutatja, hogy a beszerzési rendelés állapota Beérkezett.</span><span class="sxs-lookup"><span data-stu-id="bb7d8-116">The line is marked as Consignment, and the header section shows that the purchase order has a status of Received.</span></span>  
4. <span data-ttu-id="bb7d8-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="bb7d8-117">Close the page.</span></span>

## <a name="view-on-hand-inventory"></a><span data-ttu-id="bb7d8-118">Megtekinti az aktuális készletet</span><span class="sxs-lookup"><span data-stu-id="bb7d8-118">View on-hand inventory</span></span>
1. <span data-ttu-id="bb7d8-119">Ugrás a Szállítói együttműködés > Bizományosi készlet > Aktuális bizományosi készlet elemre.</span><span class="sxs-lookup"><span data-stu-id="bb7d8-119">Go to Vendor collaboration > Consignment inventory > On-hand consignment inventory.</span></span>
    * <span data-ttu-id="bb7d8-120">Az aktuális készlet lap a vevő raktárában levő, az ön tulajdonában álló készletet mutatja.</span><span class="sxs-lookup"><span data-stu-id="bb7d8-120">The On-hand consignment inventory page shows the stock that you own at the customer's warehouse.</span></span> <span data-ttu-id="bb7d8-121">További dimenziók, például a hely és a raktár, a Dimenziók megjelenítése fülre kattintva jeleníthetők meg.</span><span class="sxs-lookup"><span data-stu-id="bb7d8-121">You can show additional dimensions, such as the site and warehouse, by clicking the Display dimensions tab.</span></span>   

