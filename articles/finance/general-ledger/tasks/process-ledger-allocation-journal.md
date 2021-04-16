---
title: Főkönyvi felosztási napló feldolgozása
description: Ez a cikk azt mutatja be, hogyan dolgozhatók fel a felosztási kérelmek a Dynamics 365 Finance rendszerben.
author: aprilolson
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e89aa21f988d50bc1a922e053be0ff2dcd196268
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834416"
---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="ad1d8-103">Főkönyvi felosztási napló feldolgozása</span><span class="sxs-lookup"><span data-stu-id="ad1d8-103">Process ledger allocation journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ad1d8-104">Ez a cikk azt mutatja be, hogyan dolgozhatók fel a felosztási kérelmek.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-104">This topic explains how to process an allocation request.</span></span> <span data-ttu-id="ad1d8-105">A Felosztási kérés feldolgozása lapon létrehozhat egy felosztási naplót, amelyet a főkönyvbe történő feladás előtt átnézhet és jóváhagyhat. Ha erre nincs szükség, a tranzakciókat közvetlenül is feladhatja a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-105">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="ad1d8-106">Felosztási napló létrehozásához előtt legalább egy aktív Főkönyvi felosztási szabályt be kell állítani.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-106">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="ad1d8-107">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="ad1d8-108">A navigációs ablakban lépjen a **Modulok > Főkönyv > Felosztások > Felosztási kérés feldolgozása** részre.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-108">In the navigation pane, go to **Modules > General ledger > Allocations > Process allocation request**.</span></span>
2. <span data-ttu-id="ad1d8-109">A **Szabály** mező legördülő mezőjében válassza ki a kívánt rekordot.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-109">In the **Rule** field, select the desired record in the drop-down menu.</span></span>
3. <span data-ttu-id="ad1d8-110">A **Dátum szerint** mezőbe írjon be egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-110">In the **As of date** field, enter a date.</span></span>

    - <span data-ttu-id="ad1d8-111">A **Dátum szerint** beállítás nagyon fontos, ha a szabályhoz tartozó adatforrás a főkönyv.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-111">The **As of Date** is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="ad1d8-112">Ez a dátum vezérli, hogy mely főkönyvi egyenlegeket szeretné felvenni a felosztáshoz.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-112">This date controls which ledger balances to include for allocation.</span></span>  
    - <span data-ttu-id="ad1d8-113">A **Nulla forrás** mezőben válassza ki a **Leállítás** elemet.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-113">In the **Zero source** field select **Stop**.</span></span> <span data-ttu-id="ad1d8-114">Ezzel leállítja a felosztási folyamatot, és egy üzenet jelenik meg arról, hogy a forrás kiválasztott összege nulla.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-114">This will stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  

4. <span data-ttu-id="ad1d8-115">A **Javaslatbeállítások** mezőben válassza a **Csak javaslat** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-115">In the **Proposal options** field, select **Proposal only**.</span></span> <span data-ttu-id="ad1d8-116">Akkor válassza a **Csak javaslat** lehetőséget, ha áttekintené és esetleg jóváhagyná a Felosztási naplók eredményét, mielőtt feladja a felosztást a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-116">Select **Proposal only** to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
5. <span data-ttu-id="ad1d8-117">A GL feladási dátum mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-117">In the GL posting date field, enter a date.</span></span>
6. <span data-ttu-id="ad1d8-118">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-118">Select **OK**.</span></span>
7. <span data-ttu-id="ad1d8-119">A navigációs ablakban lépjen a **Modulok > Főkönyv > Felosztások > Felosztási naplók** részre.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-119">In the navigation pane, go to **Modules > General ledger > Allocations > Allocation journals**.</span></span>
8. <span data-ttu-id="ad1d8-120">**Sorok** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-120">Select **Lines**.</span></span>
9. <span data-ttu-id="ad1d8-121">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-121">Select **Post**.</span></span>
10. <span data-ttu-id="ad1d8-122">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ad1d8-122">Select **Post**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]