--- 
title: "Tranzakciók átvitele az Intrastatba"
description: "Ez az eljárás bemutatja, hogy hogyan lehet beállítani az Intrastat paramétereit illetve, hogy hogyan viheti át a tranzakciókat az Intrastatba."
author: Anasyash
manager: AnnBe
ms.date: 06/09/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: a968bf4ec263f3b7c2b4e5b215fe782d4b54dd8e
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="transfer-transactions-to-the-intrastat"></a><span data-ttu-id="4cdb2-103">Tranzakciók átvitele az Intrastatba</span><span class="sxs-lookup"><span data-stu-id="4cdb2-103">Transfer transactions to the Intrastat</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4cdb2-104">Ez az eljárás bemutatja, hogy hogyan lehet beállítani az Intrastat paramétereit illetve, hogy hogyan viheti át a tranzakciókat az Intrastatba.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-104">This procedure walks you through how to set up Intrastat parameters and transfer transactions to Intrastat.</span></span> <span data-ttu-id="4cdb2-105">Ez az eljárás a DEMF bemutatócég segítségével lett létrehozva.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-105">This procedure was created using the demo data company DEMF.</span></span>


## <a name="create-new-and-update-existing-commodity-code"></a><span data-ttu-id="4cdb2-106">Hozzon létre egy új árucikk-kódot és módosítsa a meglévő árucikk-kódot</span><span class="sxs-lookup"><span data-stu-id="4cdb2-106">Create new and update existing commodity code</span></span>
1. <span data-ttu-id="4cdb2-107">Ugorjon a Termékinformációk kezelése > Beállítás > Kategóriák és attribútumok > Kategóriahierarchiák pontra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-107">Go to Product information management > Setup > Categories and attributes > Category hierarchies.</span></span>
2. <span data-ttu-id="4cdb2-108">A listában keresse meg vagy válassza ki a „Intrastat-vámtarifakódok” rekordot.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-108">In the list, find or select the record "Intrastat commodity codes."</span></span>
3. <span data-ttu-id="4cdb2-109">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="4cdb2-110">Válassza ki az „egy rekord” lehetőséget a fastruktúrában.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-110">In the tree, select 'a record'.</span></span>
    * <span data-ttu-id="4cdb2-111">Például válassza ki a „Intrastat\Beszélő” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-111">For example, select 'Intrastat\Speaker'.</span></span>  
5. <span data-ttu-id="4cdb2-112">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-112">Click Edit.</span></span>
6. <span data-ttu-id="4cdb2-113">Bontsa ki a Külkereskedelem szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-113">Expand the Foreign trade section.</span></span>
7. <span data-ttu-id="4cdb2-114">A Kiegészítő egységek mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-114">In the Additional units field, enter or select a value.</span></span>
    * <span data-ttu-id="4cdb2-115">Válassza ki például a „darab” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-115">For example, choose 'pcs'.</span></span>  
8. <span data-ttu-id="4cdb2-116">Válassza az Igen értéket a Súly nem alkalmazható mezőben.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-116">Select Yes in the Weight not applicable field.</span></span>
9. <span data-ttu-id="4cdb2-117">Válassza ki az „Intrastat” lehetőséget a fastruktúrában.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-117">In the tree, select 'Intrastat'.</span></span>
10. <span data-ttu-id="4cdb2-118">Kattintson az Új kategória-csomópont gombra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-118">Click New category node.</span></span>
11. <span data-ttu-id="4cdb2-119">A Név mezőben adja meg az árucikk nevét.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-119">In the Name field, enter the name of commodity.</span></span>
    * <span data-ttu-id="4cdb2-120">Például írja be a „Másik árucikk” szöveget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-120">For example, type 'Other commodity'.</span></span>  
12. <span data-ttu-id="4cdb2-121">A Kód mezpben adja meg az árucikk-kódját.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-121">In the Code field, enter the commodity code.</span></span>
    * <span data-ttu-id="4cdb2-122">Például írja be a „995 00 00” értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-122">For example, type '995 00 00'.</span></span>  
13. <span data-ttu-id="4cdb2-123">Írjon be egy értéket a Barátságos név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-123">In the Friendly name field, type a value.</span></span>
    * <span data-ttu-id="4cdb2-124">Például írja be az „Egyéb” szöveget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-124">For example, type 'Other'.</span></span>  
14. <span data-ttu-id="4cdb2-125">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-125">Click Save.</span></span>
15. <span data-ttu-id="4cdb2-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-126">Close the page.</span></span>

## <a name="assign-commodity-code-to-product-hierarchy-and-released-product"></a><span data-ttu-id="4cdb2-127">Rendelje hozzá az árucikk-kódot a termékhierarchiához és a kiadott termékhez.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-127">Assign commodity code to product hierarchy and released product</span></span>
1. <span data-ttu-id="4cdb2-128">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-128">Use the Quick Filter to find records.</span></span> <span data-ttu-id="4cdb2-129">Végezzen szűrést a Név mezőben az „Értékesítés” értékkel.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-129">For example, filter on the Name field with a value of 'sales'.</span></span>
2. <span data-ttu-id="4cdb2-130">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-130">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="4cdb2-131">Bontsa ki a fastruktúrában a „a kategória-csomópont” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-131">In the tree, expand 'a category node'.</span></span>
    * <span data-ttu-id="4cdb2-132">Például bontsa ki az „Értékesítési hierarchia\Home audio” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-132">For example, expand 'Sales hierarchy\Home audio'.</span></span>  
4. <span data-ttu-id="4cdb2-133">Válassza ki a „A vámtarifakódhoz társítandó kategória” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-133">In the tree, select 'the category to assign to the commodity code'.</span></span>
    * <span data-ttu-id="4cdb2-134">Például válassza ki az „Értékesítési hierarchia\Home audio\Beszélő” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-134">For example, select 'Sales hierarchy\Home audio\Speakers.</span></span>  
5. <span data-ttu-id="4cdb2-135">Bontsa ki az Árucikk-kódok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-135">Expand the Commodity codes section.</span></span>
6. <span data-ttu-id="4cdb2-136">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-136">Click Add.</span></span>
7. <span data-ttu-id="4cdb2-137">A Hierarchia kiválasztás mezőben válassza ki az „Intrastat” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-137">In the Select hierarchy field, select 'Intrastat'.</span></span>
8. <span data-ttu-id="4cdb2-138">Keresse meg és válassza ki az árucikk-kódot a listában</span><span class="sxs-lookup"><span data-stu-id="4cdb2-138">In the list, find and select the commodity code</span></span>
    * <span data-ttu-id="4cdb2-139">Például válassza ki a „920 20 34 Beszélő” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-139">For example, select '920 20 34 Speaker'.</span></span>  
9. <span data-ttu-id="4cdb2-140">Kattintson a SelectCodes lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-140">Click SelectCodes.</span></span>
10. <span data-ttu-id="4cdb2-141">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-141">Click OK.</span></span>
11. <span data-ttu-id="4cdb2-142">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-142">Go to Product information management > Products > Released products.</span></span>
12. <span data-ttu-id="4cdb2-143">Válassza ki a listában azt a kiadott terméket, amelyet az árucikk-kódhoz rendel.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-143">In the list, choose the released product that you will assign to the commodity code.</span></span>
    * <span data-ttu-id="4cdb2-144">Válassza ki például a „D0001” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-144">For example, choose 'D0001'.</span></span>  
13. <span data-ttu-id="4cdb2-145">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-145">Click Edit.</span></span>
14. <span data-ttu-id="4cdb2-146">Bontsa ki a Külkereskedelem szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-146">Expand the Foreign trade section.</span></span>
15. <span data-ttu-id="4cdb2-147">Az Árucikk mezőben adja meg az árucikk-kódját.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-147">In the Commodity field, enter the commodity code</span></span>
    * <span data-ttu-id="4cdb2-148">Válassza ki például a „920 20 34 Beszélő” értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-148">For example, select value '920 20 34 Speaker'.</span></span>    
16. <span data-ttu-id="4cdb2-149">Adjon meg egy számot a Költségszázalék mezőben.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-149">In the Charges percentage field, enter a number.</span></span>
    * <span data-ttu-id="4cdb2-150">Adja meg például a „3” értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-150">For example, enter '3'.</span></span>  
17. <span data-ttu-id="4cdb2-151">Az ország/régió mezőben adjon meg vagy válasszon ki egy származási országot vagy régiót</span><span class="sxs-lookup"><span data-stu-id="4cdb2-151">In the Country/region field, enter or select a country or region of origin</span></span>
    * <span data-ttu-id="4cdb2-152">Válassza ki például az „AUT” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-152">For example, select 'AUT'.</span></span>  
18. <span data-ttu-id="4cdb2-153">Bontsa ki a Készletkezelés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-153">Expand the Manage inventory section.</span></span>
19. <span data-ttu-id="4cdb2-154">Adja meg egy Súly (kg) értéket a Nettó tömeg mezőben.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-154">In the Net weight field, enter a weight in kg.</span></span>
    * <span data-ttu-id="4cdb2-155">Adja meg például a „2,5” értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-155">For example, enter '2.5'.</span></span>  
20. <span data-ttu-id="4cdb2-156">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-156">Click Save.</span></span>

## <a name="set-up-intrastat-transaction-codes-and-foreign-trade-parameters"></a><span data-ttu-id="4cdb2-157">Állítsa be az Intrastat-tranzakciókódokat és a Külkereskedelmi paramétereket</span><span class="sxs-lookup"><span data-stu-id="4cdb2-157">Set up Intrastat transaction codes and foreign trade parameters</span></span>
1. <span data-ttu-id="4cdb2-158">Ugorjon az Adó > Beállítás > Külkereskedelem > Tranzakciókódok pontra</span><span class="sxs-lookup"><span data-stu-id="4cdb2-158">Go to Tax > Setup > Foreign trade > Transaction codes</span></span>
2. <span data-ttu-id="4cdb2-159">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-159">Click New.</span></span>
3. <span data-ttu-id="4cdb2-160">Írjon be egy értéket a Tranzakciókódok mezőben.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-160">In the Transaction code field, type a value.</span></span>
    * <span data-ttu-id="4cdb2-161">Írja be például a „21” értéket a visszatérítésként használt tranzakciókódra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-161">For example, enter '21' for the transaction code used as return.</span></span>  
4. <span data-ttu-id="4cdb2-162">A Név mezőbe írja be a Tranzakciókódok nevét.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-162">In the Name field, type the name of transaction code.</span></span>
    * <span data-ttu-id="4cdb2-163">Adja meg például a „Visszatérés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-163">For example, enter 'Return'.</span></span>  
5. <span data-ttu-id="4cdb2-164">Válasszon ki egy lehetőséget a Statisztikai összeg mezőben.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-164">In the Statistical amount field, select an option.</span></span>
    * <span data-ttu-id="4cdb2-165">Jelölje ki például az „Üres” lehetőséget, amely azt jelzi, hogy a „21”-es tranzakciókódos tranzakcióra vonatkozóan jelentendő Statisztikai értéknek mindig nullának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-165">For example, select 'Empty' which indicates that the Statistical value to be reported for transactions with Transaction code of "21" will always be zero.</span></span>  
6. <span data-ttu-id="4cdb2-166">Ugrás az Adó > Beállítás > Külkereskedelem > Külkereskedelmi paraméterek pontra</span><span class="sxs-lookup"><span data-stu-id="4cdb2-166">Go to Tax > Setup > Foreign trade > Foreign trade parameters</span></span>
7. <span data-ttu-id="4cdb2-167">A Tranzakciókód mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-167">In the Transaction code field, enter or select a value.</span></span>
    * <span data-ttu-id="4cdb2-168">Válassza ki például a „11”-es lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-168">For example, select '11'.</span></span>  
8. <span data-ttu-id="4cdb2-169">A Jóváírás mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-169">In the Credit note field, enter or select a value.</span></span>
    * <span data-ttu-id="4cdb2-170">Ez az érték a fizikai visszárut azonosítja.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-170">This value also identifies the physical return.</span></span> <span data-ttu-id="4cdb2-171">A rendszer a tényleges visszaadásra vonatkozó jóváírást az ellenkező irányba helyezi át az Intrastat naplóban.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-171">The credit note for the physical return will be transferred in the Intrastat journal with opposite direction.</span></span> <span data-ttu-id="4cdb2-172">Például a rendszer az érkezés visszáruzásának átvitelét kiszállításként végzi el.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-172">For example, the return of arrival is transferred as dispatch.</span></span>   <span data-ttu-id="4cdb2-173">Ellenkező esetben a jóváírást helyesbítésnek minősül, és a rendszer ugyanabba az irányba helyezi át, de ellenkező előjellel.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-173">Otherwise, the credit note is considered a correction and is transferred with the same direction and opposite sign.</span></span> <span data-ttu-id="4cdb2-174">Például a rendszer az érkezés helyesbítésének átvitelét negatív összeges érkezésként végzi el és az aktív jelzőt „Helyesbítés” értékre állítja.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-174">For example, the correction of arrival is transferred as an arrival with negative amount and the active flag is set to "Correction".</span></span>  
9. <span data-ttu-id="4cdb2-175">Bontsa ki az Átvitel szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-175">Expand the Transfer section.</span></span>
10. <span data-ttu-id="4cdb2-176">Válassza az Igen lehetőséget a Cikkek árucikk-kóddal mezőben.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-176">Select Yes in the Items with commodity code field.</span></span>
    * <span data-ttu-id="4cdb2-177">Jelölje be ezt a lehetőséget, ha csak az árucikk-kóddal rendelkező tranzakció átvitelét szeretné elvégezni.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-177">Select this option to transfer only the transactions with a commodity code assigned.</span></span> <span data-ttu-id="4cdb2-178">Az árucikk-kód nélküli tranzakciókat nem lehet áthelyezni az Intrastatba.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-178">Transactions without a commodity code won't be transferred to Intrastat.</span></span>  
11. <span data-ttu-id="4cdb2-179">Az Átvitel, ha megfelel a következő feltételnek mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-179">In the Transfer when meeting criterion for field, select an option.</span></span>
    * <span data-ttu-id="4cdb2-180">Válassza ki például az „A kijelöltek egyike” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-180">For example, select 'One of the selected'.</span></span>  
12. <span data-ttu-id="4cdb2-181">Bontsa ki az Árucikk-kódok hierarchiája szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-181">Expand the Commodity code hierarchy section.</span></span>
13. <span data-ttu-id="4cdb2-182">Kattintson az Ország/régió tulajdonságai lapra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-182">Click the Country/region properties tab.</span></span>
14. <span data-ttu-id="4cdb2-183">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-183">Click New.</span></span>
15. <span data-ttu-id="4cdb2-184">Az Ország/régió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-184">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="4cdb2-185">Válassza ki például a „FRA” értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-185">For example, select the value 'FRA'.</span></span>  
16. <span data-ttu-id="4cdb2-186">Az Intrastat kód mezőben adja meg az ország ISO-kódját.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-186">In the Intrastat code field, enter the ISO code for the country.</span></span>
    * <span data-ttu-id="4cdb2-187">Írja be például a „FR” értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-187">For example, type 'FR'.</span></span>  
17. <span data-ttu-id="4cdb2-188">Az Ország/régió típusa mezőben válassza ki az „EU” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-188">In the Country/region type field, select 'EU'.</span></span>
18. <span data-ttu-id="4cdb2-189">Kattintson a Számsorozatok lapra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-189">Click the Number sequences tab.</span></span>

## <a name="set-up-modes-of-delivery-and-rules-for-including-charges-in-intrastat"></a><span data-ttu-id="4cdb2-190">Állítsa be a Szállítási módot és az Intrastat költségek bevételére vonatkozó szabályokat</span><span class="sxs-lookup"><span data-stu-id="4cdb2-190">Set up Modes of delivery and rules for including charges in Intrastat</span></span>
1. <span data-ttu-id="4cdb2-191">Ugorjon az Értékesítés és marketing > Beállítás > Elosztás > Szállítási módok pontra</span><span class="sxs-lookup"><span data-stu-id="4cdb2-191">Go to Sales and marketing > Setup > Distribution > Modes of delivery</span></span>
2. <span data-ttu-id="4cdb2-192">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-192">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4cdb2-193">Válassza ki például a „20 Légi” értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-193">For example, select '20 Air'.</span></span>  
3. <span data-ttu-id="4cdb2-194">Bontsa ki a Külkereskedelem szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-194">Expand the Foreign trade section.</span></span>
4. <span data-ttu-id="4cdb2-195">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-195">Click Edit.</span></span>
5. <span data-ttu-id="4cdb2-196">A Szállítás mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-196">In the Transport field, enter or select a value.</span></span>
    * <span data-ttu-id="4cdb2-197">Válassza ki például a „02” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-197">For example, select '02'.</span></span>  
6. <span data-ttu-id="4cdb2-198">Ugorjon a Kintlévőségek > Költségek beállítása > Költségkód pontra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-198">Go to Accounts receivable > Charges setup > Charges code.</span></span>
7. <span data-ttu-id="4cdb2-199">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-199">Use the Quick Filter to find records.</span></span> <span data-ttu-id="4cdb2-200">Például végezzen szűrést a Költségkód mezőben a „ fuvardíj” értékkel.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-200">For example, filter on the Charges code field with a value of 'freight'.</span></span>
8. <span data-ttu-id="4cdb2-201">Bontsa ki a Külkereskedelem szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-201">Expand the Foreign trade section.</span></span>
9. <span data-ttu-id="4cdb2-202">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-202">Click Edit.</span></span>
10. <span data-ttu-id="4cdb2-203">Válassza az Igen lehetőséget az Intrastat számlaérték mezőben.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-203">Select Yes in the Intrastat invoice value field.</span></span>
    * <span data-ttu-id="4cdb2-204">A rendszer átviszi az összeget a Számlaköltségek mezőbe és a Számla összege mezőbe átvitt összeggel végzi el az összegzést.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-204">The amount will be transferred to the  Invoice charges field and will be summarized with the amount transferred in the Invoice amount field.</span></span>    <span data-ttu-id="4cdb2-205">Jelölje be az Igen értéket az Intrastat statisztikai érték mezőben, ha a módosítások összegét át kell vinni a Statisztikai költségekbe és összegezni kell a Statisztikai összeggel.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-205">Select Yes in the Intrastat statistical value field if the amount of changes need to be transferred to the field Statistical charges and summarized with Statistical amount.</span></span>  

## <a name="sell-products-for-eu-customers"></a><span data-ttu-id="4cdb2-206">Termékek értékesítése az EU vevőkre vonatkozóan</span><span class="sxs-lookup"><span data-stu-id="4cdb2-206">Sell products for EU customers</span></span>
1. <span data-ttu-id="4cdb2-207">Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-207">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="4cdb2-208">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-208">Click New.</span></span>
3. <span data-ttu-id="4cdb2-209">Válasszon ki egy uniós vevőt a Vevői számla mezőben.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-209">In the Customer account field, select an EU customer</span></span>
    * <span data-ttu-id="4cdb2-210">Jelölje be például a „DE-012 Litware Kiskereskedelem” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-210">For example, select "DE-012 Litware Retail".</span></span>  
4. <span data-ttu-id="4cdb2-211">Bontsa ki a Szállítás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-211">Expand the Delivery section.</span></span>
5. <span data-ttu-id="4cdb2-212">A Szállítás módja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-212">In the Mode of delivery field, enter or select a value.</span></span>
    * <span data-ttu-id="4cdb2-213">Válassza ki például a „20 Légi” értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-213">For example, select '20 Air'.</span></span>  
6. <span data-ttu-id="4cdb2-214">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-214">Click OK.</span></span>
7. <span data-ttu-id="4cdb2-215">Vigye a mutatót az értékesítésirendelés-sorok első sorához.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-215">Place the cursor on the first row of sales order lines.</span></span>
8. <span data-ttu-id="4cdb2-216">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-216">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="4cdb2-217">Válassza ki például az „D001” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-217">For example, select 'D001'.</span></span>  
9. <span data-ttu-id="4cdb2-218">Bontsa ki a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-218">Expand the Line details section.</span></span>
10. <span data-ttu-id="4cdb2-219">Kattintson a Külkereskedelem fülre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-219">Click the Foreign trade tab.</span></span>
    * <span data-ttu-id="4cdb2-220">A rendszer automatikusan kitölti az átvitelt a kiválasztott a szállítási mód alapján.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-220">The transport is filled automatically from the chosen Mode of delivery.</span></span>  
11. <span data-ttu-id="4cdb2-221">A Port mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-221">In the Port field, enter or select a value.</span></span>
12. <span data-ttu-id="4cdb2-222">Kattintson a Pénzügyre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-222">Click Financials.</span></span>
    * <span data-ttu-id="4cdb2-223">A beállítások szerint ez az összeg fog szerepelni az Intrastat számlaértékben.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-223">As per the settings, this amount will be included in Intrastat invoice value.</span></span>  
13. <span data-ttu-id="4cdb2-224">Kattintson a Költségek karbantartása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-224">Click Maintain charges.</span></span>
14. <span data-ttu-id="4cdb2-225">A Költségkód mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-225">In the Charges code field, enter or select a value.</span></span>
    * <span data-ttu-id="4cdb2-226">Jelölje ki például a „Fuvardíj” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-226">For example, select 'FREIGHT'.</span></span>  
15. <span data-ttu-id="4cdb2-227">Jelölje be a Megtartás jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-227">Select the Keep check box.</span></span>
16. <span data-ttu-id="4cdb2-228">Adjon meg egy számot az Költségek értéke mezőben.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-228">In the Charges value field, enter a number.</span></span>
    * <span data-ttu-id="4cdb2-229">Adja meg például a „10” értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-229">For example, enter '10'.</span></span>  
17. <span data-ttu-id="4cdb2-230">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-230">Click Save.</span></span>
18. <span data-ttu-id="4cdb2-231">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-231">Close the page.</span></span>
19. <span data-ttu-id="4cdb2-232">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-232">On the Action Pane, click Invoice.</span></span>
20. <span data-ttu-id="4cdb2-233">Kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-233">Click Invoice.</span></span>
21. <span data-ttu-id="4cdb2-234">Bontsa ki a Paraméterek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-234">Expand the Parameters section.</span></span>
22. <span data-ttu-id="4cdb2-235">A Mennyiség mezőben válassza a „Mind” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-235">In the Quantity field, select 'All'.</span></span>
23. <span data-ttu-id="4cdb2-236">Bontsa ki a Beállítások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-236">Expand the Setup section.</span></span>
24. <span data-ttu-id="4cdb2-237">A Számla dátuma mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-237">In the Invoice date field, enter a date.</span></span>
    * <span data-ttu-id="4cdb2-238">Adja meg például a „2015.01.31.” dátumot.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-238">For example, enter '2015-01-31'.</span></span>  
25. <span data-ttu-id="4cdb2-239">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-239">Click OK.</span></span>
26. <span data-ttu-id="4cdb2-240">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-240">Click OK.</span></span>
27. <span data-ttu-id="4cdb2-241">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-241">Close the page.</span></span>
28. <span data-ttu-id="4cdb2-242">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-242">Click New.</span></span>
29. <span data-ttu-id="4cdb2-243">Válasszon ki egy uniós vevőt a Vevői számla mezőben.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-243">In the Customer account field, select an EU customer.</span></span>
    * <span data-ttu-id="4cdb2-244">Válassza ki például a „DE-013 Trey Wholesales” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-244">For example, select 'DE-013 Trey Wholesales'</span></span>  
30. <span data-ttu-id="4cdb2-245">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-245">Click OK.</span></span>
31. <span data-ttu-id="4cdb2-246">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-246">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="4cdb2-247">Válassza ki például az „D0001” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-247">For example, select 'D0001'.</span></span>  
32. <span data-ttu-id="4cdb2-248">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-248">Click Save.</span></span>
33. <span data-ttu-id="4cdb2-249">Kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-249">Click Invoice.</span></span>
34. <span data-ttu-id="4cdb2-250">A Számla dátuma mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-250">In the Invoice date field, enter a date.</span></span>
    * <span data-ttu-id="4cdb2-251">Adja meg például a „2015.01.31.” dátumot.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-251">For example, enter the date '2015-01-31'.</span></span>  
35. <span data-ttu-id="4cdb2-252">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-252">Click OK.</span></span>
36. <span data-ttu-id="4cdb2-253">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-253">Click OK.</span></span>

## <a name="transfer-transactions-to-the-intrastat"></a><span data-ttu-id="4cdb2-254">Tranzakciók átvitele az Intrastatba</span><span class="sxs-lookup"><span data-stu-id="4cdb2-254">Transfer transactions to the Intrastat</span></span>
1. <span data-ttu-id="4cdb2-255">Ugorjon az Adó > Nyilatkozatok > Külkereskedelem > Intrastat pontra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-255">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
2. <span data-ttu-id="4cdb2-256">Kattintson az Áthelyezés elemre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-256">Click Transfer.</span></span>
3. <span data-ttu-id="4cdb2-257">Válassza az Igen lehetőséget a Vevői számla mezőben.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-257">Select Yes in the Customer invoice field.</span></span>
4. <span data-ttu-id="4cdb2-258">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-258">Click Filter.</span></span>
5. <span data-ttu-id="4cdb2-259">Jelölje meg a Dátummal ellátott sort a listában</span><span class="sxs-lookup"><span data-stu-id="4cdb2-259">In the list, mark the row with Date</span></span>
6. <span data-ttu-id="4cdb2-260">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-260">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="4cdb2-261">Adja meg például a szűrést a 2015 januári időszakra vonatkozóan (a pontos érték a dátumformátumtól függ): 2015.01.01. .. 2015.01.31.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-261">For example, enter the filter for the period January 2015 (the exact value depends on your date format): 1/1/2015..1/31/2015</span></span>  
7. <span data-ttu-id="4cdb2-262">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-262">Click OK.</span></span>
8. <span data-ttu-id="4cdb2-263">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-263">Click OK.</span></span>
9. <span data-ttu-id="4cdb2-264">Keresse meg és válassza ki az átvitt rekordot a listában.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-264">In the list, find and selected the transferred record.</span></span>
10. <span data-ttu-id="4cdb2-265">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-265">Click the General tab.</span></span>
    * <span data-ttu-id="4cdb2-266">Tekintse át az átvitt adatokat, többek között a cél/feladás országát/régióját, a származási országot, a súlyt, a mennyiséget, a kiegészítő egységek mennyiségét, az árucikket, a tranzakciókódot, a számlaösszeget és a statisztikai összegeket.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-266">Review transferred data, including country\region of destination/dispatch, country of origin, weight, quantity, quantity in additional units, commodity, transaction code, invoice amounts and statistical amounts.</span></span>   <span data-ttu-id="4cdb2-267">Szükség esetén módosíthatja az adatot.</span><span class="sxs-lookup"><span data-stu-id="4cdb2-267">You can modify data if necessary.</span></span>  


