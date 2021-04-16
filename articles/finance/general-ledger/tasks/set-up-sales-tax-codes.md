---
title: Áfakódok beállítása
description: Ez a témakör bemutatja, hogyan állítsuk be az áfát a Dynamics 365 Finance szolgáltatásban.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6c7208fa65905fcc902d9c08b5b90178745e76d4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815044"
---
# <a name="set-up-sales-tax-codes"></a><span data-ttu-id="705c5-103">Áfakódok beállítása</span><span class="sxs-lookup"><span data-stu-id="705c5-103">Set up sales tax codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="705c5-104">Ez a témakör bemutatja, hogyan állítsuk be az áfakódokat.</span><span class="sxs-lookup"><span data-stu-id="705c5-104">This topic explains how to set up sales tax codes.</span></span> <span data-ttu-id="705c5-105">Áfakódok jönnek létre minden közvetett adóhoz vagy járulékhoz, amelyet a vállalat köteles kiszámítani, beszedni és megfizetni az adóhatóság számára.</span><span class="sxs-lookup"><span data-stu-id="705c5-105">Sales tax codes are created for every indirect tax or duty that the legal entity is obligated to calculate, collect, and pay to sales tax authorities.</span></span>

<span data-ttu-id="705c5-106">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="705c5-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="705c5-107">Ugorjon a **Navigációs ablaktábla > Adók > Közvetett adók > Áfa > Áfakódok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="705c5-107">Go to **Navigation pane > Tax > Indirect taxes > Sales tax > Sales tax codes**.</span></span>
2. <span data-ttu-id="705c5-108">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="705c5-108">Select **New**.</span></span>
3. <span data-ttu-id="705c5-109">Adjon meg egy értéket az **Áfakód** mezőben.</span><span class="sxs-lookup"><span data-stu-id="705c5-109">In the **Sales tax code** field, type a value.</span></span>
4. <span data-ttu-id="705c5-110">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="705c5-110">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="705c5-111">A lehúzható lista megnyitásával válasszon ki egy **Kiegyenlítési időszakot**, majd adja meg az adóhatóságot, és hogy milyen időközönként kell ezt az áfát bevallani és befizetni.</span><span class="sxs-lookup"><span data-stu-id="705c5-111">Select a **Settlement period** by opening the pull-down list to specify which Sales tax authority and in which intervals this sales tax needs to be reported and paid.</span></span>
6. <span data-ttu-id="705c5-112">Válassza ki a **Főkönyvi feladási csoportot**, és határozza meg azokat a fő számlákat, amelyek áfáját fel kell adni a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="705c5-112">Select a **Ledger posting group** to specify the main accounts to post sales tax to the general ledger.</span></span>
7. <span data-ttu-id="705c5-113">Bontsa ki a **Számítás** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="705c5-113">Expand the **Calculation** FastTab.</span></span> <span data-ttu-id="705c5-114">Ezen a lapon több mező szerepel, amelyek megszabják, hogyan történik az áfaösszegek kiszámítása.</span><span class="sxs-lookup"><span data-stu-id="705c5-114">This includes multiple fields that control how sales tax amounts will be calculated.</span></span> <span data-ttu-id="705c5-115">Töltse ki ezeket a mezőket, ha szükséges.</span><span class="sxs-lookup"><span data-stu-id="705c5-115">Fill these fields out as needed.</span></span>  
8. <span data-ttu-id="705c5-116">A felület felső részén lévő **Műveleti ablaktáblán** válassza ki az **Áfakód** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="705c5-116">On the **Action Pane** at the top of the interface, select **Sales tax code**.</span></span>
9. <span data-ttu-id="705c5-117">Válassza ki az **Értékek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="705c5-117">Select **Values**.</span></span>
10. <span data-ttu-id="705c5-118">Adja meg az adókód értékét az **érték** oszlopban.</span><span class="sxs-lookup"><span data-stu-id="705c5-118">Enter the value for this tax code in the **value** column.</span></span>
    - <span data-ttu-id="705c5-119">A **Számítás** gyorslapon az Eredet mezőben ha az Egységárankénti beállítást választja, az érték meg lesz szorozva a tranzakció összegével az áfaösszeg kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="705c5-119">On the **Calculation** FastTab, in the Origin field, if Amount per unit is selected, the value will be multiplied by the quantity on the transaction to calculate the sales tax amount.</span></span>  <span data-ttu-id="705c5-120">Ha az áfakód nem egy egységalapú adó, az értéke egy százalék, amelyet az ehhez az áfakódhoz tartozó Eredeti értékre alkalmaz az áfaösszeg kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="705c5-120">If the tax code is not a unit based tax, the value is a percentage that is applied on the Origin for this tax code to calculate the sales tax amount.</span></span>     
11. <span data-ttu-id="705c5-121">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="705c5-121">Select **Save**.</span></span>
12. <span data-ttu-id="705c5-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="705c5-122">Close the page.</span></span>
13. <span data-ttu-id="705c5-123">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="705c5-123">Select **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]