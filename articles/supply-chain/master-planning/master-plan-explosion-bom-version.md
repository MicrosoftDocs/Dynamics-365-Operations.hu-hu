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
ms.openlocfilehash: dbdfc169365cb73e13383b11efcd8983aef4bbca
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2815318"
---
# <a name="explosion-of-a-bom-version"></a><span data-ttu-id="45618-103">Anyagjegyzék-verzió alábontása</span><span class="sxs-lookup"><span data-stu-id="45618-103">Explosion of a BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="45618-104">Ez a cikk egy anyagjegyzék-verzió alábontásának alaptervezési forgatókönyvét ismerteti.</span><span class="sxs-lookup"><span data-stu-id="45618-104">This article explains a master planning scenario that involves explosion of a bill of materials (BOM) version.</span></span>

<span data-ttu-id="45618-105">Egy anyagjegyzék-verzió igényalábontása létrehoz egy igényt minden anyagjegyzéksor-cikkhez egy adott telephelyen, esetleg egy adott raktárban.</span><span class="sxs-lookup"><span data-stu-id="45618-105">A demand explosion of a bill of materials (BOM) version creates a demand for each BOM line item at a specific site and, possibly, at a specific warehouse.</span></span> <span data-ttu-id="45618-106">Egy telephely-specifikus anyagjegyzékben egy adott raktár határozható meg minden anyagjegyzék-sorhoz.</span><span class="sxs-lookup"><span data-stu-id="45618-106">In a site-specific BOM, a specific warehouse can be defined for each BOM line.</span></span> <span data-ttu-id="45618-107">Továbbá minden anyagjegyzék-sorhoz a cikk dimenzióbeállításai meghatározzák, hogy a raktár szükséges-e.</span><span class="sxs-lookup"><span data-stu-id="45618-107">Additionally, for each BOM line, the item's dimension settings determine whether the warehouse is required.</span></span> <span data-ttu-id="45618-108">Az egyes anyagjegyzékcikk-sorokhoz megjelenő igény ezután a további igényalábontás kezdőpontja lesz.</span><span class="sxs-lookup"><span data-stu-id="45618-108">The resulting demand for each BOM line item then becomes the starting point for additional demand explosion.</span></span> <span data-ttu-id="45618-109">Ez az alaptervezési eset a következő feltételeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="45618-109">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="45618-110">A telephely dimenzió kötelező, és meg kell adni az igénytranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="45618-110">The site dimension is mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="45618-111">A hely dimenzió konzisztens.</span><span class="sxs-lookup"><span data-stu-id="45618-111">The site dimension is consistent.</span></span> <span data-ttu-id="45618-112">Az alsóbb szintű igények telephelye megegyezik a kiinduló igénytranzakció telephelyével.</span><span class="sxs-lookup"><span data-stu-id="45618-112">Therefore, the site for lower-level demand is the same as the site on the initial demand transaction.</span></span>

<span data-ttu-id="45618-113">A következő ábra mutatja az alaptervezési igényalábontás folyamatát.</span><span class="sxs-lookup"><span data-stu-id="45618-113">The following illustration shows how the process for master planning demand explosion.</span></span> ![Alábontás igénylése az anyagjegyzék-verzió használatával](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="additional-resources"></a><span data-ttu-id="45618-115">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="45618-115">Additional resources</span></span>
--------

[<span data-ttu-id="45618-116">Anyagjegyzék-verzió meghatározása</span><span class="sxs-lookup"><span data-stu-id="45618-116">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)

[<span data-ttu-id="45618-117">Az alaptervezés és a többhelyes funkció áttekintése</span><span class="sxs-lookup"><span data-stu-id="45618-117">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)



