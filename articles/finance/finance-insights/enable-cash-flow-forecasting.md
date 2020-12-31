---
title: Pénzforgalmi előrejelzés engedélyezése (előzetes verzió)
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Pénzforgalmi előrejelzések funkcióját a pénzügyi elemzésekben.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 321c716c10b136769ea3a48a3b60a8a717798338
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646229"
---
# <a name="enable-cash-flow-forecasting-preview"></a><span data-ttu-id="5795c-103">Pénzforgalmi előrejelzés engedélyezése (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="5795c-103">Enable cash flow forecasting (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="5795c-104">Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Pénzforgalmi előrejelzések funkcióját a pénzügyi elemzésekben.</span><span class="sxs-lookup"><span data-stu-id="5795c-104">This topic explains how to turn on the Cash flow forecasts feature in Finance Insights.</span></span>

> [!NOTE]
> <span data-ttu-id="5795c-105">Ha fizetési előrejelzéseket szeretne használni a pénzforgalomban, be kell állítania a Vevői fizetési előrejelzések funkciót a [Vevői fizetési előrejelzések engedélyezése](enable-cust-paymnt-prediction.md) című részben leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="5795c-105">To use payment predictions in the cash flow, you must set up the Customer payment predictions feature as described in [Enable customer payment predictions](enable-cust-paymnt-prediction.md).</span></span>

1. <span data-ttu-id="5795c-106">A Microsoft Dynamics Lifecycle Services (LCS) környezet lapjáról származó információk használatával csatlakozhat az Azure SQL elsődleges példányához az adott környezetben.</span><span class="sxs-lookup"><span data-stu-id="5795c-106">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="5795c-107">Futtassa a következő Transact-SQL (T-SQL) parancsot a tesztkörnyezetben a teszteléshez kiadás bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="5795c-107">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="5795c-108">(Előfordulhat, hogy az LCS-ben be kell kapcsolnia az IP-cím hez való hozzáférést, mielőtt távolról csatlakozhatna az Application Object Server szolgáltatáshoz \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="5795c-108">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="5795c-109">Ha a Microsoft Dynamics 365 Finance központi telepítése egy Service Fabric üzemelő példány, kihagyhatja ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="5795c-109">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="5795c-110">A pénzügyi elemzési csoportnak már be kellett kapcsolnia a tesztelés kiadását az Ön számára.</span><span class="sxs-lookup"><span data-stu-id="5795c-110">The Finance Insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="5795c-111">Ha nem látja a funkciókat a **Funkciókezelés** munkaterületen, vagy ha problémákat tapasztal, amikor megpróbálja bekapcsolni őket, keressen fel minket: <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="5795c-111">If you don't see the features in the **Feature management** workspace, or if experience issues when you try to turn them on, contact <fiap@microsoft.com>.</span></span>
  
2. <span data-ttu-id="5795c-112">Nyissa meg a **Funkciókezelés** munkaterületet, és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="5795c-112">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="5795c-113">Válassza a **Frissítések keresése** elemet.</span><span class="sxs-lookup"><span data-stu-id="5795c-113">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="5795c-114">Kapcsolja be a következő szolgáltatásokat:</span><span class="sxs-lookup"><span data-stu-id="5795c-114">Turn on the following features:</span></span>

        - <span data-ttu-id="5795c-115">Új rácsvezérlő</span><span class="sxs-lookup"><span data-stu-id="5795c-115">New grid control</span></span>
        - <span data-ttu-id="5795c-116">Csoportosítás rácsokba (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="5795c-116">Grouping in grids (preview)</span></span> 
        - <span data-ttu-id="5795c-117">Vevői fizetési előrejelzések (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="5795c-117">Customer payment predictions (preview)</span></span>
        - <span data-ttu-id="5795c-118">Pénzforgalmi előrejelzések (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="5795c-118">Cash flow forecasts (preview)</span></span>

3. <span data-ttu-id="5795c-119">Nyissa meg a **Készpénz- és bankkezelés \> Pénzforgalom-előrejelzés** lehetőséget, és adja hozzá az előrejelzésekben szerepeltetni kívánt likviditási számlákat.</span><span class="sxs-lookup"><span data-stu-id="5795c-119">Go to **Cash and bank management \> Cash flow forecast setup**, and add the liquidity accounts that should be included in the forecasts.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5795c-120">Ha a likviditási számlák nincsenek beállítva, a pénzforgalom nem generálható.</span><span class="sxs-lookup"><span data-stu-id="5795c-120">If liquidity accounts aren't set up, the cash flow can't be generated.</span></span>

4. <span data-ttu-id="5795c-121">Nyissa meg a **Készpénz- és bankkezelés \> Beállítás \> Pénzügyi elemzések (előzetes verzió) \> Pénzforgalmi előrejelzések (előzetes verzió)** című részt, és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="5795c-121">Go to **Cash and bank management \> Setup \> Finance Insights (preview) \> Cash flow forecasts (preview)**, and follow these steps:</span></span>

    1. <span data-ttu-id="5795c-122">A **Pénzforgalmi előrejelzés** lapon válassza a **Funkció engedélyezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5795c-122">On the **Cash flow forecast** tab, select **Enable feature**.</span></span>
    2. <span data-ttu-id="5795c-123">Válassza az **Előrejelzési modell létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5795c-123">Select **Create prediction model**.</span></span>

<span data-ttu-id="5795c-124">A pénzforgalmi előrejelzés képesség beállításával kapcsolatos további tudnivalókat lásd: [Pénzforgalmi előrejelzés](cash-flow-forecast-intro.md).</span><span class="sxs-lookup"><span data-stu-id="5795c-124">For more information about the cash flow forecasting capability, see [Cash flow forecasting](cash-flow-forecast-intro.md).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="5795c-125">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="5795c-125">Privacy notice</span></span>

<span data-ttu-id="5795c-126">Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmazhatnak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés (SLA) ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.</span><span class="sxs-lookup"><span data-stu-id="5795c-126">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
