---
title: Készlettranzakciók archiválása
description: Ez a témakör azt ismerteti, hogyan lehet archiválni a készlettranzakciók adatait a rendszer teljesítményének javítása érdekében.
author: sherry-zheng
manager: tfehr
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTransArchiveProcessForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 3a0fa65eb728e4ce96bdfc3f7a0f04901551ccea
ms.sourcegitcommit: 70b1567d316f19c15a4b032b4897f15c8dcdca09
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2021
ms.locfileid: "5556423"
---
# <a name="archive-inventory-transactions"></a><span data-ttu-id="37fc4-103">Készlettranzakciók archiválása</span><span class="sxs-lookup"><span data-stu-id="37fc4-103">Archive inventory transactions</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="37fc4-104">Az idő folyamán a készlettranzakciók táblája (`InventTrans`) tovább nő és több adatbázisterületet foglal el.</span><span class="sxs-lookup"><span data-stu-id="37fc4-104">Over time, the inventory transactions table (`InventTrans`) will continue to grow and consume more database space.</span></span> <span data-ttu-id="37fc4-105">Emiatt a táblába küldött lekérdezések fokozatosan lelassulnak.</span><span class="sxs-lookup"><span data-stu-id="37fc4-105">Therefore, queries that are made against the table will gradually become slower.</span></span> <span data-ttu-id="37fc4-106">Ez a témakör azt írja le, hogy hogyan archiválhatja a *Készlettranzakciók archívuma* funkcióval a készlettranzakciók adatait, hogy ezzel javítsa a rendszer teljesítményét.</span><span class="sxs-lookup"><span data-stu-id="37fc4-106">This topic describes how you can use the *Inventory transactions archive* feature to archive data about inventory transactions to help improve system performance.</span></span>

> [!NOTE]
> <span data-ttu-id="37fc4-107">Csak a pénzügyileg frissített készlettranzakciók archiválhatók a kiválasztott lezárt főkönyvi időszakban.</span><span class="sxs-lookup"><span data-stu-id="37fc4-107">Only financially updated inventory transactions can be archived in a selected closed ledger period.</span></span> <span data-ttu-id="37fc4-108">Az archiváláshoz a pénzügyileg frissített kimenő készlettranzakciók kiadási állapotának *Eladva* értéknek kell lennie, a bejövő készlettranzakcióknak *Beszerzett* bevételezési állapotúnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="37fc4-108">To be archived, financially updated outbound inventory transactions must have an issue status of *Sold*, and inbound inventory transactions must have a receipt status of *Purchased*.</span></span>

<span data-ttu-id="37fc4-109">A készlettranzakciók archiválásakor minden kapcsolódó tranzakció az `InventTransArchive` táblába kerül.</span><span class="sxs-lookup"><span data-stu-id="37fc4-109">When you archive inventory transactions, all related transactions are moved to the `InventTransArchive` table.</span></span> <span data-ttu-id="37fc4-110">A készletkiadási tranzakciók és a készletbevételezési tranzakciók archiválása külön történik, a cikkazonosító (`itemId`) és a készletdimenzió-azonosító (`inventDimId`) kombinációja alapján, és a rendszer összesített kiadási és összesített bevételezési tranzakciók közé sorolja őket.</span><span class="sxs-lookup"><span data-stu-id="37fc4-110">Inventory issue transactions and inventory receipt transactions are archived separately, based on the combination of the item ID (`itemId`) and inventory dimension ID (`inventDimId`), and they are put into the summarized issue and summarized receipt transactions.</span></span>

<span data-ttu-id="37fc4-111">Ha egy `itemId` és `inventDimId` kombináció csak egy bevételezési vagy kibocsátási tranzakciót tartalmaz, a tranzakció nem lesz archiválva.</span><span class="sxs-lookup"><span data-stu-id="37fc4-111">If an `itemId` and `inventDimId` combination contains only one receipt or issue transaction, the transaction won't be archived.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="37fc4-112">A funkció bekapcsolása a rendszerben</span><span class="sxs-lookup"><span data-stu-id="37fc4-112">Turn on the feature in your system</span></span>

<span data-ttu-id="37fc4-113">Ha a rendszer még nem tartalmazza az ebben a témakörben leírt funkciókat, lépjen a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőségre, és a kapcsolja be az *Készlettranzakciók archívuma* funkciót.</span><span class="sxs-lookup"><span data-stu-id="37fc4-113">If your system doesn't already include the features that is described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Inventory transactions archive* feature.</span></span>

## <a name="things-to-consider-before-you-archive-inventory-transactions"></a><span data-ttu-id="37fc4-114">Megfontolandó szempontok a készlettranzakciók archiválását megelőzően</span><span class="sxs-lookup"><span data-stu-id="37fc4-114">Things to consider before you archive inventory transactions</span></span>

<span data-ttu-id="37fc4-115">A készlettranzakciók archiválását megelőzően figyelembe kell vennie a következő üzleti eseteket, mivel azok hatással lesznek a műveletre:</span><span class="sxs-lookup"><span data-stu-id="37fc4-115">Before you archive inventory transactions, you should consider the following business scenarios, because they will be affected by the operation:</span></span>

- <span data-ttu-id="37fc4-116">Amikor a kapcsolódó dokumentumokból – például beszerzésirendelés-sorokból – könyvvizsgálati készlettranzakciókat végez, azok archiváltként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="37fc4-116">When you audit inventory transactions from related documents, such as purchase order lines, they will be shown as archived.</span></span> <span data-ttu-id="37fc4-117">Az archivált tranzakciók ellenőrzéséhez lépjen a **Készletkezelés \> Időszakos feladatok \> Adattisztítás \> Készlettranzakciók archívuma** pontra.</span><span class="sxs-lookup"><span data-stu-id="37fc4-117">To review the archived transactions, you must go to **Inventory management \> Periodic tasks \> Clean up \> Inventory transactions archive**.</span></span>
- <span data-ttu-id="37fc4-118">Archivált időszakok esetén nem érvénytelen lehet készletzárást visszavonni.</span><span class="sxs-lookup"><span data-stu-id="37fc4-118">Inventory closing can't be canceled for archived periods.</span></span> <span data-ttu-id="37fc4-119">Készletzárás visszavonása előtt az adott időszakra vonatkozóan sztornírozni kell a készlettranzakció-archívumot.</span><span class="sxs-lookup"><span data-stu-id="37fc4-119">Before you can cancel an inventory closing, you must reverse the inventory transaction archive for the relevant period.</span></span>
- <span data-ttu-id="37fc4-120">Archivált időszakokra nem lehet elszámolóárra való átalakítást végezni.</span><span class="sxs-lookup"><span data-stu-id="37fc4-120">Standard cost conversion can't be done for archived periods.</span></span> <span data-ttu-id="37fc4-121">Elszámolóárra való átalakítás előtt az adott időszakra vonatkozóan sztornírozni kell a készlettranzakció-archívumot.</span><span class="sxs-lookup"><span data-stu-id="37fc4-121">Before you can do standard cost conversion, you must reverse the inventory transaction archive for the relevant period.</span></span>
- <span data-ttu-id="37fc4-122">A készlettranzakciókból származó készletjelentéseket befolyásolja a készlettranzakciók archiválása.</span><span class="sxs-lookup"><span data-stu-id="37fc4-122">Inventory reports that are sourced from inventory transactions will be affected when you archive inventory transactions.</span></span> <span data-ttu-id="37fc4-123">Ezek a jelentések tartalmazzák a készletkorosítási jelentést és a készletérték-jelentéseket.</span><span class="sxs-lookup"><span data-stu-id="37fc4-123">These reports include the inventory aging report and inventory value reports.</span></span>
- <span data-ttu-id="37fc4-124">A készlet-előrejelzésekre hatással lehet, ha az archivált időszakok időhorizontja alatt futnak.</span><span class="sxs-lookup"><span data-stu-id="37fc4-124">Inventory forecasts might be affected if they are run during the time horizon of archived periods.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="37fc4-125">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="37fc4-125">Prerequisites</span></span>

<span data-ttu-id="37fc4-126">A készlettranzakciók csak olyan időszakokban archiválhatók, ahol teljesülnek a következő feltételek:</span><span class="sxs-lookup"><span data-stu-id="37fc4-126">Inventory transactions can be archived only during periods where the following conditions are met:</span></span>

- <span data-ttu-id="37fc4-127">A főkönyvi időszakot le kell zárni.</span><span class="sxs-lookup"><span data-stu-id="37fc4-127">The ledger period must be closed.</span></span>
- <span data-ttu-id="37fc4-128">A készletzárást az archívum záró dátumán vagy azt követően kell futtatni.</span><span class="sxs-lookup"><span data-stu-id="37fc4-128">Inventory closing must be run on or after the to-period date of the archive.</span></span>
- <span data-ttu-id="37fc4-129">Az időszaknak legalább egy évvel az archívum időszakának kezdési dátuma előtt kell lennie.</span><span class="sxs-lookup"><span data-stu-id="37fc4-129">The period must be at least one year before the from-period date of the archive.</span></span>
- <span data-ttu-id="37fc4-130">Nem létezhetnek meglévő készlet-újraszámítások.</span><span class="sxs-lookup"><span data-stu-id="37fc4-130">There must not be any existing inventory recalculations.</span></span>

## <a name="archive-inventory-transactions"></a><span data-ttu-id="37fc4-131">Készlettranzakciók archiválása</span><span class="sxs-lookup"><span data-stu-id="37fc4-131">Archive inventory transactions</span></span>

<span data-ttu-id="37fc4-132">Készlettranzakciók archiválásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="37fc4-132">To archive inventory transactions, follow these steps.</span></span>

1. <span data-ttu-id="37fc4-133">Lépjen a **Készletkezelés** \> **Időszakos feladatok** \> **Adattisztítás** \> **Készlettranzakció archívuma** pontra.</span><span class="sxs-lookup"><span data-stu-id="37fc4-133">Go to **Inventory management** \> **Periodic tasks** \> **Clean up** \> **Inventory transaction archive**.</span></span>

    <span data-ttu-id="37fc4-134">Megjelenik a **Készlettranzakciók archívuma** oldal, és megjeleníti az archivált folyamatrekordok listáját.</span><span class="sxs-lookup"><span data-stu-id="37fc4-134">The **Inventory transactions archive** page appears and shows a list of archived process records.</span></span>

    <span data-ttu-id="37fc4-135">![Készlettranzakciók archívumának oldala](media/archive-inventory-empty.png "Készlettranzakciók archívumának oldala")</span><span class="sxs-lookup"><span data-stu-id="37fc4-135">![Inventory transactions archive page](media/archive-inventory-empty.png "Inventory transactions archive page")</span></span>

1. <span data-ttu-id="37fc4-136">A műveletpanelen válassza ki a **Készlettranzakciók archívumát** készlettranzakció-archívum létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="37fc4-136">On the Action Pane, select **Inventory transactions archive** to create an inventory transaction archive.</span></span>
1. <span data-ttu-id="37fc4-137">A **Készlettranzakciók archívuma** párbeszédpanel **Paraméterek** gyorslapján állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="37fc4-137">In the **Inventory transactions archive** dialog box, on the **Parameters** FastTab, set the following fields:</span></span>

    - <span data-ttu-id="37fc4-138">**Kezdési dátum lezárt főkönyvi időszakban** – Válassza ki a legkorábbi tranzakció dátumát, amit szerepeltetni szeretne az archívumban.</span><span class="sxs-lookup"><span data-stu-id="37fc4-138">**From date in closed ledger period** – Select the earliest transaction date to include in the archive.</span></span>
    - <span data-ttu-id="37fc4-139">**Záró dátum lezárt főkönyvi időszakban** – Válassza ki a legkésőbbi tranzakció dátumát, amit szerepeltetni szeretne az archívumban.</span><span class="sxs-lookup"><span data-stu-id="37fc4-139">**To date in closed ledger period** – Select the latest transaction date to include in the archive.</span></span>

    <span data-ttu-id="37fc4-140">![Készlettranzakciók archívumának párbeszédablaka](media/archive-inventory-dates.png "Készlettranzakciók archívumának párbeszédablaka")</span><span class="sxs-lookup"><span data-stu-id="37fc4-140">![Inventory transactions archive dialog box](media/archive-inventory-dates.png "Inventory transactions archive dialog box")</span></span>

    > [!NOTE]
    > <span data-ttu-id="37fc4-141">Csak az [előfeltételeknek](#prerequisites) megfelelő időszakok választhatók ki.</span><span class="sxs-lookup"><span data-stu-id="37fc4-141">Only periods that meet the [prerequisites](#prerequisites) will be available for selection.</span></span>

1. <span data-ttu-id="37fc4-142">A **Futtatás a háttérben** gyorslapon az igényeinek megfelelően állítsa be a kötegelt feldolgozás részleteit.</span><span class="sxs-lookup"><span data-stu-id="37fc4-142">On the **Run in the background** FastTab, set up batch processing details as you require.</span></span> <span data-ttu-id="37fc4-143">Kövesse a Microsoft Dynamics 365 Supply Chain Management kötegelt feladatokkal kapcsolatos általános lépéseit.</span><span class="sxs-lookup"><span data-stu-id="37fc4-143">Follow the usual steps for batch jobs in Microsoft Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="37fc4-144">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="37fc4-144">Select **OK**.</span></span>
1. <span data-ttu-id="37fc4-145">Egy üzenet jelenik meg, amely arra kéri, hogy erősítse meg a folytatást.</span><span class="sxs-lookup"><span data-stu-id="37fc4-145">You receive a message that prompts you to confirm that you want to continue.</span></span> <span data-ttu-id="37fc4-146">Olvassa el alaposan az üzenetet, majd kattintson az **Igen** gombra, ha folytatni szeretné.</span><span class="sxs-lookup"><span data-stu-id="37fc4-146">Read the message carefully, and then select **Yes** if you want to continue.</span></span>

    <span data-ttu-id="37fc4-147">Egy üzenet jelenik meg, amely jelzi, hogy a készlettranzakciók archiválási feladata felkerült a köteg feldolgozási sorára.</span><span class="sxs-lookup"><span data-stu-id="37fc4-147">You receive a message that states that your inventory transactions archive job has been added to the batch queue.</span></span> <span data-ttu-id="37fc4-148">A feladat elindul a kijelölt időszak készlettranzakcióinak archiválására.</span><span class="sxs-lookup"><span data-stu-id="37fc4-148">The job will now start to archive inventory transactions from the selected period.</span></span>

## <a name="view-archived-inventory-transactions"></a><span data-ttu-id="37fc4-149">Archivált készlettranzakciók megtekintése</span><span class="sxs-lookup"><span data-stu-id="37fc4-149">View archived inventory transactions</span></span>

<span data-ttu-id="37fc4-150">A **Készlettranzakciók archívuma** oldal a teljes archiválási előzményeket mutatja.</span><span class="sxs-lookup"><span data-stu-id="37fc4-150">The **Inventory transactions archive** page shows your full archiving history.</span></span> <span data-ttu-id="37fc4-151">A rács minden sorában olyan adatok láthatók, mint például az archívum létrehozási dátuma, az a felhasználó, aki létrehozta, valamint annak állapota.</span><span class="sxs-lookup"><span data-stu-id="37fc4-151">Each row in the grid shows information such as the date when the archive was created, the user who created it, and its status.</span></span>

<span data-ttu-id="37fc4-152">![Készlettranzakciók archívumának oldalán található archiválási előzmények](media/archive-inventory-full.png "Készlettranzakciók archívumának oldalán található archiválási előzmények")</span><span class="sxs-lookup"><span data-stu-id="37fc4-152">![Archiving history on the Inventory transactions archive page](media/archive-inventory-full.png "Archiving history on the Inventory transactions archive page")</span></span>

<span data-ttu-id="37fc4-153">Az oldal tetején lévő legördülő listából válasszon a következő értékek közül a rácsban látható archívum szűréséhez:</span><span class="sxs-lookup"><span data-stu-id="37fc4-153">In the drop-down list at the top of the page select one of the following values to filter the archives that are shown in the grid:</span></span>

- <span data-ttu-id="37fc4-154">**Aktív** – Csak az aktív archívumok megjelenítése, a sztornírozott archívumok nem.</span><span class="sxs-lookup"><span data-stu-id="37fc4-154">**Active** – Show only active archives, not reversed archives.</span></span>
- <span data-ttu-id="37fc4-155">**Összes** – Minden archívum megjelenítése, aktív és sztornírozva is.</span><span class="sxs-lookup"><span data-stu-id="37fc4-155">**All** – Show all archives, both active and reversed.</span></span>

<span data-ttu-id="37fc4-156">A rács minden egyes archívumához a következő információk biztosítanak:</span><span class="sxs-lookup"><span data-stu-id="37fc4-156">For each archive in the grid, the following information is provided:</span></span>

- <span data-ttu-id="37fc4-157">**Aktív** – A bejelölés jelzi, hogy az archívum aktív.</span><span class="sxs-lookup"><span data-stu-id="37fc4-157">**Active** – A check mark indicates that the archive is active.</span></span>
- <span data-ttu-id="37fc4-158">**Kezdési dátum** – Az archívumba kerülő legrégebbi tranzakció dátuma.</span><span class="sxs-lookup"><span data-stu-id="37fc4-158">**From date** – The date of the oldest transaction that can be included in the archive.</span></span>
- <span data-ttu-id="37fc4-159">**Záró dátum** – Az archívumba kerülő legújabb tranzakció dátuma.</span><span class="sxs-lookup"><span data-stu-id="37fc4-159">**To date** – The date of the latest transaction that can be included in the archive.</span></span>
- <span data-ttu-id="37fc4-160">**Ütemezte** – Az archívumot létrehozó felhasználói fiók.</span><span class="sxs-lookup"><span data-stu-id="37fc4-160">**Scheduled by** – The user account that created the archive.</span></span>
- <span data-ttu-id="37fc4-161">**Végrehajtva** – Az archívum létrehozásának dátuma.</span><span class="sxs-lookup"><span data-stu-id="37fc4-161">**Executed** – The date when the archive was created.</span></span>
- <span data-ttu-id="37fc4-162">**Sztornírozás** – A jelölés azt jelzi, hogy az archívum sztornózva lett.</span><span class="sxs-lookup"><span data-stu-id="37fc4-162">**Reverse** – A check mark indicates that the archive has been reversed.</span></span>
- <span data-ttu-id="37fc4-163">**Aktuális frissítés leállítása** - A jelölés azt jelzi, hogy az archívum folyamatban van, de szünetel.</span><span class="sxs-lookup"><span data-stu-id="37fc4-163">**Stop current update** – A check mark indicates that the archive is in progress, but it has been paused.</span></span>
- <span data-ttu-id="37fc4-164">**Állapot** – Az archívum feldolgozási állapota.</span><span class="sxs-lookup"><span data-stu-id="37fc4-164">**State** – The processing status of the archive.</span></span> <span data-ttu-id="37fc4-165">A lehetséges értékek: *Várakozás*, *Folyamatban* és *Kész*.</span><span class="sxs-lookup"><span data-stu-id="37fc4-165">The possible values are *Waiting*, *In progress*, and *Finished*.</span></span>

<span data-ttu-id="37fc4-166">A rács feletti eszköztár a következő gombokat tartalmazza, amelyek a kiválasztott archívummal való munkára használhatók:</span><span class="sxs-lookup"><span data-stu-id="37fc4-166">The toolbar above the grid provides the following buttons that you can use to work with a selected archive:</span></span>

- <span data-ttu-id="37fc4-167">**Archivált tranzakciók** – a kijelölt archívum részletes megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="37fc4-167">**Archived transactions** – View the full details of the selected archive.</span></span> <span data-ttu-id="37fc4-168">A megjelenő **Archivált tranzakciók** oldal az archívum összes tranzakcióját megjeleníti.</span><span class="sxs-lookup"><span data-stu-id="37fc4-168">The **Archived transactions** page that appears shows all the transactions in the archive.</span></span>

    <span data-ttu-id="37fc4-169">![Archivált tranzakciók oldala](media/archive-inventory-transactions.png "Archivált tranzakciók oldala")</span><span class="sxs-lookup"><span data-stu-id="37fc4-169">![Archived transactions page](media/archive-inventory-transactions.png "Archived transactions page")</span></span>

    <span data-ttu-id="37fc4-170">Ha az **Archivált tranzakciók** lapon egy adott tranzakcióval kapcsolatban további információkat is meg kell jeleníteni, jelölje ki azt a rácsban, majd a műveleti ablaktáblán válassza ki az **Archivált tranzakció részletei** elemet.</span><span class="sxs-lookup"><span data-stu-id="37fc4-170">To view more information about a specific transaction on the **Archived transactions** page, select it in the grid, and then, on the Action Pane, select **Archived transaction details**.</span></span> <span data-ttu-id="37fc4-171">A megjelenő **Archivált tranzakció részletei** oldalon olyan adatok jelennek meg, mint a főkönyvi elszámolás, a kapcsolódó részfőkönyv hivatkozásai és a pénzügyi dimenziók.</span><span class="sxs-lookup"><span data-stu-id="37fc4-171">The **Archived transaction details** page that appears shows information such as the ledger posting, related subledger references, and financial dimensions.</span></span>

- <span data-ttu-id="37fc4-172">**Az archiválás szüneteltetése** – A jelenleg feldolgozás alatt álló kijelölt archívum szüneteltetése.</span><span class="sxs-lookup"><span data-stu-id="37fc4-172">**Pause archiving** – Pause a selected archive that is currently being processed.</span></span> <span data-ttu-id="37fc4-173">A szünet csak az archiválási feladat létrehozása után lép életbe.</span><span class="sxs-lookup"><span data-stu-id="37fc4-173">The pause takes effect only after the archiving task has been generated.</span></span> <span data-ttu-id="37fc4-174">Emiatt előfordulhat egy kis késés a szünet hatályba lépése előtt.</span><span class="sxs-lookup"><span data-stu-id="37fc4-174">Therefore, there might be a short delay before the pause takes effect.</span></span> <span data-ttu-id="37fc4-175">Ha egy archívum szünetel, az **Aktuális frissítés leállítása** mezőben megjelenik egy pipa.</span><span class="sxs-lookup"><span data-stu-id="37fc4-175">If an archive has been paused, a check mark appears in its **Stop current update** field.</span></span>
- <span data-ttu-id="37fc4-176">**Az archiválás folytatása** – A jelenleg szünetelő kijelölt archívum feldolgozásának folytatása.</span><span class="sxs-lookup"><span data-stu-id="37fc4-176">**Resume archiving** – Resume processing for a selected archive that is currently paused.</span></span>
- <span data-ttu-id="37fc4-177">**Sztornírozás** – A kijelölt archívum sztornírozása.</span><span class="sxs-lookup"><span data-stu-id="37fc4-177">**Reverse** – Reverse the selected archive.</span></span> <span data-ttu-id="37fc4-178">Az archívum csak akkor sztornírozható, ha az **Állapot** mező beállítása *Kész*.</span><span class="sxs-lookup"><span data-stu-id="37fc4-178">You can reverse an archive only if its **State** field is set to *Finished*.</span></span> <span data-ttu-id="37fc4-179">Ha egy archívum sztornírozva van, a **Sztornírozás** mezőben megjelenik egy pipa.</span><span class="sxs-lookup"><span data-stu-id="37fc4-179">If an archive has been reversed, a check mark appears in its **Reverse** field.</span></span>
