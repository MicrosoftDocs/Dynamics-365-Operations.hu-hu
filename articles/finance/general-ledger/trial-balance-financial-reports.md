---
title: Főkönyvi kivonat pénzügyi jelentés
description: Ez a cikk a főkönyvi kivonatok alapértelmezett jelentéseit mutatja be. Ismerteti továbbá azokat az építőelemeket, amelyek ezekhez a jelentésekhez kapcsolódnak, illetve beszámol arról, hogy miként módosíthatja a jelentéseket, hogy azok megfeleljenek az üzleti követelményeinek.
author: jinniew
ms.date: 05/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26ec03422315a280f7e779f992cf694eb5f845ea
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103658"
---
# <a name="trial-balance-financial-reports"></a><span data-ttu-id="f8407-104">Főkönyvi kivonat pénzügyi jelentés</span><span class="sxs-lookup"><span data-stu-id="f8407-104">Trial balance financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f8407-105">Ez a cikk a főkönyvi kivonatok alapértelmezett jelentéseit mutatja be.</span><span class="sxs-lookup"><span data-stu-id="f8407-105">This article describes the default reports for trial balances.</span></span> <span data-ttu-id="f8407-106">Ismerteti továbbá azokat az építőelemeket, amelyek ezekhez a jelentésekhez kapcsolódnak, illetve beszámol arról, hogy miként módosíthatja a jelentéseket, hogy azok megfeleljenek az üzleti követelményeinek.</span><span class="sxs-lookup"><span data-stu-id="f8407-106">It also describes the building blocks that are associated with these reports and how you can modify the reports to fit your business requirements.</span></span> 

## <a name="default-trial-balance-reports"></a><span data-ttu-id="f8407-107">Alapértelmezett főkönyvi kivonat jelentés</span><span class="sxs-lookup"><span data-stu-id="f8407-107">Default trial balance reports</span></span>

<span data-ttu-id="f8407-108">A Pénzügyi jelentéskészítésben három főkönyvi kivonatra vonatkozó jelentés áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="f8407-108">Three trial balance reports are available in Financial reporting.</span></span>

| <span data-ttu-id="f8407-109">Alapértelmezett jelentés</span><span class="sxs-lookup"><span data-stu-id="f8407-109">Default report</span></span>                                 | <span data-ttu-id="f8407-110">Mire szolgál?</span><span class="sxs-lookup"><span data-stu-id="f8407-110">What it does</span></span>                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f8407-111">Részletes főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="f8407-111">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="f8407-112">Egyenleginformációkat ad minden olyan számlához, amely hitel- vagy bankkártya egyenleggel rendelkezik, valamint ezen egyenlegek nettó értéke, a tranzakció dátumával, a bizonylattal és a napló leírással együtt.</span><span class="sxs-lookup"><span data-stu-id="f8407-112">Provides balance information for all accounts, and includes debit and credit balances, and the net of these, together with the transaction date, voucher, and journal description.</span></span>                  |
| <span data-ttu-id="f8407-113">Összegző főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="f8407-113">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="f8407-114">Egyenleg-adatokat ad az összes számlához, amelyekhez nyitó és záró egyenleg tartozik, hitel- vagy bankkártya egyenleggel rendelkeznek nettó eltéréssel.</span><span class="sxs-lookup"><span data-stu-id="f8407-114">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference.</span></span>                                        |
| <span data-ttu-id="f8407-115">Éves összegző főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="f8407-115">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="f8407-116">Az egyenleg-adatokat ad az összes olyan számlához, amelyekhez nyitó és záró egyenleg tartozik, hitel- vagy bankkártya egyenleggel rendelkeznek nettó eltéréssel.</span><span class="sxs-lookup"><span data-stu-id="f8407-116">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference for the current year and the past year.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="f8407-117">Építőelemek</span><span class="sxs-lookup"><span data-stu-id="f8407-117">Building blocks</span></span>
<span data-ttu-id="f8407-118">A főkönyvi kivonat pénzügyi jelentések a következő építőelemekből állnak.</span><span class="sxs-lookup"><span data-stu-id="f8407-118">The trial balance financial reports use the following building blocks.</span></span>

| <span data-ttu-id="f8407-119">Alapértelmezett jelentés</span><span class="sxs-lookup"><span data-stu-id="f8407-119">Default report</span></span>                                 | <span data-ttu-id="f8407-120">Sor definíciója</span><span class="sxs-lookup"><span data-stu-id="f8407-120">Row definition</span></span>          | <span data-ttu-id="f8407-121">Oszlopdefiníció</span><span class="sxs-lookup"><span data-stu-id="f8407-121">Column definition</span></span>                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| <span data-ttu-id="f8407-122">Részletes főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="f8407-122">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="f8407-123">Főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="f8407-123">Trial Balance - Default</span></span> | <span data-ttu-id="f8407-124">Részletes főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="f8407-124">Detailed Trial Balance - Default</span></span>               |
| <span data-ttu-id="f8407-125">Összegző főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="f8407-125">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="f8407-126">Főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="f8407-126">Trial Balance - Default</span></span> | <span data-ttu-id="f8407-127">Összegző főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="f8407-127">Summary Trial Balance - Default</span></span>                |
| <span data-ttu-id="f8407-128">Éves összegző főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="f8407-128">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="f8407-129">Főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="f8407-129">Trial Balance - Default</span></span> | <span data-ttu-id="f8407-130">Éves összegző főkönyvi kivonat – Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="f8407-130">Summary Trial Balance Year Over Year - Default</span></span> |

> [!NOTE] 
> <span data-ttu-id="f8407-131">Amikor a Financial Reporting szolgáltatásban futtatja a **Főkönyvi kivonat** jelentést, akkor legyen bejelölve az **Összegek nélküli sorok megjelenítése** és az **Aktív sorok nélküli jelentések megjelenítése** jelölőnégyzetet a **Beállítások** lapon.</span><span class="sxs-lookup"><span data-stu-id="f8407-131">When running the **Trial Balance** report in Financial reporting, be sure to select the check boxes for **Display rows with no amounts** and **Display reports with no active rows** on the **Settings** tab.</span></span>

### <a name="row-definition"></a><span data-ttu-id="f8407-132">Sor definíciója</span><span class="sxs-lookup"><span data-stu-id="f8407-132">Row definition</span></span>

<span data-ttu-id="f8407-133">A sordefiníció, Főkönyvi kivonat – Alapértelmezett, egy sort tartalmaz, amely behúzza az összes fő számlát.</span><span class="sxs-lookup"><span data-stu-id="f8407-133">The row definition, Trial Balance – Default, contains a single row that pulls in all main accounts.</span></span> <span data-ttu-id="f8407-134">Ezért bárki létrehozhat jelentést anélkül, hogy módosításokat végezne.</span><span class="sxs-lookup"><span data-stu-id="f8407-134">Therefore, anyone can generate the report without having to make any modifications.</span></span> <span data-ttu-id="f8407-135">A jelentés megtekintésekor, láshat egy sorhoz, az egyes számlák részleteinek megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="f8407-135">When you view the report, you drill into the single row to see details about each account.</span></span> <span data-ttu-id="f8407-136">Módosíthatja a sordefiníciót, hogy további részleteket tartalmazzon.</span><span class="sxs-lookup"><span data-stu-id="f8407-136">You can modify the row definition so that it includes more detail.</span></span> <span data-ttu-id="f8407-137">A főkönyvi kivonat módosítása – Alapértelmezett sordefiníció, ezért tartalmazza az összes számla sorait, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f8407-137">To modify the Trial Balance – Default row definition so that it includes rows for all accounts, follow these steps.</span></span>

1.  <span data-ttu-id="f8407-138">Kattintson a **Szerkesztés** lehetőségre, majd kattintson a **Sorok beszúrása dimenziókból** elemre.</span><span class="sxs-lookup"><span data-stu-id="f8407-138">Click **Edit**, and then click **Insert Rows from Dimensions**.</span></span> <span data-ttu-id="f8407-139">A **Sorok beszúrása dimenziókból** parancs segítségével kiválaszthatja, milyen dimenziókat szeretne a sordefiníciójában.</span><span class="sxs-lookup"><span data-stu-id="f8407-139">The **Insert Rows from Dimensions** command lets you choose the dimensions that you want to have in your row definition.</span></span> <span data-ttu-id="f8407-140">Ehhez a sordefinícióhoz a **Fő számlát** fogja használni.</span><span class="sxs-lookup"><span data-stu-id="f8407-140">For this row definition, you're going to use **Main Account**.</span></span>
2.  <span data-ttu-id="f8407-141">Győződjön meg róla, hogy a **Fő számla** tartalmaz minden és-jelet (&), majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="f8407-141">Make sure that **Main Account** contains all ampersands (&), and then click **OK**.</span></span>

<span data-ttu-id="f8407-142">A sordefiníció most tartalmazza az alapértelmezett jogi személy minden fő számláját.</span><span class="sxs-lookup"><span data-stu-id="f8407-142">The row definition now contains all the main accounts for your default legal entity.</span></span>

### <a name="column-definition"></a><span data-ttu-id="f8407-143">Oszlopdefiníció</span><span class="sxs-lookup"><span data-stu-id="f8407-143">Column definition</span></span>

<span data-ttu-id="f8407-144">Minden egyes főkönyvi kivonati jelentés külön oszlopdefiníciót használ.</span><span class="sxs-lookup"><span data-stu-id="f8407-144">Each trial balance report uses a different column definition.</span></span> <span data-ttu-id="f8407-145">Ezek az oszlopdefiníciók tartalmaznak különböző típusú oszlopokot, a különböző szintű részletességre és pénzügyi adatokra.</span><span class="sxs-lookup"><span data-stu-id="f8407-145">These column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="f8407-146">**Részletes főkönyvi kivonat – Alapértelmezett oszloptípusok:**</span><span class="sxs-lookup"><span data-stu-id="f8407-146">**Detailed Trial Balance – Default column types:**</span></span>
    -   <span data-ttu-id="f8407-147">**DESC** – A leírás a sordefinícióból</span><span class="sxs-lookup"><span data-stu-id="f8407-147">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="f8407-148">**ACCT** – Számlakódok</span><span class="sxs-lookup"><span data-stu-id="f8407-148">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="f8407-149">**ATTR (3)** – Attribútumok:</span><span class="sxs-lookup"><span data-stu-id="f8407-149">**ATTR (3)** – Attributes:</span></span>
        -   <span data-ttu-id="f8407-150">Tranzakció dátuma</span><span class="sxs-lookup"><span data-stu-id="f8407-150">Transaction Date</span></span>
        -   <span data-ttu-id="f8407-151">Bizonylat</span><span class="sxs-lookup"><span data-stu-id="f8407-151">Voucher</span></span>
        -   <span data-ttu-id="f8407-152">Napló leírása</span><span class="sxs-lookup"><span data-stu-id="f8407-152">Journal Description</span></span>
    -   <span data-ttu-id="f8407-153">**FD** – Csak kötelezettségeket tartalmazó pénzügyi adat</span><span class="sxs-lookup"><span data-stu-id="f8407-153">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="f8407-154">**FD** – Csak jóváírásokat tartalmazó pénzügyi adat</span><span class="sxs-lookup"><span data-stu-id="f8407-154">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="f8407-155">**CALC** – Nettó eltérés</span><span class="sxs-lookup"><span data-stu-id="f8407-155">**CALC** – The net difference</span></span>
-   <span data-ttu-id="f8407-156">**Összesítő főkönyvi kivonat – Alapértelmezett oszloptípusok:**</span><span class="sxs-lookup"><span data-stu-id="f8407-156">**Summary Trial Balance – Default columns types:**</span></span>
    -   <span data-ttu-id="f8407-157">**ACCT** – Számlakódok</span><span class="sxs-lookup"><span data-stu-id="f8407-157">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="f8407-158">**DESC** – A leírás a sordefinícióból</span><span class="sxs-lookup"><span data-stu-id="f8407-158">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="f8407-159">**ATTR** – Egy attribútum:</span><span class="sxs-lookup"><span data-stu-id="f8407-159">**ATTR** – An attribute:</span></span>
        -   <span data-ttu-id="f8407-160">Bizonylat</span><span class="sxs-lookup"><span data-stu-id="f8407-160">Voucher</span></span>
    -   <span data-ttu-id="f8407-161">**FD** – A pénzügyi adatok kezdőegyenlege</span><span class="sxs-lookup"><span data-stu-id="f8407-161">**FD** – The beginning balance financial data</span></span>
    -   <span data-ttu-id="f8407-162">**FD** – Csak kötelezettségeket tartalmazó pénzügyi adat</span><span class="sxs-lookup"><span data-stu-id="f8407-162">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="f8407-163">**FD** – Csak jóváírásokat tartalmazó pénzügyi adat</span><span class="sxs-lookup"><span data-stu-id="f8407-163">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="f8407-164">**CALC** – Nettó eltérés</span><span class="sxs-lookup"><span data-stu-id="f8407-164">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="f8407-165">**CALC** – Záró egyenleg</span><span class="sxs-lookup"><span data-stu-id="f8407-165">**CALC** – The closing balance</span></span>
-   <span data-ttu-id="f8407-166">**Éves összegző főkönyvi kivonat – Alapértelmezett:**</span><span class="sxs-lookup"><span data-stu-id="f8407-166">**Summary Trial Balance Year Over Year – Default:**</span></span>
    -   <span data-ttu-id="f8407-167">**ACCT** – Számlakódok</span><span class="sxs-lookup"><span data-stu-id="f8407-167">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="f8407-168">**DESC** – A leírás a sordefinícióból</span><span class="sxs-lookup"><span data-stu-id="f8407-168">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="f8407-169">**ATTR** – Egy attribútum</span><span class="sxs-lookup"><span data-stu-id="f8407-169">**ATTR** – An attribute</span></span>
        -   <span data-ttu-id="f8407-170">Bizonylat</span><span class="sxs-lookup"><span data-stu-id="f8407-170">Voucher</span></span>
    -   <span data-ttu-id="f8407-171">**FD** – A folyó év kezdő egyenleg pénzügyi adata</span><span class="sxs-lookup"><span data-stu-id="f8407-171">**FD** – The beginning balance financial data for the current year</span></span>
    -   <span data-ttu-id="f8407-172">**FD** – A folyó évre csak kötelezettségeket tartalmazó pénzügyi adatok</span><span class="sxs-lookup"><span data-stu-id="f8407-172">**FD** – Financial data that contains only debits for the current year</span></span>
    -   <span data-ttu-id="f8407-173">**FD** – A folyó évre csak jóváírásokat tartalmazó pénzügyi adatok</span><span class="sxs-lookup"><span data-stu-id="f8407-173">**FD** – Financial data that contains only credits for the current year</span></span>
    -   <span data-ttu-id="f8407-174">**CALC** – Nettó eltérés</span><span class="sxs-lookup"><span data-stu-id="f8407-174">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="f8407-175">**CALC** – Záró egyenleg</span><span class="sxs-lookup"><span data-stu-id="f8407-175">**CALC** – The closing balance</span></span>
    -   <span data-ttu-id="f8407-176">**FD** – A előző évre csak kötelezettségeket tartalmazó pénzügyi adatok</span><span class="sxs-lookup"><span data-stu-id="f8407-176">**FD** – Financial data that contains only debits for the last year</span></span>
    -   <span data-ttu-id="f8407-177">**FD** – A előző évre csak jóváírásokat tartalmazó pénzügyi adatok</span><span class="sxs-lookup"><span data-stu-id="f8407-177">**FD** – Financial data that contains only credits for the last year</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f8407-178">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f8407-178">Additional resources</span></span>

[<span data-ttu-id="f8407-179">Pénzügyi jelentéskészítés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="f8407-179">Financial reporting overview</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="f8407-180">Pénzügyi jelentések megtekintése</span><span class="sxs-lookup"><span data-stu-id="f8407-180">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="f8407-181">Dynamics Pénzügyi jelentések blog</span><span class="sxs-lookup"><span data-stu-id="f8407-181">Dynamics Financial Reporting Blog</span></span>](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
