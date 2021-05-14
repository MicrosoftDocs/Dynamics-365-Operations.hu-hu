---
title: Termékkonfigurációs modell anyagjegyzékének karbantartása
description: Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b4ad73265e321b6339c061a7866b55cb2769954b
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921317"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="a07aa-103">Termékkonfigurációs modell anyagjegyzékének karbantartása</span><span class="sxs-lookup"><span data-stu-id="a07aa-103">Maintain BOM for a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a07aa-104">Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre.</span><span class="sxs-lookup"><span data-stu-id="a07aa-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="a07aa-105">Ezen eljárás az USMF bemutatócég felső kategóriás hangszóró modelljét használva készült.</span><span class="sxs-lookup"><span data-stu-id="a07aa-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>

## <a name="add-a-bom-line"></a><span data-ttu-id="a07aa-106">Anyagjegyzéksor hozzáadása</span><span class="sxs-lookup"><span data-stu-id="a07aa-106">Add a BOM line</span></span>

1. <span data-ttu-id="a07aa-107">Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.</span><span class="sxs-lookup"><span data-stu-id="a07aa-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="a07aa-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="a07aa-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a07aa-109">Válassza ki a Felső kategóriás hangszóró lehetőséget ehhez az eljáráshoz.</span><span class="sxs-lookup"><span data-stu-id="a07aa-109">Select the High end speaker for this procedure.</span></span>  
1. <span data-ttu-id="a07aa-110">A listában válassza ki a kiválasztott sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="a07aa-110">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="a07aa-111">Bontsa ki az **Anyagjegyzéksorok** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="a07aa-111">Expand the **BOM lines** section.</span></span>
1. <span data-ttu-id="a07aa-112">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a07aa-112">Select **Add**.</span></span>
1. <span data-ttu-id="a07aa-113">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a07aa-113">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="a07aa-114">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a07aa-114">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="a07aa-115">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a07aa-115">Select **Save**.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="a07aa-116">Anyagjegyzéksor-részletek hozzáadása</span><span class="sxs-lookup"><span data-stu-id="a07aa-116">Add BOM line details</span></span>

1. <span data-ttu-id="a07aa-117">Válassza ki az **Anyagjegyzéksor részletei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a07aa-117">Select **BOM line details**.</span></span>
2. <span data-ttu-id="a07aa-118">Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a07aa-118">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="a07aa-119">Használhatja például az M0055 cikket.</span><span class="sxs-lookup"><span data-stu-id="a07aa-119">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="a07aa-120">Minden anyagjegyzéksor-tulajdonság esetében ki lehet választani, hogy rögzített értéke legyen vagy egy attribútum legyen hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="a07aa-120">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="a07aa-121">Jelölje be a **Beállít** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="a07aa-121">Select the **Set** check box.</span></span>
4. <span data-ttu-id="a07aa-122">Válassza ki az *Igen* lehetőséget a **Számítás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a07aa-122">Select *Yes* in the **Calculation** field.</span></span>
    * <span data-ttu-id="a07aa-123">A **Számítás** tulajdonság beállítása *Igen* értékre biztosítja, hogy az Anyagjegyzéksor szereplejen a költségszámításokban.</span><span class="sxs-lookup"><span data-stu-id="a07aa-123">Setting the **Calculation** property to *Yes* ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="a07aa-124">Válassza ki a **Beállítás** fület.</span><span class="sxs-lookup"><span data-stu-id="a07aa-124">Select the **Setup** tab.</span></span>
6. <span data-ttu-id="a07aa-125">Jelölje be a **Beállít** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="a07aa-125">Select the **Set** check box.</span></span>
7. <span data-ttu-id="a07aa-126">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a07aa-126">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="a07aa-127">A mennyiség mező határozza meg, hogy az adott cikkből mennyi szereplejen az anyagjegyzékben.</span><span class="sxs-lookup"><span data-stu-id="a07aa-127">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="a07aa-128">Ez egy nyilvánvaló jelölt lehet attribútum-hozzárendeléshez.</span><span class="sxs-lookup"><span data-stu-id="a07aa-128">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="a07aa-129">Válassza ki a **Dimenzió** fület.</span><span class="sxs-lookup"><span data-stu-id="a07aa-129">Select the **Dimension** tab.</span></span>
    * <span data-ttu-id="a07aa-130">Győződjön meg róla, hogy aktív-e valamelyik termékdimenzió és ezért szükséges beállítani egy értéket vagy hozzárendelni egy attribútumot.</span><span class="sxs-lookup"><span data-stu-id="a07aa-130">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="a07aa-131">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a07aa-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]