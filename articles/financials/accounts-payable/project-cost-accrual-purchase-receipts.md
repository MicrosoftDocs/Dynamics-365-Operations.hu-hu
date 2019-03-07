---
title: Projektköltségek könyvelése beszerzési elismervényekkel
description: Ez a témakör leírja, hogy a beszerzési elismervényekkel elszámolt projektköltségek hogyan követhetők nyomom a Microsoft Dynamics 365 for Finance and Operations programban.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bc822652abbba68f094fe5b8a65f796165a92c4c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "340430"
---
# <a name="project-cost-accrual-on-purchase-receipts"></a><span data-ttu-id="03301-103">Projektköltségek könyvelése beszerzési elismervényekkel</span><span class="sxs-lookup"><span data-stu-id="03301-103">Project cost accrual on purchase receipts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03301-104">Ez a témakör leírja, hogy a beszerzési elismervényekkel elszámolt projektköltségek hogyan követhetők nyomom a Microsoft Dynamics 365 for Finance and Operations programban.</span><span class="sxs-lookup"><span data-stu-id="03301-104">This topic describes how accrued project costs from purchase receipts can be tracked in Microsoft Dynamics 365 for Finance and Operations.</span></span> 

<span data-ttu-id="03301-105">A projekt számlái gyakran érkeznek később az árukhoz és a szolgáltatásokhoz képest, amely jelentős hatással lehet a projekt fő teljesítménymutatóira (KPI).</span><span class="sxs-lookup"><span data-stu-id="03301-105">Invoices for a project often arrive later than the goods and services are delivered, which might have a significant impact on project key performance indicators (KPIs).</span></span> <span data-ttu-id="03301-106">Fontos, hogy ezeket a tranzakciókat nyomon követhessük a pénzügyi és a projektjelentésekben.</span><span class="sxs-lookup"><span data-stu-id="03301-106">It important to be able to track these transactions in both financial and project reports.</span></span>

<span data-ttu-id="03301-107">Az alábbi példa forgatókönyv ezt ábrázolja.</span><span class="sxs-lookup"><span data-stu-id="03301-107">The following example scenario illustrates this.</span></span> 

<span data-ttu-id="03301-108">A Contoso Consulting elindított egy új felhőtelepítési projektet.</span><span class="sxs-lookup"><span data-stu-id="03301-108">Contoso Consulting has started a new cloud deployment project.</span></span> <span data-ttu-id="03301-109">A beszerzési rendelést hoztak létre egy számítógép megvásárlására a projekt számára.</span><span class="sxs-lookup"><span data-stu-id="03301-109">A purchase order is created to buy a computer for the project.</span></span> <span data-ttu-id="03301-110">A számítógép ára 1500 USA dollár, a telepítési szolgáltatás ára 150 USA dollár.</span><span class="sxs-lookup"><span data-stu-id="03301-110">The computer will cost $1500 and installation services will cost $150.</span></span> <span data-ttu-id="03301-111">A szállító leszállította és telepítette a számítógépet, de a számlát még nem kapta meg a Contoso Consulting.</span><span class="sxs-lookup"><span data-stu-id="03301-111">The vendor has delivered and installed the computer, but the invoice has not yet reached Contoso Consulting.</span></span> <span data-ttu-id="03301-112">A projektmenedzser látni szeretné az 1650 USA dolláros projektköltség elhatárolását, még a számla érkezése előtt.</span><span class="sxs-lookup"><span data-stu-id="03301-112">The project manager would like to see project cost accrual of $1650 before the invoice gets delivered.</span></span> <span data-ttu-id="03301-113">A költségnek a vállalat hónap vége pénzügyi kimutatásában is tükröződnie kell.</span><span class="sxs-lookup"><span data-stu-id="03301-113">This cost should also be reflected in the company's month end financial statements.</span></span> 

<span data-ttu-id="03301-114">Az elhatárolt költséget jelentési célokra pénzügyi szinten és a projekt szintjén is rögzíteni kell.</span><span class="sxs-lookup"><span data-stu-id="03301-114">The accrued cost needs to be recorded on both the financial level and project level for reporting purposes.</span></span> <span data-ttu-id="03301-115">A Finance and Operations esetében a termékbevételezés pénzügyi frissítése a cikk és a beszerzés kategóriákban követhető nyomon.</span><span class="sxs-lookup"><span data-stu-id="03301-115">In Finance and Operations, the financial update of the product receipt can be tracked for the item and procurement categories.</span></span> 

<span data-ttu-id="03301-116">A cikkek esetében a **Kötelezettségek paraméterei** lapon válassza a **Termékbevételezés feladása a főkönyvben** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="03301-116">For items, on the **Accounts payable parameters** page, select the **Post product receipts to ledger** option.</span></span>
<span data-ttu-id="03301-117">[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png)</span><span class="sxs-lookup"><span data-stu-id="03301-117">[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png)</span></span> 

<span data-ttu-id="03301-118">A beszerzési kategóriák esetében a **Kategória-irányelvszabály** lapon adja meg a **Beszerzés** házirendet, és válassza ki a **Nyugta szerinti beszerzési költség** lehetőséget minden beszerzési kategóriához.</span><span class="sxs-lookup"><span data-stu-id="03301-118">For procurement categories, on the **Category policy rule** page, select **Purchasing** policies, and then select **Accrue purchase expense on receipt** for each procurement category.</span></span>
<span data-ttu-id="03301-119">[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png)</span><span class="sxs-lookup"><span data-stu-id="03301-119">[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png)</span></span> 

<span data-ttu-id="03301-120">A rendszer a **Beszerzési kiadás, nem számlázott** és a **Beszerzés, elhatárolás** számlákat használja a **Feladás beállítása** részben a termékbevételezéshez kapcsolódó bizonylatok feladásakor.</span><span class="sxs-lookup"><span data-stu-id="03301-120">The **Purchase expenditure un-invoiced** and **Purchase accrual** accounts in **Posting setup** will be used when vouchers that are related to the product receipt are posted.</span></span>
<span data-ttu-id="03301-121">[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png)</span><span class="sxs-lookup"><span data-stu-id="03301-121">[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png)</span></span> 

<span data-ttu-id="03301-122">Ugyanazt a forgatókönyvet használva nézzük meg, hogyan befolyásolja egy termékbevételezés feladása a főkönyv és a projekt adatait.</span><span class="sxs-lookup"><span data-stu-id="03301-122">Using this same scenario, let's see how posting a product receipt will impact General ledger and Project information.</span></span> 

<span data-ttu-id="03301-123">**1. lépés:** Új beszerzési rendelés létrehozása és megerősítése a projekt számára a következő rögzítéséhez: számítógép vásárlása 1500 USA dollárért, valamint telepítési szolgáltatás 150 USA dollárért.</span><span class="sxs-lookup"><span data-stu-id="03301-123">**Step 1:** Create and confirm a new purchase order for the project to record the purchase of a computer for $1500 and installation services for $150.</span></span>
<span data-ttu-id="03301-124">[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png)</span><span class="sxs-lookup"><span data-stu-id="03301-124">[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png)</span></span> 

<span data-ttu-id="03301-125">Amikor a beszerzési rendelés megerősítést nyer, a vállalt költségekhez tranzakciók jönnek létre a projekthez.</span><span class="sxs-lookup"><span data-stu-id="03301-125">When the purchase order is confirmed, transactions for the committed cost are created for the project.</span></span> 
<span data-ttu-id="03301-126">[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png)</span><span class="sxs-lookup"><span data-stu-id="03301-126">[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png)</span></span> 

> [!NOTE]
> <span data-ttu-id="03301-127">A vállalt költség tranzakciókhoz a **Tranzakció eredete** mező értéke **Beszerzési rendelés** lesz.</span><span class="sxs-lookup"><span data-stu-id="03301-127">The transactions for the committed cost will have the **Transaction Origin** field set to **Purchase Order**.</span></span> <span data-ttu-id="03301-128">A beszerzési rendelés létrehozása és megerősítése nem hoz létre tranzakciókat a projekthez.</span><span class="sxs-lookup"><span data-stu-id="03301-128">Creating and confirming a purchase order does not create transactions for a project.</span></span> 

<span data-ttu-id="03301-129">**2. lépés:** Az árukat és szolgáltatásokat leszállítják, és egy szállítólevél regisztrálása történik.</span><span class="sxs-lookup"><span data-stu-id="03301-129">**Step 2:** Goods and services get delivered and a product receipt is registered.</span></span> 

<span data-ttu-id="03301-130">A termékbevételezés feladása bizonylat létrehozását főkönyvbe való feladását váltja ki.</span><span class="sxs-lookup"><span data-stu-id="03301-130">Posting a product receipt will generate and post a voucher to the ledger.</span></span> <span data-ttu-id="03301-131">A bizonylat tartozik elemként kerül fel a beszerzési kiadások, nem számlázott kiadások és beszerzési jóváírás elhatárolása számlára.</span><span class="sxs-lookup"><span data-stu-id="03301-131">The voucher will debit the purchase expenditure, un-invoiced account, and credit purchase accrual account.</span></span> 
<span data-ttu-id="03301-132">[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)</span><span class="sxs-lookup"><span data-stu-id="03301-132">[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)</span></span>

> [!NOTE]
> <span data-ttu-id="03301-133">A termékbevételezés feladása a beszerzési kategóriák és a termékek feladási beállítását használja, és nem a projektkategóriák feladási beállítását.</span><span class="sxs-lookup"><span data-stu-id="03301-133">Posting a product receipt will use the posting setup for procurement categories and products, and not the posting setup for the project categories.</span></span> <span data-ttu-id="03301-134">Annak érdekében, hogy megfelelően tükröződjön a beszerzési elhatárolások pénzügyi hatása, a beállítást igazítani kell.</span><span class="sxs-lookup"><span data-stu-id="03301-134">In order to correctly reflect financial impact of purchase accruals, this setup needs to be aligned.</span></span> 

<span data-ttu-id="03301-135">A **Beszerzési kategória** oldalon elvégezhető a projektkategóriák és a beszerzési kategóriák leképezése.</span><span class="sxs-lookup"><span data-stu-id="03301-135">It is possible to map procurement categories to project categories on the **Procurement category** page.</span></span>
<span data-ttu-id="03301-136">[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)</span><span class="sxs-lookup"><span data-stu-id="03301-136">[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)</span></span>

<span data-ttu-id="03301-137">**3. lépés:** Szállítóiszámla-tervezet létrehozása.</span><span class="sxs-lookup"><span data-stu-id="03301-137">**Step 3:** Create a draft vendor invoice.</span></span> 

<span data-ttu-id="03301-138">A Finance and Operations esetében egy termékbevételezés feladása nincs hatással a projektinformációkra.</span><span class="sxs-lookup"><span data-stu-id="03301-138">In Finance and Operations, posting a product receipt does not impact project information.</span></span> <span data-ttu-id="03301-139">Megkerülő megoldásként közvetlenül a termékbevételezés feladása után létrehozható egy szállítóiszámla-tervezet.</span><span class="sxs-lookup"><span data-stu-id="03301-139">As a workaround, you could generate a draft vendor invoice right after posting the purchase receipt.</span></span> <span data-ttu-id="03301-140">Keresse fel a következőt: **Beszerzési rendelés** lap &gt; **Számla lap** &gt; **Létrehozás** &gt; **Számla**.</span><span class="sxs-lookup"><span data-stu-id="03301-140">Go to the **Purchase Order** page &gt; **Invoice tab** &gt; **Generate** &gt; **Invoice**.</span></span> <span data-ttu-id="03301-141">Ez létrehoz egy függőben lévő számladokumentumot, amely frissíti a projekt adatait.</span><span class="sxs-lookup"><span data-stu-id="03301-141">This creates a pending invoice document that updates project information.</span></span> 

<span data-ttu-id="03301-142">A szállítóiszámla-tervezet létrehozása függő projekttranzakciókat hoz létre.</span><span class="sxs-lookup"><span data-stu-id="03301-142">Creating a draft vendor invoice will generate pending project transactions.</span></span> 
<span data-ttu-id="03301-143">[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png)</span><span class="sxs-lookup"><span data-stu-id="03301-143">[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png)</span></span> 

<span data-ttu-id="03301-144">A **Vállalt költség** lapon, az 1. lépésben létrehozott bejegyzéseket a rendszer lezárja, és új rekordokat hoz létre, hogy tükrözze a függőben lévő szállítói számláról származó költség-kötelezettségvállalás.</span><span class="sxs-lookup"><span data-stu-id="03301-144">In the **Committed cost** page, records created in step 1 will be closed and new records will be created to reflect cost commitment coming from the pending vendor invoice.</span></span> <span data-ttu-id="03301-145">A **Tranzakció eredete** mező beállítása a vállalt költséghez **Szállítói számla** lesz.</span><span class="sxs-lookup"><span data-stu-id="03301-145">The **Transaction origin** field for the committed cost will be set to **Vendor invoice**.</span></span>
<span data-ttu-id="03301-146">[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)</span><span class="sxs-lookup"><span data-stu-id="03301-146">[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)</span></span>

<span data-ttu-id="03301-147">A szállítói számla függő állapotban marad, amíg a tényleges szállítói számla megérkezik.</span><span class="sxs-lookup"><span data-stu-id="03301-147">The vendor invoice will remain in a pending state until the actual vendor invoice arrives.</span></span>



