---
title: Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.6 alkalmazásban (2019. november)
description: Ez a témakör a Dynamics 365 Supply Chain Management 10.0.6 új vagy módosított szolgáltatásait írja le.
author: josaw1
manager: tfehr
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 77fdc3ae092fc8f214ae3ba68866244385e32b74
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263422"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-1006-november-2019"></a><span data-ttu-id="b2794-103">Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.6 alkalmazásban (2019. november)</span><span class="sxs-lookup"><span data-stu-id="b2794-103">What's new or changed in Dynamics 365 Supply Chain Management 10.0.6 (November 2019)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b2794-104">Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.6 új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="b2794-104">This topic describes features that are either new or changed in Microsoft Dynamics 365 Supply Chain Management 10.0.6.</span></span> <span data-ttu-id="b2794-105">Ennek a verziónak a buildszáma 10.0.234.</span><span class="sxs-lookup"><span data-stu-id="b2794-105">This version has a build number of 10.0.234.</span></span> <span data-ttu-id="b2794-106">Az általános elérhetőségi dátum novemberben, az új szolgáltatások októberben a korai kiadásokban érhetők el.</span><span class="sxs-lookup"><span data-stu-id="b2794-106">While the general availability date is in November, the new features are available for early release in October.</span></span> <span data-ttu-id="b2794-107">A 10.0.6 verzióval kapcsolatos további tájékoztatásért lásd: [Kiegészítő források](whats-new-scm-10-0-6.md#additional-resources).</span><span class="sxs-lookup"><span data-stu-id="b2794-107">For more information about version 10.0.6, see [Additional resources](whats-new-scm-10-0-6.md#additional-resources).</span></span>

## <a name="product-configuration-models-v2-data-entity"></a><span data-ttu-id="b2794-108">Termékkonfigurálási modellek V2 adatentitás</span><span class="sxs-lookup"><span data-stu-id="b2794-108">Product configuration models V2 data entity</span></span>

<span data-ttu-id="b2794-109">Megjelent a „termékkonfigurálási modellek” adatentitás második verziója (ennek neve „termékkonfigurálási modellek v2”).</span><span class="sxs-lookup"><span data-stu-id="b2794-109">A second version for the "product configuration models" data entity is released (called "products configuration models V2").</span></span> <span data-ttu-id="b2794-110">Az alapértelmezett sablon a „418 – termék konfigurációs modell” is szükséges, így az új „termékkonfigurálási modellek v2” adatentitást használja a keretrendszer-sablonok importálásához és exportálásához.</span><span class="sxs-lookup"><span data-stu-id="b2794-110">The default template "418-product configuration models" is also needs to be so that it uses the new "product configuration models V2" data entity in the import/export framework templates.</span></span> <span data-ttu-id="b2794-111">A sablon nem lesz automatikusan frissítve, így a sablont Önnek kell manuálisan betölteni az alapértelmezésből.</span><span class="sxs-lookup"><span data-stu-id="b2794-111">The template will not be auto-updated so that you will have to load the template from the default manually.</span></span> <span data-ttu-id="b2794-112">A V2 entitás nem beágyazva, hanem külön fájlként exportál egy sort egy mellékletbe, a V1 entitás méretkorlátainak feloldásához.</span><span class="sxs-lookup"><span data-stu-id="b2794-112">The V2 entity exports one row as separate file in an attachment instead of inline, solving the size limitations of the V1 entity.</span></span> 
 
<span data-ttu-id="b2794-113">Mit kell tennie ennek a módosításnak az alkalmazásához?</span><span class="sxs-lookup"><span data-stu-id="b2794-113">What do you need to do to take this change?</span></span>
-    <span data-ttu-id="b2794-114">Mivel a V1 entitás elavult, meg kell kezdeni az áttelepítést a V1-ről a V2-re.</span><span class="sxs-lookup"><span data-stu-id="b2794-114">As the V1 entity has been deprecated, you should start migrating from V1 to V2.</span></span> <span data-ttu-id="b2794-115">Ha használja a „418-termék konfigurációs modell” sablont, akkor az „alapértelmezett sablonok betöltést” gombra kattintva újratöltheti a „418 – termékkonfigurációs modellek” sablont</span><span class="sxs-lookup"><span data-stu-id="b2794-115">If you are using the  "418-product configuration models" template, you can click on "load default templates" button and reload the template "418 – product configuration models"</span></span>
-    <span data-ttu-id="b2794-116">Ha meg kell őriznie a meglévő rendszerekkel való kompatibilitást, akkor most továbbra is használhatja a meglévő sablont és az (elavult) v1 entitást mindaddig, amíg az új sablonba át nem helyezi az integrációkat.</span><span class="sxs-lookup"><span data-stu-id="b2794-116">If you need to keep compatibility with existing systems, you can for now continue using the existing template and the (deprecated) V1 entity until you move your integrations to the new template.</span></span> 

## <a name="feature-management-enhancements"></a><span data-ttu-id="b2794-117">Funkciókezelési fejlesztések</span><span class="sxs-lookup"><span data-stu-id="b2794-117">Feature management enhancements</span></span>
<span data-ttu-id="b2794-118">A funkciókezelés immár lehetővé teszi az összes új funkció alapértelmezett engedélyezését, de a funkció engedélyezéséhez megerősítés szükséges, és minden még nem engedélyezett funkciót engedélyezni kell.</span><span class="sxs-lookup"><span data-stu-id="b2794-118">Feature management now allows you to enable all new features by default, require confirmation to enable a feature, and enable all features that have not already been enabled.</span></span> 


## <a name="purchase-agreement-responsible-party"></a><span data-ttu-id="b2794-119">Beszerzési szerződésért felelős fél</span><span class="sxs-lookup"><span data-stu-id="b2794-119">Purchase agreement responsible party</span></span>
<span data-ttu-id="b2794-120">Most lehetősége van arra, hogy a Beszerzési szerződés osztályozási képernyőjén és a létrejövő Beszerzési szerződéseknél elsődleges és másodlagos felelős feleket határozzon meg.</span><span class="sxs-lookup"><span data-stu-id="b2794-120">You now have the ability to define primary and secondary responsible parties on the Purchase agreement classification form and resulting Purchase agreements.</span></span>  <span data-ttu-id="b2794-121">Ez biztosítja, hogy a felhasználók hozzáférjenek a szerződésekhez.</span><span class="sxs-lookup"><span data-stu-id="b2794-121">This provides the user access to who oversees the agreements.</span></span>

## <a name="rfq-link-on-the-purchase-order-line"></a><span data-ttu-id="b2794-122">Árajánlatkérés hivatkozás a Beszerzési rendelés során</span><span class="sxs-lookup"><span data-stu-id="b2794-122">RFQ link on the Purchase order line</span></span>
<span data-ttu-id="b2794-123">A beszerzési rendelési sorokhoz hozzáadhat egy hivatkozást, amely visszamutat arra az árajánlatkérésre, amelyből származik, így a felhasználó könnyedén elérheti az alátámasztó árajánlatkérési dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="b2794-123">You can add a reference link from the Purchase order lines back to the corresponding RFQ lines they originated from, allowing the user to easily be provided with the supporting request for quotation document.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b2794-124">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b2794-124">Additional resources</span></span>

### <a name="bug-fixes"></a><span data-ttu-id="b2794-125">Hibajavítások</span><span class="sxs-lookup"><span data-stu-id="b2794-125">Bug fixes</span></span>
<span data-ttu-id="b2794-126">Ha további tájékoztatást szeretne kapni a 10.0.6 részét képező frissítésekben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).</span><span class="sxs-lookup"><span data-stu-id="b2794-126">For information about the bug fixes included in each of the updates that are part of 10.0.6, sign in to Lifecycle Services (LCS) and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).</span></span>

### <a name="platform-update-30"></a><span data-ttu-id="b2794-127">Platform update 30</span><span class="sxs-lookup"><span data-stu-id="b2794-127">Platform update 30</span></span>
<span data-ttu-id="b2794-128">A Microsoft Dynamics 365 Supply Chain Management 10.0.6 a 30-as platform frissítést tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b2794-128">Microsoft Dynamics 365 Supply Chain Management 10.0.6 includes Platform update 30.</span></span> <span data-ttu-id="b2794-129">A 30-as platform frissítésével kapcsolatos további tudnivalókat lásd: [Újdonságok vagy módosítások a 30-as platformfrissítésben](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).</span><span class="sxs-lookup"><span data-stu-id="b2794-129">To learn more about Platform update 30, see [What's new or changed in Platform update 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).</span></span>

### <a name="dynamics-365-2019-release-wave-2-plan"></a><span data-ttu-id="b2794-130">Dynamics 365: 2019-es 2. hullám tervei</span><span class="sxs-lookup"><span data-stu-id="b2794-130">Dynamics 365: 2019 release wave 2 plan</span></span>
<span data-ttu-id="b2794-131">Kíváncsi a bármelyik üzleti alkalmazásával vagy platformjával kapcsolatos, közelgő és a közelmúltban bevezetett lehetőségekre?</span><span class="sxs-lookup"><span data-stu-id="b2794-131">Wondering about upcoming and recently released capabilities in any of our business apps or platform?</span></span>

<span data-ttu-id="b2794-132">Nézze meg a [Dynamics 365:2019 2es frissítési hullám tervét](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/).</span><span class="sxs-lookup"><span data-stu-id="b2794-132">Check out the [Dynamics 365: 2019 release wave 2 plan](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/).</span></span> <span data-ttu-id="b2794-133">A részleteket minden apró információmorzsáig bezárólag egyetlen dokumentumban rögzítettük, amelyet felhasználhat a tervezés során.</span><span class="sxs-lookup"><span data-stu-id="b2794-133">We've captured all the details, end to end, top to bottom, in a single document that you can use for planning.</span></span>

### <a name="removed-and-deprecated-supply-chain-management-features"></a><span data-ttu-id="b2794-134">Eltávolított és elavult Supply Chain Management szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="b2794-134">Removed and deprecated Supply Chain Management features</span></span>

<span data-ttu-id="b2794-135">A [Dynamics 365 Supply Chain Management eltávolított vagy elavult szolgáltatásai](removed-deprecated-features-scm-updates.md) témakör azokat a funkciókat írja le, amelyek el lettek távolítva a Supply Chain Management szolgáltatásól vagy eltávolításuk ütemezve van.</span><span class="sxs-lookup"><span data-stu-id="b2794-135">The [Removed or deprecated features in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) topic describes features that have been or are scheduled to be removed or deprecated for Supply Chain Management.</span></span>

- <span data-ttu-id="b2794-136">Az *eltávolított* szolgáltatások már nem érhetők el a termékben.</span><span class="sxs-lookup"><span data-stu-id="b2794-136">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="b2794-137">Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.</span><span class="sxs-lookup"><span data-stu-id="b2794-137">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="b2794-138">Mielőtt a termékből eltávolítunk egy szolgáltatást, egy eltávolítással kapcsolatos értesítést teszünk közzé a [Dynamics 365 Supply Chain Management eltávolított vagy elavult funkciói](removed-deprecated-features-scm-updates.md) témakörben 12 hónappal az eltávolítás előtt.</span><span class="sxs-lookup"><span data-stu-id="b2794-138">Before any feature is removed from the product, the deprecation notice will be announced in the [Removed or deprecated features in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) topic 12 months prior to the removal.</span></span>

<span data-ttu-id="b2794-139">Olyan módosítások esetén, amelyek csak a fordítási időt érintik, de binárisan kompatibilisek a tesztkörnyezettel és a termelési környezettel, az elavulási idő 12 hónapnál rövidebb lesz.</span><span class="sxs-lookup"><span data-stu-id="b2794-139">For breaking changes that only affect compilation time, but are binary compatible with sandbox and production environments, the deprecation time will be less than 12 months.</span></span> <span data-ttu-id="b2794-140">Ezek általában olyan funkcionális frissítések, amelyeket a fordítón kell elvégezni.</span><span class="sxs-lookup"><span data-stu-id="b2794-140">Typically, these are functional updates that need to be made to the compiler.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]