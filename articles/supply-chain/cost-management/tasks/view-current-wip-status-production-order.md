---
title: Jelenlegi WIP állapot megtekintése egy termelési rendelésen
description: Ez az eljárás bemutatja, hogyan lehet egy termelési rendelés befejezetlen munkáinak kivonatát megtekinteni.
author: AndersGirke
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, CostAdminWorkspace, CostLastInventoryCloseCard, CostLastBackflushCostingCard, CostStatementCacheCard, CostReleasedProductsMissingCostingDataFormPart, CostCalculationPeriodTopVariancesChartFormPart, ProdTable, CostStatement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: be5d3c19cc0542c0bf11674e70706e3c5c624d60
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150467"
---
# <a name="view-current-wip-status-on-a-production-order"></a><span data-ttu-id="0082b-103">Jelenlegi WIP állapot megtekintése egy termelési rendelésen</span><span class="sxs-lookup"><span data-stu-id="0082b-103">View current WIP status on a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0082b-104">Ez az eljárás bemutatja, hogyan lehet egy termelési rendelés befejezetlen munkáinak kivonatát megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="0082b-104">This procedure shows how to view WIP statement on a production order.</span></span> <span data-ttu-id="0082b-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="0082b-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0082b-106">Ezt az eljárást a költségellenőr használja.</span><span class="sxs-lookup"><span data-stu-id="0082b-106">This procedure is intended for the cost controller.</span></span>

1. <span data-ttu-id="0082b-107">Kattintson a Költségadminisztrációra.</span><span class="sxs-lookup"><span data-stu-id="0082b-107">Click Cost administration.</span></span>
2. <span data-ttu-id="0082b-108">Kattintson a Termelési rendelések gombra.</span><span class="sxs-lookup"><span data-stu-id="0082b-108">Click Production orders.</span></span>
3. <span data-ttu-id="0082b-109">A gyorsszűrő használatával keresse meg azokat a rekordokat, ahol a Termelés mezőben a „p000153”' érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="0082b-109">Use the Quick Filter to filter on the Production field with a value of 'p000153'.</span></span>
4. <span data-ttu-id="0082b-110">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="0082b-110">On the Action Pane, click Manage costs.</span></span>
5. <span data-ttu-id="0082b-111">Kattintson a Termelés befejezetlen munkáinak kimutatása elemre.</span><span class="sxs-lookup"><span data-stu-id="0082b-111">Click Production WIP statement.</span></span>
6. <span data-ttu-id="0082b-112">A Kezdő dátum mezőben állítsa „2012-12-01” értékűre a dátumot.</span><span class="sxs-lookup"><span data-stu-id="0082b-112">In the From date field, set the date to '2012-12-01'.</span></span>
7. <span data-ttu-id="0082b-113">A Befejező dátum mezőben állítsa „2012-12-31” értékűre a dátumot.</span><span class="sxs-lookup"><span data-stu-id="0082b-113">In the To date field, set the date to '2012-12-31'.</span></span>

