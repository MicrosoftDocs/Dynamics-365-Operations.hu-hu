---
title: Az AJ verziójának meghatározása
description: Igény alábontása során, ha egy cikk az alapértelmezett Termelés rendeléstípushoz tartozik, a tervezési motor megkeresi az érvényes anyagjegyzék-verziót a telephely alapján.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: efc980e3a3dfff6d163812396613a1493f4428a4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213791"
---
# <a name="determine-the-bom-version"></a><span data-ttu-id="7b16b-103">Az AJ verziójának meghatározása</span><span class="sxs-lookup"><span data-stu-id="7b16b-103">Determine the BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7b16b-104">Igény alábontása során, ha egy cikk az alapértelmezett Termelés rendeléstípushoz tartozik, a tervezési motor megkeresi az érvényes anyagjegyzék-verziót a telephely alapján.</span><span class="sxs-lookup"><span data-stu-id="7b16b-104">During a demand explosion, if an item has a default order type of Production, the planning engine finds a valid BOM version based on the site.</span></span> 

<span data-ttu-id="7b16b-105">A helydimenzió mindig ismert és megjelenik az igénytranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="7b16b-105">The site dimension is always known and is stated on the demand transaction.</span></span> <span data-ttu-id="7b16b-106">A következő folyamat használható, hogy meghatározza a használandó anyagjegyzék-verziót:</span><span class="sxs-lookup"><span data-stu-id="7b16b-106">The following process is used to determine the BOM version to use:</span></span>

-   <span data-ttu-id="7b16b-107">Ha van anyagjegyzék-verzió meghatározva a cikkhez az igény telephelyén, akkor a telephelyfüggő anyagjegyzék verzió kerül használatra.</span><span class="sxs-lookup"><span data-stu-id="7b16b-107">If there is a BOM version defined for the item at the demand site, the site-specific BOM is used.</span></span>
-   <span data-ttu-id="7b16b-108">Ha nincs telephelyfüggő anyagjegyzék-verzió meghatározva egy cikkhez az igény telephelyén akkor az általános anyagjegyzék-verzió kerül használatra.</span><span class="sxs-lookup"><span data-stu-id="7b16b-108">If there is no site-specific BOM version defined for an item at the demand site, a general BOM is used.</span></span> <span data-ttu-id="7b16b-109">Az általános anyagjegyzék nem határozza meg a telephelyet, és több telephelyre is érvényes.</span><span class="sxs-lookup"><span data-stu-id="7b16b-109">A general BOM does not state a site, and it is valid for multiple sites.</span></span> <span data-ttu-id="7b16b-110">Ha van általános anyagjegyzék, akkor használatra kerül.</span><span class="sxs-lookup"><span data-stu-id="7b16b-110">If there is a general BOM, it is used.</span></span>
-   <span data-ttu-id="7b16b-111">Ha nincs használható általános anyagjegyzék, akkor az igény alábontása ezen a ponton leáll.</span><span class="sxs-lookup"><span data-stu-id="7b16b-111">If there is no general BOM version to use, the demand explosion stops at this point.</span></span>

<span data-ttu-id="7b16b-112">Minden érvényes anyagjegyzék-verziónak, legyen az telephelyre jellemző vagy általános verzió, teljesítenie kell a dátumra és a mennyiségre vonatkozó kötelező feltételeket.</span><span class="sxs-lookup"><span data-stu-id="7b16b-112">A valid BOM version, whether site-specific or general, must meet the required criteria for date and quantity.</span></span>





