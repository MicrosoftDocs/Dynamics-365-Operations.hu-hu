---
title: Az elszámolóár előfeltételeinek áttekintése
description: Ez a témakör az elszámolóár használatának alaplépéseit fedi le.
author: AndersGirke
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f2e1620de804f42688ad8d05232e38178b5fb80
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187722"
---
# <a name="prerequisites-for-standard-costs-overview"></a><span data-ttu-id="4f053-103">Az elszámolóár előfeltételeinek áttekintése</span><span class="sxs-lookup"><span data-stu-id="4f053-103">Prerequisites for standard costs overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4f053-104">Ez a témakör az elszámolóár használatának alaplépéseit fedi le.</span><span class="sxs-lookup"><span data-stu-id="4f053-104">This topic describes the basic steps for using standard costs.</span></span> <span data-ttu-id="4f053-105">A további lépések a vállalati működéstől függenek.</span><span class="sxs-lookup"><span data-stu-id="4f053-105">Subsequent steps depend on the company's operations.</span></span> <span data-ttu-id="4f053-106">Például a lépések eltérőek nem termelési környezet, útvonal nélküli termelési környezet és útvonalakat használó termelési környezet esetén.</span><span class="sxs-lookup"><span data-stu-id="4f053-106">For example, the steps differ for a nonmanufacturing environment, a manufacturing environment that doesn't use routings, and a manufacturing environment that uses routings.</span></span> 

<span data-ttu-id="4f053-107">Az elszámolóár beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4f053-107">To set up standard costs, follow these steps.</span></span>

<span data-ttu-id="4f053-108">**1. Hozzon létre egy cikkmodellcsoportot az elszámolóáraknak.**</span><span class="sxs-lookup"><span data-stu-id="4f053-108">**1. Create an item model group for standard costs.**</span></span>

<span data-ttu-id="4f053-109">Használja a **Cikkmodellcsoportok** lapot, és hozzon létre egy új csoportot az elszámolóárhoz, és rendeljen hozzá egy **Elszámolóár** készletmodellt.</span><span class="sxs-lookup"><span data-stu-id="4f053-109">Use the **Item model groups** page to create a new group for standard costs, and assign an inventory model of **Standard cost**.</span></span> <span data-ttu-id="4f053-110">A cikkmodellcsoport azonosítójának kifejezőnek kell lennie, például: **Elszámolóár**.</span><span class="sxs-lookup"><span data-stu-id="4f053-110">The identifier for the item model group should be meaningful, such as **Std Cost**.</span></span> <span data-ttu-id="4f053-111">Jelölje be a jelölőnégyzeteket annak jelzésére, hogy a csoportnak lehetővé kell tennie a pénzügyi negatív készleteket, és hogy fizikai leltárt és pénzügyi leltárt kell feladnia.</span><span class="sxs-lookup"><span data-stu-id="4f053-111">Select the check boxes to indicate that the group should allow financial negative inventory, and that it should post physical inventory and financial inventory.</span></span> <span data-ttu-id="4f053-112">Ez az elszámolóáras csoport cikkekhez kerül hozzárendelésre.</span><span class="sxs-lookup"><span data-stu-id="4f053-112">This standard cost group will be assigned to items.</span></span>

<span data-ttu-id="4f053-113">**2. Határozza meg az elszámolóár különbözeteihez tartozó főkönyvi számlákat.**</span><span class="sxs-lookup"><span data-stu-id="4f053-113">**2. Define ledger accounts that are related to standard cost variances.**</span></span> 

<span data-ttu-id="4f053-114">A **Számlatükör adatai** képernyő segítségével határozza meg az elszámolóár különbözeteihez tartozó főkönyvi számlákat.</span><span class="sxs-lookup"><span data-stu-id="4f053-114">Use the **Chart of accounts** page to define ledger accounts that are related to standard cost variances.</span></span> <span data-ttu-id="4f053-115">Ahhoz hogy a főkönyvi számlák a **Feladás** képernyőn hozzárendelhetőek legyenek, előbb meg kell határozni őket.</span><span class="sxs-lookup"><span data-stu-id="4f053-115">These ledger accounts must be defined before they can be assigned on the **Posting** page.</span></span> <span data-ttu-id="4f053-116">A főkönyvi számlák cikkcsoportokat és költségcsoportokat tükrözhetnek vissza.</span><span class="sxs-lookup"><span data-stu-id="4f053-116">The ledger accounts can reflect item groups and cost groups.</span></span>

<span data-ttu-id="4f053-117">**3. Rendeljen főkönyvi számlákat az elszámolóár-eltérésekkel kapcsolatos cikkfeladásokhoz.**</span><span class="sxs-lookup"><span data-stu-id="4f053-117">**3. Assign ledger accounts to item postings that are related to standard cost variances.**</span></span> 

<span data-ttu-id="4f053-118">Használja a **Feladás** oldalt a elszámolóár-eltérésekkel kapcsolatos főkönyvi számlák hozzárendeléséhez.</span><span class="sxs-lookup"><span data-stu-id="4f053-118">Use the **Posting** page to assign the ledger accounts that are related to standard cost variances.</span></span> <span data-ttu-id="4f053-119">Eldöntheti, hogy egy eltérés főkönyvi számláját cikk (vagy cikkcsoport) és költségcsoport (vagy költségcsoport-típus) szerint adja meg, vagy megadhatja, hogy a főkönyvi számla minden cikkre és költségcsoportra vonatkozzon.</span><span class="sxs-lookup"><span data-stu-id="4f053-119">You can specify a variance's ledger account by item (or item group) and by cost group (or cost group type), or you can specify that the ledger account applies to all items and all cost groups.</span></span> <span data-ttu-id="4f053-120">Ezek a lehetőségek összefüggenek a táblázatok, csoportok és mindenki költségkapcsolataival.</span><span class="sxs-lookup"><span data-stu-id="4f053-120">These options correspond to cost relations for tables, groups, and all.</span></span> 

<span data-ttu-id="4f053-121">Cikkfeladási szabályok megadása előtt a **Tranzakciókombinációk** képernyőt használva engedélyezze a költségkapcsolatokat (táblázatokhoz, csoportokhoz és mindenhez).</span><span class="sxs-lookup"><span data-stu-id="4f053-121">Before you define the item posting rules, use the **Transaction combinations** page to enable cost relations (for tables, groups, and all).</span></span>

<span data-ttu-id="4f053-122">**4. Adja meg az elszámolóárhoz tartozó készletparamétereket.**</span><span class="sxs-lookup"><span data-stu-id="4f053-122">**4. Define inventory parameters that are related to standard costs.**</span></span> 

-  <span data-ttu-id="4f053-123">A **Készletkönyvelés** képernyő használatával határozzon meg költségszabályozási paramétereket a **Készletkönyvelési irányelvek beállítása > Paramérerek** oldalon, hogy meghatározza az elszámolóárhoz tartozó két költség-ellenőrzési paramétert.</span><span class="sxs-lookup"><span data-stu-id="4f053-123">Use the **Inventory accounting** tab on the **Inventory accounting policies setup > Parameters** page to define two cost control parameters that are related to standard costs.</span></span>

    -  <span data-ttu-id="4f053-124">A **Költséglebontás** mezőben válassza a **Nem** vagy **Részfőkönyv** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4f053-124">In the **Cost breakdown** field, select **None** or **Sub ledger**.</span></span> <span data-ttu-id="4f053-125">Ha a **Részfőkönyv** lehetőséget választja, a költséglebontás egy *aktív* költség lebontását jelenti.</span><span class="sxs-lookup"><span data-stu-id="4f053-125">If you select **Sub ledger**, the cost breakdown is an *active* cost breakdown.</span></span> <span data-ttu-id="4f053-126">Az aktív költséglebontásnak meghatározó szerepe van az elszámolóár-elemek többszintű termékszerkezetének teljes keresztmetszetén át a költségcsoport szegmentálás kiszámításában, megőrzésében és megtekintésében.</span><span class="sxs-lookup"><span data-stu-id="4f053-126">An active cost breakdown is critical for calculating, retaining, and viewing cost group segmentation across a multilevel product structure for standard cost items.</span></span> <span data-ttu-id="4f053-127">Ha a költséglebontás aktív, lehet jelenteni és elemezni a készletet, a folyamatban lévő munkát és a költségcsoportonkénti eladott áruk beszerzési értékét (ELÁBÉ) egyszintű, többszintű vagy teljes formában.</span><span class="sxs-lookup"><span data-stu-id="4f053-127">When the cost breakdown is active, you can report and analyze inventory, work in process (WIP), and cost of goods sold (COGS) per cost group in a single-level, multilevel, or total format.</span></span> <span data-ttu-id="4f053-128">Ha a költséglebontás aktív, az azt jelenti, hogy ha egy legyártott cikk költségét aktiválja, a költségcsoport-szegmentálás a cikk költségrekordjában lesz eltárolva.</span><span class="sxs-lookup"><span data-stu-id="4f053-128">When the cost breakdown is active, if you activate a manufactured item's cost, the cost group segmentation will be stored in the item's cost record.</span></span> 

    -  <span data-ttu-id="4f053-129">Ha a **Nincs** lehetőséget választja, a költségcsoport-szegmentálás nem lesz karbantartva az elszámolóáras cikkeknél.</span><span class="sxs-lookup"><span data-stu-id="4f053-129">If you select **None**, cost group segmentation won't be maintained for standard cost items.</span></span> <span data-ttu-id="4f053-130">Más szóval a legyártott cikk elszámolóára egyetlen összegként lesz kiszámítva és karbantartva, költségcsoport-szegmentálás nélkül.</span><span class="sxs-lookup"><span data-stu-id="4f053-130">In other words, a manufactured item's standard cost will be calculated and maintained as a single amount, without cost group segmentation.</span></span> <span data-ttu-id="4f053-131">A gyártott összetevők költség-hozzájárulásai egyetlen összegbe lesznek összegyűjtve.</span><span class="sxs-lookup"><span data-stu-id="4f053-131">The cost contributions of manufactured components will be aggregated into the single amount.</span></span>

-  <span data-ttu-id="4f053-132">Az **Eltérések a szabványtól** mező segítségével válassza ki az **Összesítve** vagy a **Költségcsoportonként** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4f053-132">In the **Variances to standard** field, select **Summarized** or **Per cost group**.</span></span> <span data-ttu-id="4f053-133">Ha a **Költségcsoportonként** opciót választja, költségcsoportonként azonosíthatja a beszerzési árkülönbözeteket és termelési eltéréseket.</span><span class="sxs-lookup"><span data-stu-id="4f053-133">If you select **Per cost group**, you can identify purchase price variances and production variances by cost group.</span></span> <span data-ttu-id="4f053-134">Így azonosíthatja a négyfajta termelési eltérést: adagméret, mennyiség, ár és helyettesítési eltérések.</span><span class="sxs-lookup"><span data-stu-id="4f053-134">You can also identify the four types of production variances: the lot size, quantity, price, and substitution variances.</span></span> <span data-ttu-id="4f053-135">Az **Összesítve** opció kiválasztása azt jelenti, hogy nem lehet költségcsoport szerint szétválasztani a különbözeteket, és nem lehet azonosítani a négyféle termelési eltérést.</span><span class="sxs-lookup"><span data-stu-id="4f053-135">If you select **Summarized**, you can't identify variances by cost group, and you can't identify the four types of production variances.</span></span> <span data-ttu-id="4f053-136">Csak egy összesített gyártási különbözetet lesz látható.</span><span class="sxs-lookup"><span data-stu-id="4f053-136">You can just view a summarized production variance.</span></span>

-  <span data-ttu-id="4f053-137">A szokásos különbözetekkel kapcsolatos szabályok a költséglebontás szabályaitól függetlenül működnek.</span><span class="sxs-lookup"><span data-stu-id="4f053-137">The policy about variance to standard works independently of the cost breakdown policy.</span></span> <span data-ttu-id="4f053-138">Más szavakkal megteheti hogy költséglebontási szabályként a **Nincs** lehetőséget választja, és a költségcsoportonkénti különbözeteket pedig úgy választja ki, hogy a költségcsoportonkénti gyártási különbözetek mégis meg lesznek tartva.</span><span class="sxs-lookup"><span data-stu-id="4f053-138">In other words, you can select a cost breakdown policy of **None** and select variances per cost group, so that production variances by cost group will still be captured.</span></span>

<span data-ttu-id="4f053-139">**5. Költségszámítási verziók készítése az elszámolóárakhoz.**</span><span class="sxs-lookup"><span data-stu-id="4f053-139">**5. Create costing versions for standard costs.**</span></span> 

<span data-ttu-id="4f053-140">A **Költségszámítási verzió beállítása** képernyő segítségével hozzon létre egy vagy több költségszámítási verziót az elszámolóárakhoz.</span><span class="sxs-lookup"><span data-stu-id="4f053-140">Use the **Costing version setup** page to create one or more costing versions for standard costs.</span></span> <span data-ttu-id="4f053-141">Mindegyik költségszámítási verziót egy **Elszámolóáras** költségszámítási típushoz kell hozzárendelni, és a tartalmában engedélyeznie kell a költségadatokat.</span><span class="sxs-lookup"><span data-stu-id="4f053-141">Each costing version must be designated by a costing type of **Standard cost** and must allow content to include cost data.</span></span>

<span data-ttu-id="4f053-142">**6. Egy létező ügyfél előkészítése az elszámolóárak használatára**</span><span class="sxs-lookup"><span data-stu-id="4f053-142">**6. Prepare an existing customer to use standard costs.**</span></span> 

<span data-ttu-id="4f053-143">Azoknak a vevőknek, akik a meglévő cikkeiket át kívánják alakítani elszámolóáras készletmodellbe, az **Átalakítások elszámolóárra** képernyőt kell használniuk.</span><span class="sxs-lookup"><span data-stu-id="4f053-143">Customers who want to change their existing items to a standard cost inventory model must use the **Standard cost conversions** page.</span></span>


## <a name="related-topics"></a><span data-ttu-id="4f053-144">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="4f053-144">Related topics</span></span>

[<span data-ttu-id="4f053-145">Átalakítás elszámolóárra – áttekintés</span><span class="sxs-lookup"><span data-stu-id="4f053-145">Standard cost conversion overview</span></span>](standard-cost-conversion-overview.md)

### <a name="blogs"></a><span data-ttu-id="4f053-146">Blogok</span><span class="sxs-lookup"><span data-stu-id="4f053-146">Blogs</span></span>

#### <a name="community-blogs"></a><span data-ttu-id="4f053-147">Közösségi blogok</span><span class="sxs-lookup"><span data-stu-id="4f053-147">Community blogs</span></span>

- [<span data-ttu-id="4f053-148">Közvetlen anyagok költségének beállítása Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4f053-148">How to set up standard costs for direct materials in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/06/07/how-to-set-up-standard-costs-for-direct-materials-in-dynamics-365-for-finance-and-operations)
- [<span data-ttu-id="4f053-149">Szokásos közevetlen munkaerő-költségek: Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4f053-149">Standard direct labor costs in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/07/16/standard-direct-labor-cost-in-dynamics-365-for-finance-and-operations)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]