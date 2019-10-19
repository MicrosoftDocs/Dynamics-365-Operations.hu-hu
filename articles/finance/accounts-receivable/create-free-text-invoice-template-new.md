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
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8281de3cb336d9392a6a97f98e51a2a139a384c5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189131"
---
# <a name="create-a-free-text-invoice-template"></a><span data-ttu-id="77dde-103">Szabadszöveges számlasablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="77dde-103">Create a free text invoice template</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="77dde-104">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="77dde-104">For this walkthrough, use the USMF demo company.</span></span> <span data-ttu-id="77dde-105">Az eljárást az a felhasználó használja, aki felelős a kintlévőségek számláinak kezeléséért és feldolgozásáért.</span><span class="sxs-lookup"><span data-stu-id="77dde-105">This procedure is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

## <a name="create-a-template"></a><span data-ttu-id="77dde-106">Sablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="77dde-106">Create a template</span></span>

1. <span data-ttu-id="77dde-107">Ugrás a Kinnlevőségek > Számlák > Ismétlődő számlák > Szabadszöveges számlasablonok pontra.</span><span class="sxs-lookup"><span data-stu-id="77dde-107">Go to Accounts receivable > Invoices > Recurring invoices > Free text invoice templates.</span></span>
    * <span data-ttu-id="77dde-108">A képernyőn szabadszöveges számlasablonokat hozhat létre, amelyek számlasorokat, költségeket, könyvelési felosztási sablont és főkönyvi számlainformációkat tartalmazhatnak.</span><span class="sxs-lookup"><span data-stu-id="77dde-108">Use this form to create free text invoice templates that can include invoice lines, charges, an accounting distribution template, and ledger account information.</span></span>  
2. <span data-ttu-id="77dde-109">Új szabadszöveges számlasablon létrehozásához kattintson az „Új” elemre.</span><span class="sxs-lookup"><span data-stu-id="77dde-109">Click 'New' to create a new free text invoice template.</span></span>
3. <span data-ttu-id="77dde-110">Írjon be egy értéket a Sablonnév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="77dde-110">In the Template name field, type a value.</span></span>
    * <span data-ttu-id="77dde-111">A „Sablonnév” egyedileg azonosítja a szabadszöveges számla sablonját.</span><span class="sxs-lookup"><span data-stu-id="77dde-111">‘Template name’ uniquely identifies a free text invoice template.</span></span> <span data-ttu-id="77dde-112">Egy „Sablonnév” csakis egyetlen sablonhoz tartozhat.</span><span class="sxs-lookup"><span data-stu-id="77dde-112">No two templates can have the same ‘Template name’.</span></span>  
4. <span data-ttu-id="77dde-113">Adja meg a sablon leírását a Leírás mezőben.</span><span class="sxs-lookup"><span data-stu-id="77dde-113">In the Description field, enter a description of the template.</span></span>
5. <span data-ttu-id="77dde-114">Bontsa ki a Számlasorok lapot.</span><span class="sxs-lookup"><span data-stu-id="77dde-114">Expand the Invoice lines tab.</span></span>
6. <span data-ttu-id="77dde-115">A Leírás mezőbe írja be a számlasor leírását.</span><span class="sxs-lookup"><span data-stu-id="77dde-115">In the Description field, enter a description of the invoice line.</span></span>
7. <span data-ttu-id="77dde-116">A fő számla mezőben válasszon ki egy bevételi számlát.</span><span class="sxs-lookup"><span data-stu-id="77dde-116">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="77dde-117">Egy vevői jóváírás ellentranzakciójának számláját a teljes számlaösszeghez a Vevői feladási profilok lapján választhatja ki.</span><span class="sxs-lookup"><span data-stu-id="77dde-117">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
8. <span data-ttu-id="77dde-118">Az Áfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="77dde-118">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="77dde-119">Az aktuális számlasor áfacsoportja, amely a vevőkód alapértelmezett áfacsoportja.</span><span class="sxs-lookup"><span data-stu-id="77dde-119">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
9. <span data-ttu-id="77dde-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="77dde-120">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="77dde-121">A Cikkáfacsoport mezőben válassza ki az aktuális számlasorhoz tartozó cikkáfacsoportot.</span><span class="sxs-lookup"><span data-stu-id="77dde-121">In the Item tax group field, select the item sales tax group for the current invoice line.</span></span>
11. <span data-ttu-id="77dde-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="77dde-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="77dde-123">Az Egységár mezőben megadhatja vagy megtekintheti a számlasor egységárát.</span><span class="sxs-lookup"><span data-stu-id="77dde-123">In the Unit price field, enter or view the price per unit for the invoice line</span></span>
    * <span data-ttu-id="77dde-124">A rendszer ezt az összeget megszorozza a Mennyiség mezőben szereplő értékkel, így határozza meg a számlasor összegét.</span><span class="sxs-lookup"><span data-stu-id="77dde-124">This amount is multiplied by the Quantity field to determine the invoice line amount.</span></span>  
13. <span data-ttu-id="77dde-125">Adjon új sort a szabadszöveges számlasablonhoz.</span><span class="sxs-lookup"><span data-stu-id="77dde-125">Add a new line to free text invoice template.</span></span>
14. <span data-ttu-id="77dde-126">A Leírás mezőbe írja be a számlasor leírását.</span><span class="sxs-lookup"><span data-stu-id="77dde-126">In the Description field, enter a description of the invoice line.</span></span>
15. <span data-ttu-id="77dde-127">A fő számla mezőben válasszon ki egy bevételi számlát.</span><span class="sxs-lookup"><span data-stu-id="77dde-127">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="77dde-128">Egy vevői jóváírás ellentranzakciójának számláját a teljes számlaösszeghez a Vevői feladási profilok lapján választhatja ki.</span><span class="sxs-lookup"><span data-stu-id="77dde-128">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
16. <span data-ttu-id="77dde-129">Az Áfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="77dde-129">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="77dde-130">Az aktuális számlasor áfacsoportja, amely a vevőkód alapértelmezett áfacsoportja.</span><span class="sxs-lookup"><span data-stu-id="77dde-130">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
17. <span data-ttu-id="77dde-131">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="77dde-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="77dde-132">A Cikkáfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="77dde-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="77dde-133">Az aktuális számlatételhez tartozó cikkáfacsoport.</span><span class="sxs-lookup"><span data-stu-id="77dde-133">The item sales tax group for the current invoice line.</span></span>  
19. <span data-ttu-id="77dde-134">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="77dde-134">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="77dde-135">Megadhatja vagy megtekintheti a számlasoron szereplő egységek számát</span><span class="sxs-lookup"><span data-stu-id="77dde-135">Enter or view the number of units for the invoice line</span></span>
    * <span data-ttu-id="77dde-136">A rendszer ezt a számot megszorozza az Egységár mezőben szereplő értékkel, így határozza meg a számlasor összegét.</span><span class="sxs-lookup"><span data-stu-id="77dde-136">This number is multiplied by the value in the Unit price field to determine the invoice line amount.</span></span>  
21. <span data-ttu-id="77dde-137">Megadhatja vagy megtekintheti a számlasor egységárát.</span><span class="sxs-lookup"><span data-stu-id="77dde-137">Enter or view the price per unit for the invoice line.</span></span> 
    * <span data-ttu-id="77dde-138">A rendszer ezt az összeget megszorozza a Mennyiség mezőben szereplő értékkel, így határozza meg a számlasor összegét.</span><span class="sxs-lookup"><span data-stu-id="77dde-138">This amount is multiplied by the value in the Quantity field to determine the invoice line amount.</span></span>  
22. <span data-ttu-id="77dde-139">Megtekintheti és módosíthatja a könyvelési felosztást egy adott sorhoz és annak gyermeksoraihoz.</span><span class="sxs-lookup"><span data-stu-id="77dde-139">View and modify the accounting distributions for an individual line and any child lines.</span></span>
    * <span data-ttu-id="77dde-140">A könyvelési felosztások használatával lehet meghatározni, hogy hogyan lesz az összeg elszámolva, például hogyan lesznek könyvelve a bevételek, adó és költségek a szabadszöveges számlán.</span><span class="sxs-lookup"><span data-stu-id="77dde-140">Accounting distributions define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span>  
23. <span data-ttu-id="77dde-141">Frissítheti a könyvelési felosztást a kiválasztott számlasorhoz.</span><span class="sxs-lookup"><span data-stu-id="77dde-141">Update the accounting distributions for the selected invoice line.</span></span>
24. <span data-ttu-id="77dde-142">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="77dde-142">Click Close.</span></span>

## <a name="save-a-free-text-invoice-as-a-template"></a><span data-ttu-id="77dde-143">Szabadszöveges számla sablonként mentése</span><span class="sxs-lookup"><span data-stu-id="77dde-143">Save a free text invoice as a template</span></span>
<span data-ttu-id="77dde-144">Egy meglévő szabadszöveges számlát menthet sablonként is.</span><span class="sxs-lookup"><span data-stu-id="77dde-144">You can also save an existing free text invoice as a template.</span></span> <span data-ttu-id="77dde-145">Kiválasztásakor a Mentés sablonhoz a Számla lapjáról, adja meg a sablon nevét és leírását.</span><span class="sxs-lookup"><span data-stu-id="77dde-145">When you select Save to template from the Invoice tab, provide a name and a description for the template.</span></span> <span data-ttu-id="77dde-146">Ha ilyen nevű sablon már létezik, értesítés jelenik meg, hogy már létezik ilyen nevű sablon.</span><span class="sxs-lookup"><span data-stu-id="77dde-146">If a template with the name already exists, you will see a notification that a template with that name already exists.</span></span> <span data-ttu-id="77dde-147">Még rákattinthat a felülíráshoz az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="77dde-147">You can still click on Ok to replace it.</span></span> 
