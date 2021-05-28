---
title: TDS visszatéríthető tanúsítvány számának rögzítése
description: Ez a témakör elmagyarázza, hogyan lehet a Visszatéríthető tanúsítványok oldalt használni az adott szállítóhoz, vevőhöz vagy főkönyvhöz tartozó Forrásnál levont adó (TDS) tanúsítványszámainak és dátumainak rögzítéséhez.
author: kailiang
mms.date: 02/12/2021
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
ms.openlocfilehash: b501c331cccc6d030f36d0a13ba0a6a13c08c733
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023284"
---
# <a name="record-tds-recoverable-certificate-numbers"></a><span data-ttu-id="78c12-103">TDS visszatéríthető tanúsítvány számának rögzítése</span><span class="sxs-lookup"><span data-stu-id="78c12-103">Record TDS recoverable certificate numbers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78c12-104">Ez a témakör elmagyarázza, hogyan lehet a **Visszatéríthető tanúsítványok** oldalt használni az adott szállítóhoz, vevőhöz vagy főkönyvhöz tartozó Forrásnál levont adó (TDS) tanúsítványszámainak és dátumainak rögzítéséhez.</span><span class="sxs-lookup"><span data-stu-id="78c12-104">This topic explains how to use the **Recoverable certificates** page to record the certificate numbers and dates for Tax Deducted at Source (TDS) certificates that are received for a specific vendor, customer, or ledger.</span></span> <span data-ttu-id="78c12-105">Az ezen az oldalon a TDS-tranzakcióknál rögzített TDS-bizonylatszámok és dátumok frissítéséhez használja a **Tanúsítvány frissítése** lapot (**Főkönyv \> Időszakos \> Adóelőleg \> Tanúsítvány frissítése**).</span><span class="sxs-lookup"><span data-stu-id="78c12-105">To update the TDS certificate numbers and dates that are recorded for TDS transactions on this page, use the **Update certificate** page (**General ledger \> Periodic \> Withholding tax \> Update certificate**).</span></span> <span data-ttu-id="78c12-106">Miután befejezte a TDS-tanúsítványszámok frissítését, zárja be azokat.</span><span class="sxs-lookup"><span data-stu-id="78c12-106">After you've finished updating TDS certificate numbers, close them.</span></span>

<span data-ttu-id="78c12-107">Kövesse az alábbi lépéseket a TDS-tanúsítványok számának és dátumának rögzítéséhez.</span><span class="sxs-lookup"><span data-stu-id="78c12-107">Follow these steps to record the TDS certificate numbers and dates.</span></span>

1. <span data-ttu-id="78c12-108">Ugorjon az **Adó \> Közvetett adó \> Adóelőleg \> Visszatéríthető tanúsítvány** elemre.</span><span class="sxs-lookup"><span data-stu-id="78c12-108">Go to **Tax \> Indirect tax \> Withholding tax \> Recoverable certificates**.</span></span>

    <span data-ttu-id="78c12-109">[![Visszatéríthető tanúsítványok lap](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png)</span><span class="sxs-lookup"><span data-stu-id="78c12-109">[![Recoverable certificates page](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png)</span></span> 

2. <span data-ttu-id="78c12-110">A **Visszatéríthető tanúsítványok** lapon az **Adó típusa** mezőben válassza a **TDS** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="78c12-110">On the **Recoverable certificates** page, in the **Tax type** field, select **TDS**.</span></span>
3. <span data-ttu-id="78c12-111">Válassza az **Új** lehetőséget egy rekord létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="78c12-111">Select **New** to create a record.</span></span>
4. <span data-ttu-id="78c12-112">A **Tanúsítvány száma** mezőben adja meg a TDS-tanúsítvány számát.</span><span class="sxs-lookup"><span data-stu-id="78c12-112">In the **Certificate number** field, enter the TDS certificate number.</span></span>
5. <span data-ttu-id="78c12-113">A **Számlatípus** mezőben válassza ki azt a számlatípust, amelyhez a TDS-tanúsítvány érkezik: **Szállító**, **Vevő** vagy **Főkönyv**.</span><span class="sxs-lookup"><span data-stu-id="78c12-113">In the **Account type** field, select the type of account that the TDS certificate is received for: **Vendor**, **Customer**, or **Ledger**.</span></span>
6. <span data-ttu-id="78c12-114">A **Számla** mezőben válassza ki a szállító, a vevő vagy a főkönyv számlaszámát a kiválasztott számlatípustól függően.</span><span class="sxs-lookup"><span data-stu-id="78c12-114">In the **Account** field, select the vendor, customer, or ledger account number, depending on the account type that you selected.</span></span> <span data-ttu-id="78c12-115">A **Név** mező a szállító, a vevő vagy a főkönyv számlanevét mutatja.</span><span class="sxs-lookup"><span data-stu-id="78c12-115">The **Name** field shows the name of the vendor, customer, or ledger account.</span></span>
7. <span data-ttu-id="78c12-116">A **Tanusítvány összege** mezőbe írja be a TDS-tanúsítvány összegét.</span><span class="sxs-lookup"><span data-stu-id="78c12-116">In the **Certificate amount** field, enter the amount of the TDS certificate.</span></span>
8. <span data-ttu-id="78c12-117">A **Dátum** mezőben adja meg a tanúsítvány számának tanúsítványidejét.</span><span class="sxs-lookup"><span data-stu-id="78c12-117">In the **Date** field, enter the certificate date for the certificate number.</span></span>
9. <span data-ttu-id="78c12-118">Válassza a **Lekérdezések** lehetőséget a **Tanúsítványtranzakciók** oldal megnyitásához, ahol megtekintheti azokat a TDS-tranzakciókat, amelyekhez a TDS-tanúsítvány száma és dátuma frissül.</span><span class="sxs-lookup"><span data-stu-id="78c12-118">Select **Inquiries** to open the **Certificate transactions** page, where you can view the TDS transactions that the TDS certificate number and date are updated for.</span></span> <span data-ttu-id="78c12-119">Ez az információ frissíthető a **Tanúsítvány frissítése** oldalon (**Adó \> Bevallások \> Adóelőleg \> Tanúsítvány frissítése**).</span><span class="sxs-lookup"><span data-stu-id="78c12-119">This information can be updated on the **Update certificate** page (**Tax \> Declarations \> Withholding tax \> Update certificate**).</span></span>

    <span data-ttu-id="78c12-120">A **Tanúsítvány frissítése** lapon az egyes TDS-tranzakciókra vonatkozó következő információk találhatók:</span><span class="sxs-lookup"><span data-stu-id="78c12-120">The **Update certificate** page shows the following information for each TDS transaction:</span></span>

    - <span data-ttu-id="78c12-121">**Dátum** – A kiválasztott TDS-tranzakció feladási dátuma.</span><span class="sxs-lookup"><span data-stu-id="78c12-121">**Date** – The posting date of the TDS transaction.</span></span>
    - <span data-ttu-id="78c12-122">**Bizonylat** – A TDS-tranzakció bizonylatszámának megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="78c12-122">**Voucher** – The voucher number of the TDS transaction.</span></span>
    - <span data-ttu-id="78c12-123">**Forrás** – A modul, amelyben a TDS-tranzakció létrejött.</span><span class="sxs-lookup"><span data-stu-id="78c12-123">**Source** – The module that the TDS transaction was created in.</span></span>
    - <span data-ttu-id="78c12-124">**Számla** – Az a szállítói, vevői vagy főkönyvi számlaszám, amelyhez a TDS-tranzakció készült.</span><span class="sxs-lookup"><span data-stu-id="78c12-124">**Account** – The vendor, customer, or ledger account number that the TDS transaction was created for.</span></span>
    - <span data-ttu-id="78c12-125">**Név** – Az a szállítói, vevői vagy főkönyvi számlanév, amelyhez a TDS-tranzakció készült.</span><span class="sxs-lookup"><span data-stu-id="78c12-125">**Name** – The name of the vendor, customer, or ledger account that the TDS transaction was created for.</span></span>
    - <span data-ttu-id="78c12-126">**Összeg** – Az a számlaösszeg, amelyen a TDS kiszámításra került.</span><span class="sxs-lookup"><span data-stu-id="78c12-126">**Amount** – The invoice amount that the TDS was calculated on.</span></span>
    - <span data-ttu-id="78c12-127">**Adóösszeg** – A tranzakcióhoz kiszámított TDS-adóösszeg.</span><span class="sxs-lookup"><span data-stu-id="78c12-127">**Tax amount** – The TDS tax amount that was calculated for the transaction.</span></span>
    - <span data-ttu-id="78c12-128">**Tanúsítvány dátuma** – A TDS-tranzakcióhoz frissített TDS-tanúsítvány dátuma.</span><span class="sxs-lookup"><span data-stu-id="78c12-128">**Certificate date** – The TDS certificate date that was updated for the TDS transaction.</span></span>
    - <span data-ttu-id="78c12-129">**Tanúsítvány száma** – A TDS-tranzakcióhoz frissített TDS-tanúsítvány száma.</span><span class="sxs-lookup"><span data-stu-id="78c12-129">**Certificate number** – TDS certificate number that was updated for the TDS transaction.</span></span>

10. <span data-ttu-id="78c12-130">A **Visszatéríthető tanúsítványok** lapon jelölje be a **Lezárt** jelölőnégyzetet a TDS-tanúsítványszám bezárásához, miután befejezte a TDS-tranzakciók frissítését a **Tanúsítvány frissítése** lapon.</span><span class="sxs-lookup"><span data-stu-id="78c12-130">On the **Recoverable certificates** page, select the **Closed** check box to close the TDS certificate number after you've finished updating it for TDS transactions on the **Update certificate** page.</span></span>

    <span data-ttu-id="78c12-131">Ha ki szeretné választani az oldal összes rekordjának **Lezárt** jelölőnégyzetét, válassza az **Összes jelölése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="78c12-131">To select the **Closed** check box for all records on the page, select **Mark all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="78c12-132">A **Lezárt** jelölőnégyzet által kiválasztott TDS-tanúsítványszámok nem érhetők el a **Tanúsítvány frissítése** lapon.</span><span class="sxs-lookup"><span data-stu-id="78c12-132">TDS certificate numbers that the **Closed** check box is selected for aren't available on the **Update certificate** page.</span></span>
