---
title: Jelenlegi WIP állapot megtekintése egy termelési rendelésen
description: Ez az eljárás bemutatja, hogyan lehet egy termelési rendelés befejezetlen munkáinak kivonatát megtekinteni.
author: AndersGirke
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, CostAdminWorkspace, CostLastInventoryCloseCard, CostLastBackflushCostingCard, CostStatementCacheCard, CostReleasedProductsMissingCostingDataFormPart, CostCalculationPeriodTopVariancesChartFormPart, ProdTable, CostStatement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e8e55ccfe158146a48fd372d6f0f687d169b7632
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214205"
---
# <a name="view-current-wip-status-on-a-production-order"></a><span data-ttu-id="508df-103">Jelenlegi WIP állapot megtekintése egy termelési rendelésen</span><span class="sxs-lookup"><span data-stu-id="508df-103">View current WIP status on a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="508df-104">Ez az eljárás bemutatja, hogyan lehet egy termelési rendelés befejezetlen munkáinak kivonatát megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="508df-104">This procedure shows how to view WIP statement on a production order.</span></span> <span data-ttu-id="508df-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="508df-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="508df-106">Ezt az eljárást a költségellenőr használja.</span><span class="sxs-lookup"><span data-stu-id="508df-106">This procedure is intended for the cost controller.</span></span>

1. <span data-ttu-id="508df-107">Kattintson a Költségadminisztrációra.</span><span class="sxs-lookup"><span data-stu-id="508df-107">Click Cost administration.</span></span>
2. <span data-ttu-id="508df-108">Kattintson a Termelési rendelések gombra.</span><span class="sxs-lookup"><span data-stu-id="508df-108">Click Production orders.</span></span>
3. <span data-ttu-id="508df-109">A gyorsszűrő használatával keresse meg azokat a rekordokat, ahol a Termelés mezőben a „p000153”' érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="508df-109">Use the Quick Filter to filter on the Production field with a value of 'p000153'.</span></span>
4. <span data-ttu-id="508df-110">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="508df-110">On the Action Pane, click Manage costs.</span></span>
5. <span data-ttu-id="508df-111">Kattintson a Termelés befejezetlen munkáinak kimutatása elemre.</span><span class="sxs-lookup"><span data-stu-id="508df-111">Click Production WIP statement.</span></span>
6. <span data-ttu-id="508df-112">A Kezdő dátum mezőben állítsa „2012-12-01” értékűre a dátumot.</span><span class="sxs-lookup"><span data-stu-id="508df-112">In the From date field, set the date to '2012-12-01'.</span></span>
7. <span data-ttu-id="508df-113">A Befejező dátum mezőben állítsa „2012-12-31” értékűre a dátumot.</span><span class="sxs-lookup"><span data-stu-id="508df-113">In the To date field, set the date to '2012-12-31'.</span></span>

