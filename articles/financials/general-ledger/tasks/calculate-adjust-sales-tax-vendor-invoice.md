---
title: Szállítói számla forgalmi adójának kiszámítása és kiigazítása
description: Ha az eredeti forrásbizonylat eltérő adóösszegeket jelenít meg számítva, akkor feladás előtt ezeket az összegeket módosíthatja.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 803c038d907b68a3c72a83a3e035c4e08b8a8661
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545171"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="4f6df-103">Szállítói számla forgalmi adójának kiszámítása és kiigazítása</span><span class="sxs-lookup"><span data-stu-id="4f6df-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4f6df-104">Ha az eredeti forrásbizonylat eltérő adóösszegeket jelenít meg számítva, akkor feladás előtt ezeket az összegeket módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="4f6df-104">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="4f6df-105">Ez a feladat az DEMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="4f6df-105">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="4f6df-106">Ugorjon a Kötelezettségek > Számlák > Számlanapló pontra.</span><span class="sxs-lookup"><span data-stu-id="4f6df-106">Go to Accounts payable > Invoices > Invoice journal.</span></span>
2. <span data-ttu-id="4f6df-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4f6df-107">Click New.</span></span>
3. <span data-ttu-id="4f6df-108">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="4f6df-108">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="4f6df-109">A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4f6df-109">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="4f6df-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4f6df-110">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="4f6df-111">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="4f6df-111">Click Lines.</span></span>
7. <span data-ttu-id="4f6df-112">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="4f6df-112">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="4f6df-113">A Számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="4f6df-113">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="4f6df-114">Érték beírása a Számla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4f6df-114">In the Invoice field, type a value.</span></span>
10. <span data-ttu-id="4f6df-115">A Hitelkeret mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="4f6df-115">In the Credit field, enter a number.</span></span>
11. <span data-ttu-id="4f6df-116">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="4f6df-116">In the Offset account field, specify the desired values.</span></span>
12. <span data-ttu-id="4f6df-117">Kattintson az Áfa elemre.</span><span class="sxs-lookup"><span data-stu-id="4f6df-117">Click Sales tax.</span></span>
13. <span data-ttu-id="4f6df-118">A Teljes tényleges áfaösszeg mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="4f6df-118">In the Total actual sales tax amount field, enter a number.</span></span>
14. <span data-ttu-id="4f6df-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4f6df-119">Click OK.</span></span>
15. <span data-ttu-id="4f6df-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4f6df-120">Click Save.</span></span>
16. <span data-ttu-id="4f6df-121">Kattintson az Áfa elemre.</span><span class="sxs-lookup"><span data-stu-id="4f6df-121">Click Sales tax.</span></span>
17. <span data-ttu-id="4f6df-122">A Módosítás lapon az áfaösszegek az áfakód szerint helyesbíthetők.</span><span class="sxs-lookup"><span data-stu-id="4f6df-122">On the Adjustment tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
18. <span data-ttu-id="4f6df-123">Kattintson a Tényleges visszaállítása a számított értékekből pontra.</span><span class="sxs-lookup"><span data-stu-id="4f6df-123">Click Reset actual from calculated amounts.</span></span>
19. <span data-ttu-id="4f6df-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4f6df-124">Click OK.</span></span>
20. <span data-ttu-id="4f6df-125">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4f6df-125">Click Save.</span></span>

