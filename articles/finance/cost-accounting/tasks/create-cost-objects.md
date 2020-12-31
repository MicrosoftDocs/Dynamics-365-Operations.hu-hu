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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 55f5f6e5048f70e744cb3dc82a2a279aae69b4af
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444113"
---
# <a name="create-cost-objects"></a><span data-ttu-id="e0e1b-103">Költségobjektumok létrehozása</span><span class="sxs-lookup"><span data-stu-id="e0e1b-103">Create cost objects</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e0e1b-104">Ez az eljárás bemutatja, hogyan lehet költségobjektumokat létrehozni költséghely pénzügyi dimenziók importálásával a Költségkönyvelésbe az adatcsatlakozón keresztül.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-104">This procedure shows how to create cost objects by importing the cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="e0e1b-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-105">The USMF demo company was used to create this procedure.</span></span> 


## <a name="create-new-cost-objects"></a><span data-ttu-id="e0e1b-106">Új költségobjektumok létrehozása</span><span class="sxs-lookup"><span data-stu-id="e0e1b-106">Create new cost objects</span></span>
1. <span data-ttu-id="e0e1b-107">Ugrás a Költségkönyvelés > Dimenziók > Költségobjektum-dimenziók elemre.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-107">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="e0e1b-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-108">Click New.</span></span>
3. <span data-ttu-id="e0e1b-109">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="e0e1b-110">A Dimenziótagok adatcsatlakozója mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-110">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="e0e1b-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="e0e1b-112">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-112">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="e0e1b-113">Az adatcsatlakozó konfigurálása</span><span class="sxs-lookup"><span data-stu-id="e0e1b-113">Configure the data connector</span></span>
1. <span data-ttu-id="e0e1b-114">Kattintson a Dimenziótag-szolgáltató konfigurálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-114">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="e0e1b-115">Válassza ki a CostCenter lehetőséget a CostCenter dimenzió importálásához a Költségkönyvelésbe.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-115">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="e0e1b-116">A Dimenzió neve mezőben válassza ki a Költséghelyet.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-116">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="e0e1b-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-117">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="e0e1b-118">Költséghelyek importálása</span><span class="sxs-lookup"><span data-stu-id="e0e1b-118">Import cost centers</span></span>
1. <span data-ttu-id="e0e1b-119">Kattintson a Dimenziótagok importálása elemre.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-119">Click Import dimension members.</span></span>
2. <span data-ttu-id="e0e1b-120">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-120">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="e0e1b-121">Az importált költséghelyek megtekintése</span><span class="sxs-lookup"><span data-stu-id="e0e1b-121">View the imported cost centers</span></span>
1. <span data-ttu-id="e0e1b-122">Kattintson a Dimenziótagok megtekintése elemre.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-122">Click View dimension members.</span></span>

