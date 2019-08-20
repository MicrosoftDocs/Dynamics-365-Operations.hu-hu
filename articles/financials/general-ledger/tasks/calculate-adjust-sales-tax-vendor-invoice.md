---
title: Szállítói számla áfatartalmának kiszámítása és kiigazítása
description: Ez a témakör bemutatja, hogyan lehet helyesbíteni az áfát egy szállítói számlán a Dynamics 365 for Finance and Operations alkalmazásban.
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
ms.openlocfilehash: 684529087d5348c9e02310f812f8aa6f64c6655f
ms.sourcegitcommit: 016832198c306e8329ad21b5254e7d1cdff74c2f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2019
ms.locfileid: "1862614"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="31417-103">Szállítói számla áfatartalmának kiszámítása és kiigazítása</span><span class="sxs-lookup"><span data-stu-id="31417-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="31417-104">Ez a témakör bemutatja, hogyan lehet helyesbíteni az áfát egy szállítói számlán a Dynamics 365 for Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="31417-104">This topic explains how to adjust sales tax on a vendor invoice in Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="31417-105">Ha az eredeti forrásbizonylat eltérő adóösszegeket jelenít meg számítva, akkor feladás előtt ezeket az összegeket módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="31417-105">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="31417-106">Ez a feladat az DEMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="31417-106">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="31417-107">Anavigációs ablaktáblán válassza a **Modulok > Kötelezettségek > számlák > Számlanapló** elemre.</span><span class="sxs-lookup"><span data-stu-id="31417-107">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice journal**.</span></span>
2. <span data-ttu-id="31417-108">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="31417-108">Select **New**.</span></span>
3. <span data-ttu-id="31417-109">Az új sor **Név** mezőjében válasszon egy lehetőséget a legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="31417-109">In the **Name** field of the new row, select an option in the drop-down menu.</span></span>
4. <span data-ttu-id="31417-110">A Műveleti ablaktáblán válassza a **Sorok** elemet.</span><span class="sxs-lookup"><span data-stu-id="31417-110">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="31417-111">A **Számla** mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="31417-111">In the **Account** field, specify the desired values.</span></span>
6. <span data-ttu-id="31417-112">Írjon be egy értéket a **Számla** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="31417-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="31417-113">A **Hitelkeret** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="31417-113">In the **Credit** field, enter a number.</span></span>
8. <span data-ttu-id="31417-114">Az **Ellenszámla** mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="31417-114">In the **Offset account** field, specify the desired values.</span></span>
9. <span data-ttu-id="31417-115">Válassza az **Áfa** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="31417-115">Select **Sales tax**.</span></span>
10. <span data-ttu-id="31417-116">A **Teljes tényleges áfaösszeg** mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="31417-116">In the **Total actual sales tax amount** field, enter a number.</span></span>
11. <span data-ttu-id="31417-117">A **Helyesbítés** lapon az áfaösszegek az áfakód szerint helyesbíthetők.</span><span class="sxs-lookup"><span data-stu-id="31417-117">On the **Adjustment** tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
12. <span data-ttu-id="31417-118">Válassza a **Tényleges visszaállítása a számított értékekből** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="31417-118">Select **Reset actual from calculated amounts**.</span></span>
13. <span data-ttu-id="31417-119">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="31417-119">Select **OK**.</span></span>
14. <span data-ttu-id="31417-120">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="31417-120">Select **Save**.</span></span>

