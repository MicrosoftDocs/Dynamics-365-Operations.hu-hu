---
title: Vevői kifizetések letétbe helyezése
description: Vevői kifizetések letétele.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1d903f557fbaeb720dd4a34dc1c772be0dcb56eb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443971"
---
# <a name="deposit-customer-payments"></a><span data-ttu-id="a4eca-103">Vevői kifizetések letétbe helyezése</span><span class="sxs-lookup"><span data-stu-id="a4eca-103">Deposit customer payments</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a4eca-104">Vevői kifizetések letétele.</span><span class="sxs-lookup"><span data-stu-id="a4eca-104">Deposit customer payments.</span></span> <span data-ttu-id="a4eca-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="a4eca-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="a4eca-106">Válassza a **Navigációs ablaktábla >Modulok > Kinnlévőségek > Kifizetések > Kifizetési napló** elemet.</span><span class="sxs-lookup"><span data-stu-id="a4eca-106">Go to **Navigation pane > Modules > Accounts receivable > Payments > Payment journal**.</span></span>
2. <span data-ttu-id="a4eca-107">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a4eca-107">Select **New**.</span></span>
3. <span data-ttu-id="a4eca-108">A **Név** mezőben válassza ki a **CustPay** elemet a legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="a4eca-108">In the **Name** field, select **CustPay** in the drop-down menu.</span></span>
4. <span data-ttu-id="a4eca-109">**Sorok** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="a4eca-109">Select **Lines**.</span></span>
5. <span data-ttu-id="a4eca-110">A **Számla** mezőben válassza ki azt a vevőt, akihez rögzíti a fizetést.</span><span class="sxs-lookup"><span data-stu-id="a4eca-110">In the **Account** field, select the customer for whom you are recording the payment.</span></span>
6. <span data-ttu-id="a4eca-111">A **Követel** mezőbe írja be a fizetés összegét.</span><span class="sxs-lookup"><span data-stu-id="a4eca-111">In the **Credit** field, enter the amount of the payment.</span></span> <span data-ttu-id="a4eca-112">Az összeget üresen is hagyhatja, ilyenkor a rendszer kiszámítja, ha kiválasztja a kifizetett számlákat.</span><span class="sxs-lookup"><span data-stu-id="a4eca-112">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
7. <span data-ttu-id="a4eca-113">Írjon be egy értéket a **Fizetési hivatkozás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a4eca-113">In the **Payment reference** field, type a value.</span></span> <span data-ttu-id="a4eca-114">A kifizetési hivatkozás lehet a bevitt kifizetés csekkszáma.</span><span class="sxs-lookup"><span data-stu-id="a4eca-114">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="a4eca-115">A kifizetési hivatkozás azért szükséges, hogy a kifizetés letéti jegyen is szerepeljen.</span><span class="sxs-lookup"><span data-stu-id="a4eca-115">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
8. <span data-ttu-id="a4eca-116">Jelölje be a négyzetet a letéti jegy használatához.</span><span class="sxs-lookup"><span data-stu-id="a4eca-116">Mark the box Use a deposit slip.</span></span> <span data-ttu-id="a4eca-117">Ha a kifizetésnek szerepelnie kell a letéten, ezt a beállítást állítsa az Igen lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a4eca-117">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
9. <span data-ttu-id="a4eca-118">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a4eca-118">Select **New**.</span></span>
10. <span data-ttu-id="a4eca-119">A **Számla** mezőben válassza ki a vevőt a következő fizetéshez.</span><span class="sxs-lookup"><span data-stu-id="a4eca-119">In the **Account** field, select the customer for the next payment.</span></span>
11. <span data-ttu-id="a4eca-120">Adja meg a fizetés összegét a **Követel** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a4eca-120">In the **Credit** field, enter the payment amount.</span></span>
12. <span data-ttu-id="a4eca-121">Írjon be egy értéket a **Fizetési hivatkozás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a4eca-121">In the **Payment reference** field, type a value.</span></span>
13. <span data-ttu-id="a4eca-122">Jelölje be a négyzetet a **Letéti jegy használatához**.</span><span class="sxs-lookup"><span data-stu-id="a4eca-122">Mark the box **Use a deposit slip**.</span></span>
14. <span data-ttu-id="a4eca-123">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="a4eca-123">Select **Post**.</span></span> <span data-ttu-id="a4eca-124">Letéti jegyet csak akkor hozhat létre, ha feladta a kifizetéseket.</span><span class="sxs-lookup"><span data-stu-id="a4eca-124">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="a4eca-125">Ez azért van így, hogy a kifizetés ne változhasson a letéti jegy létrehozása után.</span><span class="sxs-lookup"><span data-stu-id="a4eca-125">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
15. <span data-ttu-id="a4eca-126">Válassza a **Funkciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a4eca-126">Select **Functions**.</span></span>
16. <span data-ttu-id="a4eca-127">Válassza a **Letéti jegy** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a4eca-127">Select **Deposit slip**.</span></span>
17. <span data-ttu-id="a4eca-128">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a4eca-128">Select **OK**.</span></span> <span data-ttu-id="a4eca-129">Az első oldalon a letéti jegyet hozhatja létre.</span><span class="sxs-lookup"><span data-stu-id="a4eca-129">The first page is used to create the deposit slip.</span></span>  
18. <span data-ttu-id="a4eca-130">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a4eca-130">Select **OK**.</span></span> <span data-ttu-id="a4eca-131">A második lépésben kinyomtatja a letéti jegyet, de ez a lépés ne kötelező.</span><span class="sxs-lookup"><span data-stu-id="a4eca-131">The second step is to print the deposit slip, but this step is not required.</span></span>  

