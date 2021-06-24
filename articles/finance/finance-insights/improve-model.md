---
title: Az előrejelzési modell javítása (előzetes verzió)
description: Ez a témakör az előrejelzési modellek teljesítményének javítására használható funkciókat ismerteti.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 184a1cb5d3851e26b41340b711c51ef38e06eb53
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186642"
---
# <a name="improve-the-prediction-model-preview"></a><span data-ttu-id="50c44-103">Az előrejelzési modell javítása (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="50c44-103">Improve the prediction model (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="50c44-104">Ez a témakör az előrejelzési modellek teljesítményének javítására használható funkciókat ismerteti.</span><span class="sxs-lookup"><span data-stu-id="50c44-104">This topic describes features that you can use to improve the performance of prediction models.</span></span> <span data-ttu-id="50c44-105">A modell javítását a Microsoft Dynamics 365 Finance **Vevői fizetési előrejelzések** munkaterületen kezdi el.</span><span class="sxs-lookup"><span data-stu-id="50c44-105">You start to improve your model in the **Customer payment predictions** workspace in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="50c44-106">A fejlesztési lépéseket ezután az AI Builder fejezi be.</span><span class="sxs-lookup"><span data-stu-id="50c44-106">The improvement steps are then completed in AI Builder.</span></span>

## <a name="select-historical-outcomes"></a><span data-ttu-id="50c44-107">Előzményalapú eredmény kiválasztása</span><span class="sxs-lookup"><span data-stu-id="50c44-107">Select historical outcomes</span></span>

<span data-ttu-id="50c44-108">Először a számlák három lehetséges kimenetele közül válasszon ki egyet vagy többet: **Időben**, **Későn** és a **Nagyon későn**.</span><span class="sxs-lookup"><span data-stu-id="50c44-108">You first select one or more of the three possible outcomes for invoices: **On time**, **Late**, and **Very late**.</span></span> <span data-ttu-id="50c44-109">Mindhárom eredményt ki kell választani.</span><span class="sxs-lookup"><span data-stu-id="50c44-109">All three outcomes should be selected.</span></span> <span data-ttu-id="50c44-110">Ha törli az eredmények bármelyikének kiválasztását, a számlák ki lesznek szűrve a betanítási folyamatból, és az előrejelzés pontossága csökken.</span><span class="sxs-lookup"><span data-stu-id="50c44-110">If you clear the selection of any of the outcomes, invoices will be filtered out of the training process and the accuracy of the prediction will be reduced.</span></span>

<span data-ttu-id="50c44-111">[![Eredmények megerősítése](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span><span class="sxs-lookup"><span data-stu-id="50c44-111">[![Confirming outcomes](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span></span>

<span data-ttu-id="50c44-112">Ha a szervezet csak két eredményt igényel, módosítsa a **Későn** és a **Nagyon későn** küszöbértékeket 0 (nulla) napra.</span><span class="sxs-lookup"><span data-stu-id="50c44-112">If your organization requires only two outcomes, change the **Late** and **Very late** thresholds to 0 (zero) days.</span></span> <span data-ttu-id="50c44-113">Így hatékonyan összecsukhatja az előrejelzést az **Időben** vagy a **Későn** bináris állapotában.</span><span class="sxs-lookup"><span data-stu-id="50c44-113">In this way, you effectively collapse the prediction to a binary state of **On time** or **Late**.</span></span>

## <a name="select-fields"></a><span data-ttu-id="50c44-114">Mezők kijelölése</span><span class="sxs-lookup"><span data-stu-id="50c44-114">Select fields</span></span>

<span data-ttu-id="50c44-115">Amikor a modellbe felvenni kívánt mezőket választja, vegye figyelembe, hogy a lista tartalmazza a Microsoft Dataverse-tábla összes elérhető mezőjét, amely az Azure Data Lake-ben lévő adatokhoz van rendelve.</span><span class="sxs-lookup"><span data-stu-id="50c44-115">When you're selecting fields to include in the model, be aware that the list includes all available fields in the Microsoft Dataverse table that is mapped to the data in the Azure data lake.</span></span> <span data-ttu-id="50c44-116">A mezők némelyikét **Nem** szabad kijelölni.</span><span class="sxs-lookup"><span data-stu-id="50c44-116">Some of these fields should **not** be selected.</span></span> <span data-ttu-id="50c44-117">A ki nem jelölendő mezők a következő három kategória egyikébe tartoznak:</span><span class="sxs-lookup"><span data-stu-id="50c44-117">The fields that should not be selected fall into one of three categories:</span></span>

- <span data-ttu-id="50c44-118">A mező kitöltése szükséges a Dataverse-táblához, de nincsenek háttéradatok a Data Lake-ben.</span><span class="sxs-lookup"><span data-stu-id="50c44-118">The field is required for the Dataverse table, but there is no backing data for it in the data lake.</span></span>
- <span data-ttu-id="50c44-119">A mező egy azonosító, ezért nincs értelme a gépi tanulási funkciónak.</span><span class="sxs-lookup"><span data-stu-id="50c44-119">The field is an ID and therefore doesn't make sense for a machine learning feature.</span></span>
- <span data-ttu-id="50c44-120">A mező olyan információkat mutat, amelyek nem érhetők el az előrejelzés során.</span><span class="sxs-lookup"><span data-stu-id="50c44-120">The field represents information that won't be available during prediction.</span></span>

<span data-ttu-id="50c44-121">A következő szakaszok a számla és a vevőentitások számára rendelkezésre álló mezőket mutatják be, és felsorolják azokat a mezőket, amelyeket **nem** szabad betanításra kiválasztani.</span><span class="sxs-lookup"><span data-stu-id="50c44-121">The following sections show the fields that are available for the invoice and customer entities, and list the fields that should **not** be selected for training.</span></span> <span data-ttu-id="50c44-122">Az egyes mezőkhöz megadott kategória az előző listában szereplő kategóriákra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="50c44-122">The category that is specified for each of those fields refers to the categories in the preceding list.</span></span>
 
### <a name="invoice-dataverse-table"></a><span data-ttu-id="50c44-123">Dataverse-számlatábla</span><span class="sxs-lookup"><span data-stu-id="50c44-123">Invoice Dataverse table</span></span>

<span data-ttu-id="50c44-124">A következő ábra a számlatáblához rendelkezésre álló mezőket mutatja be.</span><span class="sxs-lookup"><span data-stu-id="50c44-124">The following illustration shows the fields that are available for the invoice table.</span></span>

<span data-ttu-id="50c44-125">[![A számlatábla elérhető mezői](./media/available-fields.png)](./media/available-fields.png)</span><span class="sxs-lookup"><span data-stu-id="50c44-125">[![Available fields for the invoice table](./media/available-fields.png)](./media/available-fields.png)</span></span>

<span data-ttu-id="50c44-126">A következő mezőket nem szabad kiválasztani betanításhoz:</span><span class="sxs-lookup"><span data-stu-id="50c44-126">The following fields should not be selected for training:</span></span>

- <span data-ttu-id="50c44-127">**Számlafiók** (2. kategória)</span><span class="sxs-lookup"><span data-stu-id="50c44-127">**Invoice Account** (category 2)</span></span>
- <span data-ttu-id="50c44-128">**Le van zárva** (3. kategória) – Ez a mező a betanítási (lezárt) és előrejelzési (le nem lezárt) számlák szűrésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="50c44-128">**Is closed** (category 3) – This field is used to filter invoices for training (closed) and prediction (not closed).</span></span>
- <span data-ttu-id="50c44-129">**Név** (1. kategória)</span><span class="sxs-lookup"><span data-stu-id="50c44-129">**Name** (category 1)</span></span>
- <span data-ttu-id="50c44-130">**Erőforrásazonosító** (2. kategória)</span><span class="sxs-lookup"><span data-stu-id="50c44-130">**Source Id** (category 2)</span></span>
- <span data-ttu-id="50c44-131">**Erőforrásrekord** (2. kategória)</span><span class="sxs-lookup"><span data-stu-id="50c44-131">**Source record** (category 2)</span></span>
- <span data-ttu-id="50c44-132">**Forrástábla** (2. kategória)</span><span class="sxs-lookup"><span data-stu-id="50c44-132">**Source table** (category 2)</span></span>

### <a name="customer-dataverse-table"></a><span data-ttu-id="50c44-133">Dataverse vevői tábla</span><span class="sxs-lookup"><span data-stu-id="50c44-133">Customer Dataverse table</span></span>

<span data-ttu-id="50c44-134">A következő ábra a vevőtáblához rendelkezésre álló mezőket mutatja be.</span><span class="sxs-lookup"><span data-stu-id="50c44-134">The following illustration shows the fields that are available for the customer table.</span></span>

<span data-ttu-id="50c44-135">[![A vevőtábla elérhető mezői](./media/related-entities.png)](./media/related-entities.png)</span><span class="sxs-lookup"><span data-stu-id="50c44-135">[![Available fields for the customer table](./media/related-entities.png)](./media/related-entities.png)</span></span>

<span data-ttu-id="50c44-136">A következő mezőt nem szabad kiválasztani betanításhoz:</span><span class="sxs-lookup"><span data-stu-id="50c44-136">The following field should not be selected for training:</span></span>

- <span data-ttu-id="50c44-137">**Sor egyedi kulcsa** (2. kategória)</span><span class="sxs-lookup"><span data-stu-id="50c44-137">**Row Unique Key** (category 2)</span></span>

## <a name="filters"></a><span data-ttu-id="50c44-138">Szűrők</span><span class="sxs-lookup"><span data-stu-id="50c44-138">Filters</span></span>

<span data-ttu-id="50c44-139">A szűrők jelenleg nem támogatják az Ügyfél fizetési előrejelzési forgatókönyvet.</span><span class="sxs-lookup"><span data-stu-id="50c44-139">The filters don't currently support the Customer payment predictor scenario.</span></span> <span data-ttu-id="50c44-140">Ezért válassza a **Lépés kihagyása** lehetőséget, majd menjen az összesítő lapra.</span><span class="sxs-lookup"><span data-stu-id="50c44-140">Therefore, select **Skip this step**, and continue to the summary page.</span></span>

<span data-ttu-id="50c44-141">[![Fókuszmodell szűrőkkel](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span><span class="sxs-lookup"><span data-stu-id="50c44-141">[![Focus model with filters](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
