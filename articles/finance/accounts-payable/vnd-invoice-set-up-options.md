---
title: A szállítói számla automatizálásának beállítási lehetőségei (előzetes verzió)
description: Ez a témakör a szállítóiszámla-automatizálás beállításának és konfigurálásának lehetőségeit ismerteti.
author: abruer
manager: AnnBe
ms.date: 08/30/2020
ms.topic: articl
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: eedc5ae1ed20da4c506b3510eaeac32c0ada3b70
ms.sourcegitcommit: 6ffbae02de2eee1f3be9bab2da37a3771aae8bec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2020
ms.locfileid: "3905016"
---
# <a name="setup-options-for-vendor-invoice-automation-preview"></a><span data-ttu-id="6da06-103">A szállítói számla automatizálásának beállítási lehetőségei (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="6da06-103">Setup options for vendor invoice automation (Preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="6da06-104">Ez a témakör a szállítóiszámla-automatizálás beállításának és konfigurálásának lehetőségeit ismerteti.</span><span class="sxs-lookup"><span data-stu-id="6da06-104">This topic describes the options that are available for setting up and configuring vendor invoice automation.</span></span> <span data-ttu-id="6da06-105">A számlázásautomatizáló szolgáltatások a következő típusú beállítási paramétereket használják:</span><span class="sxs-lookup"><span data-stu-id="6da06-105">Invoice automation features use the following types of setup parameters:</span></span>

- <span data-ttu-id="6da06-106">Az importált szállítói számlák munkafolyamat-rendszerbe történő beküldésének paraméterei és a feladott terméknyugta sorainak egyeztetése a függőben lévő szállítói számlák soraival.</span><span class="sxs-lookup"><span data-stu-id="6da06-106">Parameters for submitting imported vendor invoices to the workflow system and matching posted product receipt lines to pending vendor invoice lines.</span></span>
- <span data-ttu-id="6da06-107">A folyamatautomatizálás háttérfeladatainak paraméterei.</span><span class="sxs-lookup"><span data-stu-id="6da06-107">Parameters for process automation background tasks.</span></span> <span data-ttu-id="6da06-108">A folyamatautomatizálási keretrendszer segítségével importált szállítói számlákat küldhet a munkafolyamat-rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="6da06-108">The process automation framework is used to submit imported vendor invoices to the workflow system.</span></span> <span data-ttu-id="6da06-109">Alkalmas továbbá a feladott terméknyugta sorainak a függőben lévő szállítói számlák soraival való automatikus egyeztetésére.</span><span class="sxs-lookup"><span data-stu-id="6da06-109">It's also used to automatically match posted product receipt lines to pending vendor invoice lines.</span></span> <span data-ttu-id="6da06-110">A különböző üzleti folyamatok ezt a keretrendszert alkalmazzák annak meghatározására, hogy a kiválasztott folyamat milyen gyakorisággal fusson.</span><span class="sxs-lookup"><span data-stu-id="6da06-110">Different business processes use this framework to define how often the selected process is run.</span></span> <span data-ttu-id="6da06-111">A **terméknyugta egyeztetése a számlasorokkal** és a **Szállítói számlák beküldése a munkafolyamatba** háttérfolyamatokhoz elérhető gyakoriságok az **Óra** és a **Napi** .</span><span class="sxs-lookup"><span data-stu-id="6da06-111">The available frequencies for the **Match product receipt to invoice lines** and **Submit vendor invoices to workflow** background processes include **Hour** and **Daily** .</span></span>

<span data-ttu-id="6da06-112">Egy adott háttérfeladat beállításához vagy azzal kapcsolatos információk megtekintéséhez lépjen a **Rendszerfelügyelet \> Beállítás \> Folyamatautomatizációk** felületre, majd válassza ki a **Háttérfeladat** fület.</span><span class="sxs-lookup"><span data-stu-id="6da06-112">To set up or view information about a background task, go to **System administration \> Setup \> Process automations** , and select the **Background task** tab.</span></span>

<span data-ttu-id="6da06-113">Az importálás folyamatától a szállítói számla feladásáig teljes körű automatizálás megvalósításához be kell állítania egy szállítóiszámla-munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="6da06-113">To achieve touchless automation from the import process through vendor invoice posting, you must set up a Vendor invoice workflow.</span></span> <span data-ttu-id="6da06-114">A munkafolyamat beállításához lépjen a **Kötelezettségek > Beállítás > Kötelezettségek munkafolyamatai** felületre.</span><span class="sxs-lookup"><span data-stu-id="6da06-114">To set up a workflow, go to **Accounts payable > Setup > Accounts payable workflows** .</span></span> <span data-ttu-id="6da06-115">Ha azt szeretné, hogy a számla manuális beavatkozás nélkül is feldolgozható legyen az elejétől a végéig, akkor a munkafolyamat-konfigurációban szerepelnie kell egy automatikus feladási feladatnak.</span><span class="sxs-lookup"><span data-stu-id="6da06-115">To ensure that the invoice can be processed from start to finish without manual intervention, you must include an automated posting task in your workflow configuration.</span></span> <span data-ttu-id="6da06-116">.</span><span class="sxs-lookup"><span data-stu-id="6da06-116">.</span></span>

## <a name="parameters-for-submitting-imported-vendor-invoices-to-the-workflow-system"></a><span data-ttu-id="6da06-117">Az importált szállítói számlák munkafolyamat-rendszerbe történő elküldésének paraméterei</span><span class="sxs-lookup"><span data-stu-id="6da06-117">Parameters for submitting imported vendor invoices to the workflow system</span></span>

<span data-ttu-id="6da06-118">Az importált szállítói számlák munkafolyamat-rendszerbe történő elküldéséhez speciális paramétereket kell használni.</span><span class="sxs-lookup"><span data-stu-id="6da06-118">Specific parameters are used to submit imported vendor invoices to the workflow system.</span></span> <span data-ttu-id="6da06-119">Egyes paraméterek ezenkívül a feladott terméknyugta sorainak a függőben lévő szállítói számlák soraival való egyeztetésére szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="6da06-119">Additionally, some parameters are used to match posted product receipt lines to pending vendor invoice lines.</span></span> <span data-ttu-id="6da06-120">A **Kötelezettségek paraméterei oldal** **Szállítói számla automatizálása** lapján a beállítandó paramétereket a következő szakaszok között kell elosztani:</span><span class="sxs-lookup"><span data-stu-id="6da06-120">On the **Vendor invoice automation** tab of the **Accounts payable parameters** page, the parameters that you must set are divided between the following sections:</span></span>

- <span data-ttu-id="6da06-121">Szállítói számlák munkafolyamata</span><span class="sxs-lookup"><span data-stu-id="6da06-121">Vendor invoices workflow</span></span>
- <span data-ttu-id="6da06-122">Termékbevételezési bizonylatok automatikus egyeztetése</span><span class="sxs-lookup"><span data-stu-id="6da06-122">Match product receipts automatically</span></span>

<span data-ttu-id="6da06-123">A következő paraméterek állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="6da06-123">The following parameters are available:</span></span>

- <span data-ttu-id="6da06-124">**Importált számlák automatikus elküldése a munkafolyamatba** – Ha ezt a beállítást **Igen** értékűre állítja, akkor a program az importált számlákat automatikusan beküldi a munkafolyamat-rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="6da06-124">**Automatically submit imported invoices to workflow** – If you set this option to **Yes** , imported invoices are automatically submitted to the workflow system.</span></span> <span data-ttu-id="6da06-125">Ha a beállítás értéke **Nem** , akkor a számlákat manuálisan kell elküldenie.</span><span class="sxs-lookup"><span data-stu-id="6da06-125">If this option is set to **No** , invoices must be manually submitted.</span></span> <span data-ttu-id="6da06-126">Ha ezt a beállítást **Igen** értékre állítja, akkor az eredmények importálásától a feladásig engedélyezheti az érintés nélküli folyamatot.</span><span class="sxs-lookup"><span data-stu-id="6da06-126">By setting this option to **Yes** , you enable a touchless process from the import results through posting.</span></span>

    <span data-ttu-id="6da06-127">Ez a beállítás csak akkor állítható **Igen** értékre, ha az Ön szervezetéhez aktív szállítóiszámla-munkafolyamatot állítottak be.</span><span class="sxs-lookup"><span data-stu-id="6da06-127">You can set this option to **Yes** only if an active vendor invoice workflow is set up for your legal entity.</span></span> <span data-ttu-id="6da06-128">A munkafolyamat beállításához lépjen a **Kötelezettségek \> Beállítás \> Kötelezettségek munkafolyamatai** felületre.</span><span class="sxs-lookup"><span data-stu-id="6da06-128">To set up a workflow, go to **Accounts payable \> Setup \> Accounts payable workflow** .</span></span>

- <span data-ttu-id="6da06-129">**Terméknyugták egyeztetése a számlasorokkal az automatikus beküldés előtt** – Ha ezt a beállítást **Igen** értékűre állítja, akkor az importált számla nem küldhető be automatikusan a munkafolyamat-rendszerbe mindaddig, amíg az egyeztetett terméknyugta mennyisége nem egyezik meg a számla szerinti mennyiséggel.</span><span class="sxs-lookup"><span data-stu-id="6da06-129">**Match product receipts to invoice lines prior to automatically submitting** – If you set this option to **Yes** , the imported invoice can't automatically be submitted to the workflow system until the matched product receipt quantity equals the invoice quantity.</span></span> <span data-ttu-id="6da06-130">Ha ezt a beállítást **Igen** értékre állítja, akkor engedélyezi a feladott terméknyugták automatikus egyeztetését olyan számlasorok esetében, amelyekhez háromirányú egyeztetési irányelvet határoztak meg.</span><span class="sxs-lookup"><span data-stu-id="6da06-130">By setting this option to **Yes** , you enable automatic matching of posted product receipts to invoice lines that a three-way matching policy is defined for.</span></span> <span data-ttu-id="6da06-131">Ez a folyamat addig fog futni, amíg az egyeztetett terméknyugták mennyisége nem egyezik meg a számla szerinti mennyiséggel.</span><span class="sxs-lookup"><span data-stu-id="6da06-131">That process will run until the matched product receipt quantity equals the invoice quantity.</span></span> <span data-ttu-id="6da06-132">Ezen a ponton a program automatikusan elküldi a számlát a munkafolyamat-rendszernek.</span><span class="sxs-lookup"><span data-stu-id="6da06-132">At that point, the invoice is automatically submitted to the workflow system.</span></span>

    <span data-ttu-id="6da06-133">A „Terméknyugták egyeztetése a számlasorokkal az automatikus beküldés előtt” lehetőség akkor érhető el, ha a **Számlaegyeztetés érvényesítésének engedélyezése** beállítást kiválasztotta.</span><span class="sxs-lookup"><span data-stu-id="6da06-133">The 'Match product receipts to invoice lines prior to automatically submitting option is available only if the **Enable invoice matching validation** option is selected.</span></span> <span data-ttu-id="6da06-134">Ha ezt a lehetőséget kiválasztotta, akkor a **Terméknyugták automatikus egyeztetése a számlasorokkal** beállítás automatikusan kiválasztottá válik.</span><span class="sxs-lookup"><span data-stu-id="6da06-134">When this option is selected, the **Automatically match product receipts to invoice lines** option is automatically selected.</span></span>

- <span data-ttu-id="6da06-135">**Számított összegek egyezzenek az automatikus munkafolyamatba küldéshez tartozó importált összegekkel** – Ha ezt a beállítást **Igen** értékre állítja, akkor a számla nem küldhető el automatikusan a munkafolyamat-rendszerbe mindaddig, amíg a számlára kiszámított összegek nem egyeznek az importált összegekkel.</span><span class="sxs-lookup"><span data-stu-id="6da06-135">**Require the calculated totals to equal the imported totals for automatic workflow submission** – If you set this option to **Yes** , the invoice can't automatically be submitted to the workflow system until the totals that are calculated for the invoice equal the imported totals.</span></span> <span data-ttu-id="6da06-136">Ha ezt a beállítást **Nem** értékre állítja, akkor a számla automatikusan elküldhető a munkafolyamat-rendszerbe, de nem lehet feladni addig, amíg a kiszámított összegeket nem korrigálja úgy, hogy egyezzenek az importált összegekkel.</span><span class="sxs-lookup"><span data-stu-id="6da06-136">If this option is set to **No** , the invoice can automatically be submitted to the workflow system, but it can't be posted until the calculated totals are corrected so that they match the imported totals.</span></span> <span data-ttu-id="6da06-137">Ha nem importálja a számlaösszeget vagy az áfaösszeget, akkor ezt a beállítást **Nem** értékre kell állítani.</span><span class="sxs-lookup"><span data-stu-id="6da06-137">If you don't import the invoice amount or the sales tax amount, this option should be set to **No** .</span></span>
- <span data-ttu-id="6da06-138">**Terméknyugták automatikus egyeztetése a számlasorokkal** – Ha ezt a beállítást **Igen** értékűre állítja, akkor a háttérben történő feldolgozással elvégezhető a feladott terméknyugták automatikus egyeztetése azokkal a számlasorokkal, amelyekhez háromirányú egyeztetési irányelvet határoztak meg.</span><span class="sxs-lookup"><span data-stu-id="6da06-138">**Automatically match product receipts to invoice lines** – If you set this option to **Yes** , background processing can be used to do automatic matching of posted product receipts to invoice lines that a three-way matching policy is defined for.</span></span> <span data-ttu-id="6da06-139">Ezt a folyamatot addig futtatja a program, amíg az egyeztetett terméknyugta mennyisége nem egyezik a számla mennyiségével, vagy amíg az **Automatikus egyeztetési próbálkozások száma** mezőben megadott értéket el nem éri.</span><span class="sxs-lookup"><span data-stu-id="6da06-139">That process will run until the matched product receipt quantity equals the invoice quantity, or until the value of the **Number of times to attempt automatic matching** field is reached.</span></span> <span data-ttu-id="6da06-140">A folyamat addig futtatható, amíg a számlát el nem küldik a munkafolyamat-rendszernek.</span><span class="sxs-lookup"><span data-stu-id="6da06-140">The process can be run until the invoice has been submitted to the workflow system.</span></span>

    <span data-ttu-id="6da06-141">Ez a mező csak akkor elérhető, ha a **Számlaegyeztetés ellenőrzésének engedélyezése** lehetőséget kiválasztotta.</span><span class="sxs-lookup"><span data-stu-id="6da06-141">This option is available only if the **Enable invoice matching validation** option is selected.</span></span>

    <span data-ttu-id="6da06-142">Ha a **Terméknyugták egyeztetése a számlasorokkal az automatikus beküldés előtt** lehetőséget **Igen** értékűre állítja, akkor ez a beállítás nem állítható **Nem** értékre.</span><span class="sxs-lookup"><span data-stu-id="6da06-142">If you set the **Match product receipts to invoice lines prior to automatically matching** option to **Yes** , this option can't be set to **No** .</span></span> <span data-ttu-id="6da06-143">Ahhoz, hogy ezt a beállítást **Nem** értékűre állítsa, először a **Terméknyugták egyeztetése a számlasorokkal az automatikus beküldés előtt** lehetőséget **Nem** értékűre kell állítania.</span><span class="sxs-lookup"><span data-stu-id="6da06-143">To set this option to **No** , you must first set the **Match product receipts to invoice lines prior to automatically matching** option to **No** .</span></span>

- <span data-ttu-id="6da06-144">**Automatikus egyeztetési próbálkozások száma** – Kiválaszthatja, hogy hány alkalommal próbálja meg a rendszer egyeztetni a terméknyugtákat egy adott számlasorral, mielőtt a folyamatot sikertelenként lezárná.</span><span class="sxs-lookup"><span data-stu-id="6da06-144">**Number of times to attempt automatic matching** – Select the number of times that the system should try to match product receipts to an invoice line before it concludes that the process failed.</span></span> <span data-ttu-id="6da06-145">Ha a rendszer eléri a megadott próbálkozásszámot, a számla törlődik az automatizált feldolgozásból.</span><span class="sxs-lookup"><span data-stu-id="6da06-145">When the specified number of attempts is reached, the invoice is removed from automation processing.</span></span>
- <span data-ttu-id="6da06-146">**Érvényesítés csak akkor, amikor az egyeztetett terméknyugta-mennyiség megegyezik a számla szerinti mennyiséggel** – Ha kiválasztja ezt a beállítást, akkor a számlaegyeztetés csak akkor kerül automatikus érvényesítésre, amikor a számlasor egyeztetett terméknyugta-mennyisége megegyezik a számlasor számla szerinti mennyiségével.</span><span class="sxs-lookup"><span data-stu-id="6da06-146">**Validate only when the matched product receipt quantity is equal to the invoice quantity** – If you select this option invoice matching is automatically validated only when the matched product receipt quantity of the invoice line equals the invoice quantity of the invoice line.</span></span> <span data-ttu-id="6da06-147">Ha nincs bejelölve ez a beállítás, a program minden alkalommal érvényesíti a számlaegyeztetést, amikor a rendszer egy terméknyugtasort egy számlasorral egyeztet automatikusan.</span><span class="sxs-lookup"><span data-stu-id="6da06-147">If this option is cleared, invoice matching is validated every time that the system automatically matches a product receipt line to an invoice line.</span></span>