---
title: Elhatárolási sémák létrehozása
description: Ez a témakör bemutatja, hogyan kell könyvelési sémát létrehozni.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a83870c4cec4de2e51e90ff1889d4beff6c23f95
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444055"
---
# <a name="create-accrual-schemes"></a><span data-ttu-id="7160d-103">Elhatárolási sémák létrehozása</span><span class="sxs-lookup"><span data-stu-id="7160d-103">Create accrual schemes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7160d-104">Ez a témakör bemutatja, hogyan kell könyvelési sémát létrehozni.</span><span class="sxs-lookup"><span data-stu-id="7160d-104">This topic explains how to create an accrual scheme.</span></span> <span data-ttu-id="7160d-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="7160d-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="7160d-106">Nyissa meg a **Navigációs ablak > Modulok > Főkönyv > Napló beállítása > Könyvelési sémák** elemet.</span><span class="sxs-lookup"><span data-stu-id="7160d-106">Go to **Navigation pane > Modules > General ledger > Journal setup > Accrual schemes**.</span></span>
2. <span data-ttu-id="7160d-107">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7160d-107">Select **New**.</span></span>
3. <span data-ttu-id="7160d-108">Írjon be egy értéket a **Könyvelés azonosítója** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7160d-108">In the **Accrual identification** field, type a value.</span></span>
4. <span data-ttu-id="7160d-109">A **Könyvelési séma leírása** mezőbe írja be az érték leírását.</span><span class="sxs-lookup"><span data-stu-id="7160d-109">In the **Description of accrual scheme** field, type a value.</span></span>
5. <span data-ttu-id="7160d-110">A **Levonás** mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="7160d-110">In the **Debit** field, specify the desired values.</span></span> <span data-ttu-id="7160d-111">A megadott fő számla felülírja a tartozási fő számlát a naplóbizonylat sorában, és ezt használja majd a rendszer a halasztás sztornírozásához is, a főkönyvi könyvelési tranzakciókon alapján.</span><span class="sxs-lookup"><span data-stu-id="7160d-111">The main account defined will replace the debit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
6. <span data-ttu-id="7160d-112">A **Jóváírás** mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="7160d-112">In the **Credit** field, specify the desired values.</span></span> <span data-ttu-id="7160d-113">A megadott fő számla felülírja a jóváírási fő számlát a naplóbizonylat sorában, és ezt használja majd a rendszer a halasztás sztornírozásához is, a főkönyvi könyvelési tranzakciókon alapján.</span><span class="sxs-lookup"><span data-stu-id="7160d-113">The main account defined will replace the credit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
7. <span data-ttu-id="7160d-114">A **Bizonylat** mezőben válassza ki, hogyan szeretné a bizonylatot meghatározni a tranzakcióinak feladása során.</span><span class="sxs-lookup"><span data-stu-id="7160d-114">In the **Voucher** field, select how you want the voucher determined when the transactions are posted.</span></span>
8. <span data-ttu-id="7160d-115">A **Leírás** mezőben adja meg a feladandó tranzakciók leírásához az értéket.</span><span class="sxs-lookup"><span data-stu-id="7160d-115">In the **Description** field, type a value to describe the transactions that will be posted.</span></span>
9. <span data-ttu-id="7160d-116">Az **Időszak gyakorisága** mezőben válassza ki, milyen gyakran történjenek a tranzakciók.</span><span class="sxs-lookup"><span data-stu-id="7160d-116">In the **Period frequency** field, select how often the transactions should occur.</span></span>
10. <span data-ttu-id="7160d-117">Adjon meg egy számot az **Előfordulások száma időszak szerint** mezőben.</span><span class="sxs-lookup"><span data-stu-id="7160d-117">In the **Number of occurrences by period** field, enter a number.</span></span>
11. <span data-ttu-id="7160d-118">A **Tranzakciók feladása** mezőben válassza ki, hogy mikor szeretné a tranzakciókat feladni, például a **Havi** értéket.</span><span class="sxs-lookup"><span data-stu-id="7160d-118">In the **Post transactions** field, select when the transactions should be posted, such as **Monthly**.</span></span>

