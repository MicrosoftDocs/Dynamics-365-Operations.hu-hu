---
title: Commerce előlegszámlák (Kelet-Európa)
description: Ez a témakör bemutatja az előzetes értesítések beállítását a Commerce megoldásban Kelet-Európa esetében.
author: epopov
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 7bdd1d99ffbc1112226fd2db168cc5fc61615b9a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798835"
---
# <a name="advance-invoices-for-commerce-for-eastern-europe"></a><span data-ttu-id="5999b-103">Commerce előlegszámlák (Kelet-Európa)</span><span class="sxs-lookup"><span data-stu-id="5999b-103">Advance invoices for Commerce for Eastern Europe</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5999b-104">Ez a témakör a kelet-európai honosításra vonatkozik, és a kereskedelemmel foglalkozik.</span><span class="sxs-lookup"><span data-stu-id="5999b-104">The information in this topic applies to the Eastern European localization and is specific to the commerce industry.</span></span>

<span data-ttu-id="5999b-105">Lengyelország, Magyarország és Csehország számára egy vevőtől Point of Sale (POS) keresztül előleg érkezése esetén adózási szempontból regisztrálni kell az előleget, és szükséges egy előzetes számla dokumentum generálása és kinyomtatása, amely tartalmazza az előleg összegét.</span><span class="sxs-lookup"><span data-stu-id="5999b-105">For Poland, Hungary, and Czech Republic, when a prepayment is received from a customer via Point of Sale (POS), the prepayment must be registered for tax purposes, and it's required to generate and print an advance invoice document that includes the prepayment amount.</span></span> <span data-ttu-id="5999b-106">Ezenkívül Lengyelországban az előzetes számlatranzakciókat fel kell adni a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="5999b-106">Additionally, for Poland, advance invoice transactions must be posted in the general ledger.</span></span>

<span data-ttu-id="5999b-107">Az értékesítési rendelés számlájának feladásakor a végső dokumentumnak tartalmaznia kell az előlegszámlát, és bármely előleget meg kell jelölni.</span><span class="sxs-lookup"><span data-stu-id="5999b-107">When the invoice for the sales order is finally posted, the final document should include the advance invoice, and any prepayments should be indicated.</span></span>

<span data-ttu-id="5999b-108">Értékesítési rendelések készítéskor a Kinnlevőségekből, manuálisan generálnia kell előlegszámlákat az itt ismertetettek szerint: [Előlegszámlák Kelet-Európa számára](https://docs.microsoft.com/dynamics365/unified-operations/financials/localizations/emea-advance-invoice).</span><span class="sxs-lookup"><span data-stu-id="5999b-108">If you generate sales orders from Accounts receivable, you must manually generate advance invoices by using the procedure in [Advance invoices for Eastern Europe](https://docs.microsoft.com/dynamics365/unified-operations/financials/localizations/emea-advance-invoice).</span></span> <span data-ttu-id="5999b-109">Ha értékesítési rendeléseket POS útján generál, a rendszer létrehozza és feladja az előlegszámlákat.</span><span class="sxs-lookup"><span data-stu-id="5999b-109">If you generate sales orders via POS, the system generates and posts the advance invoices for you.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="5999b-110">Támogatott esetek</span><span class="sxs-lookup"><span data-stu-id="5999b-110">Supported scenarios</span></span>

<span data-ttu-id="5999b-111">A varázsló a következő forgatókönyveket támogatja:</span><span class="sxs-lookup"><span data-stu-id="5999b-111">The following scenarios are supported:</span></span>

- <span data-ttu-id="5999b-112">Előlegszámla készítése és feladása.</span><span class="sxs-lookup"><span data-stu-id="5999b-112">Create and post an advance invoice.</span></span>
- <span data-ttu-id="5999b-113">Módosítsa a letét összegét.</span><span class="sxs-lookup"><span data-stu-id="5999b-113">Modify a deposit amount.</span></span> <span data-ttu-id="5999b-114">Ha egy ügyfél úgy dönt, hogy növeli a letét összegét, további előlegszámla kibocsájtása történik.</span><span class="sxs-lookup"><span data-stu-id="5999b-114">If a customer decides to increase the amount of a deposit, an additional advance invoice is issued.</span></span> <span data-ttu-id="5999b-115">Minden egyéb módosításkor a letét összegén (például ha szerkeszti a vevői rendelést), a korábban létrehozott előlegszámlához jóváírás jön létre, és új előlegszámla készítése és feladása történik a helyesbített összeggel.</span><span class="sxs-lookup"><span data-stu-id="5999b-115">For all other changes to the deposit amount (for example, if a customer order is edited), a credit note is created for the advance invoice that was previously generated, and a new advance invoice is generated and posted for the corrected amount.</span></span>
- <span data-ttu-id="5999b-116">Értékesítési rendelés, amely hozzá van kapcsolva az előlegszámlákhoz, érvénytelenítése.</span><span class="sxs-lookup"><span data-stu-id="5999b-116">Cancel a sales order that has linked advance invoices.</span></span> <span data-ttu-id="5999b-117">Ebben az esetben az előlegszámlához jóváírás jön létre.</span><span class="sxs-lookup"><span data-stu-id="5999b-117">In this case, a credit note is created for the advance invoice.</span></span>
- <span data-ttu-id="5999b-118">Értékesítési rendelési számla, amely hozzá van kapcsolva az előlegszámlákhoz, feladása.</span><span class="sxs-lookup"><span data-stu-id="5999b-118">Post a sales order invoice that has linked advance invoices.</span></span> <span data-ttu-id="5999b-119">Az értékesítési rendeléshez kapcsolódó előlegszámla sztornírozott az értékesítési számla értékéig.</span><span class="sxs-lookup"><span data-stu-id="5999b-119">The advance invoice that is linked to a sales order is reversed for the amount of the sales invoice.</span></span> <span data-ttu-id="5999b-120">Az előlegszámla tranzakció kiegyenlítése egy előlegszámla sztornírozás tranzakcióval történik.</span><span class="sxs-lookup"><span data-stu-id="5999b-120">The advance invoice transactions are settled with advance invoice reversal transactions.</span></span>

## <a name="set-up-advance-invoices"></a><span data-ttu-id="5999b-121">Előlegszámlák beállítása</span><span class="sxs-lookup"><span data-stu-id="5999b-121">Set up advance invoices</span></span>

### <a name="turn-on-the-functionality-for-creating-advance-invoices"></a><span data-ttu-id="5999b-122">Az előlegszámlák létrehozásához a funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="5999b-122">Turn on the functionality for creating advance invoices</span></span>

1. <span data-ttu-id="5999b-123">Menjen a **Kiskereskedelem és kereskedelem \> Központ beállítása \> Paraméterek \> Kiskereskedelmi paraméterek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5999b-123">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**.</span></span>
2. <span data-ttu-id="5999b-124">A **Vevői rendelések** lapon, a **Rendelés** gyorslapon állítsa a **Letéti előlegszámla létrehozása** lehetőséget **Igen** beállításra.</span><span class="sxs-lookup"><span data-stu-id="5999b-124">On the **Customer orders** tab, on the **Order** FastTab, set the **Create advance invoice for deposit** option to **Yes**.</span></span>

### <a name="define-the-parameters-for-posting-advance-invoices"></a><span data-ttu-id="5999b-125">Az előlegszámlák feladásához tartozó paraméterek meghatározása</span><span class="sxs-lookup"><span data-stu-id="5999b-125">Define the parameters for posting advance invoices</span></span>

1. <span data-ttu-id="5999b-126">Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.</span><span class="sxs-lookup"><span data-stu-id="5999b-126">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="5999b-127">A **Frissítések** lapon, az **Előlegszámla** gyorslapon, állítsa be a **Feladási profil**, **Áfacsoport** és **Cikkáfacsoport** mezőket.</span><span class="sxs-lookup"><span data-stu-id="5999b-127">On the **Updates** tab, on the **Advance invoice** FastTab, set the **Posting profile**, **Sales tax group**, and **Item sales tax group** fields.</span></span> <span data-ttu-id="5999b-128">Ha ezek a mezők helyesen vannak beállítva, az előlegszámlát feladja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="5999b-128">If these fields are set correctly, the advance invoice will be posted.</span></span> <span data-ttu-id="5999b-129">Ha ezek a mezők nincsenek beállítva, előlegszámla nem lesz feladva.</span><span class="sxs-lookup"><span data-stu-id="5999b-129">If these fields aren't set, advance invoices won't be posted.</span></span>

### <a name="turn-off-posting-of-the-sales-tax-on-prepayment-journal-voucher"></a><span data-ttu-id="5999b-130">Áfa az előlegnapló-bizonylaton feladási kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="5999b-130">Turn off posting of the Sales tax on prepayment journal voucher</span></span>

<span data-ttu-id="5999b-131">Az áfa az előlegnapló-bizonylaton nem adódhat fel, ha az előlegszámla feladása ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="5999b-131">The Sales tax on prepayment journal voucher must not be posted if advance invoice posting is turned on.</span></span> <span data-ttu-id="5999b-132">Ha ellenőrizni szeretné, hogy ez a követelmény teljesül-e, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="5999b-132">To verify that this requirement is met, follow these steps.</span></span>

1. <span data-ttu-id="5999b-133">Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.</span><span class="sxs-lookup"><span data-stu-id="5999b-133">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="5999b-134">Az **Főkönyv és áfa** lapon, a **Fizetés** gyorslapon gondoskodjon arról, hogy a következő mezők üresek legyenek vagy a beállításuk legyen **Nem**:</span><span class="sxs-lookup"><span data-stu-id="5999b-134">On the **Ledger and sales tax** tab, on the **Payment** FastTab, make sure that the following fields are blank or set to **No**:</span></span>

    - <span data-ttu-id="5999b-135">Áfa az előlegnapló-bizonylaton</span><span class="sxs-lookup"><span data-stu-id="5999b-135">Sales tax on prepayment journal voucher</span></span>
    - <span data-ttu-id="5999b-136">Feladási profil az előlegnapló-bizonylathoz</span><span class="sxs-lookup"><span data-stu-id="5999b-136">Posting profile with prepayment journal voucher</span></span>
    - <span data-ttu-id="5999b-137">Előleg adócsoportja</span><span class="sxs-lookup"><span data-stu-id="5999b-137">Tax group for prepayment</span></span>
    - <span data-ttu-id="5999b-138">Cikkáfacsoport</span><span class="sxs-lookup"><span data-stu-id="5999b-138">Item Sales tax group</span></span>

## <a name="print-advance-invoices"></a><span data-ttu-id="5999b-139">Előlegszámlák nyomtatása</span><span class="sxs-lookup"><span data-stu-id="5999b-139">Print advance invoices</span></span>

<span data-ttu-id="5999b-140">A pénztárból származó előlegszámlákat egy Microsoft Windows-nyomtatón, amely a hardverállomáshoz van csatlakoztatva, lehet nyomtatni.</span><span class="sxs-lookup"><span data-stu-id="5999b-140">You can print advance invoices from POS on a Microsoft Windows printer that is connected to the hardware station.</span></span> <span data-ttu-id="5999b-141">Az előlegszámla nyomtatása a pénztár esetében két lehetőség kínálkozik:</span><span class="sxs-lookup"><span data-stu-id="5999b-141">There are two options for printing an advance invoice from POS:</span></span>

- <span data-ttu-id="5999b-142">**Előlegszámla nyomtatása miután egy tranzakció lezárult a pénztáron.**</span><span class="sxs-lookup"><span data-stu-id="5999b-142">**Print an advance invoice after a transaction is concluded in POS.**</span></span> <span data-ttu-id="5999b-143">Ezt a lehetőséget automatikusan megtörténik, ha előlegszámla jött létre, és a Windows-nyomtató helyesen be van állítva.</span><span class="sxs-lookup"><span data-stu-id="5999b-143">This option occurs automatically if an advance invoice was generated and a Windows printer was correctly set up.</span></span> <span data-ttu-id="5999b-144">Ebben az esetben csak az utolsó előlegszámla, amely kapcsolódik a vevői rendeléshez, lesz kinyomtatva.</span><span class="sxs-lookup"><span data-stu-id="5999b-144">In this case, only the last advance invoice that is linked to the customer order is printed.</span></span>
- <span data-ttu-id="5999b-145">**A tranzakciónaplóból egy előzetes számla kinyomtatása.**</span><span class="sxs-lookup"><span data-stu-id="5999b-145">**Reprint an advance invoice from the transaction journal.**</span></span> <span data-ttu-id="5999b-146">Válassz a **Napló megjelenítése** lehetőséget a tranzakciók naplójának megnyitásához, keresse meg a vevői rendelést, és válassza az **Előlegszámla nyomtatása** elemet.</span><span class="sxs-lookup"><span data-stu-id="5999b-146">Select **Show journal** to open the transactions journal, find the customer order, and then select **Print Advance invoice**.</span></span> <span data-ttu-id="5999b-147">Ebben az esetben minden számla, amely kapcsolódik a vevői rendeléshez, lesz kinyomtatva.</span><span class="sxs-lookup"><span data-stu-id="5999b-147">In this case, all advance invoices that are linked to the customer order are printed.</span></span>

### <a name="set-up-a-windows-printer"></a><span data-ttu-id="5999b-148">Windows-nyomtató beállítása</span><span class="sxs-lookup"><span data-stu-id="5999b-148">Set up a Windows printer</span></span>

<span data-ttu-id="5999b-149">Kövesse az alábbi lépéseket ahhoz, hogy a Windows-nyomtatón, amely a hardverállomásra csatlakozik, a pénztárból származó dokumentumok nyomtatva legyenek.</span><span class="sxs-lookup"><span data-stu-id="5999b-149">Follow these steps to enable documents to be printed from POS on a Windows printer that is connected to the hardware station.</span></span>

1. <span data-ttu-id="5999b-150">Lépjen a **Kiskereskedelem és kereskedelem \> Csatorna beállítás \> POS beállítás \> POS profilok \> Hardverprofilok** pontra.</span><span class="sxs-lookup"><span data-stu-id="5999b-150">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS profiles \> Hardware profiles**.</span></span>
2. <span data-ttu-id="5999b-151">Válassza ki a hardverprofilt, amelyek az üzlethez kapcsolódik, ahol a nyomtatót használják.</span><span class="sxs-lookup"><span data-stu-id="5999b-151">Select a hardware profile that is related to the store where the printer is used.</span></span>
3. <span data-ttu-id="5999b-152">A **Nyomtató** vagy a **Nyomtató 2** szakaszban, a beállítások frissítése:</span><span class="sxs-lookup"><span data-stu-id="5999b-152">In either the **Printer** section or the **Printer 2** section, update the settings:</span></span>

    - <span data-ttu-id="5999b-153">A **Nyomtató** mezőben válassza: **Windows-illesztőprogram**.</span><span class="sxs-lookup"><span data-stu-id="5999b-153">In the **Printer** field, select **Windows driver**.</span></span>
    - <span data-ttu-id="5999b-154">Az **Eszköznév** mezőben adja meg a nyomtató nevét.</span><span class="sxs-lookup"><span data-stu-id="5999b-154">In the **Device name** field, enter the name of the printer.</span></span>

4. <span data-ttu-id="5999b-155">Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.</span><span class="sxs-lookup"><span data-stu-id="5999b-155">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
5. <span data-ttu-id="5999b-156">Válassza ki az **1090** munkát és kattintson a **Futtatás most** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5999b-156">Select job **1090**, and then select **Run now**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]