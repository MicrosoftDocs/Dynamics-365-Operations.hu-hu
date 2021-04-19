---
title: Szervizfeladat-kapcsolatok létrehozása
description: A szervizfeladatok társítani lehet a szolgáltatási szerződésekhez vagy szervizrendelésekhez, annak leírásához, hogy milyen szervizfeladatokat kell elvégezni a szerződéhez vagy a rendeléshez.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f9a7808357916ed80ddfa46e1e4f362e0dde1671
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819064"
---
# <a name="create-service-task-relations"></a><span data-ttu-id="21ed3-103">Szervizfeladat-kapcsolatok létrehozása</span><span class="sxs-lookup"><span data-stu-id="21ed3-103">Create service task relations</span></span>    

[!include [banner](../includes/banner.md)]

<span data-ttu-id="21ed3-104">A szervizfeladatok társítani lehet a szolgáltatási szerződésekhez vagy szervizrendelésekhez, annak leírásához, hogy milyen szervizfeladatokat kell elvégezni a szerződéhez vagy a rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="21ed3-104">You can associate service tasks with service agreements or service orders in order to describe the service task to be completed for the agreement or order.</span></span> <span data-ttu-id="21ed3-105">Ezt az információt a szerviztechnikusok és a vevők látják.</span><span class="sxs-lookup"><span data-stu-id="21ed3-105">This information is available to service technicians and customers.</span></span>

## <a name="create-a-relation-with-a-service-agreement"></a><span data-ttu-id="21ed3-106">Kapcsolat létrehozása szolgáltatási szerződéssel</span><span class="sxs-lookup"><span data-stu-id="21ed3-106">Create a relation with a service agreement</span></span>

1.  <span data-ttu-id="21ed3-107">Lépjen a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="21ed3-107">Go to **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="21ed3-108">Válasszon ki egy meglévő szolgáltatási szerződést, vagy hozzon létre egy új szolgáltatási szerződést.</span><span class="sxs-lookup"><span data-stu-id="21ed3-108">Select an existing service agreement, or create a new service agreement.</span></span>

3.  <span data-ttu-id="21ed3-109">A műveleti panelen válassza a **Szervizfeladatok** gombot.</span><span class="sxs-lookup"><span data-stu-id="21ed3-109">On the Action Pane, select the **Service tasks** button.</span></span>

4.  <span data-ttu-id="21ed3-110">A **Szervizfeladatok** képernyőn válassza az **Új** lehetőséget egy új sort létrehozásához, majd válassza ki a **Szervizfeladat** listáról azt a szervizfeladatot, amelyet csatolni kíván a szolgáltatási szerződéshez.</span><span class="sxs-lookup"><span data-stu-id="21ed3-110">On the **Service tasks** form, select **New** to create a new line, and then select a service task from the **Service task** list to attach the service task to the service agreement.</span></span>

5.  <span data-ttu-id="21ed3-111">Írja be az esetleges belső vagy külső leírásokat a **Leírás** lapon található szabadszöveges mezőkbe.</span><span class="sxs-lookup"><span data-stu-id="21ed3-111">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="21ed3-112">Mentse a rekordot a képernyő bezárásával.</span><span class="sxs-lookup"><span data-stu-id="21ed3-112">Close the form to save the record.</span></span>

<span data-ttu-id="21ed3-113">Ismételje meg ezt az eljárást annyiszor, hogy minden szükséges szervizfeladat-kapcsolatot megadjon szolgáltatási szerződésben.</span><span class="sxs-lookup"><span data-stu-id="21ed3-113">Repeat this procedure until you have created all the necessary service task relations for the service agreement.</span></span> <span data-ttu-id="21ed3-114">Mostantól megadhatók ezek a szervizfeladatok bármely csatolt szerződéssorban.</span><span class="sxs-lookup"><span data-stu-id="21ed3-114">You can now specify these service tasks for any attached agreement lines.</span></span>

<span data-ttu-id="21ed3-115">A szolgáltatási szerződéshez kapcsolt szervizfeladatok elérhetők minden olyan szervizrendelésen, amely a szolgáltatási szerződéshez van csatolva.</span><span class="sxs-lookup"><span data-stu-id="21ed3-115">A service tasks relation that is created on a service agreement is available from all service orders that are attached to the service agreement.</span></span>

## <a name="create-a-relation-with-a-service-order"></a><span data-ttu-id="21ed3-116">Kapcsolat létrehozása szervizrendeléssel</span><span class="sxs-lookup"><span data-stu-id="21ed3-116">Create a relation with a service order</span></span>

1.  <span data-ttu-id="21ed3-117">Lépjen ide: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.</span><span class="sxs-lookup"><span data-stu-id="21ed3-117">Go to **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="21ed3-118">Válasszon ki egy meglévő szervizrendelést, vagy hozzon létre egy új szervizrendelést.</span><span class="sxs-lookup"><span data-stu-id="21ed3-118">Select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="21ed3-119">A műveleti panelen válassza a **Szervizfeladatok** gombot.</span><span class="sxs-lookup"><span data-stu-id="21ed3-119">On the Action Pane, select the **Service tasks** button.</span></span>

4.  <span data-ttu-id="21ed3-120">A **Szervizfeladatok** űrlapról válassza az **Új** lehetőséget egy új sort létrehozásához, majd válassza ki a **Szervizfeladat** listáról azokat a szervizfeladatokat, amelyet csatolni kíván a szolgáltatási utasításhoz.</span><span class="sxs-lookup"><span data-stu-id="21ed3-120">From the **Service tasks** form, select **New** to create a new line, and then select a service task from the **Service task** list to attach the service tasks to the service order.</span></span>

5.  <span data-ttu-id="21ed3-121">Írja be az esetleges belső vagy külső leírásokat a **Leírás** lapon található szabadszöveges mezőkbe.</span><span class="sxs-lookup"><span data-stu-id="21ed3-121">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="21ed3-122">Mentse a rekordot a képernyő bezárásával.</span><span class="sxs-lookup"><span data-stu-id="21ed3-122">Close the form to save the record.</span></span>

<span data-ttu-id="21ed3-123">Ismételje meg ezt az eljárást annyiszor, hogy minden szükséges szervizfeladat-kapcsolatot megadjon szervizrendelésben.</span><span class="sxs-lookup"><span data-stu-id="21ed3-123">Repeat this procedure until you have created all the necessary service task relations for the service order.</span></span> <span data-ttu-id="21ed3-124">Most kiválaszthatja azt a szervizfeladatot, amelyhez létrehozta a kapcsolatot a szervizrendeléssorok létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="21ed3-124">You can now select the service task for which you have created the relation when you create service order lines.</span></span>

<span data-ttu-id="21ed3-125">A szervizrendelésen létrehozott szervizfeladat-kapcsolatok az adott szervizrendelésen érhetők el.</span><span class="sxs-lookup"><span data-stu-id="21ed3-125">Service task relations that are created on a service order are available on the specific service order.</span></span>

## <a name="see-also"></a><span data-ttu-id="21ed3-126">Lásd még</span><span class="sxs-lookup"><span data-stu-id="21ed3-126">See also</span></span>

[<span data-ttu-id="21ed3-127">Szervizfeladatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="21ed3-127">Service tasks overview</span></span>](service-tasks.md)


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]