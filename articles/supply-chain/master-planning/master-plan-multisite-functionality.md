---
title: Az alaptervezés és a többhelyes funkció áttekintése
description: Az Alaptervezés figyelembe veszi a webhely beállításait és a raktár készletdimenziót.
author: roxanadiaconu
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f05e3efd1716a27a659ae40145f37bb0b3d977f
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2019
ms.locfileid: "1865404"
---
# <a name="master-planning-and-multisite-functionality-overview"></a><span data-ttu-id="c57c5-103">Az alaptervezés és a többhelyes funkció áttekintése</span><span class="sxs-lookup"><span data-stu-id="c57c5-103">Master planning and multisite functionality overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c57c5-104">Az Alaptervezés figyelembe veszi a webhely beállításait és a raktár készletdimenziót.</span><span class="sxs-lookup"><span data-stu-id="c57c5-104">Master planning takes the settings of the site and warehouse inventory dimensions into account.</span></span> 

<span data-ttu-id="c57c5-105">A hely dimenzió kötelező és beállíthatja, hogy a raktárdimenzió is kötelező legyen.</span><span class="sxs-lookup"><span data-stu-id="c57c5-105">The site dimension is mandatory, and you can set the warehouse dimension to be mandatory.</span></span>

<span data-ttu-id="c57c5-106">Amikor egy dimenzió kötelező, akkor a dimenzióértéket minden készlettranzakció esetén meg kell adni.</span><span class="sxs-lookup"><span data-stu-id="c57c5-106">When a dimension is mandatory, a dimension value must be entered on all inventory transactions.</span></span> <span data-ttu-id="c57c5-107">Tehát az alaptervezés ideje alatt a telephely és a raktár ismert a kezdeti igényhez.</span><span class="sxs-lookup"><span data-stu-id="c57c5-107">Therefore, during master planning, the site and the warehouse for the initial demand are known.</span></span> <span data-ttu-id="c57c5-108">A helydimenzió konzisztens is, tehát az alacsonyabb rendű igény során történő alábontáskor az értéke nem fog változni.</span><span class="sxs-lookup"><span data-stu-id="c57c5-108">The site dimension is also consistent so that during the explosion of lower-level demand, the site value does not change.</span></span>

<span data-ttu-id="c57c5-109">Ha a raktár megadása nem kötelező, akkor előfordulhat, hogy a kezdeti igényből nem határozható meg a raktár.</span><span class="sxs-lookup"><span data-stu-id="c57c5-109">When the warehouse is not set to mandatory, it may not be known from the initial demand.</span></span> <span data-ttu-id="c57c5-110">A tervezőmotornak ilyenkor a cikkre, az egyes raktárakra, valamint a rendeléssorra meghatározott beállítások alapján kell meghatároznia, hogy melyik raktárat használja.</span><span class="sxs-lookup"><span data-stu-id="c57c5-110">The planning engine must determine which warehouse to use based on the settings that are defined for the item, individual warehouses, and the details of the order line.</span></span>

<span data-ttu-id="c57c5-111">A következő témakörök bemutatják, hogy hogyan határozza meg a tervezőmotor a raktárat különböző beállításoknál.</span><span class="sxs-lookup"><span data-stu-id="c57c5-111">The following topics describe how the planning engine works, when different settings are defined, to determine the warehouse to use.</span></span>

[<span data-ttu-id="c57c5-112">Alaptervezés - hely és raktár fedezet, a raktár kötelező</span><span class="sxs-lookup"><span data-stu-id="c57c5-112">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="c57c5-113">Alaptervezés - helyfedezet, a raktár kötelező</span><span class="sxs-lookup"><span data-stu-id="c57c5-113">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="c57c5-114">Alaptervezés - hely és raktár fedezet, a raktár nem kötelező</span><span class="sxs-lookup"><span data-stu-id="c57c5-114">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="c57c5-115">Alaptervezés - helyfedezet, a raktár nem kötelező</span><span class="sxs-lookup"><span data-stu-id="c57c5-115">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="c57c5-116">Alaptervezés - Anyagjegyzék verzió meghatározása</span><span class="sxs-lookup"><span data-stu-id="c57c5-116">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)



