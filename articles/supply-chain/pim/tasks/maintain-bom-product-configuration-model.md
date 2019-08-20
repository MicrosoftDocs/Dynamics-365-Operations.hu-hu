---
title: Termékkonfigurációs modell anyagjegyzékének karbantartása
description: Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f663c28dfcbf6b365e3e88d3a4f6385ce2fcca9f
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844393"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="baf59-103">Termékkonfigurációs modell anyagjegyzékének karbantartása</span><span class="sxs-lookup"><span data-stu-id="baf59-103">Maintain BOM for a product configuration model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="baf59-104">Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre.</span><span class="sxs-lookup"><span data-stu-id="baf59-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="baf59-105">Ezen eljárás az USMF bemutatócég felső kategóriás hangszóró modelljét használva készült.</span><span class="sxs-lookup"><span data-stu-id="baf59-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>


## <a name="add-a-bom-line"></a><span data-ttu-id="baf59-106">Anyagjegyzéksor hozzáadása</span><span class="sxs-lookup"><span data-stu-id="baf59-106">Add a BOM line</span></span>
1. <span data-ttu-id="baf59-107">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="baf59-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="baf59-108">Kattintson a Termékkonfigurációs modellek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="baf59-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="baf59-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="baf59-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="baf59-110">Válassza ki a Felső kategóriás hangszóró lehetőséget ehhez az eljáráshoz.</span><span class="sxs-lookup"><span data-stu-id="baf59-110">Select the High end speaker for this procedure.</span></span>  
4. <span data-ttu-id="baf59-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="baf59-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="baf59-112">Bontsa ki az Anyagjegyzéksorok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="baf59-112">Expand the BOM lines section.</span></span>
6. <span data-ttu-id="baf59-113">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="baf59-113">Click Add.</span></span>
7. <span data-ttu-id="baf59-114">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="baf59-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="baf59-115">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="baf59-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="baf59-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="baf59-116">Click Save.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="baf59-117">Anyagjegyzéksor-részletek hozzáadása</span><span class="sxs-lookup"><span data-stu-id="baf59-117">Add BOM line details</span></span>
1. <span data-ttu-id="baf59-118">Kattintson az Anyagjegyzéksor részletei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="baf59-118">Click BOM line details.</span></span>
2. <span data-ttu-id="baf59-119">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="baf59-119">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="baf59-120">Használhatja például az M0055 cikket.</span><span class="sxs-lookup"><span data-stu-id="baf59-120">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="baf59-121">Minden anyagjegyzéksor-tulajdonság esetében ki lehet választani, hogy rögzített értéke legyen vagy egy attribútum legyen hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="baf59-121">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="baf59-122">Jelölje be a Beállít jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="baf59-122">Select the Set check box.</span></span>
4. <span data-ttu-id="baf59-123">Válassza ki az Igen lehetőséget a Számítás mezőben.</span><span class="sxs-lookup"><span data-stu-id="baf59-123">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="baf59-124">A Számítás tulajdonság beállítása Igen értékre biztosítja, hogy az Anyagjegyzéksor szereplejen a költségszámításokban.</span><span class="sxs-lookup"><span data-stu-id="baf59-124">Setting the Calculation property to Yes ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="baf59-125">Kattintson a Beállítás fülre.</span><span class="sxs-lookup"><span data-stu-id="baf59-125">Click the Setup tab.</span></span>
6. <span data-ttu-id="baf59-126">Jelölje be a Beállít jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="baf59-126">Select the Set check box.</span></span>
7. <span data-ttu-id="baf59-127">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="baf59-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="baf59-128">A mennyiség mező határozza meg, hogy az adott cikkből mennyi szereplejen az anyagjegyzékben.</span><span class="sxs-lookup"><span data-stu-id="baf59-128">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="baf59-129">Ez egy nyilvánvaló jelölt lehet attribútum-hozzárendeléshez.</span><span class="sxs-lookup"><span data-stu-id="baf59-129">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="baf59-130">Kattintson a Dimenziók fülre.</span><span class="sxs-lookup"><span data-stu-id="baf59-130">Click the Dimension tab.</span></span>
    * <span data-ttu-id="baf59-131">Győződjön meg róla, hogy aktív-e valamelyik termékdimenzió és ezért szükséges beállítani egy értéket vagy hozzárendelni egy attribútumot.</span><span class="sxs-lookup"><span data-stu-id="baf59-131">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="baf59-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="baf59-132">Click OK.</span></span>

