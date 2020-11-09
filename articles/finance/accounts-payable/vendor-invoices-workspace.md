---
title: Szállítói számla bevitele munkaterület
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a szállítói számlákkal kapcsolatos munkaterületet, valamint bemutatja a Microsoft Power BI szolgáltatáson keresztül elérhető adatokat.
author: abruer
manager: AnnBe
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2020-09-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a4ba676d9b6df69cf0a91862bcc4d2837b7cb69e
ms.sourcegitcommit: afc43699c0edc4ff2be310cb37add2ab586b64c0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/14/2020
ms.locfileid: "4000795"
---
# <a name="vendor-invoice-entry-workspace"></a><span data-ttu-id="d613e-103">Szállítói számla bevitele munkaterület</span><span class="sxs-lookup"><span data-stu-id="d613e-103">Vendor invoice entry workspace</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="d613e-104">Ez a témakör azt mutatja be, hogyan lehet beállítani a szállítói számlákkal kapcsolatos munkaterületet, valamint bemutatja a Microsoft Power BI szolgáltatáson keresztül elérhető adatokat.</span><span class="sxs-lookup"><span data-stu-id="d613e-104">This topic explains how to set up the workspace that is related to vendor invoices and that shows the information that is available through Microsoft Power BI.</span></span> <span data-ttu-id="d613e-105">A munkaterület szállítói számlájának adatait a program a meghatározott felhasználók számára szűri, és grafikus formában jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="d613e-105">The vendor invoice information in this workspace is filtered for specific users and is shown in a graphical format.</span></span>

## <a name="overview"></a><span data-ttu-id="d613e-106">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="d613e-106">Overview</span></span>

<span data-ttu-id="d613e-107">A **Szállítói számla bevitele** munkaterület a szállítói számlák feldolgozásához kapcsolódó információkat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="d613e-107">The **Vendor invoice entry** workspace shows information that is related to vendor invoice processing.</span></span> <span data-ttu-id="d613e-108">Tartalmaz egy **Saját munka** és egy **Elemzés – az összes vállalat** nézetet.</span><span class="sxs-lookup"><span data-stu-id="d613e-108">It includes a **My work** view and an **Analytics - All companies** page.</span></span> <span data-ttu-id="d613e-109">A **Saját munka** nézet összesítő lapokat, szállítói tranzakciórácsokat és a kapcsolódó szállítói adatokat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="d613e-109">The **My work** view shows summary tiles, vendor transaction grids, and related vendor information.</span></span> <span data-ttu-id="d613e-110">Az **Elemzés - az összes vállalat** lap a Power BI lehetőségeit kihasználva a szállítói számlákkal kapcsolatos vizualizációkat jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="d613e-110">The **Analytics - All companies** page uses the capabilities of Power BI to show visualizations that are related to vendor invoices.</span></span>

## <a name="set-up-the-workspace-to-show-power-bi-content"></a><span data-ttu-id="d613e-111">A munkaterület beállítása a Power BI-tartalom megjelenítésére</span><span class="sxs-lookup"><span data-stu-id="d613e-111">Set up the workspace to show Power BI content</span></span>

<span data-ttu-id="d613e-112">Ezt a beállítást végre kell hajtania, mielőtt a Power BI a **Szállítói számla bevitele** munkaterületen megjeleníthetné az adatokat.</span><span class="sxs-lookup"><span data-stu-id="d613e-112">You must complete this setup before data can be shown in Power BI visualizations in the **Vendor invoice entry** workspace.</span></span>

1. <span data-ttu-id="d613e-113">A **Funkciókezelés** munkaterületen szűrje a listát, és keresse meg a **Szállítói számla automatizálása** funkciót.</span><span class="sxs-lookup"><span data-stu-id="d613e-113">In the **Feature management** workspace, filter the list to find the **Vendor invoice automation** feature.</span></span>
3. <span data-ttu-id="d613e-114">Válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d613e-114">Select **Enable now**.</span></span>
4. <span data-ttu-id="d613e-115">A szállítói számla munkafolyamatának beállításával biztosíthatja, hogy a számlák manuális beavatkozás nélkül is teljes egészükben feldolgozhatók legyenek.</span><span class="sxs-lookup"><span data-stu-id="d613e-115">To ensure that invoices can be processed from beginning to end without requiring manual intervention, set up a vendor invoice workflow.</span></span> <span data-ttu-id="d613e-116">A munkafolyamat beállításához lépjen a **Kötelezettségek \> Beállítás \> Kötelezettségek munkafolyamatai** felületre.</span><span class="sxs-lookup"><span data-stu-id="d613e-116">To set up a workflow, go to **Accounts payable \> Setup \> Accounts payable workflows**.</span></span>
5. <span data-ttu-id="d613e-117">Nyissa meg a **Kötelezettségek \> Beállítás \> Kötelezettségek paraméterei** lehetőséget, és válassza ki a **Szállítói számla automatizálása** lapot. További tájékoztatás a következő témakörben található: [A szállítói számla automatizálásának beállítási lehetőségei](vnd-invoice-set-up-options.md).</span><span class="sxs-lookup"><span data-stu-id="d613e-117">Go to **Accounts payable \> Setup \> Accounts payable parameters** , and select the **Vendor invoice automation** tab. For more information, see [Setup options for vendor invoice automation](vnd-invoice-set-up-options.md).</span></span>
6. <span data-ttu-id="d613e-118">Állítsa az **Importált számlák automatikus elküldése a munkafolyamat-rendszerbe** értéket erre: **Igen**.</span><span class="sxs-lookup"><span data-stu-id="d613e-118">Set the **Automatically submit imported invoices to workflow** option to **Yes**.</span></span>
7. <span data-ttu-id="d613e-119">Ha a termékek számláit automatikusan kell egyeztetni, akkor a **Terméknyugták automatikus egyeztetése a számlasorokkal** beállítása legyen **Igen**.</span><span class="sxs-lookup"><span data-stu-id="d613e-119">If product receipts should automatically be matched, set the **Automatically match product receipts to invoices lines** option to **Yes**.</span></span>
8. <span data-ttu-id="d613e-120">Tekintse át a további, nem kötelező beállításokat, és konfigurálja azokat a szervezet igényei szerint.</span><span class="sxs-lookup"><span data-stu-id="d613e-120">Review the remaining, optional settings, and configure them according to your organization's requirements.</span></span>
9. <span data-ttu-id="d613e-121">Nyissa meg a **Rendszerfelügyelet \> Beállítás \> Rendszerparaméterek** pontot, és állítsa be a **Rendszerpénznem** és a **Rendszerváltási árfolyam** mezőket.</span><span class="sxs-lookup"><span data-stu-id="d613e-121">Go to **System administration \> Setup \> System parameters** , and set the **System currency** and **System exchange rate** fields.</span></span>
10. <span data-ttu-id="d613e-122">Lépjen a **Főkönyv \> Beállítás \> Főkönyv** részre, és állítsa be a **Könyvelési pénznem** és az **Árfolyamtípus** mezőket.</span><span class="sxs-lookup"><span data-stu-id="d613e-122">Go to **General ledger \> Setup \> Ledger** , and set the **Accounting currency** and **Exchange rate type** fields.</span></span>
11. <span data-ttu-id="d613e-123">Lépjen a **Főkönyv \> Pénznemek \> Devizaárfolyamok** részre, és adja meg a tranzakció pénzneme és a könyvelési pénznem közötti átváltási árfolyamokat, valamint a könyvelési pénznem és a rendszer pénzneme közötti átváltási árfolyamokat.</span><span class="sxs-lookup"><span data-stu-id="d613e-123">Go to **General ledger \> Currencies \> Currency exchange rates** , and enter the exchange rates between the transaction currency and the accounting currency, and between the accounting currency and the system currency.</span></span>
12. <span data-ttu-id="d613e-124">Lépjen a **Rendszerfelügyelet \> Beállítás \> Entitástár** részre, és keresse meg a **Szállítói számla automatizálási eljárása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d613e-124">Go to **System administration \> Setup \> Entity store** , and look for **Vendor invoice automation measure**.</span></span> <span data-ttu-id="d613e-125">Válassza a **Frissítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d613e-125">Select **Refresh**.</span></span>

<span data-ttu-id="d613e-126">Ha meg szeretné tekinteni a munkaterületen megjelenő adatokat, rendelkeznie kell a Kötelezettségek kezelője vagy a Kötelezettségek könyvelője biztonsági szerepkörrel.</span><span class="sxs-lookup"><span data-stu-id="d613e-126">To view the information that displayed in the workspace, you must have the Accounts payable manager or Accounts payable clerk security role.</span></span>

## <a name="my-work-view"></a><span data-ttu-id="d613e-127">Saját munka nézet</span><span class="sxs-lookup"><span data-stu-id="d613e-127">My work view</span></span>

### <a name="company-selection"></a><span data-ttu-id="d613e-128">Vállalat választása</span><span class="sxs-lookup"><span data-stu-id="d613e-128">Company selection</span></span>

<span data-ttu-id="d613e-129">Amikor a **Szállítói számlák automatizálása** funkciót bekapcsolta, a munkaterület felső részén megjelenik egy **Vállalat** mező.</span><span class="sxs-lookup"><span data-stu-id="d613e-129">When the **Automate vendor invoices** feature is turned on, a **Company** field appears at the top of the workspace.</span></span> <span data-ttu-id="d613e-130">A **Vállalat** mezőben kiválasztott érték a munkaterületen megjelenített összes adatot érinti.</span><span class="sxs-lookup"><span data-stu-id="d613e-130">The selection in the **Company** field affects all the information displayed in the workspace.</span></span> <span data-ttu-id="d613e-131">Alapértelmezetten a nézet annak a vállalatnak az adatait jeleníti meg, amelyikbe bejelentkezett.</span><span class="sxs-lookup"><span data-stu-id="d613e-131">By default, the view shows information for the company that you signed in to.</span></span> <span data-ttu-id="d613e-132">Ha egy másik vállalatot választ ki a **Vállalat** mezőben, akkor a munkaterületen megjelenítheti a vállalat adatait.</span><span class="sxs-lookup"><span data-stu-id="d613e-132">By selecting a different company in the **Company** field, you can show information for that company on the workspace.</span></span> <span data-ttu-id="d613e-133">Ezután kiválaszthat egy csempét a munkaterületen, ha a kiválasztott vállalat kapcsolódó lapjára lépjen.</span><span class="sxs-lookup"><span data-stu-id="d613e-133">You can then select a tile in the workspace to go the related page in the selected company.</span></span>

### <a name="summary-tiles"></a><span data-ttu-id="d613e-134">Összesítő csempék</span><span class="sxs-lookup"><span data-stu-id="d613e-134">Summary tiles</span></span>

<span data-ttu-id="d613e-135">A **Saját munka** nézet **Függőben levő számlák összegzése** mozaikja áttekintést ad a szállítói számlák állapotáról.</span><span class="sxs-lookup"><span data-stu-id="d613e-135">The tiles in the **Summary of pending invoices** section of the **My work** view give an overview of the state of your vendor invoices.</span></span> <span data-ttu-id="d613e-136">Láthatók a még fel nem adott naplók és a várakoztatott számlák.</span><span class="sxs-lookup"><span data-stu-id="d613e-136">You can see journals that aren't yet posted and invoices that are on hold.</span></span> <span data-ttu-id="d613e-137">Ezenkívül az alábbi négy csempe tartozik a Szállítói számla automatizálása funkcióhoz:</span><span class="sxs-lookup"><span data-stu-id="d613e-137">In addition, there are the four tiles that are associated with the Vendor invoice automation feature:</span></span>

- <span data-ttu-id="d613e-138">Manuális bevételezés egyeztetése szükséges</span><span class="sxs-lookup"><span data-stu-id="d613e-138">Manual receipt match needed</span></span>
- <span data-ttu-id="d613e-139">Egyeztetés ellenőrzése sikertelen</span><span class="sxs-lookup"><span data-stu-id="d613e-139">Matching validation not successful</span></span>
- <span data-ttu-id="d613e-140">A munkafolyamatba nem beküldött számlák</span><span class="sxs-lookup"><span data-stu-id="d613e-140">Invoices not submitted to workflow</span></span>
- <span data-ttu-id="d613e-141">Nem importált számlák</span><span class="sxs-lookup"><span data-stu-id="d613e-141">Invoices not imported</span></span>

<span data-ttu-id="d613e-142">(A négy csempe meglétéhez a Szállítói számla automatizálása funkciót be kell kapcsolni a Funkciókezelés részben.)</span><span class="sxs-lookup"><span data-stu-id="d613e-142">(These four tiles require that the Vendor invoice automation feature be turned on in Feature management.)</span></span>

<span data-ttu-id="d613e-143">A **Szállítói számlák helyreállítása** lap használatához a funkciót be kell kapcsolni a Kötelezettségek paraméterei részben.</span><span class="sxs-lookup"><span data-stu-id="d613e-143">To use the **Recover vendor invoices** tile, the feature must be turned on in Accounts payable parameters.</span></span> <span data-ttu-id="d613e-144">Nyissa meg a **Kötelezettségek \> Kötelezettségek paraméterei** részt, majd a **Számla** lapon állítsa a **Szállítói számla helyreállításának engedélyezése** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="d613e-144">Go to **Accounts payable \> Accounts payable parameters** , and then, on the **Invoice** tab, set the **Allow vendor invoice recovery** option to **Yes**.</span></span>

<span data-ttu-id="d613e-145">Amikor a funkció be van kapcsolva, a munkaterületen három csempe együtt szerepel a munkaterület **Naplók** nevű szakaszában.</span><span class="sxs-lookup"><span data-stu-id="d613e-145">When the feature is turned on, you will also three tiles grouped together on the workspace in a section called **Journals**.</span></span> <span data-ttu-id="d613e-146">A csempék címei: **Naplók** , **Naplók – Hozzám rendelve** és **Számlagyűjtő**.</span><span class="sxs-lookup"><span data-stu-id="d613e-146">The tiles are titled **Journals** , **Journals - Assigned to me** , and **Invoice pool**.</span></span> 

<span data-ttu-id="d613e-147">A **Függőben levő számlák összegzése** szakaszá adatai arra a vállalatra szerepelnek, amely a bejelentkezéskori alapértelmezett vállalat.</span><span class="sxs-lookup"><span data-stu-id="d613e-147">The information in the **Summary of pending invoices** section is for the company that is set as the default company for your sign-in.</span></span>

### <a name="creating-new-records"></a><span data-ttu-id="d613e-148">Új jelentések létrehozása</span><span class="sxs-lookup"><span data-stu-id="d613e-148">Creating new records</span></span>

<span data-ttu-id="d613e-149">Új számlázási rekord létrehozásához válassza az **Új** lehetőséget, majd válassza ki a listából az alábbi rekordtípusok egyikét:</span><span class="sxs-lookup"><span data-stu-id="d613e-149">To create a new invoice record, select **New** , and then select one of the following record types in the list:</span></span>

- <span data-ttu-id="d613e-150">Szállítói számla</span><span class="sxs-lookup"><span data-stu-id="d613e-150">Vendor invoice</span></span>
- <span data-ttu-id="d613e-151">Számlanapló</span><span class="sxs-lookup"><span data-stu-id="d613e-151">Invoice journal</span></span>
- <span data-ttu-id="d613e-152">Globális számlanapló</span><span class="sxs-lookup"><span data-stu-id="d613e-152">Global invoice journal</span></span>
- <span data-ttu-id="d613e-153">Számlajegyzék</span><span class="sxs-lookup"><span data-stu-id="d613e-153">Invoice register</span></span>
- <span data-ttu-id="d613e-154">Számla jóváhagyása</span><span class="sxs-lookup"><span data-stu-id="d613e-154">Invoice approval</span></span>

<span data-ttu-id="d613e-155">Ne feledje, hogy a létrehozott rekord az illető vállalat szűrőjén alapul, és nem azén a vállalatén, amelyhez be van jelentkezve.</span><span class="sxs-lookup"><span data-stu-id="d613e-155">Note that the record that you create is based on the company filter, not the company that you're signed in to.</span></span> <span data-ttu-id="d613e-156">Például be van jelentkezve az **UMSF** vállalatba, de a vállalat szűrőjének beállítása **GBSI**.</span><span class="sxs-lookup"><span data-stu-id="d613e-156">For example, you're signed in to the **UMSF** company, but the company filter is set to **GBSI**.</span></span> <span data-ttu-id="d613e-157">Ebben az esetben az **Új** elem kiválasztása, majd a lista bejegyzéstípusának kiválasztása esetén a rekord a GBSI vállalatban jön létre.</span><span class="sxs-lookup"><span data-stu-id="d613e-157">In this case, when you select **New** and then select a record type in the list, the record is created in the GBSI company.</span></span>

### <a name="documents-not-invoiced-grids"></a><span data-ttu-id="d613e-158">Nem számlázott dokumentumok rácsa</span><span class="sxs-lookup"><span data-stu-id="d613e-158">Documents not invoiced grids</span></span>

<span data-ttu-id="d613e-159">A **Nem számlázott dokumentumok** szakasz olyan rácsokat tartalmaz, amelyek a szállítói számlára várakozó dokumentumokat jelenítenek meg.</span><span class="sxs-lookup"><span data-stu-id="d613e-159">The **Documents not invoiced** section contains grids that show documents that are awaiting vendor invoices.</span></span>

<span data-ttu-id="d613e-160">A **Nyitott beszerzési rendelések** rács azokat a beszerzési rendeléseket jeleníti meg, amelyek még nincsenek teljes mértékben számlázva.</span><span class="sxs-lookup"><span data-stu-id="d613e-160">The **Open purchase orders** grid shows all purchase orders that aren't yet fully invoiced.</span></span> <span data-ttu-id="d613e-161">A **Számlázás most** gombbal létrehozhatja a beszerzési rendelés szállítói számláját.</span><span class="sxs-lookup"><span data-stu-id="d613e-161">You can use the **Invoice now** button to create a vendor invoice for a purchase order.</span></span> <span data-ttu-id="d613e-162">Az **Előlegszámlázás most** gombbal létrehozhatja a szállítási rendelés előlegszámláját.</span><span class="sxs-lookup"><span data-stu-id="d613e-162">You can use the **Prepayment invoice now** button to create a prepayment invoice for a purchase order.</span></span>

<span data-ttu-id="d613e-163">A **Termékbevételezések** rács azokat a termékbevételezési tranzakciókat jeleníti meg, amelyek még nincsenek teljes mértékben számlázva.</span><span class="sxs-lookup"><span data-stu-id="d613e-163">The **Product receipts** grid shows purchase receipt transactions that aren't yet fully invoiced.</span></span> <span data-ttu-id="d613e-164">A **Számlázás most** gombbal létrehozhatja a beszerzési rendelés szállítói számláját.</span><span class="sxs-lookup"><span data-stu-id="d613e-164">You can use the **Invoice now** button to create a vendor invoice for a purchase order.</span></span>

<span data-ttu-id="d613e-165">A **Függőben levő szállítói számlák** rács a munkafolyamat-rendszerbe nem beküldött összes szállítói számlát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="d613e-165">The **Pending vendor invoices** grid shows all vendor invoices that haven't been submitted to the workflow system.</span></span> <span data-ttu-id="d613e-166">A **Keresés** mező és/vagy a vállalat szűrője egy adott szállítói számla keresésére használható.</span><span class="sxs-lookup"><span data-stu-id="d613e-166">You can use the **Search** field and/or the company filter to search for a specific vendor invoice.</span></span> <span data-ttu-id="d613e-167">A **Szerkesztés** gombbal szerkesztheti a rácsban megjelenő tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="d613e-167">You can use the **Edit** button to edit a transaction that appears in the grid.</span></span>

<span data-ttu-id="d613e-168">A **Beszerzési rendelési keresése** rács **Keresés** mezőjével keresheti meg az adott beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="d613e-168">On the **Find purchase order** grid, you can use the **Search** field to search for a specific purchase order.</span></span>

### <a name="related-information"></a><span data-ttu-id="d613e-169">Kapcsolódó információ</span><span class="sxs-lookup"><span data-stu-id="d613e-169">Related information</span></span>

<span data-ttu-id="d613e-170">A feladott számlákkal kapcsolatos információkat a munkaterület jobb oldalán található hivatkozásokkal tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="d613e-170">You can view information about posted invoices by using the links on the right side of the workspace.</span></span> <span data-ttu-id="d613e-171">Ilyen hivatkozások a **Nyitott szállítói számlák** , a **Számlázási napló** és a **Számlázási előzmények és egyeztetési részletek**.</span><span class="sxs-lookup"><span data-stu-id="d613e-171">These links include **Open vendor invoices** , **Invoice journal** , and **Invoice history and matching details**.</span></span> <span data-ttu-id="d613e-172">A **Szállítók** szakaszban hozzáférhet egy szűrt listához, amely megjeleníti az összes várakoztatott szállítót, vagy használhatja az **Összes szállító** hivatkozást is.</span><span class="sxs-lookup"><span data-stu-id="d613e-172">In the **Vendors** section, you can access a filtered list that shows all vendors that are on hold, or you can use the **All vendors** link.</span></span> <span data-ttu-id="d613e-173">Elérhetők ezenkívül az **Összes beszerzési rendelés** és az **Előlegek megnyitása** hivatkozások.</span><span class="sxs-lookup"><span data-stu-id="d613e-173">**All purchase orders** and **Open prepayments** links are also available.</span></span>

### <a name="analytics--all-companies-page"></a><span data-ttu-id="d613e-174">Elemzés – az összes vállalat oldal</span><span class="sxs-lookup"><span data-stu-id="d613e-174">Analytics – All companies page</span></span>

<span data-ttu-id="d613e-175">Amikor az **Importált számlák automatikus elküldése a munkafolyamat-rendszerbe** beállítás értéke a **Kötelezettségek paraméterei** lapon **Igen** , megtekintheti az automatizálási elemzéseket.</span><span class="sxs-lookup"><span data-stu-id="d613e-175">When the **Automatically submit imported invoices to workflow** option is set to **Yes** on the **Accounts payable parameters** page, you can view automation analytics.</span></span> <span data-ttu-id="d613e-176">Az **Elemzésel – az össze vállalat** lap fontos metrikákat tartalmaz, például a jóváhagyó és a vállalat által jóváhagyott szállítói számlákat.</span><span class="sxs-lookup"><span data-stu-id="d613e-176">The **Analytics - All companies** page provides important metrics, such as vendor invoices that are in approval by approver and by company.</span></span> <span data-ttu-id="d613e-177">Ezen a lapon öt jelentéslap található.</span><span class="sxs-lookup"><span data-stu-id="d613e-177">This page contains five report pages.</span></span> <span data-ttu-id="d613e-178">Egyik lapon egy áttekintés található, a többi lap a Kötelezettségek automatizálás metrikáival kapcsolatos részletes adatokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="d613e-178">One page provides an overview, and the other pages provide details about Accounts payable automation metrics.</span></span>

<span data-ttu-id="d613e-179">Az alábbi táblázat mutatja be az egyes jelentésoldalakon rendelkezésre álló megjelenítéseket.</span><span class="sxs-lookup"><span data-stu-id="d613e-179">The following table shows the visualizations that are available on each report page.</span></span>

| <span data-ttu-id="d613e-180">Jelentéslap</span><span class="sxs-lookup"><span data-stu-id="d613e-180">Report page</span></span>                    | <span data-ttu-id="d613e-181">Vizualizációk</span><span class="sxs-lookup"><span data-stu-id="d613e-181">Visualizations</span></span> |
|--------------------------------|----------------|
| <span data-ttu-id="d613e-182">Szállítói számla áttekintése</span><span class="sxs-lookup"><span data-stu-id="d613e-182">Vendor invoice overview</span></span>        | <ul><li><span data-ttu-id="d613e-183">Függőben levő, jelenleg automatizált szállítói számlák a rendszer pénznemében</span><span class="sxs-lookup"><span data-stu-id="d613e-183">Pending vendor invoices in automation in system currency</span></span></li><li><span data-ttu-id="d613e-184">Sikertelenül importált számlák</span><span class="sxs-lookup"><span data-stu-id="d613e-184">Invoices that failed to import</span></span></li><li><span data-ttu-id="d613e-185">Számlák a munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="d613e-185">Invoices in workflow</span></span></li><li><span data-ttu-id="d613e-186">Érintés nélküli számlák az elmúlt 30 napban</span><span class="sxs-lookup"><span data-stu-id="d613e-186">Touchless invoices last 30 days</span></span></li><li><span data-ttu-id="d613e-187">Összesen automatizált számlák az elmúlt 30 napban</span><span class="sxs-lookup"><span data-stu-id="d613e-187">Total automated invoices last 30 days</span></span></li><li><span data-ttu-id="d613e-188">Nyitott számlák egyenlege a rendszer pénznemében</span><span class="sxs-lookup"><span data-stu-id="d613e-188">Balance of open invoices in system currency</span></span></li><li><span data-ttu-id="d613e-189">Meghibásodások okai, elmúlt 30 nap</span><span class="sxs-lookup"><span data-stu-id="d613e-189">Reasons for failures, last 30 days</span></span></li><li><span data-ttu-id="d613e-190">Automatikusan feldolgozott feladott számlák (százalékban kifejezve)</span><span class="sxs-lookup"><span data-stu-id="d613e-190">Percent of posted invoices that were processed automatically</span></span></li><li><span data-ttu-id="d613e-191">A számla feldolgozásához szükséges napok száma</span><span class="sxs-lookup"><span data-stu-id="d613e-191">Days to process an invoice</span></span></ul></li> |
| <span data-ttu-id="d613e-192">Automatizálási állapot</span><span class="sxs-lookup"><span data-stu-id="d613e-192">Automation status</span></span>              | <ul><li><span data-ttu-id="d613e-193">Érintés nélküli számlák az elmúlt 30 napban</span><span class="sxs-lookup"><span data-stu-id="d613e-193">Touchless invoices last 30 days</span></span></li><li><span data-ttu-id="d613e-194">A vállalat által érintetlen számlák az elmúlt 30 napban</span><span class="sxs-lookup"><span data-stu-id="d613e-194">Touchless invoices last 30 days by company</span></span></li><li><span data-ttu-id="d613e-195">A szállítócsoport által érintetlen számlák az elmúlt 30 napban</span><span class="sxs-lookup"><span data-stu-id="d613e-195">Touchless invoices last 30 days by vendor group</span></span></li><li><span data-ttu-id="d613e-196">Automatikusan feldolgozott feladott számlák (százalékban kifejezve)</span><span class="sxs-lookup"><span data-stu-id="d613e-196">Percent of posted invoices that were processed automatically</span></span></li><li><span data-ttu-id="d613e-197">A számla feldolgozásához szükséges napok száma</span><span class="sxs-lookup"><span data-stu-id="d613e-197">Days to process an invoice</span></span></li></ul> |
| <span data-ttu-id="d613e-198">Sikertelenül importált számlák</span><span class="sxs-lookup"><span data-stu-id="d613e-198">Invoices that failed to import</span></span> | <ul><li><span data-ttu-id="d613e-199">Sikertelenül importált számlák</span><span class="sxs-lookup"><span data-stu-id="d613e-199">Invoices that failed to import</span></span></li><li><span data-ttu-id="d613e-200">A vállalat által sikertelenül importált számlák</span><span class="sxs-lookup"><span data-stu-id="d613e-200">Invoices that failed to import by company</span></span></li></ul> |
| <span data-ttu-id="d613e-201">Az automaizálás meghibásodásának okai</span><span class="sxs-lookup"><span data-stu-id="d613e-201">Reasons for automation failure</span></span> | <ul><li><span data-ttu-id="d613e-202">Sikertelen számlázások</span><span class="sxs-lookup"><span data-stu-id="d613e-202">Invoices failed</span></span></li><li><span data-ttu-id="d613e-203">Vállalat sikertelen számlázásai</span><span class="sxs-lookup"><span data-stu-id="d613e-203">Invoices failed by company</span></span></li><li><span data-ttu-id="d613e-204">Szállítói csoport sikertelen számlázásai</span><span class="sxs-lookup"><span data-stu-id="d613e-204">Invoices failed by vendor group</span></span></li></ul> |
| <span data-ttu-id="d613e-205">Munkafolyamat állapota</span><span class="sxs-lookup"><span data-stu-id="d613e-205">Workflow status</span></span>                | <ul><li><span data-ttu-id="d613e-206">Számlák a munkafolyamatban</span><span class="sxs-lookup"><span data-stu-id="d613e-206">Invoices in workflow</span></span></li><li><span data-ttu-id="d613e-207">Szállítói számlázási munkafolyamat-példányok</span><span class="sxs-lookup"><span data-stu-id="d613e-207">Vendor invoice workflow instances</span></span></li><li><span data-ttu-id="d613e-208">Hozzárendelés jóváhagyónként</span><span class="sxs-lookup"><span data-stu-id="d613e-208">Assignment per approver</span></span></li><li><span data-ttu-id="d613e-209">Szállítói számla-munkafolyamat vállalatonként</span><span class="sxs-lookup"><span data-stu-id="d613e-209">Vendor invoice workflow per company</span></span></li><li><span data-ttu-id="d613e-210">Átlagos napok a munkafolyamatban a jóváhagyó szerint</span><span class="sxs-lookup"><span data-stu-id="d613e-210">Average days in workflow by approver</span></span></li></ul> |