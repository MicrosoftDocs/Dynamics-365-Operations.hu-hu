---
title: Pénzforgalmi előrejelzés (előzetes verzió)
description: Ez a témakör a Pénzforgalmi előrejelzési képességet mutatja be.
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
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 64935db3b50e7598f2076ecbec72aba020d4f908
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186540"
---
# <a name="cash-flow-forecast-preview"></a><span data-ttu-id="fdf5f-103">Pénzforgalmi előrejelzés (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="fdf5f-103">Cash flow forecast (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="fdf5f-104">A pénzforgalom kritikus fontosságú minden üzleti tevékenységhez.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-104">Cash flow is critical to any business.</span></span> <span data-ttu-id="fdf5f-105">Még a nyereséges vállalatok is szembesülnek a fizetésképtelenséggel, ha nem tartják fenn a pénzforgalmat, amivel meg tudnak felelni az azonnali igényeknek.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-105">Even profitable companies can face insolvency if they don't maintain the cash flow to meet immediate needs.</span></span> <span data-ttu-id="fdf5f-106">A pénzforgalmi előrejelzések pénzforgalmi előrejelzési képessége segít a vállalatoknak a pénzforgalmi egyenleg hatékony nyomon követésében és kezelésében.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-106">The cash flow forecasting capability in Finance insights can help companies monitor and manage their cash balances effectively.</span></span> <span data-ttu-id="fdf5f-107">Ez a funkció a gépi tanulást használja a vállalatok számára, hogy a korábbinál pontosabban előrejelzést nyújtson a pénzforgalomhoz.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-107">This feature uses machine learning to help businesses forecast cash flows more accurately than they have previously.</span></span> <span data-ttu-id="fdf5f-108">Ezenkívül segítséget nyújt a menedzsereknek a lehetőségek optimalizálása érdekében, hogy az aktuális készpénzpozíció kontextusában optimalizálják a lehetőségeket.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-108">It can also help managers make decisions that optimize opportunities in the context of their current cash position.</span></span> 

<span data-ttu-id="fdf5f-109">A legtöbb vállalatnál a pénzforgalom kezelése és a pénzforgalmi előrejelzések futtatása unalmas, ismétlődő és manuális művelet.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-109">For most companies, managing cash flow and running cash flow forecasting is a tedious, repetitive, and manual process.</span></span> <span data-ttu-id="fdf5f-110">A legtöbb vállalat a különböző komplexitású Microsoft Excel-megoldásokra támaszkodik.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-110">Most companies rely on Microsoft Excel solutions that have varying degrees of complexity.</span></span> <span data-ttu-id="fdf5f-111">A pénzforgalom pontos előrejelzésének kihívásai a következők:</span><span class="sxs-lookup"><span data-stu-id="fdf5f-111">The challenges of accurately forecasting cash flow include the following:</span></span>

- <span data-ttu-id="fdf5f-112">Az adatok nem érhetők el a döntéshozók számára, mert több helyen elszórtan találhatók, többek között a következők:</span><span class="sxs-lookup"><span data-stu-id="fdf5f-112">Data isn't available to decision makers because it's scattered in multiple places, including:</span></span> 
  - <span data-ttu-id="fdf5f-113">A könyvelés vagy a vállalati erőforrástervezési rendszer</span><span class="sxs-lookup"><span data-stu-id="fdf5f-113">The accounting or enterprise resource planning system</span></span>
  - <span data-ttu-id="fdf5f-114">Pénzügyi tervezési szoftver</span><span class="sxs-lookup"><span data-stu-id="fdf5f-114">Financial planning software</span></span>
  - <span data-ttu-id="fdf5f-115">Excel</span><span class="sxs-lookup"><span data-stu-id="fdf5f-115">Excel</span></span>
  - <span data-ttu-id="fdf5f-116">További szoftveralkalmazások</span><span class="sxs-lookup"><span data-stu-id="fdf5f-116">Additional software applications</span></span> 
- <span data-ttu-id="fdf5f-117">Az előrejelzés alapja a belső tudás, amely az egyes tartományokon vagy osztályokon belül a „silókban” található.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-117">Forecasting is based on internal knowledge that resides in "silos" within each domain or department.</span></span>
- <span data-ttu-id="fdf5f-118">A Pénzforgalmi előrejelzés pontosságának mérése a pénzeszközök felfrissítését követően bizonytalan és nehézkes.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-118">Measuring the accuracy of cash flow forecasting after the financials have been realized is uncertain and difficult.</span></span>
    
## <a name="details-of-the-cash-flow-forecasts-capability"></a><span data-ttu-id="fdf5f-119">A pénzforgalmi előrejelzések funkcióval kapcsolatos részletek</span><span class="sxs-lookup"><span data-stu-id="fdf5f-119">Details of the Cash flow forecasts capability</span></span>
<span data-ttu-id="fdf5f-120">A Pénzforgalmi előrejelzések funkció a következő lehetőségeket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-120">The Cash flow forecasts feature includes the following functionality.</span></span> 

- <span data-ttu-id="fdf5f-121">Segítségével egyszerű a pénzforgalmi adatok külső rendszerekből Dynamics 365 Finance-be történő integrálása.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-121">Makes it easy to integrate cash flow data from external systems to Dynamics 365 Finance.</span></span> <span data-ttu-id="fdf5f-122">A pénzforgalmi előrejelzések az adatimport, -export keretrendszer használatára is használhatók.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-122">Cash flow forecasts can also use the data import-export framework.</span></span> <span data-ttu-id="fdf5f-123">Ez a keretrendszer megkönnyíti az Excel OData-val történő integrációt.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-123">This framework makes it easy to integrate with Excel OData.</span></span> <span data-ttu-id="fdf5f-124">Egy átfogó pénzforgalmi megoldást több forrásból származó adatok egyesítésével is lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-124">You can also combine data from multiple sources to create a comprehensive cash flow solution.</span></span> 

- <span data-ttu-id="fdf5f-125">Intelligens készpénzpozíciót vezet be.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-125">Introduces intelligent cash position.</span></span> <span data-ttu-id="fdf5f-126">A készpénzpozíció létrehozása a vevői fizetési mód alapján történik, amely azt jelzi, hogy a vállalat mikorra várhatja a számlájára a bejövő összeget.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-126">Cash position is created  based on customer’s payment behavior to predict when a company can expect cash to arrive in their accounts.</span></span> <span data-ttu-id="fdf5f-127">A fizető szállítók múltbeli feladatainak elemzésével azt is megjósolhatja, hogy a jövőbeli számlákat és rendeléseket valószínűleg mikor fizetik ki.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-127">It also analyzes the historical patterns of paying vendors, to predict when future invoices and orders are likely to be paid.</span></span> 

- <span data-ttu-id="fdf5f-128">Bemutatja az intelligens pénzforgalmi előrejelzést a hosszú távú előrejelzésekhez, az idősor előrejelzést használva az AI Builder automatizált integrációján keresztül.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-128">Introduces intelligent cash flow forecasting for long-term forecasting, using time series forecasting through automated integration with AI Builder.</span></span>

- <span data-ttu-id="fdf5f-129">Lehetőséget nyújt bizonyos pénzforgalmi helyzetek vagy előrejelzések mentésére, szerkesztésére, majd az előrejelzési teljesítmény tényleges pénzügyekkel való egyszerű összehasonlítására és mérésére.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-129">Provides the ability to save specific cash flow position or forecasts, edit them, and then easily compare and measure the forecast performance to the actual financials.</span></span>

- <span data-ttu-id="fdf5f-130">A mi lenne, ha elemzést engedélyezi a pillanatkép összehasonlításon keresztül.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-130">Enables what-if analysis through snapshot comparison.</span></span> <span data-ttu-id="fdf5f-131">Létrehozhat például több pillanatképet, amely optimista, pesszimista vagy a pénzforgalom leginkább valósághű nézeteit jeleníti meg, majd összevetheti és megtekintheti a különbségeket.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-131">For example, you can create multiple snapshots that represent optimistic, pessimistic, and the most realistic views of your cash flow, and then compare and view the differences.</span></span>

- <span data-ttu-id="fdf5f-132">Lehetőséget nyújt a pénzforgalmi előrejelzések több pénznemben történő megtekintésére jogi személyek között, valamint a bankszámlához kapcsolódó pénzforgalom szűrésére és megtekintésére.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-132">Provides the ability to view the cash flow forecast in multiple currencies, across legal entities, and filter and view cash flow related to a bank account.</span></span> 

- <span data-ttu-id="fdf5f-133">A pénzügyi dimenziókkal kapcsolatos bankszámlák szűrését és megjelenítését teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-133">Lets you filter and view bank accounts that are related to financial dimensions.</span></span>

<span data-ttu-id="fdf5f-134">A pénzforgalom-előrejelzési funkció segíti a szervezetet, hogy az unalmas, összetett, mégis ismétlődő pénzforgalmi előrejelzést egyszerű, automatizált folyamatra alakítsa át a Dynamics 365 Finance-ben.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-134">The cash flow forecasting functionality in Dynamics 365 Finance will empower your organization to transform tedious, complex, yet repetitive cash flow projection to a simple, automated process.</span></span> <span data-ttu-id="fdf5f-135">A pénzforgalmi előrejelzések leginkább unalmas aspektusainak automatizálása lehetővé teszi a kritikus döntések meghozatalát a kívánt üzleti eredmények eléréséhez.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-135">Automating the most tedious aspects of cash flow forecasting lets you focus on critical decision making to drive desired business outcomes.</span></span>

## <a name="setting-up-dimensions-for-cash-flow-forecasting"></a><span data-ttu-id="fdf5f-136">A Pénzforgalmi előrejelzés dimenzióinak beállítása</span><span class="sxs-lookup"><span data-stu-id="fdf5f-136">Setting up Dimensions for Cash flow forecasting</span></span>
<span data-ttu-id="fdf5f-137">A **Pénzforgalmi előrejelzés beállítása** lap egy új lapján beállíthatja, hogy milyen pénzügyi dimenziókat kell használni a **Pénzforgalmi előrejelzés** munkaterületen végzett szűréshez.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-137">A new tab on the **Cash flow forecasting setup** page lets you control what financial dimensions to use for filtering in the **Cash flow forecasting** workspace.</span></span> <span data-ttu-id="fdf5f-138">Ez a lap csak akkor jelenik meg, ha engedélyezve van a Pénzforgalmi előrejelzések funkció.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-138">This tab will only appear when the Cash flow forecasts feature is enabled.</span></span> 

<span data-ttu-id="fdf5f-139">A **Dimenziók** fülön válassza ki a szűréshez használni kívánt dimenziók listáját, és a nyilakkal helyezze át őket a jobb oldali oszlopba.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-139">On the **Dimensions** tab, choose from the list of dimensions to use for filtering, and use the arrow keys to move them to the right-hand column.</span></span> <span data-ttu-id="fdf5f-140">A pénzforgalmi előrejelzések adatainak szűréséhez csak két dimenzió választható ki.</span><span class="sxs-lookup"><span data-stu-id="fdf5f-140">Only two dimensions can be selected for filtering cash flow forecast data.</span></span> 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
