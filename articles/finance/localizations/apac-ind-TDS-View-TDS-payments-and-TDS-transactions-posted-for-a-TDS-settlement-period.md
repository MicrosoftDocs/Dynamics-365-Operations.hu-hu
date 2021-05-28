---
title: A TDS kiegyenlítési időszakra feladott TDS fizetések és tranzakciók megtekintése
description: Ez a témakör elmagyarázza, hogyan tekintheti meg a az elszámolási időszakra feladott Forrásnál levont adó (TDS) befizetéseket és tranzakciókat.
author: kailiang
ms.date: 03/12/2021
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
ms.openlocfilehash: 2bada42073e46c69101e6d31f3328a2eeb95f880
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023291"
---
# <a name="view-posted-tds-payments-and-transactions-for-a-tds-settlement-period"></a><span data-ttu-id="48fe6-103">A TDS kiegyenlítési időszakra feladott TDS fizetések és tranzakciók megtekintése</span><span class="sxs-lookup"><span data-stu-id="48fe6-103">View posted TDS payments and transactions for a TDS settlement period</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="48fe6-104">Ez a témakör elmagyarázza, hogyan tekintheti meg a az elszámolási időszakra feladott Forrásnál levont adó (TDS) befizetéseket és tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="48fe6-104">This topic explains how to view the Tax Deducted at Source (TDS) payments and transactions that were posted for a settlement period.</span></span>

1. <span data-ttu-id="48fe6-105">Ugorjon az **Adó \> Közvetett adók \> Adóelőleg \> Adóelőleg-kiegyenlítési időszakok** elemre.</span><span class="sxs-lookup"><span data-stu-id="48fe6-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax settlement periods**.</span></span>

    <span data-ttu-id="48fe6-106">[![Adóelőleg-kiegyenlítési időszakok oldala](./media/apac-ind-TDS-50.png)](./media/apac-ind-TDS-50.png)</span><span class="sxs-lookup"><span data-stu-id="48fe6-106">[![Withholding tax settlement periods page](./media/apac-ind-TDS-50.png)](./media/apac-ind-TDS-50.png)</span></span>

2. <span data-ttu-id="48fe6-107">Az **Adóelőleg-elszámolási időszakok** lapon válassza az **Adóelőleg-kifizetések** lehetőséget az **Adóelőlegfizetés** oldal megnyitásához, ahol megtekintheti az adott TDS-elszámolási időszakra vonatkozóan teljesített TDS-elszámolásokat.</span><span class="sxs-lookup"><span data-stu-id="48fe6-107">On the **Withholding tax settlement periods** page, select **Withholding tax payments** to open the **Withholding tax payments** page, where you can view the TDS settlements that were made for a specific TDS settlement period.</span></span>

    <span data-ttu-id="48fe6-108">Az alábbi információk láthatók az **Áttekintés** lapon:</span><span class="sxs-lookup"><span data-stu-id="48fe6-108">The **Overview** tab shows the following information:</span></span>

    - <span data-ttu-id="48fe6-109">**Dátum** – A TDS-elszámolás időszaka.</span><span class="sxs-lookup"><span data-stu-id="48fe6-109">**Date** – The date of TDS settlement.</span></span>
    - <span data-ttu-id="48fe6-110">**Bizonylat** – A TDS elszámolási tranzakció bizonylatszámának megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="48fe6-110">**Voucher** – The voucher number of the TDS settlement transaction.</span></span>
    - <span data-ttu-id="48fe6-111">**Adótípus** – Az az adótípus, amelyhez az elszámolási folyamat fut.</span><span class="sxs-lookup"><span data-stu-id="48fe6-111">**Tax type** – The tax type that the settlement process is run for.</span></span>
    - <span data-ttu-id="48fe6-112">**Adószámlaszám (TAN)** – Az elszámolt TDS tranzakció adószámlaszáma (TAN).</span><span class="sxs-lookup"><span data-stu-id="48fe6-112">**Tax Account Number (TAN)** – The Tax Account Number (TAN) of the settled TDS transaction.</span></span>
    - <span data-ttu-id="48fe6-113">**Elszámolási időszak** – Az elszámolási időszak, amelyhez futtatni szeretné a TDS elszámolási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="48fe6-113">**Settlement period** – The settlement period that the TDS settlement process is run for.</span></span>
    - <span data-ttu-id="48fe6-114">**Kezdő dátum** – Az elszámolási időszak kezdő dátuma.</span><span class="sxs-lookup"><span data-stu-id="48fe6-114">**From date** – The start date of the settlement period.</span></span>
    - <span data-ttu-id="48fe6-115">**Befejező dátum** – Az elszámolási időszak befejező dátuma.</span><span class="sxs-lookup"><span data-stu-id="48fe6-115">**To date** – The end date of the settlement period.</span></span>
    - <span data-ttu-id="48fe6-116">**Adóelőlegfizetési-változat** – Az adóelőleg-fizetés változata: **Eredeti**, **Legutóbbi helyesbítések** vagy **Teljes lista**.</span><span class="sxs-lookup"><span data-stu-id="48fe6-116">**Withholding tax payment version** – The version of the withholding tax payment: **Original**, **Latest corrections**, or **Total list**.</span></span>

5. <span data-ttu-id="48fe6-117">Válassza a **Bizonylat** lehetőséget a TDS-tranzakció bizonylatrekordjainak megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="48fe6-117">Select **Voucher** to view the voucher entries for the TDS transaction.</span></span>
6. <span data-ttu-id="48fe6-118">Válassza az **Adóelőleg-tranzakciók** lehetőséget az elszámolási időszak alatt egy adott időszakra kiegyenlített TDS-tranzakciók részleteinek megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="48fe6-118">Select **Withholding tax transactions** to view the details of the TDS transactions that were settled for a specific period during a settlement period.</span></span> <span data-ttu-id="48fe6-119">Válassza a **Bizonylat** lehetőséget a TDS-tranzakció bizonylatrekordjainak megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="48fe6-119">Select **Voucher** to view the voucher entries for the TDS transaction.</span></span> <span data-ttu-id="48fe6-120">Válassza az **Adóelőleg-összetevők** lehetőséget az Adóelőleg-összetevők lap megnyitásához, ahol megtekintheti a TDS-t, ami ki lett számítva TSD-adóösszetevőnként az adott TDS-adókódhoz.</span><span class="sxs-lookup"><span data-stu-id="48fe6-120">Select **Withholding tax components** to view the TDS that was calculated per TDS tax component for a specific TDS tax code.</span></span>
7. <span data-ttu-id="48fe6-121">Az **Adóelőlegfizetések** lap bezárásával térjen vissza **Adóelőlegelszámolási-időszakok** lapra.</span><span class="sxs-lookup"><span data-stu-id="48fe6-121">Close the **Withholding tax payments** page to return to the **Withholding tax settlement periods** page.</span></span>
8. <span data-ttu-id="48fe6-122">Válassza az **Adóelőleg-tranzakciók** lehetőséget az elszámolási időszak alatt kiegyenlített TDS-tranzakciók részleteinek megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="48fe6-122">Select **Withholding tax transactions** to view the details of the TDS transactions that were settled for the settlement period.</span></span>
