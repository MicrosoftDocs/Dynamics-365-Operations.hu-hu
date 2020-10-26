---
title: Anyagjegyzék-verzió alábontása
description: Ez a cikk egy anyagjegyzék-verzió alábontásának alaptervezési forgatókönyvét ismerteti.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 482c036294f525be5db1dc6efefe76a9ba5b3ce5
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983695"
---
# <a name="explosion-of-a-bom-version"></a><span data-ttu-id="dafa9-103">Anyagjegyzék-verzió alábontása</span><span class="sxs-lookup"><span data-stu-id="dafa9-103">Explosion of a BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dafa9-104">Ez a cikk egy anyagjegyzék-verzió alábontásának alaptervezési forgatókönyvét ismerteti.</span><span class="sxs-lookup"><span data-stu-id="dafa9-104">This article explains a master planning scenario that involves explosion of a bill of materials (BOM) version.</span></span>

<span data-ttu-id="dafa9-105">Egy anyagjegyzék-verzió igényalábontása létrehoz egy igényt minden anyagjegyzéksor-cikkhez egy adott telephelyen, esetleg egy adott raktárban.</span><span class="sxs-lookup"><span data-stu-id="dafa9-105">A demand explosion of a bill of materials (BOM) version creates a demand for each BOM line item at a specific site and, possibly, at a specific warehouse.</span></span> <span data-ttu-id="dafa9-106">Egy telephely-specifikus anyagjegyzékben egy adott raktár határozható meg minden anyagjegyzék-sorhoz.</span><span class="sxs-lookup"><span data-stu-id="dafa9-106">In a site-specific BOM, a specific warehouse can be defined for each BOM line.</span></span> <span data-ttu-id="dafa9-107">Továbbá minden anyagjegyzék-sorhoz a cikk dimenzióbeállításai meghatározzák, hogy a raktár szükséges-e.</span><span class="sxs-lookup"><span data-stu-id="dafa9-107">Additionally, for each BOM line, the item's dimension settings determine whether the warehouse is required.</span></span> <span data-ttu-id="dafa9-108">Az egyes anyagjegyzékcikk-sorokhoz megjelenő igény ezután a további igényalábontás kezdőpontja lesz.</span><span class="sxs-lookup"><span data-stu-id="dafa9-108">The resulting demand for each BOM line item then becomes the starting point for additional demand explosion.</span></span> <span data-ttu-id="dafa9-109">Ez az alaptervezési eset a következő feltételeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="dafa9-109">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="dafa9-110">A telephely dimenzió kötelező, és meg kell adni az igénytranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="dafa9-110">The site dimension is mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="dafa9-111">A hely dimenzió konzisztens.</span><span class="sxs-lookup"><span data-stu-id="dafa9-111">The site dimension is consistent.</span></span> <span data-ttu-id="dafa9-112">Az alsóbb szintű igények telephelye megegyezik a kiinduló igénytranzakció telephelyével.</span><span class="sxs-lookup"><span data-stu-id="dafa9-112">Therefore, the site for lower-level demand is the same as the site on the initial demand transaction.</span></span>

<span data-ttu-id="dafa9-113">A következő ábra mutatja az alaptervezési igényalábontás folyamatát.</span><span class="sxs-lookup"><span data-stu-id="dafa9-113">The following illustration shows how the process for master planning demand explosion.</span></span> ![Alábontás igénylése az anyagjegyzék-verzió használatával](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="additional-resources"></a><span data-ttu-id="dafa9-115">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="dafa9-115">Additional resources</span></span>
--------

[<span data-ttu-id="dafa9-116">Anyagjegyzék-verzió meghatározása</span><span class="sxs-lookup"><span data-stu-id="dafa9-116">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)

[<span data-ttu-id="dafa9-117">Az alaptervezés és a többhelyes funkció áttekintése</span><span class="sxs-lookup"><span data-stu-id="dafa9-117">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)



