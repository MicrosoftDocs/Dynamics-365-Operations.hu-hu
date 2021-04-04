---
title: A nem készletcikkek kivehetők
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha a vevők készleten nem lévő cikkeket adhatnak hozzá a bevásárlókocsijukhoz, és továbbléphetnek a pénztárhoz.
author: Reza-Assadi
manager: AnnBe
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
ms.openlocfilehash: 6df9c77248c7f4e16765b98327fe5838f0fce7e4
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585355"
---
# <a name="items-without-inventory-can-be-checked-out"></a><span data-ttu-id="797ab-103">A nem készletcikkek kivehetők</span><span class="sxs-lookup"><span data-stu-id="797ab-103">Items without inventory can be checked out</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="797ab-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha a vevők készleten nem lévő cikkeket adhatnak hozzá a bevásárlókocsijukhoz, és továbbléphetnek a pénztárhoz.</span><span class="sxs-lookup"><span data-stu-id="797ab-104">This topic provides troubleshooting guidance that can help when customers can add out-of-stock items to their cart and proceed to checkout.</span></span>

## <a name="description"></a><span data-ttu-id="797ab-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="797ab-105">Description</span></span>

<span data-ttu-id="797ab-106">A felhasználók akkor is hozzáadhatnak egy cikket a kosárhoz, ha az üzletben nincs aktuális készlet, majd továbbléphetnek a pénztár oldalra.</span><span class="sxs-lookup"><span data-stu-id="797ab-106">Users can add an item to their cart, even though there is no on-hand inventory in the store, and then proceed to the checkout page.</span></span>

## <a name="resolution"></a><span data-ttu-id="797ab-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="797ab-107">Resolution</span></span>

### <a name="enable-the-show-out-of-stock-errors-property-in-commerce-site-builder"></a><span data-ttu-id="797ab-108">A nincs készleten állapottal kapcsolatos hibák megjelenítése tulajdonság engedélyezése a Commerce webhelyszerkesztőben</span><span class="sxs-lookup"><span data-stu-id="797ab-108">Enable the Show Out Of Stock Errors property in Commerce site builder</span></span>

<span data-ttu-id="797ab-109">Kövesse az alábbi lépéseket **A nincs készleten állapottal kapcsolatos hibák megjelenítése** tulajdonság Commerce webhelyszerkesztőben történő engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="797ab-109">To enable the **Show Out Of Stock Errors** property in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="797ab-110">Válassza ki azt a webhelyet, amelyen dolgozik.</span><span class="sxs-lookup"><span data-stu-id="797ab-110">Select the site that you're working on.</span></span>
1. <span data-ttu-id="797ab-111">A bal oldali navigációs részben válassza ki az **Oldalak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="797ab-111">In the left navigation, select **Pages**.</span></span>
1. <span data-ttu-id="797ab-112">A megnyitáshoz válassza a **CartPage** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="797ab-112">Select **CartPage** to open it.</span></span>
1. <span data-ttu-id="797ab-113">Válassza ki az **1. bevásárlókocsi** lehetőséget, válassza a **Szerkesztés** lehetőséget, majd a tulajdonságok panelen jelölje be **A nincs készleten állapottal kapcsolatos hibák megjelenítése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="797ab-113">Select the **Cart 1** slot, select **Edit**, and then, in the properties pane, select the **Show Out Of Stock Errors** check box.</span></span>
1. <span data-ttu-id="797ab-114">Mentse és tegye közzé az oldalt.</span><span class="sxs-lookup"><span data-stu-id="797ab-114">Save and publish the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="797ab-115">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="797ab-115">Additional resources</span></span>

[<span data-ttu-id="797ab-116">Készletbeállítások alkalmazása</span><span class="sxs-lookup"><span data-stu-id="797ab-116">Apply inventory settings</span></span>](../inventory-settings.md)

[<span data-ttu-id="797ab-117">Kiskereskedelmi csatornák készletelérhetőségének kiszámítása</span><span class="sxs-lookup"><span data-stu-id="797ab-117">Calculate inventory availability for retail channels</span></span>](../calculated-inventory-retail-channels.md)

[<span data-ttu-id="797ab-118">Készletpufferek és készletszintek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="797ab-118">Configure inventory buffers and inventory levels</span></span>](../inventory-buffers-levels.md)