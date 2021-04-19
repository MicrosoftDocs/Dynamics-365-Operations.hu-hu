---
title: Az online rendelések adói helytelenül vannak kiszámítva
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget jelenthet az online rendelések adójának helytelen kiszámítása vagy az értékesítési sorban beállított áfacsoport helytelen beállítása esetén.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7f71add679e1d24f80db8ce3990058b591128ec1
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801411"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a><span data-ttu-id="ca349-103">Az online rendelések adói helytelenül vannak kiszámítva</span><span class="sxs-lookup"><span data-stu-id="ca349-103">Taxes on online orders are incorrectly calculated</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ca349-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget jelenthet az online rendelések adójának helytelen kiszámítása vagy az értékesítési sorban beállított áfacsoport helytelen beállítása esetén.</span><span class="sxs-lookup"><span data-stu-id="ca349-104">This topic provides troubleshooting guidance that can help when taxes on online orders are incorrectly calculated, or when the tax group on the sales line isn't correctly set.</span></span>

## <a name="description"></a><span data-ttu-id="ca349-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="ca349-105">Description</span></span>

<span data-ttu-id="ca349-106">Az e-kereskedelmi rendelések leadása esetén a program helytelenül számítja ki az adót, vagy helytelenül van beállítva az értékesítési sorban beállított áfacsoport.</span><span class="sxs-lookup"><span data-stu-id="ca349-106">When an e-commerce order is placed, the taxes are incorrectly calculated, or the tax group on the sales line is incorrectly set.</span></span>

## <a name="resolution"></a><span data-ttu-id="ca349-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="ca349-107">Resolution</span></span>

### <a name="configure-the-sales-tax-for-a-retail-store-in-commerce-headquarters"></a><span data-ttu-id="ca349-108">Kiskereskedelmi áruház áfájának konfigurálása a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="ca349-108">Configure the sales tax for a retail store in Commerce headquarters</span></span>

<span data-ttu-id="ca349-109">Egy kiskereskedelmi áruház áfájának konfigurálásához a Commerce központi felületén kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ca349-109">To configure the sales tax for a retail store in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="ca349-110">Ugorjon a következő oldalra: **Retail és Commerce \> Csatornák \> Minden üzlet**.</span><span class="sxs-lookup"><span data-stu-id="ca349-110">Go to **Retail and Commerce \> Channels \> All stores**.</span></span>
1. <span data-ttu-id="ca349-111">Válassza ki azt az üzletet, amelyhez konfigurálni akarja az áfát.</span><span class="sxs-lookup"><span data-stu-id="ca349-111">Select the store to configure sales tax for.</span></span>
1. <span data-ttu-id="ca349-112">Az **Általános** gyorslapon az **Áfa** részben konfigurálja az üzlet áfainformációit.</span><span class="sxs-lookup"><span data-stu-id="ca349-112">On the **General** FastTab, in the **Sales tax** section, configure the sales tax information for the store.</span></span>

> [!NOTE]
> <span data-ttu-id="ca349-113">Termék üzletből való felvétele esetén az áfacsoport a felvételre kiválasztott üzletből származik.</span><span class="sxs-lookup"><span data-stu-id="ca349-113">For product pickup from a store, the tax group comes from the store that is selected for pickup.</span></span> <span data-ttu-id="ca349-114">További információk: [Üzletek egyéb adóbeállításainak megadása](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span><span class="sxs-lookup"><span data-stu-id="ca349-114">For more information, see [Set other tax options for stores](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span></span>

### <a name="configure-the-sales-tax-for-a-customers-address-in-commerce-headquarters"></a><span data-ttu-id="ca349-115">Ügyfél címéhez kapcsolódó áfa konfigurálása a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="ca349-115">Configure the sales tax for a customer's address in Commerce headquarters</span></span>

<span data-ttu-id="ca349-116">Egy ügyfél címéhez kapcsolódó áfa konfigurálásához a Commerce központi felületén kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ca349-116">To configure the sales tax for a customer's address in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="ca349-117">Nyissa meg a **Kinnlevőségek \> Vevők \> Minden vevő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca349-117">Go to **Accounts receivable \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="ca349-118">Válassza ki azt a vevőt, amelyhez áfát szeretne konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="ca349-118">Select the customer to configure sales taxes for.</span></span>
1. <span data-ttu-id="ca349-119">A **Címek** gyorslapon válassza ki azt a címet, amelyhez áfát szeretne konfigurálni, válassza ki a **További beállítások** lehetőséget, majd válassza a **Speciális** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca349-119">On the **Addresses** FastTab, select the address to configure sales taxes for, select **More options**, and then select **Advanced**.</span></span>
1. <span data-ttu-id="ca349-120">Az **Általános** gyorslapon válassza az **Áfacsoport** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca349-120">On the **General** FastTab, select the **Tax group**.</span></span>
1. <span data-ttu-id="ca349-121">Válassza ki a megfelelő értéket az **Áfa** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ca349-121">In the **Sales tax** field, select the appropriate value.</span></span>

> [!NOTE]
> <span data-ttu-id="ca349-122">Olyan szállítások esetén, amelyek a vevő címéhez kapcsolódóan áfát tartalmaznak, a sor szállítási címe határozza meg a sor áfacsoportját.</span><span class="sxs-lookup"><span data-stu-id="ca349-122">For shipping that involves sales tax on the customer's address, the delivery address of the line determines the tax group for the line.</span></span> <span data-ttu-id="ca349-123">Ha a vevő olyan létező címre szállít, amelyhez már konfigurált áfacsoport tartozik, a rendszer a meglévő áfacsoportot használja.</span><span class="sxs-lookup"><span data-stu-id="ca349-123">If the customer is shipping to an existing address that has a tax group that is already configured, the existing tax group will be used.</span></span> <span data-ttu-id="ca349-124">A címek alapértelmezés szerint létrehozáskor nem rendelkeznek áfacsoporttal.</span><span class="sxs-lookup"><span data-stu-id="ca349-124">By default, addresses don't have a tax group when they are created.</span></span>

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a><span data-ttu-id="ca349-125">Általános áfacsoportok konfigurálása a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="ca349-125">Configure general sales tax groups in Commerce headquarters</span></span>

<span data-ttu-id="ca349-126">Az általános áfacsoportok Commerce központi felületén történő konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ca349-126">To configure general sales tax groups in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="ca349-127">Ugorjon az **Adó \> Közvetett adók \> Áfa \> Áfakódcsoportok** pontra.</span><span class="sxs-lookup"><span data-stu-id="ca349-127">Go to **Tax \> Indirect taxes \> Sales tax \> Sales tax group**.</span></span>
1. <span data-ttu-id="ca349-128">A bal oldali navigációs részben válassza ki a konfigurálni kívánt áfacsoportot.</span><span class="sxs-lookup"><span data-stu-id="ca349-128">In the left navigation, select the tax group to configure.</span></span>
1. <span data-ttu-id="ca349-129">A **Kiskereskedelmi célalapú adó** gyorslapon konfigurálja az áfacsoport adóit.</span><span class="sxs-lookup"><span data-stu-id="ca349-129">On the **Retail destination based tax** FastTab, configure the taxes for the sales tax group.</span></span>

> [!NOTE]
> <span data-ttu-id="ca349-130">Olyan szállítások esetén, amelyek nem tartalmaznak áfát a vevő címében, a sor szállítási címe és az áfacsoporthoz beállított célalapú adók határozzák meg az áfacsoportot.</span><span class="sxs-lookup"><span data-stu-id="ca349-130">For shipping that doesn't involve sales tax on the customer's address, the delivery address of the line and the destination-based taxes that are configured for the tax group determine the tax group.</span></span> <span data-ttu-id="ca349-131">További információ: [Online áruházak adóinak beállítása cél alapján](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination) című témakörben olvashat.</span><span class="sxs-lookup"><span data-stu-id="ca349-131">For more information, see [Set up taxes for online stores based on destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ca349-132">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ca349-132">Additional resources</span></span>

[<span data-ttu-id="ca349-133">Az online rendelések áfájának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ca349-133">Configure sales tax for online orders</span></span>](../sales-tax-config.md)
