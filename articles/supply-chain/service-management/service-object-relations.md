---
title: A szolgáltatás tárgyának kapcsolatai
description: A szolgáltatásitárgy-kapcsolatokat egy szolgáltatási tárgy és egy szolgáltatási szerződés vagy szervizrendelés között lehet létrehozni.
author: ShylaThompson
manager: tfehr
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectRelation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c196a070d1e18b2cc14c54eda0fe0aad5346d93
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215125"
---
# <a name="service-object-relations"></a><span data-ttu-id="efad4-103">A szolgáltatás tárgyának kapcsolatai</span><span class="sxs-lookup"><span data-stu-id="efad4-103">Service object relations</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="efad4-104">A szolgáltatásitárgy-kapcsolatokat egy szolgáltatási tárgy és egy szolgáltatási szerződés vagy szervizrendelés között lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="efad4-104">You can create service object relations between a service object and a service agreement or service order.</span></span> <span data-ttu-id="efad4-105">Ehhez a kapcsolat létrehozásakor csatolni kell a szolgáltatási tárgyat a szolgáltatási szerződéshez vagy a szervizrendeléshez.</span><span class="sxs-lookup"><span data-stu-id="efad4-105">When you create a relation, you attach the service object to the service agreement or service order.</span></span>

<span data-ttu-id="efad4-106">Amikor létrejött a kapcsolat, csatolhatja a szolgáltatási tárgyat a szolgáltatási szerződés vagy a szervizrendelés bármelyik sorához.</span><span class="sxs-lookup"><span data-stu-id="efad4-106">After the relation is created, you can attach the service object to any lines on the service agreement or service order.</span></span>

## <a name="template-boms"></a><span data-ttu-id="efad4-107">Sablonanyagjegyzékek</span><span class="sxs-lookup"><span data-stu-id="efad4-107">Template BOMs</span></span>

<span data-ttu-id="efad4-108">A tárgykapcsolathoz sablonanyagjegyzék is megadható.</span><span class="sxs-lookup"><span data-stu-id="efad4-108">You can also specify a template BOM for the object relation.</span></span> <span data-ttu-id="efad4-109">A sablonanyagjegyzék annak a tárgynak az anyagjegyzéke, amelyen a szolgáltatást végzik.</span><span class="sxs-lookup"><span data-stu-id="efad4-109">The template BOM is a bill of materials for the object on which you perform service.</span></span> <span data-ttu-id="efad4-110">Ha egy szervizlátogatás alkalmával kicseréli egy szolgáltatási tárgy egy alkatrészét, akkor ez a módosítás A szolgáltatás tárgyai képernyő segítségével regisztrálható a szolgáltatási anyagjegyzékben.</span><span class="sxs-lookup"><span data-stu-id="efad4-110">If you replace a component part of the service object during a service visit, you can register this change in the service BOM by using the Service objects form.</span></span>

## <a name="example"></a><span data-ttu-id="efad4-111">Példa</span><span class="sxs-lookup"><span data-stu-id="efad4-111">Example</span></span>

<span data-ttu-id="efad4-112">Létrehoz egy szolgáltatási szerződést, amelynek értelmében Ön szervizel két liftet egy vevő telephelyén.</span><span class="sxs-lookup"><span data-stu-id="efad4-112">You create a service agreement for servicing two elevators at a customer site.</span></span>
<span data-ttu-id="efad4-113">A szolgáltatás szerződés azonosítója ID SAL-001.</span><span class="sxs-lookup"><span data-stu-id="efad4-113">The service agreement has the identifier ID SAL-001.</span></span>

<span data-ttu-id="efad4-114">A lifteket létrehozta tárgyként A szolgáltatás tárgyai képernyőn, az EL-S/1000 és az EL-L/1000 kóddal.</span><span class="sxs-lookup"><span data-stu-id="efad4-114">The elevators are set up in the Service objects form as objects, EL-S/1000 and EL-L/1000.</span></span>

<span data-ttu-id="efad4-115">A tárgyakat (EL-S/1000 és EL-L/1000) csatolta a szolgáltatási szerződéshez.</span><span class="sxs-lookup"><span data-stu-id="efad4-115">You attach the service objects, EL-S/1000 and EL-L/1000, to the service agreement.</span></span>

<span data-ttu-id="efad4-116">Módosításokat kíván regisztrálni a szolgáltatási tárgy anyagjegyzékében, ugyanis kicserélték a tárgy egyes alkatrészeit. Ezért egy szolgáltatási anyagjegyzéket csatol a szolgáltatásitárgy-kapcsolathoz, amint azt a következő táblázat ismerteti.</span><span class="sxs-lookup"><span data-stu-id="efad4-116">You want to register changes in the BOM for the service object as you replace component parts of the object, so you attach a service BOM to the service object relation, as described in the following table.</span></span>

| <span data-ttu-id="efad4-117">A szolgáltatás tárgya</span><span class="sxs-lookup"><span data-stu-id="efad4-117">Service object</span></span> | <span data-ttu-id="efad4-118">Kapcsolat – szolgáltatási szerződés</span><span class="sxs-lookup"><span data-stu-id="efad4-118">Relation – Service agreement</span></span> | <span data-ttu-id="efad4-119">Szolgáltatási anyagjegyzék</span><span class="sxs-lookup"><span data-stu-id="efad4-119">Service BOM</span></span>   |
|----------------|------------------------------|---------------|
| <span data-ttu-id="efad4-120">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="efad4-120">EL-S/1000</span></span>      | <span data-ttu-id="efad4-121">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="efad4-121">ID SAL-001</span></span>                   | <span data-ttu-id="efad4-122">BOM-EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="efad4-122">BOM-EL-S/1000</span></span> |
| <span data-ttu-id="efad4-123">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="efad4-123">EL-L/1000</span></span>      | <span data-ttu-id="efad4-124">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="efad4-124">ID SAL-001</span></span>                   | <span data-ttu-id="efad4-125">BOM-EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="efad4-125">BOM-EL-L/1000</span></span> |

<span data-ttu-id="efad4-126">A szerződésnek vannak szolgáltatásitárgy-kapcsolatai, ezért létrehozhatók az ezeket a tárgyakat tartalmazó szolgáltatásiszerződés-sorok, amint a következő táblázatban megjelenik.</span><span class="sxs-lookup"><span data-stu-id="efad4-126">Because there are service object relations for the agreement, you can now create service agreement lines with these objects, as shown in the following table.</span></span>

| <span data-ttu-id="efad4-127">Tranzakció típusa</span><span class="sxs-lookup"><span data-stu-id="efad4-127">Transaction type</span></span> | <span data-ttu-id="efad4-128">Kategória</span><span class="sxs-lookup"><span data-stu-id="efad4-128">Category</span></span>           | <span data-ttu-id="efad4-129">A szolgáltatás tárgya</span><span class="sxs-lookup"><span data-stu-id="efad4-129">Service object</span></span> |
|------------------|--------------------|----------------|
| <span data-ttu-id="efad4-130">Óra</span><span class="sxs-lookup"><span data-stu-id="efad4-130">Hour</span></span>             | <span data-ttu-id="efad4-131">Vizsgálat</span><span class="sxs-lookup"><span data-stu-id="efad4-131">Inspection</span></span>         | <span data-ttu-id="efad4-132">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="efad4-132">EL-S/1000</span></span>      |
| <span data-ttu-id="efad4-133">Óra</span><span class="sxs-lookup"><span data-stu-id="efad4-133">Hour</span></span>             | <span data-ttu-id="efad4-134">Fogaskerekek tisztítása</span><span class="sxs-lookup"><span data-stu-id="efad4-134">Gear box cleaning</span></span>  | <span data-ttu-id="efad4-135">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="efad4-135">EL-S/1000</span></span>      |
| <span data-ttu-id="efad4-136">Cikk</span><span class="sxs-lookup"><span data-stu-id="efad4-136">Item</span></span>             | <span data-ttu-id="efad4-137">Tisztítóanyagok</span><span class="sxs-lookup"><span data-stu-id="efad4-137">Cleaning materials</span></span> | <span data-ttu-id="efad4-138">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="efad4-138">EL-S/1000</span></span>      |
| <span data-ttu-id="efad4-139">Óra</span><span class="sxs-lookup"><span data-stu-id="efad4-139">Hour</span></span>             | <span data-ttu-id="efad4-140">Vizsgálat</span><span class="sxs-lookup"><span data-stu-id="efad4-140">Inspection</span></span>         | <span data-ttu-id="efad4-141">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="efad4-141">EL-L/1000</span></span>      |
| <span data-ttu-id="efad4-142">Óra</span><span class="sxs-lookup"><span data-stu-id="efad4-142">Hour</span></span>             | <span data-ttu-id="efad4-143">Fogaskerekek tisztítása</span><span class="sxs-lookup"><span data-stu-id="efad4-143">Gearbox cleaning</span></span>   | <span data-ttu-id="efad4-144">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="efad4-144">EL-L/1000</span></span>      |
| <span data-ttu-id="efad4-145">Cikk</span><span class="sxs-lookup"><span data-stu-id="efad4-145">Item</span></span>             | <span data-ttu-id="efad4-146">Tisztítóanyagok</span><span class="sxs-lookup"><span data-stu-id="efad4-146">Cleaning materials</span></span> | <span data-ttu-id="efad4-147">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="efad4-147">EL-L/1000</span></span>      |

<span data-ttu-id="efad4-148">Egy szervizlátogatás alkalmával ki kell cserélni az EL-S/1000 kódú lift fogaskerekeit.</span><span class="sxs-lookup"><span data-stu-id="efad4-148">On a service visit, you have to replace the gearbox for elevator EL-S/1000.</span></span> <span data-ttu-id="efad4-149">Ha ki kell cserélnie a tárgy egy alkatrészét, megnyithatja az Anyagjegyzék-tervezőt az aktuális szolgáltatási szerződés szolgáltatásitárgy-kapcsolata segítségével.</span><span class="sxs-lookup"><span data-stu-id="efad4-149">To replace a component part of the object, you can access the BOM Designer by using the service object relation that you set up for the current service agreement.</span></span>

<span data-ttu-id="efad4-150">Az Anyagjegyzék-tervező megnyitása egy szolgáltatásitárgy-kapcsolat segítségével.</span><span class="sxs-lookup"><span data-stu-id="efad4-150">Access the BOM Designer by using a service object relation</span></span>

1. <span data-ttu-id="efad4-151">Szolgáltatási szerződések</span><span class="sxs-lookup"><span data-stu-id="efad4-151">Service agreements</span></span>
2. <span data-ttu-id="efad4-152">Kattintson duplán egy szolgáltatási szerződésre, vagy kattintson a Szolgáltatási szerződés lehetőségre új szolgáltatási szerződés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="efad4-152">Double-click a service agreement, or click Service agreement to create a service agreement.</span></span>
3. <span data-ttu-id="efad4-153">Kattintson a Beállítás fülre.</span><span class="sxs-lookup"><span data-stu-id="efad4-153">Click the Setup tab.</span></span>
4. <span data-ttu-id="efad4-154">Ha csatolni szeretne egy sablonanyagjegyzéket a szolgáltatási szerződéshez, kattintson A szolgáltatás tárgyai elemre.</span><span class="sxs-lookup"><span data-stu-id="efad4-154">Click Service objects to attach a template BOM to the service agreement.</span></span>
5. <span data-ttu-id="efad4-155">A szolgáltatás tárgyai képernyőn kattintson a Tervező lehetőségre a Tervező megnyitásához a sablon anyagjegyzék módosításához.</span><span class="sxs-lookup"><span data-stu-id="efad4-155">In the Service objects form, click Designer to open the Designer form to modify the template BOM.</span></span>

## <a name="automatically-created-service-orders"></a><span data-ttu-id="efad4-156">Automatikusan létrehozott szervizrendelések</span><span class="sxs-lookup"><span data-stu-id="efad4-156">Automatically created service orders</span></span>

<span data-ttu-id="efad4-157">Ha automatikusan hoz létre szervizrendeléseket egy szolgáltatási szerződéshez, a szerződés szolgáltatásitárgy-kapcsolatai átkerülnek a létrehozott szervizrendelésekbe is.</span><span class="sxs-lookup"><span data-stu-id="efad4-157">If you automatically create service orders for a service agreement, the service object relations in the agreement are also created in the service orders.</span></span>

