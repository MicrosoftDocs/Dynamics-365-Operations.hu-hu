---
title: Tervezési változáskezelés áttekintése
description: Ez a témakör áttekintést nyújt a tervezési változáskezeléssel kapcsolatban, amely segítséget nyújt a termék verziószámozásának tervezéséhez és kezeléséhez, valamint a termékéletciklusok és mérnöki változásainak kezeléséhez.
author: t-benebo
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: d7c0839ffbea80904ca12d1cba7ba9880f721cdd
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947520"
---
# <a name="engineering-change-management-overview"></a><span data-ttu-id="209ff-103">Tervezési változáskezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="209ff-103">Engineering change management overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a><span data-ttu-id="209ff-104">Funkció összegzése</span><span class="sxs-lookup"><span data-stu-id="209ff-104">Feature summary</span></span>

<span data-ttu-id="209ff-105">A mai gyártóknak szükségük van hatékony termék-adatmenedzsmentre, verziószabályozásra és tervezési változáskezelésre, hogy sikeresek legyenek a folyamatosan csökkenő termékéletciklusok, a megnövekedő minőségi és megbízhatósági követelmények, valamint a növekedő termékbiztonsági fókusz világában.</span><span class="sxs-lookup"><span data-stu-id="209ff-105">Today's manufacturers require strong product data management, version control, and engineering change management to succeed in a world of constantly shrinking product lifecycles, increased quality and reliability requirements, and an increased focus on product safety.</span></span>

<span data-ttu-id="209ff-106">A mérnöki változtatáskezelés struktúrát és fegyelmet hoz a termékadat-menedzsment folyamatba, és a termékek így szabályozott módon határozhatók meg, adhatók ki és felügyelhetők, amelyet munkafolyamatok támogatnak.</span><span class="sxs-lookup"><span data-stu-id="209ff-106">Engineering change management brings structure and discipline to the product data management process, and enables products to be defined, released, and revised in a controlled manner that is supported by workflows.</span></span><span data-ttu-id="209ff-107"> A termékverziók és a mérnöki változáskezelés segítségével dokumentálhatja a mérnöki változásokat, értékelheti a határukat és alkalmazhatja őket a termék teljes életciklusa során.</span><span class="sxs-lookup"><span data-stu-id="209ff-107"> Through product versions and engineering change management, you can document, assess the impact of, and apply engineering changes throughout the whole lifecycle of a product.</span></span>

<span data-ttu-id="209ff-108">A tervezési változáskezelés segítséget nyújt a termék verziószámozásának tervezéséhez és kezeléséhez, valamint a termékéletciklusok és mérnöki változásainak kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="209ff-108">Engineering change management helps you plan and manage product versioning, and manage product lifecycles and engineering changes.</span></span> <span data-ttu-id="209ff-109">Itt van egy lista a fő funkciókról:</span><span class="sxs-lookup"><span data-stu-id="209ff-109">Here is a list of its main features:</span></span>

- <span data-ttu-id="209ff-110">Termék verziószámozása</span><span class="sxs-lookup"><span data-stu-id="209ff-110">Product versioning</span></span>
- <span data-ttu-id="209ff-111">Továbbfejlesztett termékkiadási funkció, amely lehetővé teszi a termék alapadatainak karbantartását egy jogi személyben (a tervezési vállalatban), és közzéteheti a teljesen konfigurált kiadott terméket más jogi személyekbe</span><span class="sxs-lookup"><span data-stu-id="209ff-111">Enhanced product release functionality that lets you maintain product master data in one legal entity (the engineering company) and publish the fully configured released product to other legal entities</span></span>
- <span data-ttu-id="209ff-112">Annak ellenőrzésére vonatkozó szabályok, hogy a kötelező adatokat megadták-e a termékverzió aktiválása előtt (készenléti ellenőrzések)</span><span class="sxs-lookup"><span data-stu-id="209ff-112">Rules for validating that required information is entered before a product version is activated (readiness checks)</span></span>
- <span data-ttu-id="209ff-113">Továbbfejlesztett termékéletciklus-kezelés a kiadott termék meghatározott üzleti folyamatokban való alkalmazásának részletes szabályozásával</span><span class="sxs-lookup"><span data-stu-id="209ff-113">Improved product lifecycle management through fine-grained control over when a released product can be used in specific business processes</span></span>
- <span data-ttu-id="209ff-114">Tervezési változási kérelmek, amelyeket munkafolyamatok támogatnak</span><span class="sxs-lookup"><span data-stu-id="209ff-114">Engineering change requests that are supported by workflows</span></span>
- <span data-ttu-id="209ff-115">Tervezési változási rendelések, amelyeket munkafolyamatok támogatnak</span><span class="sxs-lookup"><span data-stu-id="209ff-115">Engineering change orders that are supported by workflows</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

<span data-ttu-id="209ff-116">Az előző videó ([Módosításkezelési képességek a Dynamics 365 Supply Chain Management rendszerben](https://youtu.be/N313FqvRuBc)) szerepel a [Finance and Operations lejátszási listában](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) a YouTube-on.</span><span class="sxs-lookup"><span data-stu-id="209ff-116">The preceding video ([Change management capabilities in Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="turn-on-the-engineering-change-management-and-version-dimension-features-for-your-system"></a><span data-ttu-id="209ff-117">Kapcsolja be a tervezési változáskezelést és a verziódimenziókat a rendszerén</span><span class="sxs-lookup"><span data-stu-id="209ff-117">Turn on the engineering change management and version dimension features for your system</span></span>

<span data-ttu-id="209ff-118">A tervezési változáskezelés használata előtt engedélyeznie kell a *Tervezési változáskezelés* szolgáltatást és annak konfigurációs kulcsát.</span><span class="sxs-lookup"><span data-stu-id="209ff-118">Before you can use engineering change management, you must enable both the *Engineering Change Management* feature and its configuration key.</span></span> <span data-ttu-id="209ff-119">Ha a tranzakciókban nyomon szeretné követni a termékek verziódimenzióját is (opcionális), akkor engedélyeznie kell a *Termékverzió dimenzió* szolgáltatást és annak konfigurációs kulcsát is.</span><span class="sxs-lookup"><span data-stu-id="209ff-119">If you also want to track the version dimension of products in transactions (optional), then you must also enable the *Product version dimension* feature and its configuration key.</span></span>

<span data-ttu-id="209ff-120">Először kapcsolja be a funkciókat a következő lépések végrehajtásával.</span><span class="sxs-lookup"><span data-stu-id="209ff-120">First, turn on the features by following these steps.</span></span>

1. <span data-ttu-id="209ff-121">Ugorjon a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületre.</span><span class="sxs-lookup"><span data-stu-id="209ff-121">Go to the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace.</span></span>
1. <span data-ttu-id="209ff-122">Keressen frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="209ff-122">Check for updates.</span></span>
1. <span data-ttu-id="209ff-123">Kapcsolja be a **Mérnöki módosításkezelés** szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="209ff-123">Turn on the feature that is named **Engineering Change Management**.</span></span>
1. <span data-ttu-id="209ff-124">Ha használni szeretné, kapcsolja be a **Termékdimenzió verziója** nevű szolgáltatást is.</span><span class="sxs-lookup"><span data-stu-id="209ff-124">If you want to use it, then also turn on the feature that is named **Product dimension version**.</span></span>

<span data-ttu-id="209ff-125">Ezután kapcsolja be a konfigurációs kulcsokat a következő lépések végrehajtásával.</span><span class="sxs-lookup"><span data-stu-id="209ff-125">Next, turn on the configuration keys by following these steps.</span></span>

1. <span data-ttu-id="209ff-126">Állítsa a rendszert karbantartási módba a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="209ff-126">Put your system into maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="209ff-127">Lépjen a **Rendszerfelügyelet \> Beállítás \> Licenckonfiguráció** elemre.</span><span class="sxs-lookup"><span data-stu-id="209ff-127">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="209ff-128">Bontsa ki a **Kereskedelem** csomópontot,</span><span class="sxs-lookup"><span data-stu-id="209ff-128">Expand the **Trade** node.</span></span>
1. <span data-ttu-id="209ff-129">A fő funkció konfigurációs kulcsának engedélyezéséhez jelölje be a **Mérnöki változások kezelése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="209ff-129">Enable the configuration key for the main feature by selecting the **Engineering Change Management** check box.</span></span> <span data-ttu-id="209ff-130">(Nem kell feltétlenül kibontania a csomópontot, hacsak nem szeretné letiltani az egyik vagy az összes alfunkcióját.)</span><span class="sxs-lookup"><span data-stu-id="209ff-130">(It isn't necessary to expand the node unless you also want to disable one or both of its sub-features.)</span></span>
1. <span data-ttu-id="209ff-131">Ha használni szeretné a verziódimenziót is, jelölje be a **Termékdimenzió – Verzió** jelölőnégyzetet is.</span><span class="sxs-lookup"><span data-stu-id="209ff-131">If you also want to use the version dimension, then select the **Product dimension - Version** check box.</span></span> <span data-ttu-id="209ff-132">(Ez a jelölőnégyzet a listában lejjebb van, nem a **Műszaki módosítások kezelése** csomópont alatt.)</span><span class="sxs-lookup"><span data-stu-id="209ff-132">(This check box is further down the list, not nested under the **Engineering Change Management** node.)</span></span>
1. <span data-ttu-id="209ff-133">Kapcsolja ki a karbantartási módot a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="209ff-133">Turn off maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="209ff-134">2022 áprilisától kezdve a **Mérnöki változások kezelése** és a **Termékdimenzió – Verzió** licenckulcsok alapértelmezés szerint engedélyezve lesznek minden új telepítés esetén, de szükség esetén továbbra is letilthatja őket.</span><span class="sxs-lookup"><span data-stu-id="209ff-134">Starting in April 2022, the license keys for both **Engineering Change Management** and **Product dimension - Version** will be enabled by default for all new installations, but you will still be able to disable them if needed.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
