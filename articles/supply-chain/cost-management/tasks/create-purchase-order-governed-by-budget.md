---
title: Költségvetés által irányított beszerzési rendelés létrehozása
description: Ezzel az eljárással beszerzési rendelést lehet létrehozni, amelyet a rendszer költségvetés-ellenőrzésnek vet alá.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a79b19ce4ff35ecc1f691edea1bdc5e30010b433
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821369"
---
# <a name="create-a-purchase-order-governed-by-budget"></a><span data-ttu-id="6313b-103">Költségvetés által irányított beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="6313b-103">Create a purchase order governed by budget</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6313b-104">Ezzel az eljárással beszerzési rendelést lehet létrehozni, amelyet a rendszer költségvetés-ellenőrzésnek vet alá.</span><span class="sxs-lookup"><span data-stu-id="6313b-104">Use this procedure to create a purchase order that is checked for available budget.</span></span> <span data-ttu-id="6313b-105">Ez a felvétel az USMF bemutató vállalati adatait használja.</span><span class="sxs-lookup"><span data-stu-id="6313b-105">This recording uses the USMF demo data company.</span></span>


## <a name="review-the-budget-control-configuration"></a><span data-ttu-id="6313b-106">Költségvetés-ellenőrzési konfiguráció áttekintése</span><span class="sxs-lookup"><span data-stu-id="6313b-106">Review the budget control configuration</span></span>
1. <span data-ttu-id="6313b-107">Lépjen a Költségvetés készítése > Beállítás > Költségvetés-ellenőrzés > Költségvetés-ellenőrzés konfigurációja lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6313b-107">Go to Budgeting > Setup > Budget control > Budget control configuration.</span></span>
2. <span data-ttu-id="6313b-108">Kattintson a Rendelkezésre álló költségvetési források lapra.</span><span class="sxs-lookup"><span data-stu-id="6313b-108">Click the Budget funds available tab.</span></span>
3. <span data-ttu-id="6313b-109">Kattintson a Dokumentumok és naplók lapra.</span><span class="sxs-lookup"><span data-stu-id="6313b-109">Click the Documents and journals tab.</span></span>
4. <span data-ttu-id="6313b-110">Kattintson a Költségvetés-ellenőrzési szabályok meghatározása lapra.</span><span class="sxs-lookup"><span data-stu-id="6313b-110">Click the Define budget control rules tab.</span></span>
5. <span data-ttu-id="6313b-111">Kattintson a Költségvetés-ellenőrzési csoportok meghatározása lapra.</span><span class="sxs-lookup"><span data-stu-id="6313b-111">Click the Define budget groups tab.</span></span>
6. <span data-ttu-id="6313b-112">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6313b-112">Close the page.</span></span>

## <a name="create-the-purchase-order-header"></a><span data-ttu-id="6313b-113">Beszerzési rendelési fejléc létrehozása</span><span class="sxs-lookup"><span data-stu-id="6313b-113">Create the purchase order header</span></span>
1. <span data-ttu-id="6313b-114">Ugorjon a Beszerzés és forrás > Beszerzési rendelés > Összes beszerzési rendelés pontra.</span><span class="sxs-lookup"><span data-stu-id="6313b-114">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="6313b-115">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6313b-115">Click New.</span></span>
3. <span data-ttu-id="6313b-116">A Szállítószámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6313b-116">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="6313b-117">Bontsa ki az Általános szakaszt.</span><span class="sxs-lookup"><span data-stu-id="6313b-117">Expand the General section.</span></span>
5. <span data-ttu-id="6313b-118">A Könyvelési dátum mezőben állítsa a dátumot „2016-01-01” értékre.</span><span class="sxs-lookup"><span data-stu-id="6313b-118">In the Accounting date field, set the date to '2016-01-01'.</span></span>
6. <span data-ttu-id="6313b-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6313b-119">Click OK.</span></span>

## <a name="add-a-purchase-order-line"></a><span data-ttu-id="6313b-120">Beszerzési rendelési sor hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6313b-120">Add a purchase order line</span></span>
1. <span data-ttu-id="6313b-121">A Beszerzési kategória mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6313b-121">In the Procurement category field, enter or select a value.</span></span>
2. <span data-ttu-id="6313b-122">Állítsa a mennyiséget „2” értékre.</span><span class="sxs-lookup"><span data-stu-id="6313b-122">Set Quantity to '2'.</span></span>
3. <span data-ttu-id="6313b-123">Az Egység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6313b-123">In the Unit field, enter or select a value.</span></span>
4. <span data-ttu-id="6313b-124">Állítsa az Egységárat „10000”-re.</span><span class="sxs-lookup"><span data-stu-id="6313b-124">Set Unit price to '10000'.</span></span>
5. <span data-ttu-id="6313b-125">Kattintson a Pénzügyre.</span><span class="sxs-lookup"><span data-stu-id="6313b-125">Click Financials.</span></span>
6. <span data-ttu-id="6313b-126">Kattintson az Összegek felosztása elemre.</span><span class="sxs-lookup"><span data-stu-id="6313b-126">Click Distribute amounts.</span></span>
7. <span data-ttu-id="6313b-127">A Főkönyvi számla mezőben adja meg a „601300-001-023--” értéket.</span><span class="sxs-lookup"><span data-stu-id="6313b-127">In the Ledger account field, specify the value '601300-001-023--'.</span></span>
8. <span data-ttu-id="6313b-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6313b-128">Close the page.</span></span>

## <a name="perform-budget-checking"></a><span data-ttu-id="6313b-129">Költségvetés ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="6313b-129">Perform budget checking</span></span>
1. <span data-ttu-id="6313b-130">Kattintson a Pénzügyre.</span><span class="sxs-lookup"><span data-stu-id="6313b-130">Click Financials.</span></span>
2. <span data-ttu-id="6313b-131">Kattintson a Költségvetés ellenőrzése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6313b-131">Click Perform budget checking.</span></span>
3. <span data-ttu-id="6313b-132">Kattintson a Pénzügyre.</span><span class="sxs-lookup"><span data-stu-id="6313b-132">Click Financials.</span></span>
4. <span data-ttu-id="6313b-133">Kattintson a Költségvetés ellenőrzésekor fellépő hibák vagy figyelmeztetések lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6313b-133">Click Budget check errors or warnings.</span></span>
5. <span data-ttu-id="6313b-134">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="6313b-134">Click Close.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]