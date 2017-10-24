---
title: "Menedzsment feltételeinek beállítása"
description: "Engedélyezze a szabálytalanság kezelési folyamatokat ezen eljárások segítségével"
author: perlynne
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 842a9441158defca74d1b203a1b2509773ba8919
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-prerequisites-for-management"></a><span data-ttu-id="d4802-103">Menedzsment feltételeinek beállítása</span><span class="sxs-lookup"><span data-stu-id="d4802-103">Set up prerequisites for management</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d4802-104">Engedélyezze a szabálytalanság kezelési folyamatokat ezen eljárások segítségével</span><span class="sxs-lookup"><span data-stu-id="d4802-104">Use this procedure to enable nonconformance management processes.</span></span> <span data-ttu-id="d4802-105">A szabálytalanság ismerteti azt az elemet vagy eljárást, amely minőségi problémával rendelkezik, ahol a leíró jellegű információ a forrást és a probléma típusát tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="d4802-105">A nonconformance describes a procedure or item that has a quality problem, where the descriptive information includes the source and type of problem.</span></span> <span data-ttu-id="d4802-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="d4802-106">This procedure uses the USMF demo data company.</span></span> <span data-ttu-id="d4802-107">Ezt az eljárást általában a minőségbiztosítási vezető végzi el.</span><span class="sxs-lookup"><span data-stu-id="d4802-107">This procedure is typically performed by a quality manager.</span></span>


## <a name="enable-quality-management-processes-within-the-company"></a><span data-ttu-id="d4802-108">Engedélyezze a Minőségkezelési folyamatokat a vállalaton belül</span><span class="sxs-lookup"><span data-stu-id="d4802-108">Enable quality management processes within the company</span></span>
1. <span data-ttu-id="d4802-109">Ugrás a Készletkezelés > Beállítás > Készlet- és raktárkezelési paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d4802-109">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="d4802-110">Kattintson a Minőségkezelés lapra.</span><span class="sxs-lookup"><span data-stu-id="d4802-110">Click the Quality management tab.</span></span>
3. <span data-ttu-id="d4802-111">Válassza az Igen lehetőséget a Minőségkezelés használata mezőben.</span><span class="sxs-lookup"><span data-stu-id="d4802-111">Select Yes in the Use quality management field.</span></span>
    * <span data-ttu-id="d4802-112">Válassza ki ezt a paramétert a vállalat minőségirányítási folyamatainak engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="d4802-112">Select this parameter to enable quality management processes for the company.</span></span>  
4. <span data-ttu-id="d4802-113">Adjon meg egy számot az Órabér mezőben.</span><span class="sxs-lookup"><span data-stu-id="d4802-113">In the Hourly rate field, enter a number.</span></span>
    * <span data-ttu-id="d4802-114">Az Órabér mező segítségével adja meg az óradíjat a helyi pénznemben.</span><span class="sxs-lookup"><span data-stu-id="d4802-114">Use the Hourly rate field to enter an hourly labor rate in the local currency.</span></span> <span data-ttu-id="d4802-115">A rendszer az óradíjjal számítja ki a szabálytalansággal kapcsolatos műveletek költségeit.</span><span class="sxs-lookup"><span data-stu-id="d4802-115">The hourly rate is used for calculating costs for operations that are related to a nonconformance.</span></span> <span data-ttu-id="d4802-116">Az óradíj és a számított költségek csak a szabálytalanságokra vonatkoznak, más funkciókat nem érintenek.</span><span class="sxs-lookup"><span data-stu-id="d4802-116">The hourly rate and calculated costs provide reference information for a nonconformance, and they do not interact with other functionality.</span></span>  
5. <span data-ttu-id="d4802-117">Kattintson a Jelentés-beállítás elemre.</span><span class="sxs-lookup"><span data-stu-id="d4802-117">Click Report setup.</span></span>
    * <span data-ttu-id="d4802-118">Ez az oldal lehetővé teszi a különféle minőségirányítási jelentésekhez használandó minőségi-jelentés megjegyzéstípusainak meghatározását.</span><span class="sxs-lookup"><span data-stu-id="d4802-118">This page allows you define the quality report note types that will be used on different kinds of quality management reports.</span></span>  
6. <span data-ttu-id="d4802-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d4802-119">Close the page.</span></span>
7. <span data-ttu-id="d4802-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d4802-120">Close the page.</span></span>

## <a name="enable-user-for-nonconformance-processing"></a><span data-ttu-id="d4802-121">Engedélyezze a szabálytalanságok feldolgozására a felhasználót</span><span class="sxs-lookup"><span data-stu-id="d4802-121">Enable user for nonconformance processing</span></span>
1. <span data-ttu-id="d4802-122">Ugrás a Rendszerfelügyelet > Felhasználók > Felhasználók elemre.</span><span class="sxs-lookup"><span data-stu-id="d4802-122">Go to System administration > Users > Users.</span></span>
    * <span data-ttu-id="d4802-123">A szabálytalanság jóváhagyásának feldolgozásához azon felhasználónak, aki jóváhagyja vagy elutasítja a szabálytalanságokat a Felhasználók lapon hozzárendelt „Név” értékkel kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="d4802-123">To process the approval of a nonconformance the user who  approves or rejects nonconformances must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="d4802-124">A dokumentummegjegyzések használatához a felhasználónak rendelkeznie kell a Dokumentumkezeléssel, amelyet a felhasználói beállításokban kell aktiválni.</span><span class="sxs-lookup"><span data-stu-id="d4802-124">To use the document notes, the user must also have Document handling activated in the user options.</span></span>  
2. <span data-ttu-id="d4802-125">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="d4802-125">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d4802-126">Végezzen szűrést a Név mezőben például a „Ricardo” értékkel.</span><span class="sxs-lookup"><span data-stu-id="d4802-126">For example, filter on the Name field with a value of 'Ricardo'.</span></span>
    * <span data-ttu-id="d4802-127">A szűrő használatával keresse meg azt a felhasználót, aki jóváhagyja vagy elutasítja a Szabálytalanságrekordokat.</span><span class="sxs-lookup"><span data-stu-id="d4802-127">Use the filter to find the user who will be approving or rejecting the nonconformance records.</span></span>  
3. <span data-ttu-id="d4802-128">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d4802-128">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d4802-129">A szabálytalanság jóváhagyásának feldolgozásához győződjön meg arról, hogy a felhasználó, aki jóváhagyja vagy elutasítja a szabálytalanságokat rendelkezik a Felhasználók lapon hozzárendelt „Név” értékkel.</span><span class="sxs-lookup"><span data-stu-id="d4802-129">To process the approval of a nonconformance, make sure the user who approves or rejects nonconformances has a “Name” value assigned on the Users page.</span></span>  
4. <span data-ttu-id="d4802-130">Kattintson a Felhasználói beállítások lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d4802-130">Click User options.</span></span>
5. <span data-ttu-id="d4802-131">Kattintson a Beállítások fülre.</span><span class="sxs-lookup"><span data-stu-id="d4802-131">Click the Preferences tab.</span></span>
6. <span data-ttu-id="d4802-132">Válassza az Igen lehetőséget a Dokumentumkezelés engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="d4802-132">Select Yes in the Enable document handling field.</span></span>
    * <span data-ttu-id="d4802-133">A dokumentummegjegyzések használatához a felhasználónak rendelkeznie kell a Dokumentumkezeléssel, amelyet a felhasználói beállításokban kell aktiválni.</span><span class="sxs-lookup"><span data-stu-id="d4802-133">To use the document notes, the user must also have Document handling activated in the user options.</span></span>  
7. <span data-ttu-id="d4802-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d4802-134">Close the page.</span></span>
8. <span data-ttu-id="d4802-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d4802-135">Close the page.</span></span>
9. <span data-ttu-id="d4802-136">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d4802-136">Close the page.</span></span>

## <a name="define-diagnostic-types-for-nonconformance-processing"></a><span data-ttu-id="d4802-137">Határozza meg a diagnosztikai típusokat a szabálytalanság feldolgozásához</span><span class="sxs-lookup"><span data-stu-id="d4802-137">Define diagnostic types for nonconformance processing</span></span>
1. <span data-ttu-id="d4802-138">Ugorjon a Készletgazdálkodás > Beállítás > Minőségkezelés > Diagnosztikai típusok pontra.</span><span class="sxs-lookup"><span data-stu-id="d4802-138">Go to Inventory management > Setup > Quality management > Diagnostic types.</span></span>
    * <span data-ttu-id="d4802-139">A Diagnosztikai típusok oldalon határozhatja meg a diagnosztikai műveletek osztályozását.</span><span class="sxs-lookup"><span data-stu-id="d4802-139">Use the Diagnostic types page to define a classification of diagnostic actions.</span></span> <span data-ttu-id="d4802-140">A javítás meghatározza, hogy milyen típusú diagnosztikai műveletet kell végrehajtani a jóváhagyott szabálytalanságon, valamint hogy kinek kell elvégeznie, melyik napra kérték és mikorra tervezik a végrehajtást.</span><span class="sxs-lookup"><span data-stu-id="d4802-140">A correction identifies what type of diagnostic action should be taken on an approved nonconformance, who should perform it, and the requested and planned completion date.</span></span>  
2. <span data-ttu-id="d4802-141">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d4802-141">Click New.</span></span>
3. <span data-ttu-id="d4802-142">Írjon be egy értéket a Diagnosztika mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d4802-142">In the Diagnostic field, type a value.</span></span>
4. <span data-ttu-id="d4802-143">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d4802-143">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d4802-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d4802-144">Close the page.</span></span>

## <a name="define-quality-charges-for-nonconformance-processing"></a><span data-ttu-id="d4802-145">Határozza meg a minőségbiztosítási költségeket a szabálytalanság feldolgozásához</span><span class="sxs-lookup"><span data-stu-id="d4802-145">Define quality charges for nonconformance processing</span></span>
1. <span data-ttu-id="d4802-146">Ugorjon a Készletkezelés > Beállítás > Minőségkezelés > Minőségbiztosítási költségek pontra.</span><span class="sxs-lookup"><span data-stu-id="d4802-146">Go to Inventory management > Setup > Quality management > Quality charges.</span></span>
    * <span data-ttu-id="d4802-147">A Minőségbiztosítási költségek lap használatával osztályozza azokat a költségeket, amelyeket a szabálytalanságokhoz kapcsolódó műveletekben használ.</span><span class="sxs-lookup"><span data-stu-id="d4802-147">Use the Quality charges page to define a classification of charges that will used in operations related to nonconformances.</span></span>  
2. <span data-ttu-id="d4802-148">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d4802-148">Click New.</span></span>
3. <span data-ttu-id="d4802-149">Érték beírása a Költségek mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d4802-149">In the Charges code field, type a value.</span></span>
4. <span data-ttu-id="d4802-150">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d4802-150">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d4802-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d4802-151">Close the page.</span></span>

## <a name="define-the-operations-for-nonconformance-processing"></a><span data-ttu-id="d4802-152">Határozza meg a műveleteket a szabálytalanság feldolgozásához</span><span class="sxs-lookup"><span data-stu-id="d4802-152">Define the operations for nonconformance processing</span></span>
1. <span data-ttu-id="d4802-153">Ugorjon a Készletgazdálkodás > Beállítás > Minőségkezelés > Műveletek pontra.</span><span class="sxs-lookup"><span data-stu-id="d4802-153">Go to Inventory management > Setup > Quality management > Operations.</span></span>
    * <span data-ttu-id="d4802-154">A Műveletek lap használatával osztályozza a munkát, amelyet a jóváhagyott szabálytalanságokra vonatkozóan végezhet el.</span><span class="sxs-lookup"><span data-stu-id="d4802-154">Use the Operations page to define a classification of the work that may be performed for an approved nonconformance.</span></span> <span data-ttu-id="d4802-155">Amikor a szabálytalansághoz egy műveletet rendel, információkat adhat meg a kapcsolódó anyagról, a munkaidőről és a vegyes költségekről, amelyek a művelet végrehajtásához szükségesek.</span><span class="sxs-lookup"><span data-stu-id="d4802-155">When you relate an operation to a nonconformance, you can define information about the associated material, labor hours, and miscellaneous charges that are required to perform the operation.</span></span> <span data-ttu-id="d4802-156">Ezek az adatok képezik az alapot a művelet becsült végrehajtási költségének kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="d4802-156">This information provides the basis for calculating an estimated cost for performing the operation.</span></span>  
2. <span data-ttu-id="d4802-157">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d4802-157">Click New.</span></span>
3. <span data-ttu-id="d4802-158">Írjon be egy értéket a Műveletek mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d4802-158">In the Operation field, type a value.</span></span>
4. <span data-ttu-id="d4802-159">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d4802-159">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d4802-160">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d4802-160">Close the page.</span></span>

## <a name="define-problem-types-for-nonconformance-processing"></a><span data-ttu-id="d4802-161">Határozza meg a problématípusát a szabálytalanság feldolgozásához</span><span class="sxs-lookup"><span data-stu-id="d4802-161">Define problem types for nonconformance processing</span></span>
1. <span data-ttu-id="d4802-162">Ugorjon a Készletgazdálkodás > Beállítás > Minőségkezelés > Problématípusok pontra.</span><span class="sxs-lookup"><span data-stu-id="d4802-162">Go to Inventory management > Setup > Quality management > Problem types.</span></span>
    * <span data-ttu-id="d4802-163">A Problématípusok oldalon határozhatja meg a különböző szabálytalanságtípusok esetében felmerülő minőségproblémák osztályozását.</span><span class="sxs-lookup"><span data-stu-id="d4802-163">Use the Problem types page to define a classification of quality problems that are encountered in the various nonconformance types.</span></span> <span data-ttu-id="d4802-164">A szabálytalanság típusai a következők lehetnek: Belső, Vevő, Szolgáltatáskérés, Termelés, és Társtermék gyártás.</span><span class="sxs-lookup"><span data-stu-id="d4802-164">The nonconformance types include Internal, Customer, Vendor, Service request, Production, and Co-product production.</span></span> <span data-ttu-id="d4802-165">Egy problématípust több Szabálytalanságtípushoz lehet társítani.</span><span class="sxs-lookup"><span data-stu-id="d4802-165">A single problem type can be associated with multiple nonconformance types.</span></span>  
2. <span data-ttu-id="d4802-166">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d4802-166">Click New.</span></span>
3. <span data-ttu-id="d4802-167">Írjon be egy értéket a Problématípus mezőbe</span><span class="sxs-lookup"><span data-stu-id="d4802-167">In the Problem type field, type a value.</span></span>
4. <span data-ttu-id="d4802-168">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d4802-168">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d4802-169">Kattintson a Szabálytalanságtípusok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d4802-169">Click Non conformance types.</span></span>
    * <span data-ttu-id="d4802-170">A Szabálytalanságtípusok oldal használatával engedélyezze a problématípus használatát egy vagy több szabálytalanságtípusra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="d4802-170">Use the Non conformance types page to authorize the use of a problem type for one or more of the nonconformance types.</span></span> <span data-ttu-id="d4802-171">Például egy hibás kódot érintő problématípus minden szabálytalanságtípusra alkalmazható, míg egy vevői panasz csak a vevői és szervizigénylési szabálytalanságtípusokra.</span><span class="sxs-lookup"><span data-stu-id="d4802-171">For example, a problem type regarding a defect code could apply to all nonconformance types, whereas a problem type about customer complaints may only apply to the customer and service request nonconformance types.</span></span>  
6. <span data-ttu-id="d4802-172">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d4802-172">Click New.</span></span>
7. <span data-ttu-id="d4802-173">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d4802-173">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="d4802-174">Válasszon ki egy lehetőséget Szabálytalanságtípus mezőben.</span><span class="sxs-lookup"><span data-stu-id="d4802-174">In the Non conformance type field, select an option.</span></span>
9. <span data-ttu-id="d4802-175">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d4802-175">Close the page.</span></span>
10. <span data-ttu-id="d4802-176">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d4802-176">Close the page.</span></span>

## <a name="define-quarantine-zones-for-nonconformance-processing"></a><span data-ttu-id="d4802-177">Határozza meg a Karanténzónákat a szabálytalanság feldolgozásához</span><span class="sxs-lookup"><span data-stu-id="d4802-177">Define quarantine zones for nonconformance processing</span></span>
1. <span data-ttu-id="d4802-178">Ugorjon a Készletkezelés > Beállítás > Minőségkezelés > Karanténzónák pontra.</span><span class="sxs-lookup"><span data-stu-id="d4802-178">Go to Inventory management > Setup > Quality management > Quarantine zones.</span></span>
2. <span data-ttu-id="d4802-179">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d4802-179">Click New.</span></span>
3. <span data-ttu-id="d4802-180">Írjon be egy értéket a Karanténzónák mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d4802-180">In the Quarantine zone field, type a value.</span></span>
4. <span data-ttu-id="d4802-181">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d4802-181">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d4802-182">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d4802-182">Close the page.</span></span>
