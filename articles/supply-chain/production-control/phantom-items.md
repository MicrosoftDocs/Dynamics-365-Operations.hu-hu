---
title: Látszólagos cikkek
description: Ez a témakör részletesen leírja, hogyan használható a Látszólagos sortípus egy anyagjegyzék (BOM) sorainál, illetve egy képletben Dynamics 365 Supply Chain Management rendszerben.
author: ShylaThompson
manager: AnnBe
ms.date: 06/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.search.region: Global
ms.author: shylaw
ms.search.validfrom: ''
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 7c39b0ac2eb8a2293c828fee23ed6a78cb5fe2c9
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250009"
---
# <a name="phantom-items"></a><span data-ttu-id="c272c-103">Látszólagos cikkek</span><span class="sxs-lookup"><span data-stu-id="c272c-103">Phantom items</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c272c-104">Ez a témakör részletesen leírja, hogyan használható a Látszólagos sortípus egy anyagjegyzék (BOM) sorainál, illetve egy képletben.</span><span class="sxs-lookup"><span data-stu-id="c272c-104">This topic describes, in detail, how the Phantom line type can be used for the lines of a bill of materials (BOM) and a formula.</span></span> <span data-ttu-id="c272c-105">A következő példában (a) a H termék és F, valamint G rész anyagjegyzéke, míg (b) a H termék és F rész útvonallapja.</span><span class="sxs-lookup"><span data-stu-id="c272c-105">In the following illustration, (a) is the BOM for product H and parts F and G, and (b) is the route sheet for products H and part F.</span></span>

![H termék és F rész](media/product-H-part-F.png)


<span data-ttu-id="c272c-107">Ez az ábra egy anyagjegyzék-struktúra példáját mutatja be két szinten.</span><span class="sxs-lookup"><span data-stu-id="c272c-107">This illustration shows an example of a BOM structure in two levels.</span></span> <span data-ttu-id="c272c-108">A H késztermék egy gépösszszerelés termékét jelöli.</span><span class="sxs-lookup"><span data-stu-id="c272c-108">Finished product H represents a product for a machine assembly.</span></span> <span data-ttu-id="c272c-109">A gép két részből áll: egy elektromos egységből (F), amelynek két összetevője van (A és B) és csomagolóanyagok csoportjából (G), amelynek szintén két összetevője van (C és D).</span><span class="sxs-lookup"><span data-stu-id="c272c-109">The machine assembly consists of two parts, an electrical unit (F) that has two materials (A and B) and a group of packaging materials (G) that also has two materials (C and D).</span></span> <span data-ttu-id="c272c-110">Egy másik anyagot (E) is felhasználnak a gép általános összeszerelése során.</span><span class="sxs-lookup"><span data-stu-id="c272c-110">Another material (E) is used during the general assembly of the machine.</span></span>

![H termék és F rész](media/product-H-part-B.png)

<span data-ttu-id="c272c-112">Az előző ábra mutatja be a H termék Műszaki anyagjegyzékét. Ez a szerkezet jó áttekintést biztosít a teljes gépösszeszerelés részeiről és összetevőiről.</span><span class="sxs-lookup"><span data-stu-id="c272c-112">The preceding illustration represents the Engineering BOM for product H. This structure provides a good overview of the parts and components of the overall machine assembly.</span></span> <span data-ttu-id="c272c-113">Azonban annak ellenére, hogy a terméktervezők valószínűleg így szeretnék látni az anyagjegyzéket, előfordulhat, hogy ez a szerkezet nem jelöli megfelelően a gép üzemben történő összeszerelését.</span><span class="sxs-lookup"><span data-stu-id="c272c-113">However, although product designers might prefer to see the BOM represented in this way, this structure might not correctly represent the way that the machine is built on the shop floor.</span></span> 

<span data-ttu-id="c272c-114">Az iménti Műszaki anyagjegyzék például azt jelzi, hogy az F elektromos egység külön kerül összeszerelésre egy külön munkarendelés keretében.</span><span class="sxs-lookup"><span data-stu-id="c272c-114">For example, the Engineering BOM in the preceding illustration indicates that electrical unit F is assembled as a separate part on a separate work order.</span></span> <span data-ttu-id="c272c-115">Azonban az üzemben előfordulhat, hogy optimálisabb lenne az elektromos egység összeszerelését a teljes gépösszeszerelés részeként értelmezni egy külön munkarendelés helyett.</span><span class="sxs-lookup"><span data-stu-id="c272c-115">However, on the shop floor, it might be judged more optimal to assemble the electrical unit as part of the overall machine assembly, not as a separate work order.</span></span>

<span data-ttu-id="c272c-116">Ez a Műszaki anyagjegyzék azt is jelzi, hogy a G egy külön rész.</span><span class="sxs-lookup"><span data-stu-id="c272c-116">This Engineering BOM also indicates that part G is a separate part.</span></span> <span data-ttu-id="c272c-117">Ugyanakkor ebben a struktúrában a G rész nem fizikai részte utal, hanem csomagolóanyagok egy gyűjteményére.</span><span class="sxs-lookup"><span data-stu-id="c272c-117">However, in this structure, part G doesn’t represent a physical part but a collection of packaging materials.</span></span> 

<span data-ttu-id="c272c-118">Ebből következően annak ellenére, hogy egy Műszaki anyagjegyzék rendkívül értékes egy termék tervezése és a terv karbantartása során, lehet, hogy nem a leglogikusabb a termék gyártásának végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="c272c-118">Therefore, although an Engineering BOM provides great value for the design of a product and maintenance of that design, it might not be the most logical way to support the manufacturing execution process of the product.</span></span> <span data-ttu-id="c272c-119">Ezzel szemben a Gyártási anyagjegyzék egy termék előállítására szolgáló legjobb módszernek felel meg.</span><span class="sxs-lookup"><span data-stu-id="c272c-119">By contrast, a Manufacturing BOM represents the best way to build a product.</span></span>

<span data-ttu-id="c272c-120">Az alábbi ábra bemutatja, hogy miként változik át az előző Műszaki anyagjegyzék egy Gyártási anyagjegyzékké.</span><span class="sxs-lookup"><span data-stu-id="c272c-120">The following illustration shows how the preceding Engineering BOM is transitioned into a Manufacturing BOM.</span></span> <span data-ttu-id="c272c-121">Ezen az ábrán az (a) a H termékhez tartozó anyagjegyzék, a b pedig a H termék útvonallapja.</span><span class="sxs-lookup"><span data-stu-id="c272c-121">In this illustration, (a) is the BOM for product H, and b is the route sheet for product H.</span></span>

<span data-ttu-id="c272c-122">Ebben a szerkezetben láthatja, hogy nem értelmezhetők az F és G részek, és az anyagok, amelyekből ezek a részek állnak, kiemelésre kerültek az anyagjegyzék következő szintjére.</span><span class="sxs-lookup"><span data-stu-id="c272c-122">In this structure, you can see that there is no notion of parts F and G, and the materials that these parts consist of have been elevated to the next BOM level.</span></span> 

<span data-ttu-id="c272c-123">A Műszaki anyagjegyzék két műveletlapot is tartalmazott, ellentétben a Gyártási anyagjegyzékkel, amelynek csak egy műveletlapja van.</span><span class="sxs-lookup"><span data-stu-id="c272c-123">Unlike the Engineering BOM, which had two operations sheets, the Manufacturing BOM has only one operations sheet.</span></span> <span data-ttu-id="c272c-124">A G részhez kapcsolt csomagolási műveletet szintén kiemelte a rendszer, és az most a H termék műveleti lapjának részévé vált. Az első művelet az elektromos egység összeszerelése.</span><span class="sxs-lookup"><span data-stu-id="c272c-124">The packaging operation that was linked to part G has also been elevated and is now part of the operations sheet for product H. The assembly of the electrical unit is the first operation.</span></span> <span data-ttu-id="c272c-125">Ez a rendelés jónak tűnik, mert ezt az egységet használja a rendszer a következő műveletben, amely a gépösszeszerelés.</span><span class="sxs-lookup"><span data-stu-id="c272c-125">This order makes good sense, because this unit is used in the next operation, which is the machine assembly.</span></span> <span data-ttu-id="c272c-126">Az utolsó művelet a csomagolási művelet, amely két csomagolóanyagot (C és D) használ fel.</span><span class="sxs-lookup"><span data-stu-id="c272c-126">The last operation is the packaging operation, which consumes two packing materials (C and D).</span></span>

<span data-ttu-id="c272c-127">Az átmenet a műszaki anyagjegyzék és a gyártási anyagjegyzék közötti a Phantom anyagjegyzék sortípuson keresztül engedélyezhető.</span><span class="sxs-lookup"><span data-stu-id="c272c-127">The transition between the Engineering BOM and the Manufacturing BOM is enabled through the Phantom BOM line type.</span></span> <span data-ttu-id="c272c-128">Amint arra a „látszólagos” kifejezés is utal, az F és G részek eltűntek a két anyagjegyzéktípus közötti átmenet során.</span><span class="sxs-lookup"><span data-stu-id="c272c-128">As the term “phantom” indicates, parts F and G have disappeared during the transition between the two BOM types.</span></span> <span data-ttu-id="c272c-129">Ebben a példában a Látszólagos sortípust alkalmazza a rendszer az F és G részekre a Műszaki anyagjegyzékben.</span><span class="sxs-lookup"><span data-stu-id="c272c-129">In this example, the Phantom line type is applied to the BOM lines for parts F and G in the Engineering BOM.</span></span> <span data-ttu-id="c272c-130">Amikor létrejön egy termelési vagy kötegrendelés, a rendszer a Műszaki anyagjegyzéket bemásolja a termelési vagy kötegrendelésbe.</span><span class="sxs-lookup"><span data-stu-id="c272c-130">When a production or batch order is created, the Engineering BOM is copied to the production or batch order.</span></span> <span data-ttu-id="c272c-131">Ezután, a rendelés becslésekor, végbemegy az átmenet a Műszaki anyagjegyzékből a Gyártási anyagjegyzékbe, ahogyan azt az előző ábrákon láthatta.</span><span class="sxs-lookup"><span data-stu-id="c272c-131">Then, when the order is estimated, the transition from the Engineering BOM to the Manufacturing BOM occurs, as shown in the preceding illustrations.</span></span> <span data-ttu-id="c272c-132">A második ábra műveleti lapjáról a C és D csomagolóanyagok meg vannak adva a művelethez.</span><span class="sxs-lookup"><span data-stu-id="c272c-132">From the operations sheet in the second illustration, packaging materials C and D are input for the operation.</span></span> 

## <a name="multilevel-phantom-bom-structures"></a><span data-ttu-id="c272c-133">Többszintű látszólagos anyagjegyzék-struktúrák</span><span class="sxs-lookup"><span data-stu-id="c272c-133">Multilevel phantom BOM structures</span></span>
<span data-ttu-id="c272c-134">A Látszólagos sortípus többszintű anyagjegyzék-struktúráknál is használható, a következő ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="c272c-134">The Phantom line type can be used in multilevel BOM structures, as shown in the following illustration.</span></span> <span data-ttu-id="c272c-135">Ebben a példában (a) a G termék anyagjegyzéke, míg (b) az E és F rész, valamint a G termék útvonallapja.</span><span class="sxs-lookup"><span data-stu-id="c272c-135">In this illustration, (a) is the BOM for product G, and (b) is the route sheet for parts E and F and product G.</span></span> 

![G termék és F rész útvonallapokkal](media/product-G-route-sheet-G.png)


<span data-ttu-id="c272c-137">A következő ábrán az eredményként jelentkező gyártási anyagjegyzék és útvonallap látható, amennyiben az E és F részek anyagjegyzéksorai úgy vannak konfigurálva, hogy a sortípus a Látszólagos.</span><span class="sxs-lookup"><span data-stu-id="c272c-137">The following illustration shows the resulting Manufacturing BOM and route sheet if the BOM lines for parts E and F are configured so that the line type is Phantom.</span></span> <span data-ttu-id="c272c-138">Ezen az ábrán az (a) a G termékhez tartozó anyagjegyzék, a (b) pedig a G termék útvonallapja.</span><span class="sxs-lookup"><span data-stu-id="c272c-138">In this illustration, (a) is the BOM for product G, and (b) is the route sheet for product G.</span></span>

![G termék](media/product-G.png)


## <a name="phantom-and-route-network"></a><span data-ttu-id="c272c-140">Látszólagos anyagjegyzék és útvonalhálózat</span><span class="sxs-lookup"><span data-stu-id="c272c-140">Phantom and route network</span></span>
<span data-ttu-id="c272c-141">A látszólagos anyagjegyzékek olyan anyagjegyzéknél is használhatók, amely rendelkezik útvonalhálózattal.</span><span class="sxs-lookup"><span data-stu-id="c272c-141">Phantom BOMs can also be used for a BOM that has a route network.</span></span> <span data-ttu-id="c272c-142">Az útvonalhálózatoknál egy vagy több művelet párhuzamosan futhat.</span><span class="sxs-lookup"><span data-stu-id="c272c-142">In a route network, one or more operations run in parallel.</span></span> <span data-ttu-id="c272c-143">A következő ábra bemutat egy példát egy olyan útvonalhálózatról, amelyet többszintű anyagjegyzékben használnak.</span><span class="sxs-lookup"><span data-stu-id="c272c-143">The following illustration shows an example of a route network that is used in a multilevel BOM.</span></span> <span data-ttu-id="c272c-144">Ebben a példában az (a) a G termék és F rész anyagjegyzéke, a (b) a G termék és F rész az útvonallapja, ahol szerepel útvonalhálózat.</span><span class="sxs-lookup"><span data-stu-id="c272c-144">In this illustration, (a) is the BOM for product G and part F, and (b) is the route sheet for product G and part F, which has a route network.</span></span>

![G termék és F rész](media/product-G-part-F.png)


<span data-ttu-id="c272c-146">A következő példában (a) a G termék és F rész anyagjegyzéke, míg (b) a G termék és F rész útvonallapja.</span><span class="sxs-lookup"><span data-stu-id="c272c-146">In the following illustration, (a) is the BOM for product G and part F, and (b) is the route sheet for product G and part F.</span></span>

![G termék és F rész útvonallapokkal](media/product-G-part-F-with-route-sheet.png)
