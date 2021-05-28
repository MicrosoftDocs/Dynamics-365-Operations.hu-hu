---
title: TDS-számlák kiszámítása a beszerzési rendelési űrlap és az értékesítési rendelési űrlap segítségével
description: Ez a témakör felsorolja a forrásnál levont adó (TDS) kiszámításának lépéseit a különböző típusú számlákon.
author: kailiang
ms.date: 02/12/2021
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
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: e7925206f3c060c6332de9d4972c8a7fb0066be2
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023288"
---
# <a name="calculate-tds-invoices-using-purchase-order-form-and-sales-order-form"></a><span data-ttu-id="4b843-103">TDS-számlák kiszámítása a beszerzési rendelési űrlap és az értékesítési rendelési űrlap segítségével</span><span class="sxs-lookup"><span data-stu-id="4b843-103">Calculate TDS invoices using purchase order form and sales order form</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4b843-104">Ez a témakör felsorolja a Forrásnál levont adó (TDS) kiszámításának lépéseit a különböző típusú számlákon a **Beszerzési rendelés**, a **Beszerzési napló**, a **Keretrendelés** és az **Értékesítési rendelés** oldalak használatával.</span><span class="sxs-lookup"><span data-stu-id="4b843-104">This topic lists the steps for calculating Tax Deducted at Source (TDS) on various types of invoices using the **Purchase order**, **Purchase journal**, **Blanket order**, and **Sales order** pages.</span></span>

1. <span data-ttu-id="4b843-105">Hozzon létre egy beszerzési rendelést, beszerzési naplót, beszerzési keretrendelést vagy értékesítési rendelést a felsorolt oldalon.</span><span class="sxs-lookup"><span data-stu-id="4b843-105">Create a purchase order, purchase journal, purchase blanket order, or a sales order using the page listed.</span></span> <span data-ttu-id="4b843-106">Adja meg a szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="4b843-106">Enter the required details.</span></span>

2. <span data-ttu-id="4b843-107">Válassza a **Beállítás** fület a szállító vagy vevő értékelőjének természetének megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="4b843-107">Select the **Setup** tab to view the nature of the assessee of the vendor or customer.</span></span> <span data-ttu-id="4b843-108">Ezek az információk az **Adóelőleg-csoport** mezőcsoport alatti **Értékelők jellege** mezőben felsoroltak.</span><span class="sxs-lookup"><span data-stu-id="4b843-108">This information is listed in the **Nature of assessee** field, under the **Withholding tax group** field group.</span></span>

3. <span data-ttu-id="4b843-109">A **TDS-csoport** mezőben tekintse meg vagy módosítsa a szállító vagy vevő számára meghatározott alapértelmezett TDS-csoportot.</span><span class="sxs-lookup"><span data-stu-id="4b843-109">In the **TDS group** field, view or modify the default TDS group defined for the vendor or customer.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4b843-110">A **TCS-csoportmező** nem érhető el, ha a TDS-csoportmezőben kiválaszt egy **TDS-csoportot**.</span><span class="sxs-lookup"><span data-stu-id="4b843-110">The **TCS group** field isn't available when you select a TDS group in the **TDS group** field.</span></span> <span data-ttu-id="4b843-111">A TDS kiszámítása csak akkor történik meg, ha az **Összes szállító** vagy az **Összes vevő** lapon a szállító vagy vevő számára ki van jelölve az **Adóelőleg kiszámítása** jelölőnégyzet.</span><span class="sxs-lookup"><span data-stu-id="4b843-111">TDS is calculated only if the **Calculate withholding tax** check box is selected for the vendor or customer on the **All vendors** or **All customers** page.</span></span>  

4. <span data-ttu-id="4b843-112">Hozzon létre cikksorokat a **Sorok** lapon, és adja meg a szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="4b843-112">Create item lines on the **Lines** tab and enter the required details.</span></span>

5. <span data-ttu-id="4b843-113">Válassza a **Beállítás** lapot (vonalszint) a fejlécszinten definiált TDS-csoport megtekintéséhez vagy módosításához.</span><span class="sxs-lookup"><span data-stu-id="4b843-113">Select the **Setup** tab (line-level) to view or change the TDS group defined at the header-level.</span></span> <span data-ttu-id="4b843-114">A TDS-csoport a **TDS-csoport** mezőben jelenik meg, amely az **Adóelőleg-csoport** mezőcsoportja alatt található.</span><span class="sxs-lookup"><span data-stu-id="4b843-114">The TDS group is displayed in the **TDS group** field, which is under the **Withholding tax group** field group.</span></span>

6. <span data-ttu-id="4b843-115">Válassza ki az **Adózási információk** fület, és válassza ki az ebben a mezőben megjelenő cégnévhez beállított alternatív címeket.</span><span class="sxs-lookup"><span data-stu-id="4b843-115">Select the **Tax information** tab and select alternate addresses that are set up for the company name that's displayed in this field.</span></span> <span data-ttu-id="4b843-116">A cégnév a **Céginformáció** mezőcsoport alatt található **Név** mezőben jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="4b843-116">The company name is displayed in the **Name** field, which is under the **Company information** field group.</span></span> 

   <span data-ttu-id="4b843-117">A kiválasztott cégnév TAN-ja az **Adószámlaszám** (**TAN**) mezőben jelenik meg az **Adóelőleg** mezőcsoport alatt.</span><span class="sxs-lookup"><span data-stu-id="4b843-117">The TAN of the selected company name is displayed in the **Tax Account Number** (**TAN**) field, under the **Withholding tax** field group.</span></span> 

7. <span data-ttu-id="4b843-118">Az **Ideiglenes adóelőleg-tranzakciók** lap megnyitásához válassza az **Adóelőleg** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4b843-118">Select **Withholding tax** to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="4b843-119">Tekintse meg a következő mezőket az **Ideiglenes adóelőleg-tranzakciók** oldal felső ablaktábláján.</span><span class="sxs-lookup"><span data-stu-id="4b843-119">View the following fields on the upper pane of the **Temporary withholding tax transactions** page.</span></span>

   - <span data-ttu-id="4b843-120">**Adóelőleg** **összege** **összesen** – A TDS-csoport tranzakciójáért kiszámított teljes TDS.</span><span class="sxs-lookup"><span data-stu-id="4b843-120">**Withholding** **tax** **amount** **in** **total** - The total TDS calculated for the transaction for the TDS group.</span></span>

   - <span data-ttu-id="4b843-121">**Érték** – A tranzakció-TDS kiszámításához használt teljes százalék.</span><span class="sxs-lookup"><span data-stu-id="4b843-121">**Value** - The total percentage used to calculate TDS for the transaction.</span></span> <span data-ttu-id="4b843-122">A teljes százalék a TDS-csoporthoz csatolt TDS-adókódokra meghatározott képleten alapul.</span><span class="sxs-lookup"><span data-stu-id="4b843-122">The total percentage is based on the formula that is defined for TDS tax codes attached to the TDS group.</span></span>

   - <span data-ttu-id="4b843-123">**Korrigált forrásadó összege összesen** – A TDS csoport összes adókódjának teljes korrigált TDS-összege.</span><span class="sxs-lookup"><span data-stu-id="4b843-123">**Adjusted withholding tax amount in total** - The total adjusted TDS amount for all tax codes in the TDS group.</span></span>

   - <span data-ttu-id="4b843-124">**TDS** – Ha be van jelölve, egy TDS-csoport csatlakozik a tranzakcióhoz.</span><span class="sxs-lookup"><span data-stu-id="4b843-124">**TDS** - If selected, a TDS group is attached to the transaction.</span></span>

<span data-ttu-id="4b843-125">Az **Ideiglenes forrásadó-tranzakciók** oldal **Áttekintése**, **Általános** és **Helyesbítése** lapján található mezők a TDS-csoporthoz csatolt egyes TDS-adókódok számított TDS-összegét és kiigazított TDS-összegadatait jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="4b843-125">The fields on the **Overview**, **General**, and **Adjustment** tabs on the **Temporary withholding tax transactions** page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>

8. <span data-ttu-id="4b843-126">A **Küszöbérték** lap megnyitásához válassza a **Küszöbérték** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4b843-126">Select **Threshold** to open the **Threshold** page.</span></span> <span data-ttu-id="4b843-127">Ezen az oldalon tekintse meg az adott TDS-adókódhoz csatolt TDS-adóösszetevőre meghatározott küszöbértéket.</span><span class="sxs-lookup"><span data-stu-id="4b843-127">View the threshold limit defined for the TDS tax component attached to a specific TDS tax code on this page.</span></span>

9. <span data-ttu-id="4b843-128">A **Receptúratervező** lap megnyitásához válassza a **Receptúratervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4b843-128">Select **Formula designer** to open the **Formula designer** page.</span></span> <span data-ttu-id="4b843-129">Tekintse meg ezen az oldalon az adott TDS-adókódhoz definiált képletet.</span><span class="sxs-lookup"><span data-stu-id="4b843-129">View the formula that is defined for a specific TDS tax code on this page.</span></span> 

10. <span data-ttu-id="4b843-130">Számla feladása.</span><span class="sxs-lookup"><span data-stu-id="4b843-130">Post the invoice.</span></span> <span data-ttu-id="4b843-131">A beszerzési számlákon kiszámított TDS-összeg a fizetendő számlára kerül, és az értékesítési számlákon kiszámított TDS-összeg a TDS-csoport minden egyes TDS-adókódjához meghatározott követelésszámlára kerül.</span><span class="sxs-lookup"><span data-stu-id="4b843-131">The TDS amount calculated on purchase invoices is posted to the payable account and the TDS amount calculated on sales invoices is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="4b843-132">A TDS-adókódok fizetendő számláit vagy követelésszámláit az **Adóelőleg-kódok** oldalon határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="4b843-132">The payable accounts or receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>

11. <span data-ttu-id="4b843-133">Válassza a **Lekérdezés** gombot **> Számla > Aadóelőleg-bizonylatok** gombot az **Adóelőleg-tranzakciók** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4b843-133">Select **Inquiry** button **> Invoice > Posted withholding tax** button to open the **Withholding tax transactions** page.</span></span> <span data-ttu-id="4b843-134">Az **Érték** mezőben megtekintheti a tranzakció-TDS kiszámításához használt teljes százalékot.</span><span class="sxs-lookup"><span data-stu-id="4b843-134">You can view the total percentage used to calculate TDS for the transaction in the **Value** field.</span></span>

<span data-ttu-id="4b843-135">Az **Adóelőleg-tranzakciók** oldalon az **Áttekintés**, **Általános** és az **Összeg** fülön található mezők a tranzakcióra számított TDS adatait jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="4b843-135">The fields on the **Overview**, **General**, and **Amount** tabs on the **Withholding tax transactions** page display the information of TDS calculated for the transaction.</span></span> <span data-ttu-id="4b843-136">Tekintse meg a TDS-csoporthoz csatolt minden egyes TDS-adókód TDS-számítási adatait.</span><span class="sxs-lookup"><span data-stu-id="4b843-136">View the TDS calculation information for each TDS tax code attached to the TDS group.</span></span>
