---
title: A gyártott cikk költségeinek megjelenítése
description: A legyártott cikk állandó költségei a művelet beállítási idejét és az állandó mennyiséggel vagy állandó selejtmennyiséggel megadott összetevőket tükrözik.
author: AndersGirke
manager: tfehr
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: b955bfe4f26620724d297691e052edaca239937a
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201985"
---
# <a name="display-charges-for-a-manufactured-item"></a><span data-ttu-id="2f2ce-103">A gyártott cikk költségeinek megjelenítése</span><span class="sxs-lookup"><span data-stu-id="2f2ce-103">Display charges for a manufactured item</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2f2ce-104">A legyártott cikk állandó költségei a művelet beállítási idejét és az állandó mennyiséggel vagy állandó selejtmennyiséggel megadott összetevőket tükrözik.</span><span class="sxs-lookup"><span data-stu-id="2f2ce-104">The constant costs of a manufactured item reflect the operation setup times and the components that have a constant quantity or a constant scrap amount.</span></span>

<span data-ttu-id="2f2ce-105">A cikk költségének kiszámított összege megjeleníthető a cikk egységenkénti költségével.</span><span class="sxs-lookup"><span data-stu-id="2f2ce-105">The calculated amount of an item's charges can be displayed with the item's unit costs.</span></span> <span data-ttu-id="2f2ce-106">A költségek azonban néha két külön mező formájában jelennek meg, és nem szerepelnek a cikk egységköltségeiben.</span><span class="sxs-lookup"><span data-stu-id="2f2ce-106">However, the charges are sometimes displayed as separate fields, and they are not included in the item's unit costs.</span></span> <span data-ttu-id="2f2ce-107">Amikor a költségek külön mezőkben jelennek meg, az egyik mező a költségek teljes összegét, a második mező pedig a költségszámítási adag méretét jeleníti meg, amelyet az összeg amortizációjához használ a rendszer.</span><span class="sxs-lookup"><span data-stu-id="2f2ce-107">When the charges appear as separate fields, one field displays the total amount of charges, and another field displays the costing lot size that is used to amortize the amount.</span></span> <span data-ttu-id="2f2ce-108">A Cikk ára lap például a költségeket két külön mezőként jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="2f2ce-108">The Item price page, for example, displays the charges as two separate fields.</span></span> <span data-ttu-id="2f2ce-109">A Teljesített lap azonban a cikk teljes egységenkénti költségét jeleníti meg, és az egységköltségben szerepelnek az amortizált költségek.</span><span class="sxs-lookup"><span data-stu-id="2f2ce-109">However, the Complete page displays the item's total cost per unit, and the amortized costs are included in the unit costs.</span></span>

<span data-ttu-id="2f2ce-110">A legyártott cikkeknél a költségek az elszámolóárak szempontjából mindig szerepelnek a cikk egységköltségében.</span><span class="sxs-lookup"><span data-stu-id="2f2ce-110">The charges for a manufactured item are always included in the item's unit cost for standard cost purposes.</span></span> <span data-ttu-id="2f2ce-111">A tervezett költségek szempontjából választhatóan szerepeltethetők.</span><span class="sxs-lookup"><span data-stu-id="2f2ce-111">They can optionally be included for planned cost purposes.</span></span> <span data-ttu-id="2f2ce-112">A költségszámítási verzióban alkalmazott szabály érvényesíti a költségeknek a legyártott cikk költségében való szerepeltetését.</span><span class="sxs-lookup"><span data-stu-id="2f2ce-112">A policy in the costing version enforces the inclusion of charges in the cost of a manufactured item.</span></span> <span data-ttu-id="2f2ce-113">A cikk költségrekordjának aktiválása frissíti a cikk alapköltségadataihoz tartozó költségeket, amely a Cikk ára lapon látható.</span><span class="sxs-lookup"><span data-stu-id="2f2ce-113">When you activate an item's cost record, you update the charges for the item's base cost information, which is displayed in the Item price page.</span></span> <span data-ttu-id="2f2ce-114">A költségek két külön mező formájában jelennek meg, és nem szerepelnek a cikk egységköltségében.</span><span class="sxs-lookup"><span data-stu-id="2f2ce-114">The charges are displayed as two separate fields, and they are not included in the item's unit cost.</span></span> <span data-ttu-id="2f2ce-115">Minden aktiválás frissíti a cikk alapköltségadatait, még abban az esetben is, ha az aktiválás különböző helyekre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="2f2ce-115">Each activation updates the item's base cost information, even if the activation reflects different sites.</span></span> <span data-ttu-id="2f2ce-116">Ennek megfelelően az alapköltségadatokat referenciaadatnak kell tekinteni.</span><span class="sxs-lookup"><span data-stu-id="2f2ce-116">Therefore, you should view the base cost information as reference information.</span></span>





