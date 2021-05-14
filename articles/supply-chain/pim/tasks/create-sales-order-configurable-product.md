---
title: Értékesítési rendelés létrehozása konfigurálható termékhez
description: Ez az eljárás azt szemlélteti, hogy hogyan lehet egy konfigurációs sablont alkalmazni egy értékesítési rendelésben szereplő termékre.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8607de5705354aa58c985fb536f3e1d52acd1f37
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921289"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a><span data-ttu-id="80b77-103">Értékesítési rendelés létrehozása konfigurálható termékhez</span><span class="sxs-lookup"><span data-stu-id="80b77-103">Create a sales order for a configurable product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="80b77-104">Ez az eljárás azt szemlélteti, hogy hogyan lehet egy konfigurációs sablont alkalmazni egy értékesítési rendelésben szereplő termékre.</span><span class="sxs-lookup"><span data-stu-id="80b77-104">This procedure shows how to apply a configuration template to a product on a sales order.</span></span> <span data-ttu-id="80b77-105">Ebben a példában a D0006 hangszórómodellt használjuk a USMF bemutatócég esetében.</span><span class="sxs-lookup"><span data-stu-id="80b77-105">This example uses the D0006 speaker model in the USMF demo data company.</span></span> <span data-ttu-id="80b77-106">Ezt az eljárást jellemzően az értékesítésirendelés-feldolgozó használja.</span><span class="sxs-lookup"><span data-stu-id="80b77-106">Typically, a sales order processor uses this procedure.</span></span>

## <a name="create-a-sales-order"></a><span data-ttu-id="80b77-107">Értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="80b77-107">Create a sales order</span></span>

1. <span data-ttu-id="80b77-108">Ugrás az **Értékesítés és marketing \> Munkaterületek \> Értékesítési rendelés feldolgozása és lekérdezése** elemre.</span><span class="sxs-lookup"><span data-stu-id="80b77-108">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="80b77-109">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="80b77-109">Select **New**.</span></span>
1. <span data-ttu-id="80b77-110">Válassza ki az **Értékesítési rendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="80b77-110">Select **Sales order**.</span></span>
1. <span data-ttu-id="80b77-111">A **Vevői számla** mezőben válassza a következőt: *US-001*.</span><span class="sxs-lookup"><span data-stu-id="80b77-111">In the **Customer account** field, select *US-001*.</span></span> 
1. <span data-ttu-id="80b77-112">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="80b77-112">Select **OK**.</span></span>
1. <span data-ttu-id="80b77-113">A **Cikkszám** mezőben válassza ki a *D0006* cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="80b77-113">In the **Item number** field, select *D0006*.</span></span>
    * <span data-ttu-id="80b77-114">Ehhez a feladathoz ki kell választania egy konfigurálható terméket.</span><span class="sxs-lookup"><span data-stu-id="80b77-114">For this task, you must select a configurable product.</span></span>  
1. <span data-ttu-id="80b77-115">Kattintson a **Termék és készlet** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="80b77-115">Select **Product and supply**.</span></span>
1. <span data-ttu-id="80b77-116">Válassza a **Sor konfigurálása** elemet.</span><span class="sxs-lookup"><span data-stu-id="80b77-116">Select **Configure line**.</span></span>
    * <span data-ttu-id="80b77-117">Vegye figyelembe, hogy az ár megváltozott a kiválasztott beállítás alapján, és a **Kábel is a része** mező értéke most már *Igaz*.</span><span class="sxs-lookup"><span data-stu-id="80b77-117">Note that the price has changed, based on the configuration that was selected, and that the **Include cable** field is now set to *True*.</span></span>  
    * <span data-ttu-id="80b77-118">Tekintse meg az alapértelmezett árat és kábelhez kiválasztott beállításokat.</span><span class="sxs-lookup"><span data-stu-id="80b77-118">Note the default price and the settings that are selected for the cable.</span></span>  
1. <span data-ttu-id="80b77-119">Válassza a **Rakománysablon** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="80b77-119">Select **Load template**.</span></span>
    * <span data-ttu-id="80b77-120">Ez a példa azt mutatja be, hogyan alkalmazhat egy sablont egy előre definiált konfiguráció kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="80b77-120">This example shows how you can apply a template to select a predefined configuration.</span></span> <span data-ttu-id="80b77-121">Ha feladat-útmutatóként használja ezt az eljárást, és szeretné megtekinteni a többi rendelkezésre álló attribútumértéket, kattintson a **Feloldás** gombra.</span><span class="sxs-lookup"><span data-stu-id="80b77-121">If you're using this procedure as a task guide and want to see the other attribute values that are available, you must select the **Unlock** button.</span></span>  
1. <span data-ttu-id="80b77-122">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="80b77-122">Select **OK**.</span></span>
1. <span data-ttu-id="80b77-123">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="80b77-123">Select **OK**.</span></span>
1. <span data-ttu-id="80b77-124">Bontsa ki a **Sorrészletek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="80b77-124">Expand the **Line details** section.</span></span>
1. <span data-ttu-id="80b77-125">Válassza ki a **Termék** fület.</span><span class="sxs-lookup"><span data-stu-id="80b77-125">Select the **Product** tab.</span></span>
    * <span data-ttu-id="80b77-126">A cikk konfigurációja most már látható a termék méretei alatt.</span><span class="sxs-lookup"><span data-stu-id="80b77-126">The configuration of the item is now listed under the product dimensions.</span></span>  
1. <span data-ttu-id="80b77-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="80b77-127">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]