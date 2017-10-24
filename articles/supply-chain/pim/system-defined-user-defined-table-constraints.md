---
title: "Rendszer által meghatározott és Felhasználó által meghatározott táblázat megszorítások"
description: "Ez a cikk bemutatja a táblamegszorítások két típusát termékkonfigurációs modell összetevői esetén: felhasználó és rendszer által meghatározott. A táblamegszorítások az engedélyezett attribútumkombinációk mátrixait jelölik, hol minden sor a lehetséges attribútumértékek egy készletét határozza meg."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b59452496f0ad47f1fe2ff034895a082a205dda9
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="system-defined-and-user-defined-table-constraints"></a><span data-ttu-id="51894-104">Rendszer által meghatározott és Felhasználó által meghatározott táblázat megszorítások</span><span class="sxs-lookup"><span data-stu-id="51894-104">System-defined and user-defined table constraints</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="51894-105">Ez a cikk bemutatja a táblamegszorítások két típusát termékkonfigurációs modell összetevői esetén: felhasználó és rendszer által meghatározott.</span><span class="sxs-lookup"><span data-stu-id="51894-105">This article explains the two types of table constraints for components in a product configuration model -  user-defined and system-defined.</span></span> <span data-ttu-id="51894-106">A táblamegszorítások az engedélyezett attribútumkombinációk mátrixait jelölik, hol minden sor a lehetséges attribútumértékek egy készletét határozza meg.</span><span class="sxs-lookup"><span data-stu-id="51894-106">Table constraints represent matrices of the allowed attribute combinations, where each row defines one set of possible attribute values.</span></span>

<span data-ttu-id="51894-107">A táblamegszorítások olyan attribútumok kombinációinak a mátrixát képviselik, melyek megengedettek az összetevőknek egy termék konfigurációs modellnél.</span><span class="sxs-lookup"><span data-stu-id="51894-107">Table constraints represent matrices of the combinations of attributes that are allowed for components in a product configuration model.</span></span> <span data-ttu-id="51894-108">A táblázat minden sora egy lehetséges attribútum értékhalmazt határoz meg.</span><span class="sxs-lookup"><span data-stu-id="51894-108">Each row in the table defines one set of possible attribute values.</span></span> <span data-ttu-id="51894-109">Két típusú megszorítást nevezhet meg egy termékkonfigurációs modell esetén:</span><span class="sxs-lookup"><span data-stu-id="51894-109">You can declare two types of constraints in a product configuration model:</span></span>

-   <span data-ttu-id="51894-110">**Kifejezés megszorítás** – Hozzon létre egy kifejezést, ami meghatározza az attribútumok közötti kapcsolatot így garantálva, hogy csak az összeegyeztethető értékek váljanak kiválaszthatóvá a termékkonfiguráció során.</span><span class="sxs-lookup"><span data-stu-id="51894-110">**Expression constraint** – Create an expression that defines relations between attributes to guarantee that only compatible values can be selected during product configuration.</span></span>
-   <span data-ttu-id="51894-111">**Táblamegszorítás** – Hozzon létre egy táblázatot, amely definiálja az összes kombinációt ami megengedett az attribútumok egy bizonyos halmazának.</span><span class="sxs-lookup"><span data-stu-id="51894-111">**Table constraint** – Create a table that defines all the combinations that are allowed for a specified set of attributes.</span></span> <span data-ttu-id="51894-112">Két típusú táblamegszorítás elérhető: felhasználó által meghatározott táblamegszorítás és rendszer által meghatározott táblamegszorítás.</span><span class="sxs-lookup"><span data-stu-id="51894-112">Two types of table constraints are available: user-defined table constraints and system-defined table constraints.</span></span>

<span data-ttu-id="51894-113">Ez a cikk bemutatja a felhasználó- és a rendszer által meghatározott táblamegszorításokat termékkonfigurációs modell összetevői esetén.</span><span class="sxs-lookup"><span data-stu-id="51894-113">This article describes user-defined and system-defined table constraints for components in a product configuration model.</span></span>

## <a name="user-defined-table-constraints"></a><span data-ttu-id="51894-114">Felhasználó által meghatározott táblamegszorítások</span><span class="sxs-lookup"><span data-stu-id="51894-114">User-defined table constraints</span></span>
<span data-ttu-id="51894-115">A felhasználó által meghatározott táblamegszorítás olyan típusú mátrix, amelyet arra használunk, hogy az attribútum típusok által meghatározott attribútum értékek kombinációit leírjuk.</span><span class="sxs-lookup"><span data-stu-id="51894-115">A user-defined table constraint is a type of matrix that is used to describe the combinations of attribute values that are defined by attribute types.</span></span> <span data-ttu-id="51894-116">Például, ha hangszórókat gyárt létrehozhat oszlopokat a hangszóró borításának, illetve az elülső rácsnak a felhasználó által meghatározott táblamegszorításokkal.</span><span class="sxs-lookup"><span data-stu-id="51894-116">For example, if you produce speakers, you can include columns for the cabinet finish and the front grill in the user-defined table constraint.</span></span> <span data-ttu-id="51894-117">A hangszóró borítás attribútum típusának négy, az elülső rács attribútum típusának három értéke van.</span><span class="sxs-lookup"><span data-stu-id="51894-117">The attribute type for the cabinet finish has four values, and the attribute type for the front grill has three values.</span></span> <span data-ttu-id="51894-118">Így amennyiben nem használ megszorításokat 4 x 3 azaz 12 lehetséges kombináció létezik.</span><span class="sxs-lookup"><span data-stu-id="51894-118">Therefore, if constraints aren't used, there are 4 × 3 = 12 possible combinations.</span></span> <span data-ttu-id="51894-119">Azonban ebben a példában csak hat kombináció megengedett, ahogy az alábbi táblázat is mutatja.</span><span class="sxs-lookup"><span data-stu-id="51894-119">However, in this example, only six combinations are allowed, as shown in the following table.</span></span> <span data-ttu-id="51894-120">Ez az információ a **Megengedett kombinációk** lapon **Táblamegszorítás szerkesztése** oldalon található.</span><span class="sxs-lookup"><span data-stu-id="51894-120">This information is displayed on the **Allowed combinations** tab on the **Edit table constraint** page.</span></span>

| <span data-ttu-id="51894-121">Hangszóró borítása</span><span class="sxs-lookup"><span data-stu-id="51894-121">Cabinet finish</span></span> | <span data-ttu-id="51894-122">Elülső rács</span><span class="sxs-lookup"><span data-stu-id="51894-122">Front grill</span></span> |
|----------------|-------------|
| <span data-ttu-id="51894-123">Fekete</span><span class="sxs-lookup"><span data-stu-id="51894-123">Black</span></span>          | <span data-ttu-id="51894-124">Fekete</span><span class="sxs-lookup"><span data-stu-id="51894-124">Black</span></span>       |
| <span data-ttu-id="51894-125">Fekete</span><span class="sxs-lookup"><span data-stu-id="51894-125">Black</span></span>          | <span data-ttu-id="51894-126">Fém</span><span class="sxs-lookup"><span data-stu-id="51894-126">Metal</span></span>       |
| <span data-ttu-id="51894-127">Tölgyfa</span><span class="sxs-lookup"><span data-stu-id="51894-127">Oak</span></span>            | <span data-ttu-id="51894-128">Fekete</span><span class="sxs-lookup"><span data-stu-id="51894-128">Black</span></span>       |
| <span data-ttu-id="51894-129">Rózsafa</span><span class="sxs-lookup"><span data-stu-id="51894-129">Rosewood</span></span>       | <span data-ttu-id="51894-130">Fehér</span><span class="sxs-lookup"><span data-stu-id="51894-130">White</span></span>       |
| <span data-ttu-id="51894-131">Fehér</span><span class="sxs-lookup"><span data-stu-id="51894-131">White</span></span>          | <span data-ttu-id="51894-132">Fekete</span><span class="sxs-lookup"><span data-stu-id="51894-132">Black</span></span>       |
| <span data-ttu-id="51894-133">Fehér</span><span class="sxs-lookup"><span data-stu-id="51894-133">White</span></span>          | <span data-ttu-id="51894-134">Fehér</span><span class="sxs-lookup"><span data-stu-id="51894-134">White</span></span>       |

<span data-ttu-id="51894-135">A felhasználó által meghatározott táblamegszorításokat a statikus beviteli táblázat határozza meg, amely ugyanúgy működik, mint egy vélemény megszorítás.</span><span class="sxs-lookup"><span data-stu-id="51894-135">User-defined table constraints are defined by static table input that works the same way as an expression constraint.</span></span> <span data-ttu-id="51894-136">A felhasználó által definiált táblamegszorítás használatának előnye, hogy a táblák könnyebben létrehozhatóak, értelmezhetőek és karbantarthatóak, mint a hosszú kifejezés megszorítások.</span><span class="sxs-lookup"><span data-stu-id="51894-136">When you use a user-defined table constraint, the advantage is that tables are often easier to create, understand, and maintain than long expression constraints.</span></span>

## <a name="system-defined-table-constraints"></a><span data-ttu-id="51894-137">Rendszer által meghatározott táblamegszorítások</span><span class="sxs-lookup"><span data-stu-id="51894-137">System-defined table constraints</span></span>
<span data-ttu-id="51894-138">A rendszer által definiált táblamegszorítás dinamikus leképezést hoz létre egy attribútum típus és a táblázat egy mezője között.</span><span class="sxs-lookup"><span data-stu-id="51894-138">A system-defined table constraint creates a dynamic mapping between an attribute type and a field in a table.</span></span> <span data-ttu-id="51894-139">Amikor egy termékkonfigurációs modell rendszer által meghatározott tábla megszorítást tartalmaz, a leképezés garantálja, hogy a táblázatban szereplő adatok jelenjenek meg az attribútum típusok értékei helyett.</span><span class="sxs-lookup"><span data-stu-id="51894-139">When a system-defined table constraint is included in a product configuration model, the mapping guarantees that the data in the table is shown instead of the values of the attribute type.</span></span> <span data-ttu-id="51894-140">Ennek eredménye egy dinamikus megszorítás, mivel a táblázat elemei módosíthatóak (például más modulok által).</span><span class="sxs-lookup"><span data-stu-id="51894-140">The result is a dynamic constraint, because the table contents can be modified (for example, by other modules).</span></span>  

<span data-ttu-id="51894-141">Rendszer által definiált táblamegszorítás létrehozásakor válasszon ki egy táblázatot, tetszés szerint megadhatja a használni kívánt lekérdezést, majd társítsa az attribútum típusokat a kiválasztott táblázatban szereplő mezőkhöz.</span><span class="sxs-lookup"><span data-stu-id="51894-141">When you create a system-defined table constraint, you select a table, optionally define the query to use, and then associate attribute types to the fields in the selected table.</span></span> <span data-ttu-id="51894-142">A mezőtípusoknak meg kell egyezniük az attribútum típusokkal.</span><span class="sxs-lookup"><span data-stu-id="51894-142">The types of fields must match the types of attribute types.</span></span>  

<span data-ttu-id="51894-143">Mielőtt egy táblamegszorítás érvénybe lépne a termékkonfigurációs modellen, a táblamegszorítást tartalmaznia kell a modell összetevők egy megszorításának. Az eljárás az, hogy új megszorítást kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="51894-143">Before a table constraint can take effect on a product configuration model, the table constraint must be included in a constraint on one of the model's components.</span></span> <span data-ttu-id="51894-144">Ehhez válassza ki a táblázat megszorítás típusát, majd a táblázat megszorítás használni kívánt definícióját.</span><span class="sxs-lookup"><span data-stu-id="51894-144">The procedure is to create a new constraint, select the table constraint type, and then select the table constraint definition to use.</span></span> <span data-ttu-id="51894-145">Végül a táblamegszorítás összes mezőjének kapcsolódnia kell a termékkonfigurációs modell attribútumaihoz.</span><span class="sxs-lookup"><span data-stu-id="51894-145">Finally, all fields in the table constraint must be mapped to attributes in the product configuration model.</span></span>

<a name="see-also"></a><span data-ttu-id="51894-146">Lásd még</span><span class="sxs-lookup"><span data-stu-id="51894-146">See also</span></span>
--------

[<span data-ttu-id="51894-147">Termékkonfigurálási modellek alapfogalmai</span><span class="sxs-lookup"><span data-stu-id="51894-147">Key concepts in product configuration models</span></span>](product-configuration-models.md)



