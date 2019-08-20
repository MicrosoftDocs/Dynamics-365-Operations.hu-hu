---
title: Költségösszetevők létrehozása
description: A Költségkönyvelésben számos módon a hozhatók létre költségelemek.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7cceec1d52e1b5b2a05525c8d96f46dece17363b
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841297"
---
# <a name="create-cost-elements"></a><span data-ttu-id="18d5c-103">Költségösszetevők létrehozása</span><span class="sxs-lookup"><span data-stu-id="18d5c-103">Create cost elements</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="18d5c-104">A Költségkönyvelésben számos módon a hozhatók létre költségelemek.</span><span class="sxs-lookup"><span data-stu-id="18d5c-104">There are several ways to create cost elements in Cost accounting.</span></span> <span data-ttu-id="18d5c-105">Ez az eljárás bemutatja, hogyan lehet költségösszetevőket létrehozni a fő számlák importálásával az adatcsatlakozón keresztül.</span><span class="sxs-lookup"><span data-stu-id="18d5c-105">This procedure shows how to create cost elements by importing main accounts via a data connector.</span></span> <span data-ttu-id="18d5c-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="18d5c-106">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="18d5c-107">Ezzel az eljárással a Költségkönyvelés funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="18d5c-107">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-elements"></a><span data-ttu-id="18d5c-108">Új költségösszetevők létrehozása</span><span class="sxs-lookup"><span data-stu-id="18d5c-108">Create new cost elements</span></span>
1. <span data-ttu-id="18d5c-109">Ugrás a Költségkönyvelés > Dimenziók > Költségösszetevő-dimenziók elemre.</span><span class="sxs-lookup"><span data-stu-id="18d5c-109">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="18d5c-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="18d5c-110">Click New.</span></span>
3. <span data-ttu-id="18d5c-111">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="18d5c-111">In the Name field, type a value.</span></span>
4. <span data-ttu-id="18d5c-112">A Dimenziótagok adatcsatlakozója mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="18d5c-112">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="18d5c-113">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="18d5c-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="18d5c-114">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="18d5c-114">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="18d5c-115">Az adatcsatlakozó konfigurálása</span><span class="sxs-lookup"><span data-stu-id="18d5c-115">Configure the data connector</span></span>
1. <span data-ttu-id="18d5c-116">Kattintson a Dimenziótag-szolgáltató konfigurálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="18d5c-116">Click Configure dimension member provider.</span></span>
2. <span data-ttu-id="18d5c-117">A Számlatükör mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="18d5c-117">In the Chart of accounts field, enter or select a value.</span></span>
    * <span data-ttu-id="18d5c-118">Válassza ki a Megosztott lehetőséget a megosztott számlatükör használatához.</span><span class="sxs-lookup"><span data-stu-id="18d5c-118">Select Shared to use the shared chart of accounts.</span></span>  
3. <span data-ttu-id="18d5c-119">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="18d5c-119">Click New.</span></span>
4. <span data-ttu-id="18d5c-120">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="18d5c-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="18d5c-121">A számlákra szűrőket alkalmazhat, hogy megfeleljenek a feltételeinek.</span><span class="sxs-lookup"><span data-stu-id="18d5c-121">You can apply filters to accounts to meet your criteria.</span></span>  
5. <span data-ttu-id="18d5c-122">A fő számlából mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="18d5c-122">In the From main account field, enter or select a value.</span></span>
6. <span data-ttu-id="18d5c-123">A fő számlához mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="18d5c-123">In the To main account field, enter or select a value.</span></span>
7. <span data-ttu-id="18d5c-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="18d5c-124">Click OK.</span></span>

## <a name="import-main-accounts"></a><span data-ttu-id="18d5c-125">Fő számlák importálása</span><span class="sxs-lookup"><span data-stu-id="18d5c-125">Import main accounts</span></span>
1. <span data-ttu-id="18d5c-126">Kattintson a Dimenziótagok importálása elemre.</span><span class="sxs-lookup"><span data-stu-id="18d5c-126">Click Import dimension members.</span></span>
    * <span data-ttu-id="18d5c-127">A fő számlákat a rendszer a Költségkönyvelésbe importálja és költségösszetevőként használja.</span><span class="sxs-lookup"><span data-stu-id="18d5c-127">Main accounts will be imported into Cost accounting and used as cost elements.</span></span>  
2. <span data-ttu-id="18d5c-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="18d5c-128">Click OK.</span></span>

## <a name="view-the-imported-accounts-as-cost-elements"></a><span data-ttu-id="18d5c-129">Importált számlák megjelenítése költségösszetevőként</span><span class="sxs-lookup"><span data-stu-id="18d5c-129">View the imported accounts as cost elements</span></span>
1. <span data-ttu-id="18d5c-130">Kattintson a Dimenziótagok megtekintése elemre.</span><span class="sxs-lookup"><span data-stu-id="18d5c-130">Click View dimension members.</span></span>
    * <span data-ttu-id="18d5c-131">Az importált főkönyvi számlák megtekintése költségösszetevőként, amelyre a költségek könyvelhetők.</span><span class="sxs-lookup"><span data-stu-id="18d5c-131">View the imported ledger accounts as cost elements in your business that costs can flow to.</span></span>  

