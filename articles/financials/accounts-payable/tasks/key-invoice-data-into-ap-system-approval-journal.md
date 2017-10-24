--- 
title: "Fő számlaadatok a kötelezettségekbe jóváhagyási napló használatával"
description: "Ez a feladat-útmutató bemutatja hogy kell használni a számlajegyzéket számlák létrehozásához, majd hogyan kell a kiadási számlákat frissíteni a jóváhagyási napló segítségével."
author: abruer
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 604345d357e5019e334017b2b6d0413f40818acc
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a><span data-ttu-id="13611-103">Fő számlaadatok a kötelezettségekbe jóváhagyási napló használatával</span><span class="sxs-lookup"><span data-stu-id="13611-103">Key invoice data into accounts payable using an approval journal</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="13611-104">Ez a feladat-útmutató bemutatja hogy kell használni a számlajegyzéket számlák létrehozásához, majd hogyan kell a kiadási számlákat frissíteni a jóváhagyási napló segítségével.</span><span class="sxs-lookup"><span data-stu-id="13611-104">This task guide will show you how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>


## <a name="create-and-post-and-invoice"></a><span data-ttu-id="13611-105">Számla létrehozása és feladása</span><span class="sxs-lookup"><span data-stu-id="13611-105">Create and post and invoice</span></span>
1. <span data-ttu-id="13611-106">Ugorjon a Kötelezettségek > Számlák > Számlajegyzék elemre.</span><span class="sxs-lookup"><span data-stu-id="13611-106">Go to Accounts payable > Invoices > Invoice register.</span></span>
2. <span data-ttu-id="13611-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="13611-107">Click New.</span></span>
3. <span data-ttu-id="13611-108">Válassza ki a használni kívánt számlajegyzék nevét.</span><span class="sxs-lookup"><span data-stu-id="13611-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="13611-109">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="13611-109">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="13611-110">Kattintson a Sorokra a jegyzék megnyitásához, adjon meg költségsorokat.</span><span class="sxs-lookup"><span data-stu-id="13611-110">Click on Lines to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="13611-111">Válasszon ki egy szállítót.</span><span class="sxs-lookup"><span data-stu-id="13611-111">Select a vendor.</span></span> <span data-ttu-id="13611-112">Például adja a US-104 értéket</span><span class="sxs-lookup"><span data-stu-id="13611-112">For example, enter or select US-104</span></span>
7. <span data-ttu-id="13611-113">Érték beírása a Számla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="13611-113">In the Invoice field, type a value.</span></span>
8. <span data-ttu-id="13611-114">Írjon egy értéket a „Leírás” mezőbe.</span><span class="sxs-lookup"><span data-stu-id="13611-114">In the Description field, type a value.</span></span>
9. <span data-ttu-id="13611-115">A Hitelkeret mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="13611-115">In the Credit field, enter a number.</span></span>
10. <span data-ttu-id="13611-116">A Jóváhagyó mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="13611-116">In the Approved by field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="13611-117">Jelöljön ki egy jóváhagyót és kattintson a Kijelölés gombra a jóváhagyó kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="13611-117">Highlight an approver and click Select to select that approver.</span></span>
12. <span data-ttu-id="13611-118">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="13611-118">Click Post.</span></span>
13. <span data-ttu-id="13611-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="13611-119">Close the page.</span></span>
14. <span data-ttu-id="13611-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="13611-120">Close the page.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="13611-121">Számla jóváhagyása</span><span class="sxs-lookup"><span data-stu-id="13611-121">Approve an invoice</span></span>
1. <span data-ttu-id="13611-122">Ugorjon a Kötelezettségek > Számlák > Számlajóváhagyás elemre.</span><span class="sxs-lookup"><span data-stu-id="13611-122">Go to Accounts payable > Invoices > Invoice approval.</span></span>
2. <span data-ttu-id="13611-123">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="13611-123">Click New.</span></span>
3. <span data-ttu-id="13611-124">Válassza ki a használni kívánt számlajóváhagyás-jegyzék nevét.</span><span class="sxs-lookup"><span data-stu-id="13611-124">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="13611-125">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="13611-125">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="13611-126">Kattintson a sorokra az oldal megjelenítéséhez, ahol kiválaszthatja a jóváhagyni kívánt számlákat.</span><span class="sxs-lookup"><span data-stu-id="13611-126">Click lines to display a page where you will be able to select the invoices that you want to approve.</span></span>
6. <span data-ttu-id="13611-127">Válassza ki a Bizonylatok keresése lehetőséget az összes jóváhagyható számla megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="13611-127">Select Find Vouchers to display all of the invoices that are ready for approval.</span></span>
7. <span data-ttu-id="13611-128">Jelölje ki a létrehozott számlát.</span><span class="sxs-lookup"><span data-stu-id="13611-128">Mark the invoice that you created.</span></span>
8. <span data-ttu-id="13611-129">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="13611-129">Click Select.</span></span>
    * <span data-ttu-id="13611-130">A fent kiválasztott bizonylatok erre a listára kerülnek.</span><span class="sxs-lookup"><span data-stu-id="13611-130">The vouchers that you selected above are moved to this list after you select them.</span></span>  
9. <span data-ttu-id="13611-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="13611-131">Click OK.</span></span>
10. <span data-ttu-id="13611-132">Kattintson a számlaszám mezőre, ha szeretne a számlához költségszámlát adni.</span><span class="sxs-lookup"><span data-stu-id="13611-132">Click on the account number field to add an expense account to the invoice.</span></span>
11. <span data-ttu-id="13611-133">Adjon meg egy számlaszámot és lépjen ki a mezőből.</span><span class="sxs-lookup"><span data-stu-id="13611-133">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="13611-134">Például írja be, hogy 600120.</span><span class="sxs-lookup"><span data-stu-id="13611-134">For example, enter 600120.</span></span>
12. <span data-ttu-id="13611-135">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="13611-135">Click Post.</span></span>
13. <span data-ttu-id="13611-136">Kattintson a Bizonylat lehetőségre, hogy megtekintse hova kerültek feladásra a bejegyzések.</span><span class="sxs-lookup"><span data-stu-id="13611-136">Click Voucher to view the entries that were posted.</span></span>
    * <span data-ttu-id="13611-137">A Függőben lévő számla visszavonásra kerül és egy tényleges költségszámla jön létre helyette.</span><span class="sxs-lookup"><span data-stu-id="13611-137">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  


