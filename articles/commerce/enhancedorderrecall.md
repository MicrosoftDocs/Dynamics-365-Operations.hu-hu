---
title: Rendelési művelet visszahívása a pénztárban
description: Ez a témakör a pénztárban található, továbbfejlesztett rendelés-visszahívási oldalak kiemelt funkcióit ismerteti.
author: hhainesms
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 42b11ff16757d633b868dfdf248341193a44378f
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665298"
---
# <a name="recall-order-operation-in-pos"></a><span data-ttu-id="90aaf-103">Rendelési művelet visszahívása a pénztárban</span><span class="sxs-lookup"><span data-stu-id="90aaf-103">Recall order operation in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="90aaf-104">A Commerce pénztárban (POS) elérhető **Rendelés-visszahívási** művelet frissített rendeléskeresési és -szűrési funkciókat, valamint rendeléshez kapcsolódó információkat nyújt.</span><span class="sxs-lookup"><span data-stu-id="90aaf-104">The **Recall order** operation in the Commerce point of sale (POS) provides updated order search and filtering features and order-specific information.</span></span> <span data-ttu-id="90aaf-105">Ez a funkció a 10.0.15-ös vagy újabb verziójú Commerce modulban elérhető.</span><span class="sxs-lookup"><span data-stu-id="90aaf-105">This feature is available in Commerce versions 10.0.15 and later.</span></span>

<span data-ttu-id="90aaf-106">A funkció engedélyezéséhez kapcsolja be a **Továbbfejlesztett rendelés-visszahívási művelet a pénztárban** funkciót a Commerce központban található **Funkciókezelés** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="90aaf-106">To enable this functionality, turn the **Improved Recall order operation in POS** feature on in **Feature management** workspace in Commerce headquarters.</span></span> <span data-ttu-id="90aaf-107">Miután engedélyezte a funkciót, esetleg frissítse a [képernyő-elrendezéseket](pos-screen-layouts.md) a pénztárban a módosított képességek előnyeinek kihasználása érdekében.</span><span class="sxs-lookup"><span data-stu-id="90aaf-107">After you enable the feature, consider updating your [screen layouts](pos-screen-layouts.md) in POS to take advantage of some of the changed  capabilities.</span></span>

<span data-ttu-id="90aaf-108">A **Rendelés-visszahívás** művelet gombjának konfigurálásával a szervezetek előre meghatározott megjelenítéssel telepíthetik a műveletet.</span><span class="sxs-lookup"><span data-stu-id="90aaf-108">The configuration of the **Recall order** operation button allows organizations to deploy the operation with a pre-defined display.</span></span>

![Gombrács konfigurálása](media/recallorderbuttongrid.png)

<span data-ttu-id="90aaf-110">A megjelenítés beállítási lehetőségei a következők:</span><span class="sxs-lookup"><span data-stu-id="90aaf-110">The display options are as follows.</span></span>
- <span data-ttu-id="90aaf-111">**Nincs** – Ezzel a beállítással a művelet speciális megjelenítés nélkül telepíthető.</span><span class="sxs-lookup"><span data-stu-id="90aaf-111">**None** – This option deploys the operation with no specific display.</span></span> <span data-ttu-id="90aaf-112">Amikor egy felhasználó ezzel a konfigurációval nyitja meg a műveletet, a program felkéri, hogy keressen megrendeléseket vagy válasszon egy előre definiált rendelésszűrőből.</span><span class="sxs-lookup"><span data-stu-id="90aaf-112">When a user opens the operation with this configuration, they will be prompted to search and find orders or choose from a pre-defined order filter.</span></span>
- <span data-ttu-id="90aaf-113">**Teljesítendő megrendelések** – Amikor a felhasználó elindítja a műveletet, a lekérdezést automatikusan futtatja a rendszer, valamint megjeleníti az áruház által teljesítendő megrendelések listáját.</span><span class="sxs-lookup"><span data-stu-id="90aaf-113">**Orders to fulfill** – When a user launches the operation, a query will run automatically to search and display a list of orders that are to be fulfilled by the store.</span></span> <span data-ttu-id="90aaf-114">Ezeket a rendeléseket áruházon belüli felvételre vagy az áruház általi szállításra konfigurálták, és az ilyen rendelések sorai még kerültek összeszedésre vagy becsomagolásra.</span><span class="sxs-lookup"><span data-stu-id="90aaf-114">These orders are configured for in-store pickup or store shipment and the lines of these orders have not yet been picked or packed.</span></span>
- <span data-ttu-id="90aaf-115">**Összeszedendő megrendelések** – Amikor a felhasználó elindítja a műveletet, a lekérdezést automatikusan futtatja a rendszer, valamint megjeleníti a felhasználó aktuális áruházában való összeszedésre konfigurált megrendelések listáját.</span><span class="sxs-lookup"><span data-stu-id="90aaf-115">**Orders to pick up** – When a user launches the operation, a query will run automatically to search and display a list of orders that are configured for in-store pickup at the user's current store.</span></span>
- <span data-ttu-id="90aaf-116">**Szállítandó megrendelések** – Amikor a felhasználó elindítja a műveletet, a lekérdezést automatikusan futtatja a rendszer, valamint megjeleníti a felhasználó aktuális áruházából való szállításra konfigurált megrendelések listáját.</span><span class="sxs-lookup"><span data-stu-id="90aaf-116">**Orders to ship** - When a user launches the operation, a query will run automatically to search and display a list of orders that are configured for shipment from the user's current store.</span></span>

<span data-ttu-id="90aaf-117">A **Rendelés-visszahívás** művelet pénztárból való elindításakor, ha a képernyőt **Nincs** beállításra konfigurálták, akkor a felhasználó a következő módokon keresheti meg és kérdezheti le a rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="90aaf-117">When launching the **Recall order** operation from POS, if the display is configured to **None**, a user will be able to search and retrieve orders in one of the following ways.</span></span>
- <span data-ttu-id="90aaf-118">Rendelésvonalkódok beolvasása.</span><span class="sxs-lookup"><span data-stu-id="90aaf-118">Scan order barcodes.</span></span> <span data-ttu-id="90aaf-119">E művelet során rendelésszám, csatornahivatkozás és nyugtaazonosító mezőkben futtat keresést a rendszer.</span><span class="sxs-lookup"><span data-stu-id="90aaf-119">This will search order number, channel reference, and receipt ID fields for matches.</span></span>
- <span data-ttu-id="90aaf-120">Válassza ki a **Rendelések keresése** vagy **Keresés és szűrése** ikont az AppBar felületen, hogy a szűrési mechanizmus segítségével megkeresse azokat a rendeléseket, amelyek megfelelnek a szűrési feltételeknek.</span><span class="sxs-lookup"><span data-stu-id="90aaf-120">Select **Search orders** or **Search and filter** icon on the AppBar to use the filtering mechanism to locate orders that meet the filter criteria.</span></span>
- <span data-ttu-id="90aaf-121">Előre definiált szűrőkből választhat a **Rendelések megjelenítése** legördülő listából (teljesítendő rendelések, összeszedendő rendelések vagy szállítandó rendelések).</span><span class="sxs-lookup"><span data-stu-id="90aaf-121">Choose from a pre-defined filter from the **Show Orders** drop-down menu (orders to fulfill, orders to pick up, or orders to ship).</span></span>

![RecallOrderMainMenu](media/recallordermain.png)

<span data-ttu-id="90aaf-123">A keresési feltételekkel végzett keresés után az alkalmazás megjeleníti az egyezést mutató értékesítési rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="90aaf-123">After search criteria are applied, the application will display a list of matching sales orders.</span></span>

![RecallOrderDetail](media/orderrecalldetail.png)

<span data-ttu-id="90aaf-125">A felhasználó kiválaszthat a listán egy rendelést, és megtekintheti a további részleteket.</span><span class="sxs-lookup"><span data-stu-id="90aaf-125">A user can select an order on the list to view additional details.</span></span> <span data-ttu-id="90aaf-126">A képernyő jobb oldalán látható információs ablak a kiválasztott rendelés részleteit jeleníti meg, többek között a rendelési sor adatait, a szállítási adatokat és a teljesítési adatokat.</span><span class="sxs-lookup"><span data-stu-id="90aaf-126">The information panel on the right side of the screen displays specifics on the selected order, including order line details, delivery details, and fulfillment details.</span></span>

<span data-ttu-id="90aaf-127">Az AppBar felületen a felhasználó kiválaszthat egy műveletet.</span><span class="sxs-lookup"><span data-stu-id="90aaf-127">From the AppBar, a user can select an operation.</span></span> <span data-ttu-id="90aaf-128">A rendelés állapotától függően előfordulhat, hogy bizonyos műveletek nem engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="90aaf-128">Depending on the status of the order, certain operations may not be enabled.</span></span>

- <span data-ttu-id="90aaf-129">**Visszáru** – Visszáruzást hajt végre a kiválasztott vevői rendeléshez kapcsolódó egy vagy több számlához.</span><span class="sxs-lookup"><span data-stu-id="90aaf-129">**Return** – Executes a return for one or more invoices related to the selected customer order.</span></span>

- <span data-ttu-id="90aaf-130">**Visszavonás** – A kiválasztott értékesítési rendelés teljes visszavonásának elrendelése.</span><span class="sxs-lookup"><span data-stu-id="90aaf-130">**Cancel** – Issue a full cancellation of the selected sales order.</span></span>

- <span data-ttu-id="90aaf-131">**Teljesítés** – A felhasználót a rendelés teljesítése oldalra vezeti át, amely a kiválasztott rendelésnek megfelelő előzetesen szűrten jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="90aaf-131">**Fulfill** – Transfers the user to the order fulfillment page, which will be pre-filtered for the selected order.</span></span> <span data-ttu-id="90aaf-132">Csak azok a rendeléssorok jelennek meg, amelyek a kijelölt rendelésnek a felhasználó áruháza általi teljesítése céljából nyitottak.</span><span class="sxs-lookup"><span data-stu-id="90aaf-132">Only order lines that are open for fulfillment by the user's store for the selected order will be displayed.</span></span>

- <span data-ttu-id="90aaf-133">**Szerkesztés** – Lehetővé teszi a felhasználók számára a kiválasztott vevői rendelés módosítását.</span><span class="sxs-lookup"><span data-stu-id="90aaf-133">**Edit** – Allows users to make changes to the selected customer order.</span></span>

- <span data-ttu-id="90aaf-134">**Összeszedés** – Elindítja az összeszedési folyamatot, amellyel a felhasználó kiválaszthatja az összeszedendő termékeket, és létrehozza az összeszedési értékesítési tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="90aaf-134">**Pick up** – Launches the pickup flow, which allows the user to choose the products to be picked up and creates the pickup sales transaction.</span></span>
