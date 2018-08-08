---
title: "Javításkezelés"
description: "A problémákat csoportokba rendszerezheti, így hozzájárul ahhoz, hogy a korábban már bevált megoldások javaslatként elérhetők legyenek."
author: ShylaThompson
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAConditionTable, SMASymptomArea, SMADiagnosisArea, SMAResolutionTable, SMARepairStage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 32202344f77352cd3f9c1a807d14192a9bf0d9e6
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---

# <a name="repair-management"></a><span data-ttu-id="fcf46-103">Javításkezelés</span><span class="sxs-lookup"><span data-stu-id="fcf46-103">Repair management</span></span>       

[!include [banner](../includes/banner.md)]


<span data-ttu-id="fcf46-104">A javításkezeléshez a roblémákat csoportokba rendszerezheti.</span><span class="sxs-lookup"><span data-stu-id="fcf46-104">For repair management you can group problems systematically.</span></span> <span data-ttu-id="fcf46-105">Ez hozzájárul ahhoz, hogy a korábban már bevált megoldások javaslatként elérhetők legyenek.</span><span class="sxs-lookup"><span data-stu-id="fcf46-105">This is to help with the suggestion of solutions that have been successful in the past.</span></span>

<span data-ttu-id="fcf46-106">Ön beállítja a tüneteket, a diagnózist és a megoldás beállításait.</span><span class="sxs-lookup"><span data-stu-id="fcf46-106">You set up symptoms, diagnosis, and resolution settings.</span></span> <span data-ttu-id="fcf46-107">Ezeket mindet alkalmazhatja később, amikor hasonló elem érkezik javításra.</span><span class="sxs-lookup"><span data-stu-id="fcf46-107">All these can later be applied when you receive a similar item for repair.</span></span> <span data-ttu-id="fcf46-108">Javítási állapotokat is beállíthat, amelyekkel egy-egy javítási kérdés előrehaladását nyomon lehet követni.</span><span class="sxs-lookup"><span data-stu-id="fcf46-108">You can also set up repair stages that can follow the progress of a repair issue.</span></span>

## <a name="setting-up-repair-management"></a><span data-ttu-id="fcf46-109">A javításkezelés beállítása</span><span class="sxs-lookup"><span data-stu-id="fcf46-109">Setting up repair management</span></span>

<span data-ttu-id="fcf46-110">A következő beállítási űrlapok segítségével adja meg a tünetek, a diagnózis és a megoldás meghatározásához használt adatokat a javításhoz.</span><span class="sxs-lookup"><span data-stu-id="fcf46-110">Use the following setup forms to enter information that will be used to specify the symptoms, the diagnosis, and the resolution, of the repair.</span></span>

1.  <span data-ttu-id="fcf46-111">Kattintson a **Szolgáltatáskezelés**\>**Beállítás**\>**Javítás**\>**Feltételek** elemre.</span><span class="sxs-lookup"><span data-stu-id="fcf46-111">Click **Service management** \> **Setup** \> **Repair** \> **Conditions**.</span></span>

2.  <span data-ttu-id="fcf46-112">Kattintson a **Szolgáltatáskezelés**\>**Beállítás**\>**Javítás**\>**Tünetterületek** elemre.</span><span class="sxs-lookup"><span data-stu-id="fcf46-112">Click **Service management** \> **Setup** \> **Repair** \> **Symptom areas**.</span></span>

3.  <span data-ttu-id="fcf46-113">Kattintson a **Szolgáltatáskezelés**\>**Beállítás**\>**Javítás**\>**Diagnózisterületek** elemre.</span><span class="sxs-lookup"><span data-stu-id="fcf46-113">Click **Service management** \> **Setup** \> **Repair** \> **Diagnosis areas**.</span></span>

4.  <span data-ttu-id="fcf46-114">Kattintson a **Szolgáltatáskezelés**\>**Beállítás**\>**Javítás**\>**Megoldások** elemre.</span><span class="sxs-lookup"><span data-stu-id="fcf46-114">Click **Service management** \> **Setup** \> **Repair** \> **Resolutions**.</span></span>

5.  <span data-ttu-id="fcf46-115">Kattintson a **Szolgáltatáskezelés**\>**Beállítás**\>**Javítás**\>**Javítási állapotok** elemre.</span><span class="sxs-lookup"><span data-stu-id="fcf46-115">Click **Service management** \> **Setup** \> **Repair** \> **Repair stages**.</span></span>

## <a name="symptoms-and-conditions"></a><span data-ttu-id="fcf46-116">Tünetek és feltételek</span><span class="sxs-lookup"><span data-stu-id="fcf46-116">Symptoms and conditions</span></span>

<span data-ttu-id="fcf46-117">A tünetek a probléma vevő általi leírását jelentik.</span><span class="sxs-lookup"><span data-stu-id="fcf46-117">Symptoms are how the customer characterizes the problem.</span></span> <span data-ttu-id="fcf46-118">A tünetek a vevő azon megfigyeléseit foglalják magukban, amelyek a javítás szükségességét jelzik.</span><span class="sxs-lookup"><span data-stu-id="fcf46-118">Symptoms include the customer observations that indicate the need for repair.</span></span>

<span data-ttu-id="fcf46-119">Beállíthat tünetterületeket, tünetkódokat és feltételeket.</span><span class="sxs-lookup"><span data-stu-id="fcf46-119">You can set up symptom areas, symptom codes, and conditions.</span></span> <span data-ttu-id="fcf46-120">A tünetterület a meghibásodás területét fedi le, a tünetkód a meghibásodása tünetét fedi le..</span><span class="sxs-lookup"><span data-stu-id="fcf46-120">The symptom area covers the area of malfunction, and the symptom code covers the malfunction symptom.</span></span> <span data-ttu-id="fcf46-121">A feltétel azt a helyzetet vagy környezetet mutatja be, amelynél a probléma előfordul.</span><span class="sxs-lookup"><span data-stu-id="fcf46-121">The condition describes the situation or environment that is present when the problem occurs.</span></span>

<span data-ttu-id="fcf46-122">**Példa**</span><span class="sxs-lookup"><span data-stu-id="fcf46-122">**Example**</span></span>

<span data-ttu-id="fcf46-123">A számítógépet azért hozták be javításra, mert a merevlemez hosszabb ideig tartó használat után nem működik.</span><span class="sxs-lookup"><span data-stu-id="fcf46-123">A computer is brought in for repair because the hard drive fails after an extended period of use.</span></span> <span data-ttu-id="fcf46-124">A merevlemez meghibásodása "kék képernyő" hibaüzenetet okoz.</span><span class="sxs-lookup"><span data-stu-id="fcf46-124">The hard drive failure causes a blue screen error.</span></span> <span data-ttu-id="fcf46-125">A technikust, aki átveszi a számítógépet, a következő tüneteket és feltételeket rögzíti:</span><span class="sxs-lookup"><span data-stu-id="fcf46-125">The technician who receives the computer enters the following symptoms and conditions:</span></span>

1.  <span data-ttu-id="fcf46-126">A tünetterület a merevlemez</span><span class="sxs-lookup"><span data-stu-id="fcf46-126">The symptom area is the hard drive</span></span>

2.  <span data-ttu-id="fcf46-127">A tünetkód a "kék képernyő" hiba</span><span class="sxs-lookup"><span data-stu-id="fcf46-127">The symptom code is the blue screen error</span></span>

3.  <span data-ttu-id="fcf46-128">A körülmény az, hogy a merevlemez hosszabb idejű használat után hibásodik meg</span><span class="sxs-lookup"><span data-stu-id="fcf46-128">The condition is that the hard drive fails after extended use</span></span>

## <a name="diagnosis-and-resolutions"></a><span data-ttu-id="fcf46-129">Diagnózis és megoldások</span><span class="sxs-lookup"><span data-stu-id="fcf46-129">Diagnosis and resolutions</span></span>

<span data-ttu-id="fcf46-130">A diagnózis és a megoldások mezői a javítási szempontból tett állítások.</span><span class="sxs-lookup"><span data-stu-id="fcf46-130">The diagnosis and resolution fields are statements from the repair perspective.</span></span> <span data-ttu-id="fcf46-131">Ezek azok a lépések, amelyeken egy technikus végigment a probléma kivizsgálása céljából.</span><span class="sxs-lookup"><span data-stu-id="fcf46-131">These are the steps that a technician went through to investigate the problem.</span></span>

<span data-ttu-id="fcf46-132">A diagnosztikai terület foglalkozik a feladat megoldásához végrehajtandó művelettel.</span><span class="sxs-lookup"><span data-stu-id="fcf46-132">The diagnosis area covers the operation that must occur to solve the issue.</span></span> <span data-ttu-id="fcf46-133">A diagnóziskód mutatja, hogyan történt a probléma kezelése, míg a megoldás lehet az, hogy a cikket javították, kicserélték, vagy a vevő visszavonta a rendelést.</span><span class="sxs-lookup"><span data-stu-id="fcf46-133">The diagnosis code is how the problem was handled, and the resolution could be that the item was repaired, replaced, or the order was canceled by the customer.</span></span> <span data-ttu-id="fcf46-134">Ha például a számítógépet megjavítják, a diagnózis területe tartalmazhatja a „hibás alkatrész” leírást, a diagnóziskód lehet „új videokártya beszerelve”, míg a megoldás lehet „cserélve”.</span><span class="sxs-lookup"><span data-stu-id="fcf46-134">For example, if the computer is repaired, the diagnosis area could be "defective part," the diagnosis code could be "new video card installed," and the resolution could be "replaced."</span></span>

## <a name="repair-stages"></a><span data-ttu-id="fcf46-135">Javítási állapotok</span><span class="sxs-lookup"><span data-stu-id="fcf46-135">Repair stages</span></span>

<span data-ttu-id="fcf46-136">A javítási állapotok a javítási folyamat haladását mutatják.</span><span class="sxs-lookup"><span data-stu-id="fcf46-136">Repair stages state the progress of the repair process.</span></span> <span data-ttu-id="fcf46-137">A javítási állapothoz egy **Elkészült** láttamozási paraméter is tartozik, amely mutatja, hogy a javítási sor befejezése megtörtént, és rögzítve van a befejezés dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="fcf46-137">The repair stage has a **Finished** sign-off parameter that indicates that the repair line has been completed, and the finishing date and time has been recorded.</span></span>

## <a name="applying-repair-management"></a><span data-ttu-id="fcf46-138">A javításkezelés alkalmazása</span><span class="sxs-lookup"><span data-stu-id="fcf46-138">Applying repair management</span></span>

<span data-ttu-id="fcf46-139">Ahhoz, hogy egy cikken alkalmazható legyen a javításkezelés, a cikken be kell lennie állítva egy szervizrendeléshez tartozó szolgáltatásiobjektum-kapcsolatnak.</span><span class="sxs-lookup"><span data-stu-id="fcf46-139">To apply repair management to an item, the item must be set up with a service object relation on a service order.</span></span> <span data-ttu-id="fcf46-140">Ezután a szervizrendelésből létrehozhat egy javítási sort az aktuális feladatra vonatkozó információval.</span><span class="sxs-lookup"><span data-stu-id="fcf46-140">From the service order you can then create a repair line with information about the current issue.</span></span> <span data-ttu-id="fcf46-141">A javítási soron határozza meg a javítás alatt álló szolgáltatási objektumot, valamint a tünetekkel, diagnózissal és a végrehajtással kapcsolatos információkat.</span><span class="sxs-lookup"><span data-stu-id="fcf46-141">On the repair line you define the service object that is in repair and information about symptoms, diagnosis, and execution.</span></span> <span data-ttu-id="fcf46-142">A javítási sorhoz jegyzetet is létrehozhat.</span><span class="sxs-lookup"><span data-stu-id="fcf46-142">You can also create a note for the repair line.</span></span>

<span data-ttu-id="fcf46-143">A javítási folyamat minden lépéséhez létrehozhat külön javítási sort.</span><span class="sxs-lookup"><span data-stu-id="fcf46-143">You can create repair lines for each step in the repair process.</span></span>

## <a name="create-a-repair-line-on-a-service-order"></a><span data-ttu-id="fcf46-144">Javítási sor létrehozása szervizrendeléshez</span><span class="sxs-lookup"><span data-stu-id="fcf46-144">Create a repair line on a service order</span></span>

1.  <span data-ttu-id="fcf46-145">Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.</span><span class="sxs-lookup"><span data-stu-id="fcf46-145">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="fcf46-146">Válassza ki azt a szervizrendelést, amelyik a javítást igénylő szolgáltatási objektumot tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="fcf46-146">Select the service order with the service object that needs repair.</span></span>

3.  <span data-ttu-id="fcf46-147">Kattintson a **Javítás** \>**Javítási sorok** elemre a **Javítási sorok** képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="fcf46-147">Click **Repair** \> **Repair lines** to open the **Repair lines** form.</span></span>

4.  <span data-ttu-id="fcf46-148">Új sor létrehozásához nyomja le a CTRL+N billentyűkombinációt.</span><span class="sxs-lookup"><span data-stu-id="fcf46-148">Press CTRL+N to create a new line.</span></span>

5.  <span data-ttu-id="fcf46-149">Válasszon ki egy szolgáltatási objektumot.</span><span class="sxs-lookup"><span data-stu-id="fcf46-149">Select a service object.</span></span> <span data-ttu-id="fcf46-150">Bármely szolgáltatási objektum választható, amelyiknél be van állítva objektumkapcsolat a szervizrendeléshez.</span><span class="sxs-lookup"><span data-stu-id="fcf46-150">You can select any service object that has been set up with an object relation on the service order.</span></span>

6.  <span data-ttu-id="fcf46-151">Válassza ki a javítási sorban az odavágó, előre beállított tüneteket, diagnózis- és végrehajtási értékeket, és ha szükséges, a **Megjegyzés** fülre kattintva hozzon létre jegyzetet a javítási sorhoz.</span><span class="sxs-lookup"><span data-stu-id="fcf46-151">Select any of the preset symptoms, diagnosis, and execution values that are relevant in the repair line and then click the **Note** tab to create a note on the repair line, if needed.</span></span>

7.  <span data-ttu-id="fcf46-152">A CTRL+S billentyűkombinációval mentse az új javítási sort.</span><span class="sxs-lookup"><span data-stu-id="fcf46-152">Press CTRL+S to save the new repair line.</span></span> <span data-ttu-id="fcf46-153">A **Javítási sorok** képernyő **Általános** lapjának **Létrehozás dátuma és időpontja** mezője frissül a mentés dátumával.</span><span class="sxs-lookup"><span data-stu-id="fcf46-153">The **Created date and time** field in the **General** tab of the **Repair lines** form is updated with the time of saving.</span></span>

## <a name="tracking-progress-and-resolving-a-repair-issue"></a><span data-ttu-id="fcf46-154">Nyomon követési állapot és egy javítási feladat megoldása</span><span class="sxs-lookup"><span data-stu-id="fcf46-154">Tracking progress and resolving a repair issue</span></span>

<span data-ttu-id="fcf46-155">A javítási sor javítási állapotainak megadásával nyomon követheti a javítás előrehaladását.</span><span class="sxs-lookup"><span data-stu-id="fcf46-155">You can set the repair stages of a repair line to track the progress of the repair.</span></span>

<span data-ttu-id="fcf46-156">Amikor egy javítási feladat elkészül, lezárhatja a javítási sort.</span><span class="sxs-lookup"><span data-stu-id="fcf46-156">When a repair issue is resolved, you can close the repair line.</span></span> <span data-ttu-id="fcf46-157">A javítási állapotot állítsa be olyan állapotra, amelynél az **Elkészült** tulajdonság engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="fcf46-157">Set the repair stage to a stage with a **Finished** property enabled.</span></span> <span data-ttu-id="fcf46-158">Befejezési időként a program az aktuális dátumot és időt regisztrálja a soron.</span><span class="sxs-lookup"><span data-stu-id="fcf46-158">The current date and time is registered as the finish time on the line.</span></span>

## <a name="close-a-repair-line-for-a-resolved-issue"></a><span data-ttu-id="fcf46-159">Megoldott feladat javítási sorának lezárása</span><span class="sxs-lookup"><span data-stu-id="fcf46-159">Close a repair line for a resolved issue</span></span>

1.  <span data-ttu-id="fcf46-160">Nyissa meg a **Javítási sorok** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="fcf46-160">Open the **Repair lines** form.</span></span> <span data-ttu-id="fcf46-161">Végezze el a témakörben korábban, a javítási sor létrehozásánál ismertetett lépéseket.</span><span class="sxs-lookup"><span data-stu-id="fcf46-161">Follow the procedure earlier in this topic to create a repair line.</span></span>

2.  <span data-ttu-id="fcf46-162">Válassza ki a lezárni kívánt javítási feladathoz tartozó javítási sort.</span><span class="sxs-lookup"><span data-stu-id="fcf46-162">Select the repair line with the repair issue that you want to close.</span></span>

3.  <span data-ttu-id="fcf46-163">A **Javítási állapot** mezőben válasszon olyan állapotot, amelynél engedélyezve van az **Elkészült** tulajdonság.</span><span class="sxs-lookup"><span data-stu-id="fcf46-163">In the **Repair stage** field, select a stage with the **Finished** property enabled.</span></span>

  



