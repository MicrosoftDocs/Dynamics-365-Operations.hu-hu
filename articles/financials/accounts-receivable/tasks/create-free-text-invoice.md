--- 
title: "Szabadszöveges számla létrehozása"
description: "Ez a feladat-útmutató a szabadszöveges számla létrehozását mutatja be."
author: mikefalkner
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 33324a9b95026600bcc6facb9c22a04fd2e323c8
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-free-text-invoice"></a><span data-ttu-id="08d61-103">Szabadszöveges számla létrehozása</span><span class="sxs-lookup"><span data-stu-id="08d61-103">Create a free text invoice</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="08d61-104">Ez a feladat-útmutató a szabadszöveges számla létrehozását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="08d61-104">This task guide demonstrates creating a free text invoice.</span></span> <span data-ttu-id="08d61-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="08d61-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="08d61-106">Ugorjon a Kinnlévőségek > Számlák > Kizárólag szabadszöveges számlák pontra.</span><span class="sxs-lookup"><span data-stu-id="08d61-106">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="08d61-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="08d61-107">Click New.</span></span>
3. <span data-ttu-id="08d61-108">Válasszon egy értéket a Vevői számla mezőnek.</span><span class="sxs-lookup"><span data-stu-id="08d61-108">In the Customer account field, select a value.</span></span>
    * <span data-ttu-id="08d61-109">A számla alapértelmezett esetben a vevői számlához használt példány.</span><span class="sxs-lookup"><span data-stu-id="08d61-109">The invoice account will default to the same account used for the customer account.</span></span>   
    * <span data-ttu-id="08d61-110">A könyvelési állapot Folyamatban állapottal kezdődik, ha a számla nincs feladva.</span><span class="sxs-lookup"><span data-stu-id="08d61-110">The accounting status starts with In process if the invoice is not posted.</span></span>   
    * <span data-ttu-id="08d61-111">A számlaszám a számla feladásakor kerül hozzárendelésre.</span><span class="sxs-lookup"><span data-stu-id="08d61-111">The invoice number will be assigned when the invoice is posted.</span></span>  
    * <span data-ttu-id="08d61-112">SEPA típusú felhatalmazások használatakor a beszedési megbízási felhatalmazást automatikusan kitölti a program egy felhatalmazással, ha a vevői számla lehetőséget választja.</span><span class="sxs-lookup"><span data-stu-id="08d61-112">If you are using SEPA mandates, the direct debit mandate will be automatically populated with a mandate when you select the customer account.</span></span>  
4. <span data-ttu-id="08d61-113">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="08d61-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="08d61-114">A Fő számla mezőben adja meg a számlaszámot és a dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="08d61-114">In the Main account field, specify an account number without dimensions.</span></span>
    * <span data-ttu-id="08d61-115">Megadhat továbbá egy vagy több karaktert a fő számlából, és használhatja a keresés funkciót a számlája megtalálásához.</span><span class="sxs-lookup"><span data-stu-id="08d61-115">You can also enter one or more characters for the main account and use the lookup to find your account.</span></span> <span data-ttu-id="08d61-116">Ebben az útmutatóban később kell megadni a dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="08d61-116">You will enter dimensions later on in this guide.</span></span>  
6. <span data-ttu-id="08d61-117">Bontsa ki a Soradatok gyorslapját, hogy hozzáadhasson dimenziókat a fő számlájához.</span><span class="sxs-lookup"><span data-stu-id="08d61-117">Expand the Line details fasttab so you can add dimensions to your main account.</span></span>
7. <span data-ttu-id="08d61-118">Kattintson a Pénzügyi dimenziók lapra.</span><span class="sxs-lookup"><span data-stu-id="08d61-118">Click the Financial dimensions line tab.</span></span>
    * <span data-ttu-id="08d61-119">A dimenziók kizárólag a kijelölt sorra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="08d61-119">The dimensions are for the selected line only.</span></span>    
    * <span data-ttu-id="08d61-120">Az áfacsoportot a vevő tölti ki.</span><span class="sxs-lookup"><span data-stu-id="08d61-120">The sales tax group is populated from the customer.</span></span> <span data-ttu-id="08d61-121">Ha a vevő nem rendelkezik áfacsoporttal, akkor a fő számla áfacsoportját kell használni.</span><span class="sxs-lookup"><span data-stu-id="08d61-121">If the customer does not have a sales tax group, the sales tax group from the main account is used.</span></span>  
    * <span data-ttu-id="08d61-122">A cikkek áfacsoportja a fő számla alapján kerül kitöltésre.</span><span class="sxs-lookup"><span data-stu-id="08d61-122">The items sales tax group is populated from the main account.</span></span> <span data-ttu-id="08d61-123">Ha a fő számla nem rendelkezik cikkekre vonatkozó áfacsoporttal, akkor a Főkönyv áfa paramétereiben található cikk áfacsoport használatos.</span><span class="sxs-lookup"><span data-stu-id="08d61-123">If the main account does not have a item sales tax group, then the item sales tax group in the General ledger sales tax parameters is used.</span></span>    
8. <span data-ttu-id="08d61-124">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="08d61-124">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="08d61-125">A mennyiség megadása nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="08d61-125">The quantity is optional.</span></span>  
9. <span data-ttu-id="08d61-126">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="08d61-126">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="08d61-127">Az egységár megadása nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="08d61-127">The unit price is optional.</span></span>  
    * <span data-ttu-id="08d61-128">Az összeg a mennyiség és az egységár szorzata alapján kerül kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="08d61-128">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="08d61-129">Ugyanakkor felülírhatja a számítást, és bevihet egy összeget.</span><span class="sxs-lookup"><span data-stu-id="08d61-129">However, you can override that calculation and enter an amount.</span></span>  
10. <span data-ttu-id="08d61-130">Kattintson az Áfa lehetőségre a számla számított áfájának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="08d61-130">Click on Sales tax to view the sales tax calculated for your invoice.</span></span>
    * <span data-ttu-id="08d61-131">Ezen a lapon megtekintheti az áfaösszegeket, vagy felülírhatja ezeket az összegeket a Kiigazítás lapon.</span><span class="sxs-lookup"><span data-stu-id="08d61-131">View the sales tax amounts in this page or you can override the amounts on the Adjustment tab.</span></span>  
11. <span data-ttu-id="08d61-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="08d61-132">Click OK.</span></span>
12. <span data-ttu-id="08d61-133">Kattintson a Költségek lehetőségre, ha szeretne költségeket adni a számlához.</span><span class="sxs-lookup"><span data-stu-id="08d61-133">Click Charges to add a charge to your invoice.</span></span> 
13. <span data-ttu-id="08d61-134">Érték beírása a Költségek mezőbe.</span><span class="sxs-lookup"><span data-stu-id="08d61-134">In the Charges code field, type a value.</span></span>
14. <span data-ttu-id="08d61-135">Adjon meg egy számot az Költségek értéke mezőben.</span><span class="sxs-lookup"><span data-stu-id="08d61-135">In the Charges value field, enter a number.</span></span>
15. <span data-ttu-id="08d61-136">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="08d61-136">Close the page.</span></span>
16. <span data-ttu-id="08d61-137">Kattintson az Összeg lehetőségre az összesítő számla részleteinek és végösszegének áttekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="08d61-137">Click Totals to view the summary invoice details and totals.</span></span>
17. <span data-ttu-id="08d61-138">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="08d61-138">Click Close.</span></span>
18. <span data-ttu-id="08d61-139">Adja fel a számlát a Feladás gombra kattintva.</span><span class="sxs-lookup"><span data-stu-id="08d61-139">Click Post to post the invoice.</span></span> <span data-ttu-id="08d61-140">Érvénytelenítheti feladás előtt.</span><span class="sxs-lookup"><span data-stu-id="08d61-140">You will be able to cancel before you post.</span></span>
    * <span data-ttu-id="08d61-141">A számla nyomtatásának időpontját megváltoztathatja: Válassza ki a Jelenlegi lehetőséget az egyes számlák kinyomtatásához, vagy válassza ki az Után lehetőséget, ekkor az összes számla frissítése után történik a nyomtatás.</span><span class="sxs-lookup"><span data-stu-id="08d61-141">To change the timing of your invoice printing:  Select Current to print each invoice as it is updated   or  Select After to print after all invoices have been updated.</span></span>  
    * <span data-ttu-id="08d61-142">Ha szeretné megváltoztatni a vevő hitelkeretének ellenőrzését feladás előtt, akkor változtassa meg a Hitelkeret típusát.</span><span class="sxs-lookup"><span data-stu-id="08d61-142">If you want to change how the customer's credit limit is checked before posting, change the Credit limit type.</span></span>  
    * <span data-ttu-id="08d61-143">Ha nyomtatni akarja a számlát akkor válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="08d61-143">If you want to print the invoice, select Yes.</span></span>  
    * <span data-ttu-id="08d61-144">Ha biztosan feladja a számlát akkor válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="08d61-144">If you want to post the invoice, select Yes.</span></span> <span data-ttu-id="08d61-145">Feladás nélkül is kinyomtathatja a számlát.</span><span class="sxs-lookup"><span data-stu-id="08d61-145">You can print the invoice without posting.</span></span>  
19. <span data-ttu-id="08d61-146">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="08d61-146">Click OK.</span></span>

