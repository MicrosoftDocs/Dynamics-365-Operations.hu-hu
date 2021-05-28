---
title: Tanúsítványszámok és -dátumok frissítése TDS-tranzakciókhoz
description: Ez a témakör elmagyarázza, hogyan lehet frissíteni a visszaigényelhető tanúsítványszámokat és dátumokat frissíteni, amelyek a szállítói, ügyfél- és könyvelési számlákhoz lettek rögzítve a Forrásnál levont adóhoz (TDS).
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
ms.openlocfilehash: 248de8e12703a84482b67d0899857a6efb33531c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023294"
---
# <a name="update-certificate-numbers-and-dates-for-tds-transactions"></a><span data-ttu-id="948e3-103">Tanúsítványszámok és -dátumok frissítése TDS-tranzakciókhoz</span><span class="sxs-lookup"><span data-stu-id="948e3-103">Update certificate numbers and dates for TDS transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="948e3-104">Ez a témakör elmagyarázza, hogyan lehet frissíteni a visszaigényelhető tanúsítványszámokat és dátumokat frissíteni, amelyek a szállítói, ügyfél- és könyvelési számlákhoz lettek rögzítve a Forrásnál levont adóhoz (TDS).</span><span class="sxs-lookup"><span data-stu-id="948e3-104">This topic explains how to update the recoverable certificate numbers and dates that were recorded for vendor, customer, and ledger accounts for Tax Deducted at Source (TDS).</span></span> <span data-ttu-id="948e3-105">A TDS-tranzakciók tanúsítványait a **Visszatéríthető tanúsítványok** lapon lehet megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="948e3-105">You can view the certificates for TDS transactions on the **Recoverable certificates** page.</span></span> <span data-ttu-id="948e3-106">A tanúsítványokat a **Tanúsítványok frissítése** lapon frissítheti.</span><span class="sxs-lookup"><span data-stu-id="948e3-106">You can update the certificates by using the **Update Certificates** page.</span></span>

<span data-ttu-id="948e3-107">Kövesse az alábbi lépéseket a TDS-tanúsítványok számának és dátumának frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="948e3-107">Follow these steps to update certificate numbers and dates for TDS transactions.</span></span>

1. <span data-ttu-id="948e3-108">Lépjen ide: **Adó \> Bevallások \> Adóelőleg \> Tanúsítvány frissítése**.</span><span class="sxs-lookup"><span data-stu-id="948e3-108">Go to **Tax \> Declarations \> Withholding tax \> Update certificate**.</span></span>

    <span data-ttu-id="948e3-109">[![Tanúsítvány frissítése oldal](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)</span><span class="sxs-lookup"><span data-stu-id="948e3-109">[![Update certificate page](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)</span></span>

2. <span data-ttu-id="948e3-110">A **Tanúsítvány frissítése** lapon, az **Adótípus** mezőben a **Kijelölés** szakaszában válassza ki a **TDS** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="948e3-110">On the **Update certificate** page, in the **Select** section, in the **Tax type** field, select **TDS**.</span></span>
3. <span data-ttu-id="948e3-111">A **Tanúsítvány** száma mezőben válassza ki a vevő vagy a szállító TDS-tanúsítványának számát.</span><span class="sxs-lookup"><span data-stu-id="948e3-111">In the **Certificate number** field, select the customer's or vendor's TDS certificate number.</span></span>

    > [!NOTE]
    > <span data-ttu-id="948e3-112">A **Tanúsítvány száma** mező csak azokat a TDS-tanúsítványszámokat sorolja fel, amelyek esetében a **Visszaállítható tanúsítványok** lapon törölve van a jelölés a **Lezárt** jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="948e3-112">The **Certificate number** field lists only TDS certificate numbers that the **Closed** check box is cleared for on the **Recoverable certificates** page.</span></span>

    <span data-ttu-id="948e3-113">A **Tanúsítvány dátuma** mező jeleníti meg a tanúsítvány dátumát.</span><span class="sxs-lookup"><span data-stu-id="948e3-113">The **Certificate date** field shows the certificate date.</span></span> <span data-ttu-id="948e3-114">A **Számlatípus** mező mutatja annak a számlának a típusát, amelyhez a TDS-tanúsítvány száma érkezett, a **Név** mezőben pedig a számla neve látható.</span><span class="sxs-lookup"><span data-stu-id="948e3-114">The **Account type** field shows the type of account that the TDS certificate number is received for, and the **Name** field shows the name of the account.</span></span>

5. <span data-ttu-id="948e3-115">Az **Kezdő dátum** és a **Záró dátum** mezőkben, válassza ki a az időszak kezdő és záró dátumát, amelyhez meg szeretné jeleníteni a TDS-tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="948e3-115">In the **From date** and **To date** fields, select the start and end dates of the period to show the TDS transactions for.</span></span>
6. <span data-ttu-id="948e3-116">Az **Adatok megjelenítése** lehetőséget választva megtekintheti a kijelölt időszakban könyvelt TDS-tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="948e3-116">Select **Show data** to view the TDS transactions that were posted during the selected period.</span></span>

    <span data-ttu-id="948e3-117">Az **Áttekintés** lapon a felső ablaktábla rácsa a szállítóhoz vagy vevőhöz a megadott időszakban feladott minden egyes TDS-tranzakcióval kapcsolatban a következő adatokat mutatja:</span><span class="sxs-lookup"><span data-stu-id="948e3-117">On the **Overview** tab, the grid in the upper pane shows the following information about each TDS transaction that was posted for the vendor or customer during the selected period:</span></span>

    - <span data-ttu-id="948e3-118">**Bizonylat** – A TDS-tranzakció bizonylatszámának megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="948e3-118">**Voucher** – The voucher number of the TDS transaction.</span></span>
    - <span data-ttu-id="948e3-119">**Dátum** – A kiválasztott TDS-tranzakció dátuma.</span><span class="sxs-lookup"><span data-stu-id="948e3-119">**Date** – The date of the TDS transaction.</span></span>
    - <span data-ttu-id="948e3-120">**Összeg** – Az a számlaösszeg, amelyen a TDS kiszámításra került.</span><span class="sxs-lookup"><span data-stu-id="948e3-120">**Amount** – The invoice amount that the TDS was calculated on.</span></span>
    - <span data-ttu-id="948e3-121">**Adóösszeg** – A tranzakcióhoz kiszámított TDS-adóösszeg.</span><span class="sxs-lookup"><span data-stu-id="948e3-121">**Tax amount** – The TDS tax amount that was calculated for the transaction.</span></span>

7. <span data-ttu-id="948e3-122">A felső rácsból konkrét TDS-tranzakciók áthelyezéséhez az alsó rácsba, jelölje ki a tranzakciókat, majd válassza a **Belefoglalás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="948e3-122">To move specific TDS transactions from the upper grid to the lower grid, select the transactions, and then select **Include**.</span></span> <span data-ttu-id="948e3-123">Másik lehetőségként válassza az **Összes belefoglalása** lehetőséget az összes TDS-tranzakciót áthelyezéséhez a felső rácsból az alsó rácsba.</span><span class="sxs-lookup"><span data-stu-id="948e3-123">Alternatively, select **Include all** to move all TDS transactions from the upper grid to the lower grid.</span></span>

    <span data-ttu-id="948e3-124">Ha konkrét TDS-tranzakciókat vagy minden TDS-tranzakciót át szeretne áthelyezni az alsó rácsból a felső rácsba, használja a **Kihagyás** vagy az **Összes kihagyása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="948e3-124">To move specific TDS transactions or all TDS transactions from the lower grid to the upper grid, use the **Exclude** or **Exclude all** button.</span></span>

8. <span data-ttu-id="948e3-125">A **Frissítés** lehetőséget választva frissítheti az alsó rácsban a TDS-tranzakciók **Tanúsítványszám** és **Tanúsítvány dátuma** mezőit.</span><span class="sxs-lookup"><span data-stu-id="948e3-125">Select **Update** to update the **Certificate number** and **Certificate date** fields for TDS transactions in the lower grid.</span></span>
10. <span data-ttu-id="948e3-126">Menjen az **Adó \> Közvetett adók \> Adóelőleg \> Visszaállítható tanúsítvány** menübe és a **Lekérdezés** lehetőséget választva megtekintheti azokat a frissített tranzakciósorokat, amelyek az új tanúsítványszámokat tartalmazzák a **Tanúsítványtranzakciók** oldalon.</span><span class="sxs-lookup"><span data-stu-id="948e3-126">Go to **Tax \> Indirect taxes \> Withholding tax \> Recoverable certificate**, and select **Inquiry** to view the updated transaction lines that have the new certificate numbers on the **Certificate transactions** page.</span></span>

    <span data-ttu-id="948e3-127">[![Tanúsítványtranzakciók oldal](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)</span><span class="sxs-lookup"><span data-stu-id="948e3-127">[![Certificate transactions page](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)</span></span>
