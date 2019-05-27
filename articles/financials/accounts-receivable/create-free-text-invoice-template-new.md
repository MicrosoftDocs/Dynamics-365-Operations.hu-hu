---
title: Szabadszöveges számlasablon létrehozása
description: Ez az eljárás bemutatja a szabadszöveges számla sablon létrehozását.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91f2ec2f8ab21616c6a1b886ee89d6faf84023e4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559503"
---
# <a name="create-a-free-text-invoice-template"></a><span data-ttu-id="d117b-103">Szabadszöveges számlasablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="d117b-103">Create a free text invoice template</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d117b-104">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="d117b-104">For this walkthrough, use the USMF demo company.</span></span> <span data-ttu-id="d117b-105">Az eljárást az a felhasználó használja, aki felelős a kintlévőségek számláinak kezeléséért és feldolgozásáért.</span><span class="sxs-lookup"><span data-stu-id="d117b-105">This procedure is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

## <a name="create-a-template"></a><span data-ttu-id="d117b-106">Sablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="d117b-106">Create a template</span></span>

1. <span data-ttu-id="d117b-107">Ugrás a Kinnlevőségek > Számlák > Ismétlődő számlák > Szabadszöveges számlasablonok pontra.</span><span class="sxs-lookup"><span data-stu-id="d117b-107">Go to Accounts receivable > Invoices > Recurring invoices > Free text invoice templates.</span></span>
    * <span data-ttu-id="d117b-108">A képernyőn szabadszöveges számlasablonokat hozhat létre, amelyek számlasorokat, költségeket, könyvelési felosztási sablont és főkönyvi számlainformációkat tartalmazhatnak.</span><span class="sxs-lookup"><span data-stu-id="d117b-108">Use this form to create free text invoice templates that can include invoice lines, charges, an accounting distribution template, and ledger account information.</span></span>  
2. <span data-ttu-id="d117b-109">Új szabadszöveges számlasablon létrehozásához kattintson az „Új” elemre.</span><span class="sxs-lookup"><span data-stu-id="d117b-109">Click 'New' to create a new free text invoice template.</span></span>
3. <span data-ttu-id="d117b-110">Írjon be egy értéket a Sablonnév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d117b-110">In the Template name field, type a value.</span></span>
    * <span data-ttu-id="d117b-111">A „Sablonnév” egyedileg azonosítja a szabadszöveges számla sablonját.</span><span class="sxs-lookup"><span data-stu-id="d117b-111">‘Template name’ uniquely identifies a free text invoice template.</span></span> <span data-ttu-id="d117b-112">Egy „Sablonnév” csakis egyetlen sablonhoz tartozhat.</span><span class="sxs-lookup"><span data-stu-id="d117b-112">No two templates can have the same ‘Template name’.</span></span>  
4. <span data-ttu-id="d117b-113">Adja meg a sablon leírását a Leírás mezőben.</span><span class="sxs-lookup"><span data-stu-id="d117b-113">In the Description field, enter a description of the template.</span></span>
5. <span data-ttu-id="d117b-114">Bontsa ki a Számlasorok lapot.</span><span class="sxs-lookup"><span data-stu-id="d117b-114">Expand the Invoice lines tab.</span></span>
6. <span data-ttu-id="d117b-115">A Leírás mezőbe írja be a számlasor leírását.</span><span class="sxs-lookup"><span data-stu-id="d117b-115">In the Description field, enter a description of the invoice line.</span></span>
7. <span data-ttu-id="d117b-116">A fő számla mezőben válasszon ki egy bevételi számlát.</span><span class="sxs-lookup"><span data-stu-id="d117b-116">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="d117b-117">Egy vevői jóváírás ellentranzakciójának számláját a teljes számlaösszeghez a Vevői feladási profilok lapján választhatja ki.</span><span class="sxs-lookup"><span data-stu-id="d117b-117">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
8. <span data-ttu-id="d117b-118">Az Áfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d117b-118">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d117b-119">Az aktuális számlasor áfacsoportja, amely a vevőkód alapértelmezett áfacsoportja.</span><span class="sxs-lookup"><span data-stu-id="d117b-119">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
9. <span data-ttu-id="d117b-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d117b-120">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="d117b-121">A Cikkáfacsoport mezőben válassza ki az aktuális számlasorhoz tartozó cikkáfacsoportot.</span><span class="sxs-lookup"><span data-stu-id="d117b-121">In the Item tax group field, select the item sales tax group for the current invoice line.</span></span>
11. <span data-ttu-id="d117b-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d117b-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="d117b-123">Az Egységár mezőben megadhatja vagy megtekintheti a számlasor egységárát.</span><span class="sxs-lookup"><span data-stu-id="d117b-123">In the Unit price field, enter or view the price per unit for the invoice line</span></span>
    * <span data-ttu-id="d117b-124">A rendszer ezt az összeget megszorozza a Mennyiség mezőben szereplő értékkel, így határozza meg a számlasor összegét.</span><span class="sxs-lookup"><span data-stu-id="d117b-124">This amount is multiplied by the Quantity field to determine the invoice line amount.</span></span>  
13. <span data-ttu-id="d117b-125">Adjon új sort a szabadszöveges számlasablonhoz.</span><span class="sxs-lookup"><span data-stu-id="d117b-125">Add a new line to free text invoice template.</span></span>
14. <span data-ttu-id="d117b-126">A Leírás mezőbe írja be a számlasor leírását.</span><span class="sxs-lookup"><span data-stu-id="d117b-126">In the Description field, enter a description of the invoice line.</span></span>
15. <span data-ttu-id="d117b-127">A fő számla mezőben válasszon ki egy bevételi számlát.</span><span class="sxs-lookup"><span data-stu-id="d117b-127">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="d117b-128">Egy vevői jóváírás ellentranzakciójának számláját a teljes számlaösszeghez a Vevői feladási profilok lapján választhatja ki.</span><span class="sxs-lookup"><span data-stu-id="d117b-128">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
16. <span data-ttu-id="d117b-129">Az Áfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d117b-129">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d117b-130">Az aktuális számlasor áfacsoportja, amely a vevőkód alapértelmezett áfacsoportja.</span><span class="sxs-lookup"><span data-stu-id="d117b-130">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
17. <span data-ttu-id="d117b-131">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d117b-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="d117b-132">A Cikkáfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d117b-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d117b-133">Az aktuális számlatételhez tartozó cikkáfacsoport.</span><span class="sxs-lookup"><span data-stu-id="d117b-133">The item sales tax group for the current invoice line.</span></span>  
19. <span data-ttu-id="d117b-134">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d117b-134">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="d117b-135">Megadhatja vagy megtekintheti a számlasoron szereplő egységek számát</span><span class="sxs-lookup"><span data-stu-id="d117b-135">Enter or view the number of units for the invoice line</span></span>
    * <span data-ttu-id="d117b-136">A rendszer ezt a számot megszorozza az Egységár mezőben szereplő értékkel, így határozza meg a számlasor összegét.</span><span class="sxs-lookup"><span data-stu-id="d117b-136">This number is multiplied by the value in the Unit price field to determine the invoice line amount.</span></span>  
21. <span data-ttu-id="d117b-137">Megadhatja vagy megtekintheti a számlasor egységárát.</span><span class="sxs-lookup"><span data-stu-id="d117b-137">Enter or view the price per unit for the invoice line.</span></span> 
    * <span data-ttu-id="d117b-138">A rendszer ezt az összeget megszorozza a Mennyiség mezőben szereplő értékkel, így határozza meg a számlasor összegét.</span><span class="sxs-lookup"><span data-stu-id="d117b-138">This amount is multiplied by the value in the Quantity field to determine the invoice line amount.</span></span>  
22. <span data-ttu-id="d117b-139">Megtekintheti és módosíthatja a könyvelési felosztást egy adott sorhoz és annak gyermeksoraihoz.</span><span class="sxs-lookup"><span data-stu-id="d117b-139">View and modify the accounting distributions for an individual line and any child lines.</span></span>
    * <span data-ttu-id="d117b-140">A könyvelési felosztások használatával lehet meghatározni, hogy hogyan lesz az összeg elszámolva, például hogyan lesznek könyvelve a bevételek, adó és költségek a szabadszöveges számlán.</span><span class="sxs-lookup"><span data-stu-id="d117b-140">Accounting distributions define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span>  
23. <span data-ttu-id="d117b-141">Frissítheti a könyvelési felosztást a kiválasztott számlasorhoz.</span><span class="sxs-lookup"><span data-stu-id="d117b-141">Update the accounting distributions for the selected invoice line.</span></span>
24. <span data-ttu-id="d117b-142">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="d117b-142">Click Close.</span></span>

## <a name="save-a-free-text-invoice-as-a-template"></a><span data-ttu-id="d117b-143">Szabadszöveges számla sablonként mentése</span><span class="sxs-lookup"><span data-stu-id="d117b-143">Save a free text invoice as a template</span></span>
<span data-ttu-id="d117b-144">Egy meglévő szabadszöveges számlát menthet sablonként is.</span><span class="sxs-lookup"><span data-stu-id="d117b-144">You can also save an existing free text invoice as a template.</span></span> <span data-ttu-id="d117b-145">Kiválasztásakor a Mentés sablonhoz a Számla lapjáról, adja meg a sablon nevét és leírását.</span><span class="sxs-lookup"><span data-stu-id="d117b-145">When you select Save to template from the Invoice tab, provide a name and a description for the template.</span></span> <span data-ttu-id="d117b-146">Ha ilyen nevű sablon már létezik, értesítés jelenik meg, hogy már létezik ilyen nevű sablon.</span><span class="sxs-lookup"><span data-stu-id="d117b-146">If a template with the name already exists, you will see a notification that a template with that name already exists.</span></span> <span data-ttu-id="d117b-147">Még rákattinthat a felülíráshoz az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="d117b-147">You can still click on Ok to replace it.</span></span> 
