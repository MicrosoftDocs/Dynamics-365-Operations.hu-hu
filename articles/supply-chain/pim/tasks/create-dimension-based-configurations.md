---
title: Dimenzión alapuló konfigurációk létrehozása
description: Ez az eljárás bemutatja a dimenzión alapuló termékek konfigurációjának meghatározásának módját.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, EcoResDimensionBasedConfiguration, ConfigChooseFromRoute, ConfigChooseFromGroup, ConfigChoiceApprove
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9190d6dfd4b3f6cf0634e86845e7de028631bdd4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "328585"
---
# <a name="create-dimension-based-configurations"></a><span data-ttu-id="55e66-103">Dimenzión alapuló konfigurációk létrehozása</span><span class="sxs-lookup"><span data-stu-id="55e66-103">Create dimension-based configurations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="55e66-104">Ez az eljárás bemutatja a dimenzión alapuló termékek konfigurációjának meghatározásának módját.</span><span class="sxs-lookup"><span data-stu-id="55e66-104">This procedure shows how to define a configuration for a dimension-based product.</span></span> <span data-ttu-id="55e66-105">Ez az utolsó eljárás a sorozatban, amely a dimenzión alapuló konfiguráció-kombinációk létrehozását ismerteti.</span><span class="sxs-lookup"><span data-stu-id="55e66-105">This is the last procedure in the series that explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="55e66-106">Ezen eljárás végrehajtása az előző hét rögzítésben létrehozott adattól függ.</span><span class="sxs-lookup"><span data-stu-id="55e66-106">The execution of this procedure is dependent on the data created in the previous seven recordings.</span></span> <span data-ttu-id="55e66-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="55e66-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="find-the-dimension-based-product-master"></a><span data-ttu-id="55e66-108">Keresse meg a dimenzión alapuló alapterméket</span><span class="sxs-lookup"><span data-stu-id="55e66-108">Find the dimension-based product master</span></span>
1. <span data-ttu-id="55e66-109">Kattintson a Kiadott termék karbantartása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="55e66-109">Click Released product maintenance.</span></span>
2. <span data-ttu-id="55e66-110">Kattintson a Kibocsátott termék lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="55e66-110">Click Released products.</span></span>
3. <span data-ttu-id="55e66-111">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="55e66-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="55e66-112">Válassza ki a dimenzión alapuló alapterméket, amelyet az első rögzítésben hozott létre a 8 rögzítés sorozatában.</span><span class="sxs-lookup"><span data-stu-id="55e66-112">Select the dimension-based product master that you created in the first recording in this sequence of 8 recordings.</span></span>  

## <a name="create-configurations"></a><span data-ttu-id="55e66-113">Konfigurációk létrehozása</span><span class="sxs-lookup"><span data-stu-id="55e66-113">Create configurations</span></span>
1. <span data-ttu-id="55e66-114">Kattintson Konfigurációk kezelése elemre a Műszaki tervezés Műveleti Ablaktábláján.</span><span class="sxs-lookup"><span data-stu-id="55e66-114">On the Engineering Action Pane, click Maintain configurations.</span></span>
2. <span data-ttu-id="55e66-115">Kattintson a Konfigurálás elemre.</span><span class="sxs-lookup"><span data-stu-id="55e66-115">Click Configure.</span></span>
3. <span data-ttu-id="55e66-116">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="55e66-116">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="55e66-117">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="55e66-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="55e66-118">Válassza ki egy cikket az első konfigurációs csoportban.</span><span class="sxs-lookup"><span data-stu-id="55e66-118">Select any of the items in the first configuration group.</span></span>  
5. <span data-ttu-id="55e66-119">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="55e66-119">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="55e66-120">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="55e66-120">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="55e66-121">Válasszon ki valamennyi cikket a második konfigurációs csoportból.</span><span class="sxs-lookup"><span data-stu-id="55e66-121">Select any item from the second configuration group.</span></span>  
7. <span data-ttu-id="55e66-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="55e66-122">Click OK.</span></span>
8. <span data-ttu-id="55e66-123">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="55e66-123">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="55e66-124">A Konfigurációs mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="55e66-124">In the Configuration field, type a value.</span></span>
    * <span data-ttu-id="55e66-125">Adja meg a konfiguráció nevét, amely megkönnyíti a konfiguráció azonosítását.</span><span class="sxs-lookup"><span data-stu-id="55e66-125">Enter a configuration name that will make it easy to identify the configuration.</span></span>  
10. <span data-ttu-id="55e66-126">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="55e66-126">In the Description field, type a value.</span></span>
    * <span data-ttu-id="55e66-127">Adja meg a konfiguráció leírását annak megmagyarázása érdekében, hogy mit tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="55e66-127">Enter a description of the configuration to explain what it contains.</span></span>  
11. <span data-ttu-id="55e66-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="55e66-128">Click OK.</span></span>

