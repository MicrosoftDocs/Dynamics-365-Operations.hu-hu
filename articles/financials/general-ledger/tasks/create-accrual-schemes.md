--- 
title: "Könyvelési sémák létrehozása"
description: "Ez az útmutató bemutatja a könyvelési séma létrehozásának folyamatát."
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
ms.openlocfilehash: 324be23a1e26de0d05c7cf6a61567f7260d0c390
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-accrual-schemes"></a><span data-ttu-id="1ce8c-103">Könyvelési sémák létrehozása</span><span class="sxs-lookup"><span data-stu-id="1ce8c-103">Create accrual schemes</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1ce8c-104">Ez az útmutató bemutatja a könyvelési séma létrehozásának folyamatát.</span><span class="sxs-lookup"><span data-stu-id="1ce8c-104">This task guide steps through creating an accrual scheme.</span></span> <span data-ttu-id="1ce8c-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="1ce8c-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="1ce8c-106">Ugorjon a Főkönyv > Naplóbeállítások > Könyvelési sémák pontra.</span><span class="sxs-lookup"><span data-stu-id="1ce8c-106">Go to General ledger > Journal setup > Accrual schemes.</span></span>
2. <span data-ttu-id="1ce8c-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1ce8c-107">Click New.</span></span>
3. <span data-ttu-id="1ce8c-108">Írjon be egy értéket a Könyvelés azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1ce8c-108">In the Accrual identification field, type a value.</span></span>
4. <span data-ttu-id="1ce8c-109">A Könyvelési séma leírása mezőbe írja be az érték leírását.</span><span class="sxs-lookup"><span data-stu-id="1ce8c-109">In the Description of accrual scheme field, type a value.</span></span>
5. <span data-ttu-id="1ce8c-110">A Levonás mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="1ce8c-110">In the Debit field, specify the desired values.</span></span>
    * <span data-ttu-id="1ce8c-111">A megadott fő számla felülírja a tartozási fő számlát a naplóbizonylat sorában, és ezt használja majd a rendszer a halasztás sztornírozásához is, a főkönyvi könyvelési tranzakciókon alapján.</span><span class="sxs-lookup"><span data-stu-id="1ce8c-111">The main account defined will replace the debit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
6. <span data-ttu-id="1ce8c-112">A Jóváírás mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="1ce8c-112">In the Credit field, specify the desired values.</span></span>
    * <span data-ttu-id="1ce8c-113">A megadott fő számla felülírja a jóváírási fő számlát a naplóbizonylat sorában, és ezt használja majd a rendszer a halasztás sztornírozásához is, a főkönyvi könyvelési tranzakciókon alapján.</span><span class="sxs-lookup"><span data-stu-id="1ce8c-113">The main account defined will replace the credit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
7. <span data-ttu-id="1ce8c-114">A Bizonylat mezőben válassza ki, hogyan szeretné a bizonylatot meghatározni a tranzakcióinak feladása során.</span><span class="sxs-lookup"><span data-stu-id="1ce8c-114">In the Voucher field, select how you want the voucher determined when the transactions are posted.</span></span>
8. <span data-ttu-id="1ce8c-115">A Leírás mezőben adja meg a feladandó tranzakciók leírásához az értéket.</span><span class="sxs-lookup"><span data-stu-id="1ce8c-115">In the Description field, type a value to describe the transactions that will be posted.</span></span>
9. <span data-ttu-id="1ce8c-116">Az Időszak gyakorisága mezőben válassza ki, milyen gyakran történjenek a tranzakciók.</span><span class="sxs-lookup"><span data-stu-id="1ce8c-116">In the Period frequency field, select how often the transactions should occur.</span></span>
10. <span data-ttu-id="1ce8c-117">Adjon meg egy számot az Előfordulások száma időszak szerint mezőben.</span><span class="sxs-lookup"><span data-stu-id="1ce8c-117">In the Number of occurrences by period field, enter a number.</span></span>
11. <span data-ttu-id="1ce8c-118">A Tranzakciók feladása mezőben válassza ki, hogy mikor szeretné a tranzakciókat feladni, például a Havi értéket.</span><span class="sxs-lookup"><span data-stu-id="1ce8c-118">In the Post transactions field, select when the transactions should be posted, such as Monthly.</span></span>


