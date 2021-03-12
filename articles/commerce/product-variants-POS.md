---
title: Készlet ellenőrzése a pénztárnál (POS)
description: Ez a témakör leírja a készletinformációinak megtekintéséhez a pénztárnál (POS) rendelkezésre álló beállításokat.
author: ashishmsft
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: f08906c14f80b07368d88d820acae83cf1157e6c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969951"
---
# <a name="inventory-lookup-in-the-point-of-sale-pos"></a><span data-ttu-id="13e40-103">Készlet ellenőrzése a pénztárnál (POS)</span><span class="sxs-lookup"><span data-stu-id="13e40-103">Inventory lookup in the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="13e40-104">A keresés a készletben a pénztárnál (POS) segítségével a kiskereskedők valós idejű üzemi kiválóságot érhetnek el, és információkat szerezhetnek az áruházak, a pénztár és a háttériroda összekapcsolásával.</span><span class="sxs-lookup"><span data-stu-id="13e40-104">Inventory lookup in the point of sale (POS) helps retailers achieve real-time operational excellence and gain insights by connecting stores, the POS, and the back office.</span></span> <span data-ttu-id="13e40-105">Ez a funkció lehetővé teszi az üzletek és elosztóközpontok termékkészletének pontos valós idejű megtekintését.</span><span class="sxs-lookup"><span data-stu-id="13e40-105">This functionality provides an accurate real-time view of product inventory across stores and distribution centers.</span></span> <span data-ttu-id="13e40-106">A hatékonyság és a költségmegtakarítás növelését teszi lehetővé a kiskereskedők számára a valós idejű készlettervezés továbbfejlesztésével.</span><span class="sxs-lookup"><span data-stu-id="13e40-106">It also helps retailers drive additional efficiencies and cost savings by improving inventory planning in real time.</span></span>

<span data-ttu-id="13e40-107">A készletnek a szervezeten belüli pontos valós idejű nézetének segítségével az üzlet munkatársai időbeli, kiváló ügyfélkiszolgálást nyújthatnak.</span><span class="sxs-lookup"><span data-stu-id="13e40-107">An accurate real-time view of inventory across an organization helps store associates provide timely, superior customer service.</span></span> <span data-ttu-id="13e40-108">A legfontosabb pillanat az, amikor a vevő készen áll a beszerzési döntés meghozására.</span><span class="sxs-lookup"><span data-stu-id="13e40-108">The moment that matters most is the moment when the customer is ready to make a purchase decision.</span></span> <span data-ttu-id="13e40-109">Fontos, hogy a pénztárosok az üzletben valós idejű készletadatokkal rendelkezzenek, és így pontosan ígéreteket tehessenek a termék szállítására és felvételére.</span><span class="sxs-lookup"><span data-stu-id="13e40-109">It's important that cashiers in the store have real-time inventory information at their fingertips, so that they can accurately promise product delivery and pickup.</span></span>

<span data-ttu-id="13e40-110">Megnyithatja a **Keresés a készletben** lapot a **Retail Modern POS** munkaterületről vagy a **Retail Cloud POS** munkaterületről.</span><span class="sxs-lookup"><span data-stu-id="13e40-110">You can open the **Inventory lookup** page from the **Retail Modern POS** workspace or the **Retail Cloud POS** workspace.</span></span>

![Készletkeresési csempe a POS-kezdőlapon](media/POSHomepage.png)

<span data-ttu-id="13e40-112">A **Keresés a készletben** lapon a numerikus billentyűzet használatával adhatja meg a termékszámot.</span><span class="sxs-lookup"><span data-stu-id="13e40-112">On the **Inventory lookup** page, you can use the numeric keyboard to enter a product number.</span></span> <span data-ttu-id="13e40-113">A készleten lévő cikkmennyiség több áruházra és raktárra tekinthető meg.</span><span class="sxs-lookup"><span data-stu-id="13e40-113">You can then view the on-hand quantity for multiple stores and warehouses.</span></span>

![Szabványos készletkeresési lap](media/InventoryLookUp.png)

<span data-ttu-id="13e40-115">**Fenntartott** és **Megrendelve** mennyiségek is megjelennek az egyes helyekhez.</span><span class="sxs-lookup"><span data-stu-id="13e40-115">**Reserved** and **Ordered** quantities are also shown for each location.</span></span>

- <span data-ttu-id="13e40-116">**Fenntartott** – Ez a mennyiség a **Ténylegesen fenntartott** értékre vonatkozik, amely a háttérirodai rendszerből származik, a megadott termékszámra az adott helyen.</span><span class="sxs-lookup"><span data-stu-id="13e40-116">**Reserved** – This quantity refers to the **Physical reserved** value from the back office for the specified product number at the location.</span></span>
- <span data-ttu-id="13e40-117">**Megrendelve** – Ez a mennyiség az **Összes rendelés** értékre vonatkozik, amely a háttérirodai rendszerből származik, a megadott termékszámra az adott helyen.</span><span class="sxs-lookup"><span data-stu-id="13e40-117">**Ordered** – This quantity refers to the **Ordered in total** value from the back office for the specified product number at the location.</span></span>

## <a name="locations-that-inventory-availability-information-is-shown-for"></a><span data-ttu-id="13e40-118">Helyek, amelyre a készlet elérhetőségi adatok megjelennek</span><span class="sxs-lookup"><span data-stu-id="13e40-118">Locations that inventory availability information is shown for</span></span>

<span data-ttu-id="13e40-119">A helyek listája kétfajta entitást tartalmaz:</span><span class="sxs-lookup"><span data-stu-id="13e40-119">The list of locations includes two types of entities:</span></span>

- <span data-ttu-id="13e40-120">**Áruházak** – A lista azokat az üzleteket tartalmazza, amelyeket az üzletcsoport lokátorcsoport használatával konfiguráltak az aktuális üzletre a központokban.</span><span class="sxs-lookup"><span data-stu-id="13e40-120">**Stores** – The list shows stores that are configured by using the store locator group for the current store in the Headquarters.</span></span>
- <span data-ttu-id="13e40-121">**Elosztóközpontok** – Különféle elosztóközpontokat (például raktár) lehet a Commerce alkalmazásban beállítani.</span><span class="sxs-lookup"><span data-stu-id="13e40-121">**Distribution centers** – Various types of distribution centers (such as warehouses) can be configured in Commerce.</span></span> <span data-ttu-id="13e40-122">A készlet-elérhetőségi adatokat azonban a lista csak a **Szabványos**, alapértelmezett típusú elosztóközpontokra mutatja.</span><span class="sxs-lookup"><span data-stu-id="13e40-122">However, the list shows inventory availability information only for distribution centers of the **Standard** default type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="13e40-123">A készlet-elérhetőségi adatok nem jelennek meg a pénztárban a **Tranzit**, **Karantén** és **Úton lévő áruk** típusú raktárak esetében.</span><span class="sxs-lookup"><span data-stu-id="13e40-123">Inventory availability information isn't shown for warehouses of the **Transit**, **Quarantine**, and **Goods in Route** types for the POS.</span></span>

<span data-ttu-id="13e40-124">A **Keresés a készletben** lapon megtekintheti az ígérethez rendelkezésre álló (ATP) mennyiségeket az egyes üzletekben, az aktuális készleten lévő mennyiségek, a lefoglalt mennyiségek és a megrendelt mennyiségek mellett.</span><span class="sxs-lookup"><span data-stu-id="13e40-124">On the **Inventory lookup** page, you can view available to promise (ATP) quantities for each store, in addition to the current on-hand quantities, reserved quantities, and ordered quantities.</span></span> <span data-ttu-id="13e40-125">Válassza ki az üzletet, amelynek ígérethez rendelkezésre álló információit meg szeretné tekinteni, és válassza ki az **Üzlet elérhetőségének megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="13e40-125">Select the store to view the ATP information for, and then select **Show store availability**.</span></span>

![ATP-mennyiségek](media/ATP.png)

## <a name="opening-the-dimension-based-matrix-view-to-show-all-variants"></a><span data-ttu-id="13e40-127">A dimenzióalapú mátrixnézet megnyitása minden változat megtekintéséhez</span><span class="sxs-lookup"><span data-stu-id="13e40-127">Opening the Dimension based matrix view to show all variants</span></span>

<span data-ttu-id="13e40-128">A **Termékadatok** lapján az alapterméknek, vagy a **Keresés a készletben** oldalon, válassza **Az összes változat megtekintése** lehetőséget az alkalmazás-eszköztáron az oldal alján.</span><span class="sxs-lookup"><span data-stu-id="13e40-128">On the **Product details** page of a product master, or on the **Inventory lookup** page, select **View all variants** from the app-bar at bottom of the page.</span></span> <span data-ttu-id="13e40-129">A **Dimenzióalapú mátrix** nézet a kezdeti indításhoz ezeken a lapokon a készletelérhetőségi adatokat jeleníti meg minden termékváltozathoz az aktuális üzlet esetében.</span><span class="sxs-lookup"><span data-stu-id="13e40-129">The **Dimension based matrix** view for the initial launch from these pages shows the inventory availability information for all variants of a product for the current store.</span></span>

> [!NOTE]
> <span data-ttu-id="13e40-130">**Az összes változat megtekintése** gomb csak a termékváltozatokkal rendelkező cikk alaptermékekhez érhető el.</span><span class="sxs-lookup"><span data-stu-id="13e40-130">The **View all variants** button is available only for item product masters that have product variants.</span></span> <span data-ttu-id="13e40-131">Nem érhető el az önálló termékek vagy csomagok esetében.</span><span class="sxs-lookup"><span data-stu-id="13e40-131">It isn't available for standalone products or kits.</span></span>

![Az összes változat megtekintése gomb a Keresés a készletben lapon](media/StandardToMatrix.png)

<span data-ttu-id="13e40-133">Válassza ki **Az összes változat megtekintése** lehetőséget az alaptermék **Termékadatok** lapján, vagy a **Keresés a készletben** oldalon, a hely kiválasztása nélkül, az ugráshoz a **Dimenzióalapú mátrix** nézetre a készletelérhetőségi adatokat megtekintéséhez minden termékváltozathoz az aktuális üzlet esetében.</span><span class="sxs-lookup"><span data-stu-id="13e40-133">Select **View all variants** on the **Product details** page of a product master, or on the **Inventory lookup** page, without selecting a location, to go to the **Dimension based matrix** view to view the inventory availability information for all variants of a product for the current store.</span></span>

![Dimenzióalapú mátrix nézet a Keresés a készletben laphoz](media/Matrix.png)

> [!NOTE]
> <span data-ttu-id="13e40-135">Az előző ábrán a dimenziók megjelenítési sorrendje ábécésorrendű,mert a dimenziók megjelenítési sorrendje nem volt konfigurálva a kiválasztott termékhez.</span><span class="sxs-lookup"><span data-stu-id="13e40-135">In the preceding illustration, the display order of the dimensions is alphabetic, because the display order of dimensions wasn't configured for the selected product.</span></span>

<span data-ttu-id="13e40-136">A **Dimenzióalapú mátrix** nézetben a termékváltozatok cellái tartalmaznak egy aktuális készlet értéket a jobb alsó sarokban.</span><span class="sxs-lookup"><span data-stu-id="13e40-136">In the **Dimension based matrix** view, the cells for the product variants include an on-hand value in the lower-right corner.</span></span> <span data-ttu-id="13e40-137">Az alábbi táblázat bemutatja a különféle értékek jelentését.</span><span class="sxs-lookup"><span data-stu-id="13e40-137">The following table explains the meaning of the various values.</span></span>

| <span data-ttu-id="13e40-138">Aktuális készlet értéke</span><span class="sxs-lookup"><span data-stu-id="13e40-138">On-hand value</span></span>                            | <span data-ttu-id="13e40-139">Leírás</span><span class="sxs-lookup"><span data-stu-id="13e40-139">Description</span></span> |
|------------------------------------------|-------------|
| <span data-ttu-id="13e40-140">Számszerű érték, amely nagyobb, mint 0 (nulla)</span><span class="sxs-lookup"><span data-stu-id="13e40-140">Numeric value that is more than 0 (zero)</span></span> | <span data-ttu-id="13e40-141">A kiválasztott helyre fel lett adva egy változat, és további műveletek végezhetők el a cellában.</span><span class="sxs-lookup"><span data-stu-id="13e40-141">A variant has been released to the selected location, and you can perform additional actions in the cell.</span></span> <span data-ttu-id="13e40-142">(A műveletekről részletesen a jelen témakör későbbi szakaszaiban olvashat.)</span><span class="sxs-lookup"><span data-stu-id="13e40-142">(These actions are described in more detail later in this topic.)</span></span> |
| <span data-ttu-id="13e40-143">**0** (nulla)</span><span class="sxs-lookup"><span data-stu-id="13e40-143">**0** (zero)</span></span>                             | <span data-ttu-id="13e40-144">Egy változat már ki van adva a megadott helyre, de a cikk nem érhető el a kiválasztott helyen.</span><span class="sxs-lookup"><span data-stu-id="13e40-144">A variant has been released to the selected location, but the item isn't available in selected location.</span></span> <span data-ttu-id="13e40-145">Azonban a cellában további műveletek hajthatók végre.</span><span class="sxs-lookup"><span data-stu-id="13e40-145">However, you can perform additional actions in the cell.</span></span> <span data-ttu-id="13e40-146">(A műveletekről részletesen a jelen témakör későbbi szakaszaiban olvashat.)</span><span class="sxs-lookup"><span data-stu-id="13e40-146">(These actions are described in more detail later in this topic.)</span></span> |
| <span data-ttu-id="13e40-147">**n/a** vagy inaktív cella</span><span class="sxs-lookup"><span data-stu-id="13e40-147">**n/a** or an inactive cell</span></span>              | <span data-ttu-id="13e40-148">A kiválasztott helyre még nem lett feladva egy változat, és további műveletek nem végezhetők el a cellában.</span><span class="sxs-lookup"><span data-stu-id="13e40-148">A variant hasn't been released to the selected location, and you can't perform additional actions in the cell.</span></span> |

<span data-ttu-id="13e40-149">A kimutatás dimenziók szempontjából is módosítható úgy, hogy kiválasztja a használandó új dimenziót.</span><span class="sxs-lookup"><span data-stu-id="13e40-149">You can also change the pivot for dimensions by selecting the new dimension to use.</span></span>

![A kimutatás módosítása](media/ChangePivot.png)

![A kimutatás módosult](media/PivotChanged.png)

> [!NOTE]
> <span data-ttu-id="13e40-152">Az előző ábrákon a dimenziók megjelenítési sorrendje a kiválasztott termékhez egyéni (nem ábécésorrendet követ).</span><span class="sxs-lookup"><span data-stu-id="13e40-152">In the preceding illustrations, the display order of the dimensions for the selected product is custom (non-alphabetic).</span></span> <span data-ttu-id="13e40-153">A dimenziók háttérirodában beállított megjelenítési sorrendjén alapul.</span><span class="sxs-lookup"><span data-stu-id="13e40-153">It's based on the dimension display order that is set in the back office.</span></span>

<span data-ttu-id="13e40-154">Ezenkívül, a **Dimenzióalapú mátrix** nézetben, további műveleteket lehet végrehajtani a kiskereskedelmi munkatársak termelékenységének növelése érdekében.</span><span class="sxs-lookup"><span data-stu-id="13e40-154">Additionally, in the **Dimension based matrix** view, more actions can be performed to help boost a store associate's productivity.</span></span> <span data-ttu-id="13e40-155">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="13e40-155">Here are some examples:</span></span>

- <span data-ttu-id="13e40-156">Az összes termékváltozat készletének más helyeken levő rendelkezésre állásának megkereséséhez módosítsa a tárolási helyet.</span><span class="sxs-lookup"><span data-stu-id="13e40-156">Change the store location to look up the inventory availability of all product variants at other locations.</span></span> <span data-ttu-id="13e40-157">Ezek a helyek lehetnek az üzlet lokátorcsoportba tartozó más üzletek, valamint a **Szabványos** alapértelmezett típusú elosztóközpontok.</span><span class="sxs-lookup"><span data-stu-id="13e40-157">These locations include other stores in the store locator group and distribution centers of the **Standard** default type.</span></span>
- <span data-ttu-id="13e40-158">Értékesítsen egy konkrét termékváltozatot egy vevőnek cash and carry, üzleten belüli felvétele vagy szállítás címre módon.</span><span class="sxs-lookup"><span data-stu-id="13e40-158">Sell an individual product variant to a customer by using cash and carry, in-store pickup, or shipment to an address.</span></span>
- <span data-ttu-id="13e40-159">Adja meg a vevőknek az ígérethez rendelkezésre álló információkat egy adott termékváltozatról egy adott helyen.</span><span class="sxs-lookup"><span data-stu-id="13e40-159">Provide the customer with ATP information for an individual product variant at a specific location.</span></span>

![A termékváltozatokkal kapcsolatos további műveletek](media/VariantActions.png)

> [!NOTE]
> <span data-ttu-id="13e40-161">Az előző ábrán a dimenziók megjelenítési sorrendje ábécésorrendű,mert a dimenziók megjelenítési sorrendje nem volt konfigurálva a kiválasztott termékhez.</span><span class="sxs-lookup"><span data-stu-id="13e40-161">In the preceding illustration, the display order of the dimensions is alphabetic, because the display order of dimensions wasn't configured for the selected product.</span></span>

<span data-ttu-id="13e40-162">A következő táblázatban tájékozódhat a rendelkezésre álló további műveletekről.</span><span class="sxs-lookup"><span data-stu-id="13e40-162">The following table provides more information about the additional actions that are available.</span></span>

| <span data-ttu-id="13e40-163">Művelet</span><span class="sxs-lookup"><span data-stu-id="13e40-163">Action</span></span>               | <span data-ttu-id="13e40-164">Leírás</span><span class="sxs-lookup"><span data-stu-id="13e40-164">Description</span></span> |
|----------------------|-------------|
| <span data-ttu-id="13e40-165">Eladás most</span><span class="sxs-lookup"><span data-stu-id="13e40-165">Sell now</span></span>             | <span data-ttu-id="13e40-166">Adja a kijelölt cikkváltozatot a tranzakcióhoz, és irányítsa át a felhasználót a tranzakció képernyőre.</span><span class="sxs-lookup"><span data-stu-id="13e40-166">Add the selected item variant to the transaction, and redirect the user to the transaction screen.</span></span> <span data-ttu-id="13e40-167">(Ez a művelet nem érhető el, a kiválasztott hely elosztási központ.)</span><span class="sxs-lookup"><span data-stu-id="13e40-167">(This action isn't available when the selected location is a distribution center.)</span></span> |
| <span data-ttu-id="13e40-168">Felvétel az üzletben</span><span class="sxs-lookup"><span data-stu-id="13e40-168">Pick up in store</span></span>     | <span data-ttu-id="13e40-169">Hozzon létre vevői rendelést a termékváltozatra, amely a kijelölt helyen lesz felvéve, és irányítsa át a felhasználót a tranzakció képernyőre.</span><span class="sxs-lookup"><span data-stu-id="13e40-169">Create a customer order for the product variant that will be picked up from the selected location, and redirect the user to the transaction screen.</span></span> <span data-ttu-id="13e40-170">(Ez a művelet nem érhető el, a kiválasztott hely elosztási központ.)</span><span class="sxs-lookup"><span data-stu-id="13e40-170">(This action isn't available when the selected location is a distribution center.)</span></span> |
| <span data-ttu-id="13e40-171">Termék szállítása</span><span class="sxs-lookup"><span data-stu-id="13e40-171">Ship product</span></span>         | <span data-ttu-id="13e40-172">Hozzon létre vevői rendelést a termékváltozatra, amely a kijelölt helyre lesz kiszállítva, és irányítsa át a felhasználót a tranzakció képernyőre.</span><span class="sxs-lookup"><span data-stu-id="13e40-172">Create a customer order for the product variant that will be shipped from the selected location, and redirect the user to the transaction screen.</span></span> |
| <span data-ttu-id="13e40-173">Elérhetőség</span><span class="sxs-lookup"><span data-stu-id="13e40-173">Availability</span></span>         | <span data-ttu-id="13e40-174">Jelenítse meg az ígérethez rendelkezésre álló információkat a kiválasztott változatkombinációra a kiválasztott helyre.</span><span class="sxs-lookup"><span data-stu-id="13e40-174">Show the ATP information for the selected variant combination for the selected location.</span></span> |
| <span data-ttu-id="13e40-175">Minden hely megjelenítése</span><span class="sxs-lookup"><span data-stu-id="13e40-175">Show all locations</span></span>   | <span data-ttu-id="13e40-176">Váltson át a szokásos készletkeresési nézetre, és jelölje ki a készletelérhetőségi információkat a cikkváltozatra az összes üzletben az üzlet-lokátorcsoportban, valamint a **Szabványos/Alapértelmezett** típusú elosztóközpontokban.</span><span class="sxs-lookup"><span data-stu-id="13e40-176">Switch to the standard inventory lookup view, and highlight inventory availability information for the item variant across all stores in the store locator group, and also in distribution centers of the **Standard/Default** type.</span></span> |
| <span data-ttu-id="13e40-177">Termék részleteinek megtekintése</span><span class="sxs-lookup"><span data-stu-id="13e40-177">View product details</span></span> | <span data-ttu-id="13e40-178">Irányítsa át a felhasználót a társított alaptermék **Termék részletei** oldalára.</span><span class="sxs-lookup"><span data-stu-id="13e40-178">Redirect the user to the **Product details** page of the associated product master.</span></span> |
