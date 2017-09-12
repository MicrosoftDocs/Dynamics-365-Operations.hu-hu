--- 
title: "Vevői kifizetések letétbe helyezése"
description: "Vevői kifizetések letétele."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: dbf21bd5df70cd80e4fe3f2f5d699aa82b62423b
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="deposit-customer-payments"></a><span data-ttu-id="58985-103">Vevői kifizetések letétbe helyezése</span><span class="sxs-lookup"><span data-stu-id="58985-103">Deposit customer payments</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="58985-104">Vevői kifizetések letétele.</span><span class="sxs-lookup"><span data-stu-id="58985-104">Deposit customer payments.</span></span> <span data-ttu-id="58985-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="58985-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="58985-106">Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési napló pontra.</span><span class="sxs-lookup"><span data-stu-id="58985-106">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="58985-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="58985-107">Click New.</span></span>
3. <span data-ttu-id="58985-108">A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="58985-108">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="58985-109">A fizetési napló kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="58985-109">Select the payment journal.</span></span> 
5. <span data-ttu-id="58985-110">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="58985-110">Click Lines.</span></span>
6. <span data-ttu-id="58985-111">A Számla mezőben válassza ki azt a vevőt, akihez rögzíti a fizetést.</span><span class="sxs-lookup"><span data-stu-id="58985-111">In the Account field, select the Customer for whom you are recording the payment.</span></span>
7. <span data-ttu-id="58985-112">A Követel mezőbe írja be a fizetés összegét.</span><span class="sxs-lookup"><span data-stu-id="58985-112">In the Credit field, enter the amount of the payment.</span></span>
    * <span data-ttu-id="58985-113">Az összeget üresen is hagyhatja, ilyenkor a rendszer kiszámítja, ha kiválasztja a kifizetett számlákat.</span><span class="sxs-lookup"><span data-stu-id="58985-113">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
8. <span data-ttu-id="58985-114">Írjon be egy értéket a Fizetési hivatkozás mezőbe.</span><span class="sxs-lookup"><span data-stu-id="58985-114">In the Payment reference field, type a value.</span></span>
    * <span data-ttu-id="58985-115">A kifizetési hivatkozás lehet a bevitt kifizetés csekkszáma.</span><span class="sxs-lookup"><span data-stu-id="58985-115">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="58985-116">A kifizetési hivatkozás azért szükséges, hogy a kifizetés letéti jegyen is szerepeljen.</span><span class="sxs-lookup"><span data-stu-id="58985-116">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
9. <span data-ttu-id="58985-117">Jelölje be a négyzetet a letéti jegy használatához.</span><span class="sxs-lookup"><span data-stu-id="58985-117">Mark the box Use a deposit slip.</span></span>
    * <span data-ttu-id="58985-118">Ha a kifizetésnek szerepelnie kell a letéten, ezt a beállítást állítsa az Igen lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="58985-118">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
10. <span data-ttu-id="58985-119">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="58985-119">Click New.</span></span>
11. <span data-ttu-id="58985-120">A Számla mezőben válassza ki a vevőt a következő fizetéshez.</span><span class="sxs-lookup"><span data-stu-id="58985-120">In the Account field, select the Customer for the next payment.</span></span>
12. <span data-ttu-id="58985-121">Adja meg a fizetés összegét a Követel mezőben.</span><span class="sxs-lookup"><span data-stu-id="58985-121">In the Credit field, enter the payment amount.</span></span>
13. <span data-ttu-id="58985-122">Írjon be egy értéket a Fizetési hivatkozás mezőbe.</span><span class="sxs-lookup"><span data-stu-id="58985-122">In the Payment reference field, type a value.</span></span>
14. <span data-ttu-id="58985-123">Jelölje be a négyzetet a letéti jegy használatához.</span><span class="sxs-lookup"><span data-stu-id="58985-123">Mark the box Use a deposit slip.</span></span>
15. <span data-ttu-id="58985-124">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="58985-124">Click Post.</span></span>
    * <span data-ttu-id="58985-125">Letéti jegyet csak akkor hozhat létre, ha feladta a kifizetéseket.</span><span class="sxs-lookup"><span data-stu-id="58985-125">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="58985-126">Ez azért van így, hogy a kifizetés ne változhasson a letéti jegy létrehozása után.</span><span class="sxs-lookup"><span data-stu-id="58985-126">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
16. <span data-ttu-id="58985-127">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="58985-127">Click Functions.</span></span>
17. <span data-ttu-id="58985-128">Kattintson a Letéti jegyre.</span><span class="sxs-lookup"><span data-stu-id="58985-128">Click Deposit slip.</span></span>
18. <span data-ttu-id="58985-129">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="58985-129">Click OK.</span></span>
    * <span data-ttu-id="58985-130">Az első oldalon a letéti jegyet hozhatja létre.</span><span class="sxs-lookup"><span data-stu-id="58985-130">The first page is used to create the deposit slip.</span></span>  
19. <span data-ttu-id="58985-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="58985-131">Click OK.</span></span>
    * <span data-ttu-id="58985-132">A második lépésben kinyomtatja a letéti jegyet, de ez a lépés ne kötelező.</span><span class="sxs-lookup"><span data-stu-id="58985-132">The second step is to print the deposit slip, but this step is not required.</span></span>  


