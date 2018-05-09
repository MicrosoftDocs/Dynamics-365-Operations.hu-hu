---
title: "Szolgáltatási szerződések létrehozása"
description: "Ez a témakör ismerteti a Szolgáltatáskezelés és a Projektvezetés és könyvelés modulok funkcióinak használatát a szolgáltatási szerződések létrehozásánál."
author: YuyuScheller
manager: AnnBe
ms.date: 02/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: a3d848b0cfebd190f1aa1d8aa6717d9cf3b80685
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="create-service-agreements"></a><span data-ttu-id="7ee21-103">Szolgáltatási szerződések létrehozása</span><span class="sxs-lookup"><span data-stu-id="7ee21-103">Create service agreements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7ee21-104">Ez a témakör ismerteti a Szolgáltatáskezelés és a Projektvezetés és könyvelés modulok funkcióinak használatát a szolgáltatási szerződések létrehozásánál.</span><span class="sxs-lookup"><span data-stu-id="7ee21-104">This topic describes how to use features in the Service management and the Project management and accounting modules to create service agreements.</span></span>

## <a name="create-a-service-agreement-from-service-management"></a><span data-ttu-id="7ee21-105">Szolgáltatási szerződés létrehozása a Szolgáltatáskezelésből</span><span class="sxs-lookup"><span data-stu-id="7ee21-105">Create a service agreement from Service management</span></span>

1. <span data-ttu-id="7ee21-106">Lépjen a **Szolgáltatáskezelés** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="7ee21-106">Navigate to **Service management**.</span></span>
2. <span data-ttu-id="7ee21-107">Kattintson a **Szolgáltatási szerződések** lehetőségre egy új szolgáltatásiszerződés-sor létrehozásához a lap fejlécében.</span><span class="sxs-lookup"><span data-stu-id="7ee21-107">Click **Service agreements** to create a new service agreement line in the page header.</span></span> 
3. <span data-ttu-id="7ee21-108">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="7ee21-108">Click **New**.</span></span> <span data-ttu-id="7ee21-109">Adjon meg egy leírást, válasszon egy hivatkozást a projekthez a **Projektazonosító** mezőben, és töltse ki a szolgáltatási szerződés többi mezőjét és sorát.</span><span class="sxs-lookup"><span data-stu-id="7ee21-109">Enter a description, select a reference to a project in the **Project ID** field, and fill in the rest of the fields and lines for the service agreement.</span></span> <span data-ttu-id="7ee21-110">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="7ee21-110">Click **Save**.</span></span>
4. <span data-ttu-id="7ee21-111">A **Kapcsolatok** lapon válassza **A szolgáltatás tárgyai** vagy a **Szervizfeladatok** elemet a szolgáltatásiobjektum-kapcsolatok vagy a szervizfeladat-kapcsolatok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="7ee21-111">On the **Relations** tab, select **Service objects** or **Service tasks** to create service object relations or service task relations for the service agreement.</span></span> <span data-ttu-id="7ee21-112">A szolgáltatások kapcsol tárgyai és a kapcsolt szervizfeladatok hozzárendelhetők a szolgáltatási szerződés soraihoz.</span><span class="sxs-lookup"><span data-stu-id="7ee21-112">The service objects and tasks that you have created relations for can be attached on the lines of the service agreement.</span></span>
5. <span data-ttu-id="7ee21-113">Alap alsó részén a sablonból, másik szolgáltatási szerződésből történő másolással vagy a sorok kézi megadásával hozzon létre szolgáltatásiszerződés-sorokat.</span><span class="sxs-lookup"><span data-stu-id="7ee21-113">In the lower half of the page, create service agreement lines by copying lines from a service template, another service agreement, or manually creating the service-agreement lines.</span></span>

> [!NOTE]
> <span data-ttu-id="7ee21-114">Ha másik szolgáltatási szerződésből másol át sorokat, akkor jelezheti, hogy a szolgáltatás tárgyainak és a szervizfeladatoknak a kapcsolatait át szeretné-e másolni.</span><span class="sxs-lookup"><span data-stu-id="7ee21-114">If you copy lines into the service agreement from another service agreement, you can indicate whether you also want to copy service object and service task relations.</span></span> <span data-ttu-id="7ee21-115">Ha átmásolja ezeket a kapcsolatokat, akkor megjelennek a szolgáltatási szerződés meglévő kapcsolatai mellett.</span><span class="sxs-lookup"><span data-stu-id="7ee21-115">If you copy these relations, they are added to any existing relations on the service agreement.</span></span> <span data-ttu-id="7ee21-116">Ha szolgáltatási sablonból másol szerződéssorokat, akkor a kapcsolatok automatikusan az új szolgáltatásiszerződés-sorok megfelelő kapcsolati mezőibe kerülnek.</span><span class="sxs-lookup"><span data-stu-id="7ee21-116">If you copy service-agreement lines from a service template, the service-object and service-task relations are automatically copied as service-object relations and service-task relations on the new service-agreement lines.</span></span>

## <a name="create-service-agreement-lines-manually"></a><span data-ttu-id="7ee21-117">Szolgáltatási szerződés sorainak létrehozása kézzel</span><span class="sxs-lookup"><span data-stu-id="7ee21-117">Create service agreement lines manually</span></span>

1. <span data-ttu-id="7ee21-118">A **Szolgáltatási szerződések** lapon adjon meg egy szolgáltatásiszerződés-sort a sorrácsban.</span><span class="sxs-lookup"><span data-stu-id="7ee21-118">From the **Service agreements** page, add a service agreement line in the lines grid.</span></span> 
2. <span data-ttu-id="7ee21-119">Írja be a megfelelő adatokat a szolgáltatásiszerződés-sorba.</span><span class="sxs-lookup"><span data-stu-id="7ee21-119">Enter the appropriate information for the service agreement line.</span></span> 
3. <span data-ttu-id="7ee21-120">Mentse a sort a **CTRL+S** billentyűkombináció lenyomásával, és zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7ee21-120">Press **CTRL+S** to save the line, and then close the page.</span></span>

## <a name="create-a-service-agreement-from-project"></a><span data-ttu-id="7ee21-121">Szolgáltatási szerződések létrehozása a Projekt modulból</span><span class="sxs-lookup"><span data-stu-id="7ee21-121">Create a service agreement from Project</span></span>

1. <span data-ttu-id="7ee21-122">Kattintson a **Projektvezetés és könyvelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="7ee21-122">Click **Project management and accounting**.</span></span>
2. <span data-ttu-id="7ee21-123">Kattintson a **Minden projekt** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7ee21-123">Click **All projects**.</span></span>
3. <span data-ttu-id="7ee21-124">Válassza ki a projektet a listából.</span><span class="sxs-lookup"><span data-stu-id="7ee21-124">Select the project from the list.</span></span>
4. <span data-ttu-id="7ee21-125">A **Művelet panelen** kattintson a **Kezelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="7ee21-125">On the **Action Pane**, click **Manage**.</span></span> <span data-ttu-id="7ee21-126">Az **Új** műveletcsoportban kattintson a **Szolgáltatás** lehetőségre, és válassza ki a **Szolgáltatási szerződés** pontot.</span><span class="sxs-lookup"><span data-stu-id="7ee21-126">In the **New** Action group, click **Service** and select **Service agreement**.</span></span>
5. <span data-ttu-id="7ee21-127">Kövesse a jelen témakör korábbi, **Szolgáltatási szerződések létrehozása** című szakaszában található utasításokat a projektreferencia megadásához.</span><span class="sxs-lookup"><span data-stu-id="7ee21-127">Follow the steps in the section titled **Create a service agreement** as described earlier in this topic to enter the project reference.</span></span>


## <a name="related-topics"></a><span data-ttu-id="7ee21-128">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="7ee21-128">Related topics</span></span>

[<span data-ttu-id="7ee21-129">Szolgáltatási szerződések</span><span class="sxs-lookup"><span data-stu-id="7ee21-129">Service agreements</span></span>](service-agreements.md)



