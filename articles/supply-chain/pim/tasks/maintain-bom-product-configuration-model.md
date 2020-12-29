---
title: Termékkonfigurációs modell anyagjegyzékének karbantartása
description: Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fcdf4b735587b76b7f761f59c56da1ca358a2e37
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429376"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="2717d-103">Termékkonfigurációs modell anyagjegyzékének karbantartása</span><span class="sxs-lookup"><span data-stu-id="2717d-103">Maintain BOM for a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2717d-104">Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre.</span><span class="sxs-lookup"><span data-stu-id="2717d-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="2717d-105">Ezen eljárás az USMF bemutatócég felső kategóriás hangszóró modelljét használva készült.</span><span class="sxs-lookup"><span data-stu-id="2717d-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>


## <a name="add-a-bom-line"></a><span data-ttu-id="2717d-106">Anyagjegyzéksor hozzáadása</span><span class="sxs-lookup"><span data-stu-id="2717d-106">Add a BOM line</span></span>
1. <span data-ttu-id="2717d-107">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="2717d-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="2717d-108">Kattintson a Termékkonfigurációs modellek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2717d-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="2717d-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="2717d-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2717d-110">Válassza ki a Felső kategóriás hangszóró lehetőséget ehhez az eljáráshoz.</span><span class="sxs-lookup"><span data-stu-id="2717d-110">Select the High end speaker for this procedure.</span></span>  
4. <span data-ttu-id="2717d-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="2717d-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="2717d-112">Bontsa ki az Anyagjegyzéksorok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="2717d-112">Expand the BOM lines section.</span></span>
6. <span data-ttu-id="2717d-113">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="2717d-113">Click Add.</span></span>
7. <span data-ttu-id="2717d-114">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2717d-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="2717d-115">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2717d-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="2717d-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="2717d-116">Click Save.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="2717d-117">Anyagjegyzéksor-részletek hozzáadása</span><span class="sxs-lookup"><span data-stu-id="2717d-117">Add BOM line details</span></span>
1. <span data-ttu-id="2717d-118">Kattintson az Anyagjegyzéksor részletei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2717d-118">Click BOM line details.</span></span>
2. <span data-ttu-id="2717d-119">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2717d-119">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="2717d-120">Használhatja például az M0055 cikket.</span><span class="sxs-lookup"><span data-stu-id="2717d-120">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="2717d-121">Minden anyagjegyzéksor-tulajdonság esetében ki lehet választani, hogy rögzített értéke legyen vagy egy attribútum legyen hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="2717d-121">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="2717d-122">Jelölje be a Beállít jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="2717d-122">Select the Set check box.</span></span>
4. <span data-ttu-id="2717d-123">Válassza ki az Igen lehetőséget a Számítás mezőben.</span><span class="sxs-lookup"><span data-stu-id="2717d-123">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="2717d-124">A Számítás tulajdonság beállítása Igen értékre biztosítja, hogy az Anyagjegyzéksor szereplejen a költségszámításokban.</span><span class="sxs-lookup"><span data-stu-id="2717d-124">Setting the Calculation property to Yes ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="2717d-125">Kattintson a Beállítás fülre.</span><span class="sxs-lookup"><span data-stu-id="2717d-125">Click the Setup tab.</span></span>
6. <span data-ttu-id="2717d-126">Jelölje be a Beállít jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="2717d-126">Select the Set check box.</span></span>
7. <span data-ttu-id="2717d-127">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="2717d-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="2717d-128">A mennyiség mező határozza meg, hogy az adott cikkből mennyi szereplejen az anyagjegyzékben.</span><span class="sxs-lookup"><span data-stu-id="2717d-128">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="2717d-129">Ez egy nyilvánvaló jelölt lehet attribútum-hozzárendeléshez.</span><span class="sxs-lookup"><span data-stu-id="2717d-129">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="2717d-130">Kattintson a Dimenziók fülre.</span><span class="sxs-lookup"><span data-stu-id="2717d-130">Click the Dimension tab.</span></span>
    * <span data-ttu-id="2717d-131">Győződjön meg róla, hogy aktív-e valamelyik termékdimenzió és ezért szükséges beállítani egy értéket vagy hozzárendelni egy attribútumot.</span><span class="sxs-lookup"><span data-stu-id="2717d-131">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="2717d-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="2717d-132">Click OK.</span></span>

