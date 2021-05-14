---
title: A TaxTrans-rekord nem jön létre
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítséget nyújtnak, arra az esetre ha egy TaxTrans rekord nem jön létre.
author: qire
manager: beya
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 0c7414cc39198ff4d5be9b4c41ca62f9c78c9250
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947649"
---
# <a name="taxtrans-record-isnt-generated"></a><span data-ttu-id="9aca3-103">A TaxTrans-rekord nem jön létre</span><span class="sxs-lookup"><span data-stu-id="9aca3-103">TaxTrans record isn't generated</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9aca3-104">Ha egy tranzakcióhoz a **Feladott áfa** lehetőséget választja, de a **Feladott áfa** lapon vagy nincsenek adósorok, vagy hiányzik egy adósor, akkor előfordulhat, hogy a **TaxTrans** rekord nem lett létrehozva.</span><span class="sxs-lookup"><span data-stu-id="9aca3-104">If you select **Posted sales tax** for a transaction, but the **Posted sales tax** page either shows no tax lines or is missing a tax line, the **TaxTrans** record might not have been generated.</span></span>

<span data-ttu-id="9aca3-105">[![Feladott, sorelemeket nem tartalmazó áfaoldal](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="9aca3-105">[![Posted sales tax page that has no line items](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)</span></span>

<span data-ttu-id="9aca3-106">A probléma elhárításához igény szerint kövesse az alábbi szakaszok lépéseit.</span><span class="sxs-lookup"><span data-stu-id="9aca3-106">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="check-the-sales-tax-before-you-post-the-transaction"></a><span data-ttu-id="9aca3-107">Az áfa ellenőrzése a tranzakció feladása előtt</span><span class="sxs-lookup"><span data-stu-id="9aca3-107">Check the sales tax before you post the transaction</span></span>

1. <span data-ttu-id="9aca3-108">Mielőtt feladja a tranzakciót, a **Számla feladása** lapon válassza az **Áfa** lehetőséget a számítás ellenőrzéséhez.</span><span class="sxs-lookup"><span data-stu-id="9aca3-108">Before you post the transaction, on the **Posting invoice** page, select **Sales tax** to check the calculation.</span></span>

    <span data-ttu-id="9aca3-109">[![Áfa gomb a Számla feladása lapon](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="9aca3-109">[![Sales tax button on the Posting invoice page](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)</span></span>

2. <span data-ttu-id="9aca3-110">Az **Ideiglenes áfatranzakciók** lapon ellenőrizze a számítás eredményét.</span><span class="sxs-lookup"><span data-stu-id="9aca3-110">On the **Temporary sales tax transactions** page, review the result of the calculation.</span></span> <span data-ttu-id="9aca3-111">Ha nincs kiszámítva adó, akkor lásd: [Az adó nincs kiszámítva, vagy az adó összege nulla](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).</span><span class="sxs-lookup"><span data-stu-id="9aca3-111">If no tax is calculated, see [Tax isn't calculated or the tax amount is zero](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).</span></span>

## <a name="find-the-taxtrans-record-in-all-posted-sales-tax"></a><span data-ttu-id="9aca3-112">A TaxTrans rekord megkeresése az összes feladott áfa között</span><span class="sxs-lookup"><span data-stu-id="9aca3-112">Find the TaxTrans record in all posted sales tax</span></span>

1. <span data-ttu-id="9aca3-113">Ugorjon az **Adó** \> **Igénylések és jelentések** \> **Áfaigénylések** > **Feladott áfa** pontra.</span><span class="sxs-lookup"><span data-stu-id="9aca3-113">Go to **Tax** \> **Inquiries and reports** \> **Sales tax inquiries** > **Posted sales tax**.</span></span>
2. <span data-ttu-id="9aca3-114">A **Bizonylat** oszlop fejlécében válassza ki a szűrőszimbólumot a **TaxTrans** rekord megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="9aca3-114">In the **Voucher** column heading, select the filter symbol to find the **TaxTrans** record.</span></span>
3. <span data-ttu-id="9aca3-115">Ha a keresett áfarekordokat megtalálja, ellenőrizze a dátumot.</span><span class="sxs-lookup"><span data-stu-id="9aca3-115">If you find the sales tax records that you're looking for, check the date.</span></span> <span data-ttu-id="9aca3-116">Ha a dátum eltér a naplófejléc dátumától, hozzon létre egy Microsoft szolgáltatáskérést további segítségért.</span><span class="sxs-lookup"><span data-stu-id="9aca3-116">If the date differs from the date of the journal header, create a Microsoft service request for additional support.</span></span>

    <span data-ttu-id="9aca3-117">[![Feladott áfa oldal](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="9aca3-117">[![Posted sales tax page](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)</span></span>

## <a name="debug-to-check-details"></a><span data-ttu-id="9aca3-118">Hibakeresés a részletek ellenőrzéshez</span><span class="sxs-lookup"><span data-stu-id="9aca3-118">Debug to check details</span></span>

1. <span data-ttu-id="9aca3-119">További információért a hibakeresésről és annak megállapításához, hogy a **TmpTaxWorkTrans** és a **TaxUncommitted** helyesen van-e létrehozva lásd a [TaxTrans mezőértéke helytelen](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md) részt.</span><span class="sxs-lookup"><span data-stu-id="9aca3-119">For information about how to debug and determine whether **TmpTaxWorkTrans** and **TaxUncommitted** are correctly generated, see [Field value in TaxTrans is incorrect](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).</span></span>
2. <span data-ttu-id="9aca3-120">Ha a **TaxTmpWorkTrans** vagy a **TaxUncommitted** helyesen van létrehozva, adjon meg egy töréspontot a **TaxPost::SaveAndPost()** és a **Tax::SaveAndPost()** helyen, hogy meghatározza, miért nem lett beszúrva a **TaxTrans**.</span><span class="sxs-lookup"><span data-stu-id="9aca3-120">If **TaxTmpWorkTrans** or **TaxUncommitted** is correctly generated, add a breakpoint at **TaxPost::SaveAndPost()** and **Tax::SaveAndPost** to debug the reason why **TaxTrans** isn't inserted.</span></span>

    <span data-ttu-id="9aca3-121">[![Kódhoz hozzáadott töréspontok](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="9aca3-121">[![Breakpoints added in code](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)</span></span>

    <span data-ttu-id="9aca3-122">[![A hozzáadott töréspontok eredményei](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="9aca3-122">[![Results of added breakpoints](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="9aca3-123">Annak meghatározása, hogy létezik-e testreszabás</span><span class="sxs-lookup"><span data-stu-id="9aca3-123">Determine whether customization exists</span></span>

<span data-ttu-id="9aca3-124">Ha az előző szakaszokban már befejezte a lépéseket, de nem találta meg a problémát, határozza meg, hogy van-e testreszabás.</span><span class="sxs-lookup"><span data-stu-id="9aca3-124">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="9aca3-125">Ha nem létezik testreszabás, hozzon létre egy Microsoft szolgáltatáskérést további segítségért.</span><span class="sxs-lookup"><span data-stu-id="9aca3-125">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
