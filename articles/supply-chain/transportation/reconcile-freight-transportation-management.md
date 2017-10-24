---
title: "Szállítási költség egyeztetése a szállításkezelésben"
description: "A cikk a szállítási költség egyeztetési folyamatot ismerteti."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSInvoiceTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0e9dd669ff08c02a8bbb1f83e19dfa62298f317b
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="reconcile-freight-in-transportation-management"></a><span data-ttu-id="7b8a2-103">Szállítási költség egyeztetése a szállításkezelésben</span><span class="sxs-lookup"><span data-stu-id="7b8a2-103">Reconcile freight in transportation management</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="7b8a2-104">A cikk a szállítási költség egyeztetési folyamatot ismerteti.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-104">This article describes the freight reconciliation process.</span></span>

<span data-ttu-id="7b8a2-105">Szállítási költség egyeztetés elvégezhető manuálisan vagy beállítható automatikusra.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-105">Freight reconciliation can be done manually, or it can be set up to occur automatically.</span></span> <span data-ttu-id="7b8a2-106">Automatikus szállítási egyeztetés használatához vizsgálati alapadatok beállítása szükséges, ahol megadhatja a feltételeket, amelyek meghatározzák, hogy mely fuvarszámla egyeztetése legyen automatikus.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-106">To use automatic freight reconciliation, you must set up an audit master where you can define criteria that determine which freight bills are matched automatically.</span></span>

## <a name="the-freight-reconciliation-process"></a><span data-ttu-id="7b8a2-107">A fuvaregyeztetési folyamat</span><span class="sxs-lookup"><span data-stu-id="7b8a2-107">The freight reconciliation process</span></span>
<span data-ttu-id="7b8a2-108">A szállítási díjakat a megfelelő szállítási fuvarozóval társított díjkalkulátor számítja ki.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-108">Freight rates are calculated by the rate engine that is associated with the relevant shipping carrier.</span></span> <span data-ttu-id="7b8a2-109">Rakomány megerősítése esetén a fuvarlevélszámla létrejön, és a szállítási díjak átvitele a fuvarlevélszámlára megtörténik.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-109">When a load is confirmed, a freight bill is generated, and the freight rates are transferred to it.</span></span> <span data-ttu-id="7b8a2-110">A fuvardíjak vegyes költségek szerint vannak arányosítva a vonatkozó forrásbizonylat (beszerzési rendelés, értékesítési rendelés és/vagy átmozgatási rendelés) alapján, a rendszeres számlázási folyamat beállításaitól függően.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-110">The freight rates are apportioned as miscellaneous charges to the relevant source document (purchase order, sales order, and/or transfer order), depending on the setup that is used for the regular billing process.</span></span> <span data-ttu-id="7b8a2-111">A szállítási költség egyeztetési folyamata elindítható, amint a fuvarszámla megérkezik a szállítmányozótól.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-111">The freight reconciliation process (which is also known as the matching process) can start as soon as the freight invoice arrives from the shipping carrier.</span></span> <span data-ttu-id="7b8a2-112">A számla elektronikus úton vagy nyomtatott papíron érkezhet.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-112">The invoice can be received electronically or on paper.</span></span> <span data-ttu-id="7b8a2-113">Ha papíralapú számla érkezik, elektronikus számlát hozhat létre a fuvarlevelet használva sablonként.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-113">If the invoice is received on paper, you can generate an electronic invoice by using the freight bill as a template.</span></span> 

<span data-ttu-id="7b8a2-114">[![Fuvaregyeztetési folyamat](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span><span class="sxs-lookup"><span data-stu-id="7b8a2-114">[![Freight reconcilation process](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span></span>

## <a name="manual-reconciliation"></a><span data-ttu-id="7b8a2-115">Manuális egyeztetés</span><span class="sxs-lookup"><span data-stu-id="7b8a2-115">Manual reconciliation</span></span>
<span data-ttu-id="7b8a2-116">Ha az egyeztetést manuálisan végzi, minden számlázási sorral minden fuvarlevélsort vagy a számlázandó rakománysort egyeztetnie kell.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-116">If you're reconciling freight manually, you must match each invoice line with the freight bill line or lines for the load that is being invoiced.</span></span> <span data-ttu-id="7b8a2-117">Ezt a **Fuvarlevél és számlaegyeztetés** oldalon végezheti el.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-117">You do this matching on the **Freight bill and invoice matching** page.</span></span> <span data-ttu-id="7b8a2-118">Ha a számlasor összege nem egyezik meg a fuvardíj összegével, az eltérés egyeztetés okát kell kiválasztania.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-118">If the amount on the invoice line doesn’t match the freight bill amount, you must select a reconciliation reason for the difference.</span></span> <span data-ttu-id="7b8a2-119">Ha több egyeztetési ok fordul elő, a nem egyeztetett összeget feloszthatja.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-119">If there are multiple reasons for reconciliation, you can split the unmatched amount across them.</span></span> <span data-ttu-id="7b8a2-120">Az egyeztetés oka határozza meg, hogyan kerülnek a különbözet összegei feladásra a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-120">The reconciliation reason determines how the difference amounts are posted in the general ledger.</span></span> <span data-ttu-id="7b8a2-121">Amikor a teljes számlaösszeg egyeztetése számba lett véve, jóváhagyás céljából elküldik és a napló feladásra kerül.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-121">When the reconciliation of the whole invoice amount is accounted for, it's submitted for approval, and then the journal is posted.</span></span> <span data-ttu-id="7b8a2-122">Az alábbi ábra bemutatja, hogyan készíthető szállítási számla és hajtható végre a fuvarlevél-egyeztetés Microsoft Dynamics 365 for Finance and Operations rendszerben.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-122">The following illustration shows how to generate a freight invoice and do freight reconciliation in Microsoft Dynamics 365 for Finance and Operations.</span></span> 
<span data-ttu-id="7b8a2-123">[![Fuvaregyeztetési folyamat Dynamics AX rendszerben](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span><span class="sxs-lookup"><span data-stu-id="7b8a2-123">[![Freight reconcilation tasks in Dynamics AX](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span></span>
## <a name="automatic-reconciliation"></a><span data-ttu-id="7b8a2-124">Automatikus egyeztetés</span><span class="sxs-lookup"><span data-stu-id="7b8a2-124">Automatic reconciliation</span></span>
<span data-ttu-id="7b8a2-125">Automatikus egyeztetéshez meg kell adnia a használni kívánt egyeztetés, számlák, és szállítmányozók ütemezését.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-125">To use automatic reconciliation, you must specify the schedule for reconciliation, and the invoices and shipping carriers to use.</span></span> <span data-ttu-id="7b8a2-126">A számlasorok és fuvarlevelek ellenőrzése alapvizsgálat beállításainak és a fuvarlevél típusának megfelelően történik.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-126">The matching of the invoice lines and freight bills is done according to the setup of the audit master and freight bill type.</span></span> <span data-ttu-id="7b8a2-127">Az automatikus egyeztetés futtatása után kezelnie kell azokat a számlákat, melyeket a rendszer nem tudott.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-127">After you run the automatic reconciliation, you must handle any invoices that the system can't match.</span></span> <span data-ttu-id="7b8a2-128">Manuálisan kell feldolgoznia ezeket a számlákat a kifizetés előtt.</span><span class="sxs-lookup"><span data-stu-id="7b8a2-128">You must then process these invoices manually before you can post all the invoices for payment.</span></span>



