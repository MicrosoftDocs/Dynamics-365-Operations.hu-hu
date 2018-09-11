--- 
title: "Áfakódok beállítása"
description: "Áfakódok jönnek létre minden közvetett adóhoz vagy járulékhoz, amelyet a vállalat köteles kiszámítani, beszedni és megfizetni az adóhatóság számára."
author: twheeloc
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: f0e078b9c700570b775f91b34a55f2ef490f329a
ms.contentlocale: hu-hu
ms.lasthandoff: 09/11/2018

---
# <a name="set-up-sales-tax-codes"></a><span data-ttu-id="bd5ca-103">Áfakódok beállítása</span><span class="sxs-lookup"><span data-stu-id="bd5ca-103">Set up sales tax codes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bd5ca-104">Áfakódok jönnek létre minden közvetett adóhoz vagy járulékhoz, amelyet a vállalat köteles kiszámítani, beszedni és megfizetni az adóhatóság számára.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-104">Sales tax codes are created for every indirect tax or duty that the legal entity is obligated to calculate, collect, and pay to sales tax authorities.</span></span>

<span data-ttu-id="bd5ca-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-105">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="bd5ca-106">Ugrás az Adó > Közvetett adók > Áfa > Áfakódok pontra.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-106">Go to Tax > Indirect taxes > Sales tax > Sales tax codes.</span></span>
2. <span data-ttu-id="bd5ca-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-107">Click New.</span></span>
3. <span data-ttu-id="bd5ca-108">Az Áfakód kód mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-108">In the Sales tax code field, type a value.</span></span>
4. <span data-ttu-id="bd5ca-109">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-109">In the Name field, type a value.</span></span>
5. <span data-ttu-id="bd5ca-110">Válasszon egy Kiegyenlítési időszakot, és adja meg az adóhatóságot, és hogy milyen időközönként kell ezt a forgalmi adót bevallani és befizetni.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-110">Select a Settlement period to specify which Sales tax authority and in which intervals this sales tax needs to be reported and paid.</span></span>
6. <span data-ttu-id="bd5ca-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-111">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="bd5ca-112">Válassza ki a főkönyvi feladási csoportot a számlák meghatározásához, az áfa főkönyvbe történő feladásához.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-112">Select a Ledger posting group to specify the main accounts to post sales tax to the general ledger.</span></span>
8. <span data-ttu-id="bd5ca-113">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="bd5ca-113">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="bd5ca-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-114">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="bd5ca-115">Bontsa ki a Számítás gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-115">Expand the Calculation FastTab.</span></span>
    * <span data-ttu-id="bd5ca-116">A Számítás gyorslapon több mező szerepel, amelyek megszabják, hogyan történik az áfaösszegek kiszámítása.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-116">The Calculation FastTab has multiple fields that control how sales tax amounts will be calculated.</span></span>  
11. <span data-ttu-id="bd5ca-117">A Művelet panelen kattintson az Áfakód elemre.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-117">On the Action Pane, click Sales tax code.</span></span>
12. <span data-ttu-id="bd5ca-118">Kattintson az Értékekre.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-118">Click Values.</span></span>
13. <span data-ttu-id="bd5ca-119">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-119">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="bd5ca-120">Adja meg az adókód értékét.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-120">Enter the value for this tax code.</span></span>
    * <span data-ttu-id="bd5ca-121">A Számítás gyorslapon az Eredet mezőben ha az Egységárankénti beállítást választja, az érték meg lesz szorozva a tranzakció összegével az áfaösszeg kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-121">On the Calculation FastTab, in the Origin field, if Amount per unit is selected, the value will be multiplied by the quantity on the transaction to calculate the sales tax amount.</span></span>  <span data-ttu-id="bd5ca-122">Ha az áfakód nem egy egységalapú adó, az értéke egy százalék, amelyet az ehhez az áfakódhoz tartozó Eredeti értékre alkalmaz az áfaösszeg kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-122">If the tax code is not a unit based tax, the value is a percentage that is applied on the Origin for this tax code to calculate the sales tax amount.</span></span>     
15. <span data-ttu-id="bd5ca-123">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-123">Click Save.</span></span>
16. <span data-ttu-id="bd5ca-124">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-124">Close the page.</span></span>
17. <span data-ttu-id="bd5ca-125">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="bd5ca-125">Click Save.</span></span>


