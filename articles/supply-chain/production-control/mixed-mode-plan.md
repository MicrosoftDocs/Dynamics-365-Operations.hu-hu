---
title: "Vegyes módú tervezése - Elkülönített, folyamatos és lean típusú források kombinálása"
description: "Ez a cikk a vegyes módú tervezéssel kapcsolatban nyújt tájékoztatást. A vegyes módú tervezésben modellezheti az anyagáramláson alapuló ellátási láncot. A Microsoft Dynamics 365 for Finance and Operations meggyőződik arról, hogy az anyag folyamat követi a modelleket, függetlenül a kiválasztott ellátási házirendtől (kanban-ok termelési rendelések, beszerzési rendelések, feldolgozásiköteg-rendelések és átmozgatási rendelések)."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 52931
ms.assetid: 2e8b5fd1-cee9-45da-a3ae-6961fb020b89
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 09ced68ffe8ff300a04beb65fdf8527e63456f04
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="mixed-mode-planning---combine-discrete-process-and-lean-sourcing"></a><span data-ttu-id="9222c-105">Vegyes módú tervezése - Elkülönített, folyamatos és lean típusú források kombinálása</span><span class="sxs-lookup"><span data-stu-id="9222c-105">Mixed mode planning - Combine discrete, process, and lean sourcing</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="9222c-106">Ez a cikk a vegyes módú tervezéssel kapcsolatban nyújt tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="9222c-106">This article provides information about mixed mode planning.</span></span> <span data-ttu-id="9222c-107">A vegyes módú tervezésben modellezheti az anyagáramláson alapuló ellátási láncot.</span><span class="sxs-lookup"><span data-stu-id="9222c-107">In mixed mode planning, you can model your supply chain based on the material flow.</span></span> <span data-ttu-id="9222c-108">A Microsoft Dynamics 365 for Finance and Operations meggyőződik arról, hogy az anyag folyamat követi a modelleket, függetlenül a kiválasztott ellátási házirendtől (kanban-ok termelési rendelések, beszerzési rendelések, feldolgozásiköteg-rendelések és átmozgatási rendelések).</span><span class="sxs-lookup"><span data-stu-id="9222c-108">Microsoft Dynamics 365 for Finance and Operations makes sure that the material flow follows your models, regardless of the supply policy that is selected (kanbans, production orders, purchase orders, batch orders, or transfer orders).</span></span> 

<span data-ttu-id="9222c-109">Kiválaszthatja a termék biztosítására szolgáló átfogó stratégiáját a termékstruktúrától függetlenül.</span><span class="sxs-lookup"><span data-stu-id="9222c-109">You can select your overall strategy for supplying a product, regardless of the product structure.</span></span>  

<span data-ttu-id="9222c-110">Például, használhat kanbanvezérlést az összeszerelés során, ahol az összeszerelési terület számára válogatják az anyagokat termelési rendelés, kanbanok, szállítások, kötegrendelés vagy bármilyen, az ellátási lánc jellemzői számára megfelelő kombináció szerint, de továbbra is teljesen átláthatja a cikkeket.</span><span class="sxs-lookup"><span data-stu-id="9222c-110">For example, you can have kanban control in the assembly, where materials are sourced for the assembly area by production orders, kanbans, transfers, batch orders, or any combination that is appropriate for the characteristics of your supply chain, but you can still have full visibility across supplies.</span></span> <span data-ttu-id="9222c-111">Ez a képesség optimalizált ellátásilánc-folyamatokat és az ellátási lánc jobb átláthatóságát eredményezi.</span><span class="sxs-lookup"><span data-stu-id="9222c-111">This capability leads to optimized supply chain processes and enhanced visibility into your supply chain.</span></span>  

<span data-ttu-id="9222c-112">Az alapütemezésben használt ellátási irányelvek részletessége a fedezeti dimenzióként engedélyezet tárolási dimenzióktól függ.</span><span class="sxs-lookup"><span data-stu-id="9222c-112">The granularity of the supply policies that are used in master scheduling depends on the storage dimensions that are enabled as coverage dimensions.</span></span> <span data-ttu-id="9222c-113">A különböző típusú helyszínek ellátásának és feltöltésének ellenőrzésére szolgáló alapütemezés engedélyezéséhez (például a gyártószint különböző gyártási egységekre történő felosztásával vagy a különböző anyagtípusokat és kész termékeket tároló raktárak elválasztásával), ajánljuk a Hely és raktár fedezeti dimenzióként való engedélyezését.</span><span class="sxs-lookup"><span data-stu-id="9222c-113">To enable master scheduling to control the replenishment and supply of different types of locations (for example, by separating the production floor for different production units, or by separating different types of material and finished goods warehouses), we recommend that you enable Site and Warehouse as coverage dimensions.</span></span> <span data-ttu-id="9222c-114">Másik lehetőségként a raktár kihagyható a fedezeti dimenziók közül.</span><span class="sxs-lookup"><span data-stu-id="9222c-114">Alternatively, Warehouse can be omitted as a coverage dimension.</span></span> <span data-ttu-id="9222c-115">Ebben az esetben a haladó raktárkezelés használata során a raktáron belüli minden mozgást a raktármunka ellenőrzi, míg a raktárak között mozgásokat ellenőrizhetik a visszavonási kanbanok.</span><span class="sxs-lookup"><span data-stu-id="9222c-115">In that case, when you use advanced warehouse management, all movements inside a warehouse are controlled by warehouse work, whereas all movements across warehouses can be controlled by withdrawal kanbans.</span></span>

## <a name="supply-policies"></a><span data-ttu-id="9222c-116">Ellátási irányelvek</span><span class="sxs-lookup"><span data-stu-id="9222c-116">Supply policies</span></span>
<span data-ttu-id="9222c-117">A Finance and Operations vegyes módú tervezése szabályozza azt, hogy miként biztosítják a termék ellátását, és az ellátás alapján miként adják ki a származtatott követelményeket (termékek fogyasztása anyagjegyzékből \[AJ, BOM\]).</span><span class="sxs-lookup"><span data-stu-id="9222c-117">Finance and Operations mixed mode planning controls how a product is supplied and, based on the supply, how derived requirements (consumption of items from a bill of materials \[BOM\]) are issued.</span></span> <span data-ttu-id="9222c-118">A rendeléstípus alapján a rendszer automatikusan biztosítja az anyagforrásokat, hogy megfeleljen a követelményeknek.</span><span class="sxs-lookup"><span data-stu-id="9222c-118">Based on the order type, the system automatically sources materials to match the requirements.</span></span>  

<span data-ttu-id="9222c-119">Az ellátási irányelvek meghatározhatók a termék szintjén vagy a követelmény által támogatott bármilyen részletességgel.</span><span class="sxs-lookup"><span data-stu-id="9222c-119">Supply policies can be defined at the product level or at any granularity that supports your requirements.</span></span> <span data-ttu-id="9222c-120">Az ellátási irányelvek részletességét Ön határozza meg az **Alapértelmezett rendelésbeállítások** oldalon.</span><span class="sxs-lookup"><span data-stu-id="9222c-120">You define the granularity of supply policies on the **Default order settings** page.</span></span>  

<span data-ttu-id="9222c-121">Az ellátási irányelvek szabályozhatók termék, cikkdimenzió (konfiguráció, szín és méret), hely és raktár szerint.</span><span class="sxs-lookup"><span data-stu-id="9222c-121">Supply policies can be controlled by product, item dimensions (configuration, color, and size), site, and warehouse.</span></span> <span data-ttu-id="9222c-122">Ez a beállítás a **Cikk fedezete** oldalon végezhető elé.</span><span class="sxs-lookup"><span data-stu-id="9222c-122">This setup is done on the **Item coverage** page.</span></span>  

<span data-ttu-id="9222c-123">Az alapértelmezett rendelési típus szabályozza, hogy mit generál a rendelés alaptervezése.</span><span class="sxs-lookup"><span data-stu-id="9222c-123">The default order type controls what order master planning generates.</span></span>  

<span data-ttu-id="9222c-124">Az ellátási lánc modelljétől függetlenül a Finance and Operations támogatja az Ön ellátási irányelveit.</span><span class="sxs-lookup"><span data-stu-id="9222c-124">Regardless of how the supply chain is modeled, Finance and Operations supports your mix of supply policies.</span></span> <span data-ttu-id="9222c-125">Lehetnek kanban forrásokból származó termelési rendelései.</span><span class="sxs-lookup"><span data-stu-id="9222c-125">You can have production orders that are sourced from kanbans.</span></span> <span data-ttu-id="9222c-126">Emellett lehet olyan kötegrendelése, amelyhez szállítással vagy kanbanokkal ellátott termék szükséges.</span><span class="sxs-lookup"><span data-stu-id="9222c-126">Alternatively, you can have a batch order that requires a product that is supplied by transfers or by kanbans.</span></span>  

<span data-ttu-id="9222c-127">A Finance and Operations garantálja, hogy az anyagáramlás követi a modellt.</span><span class="sxs-lookup"><span data-stu-id="9222c-127">Finance and Operations makes sure that the material flow follows the model.</span></span>  

<span data-ttu-id="9222c-128">Az anyagok kitárolására szolgáló raktár hozzárendelése dinamikusan történik futási idő közben az ellátási irányelvek meghatározása után.</span><span class="sxs-lookup"><span data-stu-id="9222c-128">The warehouse for picking material is assigned dynamically at run time, after the supply policy has been defined.</span></span>  

<span data-ttu-id="9222c-129">Általában a kanbanokat nem jövőbeni dátumokhoz hozzák létre, mivel a kanbanok rövid életciklusúak.</span><span class="sxs-lookup"><span data-stu-id="9222c-129">Typically, kanbans aren't created for future dates, because a kanban has a short life cycle.</span></span> <span data-ttu-id="9222c-130">Ahhoz, hogy az ellátási lánc teljesen átlátható maradjon, bevezettük a „tervezett kanban” új tervezési rendszerét, amely a származtatott követelmények kiszámításához szükséges, és segít garantálni, hogy a követelmények forrását ugyanazon logika mentén határozzák meg, mint amelyet az adott kanban létrehozásához használnak.</span><span class="sxs-lookup"><span data-stu-id="9222c-130">To maintain full visibility into the supply chain, we have introduced the new planning concept of a “planned kanban,” which is used to calculate derived requirements and helps guarantee that the requirements are sourced based on the same logic that is used when the actual kanban is created.</span></span>  

<span data-ttu-id="9222c-131">Ez a megfontolás a többi ellátásiirányelv-típus esetében is jelen van.</span><span class="sxs-lookup"><span data-stu-id="9222c-131">The same logic is present for all other supply policy types.</span></span> <span data-ttu-id="9222c-132">Így a hosszú távú anyagtervezés ugyanazon a logikán alapul, mint amit az adott rendelések esetén használni kíván a termelés és az ellátás jóváhagyása után.</span><span class="sxs-lookup"><span data-stu-id="9222c-132">Therefore, long-term materials planning is based on the same logic that you expect to run with the actual orders after production and supply are approved.</span></span>

## <a name="materials-allocation-crosssupply-policy--resource-consumption-on-boms"></a><span data-ttu-id="9222c-133">Anyagfelosztási keresztellátási irányelvek – Erőforrás-felhasználás az anyagjegyzékekben</span><span class="sxs-lookup"><span data-stu-id="9222c-133">Materials allocation crosssupply policy – Resource consumption on BOMs</span></span>
<span data-ttu-id="9222c-134">Az erőforrás-felhasználás fontos funkció.</span><span class="sxs-lookup"><span data-stu-id="9222c-134">Resource consumption is an important functionality.</span></span> <span data-ttu-id="9222c-135">Az erőforrás felhasználás lehetővé teszi a raktár számára a kitárolási anyagok dinamikus kiválasztását az ellátási irányelvek (rendelési típus) alapján, és megkönnyíti az alapadatok karbantartását.</span><span class="sxs-lookup"><span data-stu-id="9222c-135">Resource consumption enables a warehouse for picking materials to be selected dynamically, based on the supply policy (order type), and also makes maintenance of base data easier.</span></span>  

<span data-ttu-id="9222c-136">Az erőforrás-felhasználáshoz szükséges, hogy a raktárat, ahonnan kitárolják az anyagokat, a termék ellátási módja alapján rendeljék hozzá.</span><span class="sxs-lookup"><span data-stu-id="9222c-136">Resource consumption requires that the warehouse that materials are picked from be assigned based on the way that the product is supplied.</span></span> <span data-ttu-id="9222c-137">Más szavakkal futási idő közben a rendszer megtalálja a gyártáshoz szükséges erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="9222c-137">In other words, at run time, the system finds the resources that should be used for manufacturing.</span></span> <span data-ttu-id="9222c-138">Az erőforrások alapján a rendszer megtalálja a kitárolási raktárat.</span><span class="sxs-lookup"><span data-stu-id="9222c-138">Based on those resources, the system then finds the picking warehouse.</span></span>  

<span data-ttu-id="9222c-139">Az ellátási irányelvektől független munka esetében nem kell megváltoztatnia az anyagjegyzéken szereplő információt, ha az ellátás módosul.</span><span class="sxs-lookup"><span data-stu-id="9222c-139">For work that is independent of a supply policy, you don't have to change information on the BOM if the supply is changed.</span></span> <span data-ttu-id="9222c-140">Az eseti változások esetében a Finance and Operations garantálja, hogy az anyagok forrása a megfelelő raktár lesz.</span><span class="sxs-lookup"><span data-stu-id="9222c-140">For ad-hoc changes, Finance and Operations makes sure that materials are sourced from the right warehouse.</span></span>

## <a name="process-manufacturing--the-production-type"></a><span data-ttu-id="9222c-141">Folyamatgyártás – A termelési típus</span><span class="sxs-lookup"><span data-stu-id="9222c-141">Process manufacturing – The production type</span></span>
<span data-ttu-id="9222c-142">A kevert mód teljes rugalmassága érdekében azt ajánljuk, hogy minden termékhez termeléstípusú anyagjegyzéket használjon.</span><span class="sxs-lookup"><span data-stu-id="9222c-142">For full flexibility in mixed mode, we recommend that you use production type BOMs for all products.</span></span> <span data-ttu-id="9222c-143">Így termelési rendeléseket, kanbanokat, szállítási rendeléseket vagy beszerzési rendeléseket használhat a termék biztosításához.</span><span class="sxs-lookup"><span data-stu-id="9222c-143">You can then use production orders, kanbans, transfer orders, or purchase orders to supply a product.</span></span> <span data-ttu-id="9222c-144">A folyamatgyártás esetében a következő termeléstípusok közül kell választani: **receptúra**, **társtermék**, **melléktermék** vagy **tervezési cikk**.</span><span class="sxs-lookup"><span data-stu-id="9222c-144">For process manufacturing, you must use a production type of **Formula**, **Co-product**, **By-product**, or **Planning item**.</span></span> <span data-ttu-id="9222c-145">A kanbanok és a termelési rendelések nem használhatók ezen termeléstípusok esetében.</span><span class="sxs-lookup"><span data-stu-id="9222c-145">Kanbans and production orders can't be used for these production types.</span></span>



