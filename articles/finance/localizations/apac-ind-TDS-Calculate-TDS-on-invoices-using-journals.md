---
title: TDS kiszámítása számlákon naplók segítségével
description: Ez a témakör felsorolja a forrásnál levont adó (TDS) kiszámításának lépéseit a naplókon.
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
ms.openlocfilehash: d68e1b3a4dc31823ec56a525149f16bdc23c0883
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023312"
---
# <a name="calculate-tds-on-invoices-using-journals"></a><span data-ttu-id="ed008-103">TDS kiszámítása számlákon naplók segítségével</span><span class="sxs-lookup"><span data-stu-id="ed008-103">Calculate TDS on invoices using journals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ed008-104">Ez a témakör felsorolja a forrásnál levont adó (TDS) kiszámításának lépéseit a naplókon.</span><span class="sxs-lookup"><span data-stu-id="ed008-104">This topic lists the steps for calculating Tax Deducted at Source (TDS) on journals.</span></span>

<span data-ttu-id="ed008-105">Kezdje az **Általános naplók** oldal megnyitásával (**Főkönyv > Naplóbejegyzések > Általános naplók**).</span><span class="sxs-lookup"><span data-stu-id="ed008-105">Begin by opening the **General journals** page (**General ledger > Journal entries > General journals**).</span></span>

<span data-ttu-id="ed008-106">[![Általános naplók](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)</span><span class="sxs-lookup"><span data-stu-id="ed008-106">[![General journals](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)</span></span>

1. <span data-ttu-id="ed008-107">Hozzon létre naplósorokat a táblázatban felsorolt naplóformák segítségével.</span><span class="sxs-lookup"><span data-stu-id="ed008-107">Create journal lines using the journal forms that are listed in the table.</span></span> <span data-ttu-id="ed008-108">Válassza ki a számlatípust és az eltolás számlatípust, és adja meg a tranzakció összegét.</span><span class="sxs-lookup"><span data-stu-id="ed008-108">Select the account type and offset account type and enter the amount for the transaction.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="ed008-109">A **Számlajóváhagyás naplója** lapon válassza az **Utalványok keresése** lehetőséget, és válassza ki a TDS kiszámításához szükséges számlákat.</span><span class="sxs-lookup"><span data-stu-id="ed008-109">On the **Invoice approval journal** page, select **Find vouchers** and select invoices to calculate TDS on.</span></span> <span data-ttu-id="ed008-110">Tekintse meg a **Számlaregisztrátság** vagy az **Bizonylatok keresése** lapon létrehozott számlákat.</span><span class="sxs-lookup"><span data-stu-id="ed008-110">View the invoices created in the **Invoice register** page or the **Find vouchers** page.</span></span>  

2. <span data-ttu-id="ed008-111">A **Napló bizonylat** oldal **Általános** lapján tekintse meg vagy módosítsa a szállítóra vagy vevőre meghatározott alapértelmezett TDS-csoportot a **TDS-csoport** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ed008-111">On the **General** tab of the **Journal voucher** page, view or modify the default TDS group defined for the vendor or customer, in the **TDS group** field.</span></span> <span data-ttu-id="ed008-112">A naplósorokra számított TDS-összeg a **TDS-csoport** mezőben felsorolt TDS-adókódokhoz meghatározott képleten alapul.</span><span class="sxs-lookup"><span data-stu-id="ed008-112">The TDS amount that's calculated on journal lines is based on the formula defined for the TDS tax codes listed in the **TDS group** field.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="ed008-113">Az **Adóelőleg-csoport** mező és a **TCS-csoport** mező nem lesz elérhető, ha a **TDS-csoport** mezőben egy TDS-csoportot választ.</span><span class="sxs-lookup"><span data-stu-id="ed008-113">The **Withholding tax group**  field and the **TCS group** field become unavailable when you select a TDS group in the **TDS group** field.</span></span> <span data-ttu-id="ed008-114">Az **Adóelőleg csoport** mező csak az **Általános napló** oldalon érhető el.</span><span class="sxs-lookup"><span data-stu-id="ed008-114">The **Withholding tax group** field is available only on the **General journal** page.</span></span> <span data-ttu-id="ed008-115">A TDS kiszámítása csak akkor történik meg, ha az **Összes szállító** vagy az **Összes vevő** lapokon a szállító vagy vevő számára ki van jelölve az **Adóelőleg kiszámítása** jelölőnégyzet.</span><span class="sxs-lookup"><span data-stu-id="ed008-115">TDS is calculated only if the **Calculate withholding tax** check box is selected for the vendor or customer on the **All vendors** or **All customers** pages.</span></span>   

3. <span data-ttu-id="ed008-116">Válassza ki az **Adózási információk** fület. Szükség esetén válassza ki ebben a mezőben a cégnévhez beállított cég alternatív címeit.</span><span class="sxs-lookup"><span data-stu-id="ed008-116">Select the **Tax information** tab. Select the alternate addresses of a company that's set up for the company in this field, if required.</span></span> <span data-ttu-id="ed008-117">A cégnevet a **Céginformáció** mezőcsoport alatt található **Név** mezőben tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="ed008-117">You can view the company name in the **Name** field, which is under the **Company information** field group.</span></span> 

4. <span data-ttu-id="ed008-118">Tekintse meg az eladó vagy vevő értékelő kategóriájának jellegét az **Adóelőleg-mezőcsoport** alá tartozó **Értékelő jellege** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ed008-118">View the nature of assessee category of the vendor or customer in the **Nature of assessee** field, which is under the **Withholding tax** field group.</span></span> <span data-ttu-id="ed008-119">Az **Adószámlaszám** (**TAN**) mezőben tekintse meg a kiválasztott cégnév TAN-ját.</span><span class="sxs-lookup"><span data-stu-id="ed008-119">In the **Tax Account Number** (**TAN**) field, view the TAN of the selected company name that's displayed.</span></span>  

5. <span data-ttu-id="ed008-120">Az **Ideiglenes adóelőleg-tranzakciók** lap megnyitásához válassza az **Adóelőleg** lehetőséget az **Adóelőleg** menüben.</span><span class="sxs-lookup"><span data-stu-id="ed008-120">Select **Withholding tax** in **Withholding tax** menu to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="ed008-121">A következő mezők az **Ideiglenes adóelőleg-tranzakciók** oldal felső ablaktábláján jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="ed008-121">The following fields are displayed on the upper pane of the **Temporary withholding tax transactions** page.</span></span>

   - <span data-ttu-id="ed008-122">Az **Adóelőleg összege összesen** – A TDS-csoport tranzakciójáért kiszámított teljes TDS.</span><span class="sxs-lookup"><span data-stu-id="ed008-122">**Withholding tax amount in total** - The total TDS calculated for the transaction for the TDS group.</span></span>

   - <span data-ttu-id="ed008-123">**Érték** – A tranzakció-TDS kiszámításához használt teljes százalék.</span><span class="sxs-lookup"><span data-stu-id="ed008-123">**Value** - The total percentage used to calculate TDS for the transaction.</span></span> <span data-ttu-id="ed008-124">A teljes százalék a TDS-csoporthoz csatolt TDS-adókódokra meghatározott képleten alapul.</span><span class="sxs-lookup"><span data-stu-id="ed008-124">The total percentage is based on the formula that is defined for TDS tax codes attached to the TDS group.</span></span>

   - <span data-ttu-id="ed008-125">**Korrigált forrásadó összege összesen** – A TDS csoport összes adókódjának teljes korrigált TDS-összege.</span><span class="sxs-lookup"><span data-stu-id="ed008-125">**Adjusted withholding tax amount in total** - The total adjusted TDS amount for all tax codes in the TDS group.</span></span>

   - <span data-ttu-id="ed008-126">**TDS** – Ha be van jelölve, egy TDS-csoport csatlakozik a tranzakcióhoz.</span><span class="sxs-lookup"><span data-stu-id="ed008-126">**TDS** - If selected, a TDS group is attached to the transaction.</span></span>

  <span data-ttu-id="ed008-127">Az **Ideiglenes forrásadó-tranzakciók** oldal **Áttekintése**, **Általános** és **Helyesbítése** lapján található mezők a TDS-csoporthoz csatolt egyes TDS-adókódok számított TDS-összegét és kiigazított TDS-összegadatait jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="ed008-127">The fields on the **Overview**, **General**, and **Adjustment** tabs on the **Temporary withholding tax transactions** page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>

6. <span data-ttu-id="ed008-128">A **Küszöbérték** lap megnyitásához válassza a **Küszöbérték** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ed008-128">Select **Threshold** to open the **Threshold** page.</span></span> <span data-ttu-id="ed008-129">Ezen az oldalon tekintse meg az adott TDS-adókódhoz csatolt TDS-adóösszetevőre meghatározott küszöbértéket és kivételi küszöbértéket.</span><span class="sxs-lookup"><span data-stu-id="ed008-129">View the threshold limit and exception threshold limit defined for the TDS tax component attached to a specific TDS tax code on this page.</span></span>

   <span data-ttu-id="ed008-130">A **Receptúratervező** lap megnyitásához válassza a **Receptúratervező** űrlapot.</span><span class="sxs-lookup"><span data-stu-id="ed008-130">Select **Formula designer** to open the **Formula designer** form.</span></span> <span data-ttu-id="ed008-131">Tekintse meg ezen az oldalon az adott TDS-adókódhoz definiált receptúrát.</span><span class="sxs-lookup"><span data-stu-id="ed008-131">View the formula defined for a specific TDS tax code in this page.</span></span> <span data-ttu-id="ed008-132">Zárja be a **Képlettervező** és az **Ideiglenes adóelőleg-tranzakciók** oldalakat, hogy visszatérjen a **Napló bizonylat** oldalára.</span><span class="sxs-lookup"><span data-stu-id="ed008-132">Close the **Formula designer** and **Temporary withholding tax transactions** pages to return to the **Journal voucher** page.</span></span>

8. <span data-ttu-id="ed008-133">Adja meg az egyéb szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="ed008-133">Enter the other required details.</span></span> <span data-ttu-id="ed008-134">Ellenőrizze és adja fel a naplót.</span><span class="sxs-lookup"><span data-stu-id="ed008-134">Validate and post the journal.</span></span> <span data-ttu-id="ed008-135">A beszerzési számlákon kiszámított TDS-összeg a fizetendő számlára kerül.</span><span class="sxs-lookup"><span data-stu-id="ed008-135">The TDS amount that's calculated on purchase invoices is posted to the payable account.</span></span> <span data-ttu-id="ed008-136">Az értékesítési számlákon kiszámított TDS-összeg a TDS-csoport minden egyes TDS-adókódjára meghatározott követelésszámlára kerül.</span><span class="sxs-lookup"><span data-stu-id="ed008-136">The TDS amount that's calculated on sales invoices is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="ed008-137">A TDS-adókódok fizetendő számláit vagy követelésszámláit az **Adóelőleg-kódok** oldalon határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="ed008-137">The payable accounts or receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>

9. <span data-ttu-id="ed008-138">Az **Adóelőleg**-**tranzakciók** lap megnyitásához válassza a **Feladott adóelőleg** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ed008-138">Select **Posted withholding tax** to open the **Withholding** **tax** **transactions** page.</span></span> <span data-ttu-id="ed008-139">Az **Érték** mezőben megjelenik a tranzakció-TDS kiszámításához használt teljes százalék.</span><span class="sxs-lookup"><span data-stu-id="ed008-139">In the **Value** field, the total percentage used to calculate TDS for the transaction is displayed.</span></span>

   <span data-ttu-id="ed008-140">Az Adóelőleg-tranzakciók oldal **Áttekintés**, **Általános** és **Összeg** lapján található mezők a TDS-csoporthoz csatolt egyes TDS-adókódok számított TDS-összegét és kiigazított TDS-összegadatait jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="ed008-140">The fields on the **Overview**, **General**, and **Amount** tabs in the Withholding tax transactions page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>
