--- 
title: "Főkönyvi felosztási napló feldolgozása"
description: "A Felosztási kérés feldolgozása lapon létrehozhat egy felosztási naplót, amelyet a főkönyvbe történő feladás előtt átnézhet és jóváhagyhat. Ha erre nincs szükség, a tranzakciókat közvetlenül is feladhatja a főkönyvbe."
author: aprilolson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7d299657758b1e1322aef07bfe8c71f7bf00b0ca
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="c3367-103">Főkönyvi felosztási napló feldolgozása</span><span class="sxs-lookup"><span data-stu-id="c3367-103">Process ledger allocation journal</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c3367-104">A Felosztási kérés feldolgozása lapon létrehozhat egy felosztási naplót, amelyet a főkönyvbe történő feladás előtt átnézhet és jóváhagyhat. Ha erre nincs szükség, a tranzakciókat közvetlenül is feladhatja a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="c3367-104">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="c3367-105">Felosztási napló létrehozásához előtt legalább egy aktív Főkönyvi felosztási szabályt be kell állítani.</span><span class="sxs-lookup"><span data-stu-id="c3367-105">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="c3367-106">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="c3367-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="c3367-107">Ugorjon a Főkönyv > Felosztások > Felosztási kérelem feldolgozása pontra.</span><span class="sxs-lookup"><span data-stu-id="c3367-107">Go to General ledger > Allocations > Process allocation request.</span></span>
2. <span data-ttu-id="c3367-108">A Szabály mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c3367-108">In the Rule field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="c3367-109">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="c3367-109">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="c3367-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="c3367-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="c3367-111">A Dátum szerint mezőbe írjon be egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="c3367-111">In the As of date field, enter a date.</span></span>
    * <span data-ttu-id="c3367-112">A Dátum szerint nagyon fontos, ha a szabályhoz tartozó adatforrás a Főkönyv.</span><span class="sxs-lookup"><span data-stu-id="c3367-112">The As of Date is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="c3367-113">Ez a dátum vezérli, hogy mely főkönyvi egyenlegeket szeretné felvenni a felosztáshoz.</span><span class="sxs-lookup"><span data-stu-id="c3367-113">This date controls which ledger balances to include for allocation.</span></span>     <span data-ttu-id="c3367-114">A Nulla forrásmezőben válassza ki a Stop elemet.</span><span class="sxs-lookup"><span data-stu-id="c3367-114">In the Zero source field select Stop.</span></span> <span data-ttu-id="c3367-115">Ezzel a felosztási folyamatot leállítja, és egy üzenet megjelenik arról, hogy a kiválasztott forrás összege nulla.</span><span class="sxs-lookup"><span data-stu-id="c3367-115">This will  Stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  
6. <span data-ttu-id="c3367-116">A Javaslati beállítások mezőben válassza ki a „Csak javaslat” elemet.</span><span class="sxs-lookup"><span data-stu-id="c3367-116">In the Proposal options field, select 'Proposal only'.</span></span>
    * <span data-ttu-id="c3367-117">Válassza a Csak javaslat lehetőséget, ha áttekintené és esetleg jóváhagyná a Felosztási naplók eredményét, mielőtt a felosztást a főkönyvbe feladja.</span><span class="sxs-lookup"><span data-stu-id="c3367-117">Select Proposal only to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
7. <span data-ttu-id="c3367-118">A GL feladási dátum mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="c3367-118">In the GL posting date field, enter a date.</span></span>
8. <span data-ttu-id="c3367-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c3367-119">Click OK.</span></span>
9. <span data-ttu-id="c3367-120">Ugorjon a Főkönyv > Felosztások > Felosztási naplók pontra.</span><span class="sxs-lookup"><span data-stu-id="c3367-120">Go to General ledger > Allocations > Allocation journals.</span></span>
10. <span data-ttu-id="c3367-121">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="c3367-121">Click Lines.</span></span>
11. <span data-ttu-id="c3367-122">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c3367-122">Click Post.</span></span>
12. <span data-ttu-id="c3367-123">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c3367-123">Click Post.</span></span>


