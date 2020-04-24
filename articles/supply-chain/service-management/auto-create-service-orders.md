---
title: Szervizrendelések automatikus létrehozása
description: A szervizrendelések a szolgáltatási szerződések alapján hozhatók létre a szolgáltatási szerződés érvényességi időtartamán belül.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33de4746b8011f4e7fc0ce2929c967870eeebae9
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203020"
---
# <a name="automatically-create-service-orders"></a><span data-ttu-id="955c4-103">Szervizrendelések automatikus létrehozása</span><span class="sxs-lookup"><span data-stu-id="955c4-103">Automatically create service orders</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="955c4-104">A szervizrendelések a szolgáltatási szerződések alapján hozhatók létre a szolgáltatási szerződés érvényességi időtartamán belül.</span><span class="sxs-lookup"><span data-stu-id="955c4-104">You can generate service orders that are based on a service agreement for the valid period of the service agreement.</span></span>

<span data-ttu-id="955c4-105">A szolgáltatási szerződésből előállított szervizrendelések a szolgáltatási szerződéshez vannak csatolva.</span><span class="sxs-lookup"><span data-stu-id="955c4-105">The service orders that you generate from a service agreement are all attached to the service agreement.</span></span>

<span data-ttu-id="955c4-106">A szervizrendelések a következő beállításokból generálhatók automatikusan:</span><span class="sxs-lookup"><span data-stu-id="955c4-106">Service orders are generated automatically from the following settings:</span></span>

  - <span data-ttu-id="955c4-107">A szolgáltatási szerződés intervalluma, amely a szolgáltatási szerződés soraiban állítható be.</span><span class="sxs-lookup"><span data-stu-id="955c4-107">The service agreement interval that is set up in the service agreement lines.</span></span> <span data-ttu-id="955c4-108">A szolgáltatási szerződés intervalluma a szervizrendelés-sorok létrehozásának gyakoriságát jelzi.</span><span class="sxs-lookup"><span data-stu-id="955c4-108">The service agreement interval indicates the frequency that service-order lines are created.</span></span> <span data-ttu-id="955c4-109">További információkkal kapcsolatban lásd: [Szolgáltatási intervallumok](service-intervals.md).</span><span class="sxs-lookup"><span data-stu-id="955c4-109">For more information, see [Service intervals](service-intervals.md).</span></span>

  - <span data-ttu-id="955c4-110">A szervizintervallumot meghatározó időszak, amely a **Szervizrendelések létrehozása** képernyő **Kezdő dátum** és **Befejezési dátum** mezőjében van megadva.</span><span class="sxs-lookup"><span data-stu-id="955c4-110">The period that you specify to define the service period in the **From date** and **To date** fields in the **Create service orders** form.</span></span> <span data-ttu-id="955c4-111">További információkkal kapcsolatban lásd: [Szervizrendelések automatikus létrehozása](create-service-orders-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="955c4-111">For more information, see [Create service orders automatically](create-service-orders-automatically.md).</span></span>

  - <span data-ttu-id="955c4-112">A **Szervizrendelések kombinálása** beállítás a szolgáltatási szerződés fejlécében.</span><span class="sxs-lookup"><span data-stu-id="955c4-112">The **Combine service orders** option on the service agreement header.</span></span> <span data-ttu-id="955c4-113">Ez az opció azt határozza meg, hogy a szolgáltatási szerződés alapján létrehozott szervizrendelési sorok kombinálják-e a szervizrendeléseket a következőknek megfelelően: munkavállaló, szolgáltatási feladat, szolgáltatási tárgy vagy szolgáltatási szerződés.</span><span class="sxs-lookup"><span data-stu-id="955c4-113">This option defines whether service order lines generated from a service agreement, combines service orders according to employee, service task, service object, or service agreement.</span></span> <span data-ttu-id="955c4-114">További információkkal kapcsolatban lásd: [Szervizrendelések kombinálása](combine-service-orders.md).</span><span class="sxs-lookup"><span data-stu-id="955c4-114">For more information, see [Combine service orders](combine-service-orders.md).</span></span>

  - <span data-ttu-id="955c4-115">Az **Időablak** beállítás a szolgáltatási szerződési soron.</span><span class="sxs-lookup"><span data-stu-id="955c4-115">The **Time window** option on the service agreement line.</span></span> <span data-ttu-id="955c4-116">Az időablak meghatározza, hogy milyen távol kerülhetnek a szervizrendeléssorok a számított dátumukhoz képest.</span><span class="sxs-lookup"><span data-stu-id="955c4-116">The time window defines how far a service order line can move with regard to its calculated date.</span></span> <span data-ttu-id="955c4-117">További információkkal kapcsolatban lásd: [Időablakok](time-windows.md).</span><span class="sxs-lookup"><span data-stu-id="955c4-117">For more information, see [Time windows](time-windows.md).</span></span>


> [!NOTE]
> <P><span data-ttu-id="955c4-118">Ha a szervizrendelés számára megadott nap nincs megnyitva a naptárban, amelyet a <STRONG>Szolgáltatáskezelés paraméterei</STRONG> képernyőn kiválasztott, akkor egy üzenetet kap, amely jelzi a dátumok ütközését.</span><span class="sxs-lookup"><span data-stu-id="955c4-118">If the day that is specified for a service order is not open in the calendar that you have selected in the <STRONG>Service management parameters</STRONG> form, a message will indicate that there is a calendar conflict.</span></span> <span data-ttu-id="955c4-119">Az üzenetet nyugodtan figyelmen kívül hagyhatja; a szervizrendelés akkor is létrejön, ha a nap le van zárva a naptárban.</span><span class="sxs-lookup"><span data-stu-id="955c4-119">You can safely ignore the message; the service order will be created, even though the day is closed on the calendar.</span></span></P>

## <a name="example-1"></a><span data-ttu-id="955c4-120">1. példa</span><span class="sxs-lookup"><span data-stu-id="955c4-120">Example 1</span></span>

<span data-ttu-id="955c4-121">A szolgáltatási szerződés 2012. január 1-től 2012. december 31-ig tart.</span><span class="sxs-lookup"><span data-stu-id="955c4-121">The service agreement lasts from January 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="955c4-122">Ha a **Szervizrendelések létrehozása** képernyőn létrehozott szolgáltatási időszak 2012. november 1-től 2013 február 1-ig tart, a szervizrendelések 2012. november 1-től 2012. december 31-ig jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="955c4-122">If the service period that you specify in the **Create service orders** form is from November 1, 2012 until February 1, 2013, service orders are created from November 1, 2012 until December 31, 2012.</span></span>

## <a name="example-2"></a><span data-ttu-id="955c4-123">2. példa</span><span class="sxs-lookup"><span data-stu-id="955c4-123">Example 2</span></span>

<span data-ttu-id="955c4-124">A szolgáltatási szerződés 2012. január 1-től 2012. december 31-ig tart.</span><span class="sxs-lookup"><span data-stu-id="955c4-124">The service agreement lasts from January 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="955c4-125">A szolgáltatási szerződéshez két szolgáltatásiszerződés-sor kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="955c4-125">Two service agreement lines are attached to the service agreement.</span></span> <span data-ttu-id="955c4-126">Az első szolgáltatásiszerződés-sor kezdési dátuma 2012. január 2. és a záró dátuma 2012. március 1.</span><span class="sxs-lookup"><span data-stu-id="955c4-126">The first service agreement line has a starting date on January 2, 2012 and an ending date on March 1, 2012.</span></span> <span data-ttu-id="955c4-127">A második szolgáltatásiszerződés-sor kezdési dátuma 2012. április 1. és a záró dátuma 2012. december 31.</span><span class="sxs-lookup"><span data-stu-id="955c4-127">The second service agreement line has a starting date on April 1, 2012 and an ending date on December 31, 2012.</span></span> <span data-ttu-id="955c4-128">Megadhatja az időszakot a **Szervizrendelések létrehozása** képernyőn, amely 2012. október 1-től 2012. december 31-ig tart.</span><span class="sxs-lookup"><span data-stu-id="955c4-128">You specify a period in the **Create service orders** form that is from October 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="955c4-129">Ennek megfelelően a szervizrendelések csak a második szolgáltatásiszerződés-sorhoz jönnek létre, mert az első szolgáltatásiszerződés-sor kezdési és a befejezési dátuma a szervizrendeléshez megadott időszak előtt van.</span><span class="sxs-lookup"><span data-stu-id="955c4-129">Therefore, service orders are generated only for the second agreement line, because the starting date and ending date of the first agreement line are before the period that you specified for the service order.</span></span>

  


