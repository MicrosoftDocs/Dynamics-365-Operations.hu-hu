---
title: Kettős írás – áttekintés
description: Ez a témakör áttekintést nyújt a kettős írásról. A kettős írás egy olyan infrastruktúra, amely közel valós idejű interakciót tesz lehetővé a Microsoft Dynamics 365 modellvezérelt alkalmazások és a Finance and Operations alkalmazások között.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 64626ebdd7fbad3d47a4b4c6bbc45bf3bc0c8277
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172784"
---
# <a name="dual-write-overview"></a><span data-ttu-id="5bde0-104">Kettős írás – áttekintés</span><span class="sxs-lookup"><span data-stu-id="5bde0-104">Dual-write overview</span></span>

[!include [banner](../../includes/banner.md)]



## <a name="what-is-dual-write"></a><span data-ttu-id="5bde0-105">Mi az a kettős írás?</span><span class="sxs-lookup"><span data-stu-id="5bde0-105">What is dual-write?</span></span>

<span data-ttu-id="5bde0-106">A kettős írás egy olyan beépített infrastruktúra, amely közel valós idejű interakciót tesz lehetővé a Microsoft Dynamics 365 modellvezérelt alkalmazásai és a Finance and Operations alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="5bde0-106">Dual-write is an out-of-box infrastructure that provides near-real-time interaction between model-driven apps in Microsoft Dynamics 365 and Finance and Operations apps.</span></span> <span data-ttu-id="5bde0-107">Amikor a vevőkkel, termékekkel, személyekkel és műveletekkel kapcsolatos adatok az alkalmazás határain túl is eljutnak, az a szervezet minden részlegét felbátorítja.</span><span class="sxs-lookup"><span data-stu-id="5bde0-107">When data about customers, products, people, and operations flows beyond application boundaries, all departments in an organization are empowered.</span></span>

<span data-ttu-id="5bde0-108">A kettős írás szorosan összekapcsolt, kétirányú integrációt tesz lehetővé a Finance and Operations alkalmazások és a Common Data Service között.</span><span class="sxs-lookup"><span data-stu-id="5bde0-108">Dual-write provides tightly coupled, bidirectional integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="5bde0-109">A Finance and Operations alkalmazások bármely adatmódosulása írást eredményez a Common Data Service szolgáltatásban, és a Common Data Service bármely adatváltozása írást eredményez a Finance and Operations alkalmazásokban.</span><span class="sxs-lookup"><span data-stu-id="5bde0-109">Any data change in Finance and Operations apps causes writes to Common Data Service, and any data change in Common Data Service causes writes to Finance and Operations apps.</span></span> <span data-ttu-id="5bde0-110">Ez az automatizált adatáramlás integrált felhasználói élményt nyújt az alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="5bde0-110">This automated data flow provides an integrated user experience across the apps.</span></span>

![Adatkapcsolat az alkalmazások között](media/dual-write-overview.jpg)

<span data-ttu-id="5bde0-112">A kettős írásnak két aspektusa van: egy *infrastruktúra* szempont és egy *alkalmazási* szempont.</span><span class="sxs-lookup"><span data-stu-id="5bde0-112">Dual-write has two aspects: an *infrastructure* aspect and an *application* aspect.</span></span>

### <a name="infrastructure"></a><span data-ttu-id="5bde0-113">Infrastruktúra</span><span class="sxs-lookup"><span data-stu-id="5bde0-113">Infrastructure</span></span>

<span data-ttu-id="5bde0-114">A kettős írás infrastruktúrája bővíthető és megbízható, és a következő kulcsfontosságú funkciókat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="5bde0-114">The dual-write infrastructure is extensible and reliable, and includes the following key features:</span></span>

+ <span data-ttu-id="5bde0-115">Az alkalmazások közötti szinkron és kétirányú adatáramlás</span><span class="sxs-lookup"><span data-stu-id="5bde0-115">Synchronous and bidirectional data flow between applications</span></span>
+ <span data-ttu-id="5bde0-116">Szinkronizálás, lejátszási, szüneteltetési és felzárkóztatás módokkal együtt a rendszer támogatása érdekében az online és offline/aszinkron mód esetében.</span><span class="sxs-lookup"><span data-stu-id="5bde0-116">Synchronization, together with play, pause, and catchup modes to support the system during online and offline/asynchronous modes.</span></span>
+ <span data-ttu-id="5bde0-117">A kezdeti adatok szinkronizálásának lehetősége az alkalmazások között</span><span class="sxs-lookup"><span data-stu-id="5bde0-117">Ability to sync initial data between the applications</span></span>
+ <span data-ttu-id="5bde0-118">A tevékenység és a hibanaplók konszolidált nézete adatrendszergazdák számára</span><span class="sxs-lookup"><span data-stu-id="5bde0-118">Consolidated view of activity and error logs for data admins</span></span>
+ <span data-ttu-id="5bde0-119">Egyéni figyelmeztetések és küszöbértékek konfigurálásának és értesítésekre való feliratkozás képessége</span><span class="sxs-lookup"><span data-stu-id="5bde0-119">Ability to configure custom alerts and thresholds, and to subscribe to notifications</span></span>
+ <span data-ttu-id="5bde0-120">Intuitív felhasználói felület (UI) szűréshez és átalakításokhoz</span><span class="sxs-lookup"><span data-stu-id="5bde0-120">Intuitive user interface (UI) for filtering and transformations</span></span>
+ <span data-ttu-id="5bde0-121">Entitásfüggőségek és kapcsolatok beállításának lehetősége</span><span class="sxs-lookup"><span data-stu-id="5bde0-121">Ability to set and view entity dependencies and relationships</span></span>
+ <span data-ttu-id="5bde0-122">Bővíthetőség a szabványos és egyéni entitások és leképezések esetében</span><span class="sxs-lookup"><span data-stu-id="5bde0-122">Extensibility for both standard and custom entities and maps</span></span>
+ <span data-ttu-id="5bde0-123">Megbízható alkalmazáséletciklus-kezelés</span><span class="sxs-lookup"><span data-stu-id="5bde0-123">Reliable application lifecycle management</span></span>
+ <span data-ttu-id="5bde0-124">Beépített beállítási élmény új ügyfelek számára</span><span class="sxs-lookup"><span data-stu-id="5bde0-124">Out-of-box setup experience for new customers</span></span>

### <a name="application"></a><span data-ttu-id="5bde0-125">Alkalmazás</span><span class="sxs-lookup"><span data-stu-id="5bde0-125">Application</span></span>

<span data-ttu-id="5bde0-126">A kettős írás megfeleltetést hoz létre a Finance and Operations alkalmazások koncepciói és a Dynamics 365 modellvezérelt alkalmazásainak koncepciói között.</span><span class="sxs-lookup"><span data-stu-id="5bde0-126">Dual-write creates a mapping between concepts in Finance and Operations apps and concepts in model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="5bde0-127">Ez az integráció a következő eseteket támogatja:</span><span class="sxs-lookup"><span data-stu-id="5bde0-127">This integration supports the following scenarios:</span></span>

+ <span data-ttu-id="5bde0-128">Integrált vevői alapadat</span><span class="sxs-lookup"><span data-stu-id="5bde0-128">Integrated customer master</span></span>
+ <span data-ttu-id="5bde0-129">A vevői hűségkártyákhoz és jutalompontokhoz való hozzáférés</span><span class="sxs-lookup"><span data-stu-id="5bde0-129">Access to customer loyalty cards and reward points</span></span>
+ <span data-ttu-id="5bde0-130">Egységes alaptermékkel kapcsolatos élmény</span><span class="sxs-lookup"><span data-stu-id="5bde0-130">Unified product mastering experience</span></span>
+ <span data-ttu-id="5bde0-131">Szervezeti hierarchiák ismertsége</span><span class="sxs-lookup"><span data-stu-id="5bde0-131">Awareness of organization hierarchy</span></span>
+ <span data-ttu-id="5bde0-132">Integrált szállítói alapadat</span><span class="sxs-lookup"><span data-stu-id="5bde0-132">Integrated vendor master</span></span>
+ <span data-ttu-id="5bde0-133">A pénzügyi és adóügyi hivatkozási adatokhoz való hozzáférés</span><span class="sxs-lookup"><span data-stu-id="5bde0-133">Access to finance and tax reference data</span></span>
+ <span data-ttu-id="5bde0-134">Igény szerinti árképzési motorral kapcsolatos élmény</span><span class="sxs-lookup"><span data-stu-id="5bde0-134">On-demand price engine experience</span></span>
+ <span data-ttu-id="5bde0-135">Integrált Potenciális vevők készpénzre váltása élmény</span><span class="sxs-lookup"><span data-stu-id="5bde0-135">Integrated prospect-to-cash experience</span></span>
+ <span data-ttu-id="5bde0-136">Képesség a házon belüli eszközök és a vevői eszközök felhasználhatóságára helyszíni ügyfelek által</span><span class="sxs-lookup"><span data-stu-id="5bde0-136">Ability to serve both in-house assets and customer assets through field agents</span></span>
+ <span data-ttu-id="5bde0-137">Integrált beszerzésirányítási élmény</span><span class="sxs-lookup"><span data-stu-id="5bde0-137">Integrated procure-to-pay experience</span></span>
+ <span data-ttu-id="5bde0-138">Integrált tevékenységek és megjegyzések a vevői adatokhoz és dokumentumokhoz</span><span class="sxs-lookup"><span data-stu-id="5bde0-138">Integrated activities and notes for customer data and documents</span></span>
+ <span data-ttu-id="5bde0-139">Lehetőség a tényleges készlet elérhetőségének és részleteinek keresésére</span><span class="sxs-lookup"><span data-stu-id="5bde0-139">Ability to look up on-hand inventory availability and details</span></span>
+ <span data-ttu-id="5bde0-140">Projekt készpénzre váltási élménye</span><span class="sxs-lookup"><span data-stu-id="5bde0-140">Project-to-cash experience</span></span>
+ <span data-ttu-id="5bde0-141">Több cím és szerepkör kezelésének képessége a fél koncepción keresztül</span><span class="sxs-lookup"><span data-stu-id="5bde0-141">Ability to handle multiple addresses and roles through the party concept</span></span>
+ <span data-ttu-id="5bde0-142">Önálló erőforrás-kezelés felhasználók számára</span><span class="sxs-lookup"><span data-stu-id="5bde0-142">Single source management for users</span></span>
+ <span data-ttu-id="5bde0-143">Integrált csatornák a kiskereskedelem és marketing modulhoz</span><span class="sxs-lookup"><span data-stu-id="5bde0-143">Integrated channels for retailing and marketing</span></span>
+ <span data-ttu-id="5bde0-144">Betekintési lehetőség promóciókba és engedményekbe</span><span class="sxs-lookup"><span data-stu-id="5bde0-144">Visibility into promotions and discounts</span></span>
+ <span data-ttu-id="5bde0-145">Szolgáltatáskérési funkciók</span><span class="sxs-lookup"><span data-stu-id="5bde0-145">Request-for-service functions</span></span>
+ <span data-ttu-id="5bde0-146">Egyszerűsített szolgáltatási műveletek</span><span class="sxs-lookup"><span data-stu-id="5bde0-146">Streamlined service operations</span></span>

## <a name="top-reasons-to-use-dual-write"></a><span data-ttu-id="5bde0-147">A kettős írás használatának legfőbb okai</span><span class="sxs-lookup"><span data-stu-id="5bde0-147">Top reasons to use dual-write</span></span>

<span data-ttu-id="5bde0-148">A kettős írás adatintegrációt tesz lehetővé az egész Microsoft Dynamics 365 alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="5bde0-148">Dual-write provides data integration across Microsoft Dynamics 365 applications.</span></span> <span data-ttu-id="5bde0-149">Ez a robosztus keretrendszer összeköti a környezeteket és lehetővé teszi az üzleti alkalmazások együttműködését.</span><span class="sxs-lookup"><span data-stu-id="5bde0-149">This robust framework links environments and enables different business applications to work together.</span></span> <span data-ttu-id="5bde0-150">Íme a legfontosabb okok a kettős írás használatára:</span><span class="sxs-lookup"><span data-stu-id="5bde0-150">Here are the top reasons why you should use dual-write:</span></span>

+ <span data-ttu-id="5bde0-151">A kettős írás szorosan összekapcsolt, szinte valós idejű, kétirányú integrációt tesz lehetővé a Finance and Operations alkalmazások és a Dynamics 365 modellvezérelt alkalmazásai között.</span><span class="sxs-lookup"><span data-stu-id="5bde0-151">Dual-write provides tightly coupled, near-real-time, and bidirectional integration between Finance and Operations apps and model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="5bde0-152">Az integrációnak köszönhetően a Microsoft Dynamics 365 egyben nyújt szolgáltatást az összes üzleti megoldáshoz.</span><span class="sxs-lookup"><span data-stu-id="5bde0-152">This integration makes Microsoft Dynamics 365 the one-stop shop for all your business solutions.</span></span> <span data-ttu-id="5bde0-153">A Dynamics 365 Finance és Dynamics 365 Supply Chain Management szolgáltatásokat használó ügyfelek, akik nem Microsoftos megoldásokat használnak ügyfélkapcsolat-kezeléshez (CRM) a kettős írás támogatása miatt áttérnek a Dynamics 365 szolgáltatásra.</span><span class="sxs-lookup"><span data-stu-id="5bde0-153">Customers who use Dynamics 365 Finance and Dynamics 365 Supply Chain Management, but who use non-Microsoft solutions for customer relationship management (CRM), are moving toward Dynamics 365 for its dual-write support.</span></span>
+ <span data-ttu-id="5bde0-154">Az ügyfelekről, termékekről, műveletektől, projektektől és az eszközök internetes hálózatától (IoT) származó adatok automatikusan átáramlanak a Common Data Service szolgáltatásba a kettős íráson keresztül.</span><span class="sxs-lookup"><span data-stu-id="5bde0-154">Data from customers, products, operations, projects, and the Internet of Things (IoT) automatically flows to Common Data Service through dual-write.</span></span> <span data-ttu-id="5bde0-155">Ez a kapcsolat nagyon hasznos a Microsoft Power Platform bővítésben érdekelt vállalatok számára.</span><span class="sxs-lookup"><span data-stu-id="5bde0-155">This connection is very useful for businesses that are interested in Microsoft Power Platform expansions.</span></span>
+ <span data-ttu-id="5bde0-156">A kettős írás infrastruktúrája a nincs kódolás/kevés kódolás elvet követi.</span><span class="sxs-lookup"><span data-stu-id="5bde0-156">The dual-write infrastructure follows the no-code/low-code principle.</span></span> <span data-ttu-id="5bde0-157">Minimális mérnöki erőfeszítést kell tenni a szabványos táblák közti leképezések kiterjesztéséhez, és az egyéni leképezések szerepeltetéséhez.</span><span class="sxs-lookup"><span data-stu-id="5bde0-157">Minimal engineering effort is required to extend the standard table-to-table maps and to include custom maps.</span></span>
+ <span data-ttu-id="5bde0-158">A kettős írás online és offline módot is támogat.</span><span class="sxs-lookup"><span data-stu-id="5bde0-158">Dual-write supports both online mode and offline mode.</span></span> <span data-ttu-id="5bde0-159">A Microsoft az egyetlen olyan vállalat, amely online és offline mód támogatását is kínálja.</span><span class="sxs-lookup"><span data-stu-id="5bde0-159">Microsoft is the only company that offers support for online and offline modes.</span></span>

## <a name="what-does-dual-write-mean-for-users-and-architects-of-crm-products"></a><span data-ttu-id="5bde0-160">Mit jelent a kettős írás a CRM-termékek felhasználói és tervezői számára?</span><span class="sxs-lookup"><span data-stu-id="5bde0-160">What does dual-write mean for users and architects of CRM products?</span></span>

<span data-ttu-id="5bde0-161">A kettős írás automatizálja a Finance and Operations alkalmazások és a Common Data Service szolgáltatás közti adatáramlást.</span><span class="sxs-lookup"><span data-stu-id="5bde0-161">Dual-write automates the data flow between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="5bde0-162">A jövőbeli kiadásokban a Dynamics 365 modellvezérelt alkalmazásainak koncepcióit (pl. ügyfél, kapcsolattartó, árajánlat és megrendelés) a közepes és a felső-közép régióban található ügyfelekre is kiterjesztik.</span><span class="sxs-lookup"><span data-stu-id="5bde0-162">In future releases, concepts in model-driven apps in Dynamics 365 (for example, customer, contact, quotation, and order) will be scaled to mid-market and upper-mid-market customers.</span></span>

<span data-ttu-id="5bde0-163">Az első verzióban az automatizálás legtöbb elemét kettős írásos megoldások kezelik.</span><span class="sxs-lookup"><span data-stu-id="5bde0-163">In the first release, most of the automation is handled by dual-write solutions.</span></span> <span data-ttu-id="5bde0-164">A későbbi verziókban ezek a megoldások a Common Data Service program részévé válnak.</span><span class="sxs-lookup"><span data-stu-id="5bde0-164">In future releases, those solutions will become part of Common Data Service.</span></span> <span data-ttu-id="5bde0-165">Ha megértjük a Common Data Service közelgő változtatásait, akkor hosszú távon erőfeszítéseket spórolhat meg.</span><span class="sxs-lookup"><span data-stu-id="5bde0-165">By understanding the upcoming changes to Common Data Service, you can save yourself effort in the long term.</span></span> <span data-ttu-id="5bde0-166">Többek között az alábbi kritikus fontosságú módosítások történtek:</span><span class="sxs-lookup"><span data-stu-id="5bde0-166">Here are some of the crucial changes:</span></span>

+ <span data-ttu-id="5bde0-167">A Common Data Service új koncepciókat fog tartalmazni, például vállalat és felek.</span><span class="sxs-lookup"><span data-stu-id="5bde0-167">Common Data Service will have new concepts, such as company and party.</span></span> <span data-ttu-id="5bde0-168">Ezek a fogalmak hatással lesznek az összes Common Data Service szolgáltatásra épített alkalmazásra, például a Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service és Dynamics 365 Field Service alkalmazásra.</span><span class="sxs-lookup"><span data-stu-id="5bde0-168">These concepts will affect all apps that are built on Common Data Service, such as Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service, and Dynamics 365 Field Service.</span></span>
+ <span data-ttu-id="5bde0-169">A tevékenységek és megjegyzések egyesülnek, és bővítésükkel támogatják a C1 (a rendszer felhasználóit) és a C2 (a rendszer ügyfeleit).</span><span class="sxs-lookup"><span data-stu-id="5bde0-169">Activities and notes are unified and expanded to support both C1s (users of the system) and C2s (customers of the system).</span></span>
+ <span data-ttu-id="5bde0-170">Íme a közelgő változások egy része a Common Data Service szolgáltatásban:</span><span class="sxs-lookup"><span data-stu-id="5bde0-170">Here are some of the upcoming changes in Common Data Service:</span></span>

    - <span data-ttu-id="5bde0-171">A decimális adattípus veszi át a pénz adattípus helyét.</span><span class="sxs-lookup"><span data-stu-id="5bde0-171">The decimal data type will replace the money data type.</span></span>
    - <span data-ttu-id="5bde0-172">A dátumérvényesség múltbéli, jelenlegi és jövőbeli dátumokat is támogatni fog ugyanazon a helyen.</span><span class="sxs-lookup"><span data-stu-id="5bde0-172">Date effectivity will support past, present, and future data in the same place.</span></span>
    - <span data-ttu-id="5bde0-173">Több támogatás áll majd rendelkezésre pénznemekkel és árfolyamokkal kapcsolatban, és felülvizsgálják az **Árfolyam** alkalmazásfejlesztési felületet (API).</span><span class="sxs-lookup"><span data-stu-id="5bde0-173">There will be more support for currency and exchange rates, and the **Exchange Rate** application programming interface (API) will be revised.</span></span>
    - <span data-ttu-id="5bde0-174">A program támogatja az egységek átváltását.</span><span class="sxs-lookup"><span data-stu-id="5bde0-174">Unit conversions will be supported.</span></span>

<span data-ttu-id="5bde0-175">A közelgő változásokkal kapcsolatos további információkért lásd: [Adatok a Common Data Service szolgáltatásban – 1. és 2. fázis](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/finance-operations-crossapp-capabilities/data-common-data-service-phase-1).</span><span class="sxs-lookup"><span data-stu-id="5bde0-175">For more information about upcoming changes, see [Data in Common Data Service – phase 1 & 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/finance-operations-crossapp-capabilities/data-common-data-service-phase-1).</span></span>
