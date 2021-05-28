---
title: Az alaptervezés tervezett rendeléseket hoz létre a látszólagos termékekhez
description: Tervezett rendeléseket jönnek létre a látszólagos termékekhez a mestertervezés futtatása után.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: anderso
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ea4bdb3729d163126234e02524cef331051cd48
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026582"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a><span data-ttu-id="88bab-103">Az alaptervezés tervezett rendeléseket hoz létre a látszólagos termékekhez</span><span class="sxs-lookup"><span data-stu-id="88bab-103">Master planning generates planned orders for phantom products</span></span>

<span data-ttu-id="88bab-104">Tudásbáziscikk száma: 4614729</span><span class="sxs-lookup"><span data-stu-id="88bab-104">KB number: 4614729</span></span>

## <a name="symptoms"></a><span data-ttu-id="88bab-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="88bab-105">Symptoms</span></span>

<span data-ttu-id="88bab-106">Tervezett rendeléseket jönnek létre a látszólagos termékekhez a mestertervezés futtatása után.</span><span class="sxs-lookup"><span data-stu-id="88bab-106">Planned orders are generated for phantom products after master planning is run.</span></span>

## <a name="resolution"></a><span data-ttu-id="88bab-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="88bab-107">Resolution</span></span>

<span data-ttu-id="88bab-108">A kiadott termékek **Látszólagos** beállításának beállítása határozza meg az anyagjegyzék alapértelmezett sortípusát.</span><span class="sxs-lookup"><span data-stu-id="88bab-108">The setting of the **Phantom** option for released products determines the default line type on the bill of material (BOM).</span></span> <span data-ttu-id="88bab-109">Ha a **Látszólagos** beállítás értéke *Igen*, a rendszer továbbra is létrehozza a cikk tervezett rendeléseit, de a **Közvetlenül származtatott követelmény** beállítása minden tervezett rendelésnél *Igen* lesz.</span><span class="sxs-lookup"><span data-stu-id="88bab-109">When the **Phantom** option is set to *Yes*, the system will still create planned orders for the item, but the **Directly derived requirement** option for each planned order will be set to *Yes*.</span></span> <span data-ttu-id="88bab-110">Így a tervezett termelési rendelést nem lehet saját magában megerősíteni.</span><span class="sxs-lookup"><span data-stu-id="88bab-110">Therefore, the planned production order can't be firmed on its own.</span></span> <span data-ttu-id="88bab-111">Ehelyett a rendszer mindig automatikusan hozzáadja a rendelést a szülő termelési rendelés megerősítésekor.</span><span class="sxs-lookup"><span data-stu-id="88bab-111">Instead, it will always be automatically included when the parent production order is firmed.</span></span> <span data-ttu-id="88bab-112">Továbbá a tervezett látszólagos rendelés anyagjegyzéksorai a szülő termelési rendelés anyagjegyzékében is szerepelni fognak.</span><span class="sxs-lookup"><span data-stu-id="88bab-112">Additionally, the BOM lines of the planned phantom order will be included in the BOM of the parent production order.</span></span>
