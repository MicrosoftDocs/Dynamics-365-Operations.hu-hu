---
title: Főkönyvi kivonat pénzügyi jelentés
description: Ez a cikk a főkönyvi kivonatok alapértelmezett jelentéseit mutatja be. Ismerteti továbbá azokat az építőelemeket, amelyek ezekhez a jelentésekhez kapcsolódnak, illetve beszámol arról, hogy miként módosíthatja a jelentéseket, hogy azok megfeleljenek az üzleti követelményeinek.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b48510febf5a5f9f4a01728b242d9750b3c62c2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443827"
---
# <a name="trial-balance-financial-reports"></a><span data-ttu-id="12315-104">Főkönyvi kivonat pénzügyi jelentés</span><span class="sxs-lookup"><span data-stu-id="12315-104">Trial balance financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="12315-105">Ez a cikk a főkönyvi kivonatok alapértelmezett jelentéseit mutatja be.</span><span class="sxs-lookup"><span data-stu-id="12315-105">This article describes the default reports for trial balances.</span></span> <span data-ttu-id="12315-106">Ismerteti továbbá azokat az építőelemeket, amelyek ezekhez a jelentésekhez kapcsolódnak, illetve beszámol arról, hogy miként módosíthatja a jelentéseket, hogy azok megfeleljenek az üzleti követelményeinek.</span><span class="sxs-lookup"><span data-stu-id="12315-106">It also describes the building blocks that are associated with these reports and how you can modify the reports to fit your business requirements.</span></span> 

<a name="default-trial-balance-reports"></a><span data-ttu-id="12315-107">Alapértelmezett főkönyvi kivonat jelentés</span><span class="sxs-lookup"><span data-stu-id="12315-107">Default trial balance reports</span></span>
-----------------------------

<span data-ttu-id="12315-108">A Pénzügyi jelentéskészítésben három főkönyvi kivonatra vonatkozó jelentés áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="12315-108">Three trial balance reports are available in Financial reporting.</span></span>

| <span data-ttu-id="12315-109">Alapértelmezett jelentés</span><span class="sxs-lookup"><span data-stu-id="12315-109">Default report</span></span>                                 | <span data-ttu-id="12315-110">Mire szolgál?</span><span class="sxs-lookup"><span data-stu-id="12315-110">What it does</span></span>                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="12315-111">Részletes főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="12315-111">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="12315-112">Egyenleginformációkat ad minden olyan számlához, amely hitel- vagy bankkártya egyenleggel rendelkezik, valamint ezen egyenlegek nettó értéke, a tranzakció dátumával, a bizonylattal és a napló leírással együtt.</span><span class="sxs-lookup"><span data-stu-id="12315-112">Provides balance information for all accounts, and includes debit and credit balances, and the net of these, together with the transaction date, voucher, and journal description.</span></span>                  |
| <span data-ttu-id="12315-113">Összegző főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="12315-113">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="12315-114">Egyenleg-adatokat ad az összes számlához, amelyekhez nyitó és záró egyenleg tartozik, hitel- vagy bankkártya egyenleggel rendelkeznek nettó eltéréssel.</span><span class="sxs-lookup"><span data-stu-id="12315-114">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference.</span></span>                                        |
| <span data-ttu-id="12315-115">Éves összegző főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="12315-115">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="12315-116">Az egyenleg-adatokat ad az összes olyan számlához, amelyekhez nyitó és záró egyenleg tartozik, hitel- vagy bankkártya egyenleggel rendelkeznek nettó eltéréssel.</span><span class="sxs-lookup"><span data-stu-id="12315-116">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference for the current year and the past year.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="12315-117">Építőelemek</span><span class="sxs-lookup"><span data-stu-id="12315-117">Building blocks</span></span>
<span data-ttu-id="12315-118">A főkönyvi kivonat pénzügyi jelentések a következő építőelemekből állnak.</span><span class="sxs-lookup"><span data-stu-id="12315-118">The trial balance financial reports use the following building blocks.</span></span>

| <span data-ttu-id="12315-119">Alapértelmezett jelentés</span><span class="sxs-lookup"><span data-stu-id="12315-119">Default report</span></span>                                 | <span data-ttu-id="12315-120">Sor definíciója</span><span class="sxs-lookup"><span data-stu-id="12315-120">Row definition</span></span>          | <span data-ttu-id="12315-121">Oszlopdefiníció</span><span class="sxs-lookup"><span data-stu-id="12315-121">Column definition</span></span>                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| <span data-ttu-id="12315-122">Részletes főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="12315-122">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="12315-123">Főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="12315-123">Trial Balance - Default</span></span> | <span data-ttu-id="12315-124">Részletes főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="12315-124">Detailed Trial Balance - Default</span></span>               |
| <span data-ttu-id="12315-125">Összegző főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="12315-125">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="12315-126">Főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="12315-126">Trial Balance - Default</span></span> | <span data-ttu-id="12315-127">Összegző főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="12315-127">Summary Trial Balance - Default</span></span>                |
| <span data-ttu-id="12315-128">Éves összegző főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="12315-128">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="12315-129">Főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="12315-129">Trial Balance - Default</span></span> | <span data-ttu-id="12315-130">Éves összegző főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="12315-130">Summary Trial Balance Year Over Year - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="12315-131">Sor definíciója</span><span class="sxs-lookup"><span data-stu-id="12315-131">Row definition</span></span>

<span data-ttu-id="12315-132">A sordefiníció, Főkönyvi kivonat – Alapértelmezett, egy sort tartalmaz, amely behúzza az összes fő számlát.</span><span class="sxs-lookup"><span data-stu-id="12315-132">The row definition, Trial Balance – Default, contains a single row that pulls in all main accounts.</span></span> <span data-ttu-id="12315-133">Ezért bárki létrehozhat jelentést anélkül, hogy módosításokat végezne.</span><span class="sxs-lookup"><span data-stu-id="12315-133">Therefore, anyone can generate the report without having to make any modifications.</span></span> <span data-ttu-id="12315-134">A jelentés megtekintésekor, láshat egy sorhoz, az egyes számlák részleteinek megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="12315-134">When you view the report, you drill into the single row to see details about each account.</span></span> <span data-ttu-id="12315-135">Módosíthatja a sordefiníciót, hogy további részleteket tartalmazzon.</span><span class="sxs-lookup"><span data-stu-id="12315-135">You can modify the row definition so that it includes more detail.</span></span> <span data-ttu-id="12315-136">A főkönyvi kivonat módosítása – Alapértelmezett sordefiníció, ezért tartalmazza az összes számla sorait, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="12315-136">To modify the Trial Balance – Default row definition so that it includes rows for all accounts, follow these steps.</span></span>

1.  <span data-ttu-id="12315-137">Kattintson a **Szerkesztés** lehetőségre, majd kattintson a **Sorok beszúrása dimenziókból** elemre.</span><span class="sxs-lookup"><span data-stu-id="12315-137">Click **Edit**, and then click **Insert Rows from Dimensions**.</span></span> <span data-ttu-id="12315-138">A **Sorok beszúrása dimenziókból** parancs segítségével kiválaszthatja, milyen dimenziókat szeretne a sordefiníciójában.</span><span class="sxs-lookup"><span data-stu-id="12315-138">The **Insert Rows from Dimensions** command lets you choose the dimensions that you want to have in your row definition.</span></span> <span data-ttu-id="12315-139">Ehhez a sordefinícióhoz a **Fő számlát** fogja használni.</span><span class="sxs-lookup"><span data-stu-id="12315-139">For this row definition, you're going to use **Main Account**.</span></span>
2.  <span data-ttu-id="12315-140">Győződjön meg róla, hogy a **Fő számla** tartalmaz minden és-jelet (&), majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="12315-140">Make sure that **Main Account** contains all ampersands (&), and then click **OK**.</span></span>

<span data-ttu-id="12315-141">A sordefiníció most tartalmazza az alapértelmezett jogi személy minden fő számláját.</span><span class="sxs-lookup"><span data-stu-id="12315-141">The row definition now contains all the main accounts for your default legal entity.</span></span>

### <a name="column-definition"></a><span data-ttu-id="12315-142">Oszlopdefiníció</span><span class="sxs-lookup"><span data-stu-id="12315-142">Column definition</span></span>

<span data-ttu-id="12315-143">Minden egyes főkönyvi kivonati jelentés külön oszlopdefiníciót használ.</span><span class="sxs-lookup"><span data-stu-id="12315-143">Each trial balance report uses a different column definition.</span></span> <span data-ttu-id="12315-144">Ezek az oszlopdefiníciók tartalmaznak különböző típusú oszlopokot, a különböző szintű részletességre és pénzügyi adatokra.</span><span class="sxs-lookup"><span data-stu-id="12315-144">These column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="12315-145">**Részletes főkönyvi kivonat – Alapértelmezett oszloptípusok:**</span><span class="sxs-lookup"><span data-stu-id="12315-145">**Detailed Trial Balance – Default column types:**</span></span>
    -   <span data-ttu-id="12315-146">**DESC** – A leírás a sordefinícióból</span><span class="sxs-lookup"><span data-stu-id="12315-146">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="12315-147">**ACCT** – Számlakódok</span><span class="sxs-lookup"><span data-stu-id="12315-147">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="12315-148">**ATTR (3)** – Attribútumok:</span><span class="sxs-lookup"><span data-stu-id="12315-148">**ATTR (3)** – Attributes:</span></span>
        -   <span data-ttu-id="12315-149">Tranzakció dátuma</span><span class="sxs-lookup"><span data-stu-id="12315-149">Transaction Date</span></span>
        -   <span data-ttu-id="12315-150">Bizonylat</span><span class="sxs-lookup"><span data-stu-id="12315-150">Voucher</span></span>
        -   <span data-ttu-id="12315-151">Napló leírása</span><span class="sxs-lookup"><span data-stu-id="12315-151">Journal Description</span></span>
    -   <span data-ttu-id="12315-152">**FD** – Csak kötelezettségeket tartalmazó pénzügyi adat</span><span class="sxs-lookup"><span data-stu-id="12315-152">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="12315-153">**FD** – Csak jóváírásokat tartalmazó pénzügyi adat</span><span class="sxs-lookup"><span data-stu-id="12315-153">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="12315-154">**CALC** – Nettó eltérés</span><span class="sxs-lookup"><span data-stu-id="12315-154">**CALC** – The net difference</span></span>
-   <span data-ttu-id="12315-155">**Összesítő főkönyvi kivonat – Alapértelmezett oszloptípusok:**</span><span class="sxs-lookup"><span data-stu-id="12315-155">**Summary Trial Balance – Default columns types:**</span></span>
    -   <span data-ttu-id="12315-156">**ACCT** – Számlakódok</span><span class="sxs-lookup"><span data-stu-id="12315-156">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="12315-157">**DESC** – A leírás a sordefinícióból</span><span class="sxs-lookup"><span data-stu-id="12315-157">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="12315-158">**ATTR** – Egy attribútum:</span><span class="sxs-lookup"><span data-stu-id="12315-158">**ATTR** – An attribute:</span></span>
        -   <span data-ttu-id="12315-159">Bizonylat</span><span class="sxs-lookup"><span data-stu-id="12315-159">Voucher</span></span>
    -   <span data-ttu-id="12315-160">**FD** – A pénzügyi adatok kezdőegyenlege</span><span class="sxs-lookup"><span data-stu-id="12315-160">**FD** – The beginning balance financial data</span></span>
    -   <span data-ttu-id="12315-161">**FD** – Csak kötelezettségeket tartalmazó pénzügyi adat</span><span class="sxs-lookup"><span data-stu-id="12315-161">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="12315-162">**FD** – Csak jóváírásokat tartalmazó pénzügyi adat</span><span class="sxs-lookup"><span data-stu-id="12315-162">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="12315-163">**CALC** – Nettó eltérés</span><span class="sxs-lookup"><span data-stu-id="12315-163">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="12315-164">**CALC** – Záró egyenleg</span><span class="sxs-lookup"><span data-stu-id="12315-164">**CALC** – The closing balance</span></span>
-   <span data-ttu-id="12315-165">**Éves összegző főkönyvi kivonat – Alapértelmezett:**</span><span class="sxs-lookup"><span data-stu-id="12315-165">**Summary Trial Balance Year Over Year – Default:**</span></span>
    -   <span data-ttu-id="12315-166">**ACCT** – Számlakódok</span><span class="sxs-lookup"><span data-stu-id="12315-166">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="12315-167">**DESC** – A leírás a sordefinícióból</span><span class="sxs-lookup"><span data-stu-id="12315-167">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="12315-168">**ATTR** – Egy attribútum</span><span class="sxs-lookup"><span data-stu-id="12315-168">**ATTR** – An attribute</span></span>
        -   <span data-ttu-id="12315-169">Bizonylat</span><span class="sxs-lookup"><span data-stu-id="12315-169">Voucher</span></span>
    -   <span data-ttu-id="12315-170">**FD** – A folyó év kezdő egyenleg pénzügyi adata</span><span class="sxs-lookup"><span data-stu-id="12315-170">**FD** – The beginning balance financial data for the current year</span></span>
    -   <span data-ttu-id="12315-171">**FD** – A folyó évre csak kötelezettségeket tartalmazó pénzügyi adatok</span><span class="sxs-lookup"><span data-stu-id="12315-171">**FD** – Financial data that contains only debits for the current year</span></span>
    -   <span data-ttu-id="12315-172">**FD** – A folyó évre csak jóváírásokat tartalmazó pénzügyi adatok</span><span class="sxs-lookup"><span data-stu-id="12315-172">**FD** – Financial data that contains only credits for the current year</span></span>
    -   <span data-ttu-id="12315-173">**CALC** – Nettó eltérés</span><span class="sxs-lookup"><span data-stu-id="12315-173">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="12315-174">**CALC** – Záró egyenleg</span><span class="sxs-lookup"><span data-stu-id="12315-174">**CALC** – The closing balance</span></span>
    -   <span data-ttu-id="12315-175">**FD** – A előző évre csak kötelezettségeket tartalmazó pénzügyi adatok</span><span class="sxs-lookup"><span data-stu-id="12315-175">**FD** – Financial data that contains only debits for the last year</span></span>
    -   <span data-ttu-id="12315-176">**FD** – A előző évre csak jóváírásokat tartalmazó pénzügyi adatok</span><span class="sxs-lookup"><span data-stu-id="12315-176">**FD** – Financial data that contains only credits for the last year</span></span>



<a name="additional-resources"></a><span data-ttu-id="12315-177">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="12315-177">Additional resources</span></span>
--------

[<span data-ttu-id="12315-178">Pénzügyi jelentéskészítés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="12315-178">Financial reporting overview</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="12315-179">Pénzügyi jelentések megtekintése</span><span class="sxs-lookup"><span data-stu-id="12315-179">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="12315-180">Dynamics Pénzügyi jelentések blog</span><span class="sxs-lookup"><span data-stu-id="12315-180">Dynamics Financial Reporting Blog</span></span>](https://blogs.msdn.com/b/dynamics_financial_reporting/)



