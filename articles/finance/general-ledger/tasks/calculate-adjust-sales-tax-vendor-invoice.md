---
title: Szállítói számla áfatartalmának kiszámítása és kiigazítása
description: Ez a témakör bemutatja, hogyan lehet helyesbíteni az áfát egy szállítói számlán a Dynamics 365 Finance alkalmazásban.
author: twheeloc
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2f3521f7bc56659fc6f7a6d47f581ddbfea16523
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139967"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="95683-103">Szállítói számla áfatartalmának kiszámítása és kiigazítása</span><span class="sxs-lookup"><span data-stu-id="95683-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="95683-104">Ez a témakör bemutatja, hogyan lehet helyesbíteni az áfát egy szállítói számlán.</span><span class="sxs-lookup"><span data-stu-id="95683-104">This topic explains how to adjust sales tax on a vendor invoice.</span></span> <span data-ttu-id="95683-105">Ha az eredeti forrásbizonylat eltérő adóösszegeket jelenít meg számítva, akkor feladás előtt ezeket az összegeket módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="95683-105">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="95683-106">Ez a feladat az DEMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="95683-106">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="95683-107">Anavigációs ablaktáblán válassza a **Modulok > Kötelezettségek > számlák > Számlanapló** elemre.</span><span class="sxs-lookup"><span data-stu-id="95683-107">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice journal**.</span></span>
2. <span data-ttu-id="95683-108">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95683-108">Select **New**.</span></span>
3. <span data-ttu-id="95683-109">Az új sor **Név** mezőjében válasszon egy lehetőséget a legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="95683-109">In the **Name** field of the new row, select an option in the drop-down menu.</span></span>
4. <span data-ttu-id="95683-110">A Műveleti ablaktáblán válassza a **Sorok** elemet.</span><span class="sxs-lookup"><span data-stu-id="95683-110">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="95683-111">A **Számla** mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="95683-111">In the **Account** field, specify the desired values.</span></span>
6. <span data-ttu-id="95683-112">Írjon be egy értéket a **Számla** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="95683-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="95683-113">A **Hitelkeret** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="95683-113">In the **Credit** field, enter a number.</span></span>
8. <span data-ttu-id="95683-114">Az **Ellenszámla** mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="95683-114">In the **Offset account** field, specify the desired values.</span></span>
9. <span data-ttu-id="95683-115">Válassza az **Áfa** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95683-115">Select **Sales tax**.</span></span>
10. <span data-ttu-id="95683-116">A **Teljes tényleges áfaösszeg** mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="95683-116">In the **Total actual sales tax amount** field, enter a number.</span></span>
11. <span data-ttu-id="95683-117">A **Helyesbítés** lapon az áfaösszegek az áfakód szerint helyesbíthetők.</span><span class="sxs-lookup"><span data-stu-id="95683-117">On the **Adjustment** tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
12. <span data-ttu-id="95683-118">Válassza a **Tényleges visszaállítása a számított értékekből** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95683-118">Select **Reset actual from calculated amounts**.</span></span>
13. <span data-ttu-id="95683-119">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95683-119">Select **OK**.</span></span>
14. <span data-ttu-id="95683-120">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95683-120">Select **Save**.</span></span>

