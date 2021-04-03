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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 82e25c162a33dd8e6e1a0cc4f215a8693fc1080b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5266055"
---
# <a name="service-object-relations"></a><span data-ttu-id="eb019-103">A szolgáltatás tárgyának kapcsolatai</span><span class="sxs-lookup"><span data-stu-id="eb019-103">Service object relations</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eb019-104">A szolgáltatásitárgy-kapcsolatokat egy szolgáltatási tárgy és egy szolgáltatási szerződés vagy szervizrendelés között lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="eb019-104">You can create service object relations between a service object and a service agreement or service order.</span></span> <span data-ttu-id="eb019-105">Ehhez a kapcsolat létrehozásakor csatolni kell a szolgáltatási tárgyat a szolgáltatási szerződéshez vagy a szervizrendeléshez.</span><span class="sxs-lookup"><span data-stu-id="eb019-105">When you create a relation, you attach the service object to the service agreement or service order.</span></span>

<span data-ttu-id="eb019-106">Amikor létrejött a kapcsolat, csatolhatja a szolgáltatási tárgyat a szolgáltatási szerződés vagy a szervizrendelés bármelyik sorához.</span><span class="sxs-lookup"><span data-stu-id="eb019-106">After the relation is created, you can attach the service object to any lines on the service agreement or service order.</span></span>

## <a name="template-boms"></a><span data-ttu-id="eb019-107">Sablonanyagjegyzékek</span><span class="sxs-lookup"><span data-stu-id="eb019-107">Template BOMs</span></span>

<span data-ttu-id="eb019-108">A tárgykapcsolathoz sablonanyagjegyzék is megadható.</span><span class="sxs-lookup"><span data-stu-id="eb019-108">You can also specify a template BOM for the object relation.</span></span> <span data-ttu-id="eb019-109">A sablonanyagjegyzék annak a tárgynak az anyagjegyzéke, amelyen a szolgáltatást végzik.</span><span class="sxs-lookup"><span data-stu-id="eb019-109">The template BOM is a bill of materials for the object on which you perform service.</span></span> <span data-ttu-id="eb019-110">Ha egy szervizlátogatás alkalmával kicseréli egy szolgáltatási tárgy egy alkatrészét, akkor ez a módosítás A szolgáltatás tárgyai képernyő segítségével regisztrálható a szolgáltatási anyagjegyzékben.</span><span class="sxs-lookup"><span data-stu-id="eb019-110">If you replace a component part of the service object during a service visit, you can register this change in the service BOM by using the Service objects form.</span></span>

## <a name="example"></a><span data-ttu-id="eb019-111">Példa</span><span class="sxs-lookup"><span data-stu-id="eb019-111">Example</span></span>

<span data-ttu-id="eb019-112">Létrehoz egy szolgáltatási szerződést, amelynek értelmében Ön szervizel két liftet egy vevő telephelyén.</span><span class="sxs-lookup"><span data-stu-id="eb019-112">You create a service agreement for servicing two elevators at a customer site.</span></span>
<span data-ttu-id="eb019-113">A szolgáltatás szerződés azonosítója ID SAL-001.</span><span class="sxs-lookup"><span data-stu-id="eb019-113">The service agreement has the identifier ID SAL-001.</span></span>

<span data-ttu-id="eb019-114">A lifteket létrehozta tárgyként A szolgáltatás tárgyai képernyőn, az EL-S/1000 és az EL-L/1000 kóddal.</span><span class="sxs-lookup"><span data-stu-id="eb019-114">The elevators are set up in the Service objects form as objects, EL-S/1000 and EL-L/1000.</span></span>

<span data-ttu-id="eb019-115">A tárgyakat (EL-S/1000 és EL-L/1000) csatolta a szolgáltatási szerződéshez.</span><span class="sxs-lookup"><span data-stu-id="eb019-115">You attach the service objects, EL-S/1000 and EL-L/1000, to the service agreement.</span></span>

<span data-ttu-id="eb019-116">Módosításokat kíván regisztrálni a szolgáltatási tárgy anyagjegyzékében, ugyanis kicserélték a tárgy egyes alkatrészeit. Ezért egy szolgáltatási anyagjegyzéket csatol a szolgáltatásitárgy-kapcsolathoz, amint azt a következő táblázat ismerteti.</span><span class="sxs-lookup"><span data-stu-id="eb019-116">You want to register changes in the BOM for the service object as you replace component parts of the object, so you attach a service BOM to the service object relation, as described in the following table.</span></span>

| <span data-ttu-id="eb019-117">A szolgáltatás tárgya</span><span class="sxs-lookup"><span data-stu-id="eb019-117">Service object</span></span> | <span data-ttu-id="eb019-118">Kapcsolat – szolgáltatási szerződés</span><span class="sxs-lookup"><span data-stu-id="eb019-118">Relation – Service agreement</span></span> | <span data-ttu-id="eb019-119">Szolgáltatási anyagjegyzék</span><span class="sxs-lookup"><span data-stu-id="eb019-119">Service BOM</span></span>   |
|----------------|------------------------------|---------------|
| <span data-ttu-id="eb019-120">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="eb019-120">EL-S/1000</span></span>      | <span data-ttu-id="eb019-121">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="eb019-121">ID SAL-001</span></span>                   | <span data-ttu-id="eb019-122">BOM-EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="eb019-122">BOM-EL-S/1000</span></span> |
| <span data-ttu-id="eb019-123">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="eb019-123">EL-L/1000</span></span>      | <span data-ttu-id="eb019-124">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="eb019-124">ID SAL-001</span></span>                   | <span data-ttu-id="eb019-125">BOM-EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="eb019-125">BOM-EL-L/1000</span></span> |

<span data-ttu-id="eb019-126">A szerződésnek vannak szolgáltatásitárgy-kapcsolatai, ezért létrehozhatók az ezeket a tárgyakat tartalmazó szolgáltatásiszerződés-sorok, amint a következő táblázatban megjelenik.</span><span class="sxs-lookup"><span data-stu-id="eb019-126">Because there are service object relations for the agreement, you can now create service agreement lines with these objects, as shown in the following table.</span></span>

| <span data-ttu-id="eb019-127">Tranzakció típusa</span><span class="sxs-lookup"><span data-stu-id="eb019-127">Transaction type</span></span> | <span data-ttu-id="eb019-128">Kategória</span><span class="sxs-lookup"><span data-stu-id="eb019-128">Category</span></span>           | <span data-ttu-id="eb019-129">A szolgáltatás tárgya</span><span class="sxs-lookup"><span data-stu-id="eb019-129">Service object</span></span> |
|------------------|--------------------|----------------|
| <span data-ttu-id="eb019-130">Óra</span><span class="sxs-lookup"><span data-stu-id="eb019-130">Hour</span></span>             | <span data-ttu-id="eb019-131">Vizsgálat</span><span class="sxs-lookup"><span data-stu-id="eb019-131">Inspection</span></span>         | <span data-ttu-id="eb019-132">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="eb019-132">EL-S/1000</span></span>      |
| <span data-ttu-id="eb019-133">Óra</span><span class="sxs-lookup"><span data-stu-id="eb019-133">Hour</span></span>             | <span data-ttu-id="eb019-134">Fogaskerekek tisztítása</span><span class="sxs-lookup"><span data-stu-id="eb019-134">Gear box cleaning</span></span>  | <span data-ttu-id="eb019-135">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="eb019-135">EL-S/1000</span></span>      |
| <span data-ttu-id="eb019-136">Cikk</span><span class="sxs-lookup"><span data-stu-id="eb019-136">Item</span></span>             | <span data-ttu-id="eb019-137">Tisztítóanyagok</span><span class="sxs-lookup"><span data-stu-id="eb019-137">Cleaning materials</span></span> | <span data-ttu-id="eb019-138">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="eb019-138">EL-S/1000</span></span>      |
| <span data-ttu-id="eb019-139">Óra</span><span class="sxs-lookup"><span data-stu-id="eb019-139">Hour</span></span>             | <span data-ttu-id="eb019-140">Vizsgálat</span><span class="sxs-lookup"><span data-stu-id="eb019-140">Inspection</span></span>         | <span data-ttu-id="eb019-141">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="eb019-141">EL-L/1000</span></span>      |
| <span data-ttu-id="eb019-142">Óra</span><span class="sxs-lookup"><span data-stu-id="eb019-142">Hour</span></span>             | <span data-ttu-id="eb019-143">Fogaskerekek tisztítása</span><span class="sxs-lookup"><span data-stu-id="eb019-143">Gearbox cleaning</span></span>   | <span data-ttu-id="eb019-144">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="eb019-144">EL-L/1000</span></span>      |
| <span data-ttu-id="eb019-145">Cikk</span><span class="sxs-lookup"><span data-stu-id="eb019-145">Item</span></span>             | <span data-ttu-id="eb019-146">Tisztítóanyagok</span><span class="sxs-lookup"><span data-stu-id="eb019-146">Cleaning materials</span></span> | <span data-ttu-id="eb019-147">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="eb019-147">EL-L/1000</span></span>      |

<span data-ttu-id="eb019-148">Egy szervizlátogatás alkalmával ki kell cserélni az EL-S/1000 kódú lift fogaskerekeit.</span><span class="sxs-lookup"><span data-stu-id="eb019-148">On a service visit, you have to replace the gearbox for elevator EL-S/1000.</span></span> <span data-ttu-id="eb019-149">Ha ki kell cserélnie a tárgy egy alkatrészét, megnyithatja az Anyagjegyzék-tervezőt az aktuális szolgáltatási szerződés szolgáltatásitárgy-kapcsolata segítségével.</span><span class="sxs-lookup"><span data-stu-id="eb019-149">To replace a component part of the object, you can access the BOM Designer by using the service object relation that you set up for the current service agreement.</span></span>

<span data-ttu-id="eb019-150">Az Anyagjegyzék-tervező megnyitása egy szolgáltatásitárgy-kapcsolat segítségével.</span><span class="sxs-lookup"><span data-stu-id="eb019-150">Access the BOM Designer by using a service object relation</span></span>

1. <span data-ttu-id="eb019-151">Szolgáltatási szerződések</span><span class="sxs-lookup"><span data-stu-id="eb019-151">Service agreements</span></span>
2. <span data-ttu-id="eb019-152">Kattintson duplán egy szolgáltatási szerződésre, vagy kattintson a Szolgáltatási szerződés lehetőségre új szolgáltatási szerződés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="eb019-152">Double-click a service agreement, or click Service agreement to create a service agreement.</span></span>
3. <span data-ttu-id="eb019-153">Kattintson a Beállítás fülre.</span><span class="sxs-lookup"><span data-stu-id="eb019-153">Click the Setup tab.</span></span>
4. <span data-ttu-id="eb019-154">Ha csatolni szeretne egy sablonanyagjegyzéket a szolgáltatási szerződéshez, kattintson A szolgáltatás tárgyai elemre.</span><span class="sxs-lookup"><span data-stu-id="eb019-154">Click Service objects to attach a template BOM to the service agreement.</span></span>
5. <span data-ttu-id="eb019-155">A szolgáltatás tárgyai képernyőn kattintson a Tervező lehetőségre a Tervező megnyitásához a sablon anyagjegyzék módosításához.</span><span class="sxs-lookup"><span data-stu-id="eb019-155">In the Service objects form, click Designer to open the Designer form to modify the template BOM.</span></span>

## <a name="automatically-created-service-orders"></a><span data-ttu-id="eb019-156">Automatikusan létrehozott szervizrendelések</span><span class="sxs-lookup"><span data-stu-id="eb019-156">Automatically created service orders</span></span>

<span data-ttu-id="eb019-157">Ha automatikusan hoz létre szervizrendeléseket egy szolgáltatási szerződéshez, a szerződés szolgáltatásitárgy-kapcsolatai átkerülnek a létrehozott szervizrendelésekbe is.</span><span class="sxs-lookup"><span data-stu-id="eb019-157">If you automatically create service orders for a service agreement, the service object relations in the agreement are also created in the service orders.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]