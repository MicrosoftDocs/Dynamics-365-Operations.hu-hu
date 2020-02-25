---
title: Szabadszöveges számla létrehozása
description: Ez a témakör bemutatja, hogyan lehet szabadszöveges számlákat létrehozni.
author: mikefalkner
manager: AnnBe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 909dd5bcaf1fa3b82adb44d265e312f9acc607d2
ms.sourcegitcommit: 9168621ca9b5061c65f3e05dbc5918b6a11d53d5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2020
ms.locfileid: "3000070"
---
# <a name="create-a-free-text-invoice"></a><span data-ttu-id="64000-103">Szabadszöveges számla létrehozása</span><span class="sxs-lookup"><span data-stu-id="64000-103">Create a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64000-104">Ez a témakör bemutatja, hogyan lehet szabadszöveges számlákat létrehozni.</span><span class="sxs-lookup"><span data-stu-id="64000-104">This topic explains how to create free text invoices.</span></span> <span data-ttu-id="64000-105">Ez az eljárás az **USMF** bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="64000-105">For the procedure, use the **USMF** demo company.</span></span>

## <a name="create-a-free-text-invoice"></a><span data-ttu-id="64000-106">Szabadszöveges számla létrehozása</span><span class="sxs-lookup"><span data-stu-id="64000-106">Create a free text invoice</span></span>

1. <span data-ttu-id="64000-107">Ugorjon a következőre: **Kinnlévőségek \> Számlák \> Kizárólag szabadszöveges számlák**.</span><span class="sxs-lookup"><span data-stu-id="64000-107">Go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>
2. <span data-ttu-id="64000-108">**Új** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="64000-108">Select **New**.</span></span>
3. <span data-ttu-id="64000-109">Válasszon egy értéket a **Vevői számla** mezőnek.</span><span class="sxs-lookup"><span data-stu-id="64000-109">In the **Customer account** field, select a value.</span></span>

    * <span data-ttu-id="64000-110">Alapértelmezett esetben a vevői számlához kiválasztott számla lesz pénzügyi adatnak használva</span><span class="sxs-lookup"><span data-stu-id="64000-110">By default, the account that is selected as the customer account is used as the invoice account.</span></span>
    * <span data-ttu-id="64000-111">A könyvelési állapot **Folyamatban** állapottal kezdődik, ha a számla nincs feladva.</span><span class="sxs-lookup"><span data-stu-id="64000-111">If the invoice isn't posted, the accounting status starts with **In process**.</span></span>
    * <span data-ttu-id="64000-112">A számlaszám a számla feladásakor kerül hozzárendelésre.</span><span class="sxs-lookup"><span data-stu-id="64000-112">The invoice number will be assigned when the invoice is posted.</span></span>
    * <span data-ttu-id="64000-113">SEPA típusú felhatalmazások használatakor a beszedési megbízási felhatalmazást automatikusan kitölti a program, ha a vevői számla lehetőséget választja.</span><span class="sxs-lookup"><span data-stu-id="64000-113">If you're using Single Euro Payments Area (SEPA) mandates, the direct debit mandate is automatically entered when you select the customer account.</span></span>

4. <span data-ttu-id="64000-114">A **Leírás** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="64000-114">In the **Description** field, enter a value.</span></span>
5. <span data-ttu-id="64000-115">A **Fő számla** mezőben adja meg egy számlaszámot, amelynek nincsenek dimenziói.</span><span class="sxs-lookup"><span data-stu-id="64000-115">In the **Main account** field, specify an account number that doesn't have dimensions.</span></span> <span data-ttu-id="64000-116">A dimenziók megadását az útmutató később ismerteti.</span><span class="sxs-lookup"><span data-stu-id="64000-116">You will enter dimensions later in this topic.</span></span>

    <span data-ttu-id="64000-117">Megadhat továbbá egy vagy több karaktert a fő számlából, és használhatja a keresés funkciót a számla megtalálásához.</span><span class="sxs-lookup"><span data-stu-id="64000-117">You can also enter one or more characters for the main account, and use the lookup to find the account.</span></span>

6. <span data-ttu-id="64000-118">Válassza ki a **Soradatok** gyorslapot hogy hozzáadhasson dimenziókat a fő számlához.</span><span class="sxs-lookup"><span data-stu-id="64000-118">Select the **Line details** FastTab to add dimensions to the main account.</span></span>
7. <span data-ttu-id="64000-119">Válassza ki a **Pénzügyi dimenziók** lapot.</span><span class="sxs-lookup"><span data-stu-id="64000-119">Select the **Financial dimensions line** tab.</span></span>

    * <span data-ttu-id="64000-120">A dimenziók kizárólag a kijelölt sorra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="64000-120">The dimensions are for the selected line only.</span></span>
    * <span data-ttu-id="64000-121">Az áfacsoport a vevőtől származik.</span><span class="sxs-lookup"><span data-stu-id="64000-121">The sales tax group is filled in from the customer.</span></span> <span data-ttu-id="64000-122">Ha a vevő nem rendelkezik áfacsoporttal, akkor a rendszer a fő számla áfacsoportját használja.</span><span class="sxs-lookup"><span data-stu-id="64000-122">If the customer doesn't have a sales tax group, the sales tax group from the main account is used.</span></span>
    * <span data-ttu-id="64000-123">A cikkek áfacsoportja a fő számla alapján kerül megadásra.</span><span class="sxs-lookup"><span data-stu-id="64000-123">The items sales tax group is filled in from the main account.</span></span> <span data-ttu-id="64000-124">Ha a fő számla nem rendelkezik cikkekre vonatkozó áfacsoporttal, akkor a Főkönyv áfa paramétereiben meghatározott cikk áfacsoport használatos.</span><span class="sxs-lookup"><span data-stu-id="64000-124">If the main account doesn't have an item sales tax group, the item sales tax group that is specified in the sales tax parameters in General ledger is used.</span></span>

8. <span data-ttu-id="64000-125">Opcionális: Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="64000-125">Optional: In the **Quantity** field, enter a number.</span></span>
9. <span data-ttu-id="64000-126">Opcionális: Adjon meg egy számot az **Egységár** mezőben.</span><span class="sxs-lookup"><span data-stu-id="64000-126">Optional: In the **Unit price** field, enter a number.</span></span>

    <span data-ttu-id="64000-127">Az összeg a mennyiség és az egységár szorzata alapján kerül kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="64000-127">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="64000-128">Ugyanakkor felülírhatja a számítást, ha bevisz egy összeget.</span><span class="sxs-lookup"><span data-stu-id="64000-128">However, you can override that calculation by entering an amount.</span></span>

10. <span data-ttu-id="64000-129">Válassza az **Áfa** lehetőséget a számla számított áfájának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="64000-129">Select **Sales tax** to view the sales tax that is calculated for the invoice.</span></span>

    <span data-ttu-id="64000-130">Ezen a lapon megtekintheti az áfaösszegeket, vagy felülírhatja ezeket az összegeket a **Kiigazítás** lapon.</span><span class="sxs-lookup"><span data-stu-id="64000-130">You can view the sales tax amounts on this page, or you can override the amounts on the **Adjustment** tab.</span></span>

11. <span data-ttu-id="64000-131">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64000-131">Select **OK**.</span></span>
12. <span data-ttu-id="64000-132">Válassza a **Költségek** lehetőséget, ha szeretne költségeket adni a számlához.</span><span class="sxs-lookup"><span data-stu-id="64000-132">Select **Charges** to add a charge to the invoice.</span></span>
13. <span data-ttu-id="64000-133">Írjon be értéket a **Költsgékód** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="64000-133">In the **Charges code** field, enter a value.</span></span>
14. <span data-ttu-id="64000-134">Adjon meg egy számot az **Költségek értéke** mezőben.</span><span class="sxs-lookup"><span data-stu-id="64000-134">In the **Charges value** field, enter a number.</span></span>
15. <span data-ttu-id="64000-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="64000-135">Close the page.</span></span>
16. <span data-ttu-id="64000-136">Kattintson az **Összeg** lehetőségre az összesítő számla részleteinek és végösszegének áttekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="64000-136">Select **Totals** to view a summary of the invoice details and totals.</span></span>
17. <span data-ttu-id="64000-137">Válassza **Bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64000-137">Select **Close**.</span></span>
18. <span data-ttu-id="64000-138">Adja fel a számlát a **Feladás** gombot választva.</span><span class="sxs-lookup"><span data-stu-id="64000-138">Select **Post** to post the invoice.</span></span> <span data-ttu-id="64000-139">Tényleges feladás előtt még van lehetősége a visszavonásra.</span><span class="sxs-lookup"><span data-stu-id="64000-139">You will still have an opportunity to cancel before you actually post.</span></span>

    * <span data-ttu-id="64000-140">A számla nyomtatásának időpontját megváltoztathatja.</span><span class="sxs-lookup"><span data-stu-id="64000-140">You can change the timing of invoice printing.</span></span> <span data-ttu-id="64000-141">Válassza ki a **Jelenlegi** lehetőséget az egyes számlák frissítéskori kinyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="64000-141">Select **Current** to print each invoice as it's updated.</span></span> <span data-ttu-id="64000-142">Válassza ki az **Után** lehetőséget, ekkor az összes számla frissítése után történik a nyomtatás.</span><span class="sxs-lookup"><span data-stu-id="64000-142">Select **After** to print after all invoices have been updated.</span></span>
    * <span data-ttu-id="64000-143">Annak módosításához, hogy a vevő hitelkerete hogyan legyen ellenőrizve a számla feladása előtt, módosítsa az értéket a **Hitelkeret típusa** mezőben.</span><span class="sxs-lookup"><span data-stu-id="64000-143">To change how the customer's credit limit is verified before the invoice is posted, change the value in the **Credit limit type** field.</span></span>
    * <span data-ttu-id="64000-144">Állítsa ezt az opciót **Igen** értékre a számla nyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="64000-144">To print the invoice, set the option to **Yes**.</span></span>
    * <span data-ttu-id="64000-145">Állítsa ezt az opciót **Igen** értékre a számla feladásához.</span><span class="sxs-lookup"><span data-stu-id="64000-145">To post the invoice, set the option to **Yes**.</span></span> <span data-ttu-id="64000-146">Feladás nélkül is kinyomtathatja a számlát.</span><span class="sxs-lookup"><span data-stu-id="64000-146">You can print the invoice without posting it.</span></span>

19. <span data-ttu-id="64000-147">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64000-147">Select **OK**.</span></span>

## <a name="copy-lines"></a><span data-ttu-id="64000-148">Sorok másolása</span><span class="sxs-lookup"><span data-stu-id="64000-148">Copy lines</span></span>
<span data-ttu-id="64000-149">A szabadszöveges számlán szereplő sorok másolásához kiválaszthat egy vagy több sort, majd válassza a **Kiválasztott sorok másolása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64000-149">To copy lines on a free text invoice, select one or more lines, and then select **Copy selected lines**.</span></span> <span data-ttu-id="64000-150">Megadhatja a létrehozni kívánt másolatok számát, és a jegyzeteket és a mellékleteket is másolhatja.</span><span class="sxs-lookup"><span data-stu-id="64000-150">You can specify the number of copies to make, and you can also copy notes and attachments.</span></span> <span data-ttu-id="64000-151">A felosztás másolhatók, vagy engedélyezheti újra létrehozásukat a könyveléskor.</span><span class="sxs-lookup"><span data-stu-id="64000-151">You can either copy the distributions or let them be re-created when you post.</span></span>

<span data-ttu-id="64000-152">A sorok másolása után módosíthatja az adatokat, szükség szerint.</span><span class="sxs-lookup"><span data-stu-id="64000-152">After you copy lines, you can edit the information as you require.</span></span>

## <a name="create-a-free-text-invoice-from-a-template"></a><span data-ttu-id="64000-153">Szabadszöveges számla sablonól létrehozása</span><span class="sxs-lookup"><span data-stu-id="64000-153">Create a free text invoice from a template</span></span>
<span data-ttu-id="64000-154">Szabadszöveges számla sablonól létrehozása is lehetséges.</span><span class="sxs-lookup"><span data-stu-id="64000-154">You can create a free text invoice from a template.</span></span> <span data-ttu-id="64000-155">Az **Új sablonból** kiválasztásakor a **Számla** lapon ki lehet választani a sablon nevét és az új szabadszöveges számlához kapcsolódó vevőszámlát.</span><span class="sxs-lookup"><span data-stu-id="64000-155">When you select **New from template** on the **Invoice** tab, you can select a template name and the customer account for the new free text invoice.</span></span> <span data-ttu-id="64000-156">Alapértelmezett értékek, például a fizetési feltételek és a fizetési mód kitölthető a vevőtől, vagy a sablonnal mentett értékek is használhatók.</span><span class="sxs-lookup"><span data-stu-id="64000-156">Default values, such as the terms of payment and method of payment, can be automatically filled in from the customer, or you can use the values that were saved in the template.</span></span>

<span data-ttu-id="64000-157">Ekkor létrejön a szabadszöveges számla, és igény szerint szerkesztheti az értékeket.</span><span class="sxs-lookup"><span data-stu-id="64000-157">A new free text invoice is created, and you can edit the values as you require.</span></span>
