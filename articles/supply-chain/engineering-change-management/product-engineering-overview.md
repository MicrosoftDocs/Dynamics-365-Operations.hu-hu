---
title: Tervezési változáskezelés áttekintése
description: Ez a témakör áttekintést nyújt a tervezési változáskezeléssel kapcsolatban, amely segítséget nyújt a termék verziószámozásának tervezéséhez és kezeléséhez, valamint a termékéletciklusok és mérnöki változásainak kezeléséhez.
author: t-benebo
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: f1aa04b472eaef7ed398f08a05d46bac2d589561
ms.sourcegitcommit: 9f32389715b226c11e74c53547527e0a8b51e300
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/12/2020
ms.locfileid: "4514350"
---
# <a name="engineering-change-management-overview"></a><span data-ttu-id="bd858-103">Tervezési változáskezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="bd858-103">Engineering change management overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a><span data-ttu-id="bd858-104">Funkció összegzése</span><span class="sxs-lookup"><span data-stu-id="bd858-104">Feature summary</span></span>

<span data-ttu-id="bd858-105">A mai gyártóknak szükségük van hatékony termék-adatmenedzsmentre, verziószabályozásra és tervezési változáskezelésre, hogy sikeresek legyenek a folyamatosan csökkenő termékéletciklusok, a megnövekedő minőségi és megbízhatósági követelmények, valamint a növekedő termékbiztonsági fókusz világában.</span><span class="sxs-lookup"><span data-stu-id="bd858-105">Today's manufacturers require strong product data management, version control, and engineering change management to succeed in a world of constantly shrinking product lifecycles, increased quality and reliability requirements, and an increased focus on product safety.</span></span>

<span data-ttu-id="bd858-106">A mérnöki változtatáskezelés struktúrát és fegyelmet hoz a termékadat-menedzsment folyamatba, és a termékek így szabályozott módon határozhatók meg, adhatók ki és felügyelhetők, amelyet munkafolyamatok támogatnak.</span><span class="sxs-lookup"><span data-stu-id="bd858-106">Engineering change management brings structure and discipline to the product data management process, and enables products to be defined, released, and revised in a controlled manner that is supported by workflows.</span></span><span data-ttu-id="bd858-107"> A termékverziók és a mérnöki változáskezelés segítségével dokumentálhatja a mérnöki változásokat, értékelheti a határukat és alkalmazhatja őket a termék teljes életciklusa során.</span><span class="sxs-lookup"><span data-stu-id="bd858-107"> Through product versions and engineering change management, you can document, assess the impact of, and apply engineering changes throughout the whole lifecycle of a product.</span></span>

<span data-ttu-id="bd858-108">A tervezési változáskezelés segítséget nyújt a termék verziószámozásának tervezéséhez és kezeléséhez, valamint a termékéletciklusok és mérnöki változásainak kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="bd858-108">Engineering change management helps you plan and manage product versioning, and manage product lifecycles and engineering changes.</span></span> <span data-ttu-id="bd858-109">Itt van egy lista a fő funkciókról:</span><span class="sxs-lookup"><span data-stu-id="bd858-109">Here is a list of its main features:</span></span>

- <span data-ttu-id="bd858-110">Termék verziószámozása</span><span class="sxs-lookup"><span data-stu-id="bd858-110">Product versioning</span></span>
- <span data-ttu-id="bd858-111">Továbbfejlesztett termékkiadási funkció, amely lehetővé teszi a termék alapadatainak karbantartását egy jogi személyben (a tervezési vállalatban), és közzéteheti a teljesen konfigurált kiadott terméket más jogi személyekbe</span><span class="sxs-lookup"><span data-stu-id="bd858-111">Enhanced product release functionality that lets you maintain product master data in one legal entity (the engineering company) and publish the fully configured released product to other legal entities</span></span>
- <span data-ttu-id="bd858-112">Annak ellenőrzésére vonatkozó szabályok, hogy a kötelező adatokat megadták-e a termékverzió aktiválása előtt (készenléti ellenőrzések)</span><span class="sxs-lookup"><span data-stu-id="bd858-112">Rules for validating that required information is entered before a product version is activated (readiness checks)</span></span>
- <span data-ttu-id="bd858-113">Továbbfejlesztett termékéletciklus-kezelés a kiadott termék meghatározott üzleti folyamatokban való alkalmazásának részletes szabályozásával</span><span class="sxs-lookup"><span data-stu-id="bd858-113">Improved product lifecycle management through fine-grained control over when a released product can be used in specific business processes</span></span>
- <span data-ttu-id="bd858-114">Tervezési változási kérelmek, amelyeket munkafolyamatok támogatnak</span><span class="sxs-lookup"><span data-stu-id="bd858-114">Engineering change requests that are supported by workflows</span></span>
- <span data-ttu-id="bd858-115">Tervezési változási rendelések, amelyeket munkafolyamatok támogatnak</span><span class="sxs-lookup"><span data-stu-id="bd858-115">Engineering change orders that are supported by workflows</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

<span data-ttu-id="bd858-116">Az előző videó ([Módosításkezelési képességek a Dynamics 365 Supply Chain Management rendszerben](https://youtu.be/N313FqvRuBc)) szerepel a [Finance and Operations lejátszási listában](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) a YouTube-on.</span><span class="sxs-lookup"><span data-stu-id="bd858-116">The preceding video ([Change management capabilities in Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="turn-on-engineering-change-management-for-your-system"></a><span data-ttu-id="bd858-117">A rendszer műszaki módosításkezelésének bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="bd858-117">Turn on engineering change management for your system</span></span>

<span data-ttu-id="bd858-118">Először kapcsolja be a mérnöki módosításkezelést az alábbi lépések végrehajtásával.</span><span class="sxs-lookup"><span data-stu-id="bd858-118">First, turn on engineering change management by following these steps.</span></span>

1. <span data-ttu-id="bd858-119">Lépjen a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bd858-119">Go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
1. <span data-ttu-id="bd858-120">Keressen frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="bd858-120">Check for updates.</span></span>
1. <span data-ttu-id="bd858-121">Kapcsolja be a **Mérnöki módosításkezelés** szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="bd858-121">Turn on the feature that is named **Engineering Change Management**.</span></span>

<span data-ttu-id="bd858-122">Ezután kapcsolja be a **Mérnöki módosításkezelés** konfigurációs kulcsot az alábbi lépések végrehajtásával.</span><span class="sxs-lookup"><span data-stu-id="bd858-122">Next, turn on the **Engineering Change Management** configuration key by following these steps.</span></span>

1. <span data-ttu-id="bd858-123">Állítsa a rendszert karbantartási módba a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="bd858-123">Put your system into maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="bd858-124">Lépjen a **Rendszerfelügyelet \> Beállítás \> Licenckonfiguráció** elemre.</span><span class="sxs-lookup"><span data-stu-id="bd858-124">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="bd858-125">Bontsa ki a **Kereskedelmi** csomópontot, és jelölje be a **Mérnöki módosításkezelés** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="bd858-125">Expand the **Trade** node, and select the **Engineering Change Management** check box.</span></span>
1. <span data-ttu-id="bd858-126">Kapcsolja ki a karbantartási módot a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="bd858-126">Turn off maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
