---
title: A kifizetéseket a program automatikusan kiegyenlíti a rendelések számlázása vagy szállítása előtt
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha egy kifizetést közvetlenül a rendelés elrendelése után egyenlít ki az Adyen portálon annak ellenére, hogy az értékesítési rendelés számlázása vagy kiszállítása még nem történt meg.
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
ms.openlocfilehash: 43fe90cf99ddbe42dc89685e7fc747ded5a285c0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801651"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a><span data-ttu-id="84945-103">A kifizetéseket a program automatikusan kiegyenlíti a rendelések számlázása vagy szállítása előtt</span><span class="sxs-lookup"><span data-stu-id="84945-103">Payments are automatically settled before orders are invoiced or shipped</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="84945-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha egy kifizetést közvetlenül a rendelés elrendelése után egyenlít ki az Adyen portálon annak ellenére, hogy az értékesítési rendelés számlázása vagy kiszállítása még nem történt meg.</span><span class="sxs-lookup"><span data-stu-id="84945-104">This topic provides troubleshooting guidance that can help when a payment is settled in the Adyen portal immediately after an order is placed, even though the sales order hasn't been invoiced or shipped.</span></span>

## <a name="description"></a><span data-ttu-id="84945-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="84945-105">Description</span></span>

<span data-ttu-id="84945-106">Egy kifizetést közvetlenül a rendelés elrendelése után kiegyenlít az Adyen portálon annak ellenére, hogy az értékesítési rendelés számlázása vagy kiszállítása még nem történt meg.</span><span class="sxs-lookup"><span data-stu-id="84945-106">After an order is placed, the payment is immediately settled in the Adyen portal, even though the sales order hasn't been invoiced or shipped.</span></span>

## <a name="resolution"></a><span data-ttu-id="84945-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="84945-107">Resolution</span></span>

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a><span data-ttu-id="84945-108">Manuális rögzítés konfigurálása az e-kereskedelmi kifizetésekhez az Adyen portálon</span><span class="sxs-lookup"><span data-stu-id="84945-108">Configure manual capture for e-commerce payments in the Adyen portal</span></span>

<span data-ttu-id="84945-109">Kövesse az alábbi lépéseket a manuális rögzítés e-kereskedelmi kifizetésekhez történő konfigurálásához az Adyen portálon.</span><span class="sxs-lookup"><span data-stu-id="84945-109">To configure manual capture for e-commerce payments in the Adyen portal, follow these steps.</span></span>

1. <span data-ttu-id="84945-110">Jelentkezzen be az Adyen portálra.</span><span class="sxs-lookup"><span data-stu-id="84945-110">Sign in to the Adyen portal.</span></span>
1. <span data-ttu-id="84945-111">A jobb felső sarokban válassza ki az e-kereskedelmi csatorna kereskedői számláját.</span><span class="sxs-lookup"><span data-stu-id="84945-111">In the upper-right corner, select your merchant account for the e-commerce channel.</span></span>
1. <span data-ttu-id="84945-112">A felső navigációs sávon válassza a **Számla**, majd a **Beállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="84945-112">On the top navigation, select **Account**, and then select **Settings**.</span></span>
1. <span data-ttu-id="84945-113">A **Rögzítés késleltetése** mezőben válassza a **kézi** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="84945-113">In the **Capture Delay** field, select **manual**.</span></span>

    ![Az Adyen portál Rögzítés késleltetésének beállítása](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a><span data-ttu-id="84945-115">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="84945-115">Additional resources</span></span>

[<span data-ttu-id="84945-116">Adyen fizetés rögzítése</span><span class="sxs-lookup"><span data-stu-id="84945-116">Adyen payment capture</span></span>](https://docs.adyen.com/point-of-sale/capturing-payments)

[<span data-ttu-id="84945-117">Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="84945-117">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="84945-118">Adyen fizetési összekötő a Dynamics 365 szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="84945-118">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
