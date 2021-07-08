---
title: Global Inventory Accounting főkönyv
description: Ez a témakör a Global Inventory Accounting főkönyvét írja le, amelyeket egy pénznem, egy naptár, egy megállapodás és egy jogi személy és egy jogi személy kombinációja határoz meg.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ea3434675aa3b7f2304be93ef9b489747994fa9d
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273166"
---
# <a name="global-inventory-accounting-ledger"></a><span data-ttu-id="c53b4-103">Global Inventory Accounting főkönyv</span><span class="sxs-lookup"><span data-stu-id="c53b4-103">Global Inventory Accounting ledger</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="c53b4-104">A Global Inventory Accounting szolgáltatásnak saját főkönyvi készlete van.</span><span class="sxs-lookup"><span data-stu-id="c53b4-104">Global Inventory Accounting has its own set of ledgers.</span></span> <span data-ttu-id="c53b4-105">A rendszer minden alkalommal, amikor egy adott jogi személy készlettel kapcsolatos tranzakcióját feldolgozhatja, a rendszer szükség esetén bármilyen számú Global Inventory Accounting főkönyvet figyelembe tud venni a tranzakcióért.</span><span class="sxs-lookup"><span data-stu-id="c53b4-105">Each time an inventory-related transaction is processed for a relevant legal entity, the system can account for that transaction in any number of Global Inventory Accounting ledgers, as required.</span></span>

<span data-ttu-id="c53b4-106">A főkönyv a tartozások és a jóváírások mértékei.</span><span class="sxs-lookup"><span data-stu-id="c53b4-106">A ledger is a register of debit and credit measures.</span></span> <span data-ttu-id="c53b4-107">Ezek az intézkedések a költségelemek és az arelikszámlák alapján vannak osztályozva.</span><span class="sxs-lookup"><span data-stu-id="c53b4-107">These measures are classified by using cost elements and subledger accounts.</span></span> <span data-ttu-id="c53b4-108">A Global Inventory Accounting főkönyvét egy pénznem, egy naptár, egy megállapodás és egy jogi személy és egy jogi személy kombinációja határoz meg.</span><span class="sxs-lookup"><span data-stu-id="c53b4-108">A Global Inventory Accounting ledger is defined by its combination of a currency, a calendar, a convention, and an association with a legal entity.</span></span>

<span data-ttu-id="c53b4-109">A Global Inventory Accounting főkönyvek beállításához menjen a **Global inventory accounting \> Beállítás \> Global inventory accounting főkönyvek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c53b4-109">To set up your Global Inventory Accounting ledgers, go to **Global inventory accounting \> Setup \> Global inventory accounting ledgers**.</span></span> <span data-ttu-id="c53b4-110">Állítsa be a következő mezőket minden egyes főkönyvhöz:</span><span class="sxs-lookup"><span data-stu-id="c53b4-110">For each ledger, set the following fields:</span></span>

- <span data-ttu-id="c53b4-111">**Név** – Írja be a főkönyv nevét.</span><span class="sxs-lookup"><span data-stu-id="c53b4-111">**Name** – Enter the name of the ledger.</span></span>
- <span data-ttu-id="c53b4-112">**Leírás** – Adja meg a főkönyv leírását.</span><span class="sxs-lookup"><span data-stu-id="c53b4-112">**Description** – Enter a description of the ledger.</span></span>
- <span data-ttu-id="c53b4-113">**Pénzügyi naptár** – Adja meg a főkönyv pénzügyi naptárát.</span><span class="sxs-lookup"><span data-stu-id="c53b4-113">**Fiscal calendar** – Specify the fiscal calendar for the ledger.</span></span>
- <span data-ttu-id="c53b4-114">**Pénznem és árfolyamtípus** – A gyorsététi űrlap mezőivel kiválaszthatja a főkönyvben használt könyvelési pénznemet, valamint az árfolyam típusát.</span><span class="sxs-lookup"><span data-stu-id="c53b4-114">**Currency and exchange rate type** – Use the fields on this FastTab to select the accounting currency that the ledger uses, and the exchange rate type.</span></span> <span data-ttu-id="c53b4-115">A kiválasztott pénznem eltérhet a jogi személy által használt pénznemtől.</span><span class="sxs-lookup"><span data-stu-id="c53b4-115">The currency that you select can differ from the currency that the legal entity uses.</span></span> <span data-ttu-id="c53b4-116">A Global Inventory Accounting szolfáltatásban a felhasználók a lehető legtöbb költségszámítási főkönyvet meghatározhatják.</span><span class="sxs-lookup"><span data-stu-id="c53b4-116">In Global Inventory Accounting, users can define as many costing ledgers as they require.</span></span> <span data-ttu-id="c53b4-117">A Global Inventory Accounting támogatja a készletek könyvelését több pénznemben és többféle értékelésben.</span><span class="sxs-lookup"><span data-stu-id="c53b4-117">Global Inventory Accounting supports inventory accounting in multiple currencies and in multiple valuations.</span></span> <span data-ttu-id="c53b4-118">Állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="c53b4-118">Set the following fields:</span></span>

    - <span data-ttu-id="c53b4-119">**Pénznem** – A készlettel kapcsolatos értékek karbantartásához használt költségszámítási pénznem kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="c53b4-119">**Currency** – Select the costing currency that inventory-related values are maintained in.</span></span> <span data-ttu-id="c53b4-120">Ezek közé tartozik a készletérték, az eladott áruk beszerzési értéke, az átmenő készlet és minden különbözet.</span><span class="sxs-lookup"><span data-stu-id="c53b4-120">These values include the inventory value, cost of goods sold, inventory in transit, and all kinds of variance.</span></span>
    - <span data-ttu-id="c53b4-121">**Árfolyamtípus** – Válassza ki, hogy milyen árfolyamot használ a rendszer a tranzakció összegének a tranzakció pénznemében történő átváltása során, valamint a cikkek elszámolóárát a költségszámítási pénznemre.</span><span class="sxs-lookup"><span data-stu-id="c53b4-121">**Exchange rate type** – Select the exchange rate that the system should use to convert the transaction amount in the transaction currency and the standard cost of the items into the costing currency.</span></span>

- <span data-ttu-id="c53b4-122">**Megállapodás neve** – Egy megállapodás megadása.</span><span class="sxs-lookup"><span data-stu-id="c53b4-122">**Convention name** – Specify a convention.</span></span> <span data-ttu-id="c53b4-123">A szabályok olyan irányelvek gyűjteménye, amelyek meghatározzák a költségek főkönyvben való könyvelésének a mikéntjét.</span><span class="sxs-lookup"><span data-stu-id="c53b4-123">A convention is a collection of policies that establish how costs will be accounted in this ledger.</span></span>
- <span data-ttu-id="c53b4-124">**Jogi személy** – A főkönyv figyelembe veszi a kijelölt jogi személynek feladott dokumentumokat.</span><span class="sxs-lookup"><span data-stu-id="c53b4-124">**Legal entity** – The ledger will account the documents that are posted to the selected legal entity.</span></span>
- <span data-ttu-id="c53b4-125">**Alapeset** – Annak kiválasztása, hogy a főkönyv létrehozása előtt létrehozott készlettranzakciókat a főkönyvben használt pénznem és megállapodás szerint kell-e feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="c53b4-125">**Priming** – Select whether inventory transactions that were created before the ledger was created should be processed according to the currency and convention in the ledger.</span></span> <span data-ttu-id="c53b4-126">Válasszon a következő értékek közül:</span><span class="sxs-lookup"><span data-stu-id="c53b4-126">Select one of the following values:</span></span>

    - <span data-ttu-id="c53b4-127">**Aktiválva** – A főkönyvnek fel kell feldolgoznia a főkönyv létrehozása előtt létrehozott tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="c53b4-127">**Activated** – The ledger should process transactions that were created before the ledger was created.</span></span>
    - <span data-ttu-id="c53b4-128">**Deaktiválva** – A főkönyvnek csak a főkönyv létrehozása után létrehozott tranzakciókat kell feldolgoznia.</span><span class="sxs-lookup"><span data-stu-id="c53b4-128">**Deactivated** – The ledger should process only transactions that are created after the ledger was created.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c53b4-129">Az új dokumentumok beíratás után **nem** lehet visszatérni és beállítani ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="c53b4-129">You will **not** be able to come back and set this field after you enter new documents.</span></span>

- <span data-ttu-id="c53b4-130">**Állapot** – A rendszer automatikusan a *Felkészülés* állapotra állítja az újonnan létrehozott főkönyvek állapotát.</span><span class="sxs-lookup"><span data-stu-id="c53b4-130">**Status** – The system automatically sets the status of newly created ledgers to *Prepare*.</span></span>
