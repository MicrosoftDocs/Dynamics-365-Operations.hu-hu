--- 
title: "Szabadszöveges számlasablon létrehozása"
description: "Ez a felvétel az USMF bemutatócéget használja."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e9c9811b348d81cd735c5b75ca48e0a56a8d52be
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-free-text-invoice-template"></a><span data-ttu-id="176cb-103">Szabadszöveges számlasablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="176cb-103">Create a free text invoice template</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="176cb-104">Ez a felvétel az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="176cb-104">This recording uses the USMF demo company.</span></span> <span data-ttu-id="176cb-105">A rögzítést az a felhasználó használja, aki felelős a kintlévőségek számláinak kezeléséért és feldolgozásáért.</span><span class="sxs-lookup"><span data-stu-id="176cb-105">The recording is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

1. <span data-ttu-id="176cb-106">Ugrás a Kinnlevőségek > Számlák > Ismétlődő számlák > Szabadszöveges számlasablonok pontra.</span><span class="sxs-lookup"><span data-stu-id="176cb-106">Go to Accounts receivable > Invoices > Recurring invoices > Free text invoice templates.</span></span>
    * <span data-ttu-id="176cb-107">A képernyőn szabadszöveges számlasablonokat hozhat létre, amelyek számlasorokat, költségeket, könyvelési felosztási sablont és főkönyvi számlainformációkat tartalmazhatnak.</span><span class="sxs-lookup"><span data-stu-id="176cb-107">Use this form to create free text invoice templates that can include invoice lines, charges, an accounting distribution template, and ledger account information.</span></span>  
2. <span data-ttu-id="176cb-108">Új szabadszöveges számlasablon létrehozásához kattintson az „Új” elemre.</span><span class="sxs-lookup"><span data-stu-id="176cb-108">Click 'New' to create a new free text invoice template.</span></span>
3. <span data-ttu-id="176cb-109">Írjon be egy értéket a Sablonnév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="176cb-109">In the Template name field, type a value.</span></span>
    * <span data-ttu-id="176cb-110">A „Sablonnév” egyedileg azonosítja a szabadszöveges számla sablonját.</span><span class="sxs-lookup"><span data-stu-id="176cb-110">‘Template name’ uniquely identifies a free text invoice template.</span></span> <span data-ttu-id="176cb-111">Egy „Sablonnév” csakis egyetlen sablonhoz tartozhat.</span><span class="sxs-lookup"><span data-stu-id="176cb-111">No two templates can have the same ‘Template name’.</span></span>  
4. <span data-ttu-id="176cb-112">Adja meg a sablon leírását a Leírás mezőben.</span><span class="sxs-lookup"><span data-stu-id="176cb-112">In the Description field, enter a description of the template.</span></span>
5. <span data-ttu-id="176cb-113">Bontsa ki a Számlasorok lapot.</span><span class="sxs-lookup"><span data-stu-id="176cb-113">Expand the Invoice lines tab.</span></span>
6. <span data-ttu-id="176cb-114">A Leírás mezőbe írja be a számlasor leírását.</span><span class="sxs-lookup"><span data-stu-id="176cb-114">In the Description field, enter a description of the invoice line.</span></span>
7. <span data-ttu-id="176cb-115">A fő számla mezőben válasszon ki egy bevételi számlát.</span><span class="sxs-lookup"><span data-stu-id="176cb-115">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="176cb-116">Egy vevői jóváírás ellentranzakciójának számláját a teljes számlaösszeghez a Vevői feladási profilok lapján választhatja ki.</span><span class="sxs-lookup"><span data-stu-id="176cb-116">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
8. <span data-ttu-id="176cb-117">Az Áfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="176cb-117">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="176cb-118">Az aktuális számlasor áfacsoportja, amely a vevőkód alapértelmezett áfacsoportja.</span><span class="sxs-lookup"><span data-stu-id="176cb-118">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
9. <span data-ttu-id="176cb-119">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="176cb-119">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="176cb-120">A Cikkáfacsoport mezőben válassza ki az aktuális számlasorhoz tartozó cikkáfacsoportot.</span><span class="sxs-lookup"><span data-stu-id="176cb-120">In the Item tax group field, select the item sales tax group for the current invoice line.</span></span>
11. <span data-ttu-id="176cb-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="176cb-121">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="176cb-122">Az Egységár mezőben megadhatja vagy megtekintheti a számlasor egységárát.</span><span class="sxs-lookup"><span data-stu-id="176cb-122">In the Unit price field, enter or view the price per unit for the invoice line</span></span>
    * <span data-ttu-id="176cb-123">A rendszer ezt az összeget megszorozza a Mennyiség mezőben szereplő értékkel, így határozza meg a számlasor összegét.</span><span class="sxs-lookup"><span data-stu-id="176cb-123">This amount is multiplied by the Quantity field to determine the invoice line amount.</span></span>  
13. <span data-ttu-id="176cb-124">Adjon új sort a szabadszöveges számlasablonhoz.</span><span class="sxs-lookup"><span data-stu-id="176cb-124">Add a new line to free text invoice template.</span></span>
14. <span data-ttu-id="176cb-125">A Leírás mezőbe írja be a számlasor leírását.</span><span class="sxs-lookup"><span data-stu-id="176cb-125">In the Description field, enter a description of the invoice line.</span></span>
15. <span data-ttu-id="176cb-126">A fő számla mezőben válasszon ki egy bevételi számlát.</span><span class="sxs-lookup"><span data-stu-id="176cb-126">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="176cb-127">Egy vevői jóváírás ellentranzakciójának számláját a teljes számlaösszeghez a Vevői feladási profilok lapján választhatja ki.</span><span class="sxs-lookup"><span data-stu-id="176cb-127">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
16. <span data-ttu-id="176cb-128">Az Áfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="176cb-128">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="176cb-129">Az aktuális számlasor áfacsoportja, amely a vevőkód alapértelmezett áfacsoportja.</span><span class="sxs-lookup"><span data-stu-id="176cb-129">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
17. <span data-ttu-id="176cb-130">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="176cb-130">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="176cb-131">A Cikkáfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="176cb-131">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="176cb-132">Az aktuális számlatételhez tartozó cikkáfacsoport.</span><span class="sxs-lookup"><span data-stu-id="176cb-132">The item sales tax group for the current invoice line.</span></span>  
19. <span data-ttu-id="176cb-133">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="176cb-133">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="176cb-134">Megadhatja vagy megtekintheti a számlasoron szereplő egységek számát</span><span class="sxs-lookup"><span data-stu-id="176cb-134">Enter or view the number of units for the invoice line</span></span>
    * <span data-ttu-id="176cb-135">A rendszer ezt a számot megszorozza az Egységár mezőben szereplő értékkel, így határozza meg a számlasor összegét.</span><span class="sxs-lookup"><span data-stu-id="176cb-135">This number is multiplied by the value in the Unit price field to determine the invoice line amount.</span></span>  
21. <span data-ttu-id="176cb-136">Megadhatja vagy megtekintheti a számlasor egységárát.</span><span class="sxs-lookup"><span data-stu-id="176cb-136">Enter or view the price per unit for the invoice line.</span></span> 
    * <span data-ttu-id="176cb-137">A rendszer ezt az összeget megszorozza a Mennyiség mezőben szereplő értékkel, így határozza meg a számlasor összegét.</span><span class="sxs-lookup"><span data-stu-id="176cb-137">This amount is multiplied by the value in the Quantity field to determine the invoice line amount.</span></span>  
22. <span data-ttu-id="176cb-138">Megtekintheti és módosíthatja a könyvelési felosztást egy adott sorhoz és annak gyermeksoraihoz.</span><span class="sxs-lookup"><span data-stu-id="176cb-138">View and modify the accounting distributions for an individual line and any child lines.</span></span>
    * <span data-ttu-id="176cb-139">A könyvelési felosztások használatával lehet meghatározni, hogy hogyan lesz az összeg elszámolva, például hogyan lesznek könyvelve a bevételek, adó és költségek a szabadszöveges számlán.</span><span class="sxs-lookup"><span data-stu-id="176cb-139">Accounting distributions define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span>  
23. <span data-ttu-id="176cb-140">Frissítheti a könyvelési felosztást a kiválasztott számlasorhoz.</span><span class="sxs-lookup"><span data-stu-id="176cb-140">Update the accounting distributions for the selected invoice line.</span></span>
24. <span data-ttu-id="176cb-141">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="176cb-141">Click Close.</span></span>


