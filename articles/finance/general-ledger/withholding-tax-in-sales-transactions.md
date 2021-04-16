---
title: Adóelőleg az értékesítési tranzakciókban
description: Ez a témakör a kiválasztott vevők adóelőleg-számításának elkerülésére vonatkozó lépéseket sorolja fel. Azon vevők esetében, akik a kifizetéseikben adóelőleget határoznak meg, hozzárendelheti az alapértelmezett adóelőleg-csoportot.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8e11ce10faa9b450b6f36a856b34b06b4ee1838d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842344"
---
# <a name="withholding-tax-in-sales-transactions"></a><span data-ttu-id="83ea6-104">Adóelőleg az értékesítési tranzakciókban</span><span class="sxs-lookup"><span data-stu-id="83ea6-104">Withholding tax in sales transactions</span></span>

<span data-ttu-id="83ea6-105">Ez a témakör a kiválasztott vevők adóelőleg-számításának elkerülésére vonatkozó lépéseket sorolja fel.</span><span class="sxs-lookup"><span data-stu-id="83ea6-105">This topic lists the steps for avoiding the calculation of withholding tax for selected customers.</span></span> <span data-ttu-id="83ea6-106">Azon vevők esetében, akik a kifizetéseikben adóelőleget határoznak meg, hozzárendelheti az alapértelmezett **Adóelőleg-csoport** lehetőséget a **Vevők** oldalon.</span><span class="sxs-lookup"><span data-stu-id="83ea6-106">For customers who specify withholding tax in their payments to you, you can assign the default **Withholding tax group** on the **Customers** page.</span></span> 

1. <span data-ttu-id="83ea6-107">Lépjen a **Navigáció ablaktábla > Modulok > Kintlévőségek > Ügyfelek > Minden ügyfél** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="83ea6-107">Go to **Navigation pane > Modules > Accounts receivable > Customers > All customers**.</span></span>

2. <span data-ttu-id="83ea6-108">Kattintson a megfelelő vevői számlára, és válassza a **Szerkesztés** gombot.</span><span class="sxs-lookup"><span data-stu-id="83ea6-108">Click the respective customer account, click **Edit**.</span></span>

3. <span data-ttu-id="83ea6-109">A **Számlázás és szállítás** lapon állítsa az **Adóelőleg számítása** mezőt **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="83ea6-109">In the **Invoice and delivery** tab, set the **Calculate withholding tax** field to **Yes**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="83ea6-110">Az adóelőleg számítása nem történik meg, ha a törzsadatokban erre a vevőre vonatkozóan nincs bekapcsolva az **Adóelőleg számítása** lehetőség.</span><span class="sxs-lookup"><span data-stu-id="83ea6-110">Withholding tax will not be calculated if **Calculate withholding tax** is not switched on for this customer in the master data.</span></span>

4. <span data-ttu-id="83ea6-111">Válasszon egy adóelőleg-csoportot az **Adóelőleg-csoport** pontban.</span><span class="sxs-lookup"><span data-stu-id="83ea6-111">Select a withholding tax group in **Withholding tax group**.</span></span>

5. <span data-ttu-id="83ea6-112">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="83ea6-112">Click **Save**.</span></span>

<span data-ttu-id="83ea6-113">Az adóelőleg-köteles cikkekhez/szolgáltatásokhoz hozzárendelheti a **Kiadott termékek** alapértelmezett **Cikk adóelőleg-csoport** funkciót.</span><span class="sxs-lookup"><span data-stu-id="83ea6-113">For items/services, which are liable to withholding tax, you can assign the default **Item withholding tax group** in **Released Products**.</span></span>

1. <span data-ttu-id="83ea6-114">Kattintson ide: **Navigációs ablaktábla > Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek**.</span><span class="sxs-lookup"><span data-stu-id="83ea6-114">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>

2. <span data-ttu-id="83ea6-115">Kattintson a megfelelő Cikkszámra, és válassza a **Szerkesztés** gombot.</span><span class="sxs-lookup"><span data-stu-id="83ea6-115">Click the respective Item number, click **Edit**.</span></span>

3. <span data-ttu-id="83ea6-116">Az **Értékesítés** lapon kattintson az **Adóelőleg számítása** elemre.</span><span class="sxs-lookup"><span data-stu-id="83ea6-116">In the **Sell** tab, click **Calculate withholding tax**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="83ea6-117">Az adóelőleg számítása nem történik meg, ha az **Adóelőleg számítása** nem **Igen** értékre van beállítva ehhez a cikkhez a **Kiadott termék** oldal **Értékesítés** lapján.</span><span class="sxs-lookup"><span data-stu-id="83ea6-117">Withholding tax will not be calculated if **Calculate withholding tax** is not set to **Yes** for this Item in the **Sell** tab on the **Released product** page.</span></span>

4. <span data-ttu-id="83ea6-118">Válasszon egy Cikk adóelőleg-csoportot a **Cikk-adóelőlegek csoportja** listában.</span><span class="sxs-lookup"><span data-stu-id="83ea6-118">Select an Item withholding tax group in **Item withholding tax group** list.</span></span>

5. <span data-ttu-id="83ea6-119">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="83ea6-119">Click **Save**.</span></span>

<span data-ttu-id="83ea6-120">Az adóelőleg-csoportok és cikk adóelőleg-csoportok az **Értékesítési rendelés** oldalon rendelhetők hozzá:</span><span class="sxs-lookup"><span data-stu-id="83ea6-120">Withholding tax groups and Item withholding tax groups can be assigned using the **Sales order** page.</span></span> 

<span data-ttu-id="83ea6-121">Új értékesítési rendelés létrehozásakor az alapértelmezett adóelőleg-csoport és cikk adóelőleg-csoport lesz az értékesítésirendelés-sorok alapértelmezett bejegyzése.</span><span class="sxs-lookup"><span data-stu-id="83ea6-121">The default Withholding tax group and Item withholding tax group will be used as default entries on sales order lines when you create a new sales order.</span></span>

<span data-ttu-id="83ea6-122">Az adóelőleg számítása és feladása a **Vevői kifizetési napló** alapján történik.</span><span class="sxs-lookup"><span data-stu-id="83ea6-122">Withholding tax is calculated and posted with **Customer payment journal**.</span></span> <span data-ttu-id="83ea6-123">Az alkalmazandó adóelőlegkódot és a tényleges adóelőleg-összeget manuálisan módosíthatja a **Tranzakciók kiegyenlítése** oldal **Adóelőleg** lapján.</span><span class="sxs-lookup"><span data-stu-id="83ea6-123">You can manually adjust the applicable withholding tax code, as well as the actual withholding tax amount in the **Withholding tax** tab on the **Settle transactions** page.</span></span>

<span data-ttu-id="83ea6-124">A kiszámított adóelőleg összege le lesz vonva a vevői kifizetésből, és a rendszer feladja az **Adóelőleg ellenszámla** számlához egy kapcsolódó bizonylaton.</span><span class="sxs-lookup"><span data-stu-id="83ea6-124">The calculated withholding tax amount will be deducted from the customer payment and posted to the **Withholding tax offset** account in a related voucher.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]