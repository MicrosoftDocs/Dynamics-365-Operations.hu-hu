--- 
title: "Termékkonfigurációs modell anyagjegyzékének karbantartása"
description: "Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ef7fc230ea028ef790ad7989fe53f95c70c3b5b1
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="dc0b1-103">Termékkonfigurációs modell anyagjegyzékének karbantartása</span><span class="sxs-lookup"><span data-stu-id="dc0b1-103">Maintain BOM for a product configuration model</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dc0b1-104">Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="dc0b1-105">Ezen eljárás az USMF bemutatócég felső kategóriás hangszóró modelljét használva készült.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>


## <a name="add-a-bom-line"></a><span data-ttu-id="dc0b1-106">Anyagjegyzéksor hozzáadása</span><span class="sxs-lookup"><span data-stu-id="dc0b1-106">Add a BOM line</span></span>
1. <span data-ttu-id="dc0b1-107">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="dc0b1-108">Kattintson a Termékkonfigurációs modellek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="dc0b1-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="dc0b1-110">Válassza ki a Felső kategóriás hangszóró lehetőséget ehhez az eljáráshoz.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-110">Select the High end speaker for this procedure.</span></span>  
4. <span data-ttu-id="dc0b1-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="dc0b1-112">Bontsa ki az Anyagjegyzéksorok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-112">Expand the BOM lines section.</span></span>
6. <span data-ttu-id="dc0b1-113">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-113">Click Add.</span></span>
7. <span data-ttu-id="dc0b1-114">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="dc0b1-115">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="dc0b1-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-116">Click Save.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="dc0b1-117">Anyagjegyzéksor-részletek hozzáadása</span><span class="sxs-lookup"><span data-stu-id="dc0b1-117">Add BOM line details</span></span>
1. <span data-ttu-id="dc0b1-118">Kattintson az Anyagjegyzéksor részletei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-118">Click BOM line details.</span></span>
2. <span data-ttu-id="dc0b1-119">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-119">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="dc0b1-120">Használhatja például az M0055 cikket.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-120">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="dc0b1-121">Minden anyagjegyzéksor-tulajdonság esetében ki lehet választani, hogy rögzített értéke legyen vagy egy attribútum legyen hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-121">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="dc0b1-122">Jelölje be a Beállít jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-122">Select the Set check box.</span></span>
4. <span data-ttu-id="dc0b1-123">Válassza ki az Igen lehetőséget a Számítás mezőben.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-123">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="dc0b1-124">A Számítás tulajdonság beállítása Igen értékre biztosítja, hogy az Anyagjegyzéksor szereplejen a költségszámításokban.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-124">Setting the Calculation property to Yes ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="dc0b1-125">Kattintson a Beállítás fülre.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-125">Click the Setup tab.</span></span>
6. <span data-ttu-id="dc0b1-126">Jelölje be a Beállít jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-126">Select the Set check box.</span></span>
7. <span data-ttu-id="dc0b1-127">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="dc0b1-128">A mennyiség mező határozza meg, hogy az adott cikkből mennyi szereplejen az anyagjegyzékben.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-128">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="dc0b1-129">Ez egy nyilvánvaló jelölt lehet attribútum-hozzárendeléshez.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-129">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="dc0b1-130">Kattintson a Dimenziók fülre.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-130">Click the Dimension tab.</span></span>
    * <span data-ttu-id="dc0b1-131">Győződjön meg róla, hogy aktív-e valamelyik termékdimenzió és ezért szükséges beállítani egy értéket vagy hozzárendelni egy attribútumot.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-131">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="dc0b1-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="dc0b1-132">Click OK.</span></span>


