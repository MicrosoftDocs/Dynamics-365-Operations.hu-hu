--- 
title: "Szabadszöveges számla létrehozása"
description: "Ez a cikk bemutatja a szabadszöveges vevői számla létrehozását."
author: mikefalkner
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f69505f0c6137121cae92d42d052b244326c8436
ms.openlocfilehash: 2a611bdd4dd97109709ed355eb80471e27413744
ms.contentlocale: hu-hu
ms.lasthandoff: 06/28/2018

---

# <a name="create-a-free-text-invoice"></a><span data-ttu-id="06681-103">Szabadszöveges számla létrehozása</span><span class="sxs-lookup"><span data-stu-id="06681-103">Create a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="06681-104">Ez a cikk bemutatja a szabadszöveges vevői számla létrehozását.</span><span class="sxs-lookup"><span data-stu-id="06681-104">This article demonstrates how to create a free text invoice.</span></span> <span data-ttu-id="06681-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="06681-105">For this procedure, use the USMF demo company.</span></span>

## <a name="create-a-free-text-invoice"></a><span data-ttu-id="06681-106">Szabadszöveges számla létrehozása</span><span class="sxs-lookup"><span data-stu-id="06681-106">Create a free text invoice</span></span>

1. <span data-ttu-id="06681-107">Ugorjon a Kinnlévőségek > Számlák > Kizárólag szabadszöveges számlák pontra.</span><span class="sxs-lookup"><span data-stu-id="06681-107">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="06681-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="06681-108">Click New.</span></span>
3. <span data-ttu-id="06681-109">Válasszon egy értéket a Vevői számla mezőnek.</span><span class="sxs-lookup"><span data-stu-id="06681-109">In the Customer account field, select a value.</span></span>
    * <span data-ttu-id="06681-110">A számla alapértelmezett esetben a vevői számlához használt példány.</span><span class="sxs-lookup"><span data-stu-id="06681-110">The invoice account will default to the same account used for the customer account.</span></span>   
    * <span data-ttu-id="06681-111">A könyvelési állapot Folyamatban állapottal kezdődik, ha a számla nincs feladva.</span><span class="sxs-lookup"><span data-stu-id="06681-111">The accounting status starts with In process if the invoice is not posted.</span></span>   
    * <span data-ttu-id="06681-112">A számlaszám a számla feladásakor kerül hozzárendelésre.</span><span class="sxs-lookup"><span data-stu-id="06681-112">The invoice number will be assigned when the invoice is posted.</span></span>  
    * <span data-ttu-id="06681-113">SEPA típusú felhatalmazások használatakor a beszedési megbízási felhatalmazást automatikusan kitölti a program egy felhatalmazással, ha a vevői számla lehetőséget választja.</span><span class="sxs-lookup"><span data-stu-id="06681-113">If you are using SEPA mandates, the direct debit mandate will be automatically populated with a mandate when you select the customer account.</span></span>  
4. <span data-ttu-id="06681-114">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="06681-114">In the Description field, type a value.</span></span>
5. <span data-ttu-id="06681-115">A Fő számla mezőben adja meg a számlaszámot és a dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="06681-115">In the Main account field, specify an account number without dimensions.</span></span>
    * <span data-ttu-id="06681-116">Megadhat továbbá egy vagy több karaktert a fő számlából, és használhatja a keresés funkciót a számlája megtalálásához.</span><span class="sxs-lookup"><span data-stu-id="06681-116">You can also enter one or more characters for the main account and use the lookup to find your account.</span></span> <span data-ttu-id="06681-117">Ebben az útmutatóban később kell megadni a dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="06681-117">You will enter dimensions later on in this guide.</span></span>  
6. <span data-ttu-id="06681-118">Bontsa ki a Soradatok gyorslapját, hogy hozzáadhasson dimenziókat a fő számlájához.</span><span class="sxs-lookup"><span data-stu-id="06681-118">Expand the Line details fasttab so you can add dimensions to your main account.</span></span>
7. <span data-ttu-id="06681-119">Kattintson a Pénzügyi dimenziók lapra.</span><span class="sxs-lookup"><span data-stu-id="06681-119">Click the Financial dimensions line tab.</span></span>
    * <span data-ttu-id="06681-120">A dimenziók kizárólag a kijelölt sorra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="06681-120">The dimensions are for the selected line only.</span></span>    
    * <span data-ttu-id="06681-121">Az áfacsoportot a vevő tölti ki.</span><span class="sxs-lookup"><span data-stu-id="06681-121">The sales tax group is populated from the customer.</span></span> <span data-ttu-id="06681-122">Ha a vevő nem rendelkezik áfacsoporttal, akkor a fő számla áfacsoportját kell használni.</span><span class="sxs-lookup"><span data-stu-id="06681-122">If the customer does not have a sales tax group, the sales tax group from the main account is used.</span></span>  
    * <span data-ttu-id="06681-123">A cikkek áfacsoportja a fő számla alapján kerül kitöltésre.</span><span class="sxs-lookup"><span data-stu-id="06681-123">The items sales tax group is populated from the main account.</span></span> <span data-ttu-id="06681-124">Ha a fő számla nem rendelkezik cikkekre vonatkozó áfacsoporttal, akkor a Főkönyv áfa paramétereiben található cikk áfacsoport használatos.</span><span class="sxs-lookup"><span data-stu-id="06681-124">If the main account does not have an item sales tax group, then the item sales tax group in the General ledger sales tax parameters is used.</span></span>    
8. <span data-ttu-id="06681-125">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="06681-125">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="06681-126">A mennyiség megadása nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="06681-126">The quantity is optional.</span></span>  
9. <span data-ttu-id="06681-127">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="06681-127">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="06681-128">Az egységár megadása nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="06681-128">The unit price is optional.</span></span>  
    * <span data-ttu-id="06681-129">Az összeg a mennyiség és az egységár szorzata alapján kerül kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="06681-129">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="06681-130">Ugyanakkor felülírhatja a számítást, és bevihet egy összeget.</span><span class="sxs-lookup"><span data-stu-id="06681-130">However, you can override that calculation and enter an amount.</span></span>  
10. <span data-ttu-id="06681-131">Kattintson az Áfa lehetőségre a számla számított áfájának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="06681-131">Click on Sales tax to view the sales tax calculated for your invoice.</span></span>
    * <span data-ttu-id="06681-132">Ezen a lapon megtekintheti az áfaösszegeket, vagy felülírhatja ezeket az összegeket a Kiigazítás lapon.</span><span class="sxs-lookup"><span data-stu-id="06681-132">View the sales tax amounts in this page or you can override the amounts on the Adjustment tab.</span></span>  
11. <span data-ttu-id="06681-133">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="06681-133">Click OK.</span></span>
12. <span data-ttu-id="06681-134">Kattintson a Költségek lehetőségre, ha szeretne költségeket adni a számlához.</span><span class="sxs-lookup"><span data-stu-id="06681-134">Click Charges to add a charge to your invoice.</span></span> 
13. <span data-ttu-id="06681-135">Érték beírása a Költségek mezőbe.</span><span class="sxs-lookup"><span data-stu-id="06681-135">In the Charges code field, type a value.</span></span>
14. <span data-ttu-id="06681-136">Adjon meg egy számot az Költségek értéke mezőben.</span><span class="sxs-lookup"><span data-stu-id="06681-136">In the Charges value field, enter a number.</span></span>
15. <span data-ttu-id="06681-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="06681-137">Close the page.</span></span>
16. <span data-ttu-id="06681-138">Kattintson az Összeg lehetőségre az összesítő számla részleteinek és végösszegének áttekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="06681-138">Click Totals to view the summary invoice details and totals.</span></span>
17. <span data-ttu-id="06681-139">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="06681-139">Click Close.</span></span>
18. <span data-ttu-id="06681-140">Adja fel a számlát a Feladás gombra kattintva.</span><span class="sxs-lookup"><span data-stu-id="06681-140">Click Post to post the invoice.</span></span> <span data-ttu-id="06681-141">Érvénytelenítheti feladás előtt.</span><span class="sxs-lookup"><span data-stu-id="06681-141">You will be able to cancel before you post.</span></span>
    * <span data-ttu-id="06681-142">A számla nyomtatásának időpontját megváltoztathatja: Válassza ki a Jelenlegi lehetőséget az egyes számlák kinyomtatásához, vagy válassza ki az Után lehetőséget, ekkor az összes számla frissítése után történik a nyomtatás.</span><span class="sxs-lookup"><span data-stu-id="06681-142">To change the timing of your invoice printing:  Select Current to print each invoice as it is updated   or  Select After to print after all invoices have been updated.</span></span>  
    * <span data-ttu-id="06681-143">Ha szeretné megváltoztatni a vevő hitelkeretének ellenőrzését feladás előtt, akkor változtassa meg a Hitelkeret típusát.</span><span class="sxs-lookup"><span data-stu-id="06681-143">If you want to change how the customer's credit limit is checked before posting, change the Credit limit type.</span></span>  
    * <span data-ttu-id="06681-144">Ha nyomtatni akarja a számlát akkor válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="06681-144">If you want to print the invoice, select Yes.</span></span>  
    * <span data-ttu-id="06681-145">Ha biztosan feladja a számlát akkor válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="06681-145">If you want to post the invoice, select Yes.</span></span> <span data-ttu-id="06681-146">Feladás nélkül is kinyomtathatja a számlát.</span><span class="sxs-lookup"><span data-stu-id="06681-146">You can print the invoice without posting.</span></span>  
19. <span data-ttu-id="06681-147">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="06681-147">Click OK.</span></span>

## <a name="copy-lines"></a><span data-ttu-id="06681-148">Sorok másolása</span><span class="sxs-lookup"><span data-stu-id="06681-148">Copy lines</span></span>
<span data-ttu-id="06681-149">A szabadszöveges számlán szereplő sorok másolásához kiválaszthat egy vagy több sort, és kattintson a Másolás kiválasztott sorok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="06681-149">To copy lines on the free text invoice, select one or more lines and then click Copy selected lines.</span></span> <span data-ttu-id="06681-150">Megadhatja a létrehozni kívánt másolatok számát, és a jegyzeteket és a mellékletek is másolhatja.</span><span class="sxs-lookup"><span data-stu-id="06681-150">You can specify the number of copies that you want to make, and you can also copy notes and attachments.</span></span> <span data-ttu-id="06681-151">A felosztás másolhatók, vagy engedélyezheti a könyvelésekor újra létrehozásukat.</span><span class="sxs-lookup"><span data-stu-id="06681-151">You can copy the distributions or allow them to be recreated when you post.</span></span> <span data-ttu-id="06681-152">Miután sorait másolja, módosíthatja az adatokat, szükség szerint.</span><span class="sxs-lookup"><span data-stu-id="06681-152">Once you copy the lines, you can edit the information as needed.</span></span> 

## <a name="create-a-free-text-invoice-from-a-template"></a><span data-ttu-id="06681-153">Szabadszöveges számla sablonól létrehozása</span><span class="sxs-lookup"><span data-stu-id="06681-153">Create a free text invoice from a template</span></span>
<span data-ttu-id="06681-154">Szabadszöveges számla sablonól létrehozása is lehetséges.</span><span class="sxs-lookup"><span data-stu-id="06681-154">You can create a free text invoice from a template.</span></span> <span data-ttu-id="06681-155">A Számla lapjáról Új sablonból kiválasztásakor választani lehet a sablon nevét és az új szabadszöveges számlához kapcsolódó vevőszámlát.</span><span class="sxs-lookup"><span data-stu-id="06681-155">When you select New from template from the Invoice tab, you can select a template name and the customer account for the new free text invoice.</span></span> <span data-ttu-id="06681-156">Megválaszthatja az alapértelmezett értékeket, például a fizetési feltételeket és a fizetési módot a vevőtől, vagy a sablonnal mentett értékek is használhatók.</span><span class="sxs-lookup"><span data-stu-id="06681-156">You can also choose to default values such as the terms of payment and method of payment from the customer or use the values that were saved with the template.</span></span> <span data-ttu-id="06681-157">Ezt követően létrejön a szabadszöveges számla, és szerkesztheti a számla értékeit.</span><span class="sxs-lookup"><span data-stu-id="06681-157">A new free text invoice will be created and you can edit the values in that invoice.</span></span> 


