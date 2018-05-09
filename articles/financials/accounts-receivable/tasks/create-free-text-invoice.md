--- 
title: "Szabadszöveges számla létrehozása"
description: "Ez a feladat-útmutató a szabadszöveges számla létrehozását mutatja be."
author: mikefalkner
manager: AnnBe
ms.date: 10/26/2017
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 16fd3c6459389d20c59047d37ec8ca40424c62d2
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-free-text-invoice"></a><span data-ttu-id="5368e-103">Szabadszöveges számla létrehozása</span><span class="sxs-lookup"><span data-stu-id="5368e-103">Create a free text invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5368e-104">Ez a feladat-útmutató a szabadszöveges számla létrehozását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="5368e-104">This task guide demonstrates creating a free text invoice.</span></span> <span data-ttu-id="5368e-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="5368e-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="5368e-106">Ugorjon a Kinnlévőségek > Számlák > Kizárólag szabadszöveges számlák pontra.</span><span class="sxs-lookup"><span data-stu-id="5368e-106">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="5368e-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5368e-107">Click New.</span></span>
3. <span data-ttu-id="5368e-108">Válasszon egy értéket a Vevői számla mezőnek.</span><span class="sxs-lookup"><span data-stu-id="5368e-108">In the Customer account field, select a value.</span></span>
    * <span data-ttu-id="5368e-109">A számla alapértelmezett esetben a vevői számlához használt példány.</span><span class="sxs-lookup"><span data-stu-id="5368e-109">The invoice account will default to the same account used for the customer account.</span></span>   
    * <span data-ttu-id="5368e-110">A könyvelési állapot Folyamatban állapottal kezdődik, ha a számla nincs feladva.</span><span class="sxs-lookup"><span data-stu-id="5368e-110">The accounting status starts with In process if the invoice is not posted.</span></span>   
    * <span data-ttu-id="5368e-111">A számlaszám a számla feladásakor kerül hozzárendelésre.</span><span class="sxs-lookup"><span data-stu-id="5368e-111">The invoice number will be assigned when the invoice is posted.</span></span>  
    * <span data-ttu-id="5368e-112">SEPA típusú felhatalmazások használatakor a beszedési megbízási felhatalmazást automatikusan kitölti a program egy felhatalmazással, ha a vevői számla lehetőséget választja.</span><span class="sxs-lookup"><span data-stu-id="5368e-112">If you are using SEPA mandates, the direct debit mandate will be automatically populated with a mandate when you select the customer account.</span></span>  
4. <span data-ttu-id="5368e-113">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5368e-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5368e-114">A Fő számla mezőben adja meg a számlaszámot és a dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="5368e-114">In the Main account field, specify an account number without dimensions.</span></span>
    * <span data-ttu-id="5368e-115">Megadhat továbbá egy vagy több karaktert a fő számlából, és használhatja a keresés funkciót a számlája megtalálásához.</span><span class="sxs-lookup"><span data-stu-id="5368e-115">You can also enter one or more characters for the main account and use the lookup to find your account.</span></span> <span data-ttu-id="5368e-116">Ebben az útmutatóban később kell megadni a dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="5368e-116">You will enter dimensions later on in this guide.</span></span>  
6. <span data-ttu-id="5368e-117">Bontsa ki a Soradatok gyorslapját, hogy hozzáadhasson dimenziókat a fő számlájához.</span><span class="sxs-lookup"><span data-stu-id="5368e-117">Expand the Line details fasttab so you can add dimensions to your main account.</span></span>
7. <span data-ttu-id="5368e-118">Kattintson a Pénzügyi dimenziók lapra.</span><span class="sxs-lookup"><span data-stu-id="5368e-118">Click the Financial dimensions line tab.</span></span>
    * <span data-ttu-id="5368e-119">A dimenziók kizárólag a kijelölt sorra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="5368e-119">The dimensions are for the selected line only.</span></span>    
    * <span data-ttu-id="5368e-120">Az áfacsoportot a vevő tölti ki.</span><span class="sxs-lookup"><span data-stu-id="5368e-120">The sales tax group is populated from the customer.</span></span> <span data-ttu-id="5368e-121">Ha a vevő nem rendelkezik áfacsoporttal, akkor a fő számla áfacsoportját kell használni.</span><span class="sxs-lookup"><span data-stu-id="5368e-121">If the customer does not have a sales tax group, the sales tax group from the main account is used.</span></span>  
    * <span data-ttu-id="5368e-122">A cikkek áfacsoportja a fő számla alapján kerül kitöltésre.</span><span class="sxs-lookup"><span data-stu-id="5368e-122">The items sales tax group is populated from the main account.</span></span> <span data-ttu-id="5368e-123">Ha a fő számla nem rendelkezik cikkekre vonatkozó áfacsoporttal, akkor a Főkönyv áfa paramétereiben található cikk áfacsoport használatos.</span><span class="sxs-lookup"><span data-stu-id="5368e-123">If the main account does not have an item sales tax group, then the item sales tax group in the General ledger sales tax parameters is used.</span></span>    
8. <span data-ttu-id="5368e-124">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="5368e-124">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="5368e-125">A mennyiség megadása nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="5368e-125">The quantity is optional.</span></span>  
9. <span data-ttu-id="5368e-126">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="5368e-126">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="5368e-127">Az egységár megadása nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="5368e-127">The unit price is optional.</span></span>  
    * <span data-ttu-id="5368e-128">Az összeg a mennyiség és az egységár szorzata alapján kerül kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="5368e-128">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="5368e-129">Ugyanakkor felülírhatja a számítást, és bevihet egy összeget.</span><span class="sxs-lookup"><span data-stu-id="5368e-129">However, you can override that calculation and enter an amount.</span></span>  
10. <span data-ttu-id="5368e-130">Kattintson az Áfa lehetőségre a számla számított áfájának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="5368e-130">Click on Sales tax to view the sales tax calculated for your invoice.</span></span>
    * <span data-ttu-id="5368e-131">Ezen a lapon megtekintheti az áfaösszegeket, vagy felülírhatja ezeket az összegeket a Kiigazítás lapon.</span><span class="sxs-lookup"><span data-stu-id="5368e-131">View the sales tax amounts in this page or you can override the amounts on the Adjustment tab.</span></span>  
11. <span data-ttu-id="5368e-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5368e-132">Click OK.</span></span>
12. <span data-ttu-id="5368e-133">Kattintson a Költségek lehetőségre, ha szeretne költségeket adni a számlához.</span><span class="sxs-lookup"><span data-stu-id="5368e-133">Click Charges to add a charge to your invoice.</span></span> 
13. <span data-ttu-id="5368e-134">Érték beírása a Költségek mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5368e-134">In the Charges code field, type a value.</span></span>
14. <span data-ttu-id="5368e-135">Adjon meg egy számot az Költségek értéke mezőben.</span><span class="sxs-lookup"><span data-stu-id="5368e-135">In the Charges value field, enter a number.</span></span>
15. <span data-ttu-id="5368e-136">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5368e-136">Close the page.</span></span>
16. <span data-ttu-id="5368e-137">Kattintson az Összeg lehetőségre az összesítő számla részleteinek és végösszegének áttekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="5368e-137">Click Totals to view the summary invoice details and totals.</span></span>
17. <span data-ttu-id="5368e-138">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="5368e-138">Click Close.</span></span>
18. <span data-ttu-id="5368e-139">Adja fel a számlát a Feladás gombra kattintva.</span><span class="sxs-lookup"><span data-stu-id="5368e-139">Click Post to post the invoice.</span></span> <span data-ttu-id="5368e-140">Érvénytelenítheti feladás előtt.</span><span class="sxs-lookup"><span data-stu-id="5368e-140">You will be able to cancel before you post.</span></span>
    * <span data-ttu-id="5368e-141">A számla nyomtatásának időpontját megváltoztathatja: Válassza ki a Jelenlegi lehetőséget az egyes számlák kinyomtatásához, vagy válassza ki az Után lehetőséget, ekkor az összes számla frissítése után történik a nyomtatás.</span><span class="sxs-lookup"><span data-stu-id="5368e-141">To change the timing of your invoice printing:  Select Current to print each invoice as it is updated   or  Select After to print after all invoices have been updated.</span></span>  
    * <span data-ttu-id="5368e-142">Ha szeretné megváltoztatni a vevő hitelkeretének ellenőrzését feladás előtt, akkor változtassa meg a Hitelkeret típusát.</span><span class="sxs-lookup"><span data-stu-id="5368e-142">If you want to change how the customer's credit limit is checked before posting, change the Credit limit type.</span></span>  
    * <span data-ttu-id="5368e-143">Ha nyomtatni akarja a számlát akkor válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5368e-143">If you want to print the invoice, select Yes.</span></span>  
    * <span data-ttu-id="5368e-144">Ha biztosan feladja a számlát akkor válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5368e-144">If you want to post the invoice, select Yes.</span></span> <span data-ttu-id="5368e-145">Feladás nélkül is kinyomtathatja a számlát.</span><span class="sxs-lookup"><span data-stu-id="5368e-145">You can print the invoice without posting.</span></span>  
19. <span data-ttu-id="5368e-146">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5368e-146">Click OK.</span></span>


