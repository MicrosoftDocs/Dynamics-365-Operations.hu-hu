---
title: Költségobjektumok létrehozása
description: Ez az eljárás bemutatja, hogyan lehet költségobjektumokat létrehozni a Dynamics 365 for Finance and Operations, Enterprise kiadás költséghely pénzügyi dimenziók importálásával a Költségkönyvelésbe az adatcsatlakozón keresztül.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e12de1d51658092fb19f652cef7c1cc78b255b5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "322674"
---
# <a name="create-cost-objects"></a><span data-ttu-id="3471c-103">Költségobjektumok létrehozása</span><span class="sxs-lookup"><span data-stu-id="3471c-103">Create cost objects</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3471c-104">Ez az eljárás bemutatja, hogyan lehet költségobjektumokat létrehozni a Dynamics 365 for Finance and Operations, Enterprise kiadás költséghely pénzügyi dimenziók importálásával a Költségkönyvelésbe az adatcsatlakozón keresztül.</span><span class="sxs-lookup"><span data-stu-id="3471c-104">This procedure shows how to create cost objects by importing the Dynamics 365 for Finance and Operations, Enterprise edition cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="3471c-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="3471c-105">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="3471c-106">Ezzel az eljárással a Költségkönyvelés funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="3471c-106">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-objects"></a><span data-ttu-id="3471c-107">Új költségobjektumok létrehozása</span><span class="sxs-lookup"><span data-stu-id="3471c-107">Create new cost objects</span></span>
1. <span data-ttu-id="3471c-108">Ugrás a Költségkönyvelés > Dimenziók > Költségobjektum-dimenziók elemre.</span><span class="sxs-lookup"><span data-stu-id="3471c-108">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="3471c-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3471c-109">Click New.</span></span>
3. <span data-ttu-id="3471c-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="3471c-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="3471c-111">A Dimenziótagok adatcsatlakozója mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3471c-111">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="3471c-112">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3471c-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="3471c-113">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3471c-113">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="3471c-114">Az adatcsatlakozó konfigurálása</span><span class="sxs-lookup"><span data-stu-id="3471c-114">Configure the data connector</span></span>
1. <span data-ttu-id="3471c-115">Kattintson a Dimenziótag-szolgáltató konfigurálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3471c-115">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="3471c-116">Válassza ki a CostCenter lehetőséget a CostCenter dimenzió importálásához a Költségkönyvelésbe.</span><span class="sxs-lookup"><span data-stu-id="3471c-116">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="3471c-117">A Dimenzió neve mezőben válassza ki a Költséghelyet.</span><span class="sxs-lookup"><span data-stu-id="3471c-117">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="3471c-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3471c-118">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="3471c-119">Költséghelyek importálása</span><span class="sxs-lookup"><span data-stu-id="3471c-119">Import cost centers</span></span>
1. <span data-ttu-id="3471c-120">Kattintson a Dimenziótagok importálása elemre.</span><span class="sxs-lookup"><span data-stu-id="3471c-120">Click Import dimension members.</span></span>
2. <span data-ttu-id="3471c-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3471c-121">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="3471c-122">Az importált költséghelyek megtekintése</span><span class="sxs-lookup"><span data-stu-id="3471c-122">View the imported cost centers</span></span>
1. <span data-ttu-id="3471c-123">Kattintson a Dimenziótagok megtekintése elemre.</span><span class="sxs-lookup"><span data-stu-id="3471c-123">Click View dimension members.</span></span>

