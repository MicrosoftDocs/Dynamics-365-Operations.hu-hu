---
title: Szervizfeladat-kapcsolatok létrehozása
description: A szervizfeladatok társítani lehet a szolgáltatási szerződésekhez vagy szervizrendelésekhez, annak leírásához, hogy milyen szervizfeladatokat kell elvégezni a szerződéhez vagy a rendeléshez.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed0800c4a650233190c6a33b1690790f0e2bf051
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814098"
---
# <a name="create-service-task-relations"></a><span data-ttu-id="e140a-103">Szervizfeladat-kapcsolatok létrehozása</span><span class="sxs-lookup"><span data-stu-id="e140a-103">Create service task relations</span></span>    

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e140a-104">A szervizfeladatok társítani lehet a szolgáltatási szerződésekhez vagy szervizrendelésekhez, annak leírásához, hogy milyen szervizfeladatokat kell elvégezni a szerződéhez vagy a rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="e140a-104">You can associate service tasks with service agreements or service orders in order to describe the service task to be completed for the agreement or order.</span></span> <span data-ttu-id="e140a-105">Ezt az információt a szerviztechnikusok és a vevők látják.</span><span class="sxs-lookup"><span data-stu-id="e140a-105">This information is available to service technicians and customers.</span></span>

## <a name="create-a-relation-with-a-service-agreement"></a><span data-ttu-id="e140a-106">Kapcsolat létrehozása szolgáltatási szerződéssel</span><span class="sxs-lookup"><span data-stu-id="e140a-106">Create a relation with a service agreement</span></span>

1.  <span data-ttu-id="e140a-107">Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e140a-107">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="e140a-108">Válasszon ki egy meglévő szolgáltatási szerződést, vagy hozzon létre egy új szolgáltatási szerződést.</span><span class="sxs-lookup"><span data-stu-id="e140a-108">Select an existing service agreement, or create a new service agreement.</span></span>

3.  <span data-ttu-id="e140a-109">A műveleti panelen kattintson a **Szervizfeladatok** gombra.</span><span class="sxs-lookup"><span data-stu-id="e140a-109">On the Action Pane, click the **Service tasks** button.</span></span>

4.  <span data-ttu-id="e140a-110">A **Szervizfeladatok** képernyőn nyomja meg a CTRL+N billentyűkombinációt egy új sort létrehozásához, majd válassza ki a **Szervizfeladat** listáról azt a szervizfeladatot, amelyet csatolni kíván a szolgáltatási szerződéshez.</span><span class="sxs-lookup"><span data-stu-id="e140a-110">On the **Service tasks** form, press CTRL+N to create a new line, and then select a service task from the **Service task** list to attach the service task to the service agreement.</span></span>

5.  <span data-ttu-id="e140a-111">Írja be az esetleges belső vagy külső leírásokat a **Leírás** lapon található szabadszöveges mezőkbe.</span><span class="sxs-lookup"><span data-stu-id="e140a-111">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="e140a-112">Mentse a rekordot a képernyő bezárásával.</span><span class="sxs-lookup"><span data-stu-id="e140a-112">Close the form to save the record.</span></span>

<span data-ttu-id="e140a-113">Ismételje meg ezt az eljárást annyiszor, hogy minden szükséges szervizfeladat-kapcsolatot megadjon szolgáltatási szerződésben.</span><span class="sxs-lookup"><span data-stu-id="e140a-113">Repeat this procedure until you have created all the necessary service task relations for the service agreement.</span></span> <span data-ttu-id="e140a-114">Mostantól megadhatók ezek a szervizfeladatok bármely csatolt szerződéssorban.</span><span class="sxs-lookup"><span data-stu-id="e140a-114">You can now specify these service tasks for any attached agreement lines.</span></span>

<span data-ttu-id="e140a-115">A szolgáltatási szerződéshez kapcsolt szervizfeladatok elérhetők minden olyan szervizrendelésen, amely a szolgáltatási szerződéshez van csatolva.</span><span class="sxs-lookup"><span data-stu-id="e140a-115">A service tasks relation that is created on a service agreement is available from all service orders that are attached to the service agreement.</span></span>

## <a name="create-a-relation-with-a-service-order"></a><span data-ttu-id="e140a-116">Kapcsolat létrehozása szervizrendeléssel</span><span class="sxs-lookup"><span data-stu-id="e140a-116">Create a relation with a service order</span></span>

1.  <span data-ttu-id="e140a-117">Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.</span><span class="sxs-lookup"><span data-stu-id="e140a-117">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="e140a-118">Válasszon ki egy meglévő szervizrendelést, vagy hozzon létre egy új szervizrendelést.</span><span class="sxs-lookup"><span data-stu-id="e140a-118">Select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="e140a-119">A műveleti panelen kattintson a **Szervizfeladatok** gombra.</span><span class="sxs-lookup"><span data-stu-id="e140a-119">On the Action Pane, click the **Service tasks** button.</span></span>

4.  <span data-ttu-id="e140a-120">A **Szervizfeladatok** képernyőn nyomja meg a CTRL+N billentyűkombinációt egy új sort létrehozásához, majd válassza ki a **Szervizfeladat** listáról azokat a szervizfeladatokat, amelyeket csatolni kíván a szervizrendeléshez.</span><span class="sxs-lookup"><span data-stu-id="e140a-120">From the **Service tasks** form, press CTRL+N to create a new line, and then select a service task from the **Service task** list to attach the service tasks to the service order.</span></span>

5.  <span data-ttu-id="e140a-121">Írja be az esetleges belső vagy külső leírásokat a **Leírás** lapon található szabadszöveges mezőkbe.</span><span class="sxs-lookup"><span data-stu-id="e140a-121">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="e140a-122">Mentse a rekordot a képernyő bezárásával.</span><span class="sxs-lookup"><span data-stu-id="e140a-122">Close the form to save the record.</span></span>

<span data-ttu-id="e140a-123">Ismételje meg ezt az eljárást annyiszor, hogy minden szükséges szervizfeladat-kapcsolatot megadjon szervizrendelésben.</span><span class="sxs-lookup"><span data-stu-id="e140a-123">Repeat this procedure until you have created all the necessary service task relations for the service order.</span></span> <span data-ttu-id="e140a-124">Most kiválaszthatja azt a szervizfeladatot, amelyhez létrehozta a kapcsolatot a szervizrendeléssorok létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="e140a-124">You can now select the service task for which you have created the relation when you create service order lines.</span></span>

<span data-ttu-id="e140a-125">A szervizrendelésen létrehozott szervizfeladat-kapcsolatok az adott szervizrendelésen érhetők el.</span><span class="sxs-lookup"><span data-stu-id="e140a-125">Service task relations that are created on a service order are available on the specific service order.</span></span>

## <a name="see-also"></a><span data-ttu-id="e140a-126">Lásd még</span><span class="sxs-lookup"><span data-stu-id="e140a-126">See also</span></span>

[<span data-ttu-id="e140a-127">Szervizfeladatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="e140a-127">Service tasks overview</span></span>](service-tasks.md)


  


