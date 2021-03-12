---
title: Projektköltségek könyvelése beszerzési elismervényekkel
description: Ez a témakör leírja, hogy a beszerzési elismervényekkel elszámolt projektköltségek hogyan követhetők nyomom a Microsoft Dynamics 365 Finance programban.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: roschlom
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d27fba816ca289e6a84e8684f7f90686864fb0b6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972081"
---
# <a name="project-cost-accrual-on-purchase-receipts"></a><span data-ttu-id="9bfdf-103">Projektköltségek könyvelése beszerzési elismervényekkel</span><span class="sxs-lookup"><span data-stu-id="9bfdf-103">Project cost accrual on purchase receipts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9bfdf-104">Ez a témakör leírja, hogy a beszerzési elismervényekkel elszámolt projektköltségek hogyan követhetők nyomom a Microsoft Dynamics 365 Finance programban.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-104">This topic describes how accrued project costs from purchase receipts can be tracked in Microsoft Dynamics 365 Finance.</span></span> 

<span data-ttu-id="9bfdf-105">A projekt számlái gyakran érkeznek később az árukhoz és a szolgáltatásokhoz képest, amely jelentős hatással lehet a projekt fő teljesítménymutatóira (KPI).</span><span class="sxs-lookup"><span data-stu-id="9bfdf-105">Invoices for a project often arrive later than the goods and services are delivered, which might have a significant impact on project key performance indicators (KPIs).</span></span> <span data-ttu-id="9bfdf-106">Fontos, hogy ezeket a tranzakciókat nyomon követhessük a pénzügyi és a projektjelentésekben.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-106">It important to be able to track these transactions in both financial and project reports.</span></span>

<span data-ttu-id="9bfdf-107">Az alábbi példa forgatókönyv ezt ábrázolja.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-107">The following example scenario illustrates this.</span></span> 

<span data-ttu-id="9bfdf-108">A Contoso Consulting elindított egy új felhőtelepítési projektet.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-108">Contoso Consulting has started a new cloud deployment project.</span></span> <span data-ttu-id="9bfdf-109">A beszerzési rendelést hoztak létre egy számítógép megvásárlására a projekt számára.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-109">A purchase order is created to buy a computer for the project.</span></span> <span data-ttu-id="9bfdf-110">A számítógép ára 1500 USA dollár, a telepítési szolgáltatás ára 150 USA dollár.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-110">The computer will cost $1500 and installation services will cost $150.</span></span> <span data-ttu-id="9bfdf-111">A szállító leszállította és telepítette a számítógépet, de a számlát még nem kapta meg a Contoso Consulting.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-111">The vendor has delivered and installed the computer, but the invoice has not yet reached Contoso Consulting.</span></span> <span data-ttu-id="9bfdf-112">A projektmenedzser látni szeretné az 1650 USA dolláros projektköltség elhatárolását, még a számla érkezése előtt.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-112">The project manager would like to see project cost accrual of $1650 before the invoice gets delivered.</span></span> <span data-ttu-id="9bfdf-113">A költségnek a vállalat hónap vége pénzügyi kimutatásában is tükröződnie kell.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-113">This cost should also be reflected in the company's month end financial statements.</span></span> 

<span data-ttu-id="9bfdf-114">Az elhatárolt költséget jelentési célokra pénzügyi szinten és a projekt szintjén is rögzíteni kell.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-114">The accrued cost needs to be recorded on both the financial level and project level for reporting purposes.</span></span> <span data-ttu-id="9bfdf-115">A termékbevételezés pénzügyi frissítése a cikk és a beszerzés kategóriákban követhető nyomon.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-115">The financial update of the product receipt can be tracked for the item and procurement categories.</span></span> 

<span data-ttu-id="9bfdf-116">A cikkek esetében a **Kötelezettségek paraméterei** lapon válassza a **Termékbevételezés feladása a főkönyvben** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-116">For items, on the **Accounts payable parameters** page, select the **Post product receipts to ledger** option.</span></span>
<span data-ttu-id="9bfdf-117">[![Kötelezettségek paramétereinek oldala](./media/accruals1-1024x409.png)](./media/accruals1.png)</span><span class="sxs-lookup"><span data-stu-id="9bfdf-117">[![Accounts payable parameters page](./media/accruals1-1024x409.png)](./media/accruals1.png)</span></span> 

<span data-ttu-id="9bfdf-118">A beszerzési kategóriák esetében a **Kategória-irányelvszabály** lapon adja meg a **Beszerzés** házirendet, és válassza ki a **Nyugta szerinti beszerzési költség** lehetőséget minden beszerzési kategóriához.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-118">For procurement categories, on the **Category policy rule** page, select **Purchasing** policies, and then select **Accrue purchase expense on receipt** for each procurement category.</span></span>
<span data-ttu-id="9bfdf-119">[![Kategória irányelvszabályának oldala](./media/accruals2-1024x569.png)](./media/accruals2.png)</span><span class="sxs-lookup"><span data-stu-id="9bfdf-119">[![Category policy rule page](./media/accruals2-1024x569.png)](./media/accruals2.png)</span></span> 

<span data-ttu-id="9bfdf-120">A rendszer a **Beszerzési kiadás, nem számlázott** és a **Beszerzés, elhatárolás** számlákat használja a **Feladás beállítása** részben a termékbevételezéshez kapcsolódó bizonylatok feladásakor.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-120">The **Purchase expenditure un-invoiced** and **Purchase accrual** accounts in **Posting setup** will be used when vouchers that are related to the product receipt are posted.</span></span>

<span data-ttu-id="9bfdf-121">Ugyanazt a forgatókönyvet használva nézzük meg, hogyan befolyásolja egy termékbevételezés feladása a főkönyv és a projekt adatait.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-121">Using this same scenario, let's see how posting a product receipt will impact General ledger and Project information.</span></span> 

<span data-ttu-id="9bfdf-122">**1. lépés:** Új beszerzési rendelés létrehozása és megerősítése a projekt számára a következő rögzítéséhez: számítógép vásárlása 1500 USA dollárért, valamint telepítési szolgáltatás 150 USA dollárért.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-122">**Step 1:** Create and confirm a new purchase order for the project to record the purchase of a computer for $1500 and installation services for $150.</span></span>
<span data-ttu-id="9bfdf-123">[![Új beszerzési rendelés létrehozása](./media/accruals4-1024x497.png)](./media/accruals4.png)</span><span class="sxs-lookup"><span data-stu-id="9bfdf-123">[![Create new purchase order](./media/accruals4-1024x497.png)](./media/accruals4.png)</span></span> 

<span data-ttu-id="9bfdf-124">Amikor a beszerzési rendelés megerősítést nyer, a vállalt költségekhez tranzakciók jönnek létre a projekthez.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-124">When the purchase order is confirmed, transactions for the committed cost are created for the project.</span></span> 
<span data-ttu-id="9bfdf-125">[![Létrehozott tranzakciók](./media/accruals5-1024x219.png)](./media/accruals5.png)</span><span class="sxs-lookup"><span data-stu-id="9bfdf-125">[![Transactions created](./media/accruals5-1024x219.png)](./media/accruals5.png)</span></span> 

> [!NOTE]
> <span data-ttu-id="9bfdf-126">A vállalt költség tranzakciókhoz a **Tranzakció eredete** mező értéke **Beszerzési rendelés** lesz.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-126">The transactions for the committed cost will have the **Transaction Origin** field set to **Purchase Order**.</span></span> <span data-ttu-id="9bfdf-127">A beszerzési rendelés létrehozása és megerősítése nem hoz létre tranzakciókat a projekthez.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-127">Creating and confirming a purchase order does not create transactions for a project.</span></span> 

<span data-ttu-id="9bfdf-128">**2. lépés:** Az árukat és szolgáltatásokat leszállítják, és egy szállítólevél regisztrálása történik.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-128">**Step 2:** Goods and services get delivered and a product receipt is registered.</span></span> 

<span data-ttu-id="9bfdf-129">A termékbevételezés feladása bizonylat létrehozását főkönyvbe való feladását váltja ki.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-129">Posting a product receipt will generate and post a voucher to the ledger.</span></span> <span data-ttu-id="9bfdf-130">A bizonylat tartozik elemként kerül fel a beszerzési kiadások, nem számlázott kiadások és beszerzési jóváírás elhatárolása számlára.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-130">The voucher will debit the purchase expenditure, un-invoiced account, and credit purchase accrual account.</span></span> 
<span data-ttu-id="9bfdf-131">[![Bizonylattranzakciók](./media/accruals6-1024x214.png)](./media/accruals6.png)</span><span class="sxs-lookup"><span data-stu-id="9bfdf-131">[![Voucher transactions](./media/accruals6-1024x214.png)](./media/accruals6.png)</span></span>

> [!NOTE]
> <span data-ttu-id="9bfdf-132">A termékbevételezés feladása a beszerzési kategóriák és a termékek feladási beállítását használja, és nem a projektkategóriák feladási beállítását.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-132">Posting a product receipt will use the posting setup for procurement categories and products, and not the posting setup for the project categories.</span></span> <span data-ttu-id="9bfdf-133">Annak érdekében, hogy megfelelően tükröződjön a beszerzési elhatárolások pénzügyi hatása, a beállítást igazítani kell.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-133">In order to correctly reflect financial impact of purchase accruals, this setup needs to be aligned.</span></span> 

<span data-ttu-id="9bfdf-134">A **Beszerzési kategória** oldalon elvégezhető a projektkategóriák és a beszerzési kategóriák leképezése.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-134">It is possible to map procurement categories to project categories on the **Procurement category** page.</span></span>
<span data-ttu-id="9bfdf-135">[![Beszerzési kategória oldala](./media/accruals7-1024x390.png)](./media/accruals7.png)</span><span class="sxs-lookup"><span data-stu-id="9bfdf-135">[![Procurement category page](./media/accruals7-1024x390.png)](./media/accruals7.png)</span></span>

<span data-ttu-id="9bfdf-136">**3. lépés:** Szállítóiszámla-tervezet létrehozása.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-136">**Step 3:** Create a draft vendor invoice.</span></span> 

<span data-ttu-id="9bfdf-137">Egy termékbevételezés feladása nincs hatással a projektinformációkra.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-137">Posting a product receipt does not impact project information.</span></span> <span data-ttu-id="9bfdf-138">Megkerülő megoldásként közvetlenül a termékbevételezés feladása után létrehozható egy szállítóiszámla-tervezet.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-138">As a workaround, you could generate a draft vendor invoice right after posting the purchase receipt.</span></span> <span data-ttu-id="9bfdf-139">Keresse fel a következőt: **Beszerzési rendelés** lap &gt; **Számla lap** &gt; **Létrehozás** &gt; **Számla**.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-139">Go to the **Purchase Order** page &gt; **Invoice tab** &gt; **Generate** &gt; **Invoice**.</span></span> <span data-ttu-id="9bfdf-140">Ez létrehoz egy függőben lévő számladokumentumot, amely frissíti a projekt adatait.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-140">This creates a pending invoice document that updates project information.</span></span> 

<span data-ttu-id="9bfdf-141">A szállítóiszámla-tervezet létrehozása függő projekttranzakciókat hoz létre.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-141">Creating a draft vendor invoice will generate pending project transactions.</span></span> 
<span data-ttu-id="9bfdf-142">[![Függő projekttranzakciók](./media/accruals8-1024x225.png)](./media/accruals8.png)</span><span class="sxs-lookup"><span data-stu-id="9bfdf-142">[![Pending project transactions](./media/accruals8-1024x225.png)](./media/accruals8.png)</span></span> 

<span data-ttu-id="9bfdf-143">A **Vállalt költség** lapon, az 1. lépésben létrehozott bejegyzéseket a rendszer lezárja, és új rekordokat hoz létre, hogy tükrözze a függőben lévő szállítói számláról származó költség-kötelezettségvállalás.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-143">In the **Committed cost** page, records created in step 1 will be closed and new records will be created to reflect cost commitment coming from the pending vendor invoice.</span></span> <span data-ttu-id="9bfdf-144">A **Tranzakció eredete** mező beállítása a vállalt költséghez **Szállítói számla** lesz.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-144">The **Transaction origin** field for the committed cost will be set to **Vendor invoice**.</span></span>
<span data-ttu-id="9bfdf-145">[![Vállalt költségek oldala](./media/accruals9-1024x200.png)](./media/accruals9.png)</span><span class="sxs-lookup"><span data-stu-id="9bfdf-145">[![Commited costs page](./media/accruals9-1024x200.png)](./media/accruals9.png)</span></span>

<span data-ttu-id="9bfdf-146">A szállítói számla függő állapotban marad, amíg a tényleges szállítói számla megérkezik.</span><span class="sxs-lookup"><span data-stu-id="9bfdf-146">The vendor invoice will remain in a pending state until the actual vendor invoice arrives.</span></span>



