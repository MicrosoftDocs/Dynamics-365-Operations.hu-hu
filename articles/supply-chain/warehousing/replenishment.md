---
title: "Feltöltés"
description: "A témakör ismerteti a Raktárkezelési funkciót használó raktárok számára elérhető feltöltési stratégiákat."
author: Mirzaab
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSReplenishmentTemplates
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 90043
ms.assetid: 49fa97eb-8e10-49a5-9261-1e393159f178
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 67e361aedf77166e01d9e7a5b9dcb19d08ea26bd
ms.openlocfilehash: 872fbe41ed8137c1e7bec24656d4f132e170ae7f
ms.contentlocale: hu-hu
ms.lasthandoff: 10/05/2017

---

# <a name="replenishment"></a><span data-ttu-id="8b592-103">Feltöltés</span><span class="sxs-lookup"><span data-stu-id="8b592-103">Replenishment</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="8b592-104">A témakör ismerteti a Raktárkezelési funkciót használó raktárok számára elérhető feltöltési stratégiákat.</span><span class="sxs-lookup"><span data-stu-id="8b592-104">This topic describes the replenishment strategies that are available for warehouses that use the functionality that is available in Warehouse management.</span></span> <span data-ttu-id="8b592-105">A témakör információi nem vonatkoznak a raktározási megoldásra, amely a Készletkezelés modulból érhető el.</span><span class="sxs-lookup"><span data-stu-id="8b592-105">The information in this topic doesn't apply to the warehousing solution that is available in Inventory management.</span></span>

<span data-ttu-id="8b592-106">A következő feltöltési stratégiák állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="8b592-106">The following replenishment strategies are available:</span></span>

- <span data-ttu-id="8b592-107">**Hullámigény feltöltés** – Ez a stratégia feltöltési munkát hoz létre kimenő rendelésekhez vagy terhelésekhez, ha a készlet nem érhető el, amikor a munkát létrehozza a hullám.</span><span class="sxs-lookup"><span data-stu-id="8b592-107">**Wave demand replenishment** – This strategy creates replenishment work for outbound orders or loads if inventory isn't available when the wave creates work.</span></span> <span data-ttu-id="8b592-108">Ha például nem áll rendelkezésre egy értékesítési rendeléshez szükséges mennyiség a hullám feldolgozásakor, feltöltési munka hozható létre.</span><span class="sxs-lookup"><span data-stu-id="8b592-108">For example, replenishment work can be created if the quantity that is required for a sales order isn't available when a wave is processed.</span></span>
- <span data-ttu-id="8b592-109">**Minimális vagy maximális feltöltés** – Ez a stratégia minimális és maximális készletezési korlátokat használ a helyek feltöltésének meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="8b592-109">**Min/Max replenishment** – This strategy uses minimum and maximum stocking limits to determine when locations should be replenished.</span></span> <span data-ttu-id="8b592-110">A cikkek és helyek feltételei meghatározzák a feltöltéshez kiértékelt készletet.</span><span class="sxs-lookup"><span data-stu-id="8b592-110">The item and location criteria define the inventory that is evaluated for replenishment.</span></span> <span data-ttu-id="8b592-111">A minimális vagy maximális feltöltési sablonok a legfontosabbak megfelelő szintek megtartásához a a kitárolási helyeken.</span><span class="sxs-lookup"><span data-stu-id="8b592-111">Min/Max replenishment templates are the primary mechanism for maintaining optimal levels in picking locations.</span></span> <span data-ttu-id="8b592-112">Annak biztosításához, hogy megfelelő mennyiségű kitárolási felület készlet legyen elérhető a hullámigénynek való megfeleléshez, használja kiegészítésként az igényfeltöltést a minimális és maximális feltöltési ciklusok között.</span><span class="sxs-lookup"><span data-stu-id="8b592-112">To help guarantee that enough pick face inventory is available to meet wave demand, you can use demand replenishment as a supplement between Min/Max replenishment cycles.</span></span>
- <span data-ttu-id="8b592-113">**Rakomány igényfeltöltése** – Ez a stratégia többféle rakomány iránti keresletet összegez, és feltöltési munkát hoz létre, mely a megfelelő kitárolási helyek feltöltéséhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="8b592-113">**Load demand replenishment** – This strategy sums the demand for several loads and creates the replenishment work that is required in order to stock the relevant picking locations.</span></span> <span data-ttu-id="8b592-114">Ez a stratégia biztosítja, hogy a létrehozott rakományok kitárolhatók legyenek a raktári kibocsátásukat követően.</span><span class="sxs-lookup"><span data-stu-id="8b592-114">This strategy helps guarantee that the loads that are created can be picked in the warehouse after they are released.</span></span>
- <span data-ttu-id="8b592-115">**Azonnali feltöltés** – Ez a stratégia felölti a készletet, mielőtt hullám futtatására kerülne sor, ha a felosztás sikertelen egy olyan helyutasítás sorművelete esetén, amelyhez feltöltési sablon tartozik.</span><span class="sxs-lookup"><span data-stu-id="8b592-115">**Immediate replenishment** – This strategy replenishes inventory before a wave is run if allocation fails for a location directive line that has a replenishment template.</span></span> 

<span data-ttu-id="8b592-116">Mind a négy stratégia feltöltési sablon alapján hoz létre feltöltési munkát.</span><span class="sxs-lookup"><span data-stu-id="8b592-116">All four strategies create replenishment work, based on a replenishment template.</span></span>

## <a name="wave-demand-replenishment"></a><span data-ttu-id="8b592-117">Hullámigény feltöltése</span><span class="sxs-lookup"><span data-stu-id="8b592-117">Wave demand replenishment</span></span>
<span data-ttu-id="8b592-118">Hullámigény-feltöltés feltöltési munkát hoz létre termelési rendelésekhez, kanbanokhoz, kimenő rendelésekhez vagy rakományokhoz igény alapján, ha a készlet nem érhető el, amikor a munkát létrehozza a hullám.</span><span class="sxs-lookup"><span data-stu-id="8b592-118">Wave demand replenishment creates replenishment work, based on demand, if the quantity that is required for production orders, kanbans, outbound orders, or loads isn't available when a wave creates work.</span></span> <span data-ttu-id="8b592-119">A feltöltési sablon a feltételekről, a mértékegységről, az igény növelési egységéről és a helyről tartalmaz adatokat.</span><span class="sxs-lookup"><span data-stu-id="8b592-119">The replenishment template contains information about the item criteria, the unit of measure, the demand increment, and the location.</span></span> 

<span data-ttu-id="8b592-120">A helyutasítások segítségével meghatározhatja, mely helyeket kell feltölteni.</span><span class="sxs-lookup"><span data-stu-id="8b592-120">Location directives are used to determine which location should be replenished.</span></span> <span data-ttu-id="8b592-121">A helyutasításokat hozzákapcsolhatja feltöltési sablonhoz a **Utasításkód** mező használatával.</span><span class="sxs-lookup"><span data-stu-id="8b592-121">You link these location directives to the replenishment template by using the **Directive code** field.</span></span> <span data-ttu-id="8b592-122">Ha a **Utasításkód** mező nincs beállítva, a lekérdezések segítségével meghatározható, hogy melyik helyutasítást kell használni.</span><span class="sxs-lookup"><span data-stu-id="8b592-122">If the **Directive code** field isn't set, queries are used to determine which location directive should be used.</span></span> <span data-ttu-id="8b592-123">Ha az utasításkód nincs meghatározva a feltöltési sablonban és a helyutasításnak van utasításkódja, a helyutasítás figyelmen kívül lesz hagyva, még akkor is, ha a helyutasítás lekérdezése helyes.</span><span class="sxs-lookup"><span data-stu-id="8b592-123">Note that if a directive code isn't specified in the replenishment template, and the location directive has a directive code, the location directive will be ignored, even if the query on the location directive is correct.</span></span> <span data-ttu-id="8b592-124">Kitárolási helyutasítás segítségével meghatározható a feltöltéshez szükséges készlet beszerzési helye.</span><span class="sxs-lookup"><span data-stu-id="8b592-124">Pick location directives are used to determine where to get inventory for the replenishment.</span></span> 

<span data-ttu-id="8b592-125">Sablon létrehozása mellett meg kell adnia bizonyos feltöltési beállításokat a hullámsablonon.</span><span class="sxs-lookup"><span data-stu-id="8b592-125">In addition to creating a template, you must specify some replenishment settings in the wave template.</span></span> <span data-ttu-id="8b592-126">A hullámsablon feltöltési hullámlépést kell tartalmazzon, ami csak akkor fut le, ha a cikkfelosztás nem sikeres.</span><span class="sxs-lookup"><span data-stu-id="8b592-126">The wave template should contain a wave step for replenishment that is run only if an item isn't successfully allocated.</span></span> <span data-ttu-id="8b592-127">A feltöltési hullámlépés egy hullámlépéskód alapján határozza meg, melyik feltöltési sablont kell használni.</span><span class="sxs-lookup"><span data-stu-id="8b592-127">This replenishment wave step uses a wave step code to determine which replenishment template should be used.</span></span> <span data-ttu-id="8b592-128">Győződjön meg róla, hogy a feltöltés hullámlépése mellett **Feltöltés** van megadva a **Módszerek** szakaszban a hullámsablonon.</span><span class="sxs-lookup"><span data-stu-id="8b592-128">In addition to having a wave step for replenishment, you must make sure that **Replenish** is selected in the **Methods** section of the wave template.</span></span> 

<span data-ttu-id="8b592-129">A **Feltöltési sablon** oldal tartalmaz egy **Hullámigény engedélyezése a nem lefoglalt mennyiségek használatához** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="8b592-129">The **Replenishment template** page includes an **Allow wave demand to use unreserved quantities** check box.</span></span> <span data-ttu-id="8b592-130">Be kell jelölnie a jelölőnégyzetet, ha engedélyezni kívánja az igényfeltöltéseket a kiválasztott feltöltési sablonokból generált munkákból történő foglalatlan mennyiségek kivonásához.</span><span class="sxs-lookup"><span data-stu-id="8b592-130">Select this check box if demand replenishment should be able to deduct unreserved quantities from work that is generated from the selected replenishment template.</span></span> <span data-ttu-id="8b592-131">Ezt a jelölőnégyzetet jelölje be minden egyes meglévő feltöltési sablon esetén annak az engedélyezéséhez, hogy az igényfeltöltési sablonok használhassák ezt a logikát.</span><span class="sxs-lookup"><span data-stu-id="8b592-131">To enable demand replenishment templates to use this logic, select this check box for every existing replenishment template.</span></span> <span data-ttu-id="8b592-132">Ha igényfeltöltés jelenik meg a raktárban, az levonja az igényt a foglalatlan mennyiségekkel rendelkező, meglévő feltöltési munkából, ha a munka a **Foglalatlan mennyiség használatához szükséges hullámigények engedélyezése** jelölőnégyzeten bejelölt feltöltési sablonból származik.</span><span class="sxs-lookup"><span data-stu-id="8b592-132">When demand replenishment is triggered in the warehouse, it will deduct the demand from existing replenishment work that has unreserved quantities, if the work originates from replenishment templates where the **Allow wave demand to use unreserved quantities** check box is selected.</span></span>

<span data-ttu-id="8b592-133">Az igényfeltöltés értékesítési rendelések, átmozgatási rendelések, termelési rendelések és kanbanok esetén támogatott.</span><span class="sxs-lookup"><span data-stu-id="8b592-133">Demand replenishment is supported for sales orders, transfer orders, production orders, and kanbans.</span></span> 

## <a name="minmax-replenishment"></a><span data-ttu-id="8b592-134">Minimális vagy maximális feltöltés</span><span class="sxs-lookup"><span data-stu-id="8b592-134">Min/Max replenishment</span></span>
<span data-ttu-id="8b592-135">Minimális/maximális feltöltés esetén a készletet úgy töltik fel, hogy a beállított minimális és maximális értékhatárok között legyen.</span><span class="sxs-lookup"><span data-stu-id="8b592-135">In Min/Max replenishment, stock is replenished so that it's between the minimum and maximum limits that have been set.</span></span> <span data-ttu-id="8b592-136">Általában ez a folyamat naponta egyszer fut le, hogy biztosítsa, a kitárolás megkezdése előtt minden kitárolási hely maximálisan fel legyen töltve.</span><span class="sxs-lookup"><span data-stu-id="8b592-136">Typically, this process occurs one time every day, to help guarantee that all picking locations are filled to the maximum level before picking starts.</span></span> 

<span data-ttu-id="8b592-137">A minimális és maximális összeg a feltöltési sablonban van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="8b592-137">The minimum and maximum amounts are set in a replenishment template.</span></span> <span data-ttu-id="8b592-138">A sablon számos egyéb beállítása hasonlít a Hullámigény feltöltése során használt sablonok beállításaira.</span><span class="sxs-lookup"><span data-stu-id="8b592-138">Many of the other settings in the template resemble the settings in templates that are used in Wave demand replenishment.</span></span> <span data-ttu-id="8b592-139">A sablonnak tartalmaznia kell egy-egy sort minden egyes cikkhez és helyhez.</span><span class="sxs-lookup"><span data-stu-id="8b592-139">The template should contain one line for each item and location.</span></span> <span data-ttu-id="8b592-140">Ha a kötegelt feldolgozással futtatja a feltöltést, a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition megvizsgálja, hogy szükséges-e feltöltés abban a sorrendben, amelyben a sorok rendezve vannak.</span><span class="sxs-lookup"><span data-stu-id="8b592-140">When you run replenishment by using the batch job, Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, evaluates whether replenishment is required by using the sequence that the lines are organized in.</span></span> 

<span data-ttu-id="8b592-141">Fontos megjegyezni, hogy a minimális/maximális feltöltési stratégia nem tud üres helyet feltölteni, kivéve, ha a hely a cikkhez rögzített helyként van beállítva.</span><span class="sxs-lookup"><span data-stu-id="8b592-141">Note that the Min/Max replenishment strategy can't replenish an empty location unless the location is set as the fixed location for the item.</span></span> <span data-ttu-id="8b592-142">Ha a hely, amit fel kell tölteni, nem rögzített hely, a rendszer nem tudja megállapítani, melyik cikk feltöltése szükséges.</span><span class="sxs-lookup"><span data-stu-id="8b592-142">If the location that must be replenished isn't a fixed location, the system can't determine which item should be replenished.</span></span> <span data-ttu-id="8b592-143">Ezért legalább néhány aktuális készlet szükséges a feltöltés bekövetkezte előtt.</span><span class="sxs-lookup"><span data-stu-id="8b592-143">Therefore, at least some on-hand quantity is required before replenishment occurs.</span></span>

## <a name="load-demand-replenishment"></a><span data-ttu-id="8b592-144">Rakomány igényfeltöltése</span><span class="sxs-lookup"><span data-stu-id="8b592-144">Load demand replenishment</span></span>
<span data-ttu-id="8b592-145">A Rakomány igényfeltöltése stratégia többféle rakomány iránti keresletet összegez, és feltöltési munkát hoz létre, mely a megfelelő kitárolási helyek feltöltéséhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="8b592-145">Load demand replenishment sums the demand for several loads and creates the replenishment work that is required in order to stock the relevant picking locations.</span></span> <span data-ttu-id="8b592-146">A Rakomány igényfeltöltése sok tekintetben hasonlít a Hullámigény feltöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="8b592-146">Load demand replenishment resembles Wave demand replenishment in many ways.</span></span> <span data-ttu-id="8b592-147">A legnagyobb eltérés a Rakomány igényfeltöltése és a Hullámigény feltöltése között a lefutás módja és ideje között figyelhető meg.</span><span class="sxs-lookup"><span data-stu-id="8b592-147">The main difference is how and when Load demand replenishment and Wave demand replenishment are run.</span></span> <span data-ttu-id="8b592-148">Mint a Minimális vagy maximális feltöltés, a Rakomány igényfeltöltése is kötegelt feladat használatával fut.</span><span class="sxs-lookup"><span data-stu-id="8b592-148">Like Min/Max replenishment, Load demand replenishment is run by using a batch job.</span></span> <span data-ttu-id="8b592-149">Az elszámolóár beállításához a **Rakomány igényfeltöltése** oldalon válassza ki a feltöltési sablont, állítson be szűrőlekérdezést a rakományigény meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="8b592-149">To set up the batch job, on the **Load demand replenishment** page, select the replenishment template to use, and set a filter query to specify which loads are used to determine the demand.</span></span> <span data-ttu-id="8b592-150">A helylekérdezés határozza meg a helyeket, amelyekből bármely rendelkezésre álló mennyiség levonásra kerül a rakományok összesített igényének való megfelelés teljesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="8b592-150">The location query defines the locations that any available quantity will be subtracted from to meet the aggregated demand of the loads.</span></span>

## <a name="immediate-replenishment"></a><span data-ttu-id="8b592-151">Azonnali feltöltés</span><span class="sxs-lookup"><span data-stu-id="8b592-151">Immediate replenishment</span></span>
<span data-ttu-id="8b592-152">Ahelyett, hogy a felosztási folyamat végén összegezné az igényeket és végezne feltöltést az összegzett mennyiségek alapján, alkalmazhat közvetlen feltöltési stratégiát.</span><span class="sxs-lookup"><span data-stu-id="8b592-152">Instead of having to sum demand at the end of an allocation process and do replenishment on the basis of the summed up quantity, you can apply the Immediate replenishment strategy.</span></span> <span data-ttu-id="8b592-153">Ezen stratégia használata esetén a készletet fel lehet tölteni azonnal azután, hogy egy helyutasítás sor sikertelen volt.</span><span class="sxs-lookup"><span data-stu-id="8b592-153">When you use this strategy, the inventory can be replenished immediately after a location directive line fails.</span></span> <span data-ttu-id="8b592-154">Így úgy állíthatja be a feltöltést,, hogy az adott egységekre korlátozódjon, és hogy az adott helyekhez beállított mennyiséget használja fel.</span><span class="sxs-lookup"><span data-stu-id="8b592-154">Therefore, you can set up the replenishment so that it's restricted by specific units, and so that it uses quantities that are set for specific locations.</span></span>

## <a name="replenishment-prerequisites"></a><span data-ttu-id="8b592-155">Feltöltés előfeltételei</span><span class="sxs-lookup"><span data-stu-id="8b592-155">Replenishment prerequisites</span></span>
| <span data-ttu-id="8b592-156">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="8b592-156">Prerequisite</span></span>            | <span data-ttu-id="8b592-157">Leírás</span><span class="sxs-lookup"><span data-stu-id="8b592-157">Description</span></span> |
|-------------------------|-------------|
| <span data-ttu-id="8b592-158">Cikk</span><span class="sxs-lookup"><span data-stu-id="8b592-158">Item</span></span>                    | <span data-ttu-id="8b592-159">A cikknek elérhetőnek kell lennie a raktárkezelő folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="8b592-159">The item must be enabled for warehouse management processes.</span></span> |
| <span data-ttu-id="8b592-160">Raktár</span><span class="sxs-lookup"><span data-stu-id="8b592-160">Warehouse</span></span>               | <span data-ttu-id="8b592-161">A raktárnak elérhetőnek kell lennie a raktárkezelő folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="8b592-161">The warehouse must be enabled for warehouse management processes.</span></span> <span data-ttu-id="8b592-162">A raktárt a **Raktárak** oldalon a raktár kiválasztásával, majd a **Raktárkezelési folyamatok alkalmazása** lehetőség kijelölésével tudja a raktárkezelési folyamatokhoz elérhetővé tenni.</span><span class="sxs-lookup"><span data-stu-id="8b592-162">To enable a warehouse for warehouse management processes, on the **Warehouses** page, select the warehouse, and then select the **Use warehouse management processes** option.</span></span> |
| <span data-ttu-id="8b592-163">Feltöltési sablonok</span><span class="sxs-lookup"><span data-stu-id="8b592-163">Replenishment templates</span></span> | <span data-ttu-id="8b592-164">Legalább az egyik feltöltési sablon esetén be kell állítani a Minimális vagy maximális feltöltést, Hullámigény feltöltését vagy a Rakomány igényfeltöltését.</span><span class="sxs-lookup"><span data-stu-id="8b592-164">At least one replenishment template must be set up for Min/Max replenishment, Wave demand replenishment, or Load demand replenishment.</span></span> |
| <span data-ttu-id="8b592-165">Helyek</span><span class="sxs-lookup"><span data-stu-id="8b592-165">Locations</span></span>               | <span data-ttu-id="8b592-166">A tárolóhelyeket létre kell hozni és csatlakoztatni kell a helyprofilhoz.</span><span class="sxs-lookup"><span data-stu-id="8b592-166">Locations must be created and connected to a location profile.</span></span> |
| <span data-ttu-id="8b592-167">Helyprofilok</span><span class="sxs-lookup"><span data-stu-id="8b592-167">Location profiles</span></span>       | <span data-ttu-id="8b592-168">Tárolóhelyek létrehozásához helyprofilok meglétére van szükség.</span><span class="sxs-lookup"><span data-stu-id="8b592-168">Location profiles are required in order to create locations.</span></span> |
| <span data-ttu-id="8b592-169">Helyutasítások</span><span class="sxs-lookup"><span data-stu-id="8b592-169">Location directives</span></span>     | <span data-ttu-id="8b592-170">Helyutasítások szükségesek a munka olyan helyekre való irányításához, ahol feltöltés szükséges és ahol a készlet forrása van.</span><span class="sxs-lookup"><span data-stu-id="8b592-170">Location directives are required in order to guide work to the locations where replenishment is required and to the locations that inventory is sourced from.</span></span> |
| <span data-ttu-id="8b592-171">Munkasablonok</span><span class="sxs-lookup"><span data-stu-id="8b592-171">Work templates</span></span>          | <span data-ttu-id="8b592-172">Munkasablonok szükségesek a **Feltöltés** típusához, feltöltési munka létrehozásához, így a készlet a kívánt helyre mozgatható.</span><span class="sxs-lookup"><span data-stu-id="8b592-172">Work templates of the **Replenishment** type are required in order to create replenishment work so that inventory can be moved to the desired locations.</span></span> |
