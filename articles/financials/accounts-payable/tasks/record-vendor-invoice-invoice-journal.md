--- 
title: "Szállítói számla rögzítése a számlanaplóban"
description: "Ez a feladat-útmutató bemutatja, hogyan rögzíthet szállítói számlákat amelyek nem kapcsolódnak beszerzési rendeléssel."
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 775f3764d34cecbfc071ff7420d32c7832b42308
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a><span data-ttu-id="50fc8-103">Szállítói számla rögzítése a számlanaplóban</span><span class="sxs-lookup"><span data-stu-id="50fc8-103">Record a vendor invoice in the invoice journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="50fc8-104">Ez a feladat-útmutató bemutatja, hogyan rögzíthet szállítói számlákat amelyek nem kapcsolódnak beszerzési rendeléssel.</span><span class="sxs-lookup"><span data-stu-id="50fc8-104">This task guide will show how to record vendor invoices that are not associated with purchase orders.</span></span> <span data-ttu-id="50fc8-105">Ilyen típusú számlák esetében a számla magában foglalja a szállítók és szolgáltatások költségeit.</span><span class="sxs-lookup"><span data-stu-id="50fc8-105">Examples of this type of invoice include expenses for supplies or services.</span></span>  <span data-ttu-id="50fc8-106">Ez a felvétel az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="50fc8-106">This recording uses the USMF demo company.</span></span>

1. <span data-ttu-id="50fc8-107">Ugorjon a Kötelezettségek > Munkaterületek > Szállítói számla bevitele elemre.</span><span class="sxs-lookup"><span data-stu-id="50fc8-107">Go to Accounts payable > Workspaces > Vendor invoice entry.</span></span>
2. <span data-ttu-id="50fc8-108">Kattintson az Új számlanapló lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="50fc8-108">Click New invoice journal.</span></span>
3. <span data-ttu-id="50fc8-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="50fc8-109">Click New.</span></span>
4. <span data-ttu-id="50fc8-110">A Név mezőben adja meg a számla nevét vagy kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="50fc8-110">In the Name field, enter the journal name or click the drop down button to open the lookup.</span></span>
5. <span data-ttu-id="50fc8-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="50fc8-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="50fc8-112">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="50fc8-112">Click Lines.</span></span>
    * <span data-ttu-id="50fc8-113">A Dátum mezőbe írja be a feladás dátumát, ami frissül a Főkönyvben.</span><span class="sxs-lookup"><span data-stu-id="50fc8-113">In the Date field, enter the posting date that will update General Ledger.</span></span>  
7. <span data-ttu-id="50fc8-114">A Számla mezőben adja meg a Szállítói számlát.</span><span class="sxs-lookup"><span data-stu-id="50fc8-114">In the Account field, specify the Vendor account.</span></span>
8. <span data-ttu-id="50fc8-115">A Számla mezőben adja meg a számlaszámot.</span><span class="sxs-lookup"><span data-stu-id="50fc8-115">In the Invoice field, enter the invoice number.</span></span>
9. <span data-ttu-id="50fc8-116">Írjon egy értéket a „Leírás” mezőbe.</span><span class="sxs-lookup"><span data-stu-id="50fc8-116">In the Description field, type a value.</span></span>
10. <span data-ttu-id="50fc8-117">A Hitelkeret mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="50fc8-117">In the Credit field, enter a number.</span></span>
11. <span data-ttu-id="50fc8-118">Az Ellenszámla mezőben adja meg a számlaszámot vagy kattintson a legördülő gombra a keresőlista megnyitásához</span><span class="sxs-lookup"><span data-stu-id="50fc8-118">In the Offset account field, enter the account number or click the drop down button to open the lookup</span></span>
    * <span data-ttu-id="50fc8-119">Az Áfacsoport alapértelmezett értéke a szállítói számlából származik.</span><span class="sxs-lookup"><span data-stu-id="50fc8-119">The Sales tax group will default from the vendor account.</span></span>  
    * <span data-ttu-id="50fc8-120">A Cikk áfacsoportjának alapértelmezett értéke a főszámlán Ellenszámla mezőben megadott értékből származik.</span><span class="sxs-lookup"><span data-stu-id="50fc8-120">The Item sales tax group will default from the main account specified in the Offset account field.</span></span>  
    * <span data-ttu-id="50fc8-121">A Határidő dátuma a Fizetési feltételek alapján kerül számításra.</span><span class="sxs-lookup"><span data-stu-id="50fc8-121">The Due date will be calculated based on the Terms of payment.</span></span>  
    * <span data-ttu-id="50fc8-122">A Készpénzfizetési engedmény alapértelmezett értéke a Szállítói számlából származik.</span><span class="sxs-lookup"><span data-stu-id="50fc8-122">The Cash discount will default from the Vendor account.</span></span>  
12. <span data-ttu-id="50fc8-123">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="50fc8-123">Click Post.</span></span>
13. <span data-ttu-id="50fc8-124">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="50fc8-124">Close the page.</span></span>


