---
title: Könyvelési sémák létrehozása
description: Ez az útmutató bemutatja a könyvelési séma létrehozásának folyamatát.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: e0ae55000a5cf1593d057d940dc3dbbf9e5cb3f3
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834885"
---
# <a name="create-accrual-schemes"></a><span data-ttu-id="f1aea-103">Könyvelési sémák létrehozása</span><span class="sxs-lookup"><span data-stu-id="f1aea-103">Create accrual schemes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f1aea-104">Ez az útmutató bemutatja a könyvelési séma létrehozásának folyamatát.</span><span class="sxs-lookup"><span data-stu-id="f1aea-104">This task guide steps through creating an accrual scheme.</span></span> <span data-ttu-id="f1aea-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="f1aea-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="f1aea-106">Ugorjon a Főkönyv > Naplóbeállítások > Könyvelési sémák pontra.</span><span class="sxs-lookup"><span data-stu-id="f1aea-106">Go to General ledger > Journal setup > Accrual schemes.</span></span>
2. <span data-ttu-id="f1aea-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f1aea-107">Click New.</span></span>
3. <span data-ttu-id="f1aea-108">Írjon be egy értéket a Könyvelés azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f1aea-108">In the Accrual identification field, type a value.</span></span>
4. <span data-ttu-id="f1aea-109">A Könyvelési séma leírása mezőbe írja be az érték leírását.</span><span class="sxs-lookup"><span data-stu-id="f1aea-109">In the Description of accrual scheme field, type a value.</span></span>
5. <span data-ttu-id="f1aea-110">A Levonás mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="f1aea-110">In the Debit field, specify the desired values.</span></span>
    * <span data-ttu-id="f1aea-111">A megadott fő számla felülírja a tartozási fő számlát a naplóbizonylat sorában, és ezt használja majd a rendszer a halasztás sztornírozásához is, a főkönyvi könyvelési tranzakciókon alapján.</span><span class="sxs-lookup"><span data-stu-id="f1aea-111">The main account defined will replace the debit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
6. <span data-ttu-id="f1aea-112">A Jóváírás mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="f1aea-112">In the Credit field, specify the desired values.</span></span>
    * <span data-ttu-id="f1aea-113">A megadott fő számla felülírja a jóváírási fő számlát a naplóbizonylat sorában, és ezt használja majd a rendszer a halasztás sztornírozásához is, a főkönyvi könyvelési tranzakciókon alapján.</span><span class="sxs-lookup"><span data-stu-id="f1aea-113">The main account defined will replace the credit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
7. <span data-ttu-id="f1aea-114">A Bizonylat mezőben válassza ki, hogyan szeretné a bizonylatot meghatározni a tranzakcióinak feladása során.</span><span class="sxs-lookup"><span data-stu-id="f1aea-114">In the Voucher field, select how you want the voucher determined when the transactions are posted.</span></span>
8. <span data-ttu-id="f1aea-115">A Leírás mezőben adja meg a feladandó tranzakciók leírásához az értéket.</span><span class="sxs-lookup"><span data-stu-id="f1aea-115">In the Description field, type a value to describe the transactions that will be posted.</span></span>
9. <span data-ttu-id="f1aea-116">Az Időszak gyakorisága mezőben válassza ki, milyen gyakran történjenek a tranzakciók.</span><span class="sxs-lookup"><span data-stu-id="f1aea-116">In the Period frequency field, select how often the transactions should occur.</span></span>
10. <span data-ttu-id="f1aea-117">Adjon meg egy számot az Előfordulások száma időszak szerint mezőben.</span><span class="sxs-lookup"><span data-stu-id="f1aea-117">In the Number of occurrences by period field, enter a number.</span></span>
11. <span data-ttu-id="f1aea-118">A Tranzakciók feladása mezőben válassza ki, hogy mikor szeretné a tranzakciókat feladni, például a Havi értéket.</span><span class="sxs-lookup"><span data-stu-id="f1aea-118">In the Post transactions field, select when the transactions should be posted, such as Monthly.</span></span>

