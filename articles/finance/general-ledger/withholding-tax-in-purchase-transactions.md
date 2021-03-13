---
title: Adóelőleg a beszerzési tranzakciókban
description: Az adóelőleg fizetésére kötelezett szállítók esetén az alapértelmezett **Adóelőleg-csoport** lehetőséget a **Minden szállító** oldalon rendelheti hozzá.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 06997e2d6b47d867e014a7d493d91015c78a5e04
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060744"
---
# <a name="withholding-tax-in-purchase-transactions"></a><span data-ttu-id="7c9b1-103">Adóelőleg a beszerzési tranzakciókban</span><span class="sxs-lookup"><span data-stu-id="7c9b1-103">Withholding tax in purchase transactions</span></span>

<span data-ttu-id="7c9b1-104">Az adóelőleg fizetésére kötelezett szállítók esetén az alapértelmezett **Adóelőleg-csoport** lehetőséget a **Minden szállító** oldalon rendelheti hozzá.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-104">For vendors who are liable to withholding tax, you can assign the default **Withholding tax group** on the **All vendors** page.</span></span>

1. <span data-ttu-id="7c9b1-105">Lépjen ide: **Navigáció ablaktábla > Modulok > Kötelezettségek > Szállítók > Minden beszállító**.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-105">Go to **Navigation pane > Modules > Accounts payable > Vendors > All vendors**.</span></span>

2. <span data-ttu-id="7c9b1-106">Kattintson a megfelelő Szállítói számlára, és válassza a **Szerkesztés** gombot.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-106">Click the respective Vendor account, click **Edit**.</span></span>

3. <span data-ttu-id="7c9b1-107">A **Számlázás és szállítás** lapon állítsa az **Adóelőleg számítása** mezőt **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-107">In **Invoice and delivery** tab, set the **Calculate withholding tax** field to **Yes**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="7c9b1-108">Az adóelőleg számítása nem történik meg, ha az adatok között nincs bekapcsolva az **Adóelőleg számítása** lehetőség.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-108">Withholding tax will not be calculated if **Calculate withholding tax** is not switched on for this vendor in the data.</span></span>

4. <span data-ttu-id="7c9b1-109">Válasszon egy adóelőleg-csoportot az **Adóelőleg-csoport** pontban.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-109">Select a withholding tax group in **Withholding tax group**.</span></span>

5. <span data-ttu-id="7c9b1-110">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-110">Click **Save**.</span></span>

<span data-ttu-id="7c9b1-111">Az adóelőleg-köteles cikkekhez/szolgáltatásokhoz hozzárendelheti a **Kiadott termékek** alapértelmezett **Cikk adóelőleg-csoport** funkciót.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-111">For items/services which are liable to withholding tax, you can assign the default **Item withholding tax group** in **Released Products**.</span></span>

1. <span data-ttu-id="7c9b1-112">Kattintson ide: **Navigációs ablaktábla > Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek**.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-112">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>

2. <span data-ttu-id="7c9b1-113">Kattintson a megfelelő Cikkszámra, és válassza a **Szerkesztés** gombot.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-113">Click the respective Item number, click **Edit**.</span></span>

3. <span data-ttu-id="7c9b1-114">A **Beszerzés** lapon kattintson az **Adóelőleg számítása** elemre.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-114">In **Purchase** tab, click **Calculate withholding tax**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="7c9b1-115">Az adóelőleg számítása nem történik meg, ha az **Adóelőleg számítása** nem **Igen** értékre van beállítva ehhez a cikkhez a **Kiadott termék** oldal **Beszerzés** lapján.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-115">Withholding tax will not be calculated if **Calculate withholding tax** isn't set to **Yes** for this Item in the **Purchase** tab on the **Released product** page.</span></span>

4. <span data-ttu-id="7c9b1-116">Válasszon egy cikk adóelőleg-csoportot a **Cikk-adóelőlegek csoportja** listában.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-116">Select an item withholding tax group in **Item withholding tax group** list.</span></span>

5. <span data-ttu-id="7c9b1-117">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-117">Click **Save**.</span></span>

<span data-ttu-id="7c9b1-118">Az adóelőleg-csoportok és cikk-adóelőlegek csoportjai a következő lapokon rendelhetők hozzá:</span><span class="sxs-lookup"><span data-stu-id="7c9b1-118">Withholding tax groups and Item withholding tax groups can be assigned in pages:</span></span> 

- <span data-ttu-id="7c9b1-119">**Beszerzési rendelés**</span><span class="sxs-lookup"><span data-stu-id="7c9b1-119">**Purchase order**</span></span>
- <span data-ttu-id="7c9b1-120">**Szállítói számla**</span><span class="sxs-lookup"><span data-stu-id="7c9b1-120">**Vendor invoice**</span></span>
- <span data-ttu-id="7c9b1-121">**Számlanapló**</span><span class="sxs-lookup"><span data-stu-id="7c9b1-121">**Invoice journal**</span></span>

<span data-ttu-id="7c9b1-122">**Beszerzési rendelések** és/vagy **Függőben levő szállítói számlák** létrehozásakor a sorokba az alapértelmezett adóelőleg-csoport és cikk-adóelőlegek csoportja kerül.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-122">The default Withholding tax group and Item withholding tax group will be carried into the lines when creating **Purchase orders** and/or **Pending Vendor invoices**.</span></span> <span data-ttu-id="7c9b1-123">A **Szállítói számla naplója** pontban átválthat az **Adóelőleg számítása** elemre, és a napló **Általános** lapján kiválaszthatja a **Cikk-adóelőlegek csoportja** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-123">For **Vendor invoice journal**, you can switch on **Calculate withholding tax** and select **Item withholding tax group** in the **General** tab in the journal.</span></span>

<span data-ttu-id="7c9b1-124">Az adóelőleg ideiglenes összege elérhető a **Beszerzési rendelés** oldal **Összegek** lapján, a **Helyesbített adóelőleg** mezőben.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-124">The temporary amount of withholding tax is available in the field **Adjusted withholding tax** of the **Totals** tab on the **Purchase order** page.</span></span>

![Az adóelőleg szerepel a beszerzési rendelésen](media/withholding-tax-adjusted.png)

<span data-ttu-id="7c9b1-126">Az adóelőleg számítása a **Szállítói kifizetési napló** alapján történik.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-126">Withholding tax is calculated on **Vendor payment journal**.</span></span> <span data-ttu-id="7c9b1-127">Az alkalmazandó adóelőlegkódokat és a tényleges adóelőleg-összegeket manuálisan módosíthatja a **Tranzakciók kiegyenlítése** oldal **Adóelőleg** lapján.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-127">You can manually adjust the applicable withholding tax codes as well as the actual withholding tax amounts in the **Withholding tax** tab on the **Settle transactions** page.</span></span>

![Az adóelőleg manuálisan módosítható a Tranzakciók kiegyenlítése oldalon](media/withholding-tax-vendor-payment-tab.png)

<span data-ttu-id="7c9b1-129">A származtatott adóelőleg összege le lesz vonva a szállítói kifizetésből, és a rendszer feladja az **Adóelőleg számlája** ponthoz egy kapcsolódó bizonylaton.</span><span class="sxs-lookup"><span data-stu-id="7c9b1-129">The derived withholding tax amount will be deducted from the vendor payment and posted to the **Withholding tax account** in a related voucher.</span></span>

![Kapcsolódó bizonylatot megjelenítő adóelőlegszámla](media/withholding-tax-adjusted.png)
