---
title: Nyugta nélküli visszárukhoz használható fizetési módok korlátozása
description: Ez a témakör leírja, hogyan korlátozhatók bizonyos kifizetéstípusok visszatérítésre, ha a vissszatérítés nyugta nélkül történik.
author: rapraj
manager: AnnBe
ms.date: 01/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: 1f84a6382453c0ba7540e618ad90ae1d3c684a2b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "315912"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="a3a49-103">Nyugta nélküli visszárukhoz használható fizetési módok korlátozása</span><span class="sxs-lookup"><span data-stu-id="a3a49-103">Restrict payment methods for returns without a receipt</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="a3a49-104">Minden egyes fizetéstípust, amelyet a kiskereskedő elfogad, konfigurálni kell a rendszer beállításakor.</span><span class="sxs-lookup"><span data-stu-id="a3a49-104">Each payment type that a retailer accepts must be configured when the system is set up.</span></span> <span data-ttu-id="a3a49-105">Ez a témakör leírja, hogyan korlátozhatók bizonyos kifizetéstípusok visszatérítésre, ha a vissszatérítés nyugta nélkül történik.</span><span class="sxs-lookup"><span data-stu-id="a3a49-105">This topic describes how certain payment types can be restricted for refund if the returns are made without a receipt.</span></span>

## <a name="set-up-payment-methods"></a><span data-ttu-id="a3a49-106">Fizetési módok beállítása</span><span class="sxs-lookup"><span data-stu-id="a3a49-106">Set up payment methods</span></span>

<span data-ttu-id="a3a49-107">Fizetési módok beállításához a következő feladatokat kell elvégezni.</span><span class="sxs-lookup"><span data-stu-id="a3a49-107">To set up payment methods, the following tasks must be completed.</span></span>
1. <span data-ttu-id="a3a49-108">A teljes szervezet által elfogadott fizetési módok létrehozása.</span><span class="sxs-lookup"><span data-stu-id="a3a49-108">Create the payment methods that are accepted by the entire organization.</span></span>
2. <span data-ttu-id="a3a49-109">Szervezeti szinten elfogadott kártyatípusok és kártyaszámok létrehozása.</span><span class="sxs-lookup"><span data-stu-id="a3a49-109">Create organization-wide card types and card numbers.</span></span> <span data-ttu-id="a3a49-110">Ha elfogadja a hitelkártyákat és bankkártyákat, akkor létre kell hoznia egy fizetési típust a kártyákhoz, majd létre kell hoznia a szervezetnél elfogadott kártyatípusokat és azok számait.</span><span class="sxs-lookup"><span data-stu-id="a3a49-110">If credit cards or debit cards are accepted, you must create one payment method for cards, and then create the organization-wide card types and card numbers.</span></span>
3. <span data-ttu-id="a3a49-111">Üzlethez tartozó fizetési módok beállítása.</span><span class="sxs-lookup"><span data-stu-id="a3a49-111">Set up store payment methods.</span></span> <span data-ttu-id="a3a49-112">Minden egyes üzlethez fizetési módokat kell társítania, majd meg kell adnia az egyes fizetési módok adott üzletben jellemző beállításait.</span><span class="sxs-lookup"><span data-stu-id="a3a49-112">Associate payment methods with each store, and then enter the store-specific settings for each payment method.</span></span>
4. <span data-ttu-id="a3a49-113">Kártyás fizetési módok beállítása az üzletekhez.</span><span class="sxs-lookup"><span data-stu-id="a3a49-113">Set up card payment methods for stores.</span></span> <span data-ttu-id="a3a49-114">Minden kártyás fizetési módhoz, amelyet az üzlet elfogad, végezze el a kártyabeállítást.</span><span class="sxs-lookup"><span data-stu-id="a3a49-114">For any card payment methods that the store accepts, complete the card setup.</span></span>

<span data-ttu-id="a3a49-115">![Retail Store beállítása](media/NoReceiptReturns1.png "Retail Store beállítása")</span><span class="sxs-lookup"><span data-stu-id="a3a49-115">![Retail Store Setup](media/NoReceiptReturns1.png "Retail Store Setup")</span></span> 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="a3a49-116">Nyugta nélküli visszárukhoz használható fizetési módok korlátozása</span><span class="sxs-lookup"><span data-stu-id="a3a49-116">Restrict payment methods for returns without a receipt</span></span>

<span data-ttu-id="a3a49-117">Minden üzleti fizetési módhoz a **Kiskereskedelmi üzlet kezelése** oldalon, a **Nyugta nélküli visszatérítések** alatt állítsa be a **Nyugta nélkül visszatérítések korlátozása** elemet **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="a3a49-117">For each store payment method, on the **Retail store management** page, under **Non receipt returns**, set **Restrict for refunds without receipt** to **Yes**.</span></span> 

<span data-ttu-id="a3a49-118">Az kapcsoló alapértelmezés szerinti értéke **Nem**, amely biztosítja, hogy a fizetési mód engedélyezve legyen a visszatérítésekhez.</span><span class="sxs-lookup"><span data-stu-id="a3a49-118">The default value of the toggle is **No**, which ensures that the payment method is allowed for refunds.</span></span> 

<span data-ttu-id="a3a49-119">Ha a **Nyugta nélkül visszatérítések korlátozása** értékre **Igen**, a választott fizetési nem érhető el visszatérítésekhez.</span><span class="sxs-lookup"><span data-stu-id="a3a49-119">When **Restrict for refunds without receipt** is set to **Yes**, the selected payment method will not be allowed for refunds.</span></span> 

<span data-ttu-id="a3a49-120">![Kiskereskedelmi üzlet fizetési mód](media/NoReceiptReturns3.png "Kiskereskedelmi üzlet fizetési mód")</span><span class="sxs-lookup"><span data-stu-id="a3a49-120">![Retail Store payment method](media/NoReceiptReturns3.png "Retail Store Payment Method")</span></span> 

> [!NOTE]
> <span data-ttu-id="a3a49-121">Amikor a pénztáros kiválaszt egy fizetési módot, amely korlátozva van nyugta nélküli visszatérítéshez megjelenik egy üzenet az elfogadható fizetési módok ellenőrzéséhez.</span><span class="sxs-lookup"><span data-stu-id="a3a49-121">When a cashier selects a payment method that is restricted for refund without a receipt, a message displays to verify the acceptable payment methods.</span></span>

<span data-ttu-id="a3a49-122">![Elfogadható fizetési módok](media/NoReceiptReturns4.png "Elfogadható fizetési módok")</span><span class="sxs-lookup"><span data-stu-id="a3a49-122">![Acceptable payment methods](media/NoReceiptReturns4.png "Acceptable payment methods")</span></span> 

<span data-ttu-id="a3a49-123">Ha egy tranzakcióhoz nyugtás és nyugata nélküli visszatérítés is tartozik akkor a korlátozási feltételek nem lesznek alkalmazva, mivel a tranzakció visszatérítés munkafolyamat lesz nyugtával.</span><span class="sxs-lookup"><span data-stu-id="a3a49-123">If a transaction has both a receipted return and a return without a receipt, the restriction conditions will not be enforced because the transaction will be a return workflow with a receipt.</span></span> 

