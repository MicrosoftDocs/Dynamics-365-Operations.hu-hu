---
title: Anyagjegyzék-verzió alábontása
description: Ez a cikk egy anyagjegyzék-verzió alábontásának alaptervezési forgatókönyvét ismerteti.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f3c800d96805df38a2e31018f2d6c305e3ed7da
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564577"
---
# <a name="explosion-of-a-bom-version"></a><span data-ttu-id="f3c5d-103">Anyagjegyzék-verzió alábontása</span><span class="sxs-lookup"><span data-stu-id="f3c5d-103">Explosion of a BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f3c5d-104">Ez a cikk egy anyagjegyzék-verzió alábontásának alaptervezési forgatókönyvét ismerteti.</span><span class="sxs-lookup"><span data-stu-id="f3c5d-104">This article explains a master planning scenario that involves explosion of a bill of materials (BOM) version.</span></span>

<span data-ttu-id="f3c5d-105">Egy anyagjegyzék-verzió igényalábontása létrehoz egy igényt minden anyagjegyzéksor-cikkhez egy adott telephelyen, esetleg egy adott raktárban.</span><span class="sxs-lookup"><span data-stu-id="f3c5d-105">A demand explosion of a bill of materials (BOM) version creates a demand for each BOM line item at a specific site and, possibly, at a specific warehouse.</span></span> <span data-ttu-id="f3c5d-106">Egy telephely-specifikus anyagjegyzékben egy adott raktár határozható meg minden anyagjegyzék-sorhoz.</span><span class="sxs-lookup"><span data-stu-id="f3c5d-106">In a site-specific BOM, a specific warehouse can be defined for each BOM line.</span></span> <span data-ttu-id="f3c5d-107">Továbbá minden anyagjegyzék-sorhoz a cikk dimenzióbeállításai meghatározzák, hogy a raktár szükséges-e.</span><span class="sxs-lookup"><span data-stu-id="f3c5d-107">Additionally, for each BOM line, the item's dimension settings determine whether the warehouse is required.</span></span> <span data-ttu-id="f3c5d-108">Az egyes anyagjegyzékcikk-sorokhoz megjelenő igény ezután a további igényalábontás kezdőpontja lesz.</span><span class="sxs-lookup"><span data-stu-id="f3c5d-108">The resulting demand for each BOM line item then becomes the starting point for additional demand explosion.</span></span> <span data-ttu-id="f3c5d-109">Ez az alaptervezési eset a következő feltételeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="f3c5d-109">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="f3c5d-110">A telephely dimenzió kötelező, és meg kell adni az igénytranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="f3c5d-110">The site dimension is mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="f3c5d-111">A hely dimenzió konzisztens.</span><span class="sxs-lookup"><span data-stu-id="f3c5d-111">The site dimension is consistent.</span></span> <span data-ttu-id="f3c5d-112">Az alsóbb szintű igények telephelye megegyezik a kiinduló igénytranzakció telephelyével.</span><span class="sxs-lookup"><span data-stu-id="f3c5d-112">Therefore, the site for lower-level demand is the same as the site on the initial demand transaction.</span></span>

<span data-ttu-id="f3c5d-113">A következő ábra mutatja az alaptervezési igényalábontás folyamatát.</span><span class="sxs-lookup"><span data-stu-id="f3c5d-113">The following illustration shows how the process for master planning demand explosion.</span></span> ![Alábontás igénylése az anyagjegyzék-verzió használatával](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="additional-resources"></a><span data-ttu-id="f3c5d-115">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f3c5d-115">Additional resources</span></span>
--------

[<span data-ttu-id="f3c5d-116">Alaptervezés - anyagjegyzék verzió meghatározása</span><span class="sxs-lookup"><span data-stu-id="f3c5d-116">Master planning - how the BOM version is determined</span></span>](master-plan-bom-version-determined.md)

[<span data-ttu-id="f3c5d-117">Az alaptervezés és a többhelyes funkció</span><span class="sxs-lookup"><span data-stu-id="f3c5d-117">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)



