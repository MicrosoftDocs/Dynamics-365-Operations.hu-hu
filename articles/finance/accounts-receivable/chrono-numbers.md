---
title: Dokumentumok és bizonylatok időrendi számozása
description: Ez a témakör bemutatja, hogyan állíthatja be és használhatja az időrendi számozást az alkalmazandó dokumentumok és a kapcsolódó bizonylatok esetében.
author: ikond
manager: AnnBe
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 401195
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 31745632de7339d167ac9f18f02e6611e1a78b28
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104392"
---
# <a name="numbering-documents-and-vouchers-chronologically"></a><span data-ttu-id="21546-103">Dokumentumok és bizonylatok időrendi számozása</span><span class="sxs-lookup"><span data-stu-id="21546-103">Numbering documents and vouchers chronologically</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="21546-104">Egyes országokban kötelező a dokumentumok és a kapcsolódó bizonylatok időrendi számozása.</span><span class="sxs-lookup"><span data-stu-id="21546-104">In some countries, there is a legal requirement to number documents and related vouchers in chronological order.</span></span> <span data-ttu-id="21546-105">Az időszakoknak támogatniuk kell az időrendet.</span><span class="sxs-lookup"><span data-stu-id="21546-105">The chronology must be supported by periods.</span></span> <span data-ttu-id="21546-106">Minden korábbi időszakhoz tartozó számnak kisebbnek kell lennie a későbbi időszakokhoz tartozó számoknál.</span><span class="sxs-lookup"><span data-stu-id="21546-106">All of the numbers that belong to earlier periods must be less than the numbers that belong to later periods.</span></span> <span data-ttu-id="21546-107">Ennek a követelménynek megfelelően időrendi számozási funkciókat hajtottunk végre.</span><span class="sxs-lookup"><span data-stu-id="21546-107">To meet this requirement, chronological numbering functionality has been implemented.</span></span> <span data-ttu-id="21546-108">Ez a témakör bemutatja, hogyan konfigurálhatja és használhatja az időrendi számozást az alkalmazandó dokumentumok és a kapcsolódó bizonylatok esetében.</span><span class="sxs-lookup"><span data-stu-id="21546-108">This topic explains how to configure and use chronological numbers for applicable documents and related vouchers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="21546-109">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="21546-109">Prerequisites</span></span>

<span data-ttu-id="21546-110">A Funkciókezelés munkaterületen kapcsolja be az **Időrendi számozás** funkciót.</span><span class="sxs-lookup"><span data-stu-id="21546-110">In the Feature management workspace, turn on the **Chronological numbering** feature.</span></span> <span data-ttu-id="21546-111">További tájékoztatás: [Funkciókezelés – áttekintés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="21546-111">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="configure-chronological-numbering"></a><span data-ttu-id="21546-112">Időrendi számozás konfigurálása</span><span class="sxs-lookup"><span data-stu-id="21546-112">Configure chronological numbering</span></span>

<span data-ttu-id="21546-113">Az időrendi számozás a következő dokumentumokat érinti.</span><span class="sxs-lookup"><span data-stu-id="21546-113">Chronological numbering affects the following documents.</span></span>

<span data-ttu-id="21546-114">**Kinnlevőségek**</span><span class="sxs-lookup"><span data-stu-id="21546-114">**Accounts receivable**</span></span>
- <span data-ttu-id="21546-115">Vevői számla</span><span class="sxs-lookup"><span data-stu-id="21546-115">Customer invoice</span></span>
- <span data-ttu-id="21546-116">Vevői számlabizonylat</span><span class="sxs-lookup"><span data-stu-id="21546-116">Customer invoice voucher</span></span>
- <span data-ttu-id="21546-117">Értékesítési jóváírás</span><span class="sxs-lookup"><span data-stu-id="21546-117">Sales credit note</span></span>
- <span data-ttu-id="21546-118">Értékesítési jóváírás-bizonylat</span><span class="sxs-lookup"><span data-stu-id="21546-118">Sales credit note voucher</span></span>
- <span data-ttu-id="21546-119">Szabadszöveges számla</span><span class="sxs-lookup"><span data-stu-id="21546-119">Free text invoice</span></span>
- <span data-ttu-id="21546-120">Szabadszövegű számlabizonylat</span><span class="sxs-lookup"><span data-stu-id="21546-120">Free text invoice voucher</span></span>
- <span data-ttu-id="21546-121">Szabadszövegű jóváírás</span><span class="sxs-lookup"><span data-stu-id="21546-121">Free text credit note</span></span>
- <span data-ttu-id="21546-122">Szabadszövegű jóváírás-bizonylat</span><span class="sxs-lookup"><span data-stu-id="21546-122">Free text credit note voucher</span></span>
- <span data-ttu-id="21546-123">Szállítólevél</span><span class="sxs-lookup"><span data-stu-id="21546-123">Packing slip</span></span>
- <span data-ttu-id="21546-124">Szállítólevél bizonylata</span><span class="sxs-lookup"><span data-stu-id="21546-124">Packing slip voucher</span></span>
- <span data-ttu-id="21546-125">Szállítólevél korrekciós bizonylata</span><span class="sxs-lookup"><span data-stu-id="21546-125">Packing slip correction voucher</span></span>
- <span data-ttu-id="21546-126">Kamatlevél bizonylata</span><span class="sxs-lookup"><span data-stu-id="21546-126">Interest note voucher</span></span>
- <span data-ttu-id="21546-127">Fizetési felszólítás bizonylata</span><span class="sxs-lookup"><span data-stu-id="21546-127">Collection letter voucher</span></span>

<span data-ttu-id="21546-128">**Kötelezettségek**</span><span class="sxs-lookup"><span data-stu-id="21546-128">**Accounts payable**</span></span>
- <span data-ttu-id="21546-129">Számlabizonylat</span><span class="sxs-lookup"><span data-stu-id="21546-129">Invoice voucher</span></span>
- <span data-ttu-id="21546-130">Jóváírás bizonylata</span><span class="sxs-lookup"><span data-stu-id="21546-130">Credit note voucher</span></span>
- <span data-ttu-id="21546-131">Termékbevételezési bizonylat</span><span class="sxs-lookup"><span data-stu-id="21546-131">Product receipt voucher</span></span>

<span data-ttu-id="21546-132">**Projektvezetés**</span><span class="sxs-lookup"><span data-stu-id="21546-132">**Project management**</span></span>
- <span data-ttu-id="21546-133">Számla</span><span class="sxs-lookup"><span data-stu-id="21546-133">Invoice</span></span>
- <span data-ttu-id="21546-134">Számlabizonylat</span><span class="sxs-lookup"><span data-stu-id="21546-134">Invoice voucher</span></span>
- <span data-ttu-id="21546-135">Jóváírás</span><span class="sxs-lookup"><span data-stu-id="21546-135">Credit note</span></span>
- <span data-ttu-id="21546-136">Jóváírás bizonylata</span><span class="sxs-lookup"><span data-stu-id="21546-136">Credit note voucher</span></span> 

### <a name="define-number-sequences"></a><span data-ttu-id="21546-137">Számsorozatok meghatározása</span><span class="sxs-lookup"><span data-stu-id="21546-137">Define number sequences</span></span>

<span data-ttu-id="21546-138">Számsorozatok meghatározásához lépjen a **Szervezeti adminisztráció** > **Számsorozatok** > **Számsorozatok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="21546-138">To define number sequences, go to **Organization administration** > **Number sequences** > **Number sequences**.</span></span> <span data-ttu-id="21546-139">Annyi számsorozatot adhat meg, amennyi csak szükséges a szükséges dokumentumok érintett periódusainak lefedéséhez.</span><span class="sxs-lookup"><span data-stu-id="21546-139">You can define as many number sequences as required to cover the affected periods for required documents.</span></span> 

<span data-ttu-id="21546-140">Minden számsorozathoz adjon meg egy vállalatot.</span><span class="sxs-lookup"><span data-stu-id="21546-140">Specify a company for each number sequence.</span></span> <span data-ttu-id="21546-141">A számsorozatok szegmenseit úgy kell meghatározni, hogy az időszakok időrendi sorrendben jelenjenek meg.</span><span class="sxs-lookup"><span data-stu-id="21546-141">The segments of the number sequences must be defined so that they provide chronological order for periods.</span></span> <span data-ttu-id="21546-142">A szegmensnevek tartalmazhatnak például egy speciális előtagot, amely az adott időszakot azonosítja.</span><span class="sxs-lookup"><span data-stu-id="21546-142">For example, the segment names can contain a special prefix that identifies a specific period.</span></span>

![Számsorozat beállítása](media/chrono-num-sequence.jpg)

### <a name="configure-number-sequence-groups"></a><span data-ttu-id="21546-144">Számsorozatcsoportok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="21546-144">Configure number sequence groups</span></span>

<span data-ttu-id="21546-145">A számsorozatcsoportok konfigurálához kattintson a **Kinnlevőségek** > **Beállítás** > **Kinnlévőségek paraméterei** gombra.</span><span class="sxs-lookup"><span data-stu-id="21546-145">To configure number sequence groups, go to **Accounts receivable** > **Setup** > **Accounts receivable parameters**.</span></span> <span data-ttu-id="21546-146">A **Számsorozatok** lapon definiálja az érintett időszakok fedezésére szükséges számsorozatcsoportokat.</span><span class="sxs-lookup"><span data-stu-id="21546-146">On the **Number sequences** tab, define as many number sequences groups as required to cover the affected periods.</span></span> 

<span data-ttu-id="21546-147">Mindegyik csoportnál a **Hivatkozás** szakaszban válassza ki a támogatott dokumentumhivatkozások valamelyikét, és a **Számsorozatkód** mezőben hivatkozzon egy, a kapcsolódó időszakhoz korábban létrehozott számsorozatra.</span><span class="sxs-lookup"><span data-stu-id="21546-147">For each group, in the **Reference** section, select one of the supported document references, and in the **Number sequence code** field, refer to a number sequence that was previously created for the related period.</span></span>

![Sorozatszámcsoport beállítása](media/chrono-num-sequence-group.jpg)

<span data-ttu-id="21546-149">Ehhez hasonlóan állítsa be a számsorozatcsoportokat a **Kötelezettségek** és a **Projektvezetés és könyvelés** modulban is.</span><span class="sxs-lookup"><span data-stu-id="21546-149">Similarly, configure number sequence groups in **Accounts payable** and **Project management and accounting** modules.</span></span>

### <a name="configure-number-sequence-groups-chronology"></a><span data-ttu-id="21546-150">Számsorozatcsoportok konfigurálásának időrendje</span><span class="sxs-lookup"><span data-stu-id="21546-150">Configure number sequence groups chronology</span></span>

<span data-ttu-id="21546-151">A számsorozatcsoportok időrendi konfigurációját a **Szervezeti adminisztráció** > **Számsorozatok** > **Időrendi számsorozatcsoportok** pontban állítsa be.</span><span class="sxs-lookup"><span data-stu-id="21546-151">To configure number sequence groups chronology, go to **Organization administration** > **Number sequences** > **Chronological number sequence groups**.</span></span> <span data-ttu-id="21546-152">Határozza meg a számsorozatcsoportok alkalmazhatósági feltételeit.</span><span class="sxs-lookup"><span data-stu-id="21546-152">Define the applicability conditions for number sequence groups.</span></span>

![Időrendi számok beállítása](media/chrono-num-sequence-group-period.jpg)

| <span data-ttu-id="21546-154">Mező</span><span class="sxs-lookup"><span data-stu-id="21546-154">Field</span></span>            | <span data-ttu-id="21546-155">Leírás</span><span class="sxs-lookup"><span data-stu-id="21546-155">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="21546-156">Érvénybe lépés</span><span class="sxs-lookup"><span data-stu-id="21546-156">Effective</span></span>  | <span data-ttu-id="21546-157">A számsorozatcsoport alkalmazhatóságának kezdő dátuma.</span><span class="sxs-lookup"><span data-stu-id="21546-157">The start date of number sequence group applicability.</span></span> |
| <span data-ttu-id="21546-158">Lejárat</span><span class="sxs-lookup"><span data-stu-id="21546-158">Expiration</span></span>      | <span data-ttu-id="21546-159">A számsorozatcsoport alkalmazhatóságának záró dátuma.</span><span class="sxs-lookup"><span data-stu-id="21546-159">The end date of number sequence group applicability.</span></span> <span data-ttu-id="21546-160">Ha nem alkalmaz záró dátumot, válassza a **Soha** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="21546-160">If no end date is applied, select **Never**.</span></span> |
| <span data-ttu-id="21546-161">Számsorozatcsoport</span><span class="sxs-lookup"><span data-stu-id="21546-161">Number sequence group</span></span> | <span data-ttu-id="21546-162">Az a számsorozatcsoport, amelyet a bizonylatszámok előállításához használ az adott időszakban.</span><span class="sxs-lookup"><span data-stu-id="21546-162">Number sequence group that will be used to generate document numbers during the period.</span></span> |
| <span data-ttu-id="21546-163">Eredeti számsorozatcsoport</span><span class="sxs-lookup"><span data-stu-id="21546-163">Original number sequence group</span></span> | <span data-ttu-id="21546-164">A rendszer ezt a számsorozatcsoport-kódot használja az olyan esetek további szűrésére, amikor a dokumentumokhoz már hozzá van rendelve egy konkrét *állandó* számsorozatcsoport.</span><span class="sxs-lookup"><span data-stu-id="21546-164">This number sequence group code is used for additional filtering for the cases when documents already have a specific *permanent* number sequence group assigned.</span></span> <span data-ttu-id="21546-165">Az üres érték konkrét értéknek számít.</span><span class="sxs-lookup"><span data-stu-id="21546-165">An empty value is considered a specific value.</span></span> <span data-ttu-id="21546-166">Ha figyelmen kívül kell hagynia egy előzetes hozzárendelt csoportot, használja az **Alapértelmezett** lehetőséget ehhez a beállításhoz.</span><span class="sxs-lookup"><span data-stu-id="21546-166">If you need to ignore a preliminary assigned group, use the **Default** option for this setup.</span></span> |
| <span data-ttu-id="21546-167">Alapértelmezett</span><span class="sxs-lookup"><span data-stu-id="21546-167">Default</span></span> | <span data-ttu-id="21546-168">Ha be van kapcsolva, a rendszer figyelmen kívül hagyja az előzetes hozzárendelt dokumentumszám-sorozatcsoportot, és csak az időszakok kezdő és záró dátumát használja az alkalmazhatósági elemzéshez.</span><span class="sxs-lookup"><span data-stu-id="21546-168">If turned on, the system ignores the preliminary assigned document number sequence group and uses only the periods start and end dates for applicability analysis.</span></span> <span data-ttu-id="21546-169">Ha ki van kapcsolva, a rendszer a kijelöléshez a **Hatályos** + **Lejárat** + **Eredeti számsorozatcsoport** teljes kombinációját használja.</span><span class="sxs-lookup"><span data-stu-id="21546-169">If turned off, the system uses the full combination **Effective** + **Expiration** + **Original number sequence group** for selection.</span></span> |

## <a name="document-posting"></a><span data-ttu-id="21546-170">Dokumentum feladása</span><span class="sxs-lookup"><span data-stu-id="21546-170">Document posting</span></span>
<span data-ttu-id="21546-171">Dokumentum feladásakor a program a dokumentum feladási dátuma alapján hozzárendeli a megfelelő számsorozatcsoportot a dokumentumhoz, majd az észlelt számsorozaton alapuló dokumentumszám előállítására használja.</span><span class="sxs-lookup"><span data-stu-id="21546-171">When you post a document, the appropriate number sequence group is assigned to the document, based on document's posting date, and then used to generate a document number based on the detected number sequence.</span></span> <span data-ttu-id="21546-172">A rendszer üzenetet küld a számsorozatcsoport hozzárendelésével kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="21546-172">The system provides a message regarding the number sequence group assignment.</span></span>

![Bizonylatszám](media/chrono-num-sequence-fti.jpg)

> [!NOTE]
> <span data-ttu-id="21546-174">Egyes országokban már létezik a dokumentumszámozáshoz meghatározott logika.</span><span class="sxs-lookup"><span data-stu-id="21546-174">For some countries, there is a specific logic already implemented for document numbering.</span></span> <span data-ttu-id="21546-175">Ebben az esetben az országspecifikus logika felülbírálja az **Időrendi számozás** funkciót.</span><span class="sxs-lookup"><span data-stu-id="21546-175">In this case, country-specific logic will override the **Chronological numbering** feature.</span></span>