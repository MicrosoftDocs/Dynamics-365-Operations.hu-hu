---
title: "Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor"
description: "Ez a cikk bemutatja, hogyan zárhatja ki a kiugró értékeket az igény-előrejelzés számítására szolgáló előzményadatokból. A kiugró értékek kizárásával, javíthatja az előrejelzés pontosságát."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ea3f08b20e25af6ebb738c2373b65532d74a0c80
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a><span data-ttu-id="bb6a7-104">Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor</span><span class="sxs-lookup"><span data-stu-id="bb6a7-104">Remove outliers from historical transaction data when calculating a demand forecast</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="bb6a7-105">Ez a cikk bemutatja, hogyan zárhatja ki a kiugró értékeket az igény-előrejelzés számítására szolgáló előzményadatokból.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-105">This article describes how to exclude outliers from the historical data that is used to calculate a demand forecast.</span></span> <span data-ttu-id="bb6a7-106">A kiugró értékek kizárásával, javíthatja az előrejelzés pontosságát.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-106">By excluding outliers, you can improve forecast accuracy.</span></span>

<span data-ttu-id="bb6a7-107">A kiugró értékek kizárásával javíthatja az előrejelzés pontosságát.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-107">You can exclude outliers to improve forecast accuracy.</span></span> <span data-ttu-id="bb6a7-108">Ez a feladat nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-108">This is an optional task.</span></span> <span data-ttu-id="bb6a7-109">Itt következik egy áttekintés a folyamatról:</span><span class="sxs-lookup"><span data-stu-id="bb6a7-109">Here is an overview of the process:</span></span>

1.  <span data-ttu-id="bb6a7-110">Kattintson az **Alaptervezés** &gt; **Beállítások** &gt; **Igény-előrejelzés** &gt; **Kívülálló tételek eltávolítása** elemekre, hogy megnyissa a **Kívülálló tételek eltávolítása** lapot, ahol egy lekérdezés használatával kiválaszthatja a kizárandó tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-110">Click **Master planning** &gt; **Setup** &gt; **Demand forecasting** &gt; **Outlier removal** to open the **Outlier removal** page, where you can use a query to select the transactions to exclude.</span></span>
2.  <span data-ttu-id="bb6a7-111">Válassza ki a vállalatot, amelyre a lekérdezés vonatkozik, majd adjon meg egy nevet és leírást.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-111">Select the company that the query applies to, and then enter a name and description.</span></span> <span data-ttu-id="bb6a7-112">A **Dátum lekérdezés** mező értéke automatikusan az aktuális dátum.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-112">The **Query date** field is automatically set to the current date.</span></span>
3.  <span data-ttu-id="bb6a7-113">Válasza ki az **Aktív** jelölőnégyzetet, hogy kizárja azokat a tranzakciókat, amiket a lekérdezés az előzményinformációkban talál.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-113">Select the **Active** check box to exclude the transactions that the query finds from the historical data.</span></span> <span data-ttu-id="bb6a7-114">Ez a beállítás a kiinduló előrejelzés létrehozásakor lép érvénybe.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-114">This setting will take effect when you create a baseline forecast.</span></span>
4.  <span data-ttu-id="bb6a7-115">Az **Lekérdezés kívülálló tételek eltávolításához** képernyőn hozzáadhat, eltávolíthat és kiválaszthat egyes feltételeket, amelyek meghatározzák a kiinduló előrejelzésből kizárandó tranzakciók körét.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-115">On the **Outlier removal query** page, you can add, remove, and select the criteria that define which transactions will be excluded when the baseline forecast is calculated.</span></span> <span data-ttu-id="bb6a7-116">A kiválasztással kizárhat például egy adott cikket vagy rendelési tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-116">For example, select a specific item or order transaction to exclude.</span></span>
5.  <span data-ttu-id="bb6a7-117">Kattintson a **Tranzakciók megjelenítése** elemre.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-117">Click **Display transactions**.</span></span> <span data-ttu-id="bb6a7-118">Az **Kívülálló tranzakciók** lap felsorolja azokat a tranzakciókat, amelyek a lekérdezésben meghatározott feltételeknek megfelelnek, és ezért nem tartoznak bele az igény-előrejelzés számításakor használt előzményadatokba.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-118">The **Outlier transactions** page lists the transactions that meet the criteria that you defined in the query, and that will be excluded from the historical data when the demand forecast is calculated.</span></span>

<span data-ttu-id="bb6a7-119">**Megjegyzés:** Létrehozhat egy lekérdezést, amely egy meglévő lekérdezésen alapul.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-119">**Note:** You can also create a query that is based on an existing query.</span></span> <span data-ttu-id="bb6a7-120">Válassza ki azt a változót, amelyből másolni szeretne, és kattintson a **Másolás** elemre.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-120">Select the query to copy, and then click **Duplicate**.</span></span> <span data-ttu-id="bb6a7-121">A **Lekérdezés dátuma** mező azonosítja a verziót.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-121">The **Query date** field identifies the version.</span></span> <span data-ttu-id="bb6a7-122">Használhatja a lekérdezést úgy, ahogy van vagy rákattinthat a **Lekérdezés szerkesztése** gombra, hogy módosítsa a feltételeket.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-122">You can use the query as it is, or you can click **Edit query** to modify the criteria.</span></span> <span data-ttu-id="bb6a7-123">Az új lekérdezés neve és leírása tetszés szerint módosítható.</span><span class="sxs-lookup"><span data-stu-id="bb6a7-123">You can optionally modify the name and description of the new query.</span></span>

<a name="see-also"></a><span data-ttu-id="bb6a7-124">Lásd még</span><span class="sxs-lookup"><span data-stu-id="bb6a7-124">See also</span></span>
--------

[<span data-ttu-id="bb6a7-125">Igény-előrejelzés – bevezetés</span><span class="sxs-lookup"><span data-stu-id="bb6a7-125">Introduction to demand forecasting</span></span>](introduction-demand-forecasting.md)

[<span data-ttu-id="bb6a7-126">Az előrejelzés pontosság megfigyelése</span><span class="sxs-lookup"><span data-stu-id="bb6a7-126">Monitoring forecast accuracy</span></span>](monitor-forecast-accuracy.md)




