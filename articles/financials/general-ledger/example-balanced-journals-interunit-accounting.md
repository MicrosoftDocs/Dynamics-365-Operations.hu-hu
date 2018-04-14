---
title: "Kiegyensúlyozott naplók egységközi számlázáshoz"
description: "Ez a cikk ismerteti, hogyan történik a napló automatikus kiegyensúlyozása a főkönyvi oldalon található kiegyenlítő pénzügyi dimenzió kijelölésekor."
author: twheeloc
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 74a55b66df63f84c6cb6926b56c4b7395b895740
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="balanced-journals-for-interunit-accounting"></a><span data-ttu-id="24bdd-103">Kiegyensúlyozott naplók egységközi számlázáshoz</span><span class="sxs-lookup"><span data-stu-id="24bdd-103">Balanced journals for interunit accounting</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="24bdd-104">Ez a cikk ismerteti, hogyan történik a napló automatikus kiegyensúlyozása a főkönyvi oldalon található kiegyenlítő pénzügyi dimenzió kijelölésekor.</span><span class="sxs-lookup"><span data-stu-id="24bdd-104">This article shows how a journal is automatically balanced when a balancing financial dimension is selected on the Ledger page.</span></span> 

<span data-ttu-id="24bdd-105">Ha a könyvelési bejegyzések a pénzügyi dimenzióértékek szintjén nem kiegyenlítettek, akkor automatikusan további könyvelési bejegyzéseket hoz létre a rendszer a napló kiegyensúlyozása érdekében.</span><span class="sxs-lookup"><span data-stu-id="24bdd-105">If account entries don't balance at the level of the financial dimension values, additional account entries are created automatically to balance the journal.</span></span> <span data-ttu-id="24bdd-106">Ezek a számlatételek az **Egységközi - tartozás** és**Egységközi - jóváírás** feladási típusokat használják a **Számlák automatikus tranzakciókhoz** lapon a fő számla meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="24bdd-106">These account entries use the **Interunit - debit** and **Interunit - credit** posting types on the **Accounts for automatic transactions** page to determine the main account.</span></span> <span data-ttu-id="24bdd-107">Például az Üzleti egység, amely a második szegmens a főkönyvi számlában, a kiegyenlítő pénzügyi dimenzióként van kiválasztva, és a következő könyvelési tételek lesznek elkészítve.</span><span class="sxs-lookup"><span data-stu-id="24bdd-107">For example, Business Unit, which is the second segment of the ledger account, is selected as the balancing financial dimension, and the following accounting entries are about to be created.</span></span>

|                      |           |
|----------------------|-----------|
| <span data-ttu-id="24bdd-108">6100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="24bdd-108">6100 – MSP – OU\_256</span></span> | <span data-ttu-id="24bdd-109">100,00 TARTOZÁS</span><span class="sxs-lookup"><span data-stu-id="24bdd-109">100.00 DR</span></span> |
| <span data-ttu-id="24bdd-110">6100 – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="24bdd-110">6100 – NY – OU\_249</span></span>  | <span data-ttu-id="24bdd-111">100,00 TARTOZÁS</span><span class="sxs-lookup"><span data-stu-id="24bdd-111">100.00 DR</span></span> |
| <span data-ttu-id="24bdd-112">2100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="24bdd-112">2100 – MSP – OU\_256</span></span> | <span data-ttu-id="24bdd-113">200.00 CR</span><span class="sxs-lookup"><span data-stu-id="24bdd-113">200.00 CR</span></span> |

<span data-ttu-id="24bdd-114">Ebben az esetben a következő egyenlegek vannak meghatározva:</span><span class="sxs-lookup"><span data-stu-id="24bdd-114">In this case, the following balances are determined:</span></span>

-   <span data-ttu-id="24bdd-115">Üzleti egység – MSP = 100.00 CR</span><span class="sxs-lookup"><span data-stu-id="24bdd-115">For Business Unit MSP = 100.00 CR</span></span>
-   <span data-ttu-id="24bdd-116">Üzleti egység – NY = 100.00 DR</span><span class="sxs-lookup"><span data-stu-id="24bdd-116">For Business Unit NY = 100.00 DR</span></span>

<span data-ttu-id="24bdd-117">Ezért a következő könyvelési bejegyzések automatikusan létrejönnek a napló kiegyenlítésére a pénzügyi dimenzió értékeinek szintjén.</span><span class="sxs-lookup"><span data-stu-id="24bdd-117">Therefore, the following accounting entries are created automatically to balance the  journal at the level of the financial dimension values.</span></span>

|                                   |           |
|-----------------------------------|-----------|
| <span data-ttu-id="24bdd-118">(Egységközi - terhelés) – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="24bdd-118">(Interunit Debit) – MSP – OU\_256</span></span> | <span data-ttu-id="24bdd-119">100,00 TARTOZÁS</span><span class="sxs-lookup"><span data-stu-id="24bdd-119">100.00 DR</span></span> |
| <span data-ttu-id="24bdd-120">(Egységközi - jóváírás) – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="24bdd-120">(Interunit Credit) – NY – OU\_249</span></span> | <span data-ttu-id="24bdd-121">100.00 CR</span><span class="sxs-lookup"><span data-stu-id="24bdd-121">100.00 CR</span></span> |






