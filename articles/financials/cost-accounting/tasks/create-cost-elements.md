--- 
title: "Költségösszetevők létrehozása"
description: "A Költségkönyvelésben számos módon a hozhatók létre költségelemek."
author: YuyuScheller
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1e665fc53455e457a2488f4ec28ebb5b715d90eb
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-cost-elements"></a><span data-ttu-id="6de1b-103">Költségösszetevők létrehozása</span><span class="sxs-lookup"><span data-stu-id="6de1b-103">Create cost elements</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6de1b-104">A Költségkönyvelésben számos módon a hozhatók létre költségelemek.</span><span class="sxs-lookup"><span data-stu-id="6de1b-104">There are several ways to create cost elements in Cost accounting.</span></span> <span data-ttu-id="6de1b-105">Ez az eljárás bemutatja, hogyan lehet költségösszetevőket létrehozni a fő számlák importálásával az adatcsatlakozón keresztül.</span><span class="sxs-lookup"><span data-stu-id="6de1b-105">This procedure shows how to create cost elements by importing main accounts via a data connector.</span></span> <span data-ttu-id="6de1b-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="6de1b-106">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="6de1b-107">Ez az eljárás egy olyan költségkönyvelési funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="6de1b-107">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-elements"></a><span data-ttu-id="6de1b-108">Új költségösszetevők létrehozása</span><span class="sxs-lookup"><span data-stu-id="6de1b-108">Create new cost elements</span></span>
1. <span data-ttu-id="6de1b-109">Ugrás a Költségkönyvelés > Dimenziók > Költségösszetevő-dimenziók elemre.</span><span class="sxs-lookup"><span data-stu-id="6de1b-109">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="6de1b-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6de1b-110">Click New.</span></span>
3. <span data-ttu-id="6de1b-111">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6de1b-111">In the Name field, type a value.</span></span>
4. <span data-ttu-id="6de1b-112">A Dimenziótagok adatcsatlakozója mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6de1b-112">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="6de1b-113">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6de1b-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="6de1b-114">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="6de1b-114">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="6de1b-115">Az adatcsatlakozó konfigurálása</span><span class="sxs-lookup"><span data-stu-id="6de1b-115">Configure the data connector</span></span>
1. <span data-ttu-id="6de1b-116">Kattintson a Dimenziótag-szolgáltató konfigurálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6de1b-116">Click Configure dimension member provider.</span></span>
2. <span data-ttu-id="6de1b-117">A Számlatükör mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6de1b-117">In the Chart of accounts field, enter or select a value.</span></span>
    * <span data-ttu-id="6de1b-118">Válassza ki a Megosztott lehetőséget a megosztott számlatükör használatához.</span><span class="sxs-lookup"><span data-stu-id="6de1b-118">Select Shared to use the shared chart of accounts.</span></span>  
3. <span data-ttu-id="6de1b-119">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6de1b-119">Click New.</span></span>
4. <span data-ttu-id="6de1b-120">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="6de1b-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="6de1b-121">A számlákra szűrőket alkalmazhat, hogy megfeleljenek a feltételeinek.</span><span class="sxs-lookup"><span data-stu-id="6de1b-121">You can apply filters to accounts to meet your criteria.</span></span>  
5. <span data-ttu-id="6de1b-122">A fő számlából mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6de1b-122">In the From main account field, enter or select a value.</span></span>
6. <span data-ttu-id="6de1b-123">A fő számlához mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6de1b-123">In the To main account field, enter or select a value.</span></span>
7. <span data-ttu-id="6de1b-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6de1b-124">Click OK.</span></span>

## <a name="import-main-accounts"></a><span data-ttu-id="6de1b-125">Fő számlák importálása</span><span class="sxs-lookup"><span data-stu-id="6de1b-125">Import main accounts</span></span>
1. <span data-ttu-id="6de1b-126">Kattintson a Dimenziótagok importálása elemre.</span><span class="sxs-lookup"><span data-stu-id="6de1b-126">Click Import dimension members.</span></span>
    * <span data-ttu-id="6de1b-127">A fő számlákat a rendszer a Költségkönyvelésbe importálja és költségösszetevőként használja.</span><span class="sxs-lookup"><span data-stu-id="6de1b-127">Main accounts will be imported into Cost accounting and used as cost elements.</span></span>  
2. <span data-ttu-id="6de1b-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6de1b-128">Click OK.</span></span>

## <a name="view-the-imported-accounts-as-cost-elements"></a><span data-ttu-id="6de1b-129">Importált számlák megjelenítése költségösszetevőként</span><span class="sxs-lookup"><span data-stu-id="6de1b-129">View the imported accounts as cost elements</span></span>
1. <span data-ttu-id="6de1b-130">Kattintson a Dimenziótagok megtekintése elemre.</span><span class="sxs-lookup"><span data-stu-id="6de1b-130">Click View dimension members.</span></span>
    * <span data-ttu-id="6de1b-131">Az importált főkönyvi számlák megtekintése költségösszetevőként, amelyre a költségek könyvelhetők.</span><span class="sxs-lookup"><span data-stu-id="6de1b-131">View the imported ledger accounts as cost elements in your business that costs can flow to.</span></span>  


