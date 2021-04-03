---
title: Költségobjektumok létrehozása
description: Ez az eljárás bemutatja, hogyan lehet költségobjektumokat létrehozni költséghely pénzügyi dimenziók importálásával a Költségkönyvelésbe az adatcsatlakozón keresztül.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 91c25c52a2c6dc7f096a494577b361ff30406e9c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236794"
---
# <a name="create-cost-objects"></a><span data-ttu-id="178ae-103">Költségobjektumok létrehozása</span><span class="sxs-lookup"><span data-stu-id="178ae-103">Create cost objects</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="178ae-104">Ez az eljárás bemutatja, hogyan lehet költségobjektumokat létrehozni költséghely pénzügyi dimenziók importálásával a Költségkönyvelésbe az adatcsatlakozón keresztül.</span><span class="sxs-lookup"><span data-stu-id="178ae-104">This procedure shows how to create cost objects by importing the cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="178ae-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="178ae-105">The USMF demo company was used to create this procedure.</span></span> 


## <a name="create-new-cost-objects"></a><span data-ttu-id="178ae-106">Új költségobjektumok létrehozása</span><span class="sxs-lookup"><span data-stu-id="178ae-106">Create new cost objects</span></span>
1. <span data-ttu-id="178ae-107">Ugrás a Költségkönyvelés > Dimenziók > Költségobjektum-dimenziók elemre.</span><span class="sxs-lookup"><span data-stu-id="178ae-107">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="178ae-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="178ae-108">Click New.</span></span>
3. <span data-ttu-id="178ae-109">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="178ae-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="178ae-110">A Dimenziótagok adatcsatlakozója mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="178ae-110">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="178ae-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="178ae-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="178ae-112">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="178ae-112">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="178ae-113">Az adatcsatlakozó konfigurálása</span><span class="sxs-lookup"><span data-stu-id="178ae-113">Configure the data connector</span></span>
1. <span data-ttu-id="178ae-114">Kattintson a Dimenziótag-szolgáltató konfigurálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="178ae-114">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="178ae-115">Válassza ki a CostCenter lehetőséget a CostCenter dimenzió importálásához a Költségkönyvelésbe.</span><span class="sxs-lookup"><span data-stu-id="178ae-115">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="178ae-116">A Dimenzió neve mezőben válassza ki a Költséghelyet.</span><span class="sxs-lookup"><span data-stu-id="178ae-116">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="178ae-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="178ae-117">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="178ae-118">Költséghelyek importálása</span><span class="sxs-lookup"><span data-stu-id="178ae-118">Import cost centers</span></span>
1. <span data-ttu-id="178ae-119">Kattintson a Dimenziótagok importálása elemre.</span><span class="sxs-lookup"><span data-stu-id="178ae-119">Click Import dimension members.</span></span>
2. <span data-ttu-id="178ae-120">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="178ae-120">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="178ae-121">Az importált költséghelyek megtekintése</span><span class="sxs-lookup"><span data-stu-id="178ae-121">View the imported cost centers</span></span>
1. <span data-ttu-id="178ae-122">Kattintson a Dimenziótagok megtekintése elemre.</span><span class="sxs-lookup"><span data-stu-id="178ae-122">Click View dimension members.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]