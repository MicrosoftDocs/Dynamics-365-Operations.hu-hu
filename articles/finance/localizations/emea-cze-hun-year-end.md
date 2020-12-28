---
title: Év végi zárás Magyarország és Csehország esetén
description: Ez a témakör információkat nyújt az év végi zárási folyamatról és a nyitó tranzakciókról Magyarország és Csehország esetén.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 05/18/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Czech Republic, Hungary
ms.author: epopov
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f4393931dd68a919b1c123a37bea4be82a068a2c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408057"
---
# <a name="year-end-close-for-czech-republic-and-hungary"></a><span data-ttu-id="9bd7e-103">Év végi zárás Magyarország és Csehország esetén</span><span class="sxs-lookup"><span data-stu-id="9bd7e-103">Year-end close for Czech Republic and Hungary</span></span>
[!include[banner](../includes/banner.md)]

<span data-ttu-id="9bd7e-104">Ez a témakör információkat nyújt az év végi zárási folyamatról és a nyitó tranzakciókról Magyarország és Csehország esetén.</span><span class="sxs-lookup"><span data-stu-id="9bd7e-104">This topic provides information about the year-end closing process and opening transactions for the Czech Republic and Hungary.</span></span> <span data-ttu-id="9bd7e-105">Ez a funkció lehetővé teszi, hogy a felhasználók beállítsák az év végi zárási folyamatot a következő módokon:</span><span class="sxs-lookup"><span data-stu-id="9bd7e-105">This functionality allows user to set up the year-end closing process in the following ways:</span></span>

-    <span data-ttu-id="9bd7e-106">Feladás különböző számlákra egyenlegszámlák megnyitásához és bezárásához.</span><span class="sxs-lookup"><span data-stu-id="9bd7e-106">Posting to different accounts for closing and opening of balance accounts.</span></span>
-    <span data-ttu-id="9bd7e-107">Év végi nyereség és veszteség eredmények átutalása az újonnan megnyitott évre egy másik számlára.</span><span class="sxs-lookup"><span data-stu-id="9bd7e-107">Transfer of profit or loss year-end result into the newly opened year to a different account.</span></span>

## <a name="year-end-closing-setup"></a><span data-ttu-id="9bd7e-108">Év végi zárás beállítása</span><span class="sxs-lookup"><span data-stu-id="9bd7e-108">Year-end closing setup</span></span>
<span data-ttu-id="9bd7e-109">A **Számlák automatikus tranzakciókhoz**  lapon megadhatja az év végi zárási folyamat során használt főkönyvi számlákat:</span><span class="sxs-lookup"><span data-stu-id="9bd7e-109">On the **Accounts for automatic transactions** page, you can specify the general ledger accounts to be used during the year-end closing process:</span></span>

-   <span data-ttu-id="9bd7e-110">Év végi eredmény – Ennek a számlának a segítségével történik használandó a nyereségi és veszteségi tranzakciók záróegyenlegének átutalása.</span><span class="sxs-lookup"><span data-stu-id="9bd7e-110">Year-end result – This account will be used for transferring the ending balances of profit and loss transactions.</span></span>
-   <span data-ttu-id="9bd7e-111">Záró és nyitó tranzakciók átutalása – Ennek a számlának a segítségével történik a mérlegszámlák záróegyenlegeinek átutalása.</span><span class="sxs-lookup"><span data-stu-id="9bd7e-111">Transfer of closing and opening transactions – This account will be used for transferring ending balances of balance sheet accounts.</span></span>

## <a name="opening-transactions-setup"></a><span data-ttu-id="9bd7e-112">Nyitó tranzakciók beállítása</span><span class="sxs-lookup"><span data-stu-id="9bd7e-112">Opening transactions setup</span></span>
<span data-ttu-id="9bd7e-113">Mielőtt feladhatna nyitó tranzakciókat különböző számlákra minden egyes fő számla esetében, meg kell adnia a főkönyvi számlát a **Nyitó számla** mezőben a fő számlánál.</span><span class="sxs-lookup"><span data-stu-id="9bd7e-113">Before you can post opening transactions to a different account for each of main accounts, you must specify the ledger account in the **Opening account** field on the main account.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9bd7e-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9bd7e-114">Additional resources</span></span>
[<span data-ttu-id="9bd7e-115">Év végi zárás</span><span class="sxs-lookup"><span data-stu-id="9bd7e-115">Year-end close</span></span>](../general-ledger/year-end-close.md)
