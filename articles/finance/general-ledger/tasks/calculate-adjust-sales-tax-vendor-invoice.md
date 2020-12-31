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
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 03313d875d23489b3293376dd94f808c73a4bd15
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443805"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="01cb3-103">Szállítói számla áfatartalmának kiszámítása és kiigazítása</span><span class="sxs-lookup"><span data-stu-id="01cb3-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="01cb3-104">Ez a témakör bemutatja, hogyan lehet helyesbíteni az áfát egy szállítói számlán.</span><span class="sxs-lookup"><span data-stu-id="01cb3-104">This topic explains how to adjust sales tax on a vendor invoice.</span></span> <span data-ttu-id="01cb3-105">Ha az eredeti forrásbizonylat eltérő adóösszegeket jelenít meg számítva, akkor feladás előtt ezeket az összegeket módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="01cb3-105">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="01cb3-106">Ez a feladat az DEMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="01cb3-106">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="01cb3-107">Anavigációs ablaktáblán válassza a **Modulok > Kötelezettségek > számlák > Számlanapló** elemre.</span><span class="sxs-lookup"><span data-stu-id="01cb3-107">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice journal**.</span></span>
2. <span data-ttu-id="01cb3-108">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01cb3-108">Select **New**.</span></span>
3. <span data-ttu-id="01cb3-109">Az új sor **Név** mezőjében válasszon egy lehetőséget a legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="01cb3-109">In the **Name** field of the new row, select an option in the drop-down menu.</span></span>
4. <span data-ttu-id="01cb3-110">A Műveleti ablaktáblán válassza a **Sorok** elemet.</span><span class="sxs-lookup"><span data-stu-id="01cb3-110">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="01cb3-111">A **Számla** mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="01cb3-111">In the **Account** field, specify the desired values.</span></span>
6. <span data-ttu-id="01cb3-112">Írjon be egy értéket a **Számla** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="01cb3-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="01cb3-113">A **Hitelkeret** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="01cb3-113">In the **Credit** field, enter a number.</span></span>
8. <span data-ttu-id="01cb3-114">Az **Ellenszámla** mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="01cb3-114">In the **Offset account** field, specify the desired values.</span></span>
9. <span data-ttu-id="01cb3-115">Válassza az **Áfa** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01cb3-115">Select **Sales tax**.</span></span>
10. <span data-ttu-id="01cb3-116">A **Teljes tényleges áfaösszeg** mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="01cb3-116">In the **Total actual sales tax amount** field, enter a number.</span></span>
11. <span data-ttu-id="01cb3-117">A **Helyesbítés** lapon az áfaösszegek az áfakód szerint helyesbíthetők.</span><span class="sxs-lookup"><span data-stu-id="01cb3-117">On the **Adjustment** tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
12. <span data-ttu-id="01cb3-118">Válassza a **Tényleges visszaállítása a számított értékekből** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01cb3-118">Select **Reset actual from calculated amounts**.</span></span>
13. <span data-ttu-id="01cb3-119">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01cb3-119">Select **OK**.</span></span>
14. <span data-ttu-id="01cb3-120">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01cb3-120">Select **Save**.</span></span>

