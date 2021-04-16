---
title: Szállítói számla rögzítése a számlanaplóban
description: Ez a feladat-útmutató bemutatja, hogyan rögzíthet szállítói számlákat amelyek nem kapcsolódnak beszerzési rendeléssel.
author: abruer
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 35862195f3c2c13711157be919956f40fea0989b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820641"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a><span data-ttu-id="8fbab-103">Szállítói számla rögzítése a számlanaplóban</span><span class="sxs-lookup"><span data-stu-id="8fbab-103">Record a vendor invoice in the invoice journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8fbab-104">Ez a feladat-útmutató bemutatja, hogyan rögzíthet szállítói számlákat amelyek nem kapcsolódnak beszerzési rendeléssel.</span><span class="sxs-lookup"><span data-stu-id="8fbab-104">This task guide will show how to record vendor invoices that are not associated with purchase orders.</span></span> <span data-ttu-id="8fbab-105">Ilyen típusú számlák esetében a számla magában foglalja a szállítók és szolgáltatások költségeit.</span><span class="sxs-lookup"><span data-stu-id="8fbab-105">Examples of this type of invoice include expenses for supplies or services.</span></span>  <span data-ttu-id="8fbab-106">Ez a felvétel az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="8fbab-106">This recording uses the USMF demo company.</span></span>

1. <span data-ttu-id="8fbab-107">Ugorjon a **Navigációs ablaktábla > Modulok > Kötelezettségek > Munkaterületek > Szállítói számla bevitele** elemre.</span><span class="sxs-lookup"><span data-stu-id="8fbab-107">Go to **Navigation pane > Modules > Accounts payable > Workspaces > Vendor invoice entry**.</span></span>
2. <span data-ttu-id="8fbab-108">A **Műveleti ablaktáblán** kattintson az **Új számlanapló** elemre.</span><span class="sxs-lookup"><span data-stu-id="8fbab-108">On the **Action pane**, click **New invoice journal**.</span></span>
3. <span data-ttu-id="8fbab-109">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="8fbab-109">Click **New**.</span></span>
4. <span data-ttu-id="8fbab-110">A **Név** mezőben adja meg a napló nevét, vagy kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8fbab-110">In the **Name** field, enter the journal name or click the drop down button to open the lookup.</span></span>
5. <span data-ttu-id="8fbab-111">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8fbab-111">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="8fbab-112">A **Művelet ablaktáblán** kattintson a **Sorok** elemre.</span><span class="sxs-lookup"><span data-stu-id="8fbab-112">On the **Action pane**, click **Lines**.</span></span> <span data-ttu-id="8fbab-113">A **Dátum** mezőben adja meg a feladás dátumát, ami frissül a Főkönyvben.</span><span class="sxs-lookup"><span data-stu-id="8fbab-113">In the **Date** field, enter the posting date that will update General Ledger.</span></span>  
7. <span data-ttu-id="8fbab-114">A **Számla** mezőben adja meg a **Szállítói számlát**.</span><span class="sxs-lookup"><span data-stu-id="8fbab-114">In the **Account** field, specify the **Vendor account**.</span></span>
8. <span data-ttu-id="8fbab-115">A **Számla** mezőben adja meg a számlaszámot.</span><span class="sxs-lookup"><span data-stu-id="8fbab-115">In the **Invoice** field, enter the invoice number.</span></span>
9. <span data-ttu-id="8fbab-116">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8fbab-116">In the **Description** field, type a value.</span></span>
10. <span data-ttu-id="8fbab-117">A **Hitelkeret** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="8fbab-117">In the **Credit** field, enter a number.</span></span>
11. <span data-ttu-id="8fbab-118">Az **Ellenszámla** mezőben adja meg a számlaszámot, vagy kattintson a legördülő gombra a keresőlista megnyitásához</span><span class="sxs-lookup"><span data-stu-id="8fbab-118">In the **Offset account** field, enter the account number or click the drop down button to open the lookup</span></span>
    * <span data-ttu-id="8fbab-119">Az **Áfacsoport** alapértelmezett értéke a szállítói számlából származik.</span><span class="sxs-lookup"><span data-stu-id="8fbab-119">The **Sales tax group** will be default from the vendor account.</span></span>  
    * <span data-ttu-id="8fbab-120">A **Cikk áfacsoportjának** alapértelmezett értéke a főszámlán az **Ellenszámla** mezőben megadott értékből származik.</span><span class="sxs-lookup"><span data-stu-id="8fbab-120">The **Item sales tax group** will be default from the main account specified in the **Offset account** field.</span></span>  
    * <span data-ttu-id="8fbab-121">A **Határidőt** a Fizetési feltételek alapján számítja ki a rendszer.</span><span class="sxs-lookup"><span data-stu-id="8fbab-121">The **Due date** will be calculated based on the Terms of payment.</span></span>  
    * <span data-ttu-id="8fbab-122">A **Készpénzfizetési engedmény** alapértelmezett értéke a Szállítói számlából származik.</span><span class="sxs-lookup"><span data-stu-id="8fbab-122">The **Cash discount** will default from the Vendor account.</span></span>
12. <span data-ttu-id="8fbab-123">Ha engedélyezte a Szállítói számlanapló munkafolyamatát, kattintson a **Munkafolyamat > Küldés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8fbab-123">If you have enabled Vendor invoice journal workflow, click **Workflow > Submit**.</span></span>
    * <span data-ttu-id="8fbab-124">A beküldés jóváhagyásakor a program a dátumot a következő nyitott időszak első napjára vezeti, ha a tranzakció feladási dátuma a Várakoztatott vagy a Főkönyvi könyveléshez lezárt időszakon belülre esik.</span><span class="sxs-lookup"><span data-stu-id="8fbab-124">When your submission is approved, the date will be advanced to the first day of the next open period, if the transaction posting date falls within a period that is On hold or Closed for ledger posting.</span></span>
12. <span data-ttu-id="8fbab-125">Kattintson a **Bejegyzés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8fbab-125">Click **Post**.</span></span>
13. <span data-ttu-id="8fbab-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8fbab-126">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]