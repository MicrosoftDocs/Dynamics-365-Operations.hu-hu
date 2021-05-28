---
title: A Mentés a következő fizetéshez lehetőség nem jelenik meg
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha az e-kereskedelmi webhely pénztároldalán nem jelenik meg a Mentés a következő fizetéshez lehetőség jelölőnégyzet a Fizetési mód pontban.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: af19a3abd78d543d82f7a8d017e2dc413115a6d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018434"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a><span data-ttu-id="2678b-103">A Mentés a következő fizetéshez lehetőség nem jelenik meg</span><span class="sxs-lookup"><span data-stu-id="2678b-103">"Save for my next payment" option doesn't appear</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2678b-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha az e-kereskedelmi webhely pénztároldalán nem jelenik meg a **Mentés a következő fizetéshez** lehetőség jelölőnégyzet a **Fizetési mód** pontban.</span><span class="sxs-lookup"><span data-stu-id="2678b-104">This topic provides troubleshooting guidance that can help when the **Save for my next payment** check box doesn't appear under **Payment method** on an e-commerce site's checkout page.</span></span>

## <a name="description"></a><span data-ttu-id="2678b-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="2678b-105">Description</span></span>

<span data-ttu-id="2678b-106">Az e-kereskedelmi pénztároldalon a **Mentés a következő fizetéshez** lehetőség nem jelenik meg a **Fizetési mód** pontban.</span><span class="sxs-lookup"><span data-stu-id="2678b-106">The **Save for my next payment** check box doesn't appear in the **Payment method** section on an e-commerce site's checkout page.</span></span>

<span data-ttu-id="2678b-107">A következő illusztráció egy olyan pénztároldalt mutat be, amely tartalmazza a **Mentés a következő fizetéshez** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="2678b-107">The following illustration shows an example of a checkout page that includes the **Save for my next payment** check box.</span></span>

![A Mentés a következő fizetéshez jelölőnégyzet a Fizetés modulban](media/payment-module-save-payment.jpg)

## <a name="resolution"></a><span data-ttu-id="2678b-109">Felbontás</span><span class="sxs-lookup"><span data-stu-id="2678b-109">Resolution</span></span>

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a><span data-ttu-id="2678b-110">Győződjön meg arról, hogy a Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz helyesen van-e konfigurálva a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="2678b-110">Verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters</span></span>

<span data-ttu-id="2678b-111">Annak ellenőrzésére, hogy a Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz helyesen van-e konfigurálva a Commerce központi felületén, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="2678b-111">To verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="2678b-112">Nyissa meg a következőt: **Kiskereskedelem és kereskedelem \> Csatornák \> Online áruházak**.</span><span class="sxs-lookup"><span data-stu-id="2678b-112">Go to **Retail and Commerce \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="2678b-113">Válassza ki az online áruházat.</span><span class="sxs-lookup"><span data-stu-id="2678b-113">Select the online store.</span></span>
1. <span data-ttu-id="2678b-114">A **Fizetési számlák** gyorslapon győződjön meg arról, hogy a **Fizetési információ mentésének engedélyezése az e-kereskedelemben** mező értéke **Igaz** legyen.</span><span class="sxs-lookup"><span data-stu-id="2678b-114">On the **Payment accounts** FastTab, make sure that the **Allow saving payment information in e-commerce** field is set to **True**.</span></span>

![Fizetési információ mentésének engedélyezése az e-kereskedelemben a Commerce központi felületén](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a><span data-ttu-id="2678b-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2678b-116">Additional resources</span></span>

[<span data-ttu-id="2678b-117">Fizetési modul</span><span class="sxs-lookup"><span data-stu-id="2678b-117">Payment module</span></span>](../payment-module.md)

[<span data-ttu-id="2678b-118">Online fizetési eszközök mentése az Adyen összekötővel</span><span class="sxs-lookup"><span data-stu-id="2678b-118">Saving online payment instruments with the Adyen connector</span></span>](../dev-itpro/adyen-connector-listPI.md)
