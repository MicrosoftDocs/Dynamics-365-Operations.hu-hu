---
title: Értékesítési rendelés létrehozása konfigurálható termékhez
description: Ez az eljárás azt szemlélteti, hogy hogyan lehet egy konfigurációs sablont alkalmazni egy értékesítési rendelésben szereplő termékre.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 988d87757019d20dcaf675af925166ed376685f5
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985485"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a><span data-ttu-id="3f405-103">Értékesítési rendelés létrehozása konfigurálható termékhez</span><span class="sxs-lookup"><span data-stu-id="3f405-103">Create a sales order for a configurable product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3f405-104">Ez az eljárás azt szemlélteti, hogy hogyan lehet egy konfigurációs sablont alkalmazni egy értékesítési rendelésben szereplő termékre.</span><span class="sxs-lookup"><span data-stu-id="3f405-104">This procedure shows how to apply a configuration template to a product on a sales order.</span></span> <span data-ttu-id="3f405-105">Ebben a példában a D0006 hangszórómodellt használjuk a USMF bemutatócég esetében.</span><span class="sxs-lookup"><span data-stu-id="3f405-105">This example uses the D0006 speaker model in the USMF demo data company.</span></span> <span data-ttu-id="3f405-106">Ezt az eljárást jellemzően az értékesítésirendelés-feldolgozó használja.</span><span class="sxs-lookup"><span data-stu-id="3f405-106">Typically, a sales order processor uses this procedure.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="3f405-107">Értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="3f405-107">Create a sales order</span></span>
1. <span data-ttu-id="3f405-108">Kattintson az Értékesítési rendelés feldolgozása és lekérdezése menüpontra.</span><span class="sxs-lookup"><span data-stu-id="3f405-108">Click Sales order processing and inquiry.</span></span>
2. <span data-ttu-id="3f405-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f405-109">Click New.</span></span>
3. <span data-ttu-id="3f405-110">Kattintson az Értékesítési rendelés gombra.</span><span class="sxs-lookup"><span data-stu-id="3f405-110">Click Sales order.</span></span>
4. <span data-ttu-id="3f405-111">A Vevői számla mezőben válassza a következőt: US-001.</span><span class="sxs-lookup"><span data-stu-id="3f405-111">In the Customer account field, select US-001.</span></span> 
5. <span data-ttu-id="3f405-112">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3f405-112">Click OK.</span></span>
6. <span data-ttu-id="3f405-113">A Cikkszám mezőben válassza ki a D0006 értéket.</span><span class="sxs-lookup"><span data-stu-id="3f405-113">In the Item number field, select D0006.</span></span>
    * <span data-ttu-id="3f405-114">Ehhez a feladathoz ki kell választania egy konfigurálható terméket.</span><span class="sxs-lookup"><span data-stu-id="3f405-114">For this task, you must select a configurable product.</span></span>  
7. <span data-ttu-id="3f405-115">Kattintson a Termék és készlet menüpontra.</span><span class="sxs-lookup"><span data-stu-id="3f405-115">Click Product and supply.</span></span>
8. <span data-ttu-id="3f405-116">Kattintson a Sor konfigurálására.</span><span class="sxs-lookup"><span data-stu-id="3f405-116">Click Configure line.</span></span>
    * <span data-ttu-id="3f405-117">Vegye figyelembe, hogy az ár megváltozott a kiválasztott beállítás alapján, és a Kábel is a része mező értéke most már Igaz.</span><span class="sxs-lookup"><span data-stu-id="3f405-117">Note that the price has changed, based on the configuration that was selected, and that the Include cable field is now set to True.</span></span>  
    * <span data-ttu-id="3f405-118">Tekintse meg az alapértelmezett árat és kábelhez kiválasztott beállításokat.</span><span class="sxs-lookup"><span data-stu-id="3f405-118">Note the default price and the settings that are selected for the cable.</span></span>  
9. <span data-ttu-id="3f405-119">Kattintson a Rakománysablonra.</span><span class="sxs-lookup"><span data-stu-id="3f405-119">Click Load template.</span></span>
    * <span data-ttu-id="3f405-120">Ez a példa azt mutatja be, hogyan alkalmazhat egy sablont egy előre definiált konfiguráció kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="3f405-120">This example shows how you can apply a template to select a predefined configuration.</span></span> <span data-ttu-id="3f405-121">Ha feladat-útmutatóként használja ezt az eljárást, és szeretné megtekinteni a többi rendelkezésre álló attribútumértéket, kattintson a Feloldás gombra.</span><span class="sxs-lookup"><span data-stu-id="3f405-121">If you're using this procedure as a task guide and want to see the other attribute values that are available, you must click the Unlock button.</span></span>  
10. <span data-ttu-id="3f405-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3f405-122">Click OK.</span></span>
11. <span data-ttu-id="3f405-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3f405-123">Click OK.</span></span>
12. <span data-ttu-id="3f405-124">Bontsa ki a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="3f405-124">Expand the Line details section.</span></span>
13. <span data-ttu-id="3f405-125">Kattintson a Termék fülre.</span><span class="sxs-lookup"><span data-stu-id="3f405-125">Click the Product tab.</span></span>
    * <span data-ttu-id="3f405-126">A cikk konfigurációja most már látható a termék méretei alatt.</span><span class="sxs-lookup"><span data-stu-id="3f405-126">The configuration of the item is now listed under the product dimensions.</span></span>  
14. <span data-ttu-id="3f405-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3f405-127">Close the page.</span></span>

## <a name="select-the-product-configuration"></a><span data-ttu-id="3f405-128">Válassza ki a termékkonfigurációt.</span><span class="sxs-lookup"><span data-stu-id="3f405-128">Select the product configuration</span></span>

