---
title: Szolgáltatásiobjektum-kapcsolat létrehozása
description: Ez a témakör a szolgáltatási szerződésekhez és a szervizrendelésekhez alkalmazható szolgáltatásitárgy-kapcsolatok létrehozását mutatja be.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 352d3b790da340102b7dbe116d9deeb2f3cbfc4e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429707"
---
# <a name="create-service-object-relations"></a><span data-ttu-id="59a21-103">Szolgáltatásiobjektum-kapcsolat létrehozása</span><span class="sxs-lookup"><span data-stu-id="59a21-103">Create service object relations</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="59a21-104">Ez a témakör a szolgáltatási szerződésekhez és a szervizrendelésekhez alkalmazható szolgáltatásitárgy-kapcsolatok létrehozását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="59a21-104">This topic describes how to create service object relations for a service agreement and a service order.</span></span> <span data-ttu-id="59a21-105">Egy szolgáltatásitárgy-kapcsolat létrehozásakor a szolgáltatási tárgyat egy szolgáltatási szerződéshez vagy egy szervizrendeléshez társítja.</span><span class="sxs-lookup"><span data-stu-id="59a21-105">When you a create service object relation, you associate the service object to a service agreement or service order.</span></span> <span data-ttu-id="59a21-106">Ha egy vevő szolgáltatást igényel egy olyan cikkhez, ami egy szolgáltatási tárgy, a szolgáltatási tárgyat kiválaszthatja a szolgáltatásitárgy-kapcsolatok listájáról.</span><span class="sxs-lookup"><span data-stu-id="59a21-106">When a customer requests service for an item that is a service object, you can select the service object from the list of service object relations.</span></span>

## <a name="create-a-service-object-relation-for-a-service-agreement"></a><span data-ttu-id="59a21-107">Hozzon létre szolgáltatásitárgy-kapcsolatot egy szolgáltatási szerződéshez</span><span class="sxs-lookup"><span data-stu-id="59a21-107">Create a service object relation for a service agreement</span></span>

<span data-ttu-id="59a21-108">Kövesse az alábbi lépéseket egy szolgáltatási szerződéshez tartozó szolgáltatásitárgy-kapcsolat létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="59a21-108">Use the following steps to create a service object relation for a service agreement:</span></span>

1.  <span data-ttu-id="59a21-109">Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="59a21-109">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="59a21-110">A **Szolgáltatási szerződések** listából válasszon ki egy létező szolgáltatási szerződést, vagy kattintson az **Új** lehetőségre egy új szolgáltatási szerződés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="59a21-110">In the **Service agreements** list, select an existing service agreement, or click **New** to create a new service agreement.</span></span>

3.  <span data-ttu-id="59a21-111">A **Műveleti ablaktáblán**, a **Szolgáltatási szerződések** képernyőn, a **Szolgáltatási szerződés** fülön, a **Kapcsolatok** csoportban kattintson a **Szolgáltatási tárgyak** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="59a21-111">In the **Service agreements** form, on the **Action Pane**, on the **Service agreement** tab, in the **Relations** group, click **Service objects**.</span></span>

4.  <span data-ttu-id="59a21-112">Válassza ki a szolgáltatási megállapodáshoz tartozó szolgáltatási tárgyat a **Szolgáltatási tárgyak** képernyőn található **Új** parancsra kattintva.</span><span class="sxs-lookup"><span data-stu-id="59a21-112">In the **Service objects** form, click **New**, and then select a service object for this service agreement.</span></span>

5.  <span data-ttu-id="59a21-113">Ha csatolni szeretne egy anyagjegyzék-sablont a szolgáltatási szerződéshez, kattintson a **Funkciók** menüpontra, és kattintson a **Sablonanyagjegyzék csatolása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="59a21-113">To assign a template bill of materials (BOM) to the service agreement, click **Functions**, and then select **Attach template BOM**.</span></span> <span data-ttu-id="59a21-114">A **Sablon AJ kiválasztása** ablakban található **Sablon AJ** mezőben válassza ki a megfelelő sablont.</span><span class="sxs-lookup"><span data-stu-id="59a21-114">In the **Select template BOM** form, in the **Template BOM** field, select a template.</span></span> 

## <a name="create-a-service-object-relation-for-a-service-order"></a><span data-ttu-id="59a21-115">Hozzon létre szolgáltatásitárgy-kapcsolatot egy szervizrendeléshez</span><span class="sxs-lookup"><span data-stu-id="59a21-115">Create a service object relation for a service order</span></span>

<span data-ttu-id="59a21-116">Kövesse az alábbi lépéseket egy szervizrendeléshez tartozó szolgáltatásitárgy-kapcsolat létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="59a21-116">Use the following steps to create a service object relation for a service order:</span></span>

1.  <span data-ttu-id="59a21-117">Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.</span><span class="sxs-lookup"><span data-stu-id="59a21-117">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="59a21-118">Válasszon ki egy meglévő szervizrendelést a **Szervizrendelések** listáról, vagy hozzon létre egy új szervizrendelést.</span><span class="sxs-lookup"><span data-stu-id="59a21-118">In the **Service orders** list, select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="59a21-119">A **Műveleti ablaktáblán**, a **Szervizrendelések** képernyőn, a **Szervizrendelés** fülön, a **Kapcsolatok** csoportban kattintson a **Szolgáltatási tárgyak** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="59a21-119">In the **Service orders** form, on the **Action Pane**, on the **Service order** tab, in the **Relations** group, click **Service objects**.</span></span>

4.  <span data-ttu-id="59a21-120">Válassza ki a szervizrendeléshez tartozó szolgáltatási tárgyat a **Szolgáltatási tárgyak** képernyőn található **Új** parancsra kattintva.</span><span class="sxs-lookup"><span data-stu-id="59a21-120">In the **Service objects** form, click **New**, and then select a service object for this service order.</span></span>

5.  <span data-ttu-id="59a21-121">Ha csatolni szeretne egy AJ-sablont a szolgáltatási szerződéshez, kattintson a **Funkciók** menüpontra, és kattintson a **Sablonanyagjegyzék csatolása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="59a21-121">To assign a template BOM to the service agreement, click **Functions**, and then select **Attach template BOM**.</span></span> <span data-ttu-id="59a21-122">A **Sablon AJ kiválasztása** ablakban található **Sablon AJ** mezőben válassza ki a megfelelő sablont.</span><span class="sxs-lookup"><span data-stu-id="59a21-122">In the **Select template BOM** form, in the **Template BOM** field, select a template.</span></span> 


## <a name="see-also"></a><span data-ttu-id="59a21-123">Lásd még</span><span class="sxs-lookup"><span data-stu-id="59a21-123">See also</span></span>

[<span data-ttu-id="59a21-124">Szolgáltatási tárgyak áttekintése</span><span class="sxs-lookup"><span data-stu-id="59a21-124">Service objects overview</span></span>](service-objects.md)

[<span data-ttu-id="59a21-125">A szolgáltatás tárgyának kapcsolatai</span><span class="sxs-lookup"><span data-stu-id="59a21-125">Service object relations</span></span>](service-object-relations.md)

[<span data-ttu-id="59a21-126">Sablonanyagjegyzékek</span><span class="sxs-lookup"><span data-stu-id="59a21-126">Template BOMs</span></span>](template-boms.md)

  


