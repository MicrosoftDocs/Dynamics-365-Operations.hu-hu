---
title: "Készlethelyek"
description: "A készlethelyek az alapvető raktározással (WMS I) együtt alkalmazandóak, a cikkek tárolási helyének és a cikkek WMS I raktárból történő felvételének meghatározásához."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSLocation
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 6d40069b4116d38f25a12340df0d939afa2866e7
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="inventory-locations"></a><span data-ttu-id="0c887-103">Készlethelyek</span><span class="sxs-lookup"><span data-stu-id="0c887-103">Inventory locations</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="0c887-104">A készlethelyek az alapvető raktározással (WMS I) együtt alkalmazandóak, a cikkek tárolási helyének és a cikkek WMS I raktárból történő felvételének meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="0c887-104">Inventory locations are used with basic warehousing (WMS I) to determine where items are stored and where items are picked from in a WMS I warehouse.</span></span>

<span data-ttu-id="0c887-105">Ez a témakör a Készletkezelés modul szolgáltatásaira vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="0c887-105">This topic applies to features in the Inventory management module.</span></span> <span data-ttu-id="0c887-106">Nem vonatkozik a Raktárkezelés modul funkcióira..</span><span class="sxs-lookup"><span data-stu-id="0c887-106">It does not apply to features in the Warehouse management module.</span></span>

<span data-ttu-id="0c887-107">A hely megnevezés azt a helyet jelenti, ahol a cikkek tárolása és kivétele történik.</span><span class="sxs-lookup"><span data-stu-id="0c887-107">The term location refers to the place that items are stored and drawn from.</span></span>

<span data-ttu-id="0c887-108">Minden egyes hely esetén meg lehet adni a cikk tárolási helyét is.</span><span class="sxs-lookup"><span data-stu-id="0c887-108">For each location, the place where the item is inserted can also be specified.</span></span> <span data-ttu-id="0c887-109">Alapértelmezés szerint ezek megegyeznek.</span><span class="sxs-lookup"><span data-stu-id="0c887-109">By default, they are the same.</span></span> <span data-ttu-id="0c887-110">A cikkek kivétele és betétele általában ugyanazon a helyen történik, de nem mindig.</span><span class="sxs-lookup"><span data-stu-id="0c887-110">Items are usually inserted and drawn from the same side of a location, but not always.</span></span> <span data-ttu-id="0c887-111">Például az élő tároló állványoknál a tételek behelyezése az egyik folyosón történik, a kivétel azonban egy másikon.</span><span class="sxs-lookup"><span data-stu-id="0c887-111">For example, items that are stored in live storage racks are inserted from one aisle and drawn from another.</span></span> <span data-ttu-id="0c887-112">A fő bemenetet a hely nevével adják meg, amelyet általában a koordinátái határoznak meg: raktár, folyosó, állvány, polc, és rekesz.</span><span class="sxs-lookup"><span data-stu-id="0c887-112">The main input is given by a location name, which is usually determined by its coordinates: warehouse, aisle, rack, shelf, and bin.</span></span> <span data-ttu-id="0c887-113">Ezt a nevet vagy azonosítót manuálisan vagy a helykoordináták alapján lehet bevinni – például a 01-02-03-4 az 1-es folyosót, 2-es állványt, 3-as polcot, és a 4-es rekeszt jelöli a Készlethelyek képernyőn.</span><span class="sxs-lookup"><span data-stu-id="0c887-113">This name or ID can be entered manually or generated from the location coordinates—for example, 01-02-03-4 for aisle 1, rack 2, shelf 3, bin 4 in the Inventory locations page.</span></span>
<span data-ttu-id="0c887-114">Helytulajdonságok</span><span class="sxs-lookup"><span data-stu-id="0c887-114">Location properties</span></span>

<span data-ttu-id="0c887-115">Egy hely a következő jellemzőkkel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="0c887-115">A location has the following characteristics:</span></span>
-   <span data-ttu-id="0c887-116">Méret (magasság, szélesség, mélység, és ezzel terjedelem)</span><span class="sxs-lookup"><span data-stu-id="0c887-116">Size (height, width, depth, and thereby volume)</span></span>
-   <span data-ttu-id="0c887-117">Raktár, folyosó, állvány, polc és rekesz pozíciója.</span><span class="sxs-lookup"><span data-stu-id="0c887-117">Warehouse, aisle, rack, shelf, and bin position</span></span>
-   <span data-ttu-id="0c887-118">Hely típusa (ömlesztett tárolóhely, kitárolási hely, érkeztetési terület, kiszállítási területre, termelési bemeneti hely, vizsgálat helye vagy kanban szupermarket)</span><span class="sxs-lookup"><span data-stu-id="0c887-118">Location type (bulk location, picking location, inbound dock, outbound dock, production input location, inspection location, or kanban supermarket)</span></span>

<span data-ttu-id="0c887-119">Online rendszereknél ellenőrzőszövegekkel ellenőrizhető, hogy a kezelő a megfelelő helyet választotta-e ki az adott cikkhez.</span><span class="sxs-lookup"><span data-stu-id="0c887-119">Check text can be used in online systems to verify that the operator has selected the correct location for a specific item.</span></span> <span data-ttu-id="0c887-120">Az ellenőrzőszöveget létre lehet hozni kézzel vagy egy alapértelmezésnek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="0c887-120">This check text can be created manually or by default.</span></span>

## <a name="sort-codes"></a><span data-ttu-id="0c887-121">Rendezési kódok</span><span class="sxs-lookup"><span data-stu-id="0c887-121">Sort codes</span></span>
<span data-ttu-id="0c887-122">A rendezési kódok segítségével lehet optimalizálni a válogatási sorok kezelését, amelyek részletezik a készletből kivenni kívánt cikkek szükséges adatait, így a válogatás sorrendjét is.</span><span class="sxs-lookup"><span data-stu-id="0c887-122">Use sort codes to optimize the handling of picking lines, which describe the information that is required for picking items from inventory, including the picking order.</span></span> <span data-ttu-id="0c887-123">A rendezési kódokat a folyosó és más koordináták alapján lehet megadni, vagy manuálisan a helyhez lehet őket rendelni.</span><span class="sxs-lookup"><span data-stu-id="0c887-123">Sort codes can be specified by the aisle and other coordinates, or assigned manually for the location.</span></span>

## <a name="blocked-locations"></a><span data-ttu-id="0c887-124">Blokkolt helyek</span><span class="sxs-lookup"><span data-stu-id="0c887-124">Blocked locations</span></span>
<span data-ttu-id="0c887-125">Időnként jelezheti a helyek lezárását, például hogy el lehessen végezni a javításokat.</span><span class="sxs-lookup"><span data-stu-id="0c887-125">Occasionally, you might want to indicate that a location is blocked for a period of time, for example, to allow for repairs.</span></span> <span data-ttu-id="0c887-126">Más esetekben előfordulhat, hogy csak a bejövő vagy a kimenő forgalom blokkolását szeretné jelezni.</span><span class="sxs-lookup"><span data-stu-id="0c887-126">At other times, you may want to indicate blocking of only the input or only output.</span></span>

## <a name="tree-structure"></a><span data-ttu-id="0c887-127">Fastruktúra</span><span class="sxs-lookup"><span data-stu-id="0c887-127">Tree structure</span></span>

<span data-ttu-id="0c887-128">A Készlethelyek lapon tekintheti meg a raktárelrendezést egy fastruktúrában a készlethelyek koordinátái alapján, egy meghatározott kijelzési formátumban.</span><span class="sxs-lookup"><span data-stu-id="0c887-128">In the Inventory locations page, you can view the warehouse layout in a tree structure based on the coordinates of inventory locations, in a defined display format.</span></span>

## <a name="maintain-inventory-locations-via-the-warehouse-form"></a><span data-ttu-id="0c887-129">Készlethelyek karbantartása a raktári képernyőn keresztül</span><span class="sxs-lookup"><span data-stu-id="0c887-129">Maintain inventory locations via the warehouse form</span></span>

<span data-ttu-id="0c887-130">Lehetséges a helyek másolása egyik raktárból a másikba, és egy varázsló segítségével helyeket is hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="0c887-130">It is possible to copy locations from one warehouse to another and to create locations via a wizard.</span></span> <span data-ttu-id="0c887-131">Mielőtt futtatná a varázslót, gondoskodnia kell arról, hogy meg vannak adva az alapértelmezett helynevek a Raktár lapon.</span><span class="sxs-lookup"><span data-stu-id="0c887-131">Before you run the wizard you should make sure that you have defined the default location names on the Warehouse page.</span></span>



<a name="see-also"></a><span data-ttu-id="0c887-132">Lásd még</span><span class="sxs-lookup"><span data-stu-id="0c887-132">See also</span></span>
--------

[<span data-ttu-id="0c887-133">Új raktárelrendezés létrehozása (Feladat-útmutató)</span><span class="sxs-lookup"><span data-stu-id="0c887-133">Create a new warehouse layout (Task guide)</span></span>](tasks/create-new-warehouse-layout.md)

