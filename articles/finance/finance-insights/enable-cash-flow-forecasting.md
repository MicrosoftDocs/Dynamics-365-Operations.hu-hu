---
title: Pénzforgalmi előrejelzés engedélyezése (előzetes verzió)
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Pénzforgalmi előrejelzések funkcióját a pénzügyi elemzésekben.
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
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: ba8acb2191291e2abed5cabf234c19fe09e6c8ff
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222558"
---
# <a name="enable-cash-flow-forecasting-preview"></a><span data-ttu-id="fbeeb-103">Pénzforgalmi előrejelzés engedélyezése (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="fbeeb-103">Enable cash flow forecasting (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="fbeeb-104">Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Pénzforgalmi előrejelzések funkcióját a pénzügyi elemzésekben.</span><span class="sxs-lookup"><span data-stu-id="fbeeb-104">This topic explains how to turn on the Cash flow forecasts feature in Finance Insights.</span></span>

> [!NOTE]
> <span data-ttu-id="fbeeb-105">Ha fizetési előrejelzéseket szeretne használni a pénzforgalomban, be kell állítania a Vevői fizetési előrejelzések funkciót a [Vevői fizetési előrejelzések engedélyezése](enable-cust-paymnt-prediction.md) című részben leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="fbeeb-105">To use payment predictions in the cash flow, you must set up the Customer payment predictions feature as described in [Enable customer payment predictions](enable-cust-paymnt-prediction.md).</span></span>

1. <span data-ttu-id="fbeeb-106">A Microsoft Dynamics Lifecycle Services (LCS) környezet lapjáról származó információk használatával csatlakozhat az Azure SQL elsődleges példányához az adott környezetben.</span><span class="sxs-lookup"><span data-stu-id="fbeeb-106">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="fbeeb-107">Futtassa a következő Transact-SQL (T-SQL) parancsot a tesztkörnyezetben a teszteléshez kiadás bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="fbeeb-107">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="fbeeb-108">(Előfordulhat, hogy az LCS-ben be kell kapcsolnia az IP-cím hez való hozzáférést, mielőtt távolról csatlakozhatna az Application Object Server szolgáltatáshoz \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="fbeeb-108">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="fbeeb-109">Hagyja ki ezt a lépést, ha a 10.0.20-as vagy újabb verziót használja, vagy ha Service Fabric-telepítést használ.</span><span class="sxs-lookup"><span data-stu-id="fbeeb-109">Skip this step if you're using version 10.0.20 or later, or if you're using a Service Fabric deployment.</span></span> <span data-ttu-id="fbeeb-110">A pénzügyi elemzési csoportnak már be kellett kapcsolnia a tesztelés kiadását az Ön számára.</span><span class="sxs-lookup"><span data-stu-id="fbeeb-110">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="fbeeb-111">Ha nem látja a funkciót a **Funkciókezelés** munkaterületen, vagy ha problémákat tapasztal, amikor megpróbálja bekapcsolni, keressen fel minket: <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="fbeeb-111">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>
  
2. <span data-ttu-id="fbeeb-112">Nyissa meg a **Funkciókezelés** munkaterületet, és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="fbeeb-112">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="fbeeb-113">Válassza a **Frissítések keresése** elemet.</span><span class="sxs-lookup"><span data-stu-id="fbeeb-113">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="fbeeb-114">Kapcsolja be a következő szolgáltatásokat:</span><span class="sxs-lookup"><span data-stu-id="fbeeb-114">Turn on the following features:</span></span>

        - <span data-ttu-id="fbeeb-115">Új rácsvezérlő</span><span class="sxs-lookup"><span data-stu-id="fbeeb-115">New grid control</span></span>
        - <span data-ttu-id="fbeeb-116">Csoportosítás rácsokba (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="fbeeb-116">Grouping in grids (preview)</span></span> 
        - <span data-ttu-id="fbeeb-117">Vevői fizetési előrejelzések (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="fbeeb-117">Customer payment predictions (preview)</span></span>
        - <span data-ttu-id="fbeeb-118">Pénzforgalmi előrejelzések (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="fbeeb-118">Cash flow forecasts (preview)</span></span>

3. <span data-ttu-id="fbeeb-119">Nyissa meg a **Készpénz- és bankkezelés \> Pénzforgalom-előrejelzés** lehetőséget, és adja hozzá az előrejelzésekben szerepeltetni kívánt likviditási számlákat.</span><span class="sxs-lookup"><span data-stu-id="fbeeb-119">Go to **Cash and bank management \> Cash flow forecast setup**, and add the liquidity accounts that should be included in the forecasts.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fbeeb-120">Ha a likviditási számlák nincsenek beállítva, a pénzforgalom nem generálható.</span><span class="sxs-lookup"><span data-stu-id="fbeeb-120">If liquidity accounts aren't set up, the cash flow can't be generated.</span></span>

4. <span data-ttu-id="fbeeb-121">Nyissa meg a **Készpénz- és bankkezelés \> Beállítás \> Pénzügyi elemzések (előzetes verzió) \> Pénzforgalmi előrejelzések (előzetes verzió)** című részt, és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="fbeeb-121">Go to **Cash and bank management \> Setup \> Finance Insights (preview) \> Cash flow forecasts (preview)**, and follow these steps:</span></span>

    1. <span data-ttu-id="fbeeb-122">A **Pénzforgalmi előrejelzés** lapon válassza a **Funkció engedélyezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fbeeb-122">On the **Cash flow forecast** tab, select **Enable feature**.</span></span>
    2. <span data-ttu-id="fbeeb-123">Válassza az **Előrejelzési modell létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fbeeb-123">Select **Create prediction model**.</span></span>

<span data-ttu-id="fbeeb-124">A pénzforgalmi előrejelzés képesség beállításával kapcsolatos további tudnivalókat lásd: [Pénzforgalmi előrejelzés](cash-flow-forecast-intro.md).</span><span class="sxs-lookup"><span data-stu-id="fbeeb-124">For more information about the cash flow forecasting capability, see [Cash flow forecasting](cash-flow-forecast-intro.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
