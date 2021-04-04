---
title: A fizetés típusa csak hitelkártyás lehet hiba az értékesítési rendelés oldalán
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha egy rendelés szinkronizálása után hibaüzenet jelenik meg az értékesítési rendelés oldalán.
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
ms.openlocfilehash: 20f18507dee330fd1affedeee092b3dfa7cc10bc
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585358"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a><span data-ttu-id="7c516-103">„A fizetés típusa csak hitelkártyás lehet” hiba az értékesítési rendelés oldalon</span><span class="sxs-lookup"><span data-stu-id="7c516-103">"Payment type must be credit card" error on the sales order page</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7c516-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha egy rendelés szinkronizálása után hibaüzenet jelenik meg az értékesítési rendelés oldalán.</span><span class="sxs-lookup"><span data-stu-id="7c516-104">This topic provides troubleshooting guidance that can help when an error message is shown on the sales order page after an order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="7c516-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="7c516-105">Description</span></span>

<span data-ttu-id="7c516-106">Amikor a rendelés szinkronizálása után megnyitja az értékesítési rendelés lapot, a következő hibaüzenet jelenik meg: „A fizetés típusának hitelkártyának kell lennie, mivel a hitelkártya számát adta meg.”</span><span class="sxs-lookup"><span data-stu-id="7c516-106">When you open the sales order page after you sync an order, you receive the following error message: "The payment type must be credit card, since the credit card number has been specified."</span></span>

![A fizetés típusa csak hitelkártyás lehet hiba](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a><span data-ttu-id="7c516-108">Felbontás</span><span class="sxs-lookup"><span data-stu-id="7c516-108">Resolution</span></span>

### <a name="set-the-payment-type-in-commerce-headquarters"></a><span data-ttu-id="7c516-109">A fizetéstípus beállítása a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="7c516-109">Set the payment type in Commerce headquarters</span></span>

1. <span data-ttu-id="7c516-110">Ugorjon a **Kinnlevőségek \> Fizetési beállítás \> Fizetési feltételek** pontra.</span><span class="sxs-lookup"><span data-stu-id="7c516-110">Go to **Accounts receivable \> Payment setup \> Terms of payment**.</span></span>
1. <span data-ttu-id="7c516-111">A bal oldali navigációs részben válassza ki a fizetési feltételeket.</span><span class="sxs-lookup"><span data-stu-id="7c516-111">In the left navigation, select your terms of payment.</span></span>
1. <span data-ttu-id="7c516-112">A **Fizetés típusa** mezőben győződjön meg arról, hogy a **Hitelkártya** lehetőség legyen kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="7c516-112">In the **Payment type** field, make sure that **Credit card** is selected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7c516-113">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="7c516-113">Additional resources</span></span>

[<span data-ttu-id="7c516-114">Online értékesítések és kifizetések feladása</span><span class="sxs-lookup"><span data-stu-id="7c516-114">Posting of online sales and payments</span></span>](../tasks/posting-online-sales-payments.md)
