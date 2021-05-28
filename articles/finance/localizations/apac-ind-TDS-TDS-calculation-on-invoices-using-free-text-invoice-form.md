---
title: TDS számítás a szabadszöveges számla oldalon található számlákhoz
description: Ez a témakör ismerteti, hogyan kell kiszámítani a forrásnál levont adót (TDS) a számlákon a Szabadszöveges számla oldalon.
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
ms.openlocfilehash: 7d551a8ba6ba9ca282fd9de3fa7d7c7303e394ed
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023304"
---
# <a name="tds-calculation-on-invoices-from-the-free-text-invoice-page"></a><span data-ttu-id="0a633-103">TDS számítás a szabadszöveges számla oldalon található számlákhoz</span><span class="sxs-lookup"><span data-stu-id="0a633-103">TDS calculation on invoices from the Free text invoice page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0a633-104">Ez a témakör ismerteti, hogyan kell kiszámítani a forrásnál levont adót (TDS) a számlákon a **Szabadszöveges számla** oldalon.</span><span class="sxs-lookup"><span data-stu-id="0a633-104">This topic explains how to calculate Tax Deducted at Source (TDS) on invoices by using the **Free text invoice** page.</span></span>

1. <span data-ttu-id="0a633-105">Ugorjon a következőre: **Kinnlévőségek \> Számlák \> Kizárólag szabadszöveges számlák**.</span><span class="sxs-lookup"><span data-stu-id="0a633-105">Go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>

    <span data-ttu-id="0a633-106">[![Szabadszöveges számla oldal](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)</span><span class="sxs-lookup"><span data-stu-id="0a633-106">[![Free text invoice page](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)</span></span>

2. <span data-ttu-id="0a633-107">Válassza az **Új** lehetőséget, hozzon létre egy szabadszöveges számlát, majd adja meg a szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="0a633-107">Select **New** to create a free text invoice, and enter the required details.</span></span>
3. <span data-ttu-id="0a633-108">Válassza ki a **Számla** lapot. Az **Adóelőlegcsoport** szakaszban az **Értékelő jellege** mező mutatja meg az ügyfél Értékelő jellege kategóriáját.</span><span class="sxs-lookup"><span data-stu-id="0a633-108">Select the **Invoice** tab. In the **Withholding tax group** section, the **Nature of assessee** field shows the nature of assessee category of the customer.</span></span>
4. <span data-ttu-id="0a633-109">A **TDS-csoport** mezőben tekintse át vagy módosítsa a vevő számára meghatározott alapértelmezett TDS-csoportot.</span><span class="sxs-lookup"><span data-stu-id="0a633-109">In the **TDS group** field, review or change the default TDS group that is defined for the customer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0a633-110">Amikr értéket választ a **TDS-csoport** mezőben, nem érhető el a **TCS-csoport** mező.</span><span class="sxs-lookup"><span data-stu-id="0a633-110">When you select a value in the **TDS group** field, the **TCS group** field becomes unavailable.</span></span> <span data-ttu-id="0a633-111">A TDS kiszámítása csak akkor történik meg, ha az **Adóelőleg számítása** opció az **Összes szállító** lapon az ügyfél esetében **Igen** értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="0a633-111">TDS is calculated only if the **Calculate withholding tax** option is set to **Yes** for the customer on the **All customers** page.</span></span>

5. <span data-ttu-id="0a633-112">Az **Adózási információk** lapon, a **Céginformációk** részben, a **Név** mezőben kiválaszthatja a vállalat számára beállított alternatív címhez tartozó cégnevet.</span><span class="sxs-lookup"><span data-stu-id="0a633-112">On the **Tax information** tab, in the **Company information** section, in the **Name** field, select the company name for an alternate address that has been set up for the company.</span></span>

    <span data-ttu-id="0a633-113">Az **Adóelőleg** részben az **Adószámlaszám (TAN)** mező a kiválasztott vállalat adószámlaszámát (TAN) mutatja.</span><span class="sxs-lookup"><span data-stu-id="0a633-113">In the **Withholding tax** section, the **Tax Account Number (TAN)** field shows the tax account number (TAN) for the selected company.</span></span>

6. <span data-ttu-id="0a633-114">Hozzon létre számlasorokat a **Számlasorok** lapon, és adja meg a szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="0a633-114">On the **Invoice lines** tab, create invoice lines, and enter the required details.</span></span>

    <span data-ttu-id="0a633-115">Az **Adóelőlegcsoport** szakaszban az **Adószámlaszám (TAN)** mező a TAN- t, a **TDS-csoport** mező pedig a TDS-csoportot mutatja.</span><span class="sxs-lookup"><span data-stu-id="0a633-115">In the **Withholding tax group** section, the **Tax Account Number (TAN)** field shows the TAN, and the **TDS group** field shows the TDS group.</span></span>

7. <span data-ttu-id="0a633-116">Az **Ideiglenes adóelőleg-tranzakciók** lap megnyitásához válassza az **Adóelőleg** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0a633-116">Select **Withholding tax** to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="0a633-117">Az oldal felső részén a következő mezők találhatók:</span><span class="sxs-lookup"><span data-stu-id="0a633-117">The upper part of this page has the following fields:</span></span>

    - <span data-ttu-id="0a633-118">**Adóelőleg összege összesen** – A TDS-csoport tranzakciójáért kiszámított teljes TDS.</span><span class="sxs-lookup"><span data-stu-id="0a633-118">**Withholding tax amount in total** – The total TDS that was calculated for the transaction for the TDS group.</span></span>
    - <span data-ttu-id="0a633-119">**Érték** – A tranzakcióhoz a TDS kiszámításához használt teljes százalék.</span><span class="sxs-lookup"><span data-stu-id="0a633-119">**Value** – The total percentage that was used to calculate TDS for the transaction.</span></span> <span data-ttu-id="0a633-120">A teljes százalék a TDS-csoporthoz csatolt és TDS-adókódokra meghatározott képleten alapul.</span><span class="sxs-lookup"><span data-stu-id="0a633-120">The total percentage is based on the formula that is defined for the TDS tax codes and attached to the TDS group.</span></span>
    - <span data-ttu-id="0a633-121">**Korrigált forrásadó összege összesen** – A TDS csoport összes adókódjának teljes korrigált TDS-összege.</span><span class="sxs-lookup"><span data-stu-id="0a633-121">**Adjusted withholding tax amount in total** – The total adjusted TDS amount for all tax codes in the TDS group.</span></span>
    - <span data-ttu-id="0a633-122">**TDS** – A bejelölt jelölőnégyzet azt jelzi, hogy egy TDS-csoport csatolva van a tranzakcióhoz.</span><span class="sxs-lookup"><span data-stu-id="0a633-122">**TDS** – A selected checkbox indicates that a TDS group is attached to the transaction.</span></span>

    <span data-ttu-id="0a633-123">Az **Áttekintés**, **Általános** és **Kiigazítás** lapján található mezők a TDS-csoporthoz csatolt egyes TDS-adókódok számított TDS-összegét és kiigazított TDS-összegadatait jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="0a633-123">The fields on the **Overview**, **General**, and **Adjustment** tabs show the calculated TDS amount and details of the adjusted TDS amount for each TDS tax code that is attached to the TDS group.</span></span>

8. <span data-ttu-id="0a633-124">Válassza a **Küszöb** lehetőséget a **Küszöb** lap megnyitásához, ahol áttekintheti az adott TDS-adókódhoz csatolt TDS-adóösszetevőre meghatározott küszöbértéket.</span><span class="sxs-lookup"><span data-stu-id="0a633-124">Select **Threshold** to open the **Threshold** page, where you can review the threshold limit that is defined for the TDS tax component that is attached to a specific TDS tax code.</span></span>
9. <span data-ttu-id="0a633-125">Válassza a **Képlettervező** lehetőséget a **Képlettervező** oldal megnyitásához, ahol áttekintheti az adott TDS-adókódhoz definiált képletet.</span><span class="sxs-lookup"><span data-stu-id="0a633-125">Select **Formula designer** to open the **Formula designer** page, where you can review the formula that is defined for a specific TDS tax code.</span></span>
10. <span data-ttu-id="0a633-126">Szabadszöveges számla feladása.</span><span class="sxs-lookup"><span data-stu-id="0a633-126">Post the free text invoice.</span></span> <span data-ttu-id="0a633-127">A szabadszöveges számlához kiszámított TDS-összeg a TDS-csoport minden egyes TDS-adókódjára meghatározott követelésszámlára kerül.</span><span class="sxs-lookup"><span data-stu-id="0a633-127">The TDS amount that is calculated for the free text invoice is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="0a633-128">A TDS-adókódok fizetendő számláit vagy kinnlévőségszámláit az **Adóelőleg-kódok** oldalon határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="0a633-128">The receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>
11. <span data-ttu-id="0a633-129">Az **Adóelőleg-tranzakciók** lap megnyitásához válassza a **Feladott adóelőleg** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0a633-129">Select **Posted withholding tax** to open the **Withholding tax transactions** page.</span></span> <span data-ttu-id="0a633-130">Az **Érték** mező megjeleníti A tranzakcióhoz a TDS kiszámításához használt teljes százalékot.</span><span class="sxs-lookup"><span data-stu-id="0a633-130">The **Value** field shows the total percentage that was used to calculate TDS for the transaction.</span></span>

    <span data-ttu-id="0a633-131">Az **Áttekintés**, **Általános** és **Összeg** fülek mezői a számlasorokon kiszámított TDS-összegeket mutatják.</span><span class="sxs-lookup"><span data-stu-id="0a633-131">The fields on the **Overview**, **General**, and **Amount** tabs show the TDS amounts that were calculated on the invoice lines.</span></span>

12. <span data-ttu-id="0a633-132">Tekintse át a TDS-csoporthoz csatolt minden egyes TDS-adókód TDS-számítási adatait.</span><span class="sxs-lookup"><span data-stu-id="0a633-132">Review the TDS calculation information for each TDS tax code that is attached to the TDS group.</span></span>
