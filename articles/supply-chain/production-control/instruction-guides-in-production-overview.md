---
title: Vegyes valóság útmutató a termelésben dolgozók számára
description: Ez a témakör azt mutatja be, hogyan lehet integrálni a Microsoft Dynamics 365 Supply Chain Management modulját a Dynamics 365 Guides alkalmazással.
author: cabeln
manager: tfehr
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkGuidesManufacturing
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: cabeln
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: d8c2da17d4e3df37c55844f0aad00f883725f741
ms.sourcegitcommit: c55fecae96b4bb27bc313ba10a97eddb9c91350a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/12/2020
ms.locfileid: "3989276"
---
# <a name="provide-mixed-reality-guides-for-workers-in-production"></a><span data-ttu-id="ee0fc-103">Vegyes valóság útmutató a termelésben dolgozók számára</span><span class="sxs-lookup"><span data-stu-id="ee0fc-103">Provide mixed-reality Guides for workers in production</span></span>

<span data-ttu-id="ee0fc-104">A termelésben dolgozók számára hasznos, ha a megfelelő időben rendelkezésre állnak a munkájukra vonatkozó megfelelő utasítások.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-104">Workers in production processes will benefit from relevant instructions that are provided at the right time in the context of their work.</span></span> <span data-ttu-id="ee0fc-105">Az *Utasítások* számos területen használhatók, ilyenek többek között: összeállítás, szerviz, műveletek, minősítés és munkavédelem.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-105">*Instructions* apply in several domains of work, including: assembly, service, operations, certification, and safety.</span></span> <span data-ttu-id="ee0fc-106">Ezeknél az alapvető vállalati funkcióknál a folyamatos betanító utasítások segítséget jelentenek a dolgozóknak a jobb teljesítményhez és a pontosabb munkavégzéshez.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-106">Across all of these core business functions, ongoing training instructions can help empower workers to achieve more and work better.</span></span>

## <a name="introduction"></a><span data-ttu-id="ee0fc-107">Bevezetés</span><span class="sxs-lookup"><span data-stu-id="ee0fc-107">Introduction</span></span>

<span data-ttu-id="ee0fc-108">Különféle módokon lehet utasításokat megadni.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-108">You can provide instructions in different ways.</span></span> <span data-ttu-id="ee0fc-109">A [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/) alkalmazást használó, azonnal használatba vehető hatékony rendszer.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-109">One efficient system that ships out of the box uses [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/).</span></span>

<span data-ttu-id="ee0fc-110">A Dynamics 365 Guides a gyakorlati oktatással nyújt a segítséget a vállalat dolgozóinak.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-110">Dynamics 365 Guides can help empower your employees with hands-on learning.</span></span> <span data-ttu-id="ee0fc-111">Szabványosított folyamatok adhatók meg, olyan részletes utasításokkal, amelyek az alkalmazottakat a szükséges eszközökhöz és alkatrészekhez irányítják, és bemutatják, hogyan kell ezeket az eszközöket valódi munkakörülmények között használni.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-111">You can define standardized processes with step-by-step instructions that guide your employees to the tools and parts they need and show employees how to use these tools in real work situations.</span></span>

<span data-ttu-id="ee0fc-112">Útmutatók csatolhatók a termelés-ellenőrzés különböző területeihez, például a következőkhöz:</span><span class="sxs-lookup"><span data-stu-id="ee0fc-112">You can attach guides to various aspects of production control including:</span></span>

- [<span data-ttu-id="ee0fc-113">Erőforrások</span><span class="sxs-lookup"><span data-stu-id="ee0fc-113">Resources</span></span>](#resources)
- [<span data-ttu-id="ee0fc-114">Erőforráscsoportok</span><span class="sxs-lookup"><span data-stu-id="ee0fc-114">Resource groups</span></span>](#resource-groups)
- [<span data-ttu-id="ee0fc-115">Kiadott termékek</span><span class="sxs-lookup"><span data-stu-id="ee0fc-115">Released products</span></span>](#released-products)
- [<span data-ttu-id="ee0fc-116">Receptúrák</span><span class="sxs-lookup"><span data-stu-id="ee0fc-116">Formulas</span></span>](#formulas)
- [<span data-ttu-id="ee0fc-117">Receptúraverziók</span><span class="sxs-lookup"><span data-stu-id="ee0fc-117">Formula versions</span></span>](#formula-versions)
- [<span data-ttu-id="ee0fc-118">Anyagjegyzékek (AJ-k)</span><span class="sxs-lookup"><span data-stu-id="ee0fc-118">Bills of material (BOMs)</span></span>](#bom)
- [<span data-ttu-id="ee0fc-119">Anyagjegyzék-verziók</span><span class="sxs-lookup"><span data-stu-id="ee0fc-119">BOM versions</span></span>](#bom-versions)
- [<span data-ttu-id="ee0fc-120">Útvonalak</span><span class="sxs-lookup"><span data-stu-id="ee0fc-120">Routes</span></span>](#routes)
- [<span data-ttu-id="ee0fc-121">Útvonalverziók</span><span class="sxs-lookup"><span data-stu-id="ee0fc-121">Route versions</span></span>](#route-versions)
- [<span data-ttu-id="ee0fc-122">Útvonalműveleti kapcsolatok</span><span class="sxs-lookup"><span data-stu-id="ee0fc-122">Route operation relations</span></span>](#route-operation-relations)

> [!NOTE]
> <span data-ttu-id="ee0fc-123">Az Eszközkezelőhöz is csatolható útmutató.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-123">You can also attach Guides with Asset Management.</span></span> <span data-ttu-id="ee0fc-124">További információ: [Dynamics 365 Supply Chain Management (Eszközkezelés) integrálása a Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md) alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-124">For more information about that option, see [Integrate Dynamics 365 Supply Chain Management (Asset Management) with Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md).</span></span>

<span data-ttu-id="ee0fc-125">Amikor egy első vonalbeli dolgozó a Supply Chain Managementen keresztül kiválaszt egy üzemi feladatot, [a releváns útmutató](#logic) megjelenik a feladatkártyán.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-125">When a first-line worker chooses a job on the shop floor through Supply Chain Management, the worker can see [the relevant guides](#logic) on the job card.</span></span> <span data-ttu-id="ee0fc-126">Ha a dolgozó kiválaszt egy adott utasítást, annak QR-kódja megjelenik a képernyőn.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-126">When the worker chooses a specific guide, a QR code for that guide is shown on the screen.</span></span> <span data-ttu-id="ee0fc-127">A dolgozó ezt követően a HoloLens használatával beolvassa a QR-kódot, amely behívja az útmutatókat, és megjelennek a szükséges utasítások.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-127">The worker then uses their HoloLens to scan the QR code, which launches Guides and shows the required instructions.</span></span>

<span data-ttu-id="ee0fc-128">A következő alszakaszok néhány olyan esetet írnak le, amikor különféle iparágakban tevékenykedő, az útmutatókat gyártási utasításokra használó vállalatok a legjobb teljesítményt érik el.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-128">The following subsections describe a few selected scenarios where companies across industries can see the biggest value when using Guides to present instructions for manufacturing.</span></span>

### <a name="assembly"></a><span data-ttu-id="ee0fc-129">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee0fc-129">Assembly</span></span>

<span data-ttu-id="ee0fc-130">![Útmutató használata összeszerelési feladatoknál](media/instruction-guides-hero-assembly.png "Útmutató használata szervizfeladatoknál")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-130">![Use Guides in assembly tasks](media/instruction-guides-hero-assembly.png "Use Guides in service tasks")</span></span>

<span data-ttu-id="ee0fc-131">Az összeszerelési műveletekre vonatkozó utasítások megmutatják a dolgozóknak a szükséges szerszámokat és alkatrészeket, valamint használatukat valódi munkakörülmények között.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-131">Instructions in assembly operations show workers the tools and parts they need and how to use them in real work situations.</span></span>

<span data-ttu-id="ee0fc-132">A termelésvezető útmutatókat hozhat létre és rendelhet hozzá, például [termelési útvonalakhoz](routes-operations.md), [műveleti kapcsolatokhoz](routes-operations.md#operation-relations), vagy [anyagjegyzékekhez](bill-of-material-bom.md).</span><span class="sxs-lookup"><span data-stu-id="ee0fc-132">Production managers can create and assign Guides, for example, for [production routes](routes-operations.md), [operation relations](routes-operations.md#operation-relations), or [bills of material](bill-of-material-bom.md).</span></span> <span data-ttu-id="ee0fc-133">A dolgozók számára így rendelkezésre állnak az adott tevékenységre vonatkozó utasítások.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-133">Workers will find the relevant instructions on the respective operation experience on the shop floor.</span></span>

### <a name="service"></a><span data-ttu-id="ee0fc-134">Szerviz</span><span class="sxs-lookup"><span data-stu-id="ee0fc-134">Service</span></span>

<span data-ttu-id="ee0fc-135">![Útmutató használata szervizfeladatoknál](media/instruction-guides-hero-service.png "Útmutató használata szervizfeladatoknál")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-135">![Use Guides in service tasks](media/instruction-guides-hero-service.png "Use Guides in service tasks")</span></span>

<span data-ttu-id="ee0fc-136">A technikusokat irányított utasításokkal látja el a munkahelyükön, hogy feleslegessé váljanak további látogatások.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-136">Equip technicians with guided instructions at the job site, eliminating the need to schedule additional visits.</span></span>

<span data-ttu-id="ee0fc-137">A szervizvezetők hozzárendelhetnek útmutatót például adott [termékekhez](../../commerce/product.md), amelyek minőség-ellenőrzésen esnek át.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-137">Service managers can assign Guides, for example, to specific [products](../../commerce/product.md) that walk through routines of quality assessment.</span></span>

### <a name="quality"></a><span data-ttu-id="ee0fc-138">Minőség</span><span class="sxs-lookup"><span data-stu-id="ee0fc-138">Quality</span></span>

<span data-ttu-id="ee0fc-139">![Útmutató használata minőségbiztosítási feladatoknál](media/instruction-guides-hero-quality.png "Útmutató használata minőségbiztosítási feladatoknál")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-139">![Use Guides in quality assurance tasks](media/instruction-guides-hero-quality.png "Use Guides in quality assurance tasks")</span></span>

<span data-ttu-id="ee0fc-140">Új folyamatok bevezetése és a következetesség növelése az alkalmazottak tudásának megismételhető eszközzé alakításával.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-140">Rollout new processes and ensure increased consistency by turning employee knowledge into a repeatable tool.</span></span>

<span data-ttu-id="ee0fc-141">A minőségbiztosítási vezetők hozzárendelhetnek útmutatót például [termékekhez](../../commerce/product.md), amelyek minőség-ellenőrzésen esnek át.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-141">Quality assurance managers can assign guides, for example, to [products](../../commerce/product.md) that walk through routines of quality assessment.</span></span>

### <a name="certifications"></a><span data-ttu-id="ee0fc-142">Tanúsítványok</span><span class="sxs-lookup"><span data-stu-id="ee0fc-142">Certifications</span></span>

<span data-ttu-id="ee0fc-143">![Útmutató használata tanúsítással kapcsolatos feladatoknál](media/instruction-guides-hero-certification.png "Útmutató használata tanúsítással kapcsolatos feladatoknál")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-143">![Use Guides for certification related tasks](media/instruction-guides-hero-certification.png "Use Guides for certification related tasks")</span></span>

<span data-ttu-id="ee0fc-144">Fontos, hogy az alkalmazottak képesek legyenek magas elvárások teljesítésére, és gyorsan észleljék, kinek és hol van szüksége segítségre.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-144">Ensure every employee meets high standards by quickly identifying who needs help and where.</span></span>

### <a name="safety"></a><span data-ttu-id="ee0fc-145">Biztonság</span><span class="sxs-lookup"><span data-stu-id="ee0fc-145">Safety</span></span>

<span data-ttu-id="ee0fc-146">![Útmutató használata munkavédelemmel kapcsolatos feladatoknál](media/instruction-guides-hero-safety.png "Útmutató használata munkavédelemmel kapcsolatos feladatoknál")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-146">![Use Guides in work safety instructions](media/instruction-guides-hero-safety.png "Use Guides in work safety instructions")</span></span>

<span data-ttu-id="ee0fc-147">Utasításokat ad, amelyek virtuálisan áttekintik a veszélyes eljárásokat, mielőtt azokat fizikai környezetben alkalmaznák.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-147">Provide instructions that walk through dangerous procedures virtually before attempting in the physical environment.</span></span> <span data-ttu-id="ee0fc-148">A vegyes valóság megközelítésével a dolgozók virtuálisan gyakorolhatják a veszélyes eljárásokat.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-148">With a mixed reality approach, workers can experience dangerous procedures virtually.</span></span>

<span data-ttu-id="ee0fc-149">A termelésvezetők külön kezelési utasításokat adhatnak meg a veszélyes anyagok kezelésére, illetve a kényes kezelési eljárásokra, utasítások hozzárendelésével a [termékelemekhez](../../commerce/product.md), [útvonalakhoz](routes-operations.md) és [műveletekhez](routes-operations.md#operation-relations).</span><span class="sxs-lookup"><span data-stu-id="ee0fc-149">Production managers can provide dedicated handling instructions for hazardous material handling or delicate handling procedures by assigning instructions to [product items](../../commerce/product.md), [routes](routes-operations.md), and [operations](routes-operations.md#operation-relations).</span></span>

## <a name="get-started-with-instructions-and-guides"></a><span data-ttu-id="ee0fc-150">Első lépések az utasítások és az útmutatók használatához</span><span class="sxs-lookup"><span data-stu-id="ee0fc-150">Get started with instructions and Guides</span></span>

<span data-ttu-id="ee0fc-151">Az utasítások engedélyezéséhez a termelési folyamatokban a Supply Chain Management biztosítja a kulcsrakész integrációt a Dynamics 365 Guides alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-151">To enable instructions in production processes, Supply Chain Management provides an out-of-the-box integration with Dynamics 365 Guides.</span></span> <span data-ttu-id="ee0fc-152">A gyártási eszközök és a munka vegyes valóságra vonatkozó utasításainak összeállításához, karbantartásához és hozzárendeléséhez engedélyezett és telepített Guides-alkalmazáspéldány szükséges.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-152">A licensed and installed application instance of Guides is required to build, maintain, and assign mixed reality instructions to production assets and work.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="ee0fc-153">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="ee0fc-153">Prerequisites</span></span>

<span data-ttu-id="ee0fc-154">A funkció használatához a rendszernek tartalmaznia kell a következőket:</span><span class="sxs-lookup"><span data-stu-id="ee0fc-154">To use this feature, your system must include the following:</span></span>

- <span data-ttu-id="ee0fc-155">Dynamics 365 Supply Chain Management 10.0.15 vagy újabb verziója</span><span class="sxs-lookup"><span data-stu-id="ee0fc-155">Dynamics 365 Supply Chain Management version 10.0.15 or later</span></span>
- <span data-ttu-id="ee0fc-156">[Kettős írás](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write) funkció a Supply Chain Management alkalmazásokhoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-156">[Dual-write](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write) for Supply Chain Management apps.</span></span>
- <span data-ttu-id="ee0fc-157">[Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) 400.0.1.48 vagy újabb verziója</span><span class="sxs-lookup"><span data-stu-id="ee0fc-157">[Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 400.0.1.48 or later</span></span>

### <a name="turn-on-the-feature"></a><span data-ttu-id="ee0fc-158">A funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="ee0fc-158">Turn on the feature</span></span>

<span data-ttu-id="ee0fc-159">A szolgáltatás elérhetővé tételéhez a rendszerén engedélyeznie kell a konfigurációs kulcsokat.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-159">To make the feature available on your system, you must enable its configuration keys.</span></span> <span data-ttu-id="ee0fc-160">Ezt csak egyszer kell elvégeznie.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-160">You only need to do this once.</span></span> <span data-ttu-id="ee0fc-161">Ehhez a rendszergazdának a következőket kell tennie:</span><span class="sxs-lookup"><span data-stu-id="ee0fc-161">To do this, an administrator must do the following:</span></span>

1. <span data-ttu-id="ee0fc-162">Állítsa a rendszert karbantartási módba a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-162">Place your system into maintenance mode as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="ee0fc-163">Lépjen a **Rendszerfelügyelet \> Beállítás \> Licenckonfiguráció** elemre.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-163">Go to **System administration \> Setup \> License configuration** .</span></span>
1. <span data-ttu-id="ee0fc-164">Bontsa ki a **Vegyes valóság** szakaszt, és jelölje be a **Vegyes valóság útmutató** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-164">Expand the **Mixed reality** section and then select the **Mixed reality guide** check box.</span></span>
1. <span data-ttu-id="ee0fc-165">Bontsa ki a **Termelésirányítás** szakaszt, és jelölje be a **Termelési utasítások** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-165">Expand the **Production management** section and then select the **Production instructions** check box.</span></span>
1. <span data-ttu-id="ee0fc-166">Kapcsolja ki a karbantartási módot a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-166">Turn off maintenance mode as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
  
## <a name="configure-how-guides-appear-on-the-shop-floor"></a><span data-ttu-id="ee0fc-167">Az Útmutatók üzemben használt felületének konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ee0fc-167">Configure how Guides appear on the shop floor</span></span>

<span data-ttu-id="ee0fc-168">Az Útmutatók üzemben használt felületének konfigurálásához folytassa itt: **Mixed Reality \> Dynamics 365 Guides \> Útmutatók integrálásának konfigurálása** .</span><span class="sxs-lookup"><span data-stu-id="ee0fc-168">To configure how Guides appear on the shop floor, go to **Mixed Reality \> Dynamics 365 Guides \> Configure Guides integration** .</span></span>

<span data-ttu-id="ee0fc-169">![Útmutató integrálásának konfigurálása a gyártáshoz](media/instruction-guides-configure-integration.png "Útmutató integrálásának konfigurálása a gyártáshoz")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-169">![Configure Guide integration for manufacturing](media/instruction-guides-configure-integration.png "Configure Guide integration for manufacturing")</span></span>

<span data-ttu-id="ee0fc-170">Állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="ee0fc-170">Set the following fields:</span></span>

- <span data-ttu-id="ee0fc-171">**CDS-környezeti altartomány** – A mezőnek már tartalmaznia kell értéket.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-171">**CDS environment subdomain** - This field should already show a value.</span></span> <span data-ttu-id="ee0fc-172">A mező annak a Common Data Service környezetnek az altartományát tartalmazza, ahol Ön létrehozza az Útmutatókat.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-172">This field holds the subdomain for the Common Data Service environment where you create your Guides.</span></span> <span data-ttu-id="ee0fc-173">Az altartomány az URL-cím első része, és általában a szervezet nevét tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-173">The subdomain is the first part of the URL and is typically named after your organization.</span></span> <span data-ttu-id="ee0fc-174">Ha például a Common Data Service URL-cím „contoso.crm4.dynamics.com”, akkor itt a *contoso* szót kell megadnia.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-174">For example, if your Common Data Service URL is "contoso.crm4.dynamics.com", you should enter *contoso* here.</span></span> <span data-ttu-id="ee0fc-175">Ez az érték használatos az útmutatók címeinek összeállításához, és beleíródik a QR-kódba.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-175">This value is used to compose addresses for your guides and will be encoded into the QR codes.</span></span>
- <span data-ttu-id="ee0fc-176">**QR-kód mérete** – Beállítja a megjelenített QR-kód méretét.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-176">**QR code size** - Set the size of the rendered QR code.</span></span> <span data-ttu-id="ee0fc-177">Olyan méret választása ajánlott, amely kitölti a képernyő nagy részét, de nem nagyobb.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-177">We recommend choosing a size that will fill most of your display screen, but not more.</span></span> <span data-ttu-id="ee0fc-178">Általában a *15* a megfelelő méret.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-178">Typically, *15* is a good value.</span></span>
- <span data-ttu-id="ee0fc-179">**QR-kód hibajavító szintje** – Beállítja a QR-kód részletességét.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-179">**QR code error correction level** - Set the granularity of the QR code.</span></span> <span data-ttu-id="ee0fc-180">A magasabb részletességgel növelheti a kód megbízhatóságát, de a **QR-kódnak** elég nagynak kell lennie ahhoz, hogy támogassa a kiválasztott korrekciós szinthez szükséges részletességi szintet.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-180">Higher granularity can help increase the code's reliability, but your **QR code size** must be large enough to support the level of detail required by your selected correction level.</span></span>


> [!TIP]
> - <span data-ttu-id="ee0fc-181">A túl nagy méretű QR-kódok megjelenítése egy kicsit hosszabb időt igényel, majd le kell kicsinyíteni, hogy ráférjen a képernyőre.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-181">QR codes sizes that are too large for your display will take a bit longer to render and then be scaled down to fit your display.</span></span> <span data-ttu-id="ee0fc-182">Ezek miatt nem előnyös.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-182">These do not provide a benefit.</span></span>
> - <span data-ttu-id="ee0fc-183">A túl kis méretű QR-kód csökkentheti a HoloLens kódolvasó képességét bizonyos környezetekben.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-183">QR code sizes that are too small may decrease the ability of HoloLens to read the code properly in some environments.</span></span>
> - <span data-ttu-id="ee0fc-184">Ajánlott a HoloLens-felhasználók által használt összes, QR-kódot megjelenítő eszköz beállításainak előzetes tesztelése.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-184">We recommend that you test the settings for each device that will display QR codes for HoloLens users.</span></span> <span data-ttu-id="ee0fc-185">Válasszon olyan beállításokat, amelyek üzemi környezetben is kielégítő olvashatóságot biztosítanak.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-185">Choose settings that provide sufficient readability in your shop floor environment.</span></span>  

## <a name="get-an-overview-of-all-guide-assignments"></a><span data-ttu-id="ee0fc-186">Az összes útmutató-hozzárendelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="ee0fc-186">Get an overview of all Guide assignments</span></span>

<span data-ttu-id="ee0fc-187">Az **Összes útmutató** lapon megtekintheti a szervezet összes elérhető útmutatóját, valamint azok összes hozzárendelését a termelési folyamatokhoz és erőforrásokhoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-187">Use the **All Guides** page to see the list of all available Guides in your organization and all assignments to your production processes and resources.</span></span> <span data-ttu-id="ee0fc-188">Megnyitásához válassza a **Vegyes valóság \> Útmutató \> Összes útmutató** elemeket.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-188">To open it, go to **Mixed reality \> Guides \> All Guides** .</span></span> <span data-ttu-id="ee0fc-189">A felső lista az összes rendelkezésre álló útmutatót jeleníti meg; a lista az itt található mezővel szűrhető.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-189">The list at the top shows all the available Guides and you can use the field here to filter the list.</span></span> <span data-ttu-id="ee0fc-190">A lenti lista az összes útmutató-hozzárendelést jeleníti meg, és egy eszköztárat tartalmaz a kezeléshez.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-190">The list at the bottom shows all Guide assignments and provides a toolbar for managing them.</span></span>

<span data-ttu-id="ee0fc-191">![Útmutatók kezelése](media/instruction-guides-allguides.png "Útmutatók kezelése")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-191">![Manage Guides](media/instruction-guides-allguides.png "Manage Guides")</span></span>

<span data-ttu-id="ee0fc-192">A következő szakaszok az útmutatókhoz társítható objektumok típusait mutatják be.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-192">The following sections describe the types of objects that you can assign Guides to.</span></span> <span data-ttu-id="ee0fc-193">Minden hozzárendelt útmutató olyan utasításokat tartalmaz, amelyek automatikusan a megfelelő gyártási feladatokhoz vannak csatolva, és amelyek elérhetők az üzemben.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-193">Each assigned guide provides instructions that are automatically attached to the respective production jobs and will be available on the shop floor.</span></span>

## <a name="associate-a-guide-to-a-resource"></a><a name="resources"></a><span data-ttu-id="ee0fc-194">Útmutató társítása erőforrással</span><span class="sxs-lookup"><span data-stu-id="ee0fc-194">Associate a Guide to a resource</span></span>

<span data-ttu-id="ee0fc-195">Adjon hozzá útmutatót egy [erőforráshoz](operations-resources.md), megfelelő termelési feladatokkal kapcsolatos útmutató létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-195">Add a Guide to a [resource](operations-resources.md) to offer the Guide in the context of relevant production jobs.</span></span>

### <a name="typical-scenario-using-resources"></a><span data-ttu-id="ee0fc-196">Jellemző példa erőforrások használatára</span><span class="sxs-lookup"><span data-stu-id="ee0fc-196">Typical scenario using resources</span></span>

<span data-ttu-id="ee0fc-197">Például csatolhat egy általános gépbiztonsági vagy kezelési utasításokat tartalmazó útmutatót az adott típusú gép egy erőforrásához.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-197">For example, you could attach a Guide with general machine security or handling instructions to a resource of type machine.</span></span> <span data-ttu-id="ee0fc-198">Ezután az útmutató elérhető lesz minden feladathoz, amelyet a gépen végeznek.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-198">Then, the Guide will be available on every job that is performed on the machine.</span></span>

### <a name="add-a-guide-to-a-resource"></a><span data-ttu-id="ee0fc-199">Útmutató hozzáadása erőforráshoz</span><span class="sxs-lookup"><span data-stu-id="ee0fc-199">Add a Guide to a resource</span></span>

<span data-ttu-id="ee0fc-200">Útmutató hozzáadása egy erőforráshoz:</span><span class="sxs-lookup"><span data-stu-id="ee0fc-200">To add a Guide to a resource:</span></span>

1. <span data-ttu-id="ee0fc-201">Válassza a **Gyártásvezérlés \> Beállítás \> Erőforrások \> Erőforrások** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-201">Go to **Production control \> Setup \> Resources \> Resources** .</span></span>
1. <span data-ttu-id="ee0fc-202">A lista ablaktáblán válassza ki azt az erőforrást, amelyhez útmutatót szeretne rendelni.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-202">From the list pane, select the resource you want to assign a Guide to.</span></span>
1. <span data-ttu-id="ee0fc-203">Bontsa ki a **Társított útmutatók** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-203">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="ee0fc-204">Válassza a **Hozzáadás** elemet a **Társított útmutatók** eszköztárból.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-204">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="ee0fc-205">A program új sort ad hozzá a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-205">A new line is added to the grid.</span></span>
1. <span data-ttu-id="ee0fc-206">Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-206">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span> <span data-ttu-id="ee0fc-207">Ha számos útmutatója van, akkor szűrheti a listát, hogy megtalálja azt, amit keres.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-207">If you have a large number of Guides, then you can filter the list to find the one you are looking for.</span></span>
    <span data-ttu-id="ee0fc-208">![Útmutatók kezelése](media/instruction-guides-allguides.png "Útmutatók kezelése")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-208">![Manage Guides](media/instruction-guides-allguides.png "Manage Guides")</span></span>

## <a name="associate-a-guide-to-a-resource-group"></a><a name="resource-groups"></a><span data-ttu-id="ee0fc-209">Útmutató társítása erőforráscsoporttal</span><span class="sxs-lookup"><span data-stu-id="ee0fc-209">Associate a Guide to a resource group</span></span>

<span data-ttu-id="ee0fc-210">Hozzáadhat útmutatót [erőforráscsoportokhoz](tasks/define-discrete-manufacturing-resource-group.md), ha gépcsoportok, gyártósorok vagy munkacellák kezelésére használja őket.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-210">You can add a guide to [resource groups](tasks/define-discrete-manufacturing-resource-group.md) if you use them to manage groups of machines, production lines, or work cells.</span></span>

### <a name="typical-scenarios-using-resource-groups"></a><span data-ttu-id="ee0fc-211">Jellemző példa erőforráscsoportok használata esetén</span><span class="sxs-lookup"><span data-stu-id="ee0fc-211">Typical scenarios using resource groups</span></span>

<span data-ttu-id="ee0fc-212">**1. példa:** Meghatározott egy erőforráscsoportot több azonos típusú géphez.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-212">**Example 1:** You have defined a resource group for several machines of the same model.</span></span> <span data-ttu-id="ee0fc-213">Ahelyett, hogy minden releváns erőforráshoz hozzárendelné a géptípus megfelelő kezelési útmutatóját, az útmutatót hozzárendelheti a géptípus erőforráscsoportjához.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-213">Instead of assigning the relevant handling instruction guide for the machine model to every relevant resource, you could instead assign the Guide to the resource group that reflects that machine model.</span></span>

<span data-ttu-id="ee0fc-214">**2. példa:** Meghatározott egy erőforráscsoportot egy különféle gépeket tartalmazó munkacella számára, és van egy útmutatója, amely általános utasításokat tartalmaz a munkacella karbantartására vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-214">**Example 2:** You have defined a resource group for a work cell that contains different machines and you have a Guide that provides general instructions for how to maintain the work cell.</span></span> <span data-ttu-id="ee0fc-215">Az útmutató a munkacella minden gyártási tevékenységére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-215">The Guide applies to any production activity in this work cell.</span></span>

### <a name="add-a-guide-to-a-resource-group"></a><span data-ttu-id="ee0fc-216">Útmutató hozzáadása erőforráscsoporthoz</span><span class="sxs-lookup"><span data-stu-id="ee0fc-216">Add a Guide to a resource group</span></span>

<span data-ttu-id="ee0fc-217">Útmutató hozzáadása egy erőforráscsoporthoz:</span><span class="sxs-lookup"><span data-stu-id="ee0fc-217">To add a Guide to a resource group:</span></span>

1. <span data-ttu-id="ee0fc-218">Válassza a **Gyártásvezérlés \> Beállítás \> Erőforrások \> Erőforráscsoportok** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-218">Go to **Production control \> Setup \> Resources \> Resource groups** .</span></span>
1. <span data-ttu-id="ee0fc-219">A lista ablaktáblán válassza ki azt az erőforráscsoportot, amelyhez útmutatót szeretne rendelni.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-219">From the list pane, select the resource group you want to assign a Guide to.</span></span>
1. <span data-ttu-id="ee0fc-220">Bontsa ki a **Társított útmutatók** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-220">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="ee0fc-221">Válassza a **Hozzáadás** elemet a **Társított útmutatók** eszköztárból.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-221">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="ee0fc-222">A program új sort ad hozzá a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-222">A new line is added to the grid.</span></span>
1. <span data-ttu-id="ee0fc-223">Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-223">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span> <span data-ttu-id="ee0fc-224">Ha számos útmutatója van, akkor szűrheti a listát, hogy megtalálja azt, amit keres.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-224">If you have a large number of Guides, then you can filter the list to find the one you are looking for.</span></span>
    <span data-ttu-id="ee0fc-225">![Útmutató hozzáadása erőforráscsoporthoz](media/instruction-guides-resourcegroup.png "Útmutató hozzáadása erőforráscsoporthoz")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-225">![Adding a Guide to a resource group](media/instruction-guides-resourcegroup.png "Adding a Guide to a resource group")</span></span>

## <a name="associate-a-guide-to-a-released-product"></a><a name="released-products"></a><span data-ttu-id="ee0fc-226">Útmutató társítása kiadott termékkel</span><span class="sxs-lookup"><span data-stu-id="ee0fc-226">Associate a Guide to a released product</span></span>

<span data-ttu-id="ee0fc-227">Minden [kiadott termékhez](../pim/tasks/create-released-product-single-company.md) hozzáadhat útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-227">You can add a guide to any [released product](../pim/tasks/create-released-product-single-company.md).</span></span>

### <a name="typical-scenario-using-released-products"></a><span data-ttu-id="ee0fc-228">Jellemző példa kiadott termékek használata esetén</span><span class="sxs-lookup"><span data-stu-id="ee0fc-228">Typical scenario using released products</span></span>

<span data-ttu-id="ee0fc-229">Termékszintű útmutatók segítenek az üzemben dolgozóknak egy adott kiadott termék vagy egy cikk kezelésével vagy mozgatásával kapcsolatos utasításokkal.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-229">Product-level Guides help shop floor workers with instructions relevant to operating or handling a specific released product or item.</span></span>

### <a name="add-a-guide-to-a-released-product"></a><span data-ttu-id="ee0fc-230">Útmutató hozzáadása kiadott termékhez</span><span class="sxs-lookup"><span data-stu-id="ee0fc-230">Add a Guide to a released product</span></span>

<span data-ttu-id="ee0fc-231">Útmutató hozzáadása egy kiadott termékhez:</span><span class="sxs-lookup"><span data-stu-id="ee0fc-231">To add a Guide to a released product:</span></span>

1. <span data-ttu-id="ee0fc-232">Válassza a **Termelési adatok kezelése \> Termékek \> Kiadott termékek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-232">Go to **Production information management \> Products \> Released products** .</span></span>
1. <span data-ttu-id="ee0fc-233">Nyissa meg a terméket, amelyhez útmutatót szeretne hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-233">Open the product you want to assign a Guide to.</span></span>
1. <span data-ttu-id="ee0fc-234">A Művelet panelen nyissa meg a **Mérnöki feladatok** lapot, és a **Nézet** csoportban válassza a **Társított útmutatók** elemet.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-234">On the Action Pane, open the **Engineer** tab and from the **View** group, select **Associated Guides** .</span></span>
1. <span data-ttu-id="ee0fc-235">Megjelenik a kiválasztott termék **Társított útmutatók** lapja.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-235">The **Associated Guides** page opens for your selected product.</span></span>
1. <span data-ttu-id="ee0fc-236">A Művelet panelen válassza a **Hozzáadás** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-236">Select **Add** on the Action Pane to add a new line to the grid.</span></span> 
1. <span data-ttu-id="ee0fc-237">Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-237">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="ee0fc-238">![Útmutató hozzáadása kiadott termékhez](media/instruction-guides-ReleasedProduct-AddGuides.png "Útmutató hozzáadása kiadott termékhez")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-238">![Adding a Guide to a released product](media/instruction-guides-ReleasedProduct-AddGuides.png "Adding a Guide to a released product")</span></span>

## <a name="associate-a-guide-to-a-formula"></a><a name="formulas"></a><span data-ttu-id="ee0fc-239">Útmutató társítása receptúrával</span><span class="sxs-lookup"><span data-stu-id="ee0fc-239">Associate a Guide to a formula</span></span>

<span data-ttu-id="ee0fc-240">Minden [receptúrához](bill-of-material-bom.md#formulas-co-products-and-by-products) hozzáadhat útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-240">You can add a guide to any [formula](bill-of-material-bom.md#formulas-co-products-and-by-products).</span></span>

### <a name="typical-scenario-using-formulas"></a><span data-ttu-id="ee0fc-241">Jellemző példa receptúrák használata esetén</span><span class="sxs-lookup"><span data-stu-id="ee0fc-241">Typical scenario using formulas</span></span>
  
<span data-ttu-id="ee0fc-242">A receptúraszintű útmutatók irányított kezelési utasításokat adnak az üzemi dolgozóknak egy formula vagy receptúra vonatkozásában.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-242">Formula-level Guides provide shop floor workers with guided handling instructions in the context of a formula or recipe.</span></span> <span data-ttu-id="ee0fc-243">Útmutató receptúraverzióhoz is hozzárendelhető.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-243">Guides can also be assigned to versions of a formula.</span></span>

> [!NOTE]
> <span data-ttu-id="ee0fc-244">A gyártási folyamatok szempontjából releváns útmutatást rendelhet receptúra alapján egy útvonalhoz, útvonalváltozathoz vagy útvonalműveleti kapcsolatokhoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-244">You can assign guidance relevant for production processes based on a formula to a route, route version, or route operation relations.</span></span>  

> <span data-ttu-id="ee0fc-245">Útmutató jelenleg nem csatolható a receptúra egyes soraihoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-245">Guides can't currently be attached to individual formula lines.</span></span>

### <a name="add-a-guide-to-a-formula"></a><span data-ttu-id="ee0fc-246">Útmutató hozzáadása receptúrához</span><span class="sxs-lookup"><span data-stu-id="ee0fc-246">Add a Guide to a formula</span></span>

<span data-ttu-id="ee0fc-247">Útmutató hozzáadása egy receptúrához:</span><span class="sxs-lookup"><span data-stu-id="ee0fc-247">To add a Guide to a formula:</span></span>

1. <span data-ttu-id="ee0fc-248">Válassza a **Termelési adatok kezelése \> Anyagjegyzékek és receptúrák \> Receptúrák** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-248">Go to **Production information management \> Bills of materials and formulas \> Formulas** .</span></span>
1. <span data-ttu-id="ee0fc-249">Nyissa meg a receptúrát, amelyhez útmutatót szeretne hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-249">Open the formula you want to assign a Guide to.</span></span>
1. <span data-ttu-id="ee0fc-250">Nyissa meg a **Fejléc** lapot a felső gyorslap fölött.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-250">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="ee0fc-251">Bontsa ki a **Társított útmutatók** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-251">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="ee0fc-252">Válassza a **Hozzáadás** elemet a **Társított útmutatók** eszköztárból.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-252">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="ee0fc-253">A program új sort ad hozzá a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-253">A new line is added to the grid.</span></span>
1. <span data-ttu-id="ee0fc-254">Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-254">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="ee0fc-255">![Útmutató hozzáadása receptúrához](media/instruction-guides-Formula.png "Útmutató hozzáadása receptúrához")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-255">![Adding a Guide to a formula](media/instruction-guides-Formula.png "Adding a Guide to a formula")</span></span>

## <a name="associate-a-guide-to-a-formula-version"></a><a name="formula-versions"></a><span data-ttu-id="ee0fc-256">Útmutató társítása receptúraverzióval</span><span class="sxs-lookup"><span data-stu-id="ee0fc-256">Associate a Guide to a formula version</span></span>

<span data-ttu-id="ee0fc-257">Minden [receptúraverzióhoz](bill-of-material-bom.md#bom-and-formula-versions) hozzáadhat útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-257">You can add a guide to any [formula version](bill-of-material-bom.md#bom-and-formula-versions).</span></span>

### <a name="typical-scenario-using-formula-versions"></a><span data-ttu-id="ee0fc-258">Jellemző példa receptúraverziók használata esetén</span><span class="sxs-lookup"><span data-stu-id="ee0fc-258">Typical scenario using formula versions</span></span>

<span data-ttu-id="ee0fc-259">A receptúrák egyedi verzióihoz csatolt útmutatók az üzemi dolgozóknak olyan utasításokat adnak, amelyek végigvezetnek a receptúra ezen verziójának elkészítésén.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-259">Guides attached to an individual version of a formula provide shop floor workers with instructions that walk through the production of that version of the formula recipe.</span></span>

> [!TIP]
> <span data-ttu-id="ee0fc-260">A gyártási folyamatok szempontjából releváns útmutatást rendelhet ezen receptúraverzió alapján egy útvonalhoz, útvonalváltozathoz vagy útvonalműveleti kapcsolatokhoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-260">You can assign guidance relevant for production processes based on this formula version to a route, route version, or route operation relations.</span></span>  

> [!NOTE]
> <span data-ttu-id="ee0fc-261">Útmutató jelenleg nem csatolható a receptúra egyes soraihoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-261">Guides can't currently be attached to individual formula lines.</span></span>

### <a name="add-a-guide-to-a-formula-version"></a><span data-ttu-id="ee0fc-262">Útmutató hozzáadása receptúraverzióhoz</span><span class="sxs-lookup"><span data-stu-id="ee0fc-262">Add a Guide to a formula version</span></span>

<span data-ttu-id="ee0fc-263">Útmutató hozzáadása egy receptúraverzióhoz:</span><span class="sxs-lookup"><span data-stu-id="ee0fc-263">To add a Guide to a formula version:</span></span>

1. <span data-ttu-id="ee0fc-264">Válassza a **Termelési adatok kezelése \> Anyagjegyzékek és receptúrák \> Receptúrák** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-264">Go to **Production information management \> Bills of materials and formulas \> Formulas** .</span></span>
1. <span data-ttu-id="ee0fc-265">Nyissa meg azt a receptúrát, amely tartalmazza azt a verziót, amelyhez útmutatót szeretne rendelni.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-265">Open the formula that includes a version that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="ee0fc-266">Nyissa meg a **Fejléc** lapot a felső gyorslap fölött.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-266">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="ee0fc-267">Válassza ki a **Receptúraverziók** gyorslapján azt a verziót, amelyhez útmutatót szeretne társítani.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-267">On the **Formula versions** FastTab, select the version you want to assign a Guide to.</span></span>
1. <span data-ttu-id="ee0fc-268">A **Receptúraverziók** eszköztáron válassza a **Társított útmutatók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-268">On the **Formula versions** toolbar, select **Associated Guides** .</span></span>
    <span data-ttu-id="ee0fc-269">![Kiválasztott receptúraverzióhoz társított útmutatók megnyitása](media/instruction-guides-FormulaVersion.png "Kiválasztott receptúraverzióhoz társított útmutatók megnyitása")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-269">![Open the Guides associated with a selected formula version](media/instruction-guides-FormulaVersion.png "Open the Guides associated with a selected formula version")</span></span>
1. <span data-ttu-id="ee0fc-270">Megjelenik a receptúraverzió **Társított útmutatók** lapja.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-270">The **Associated Guides** page opens for your formula version.</span></span>
1. <span data-ttu-id="ee0fc-271">A Művelet panelen válassza a **Hozzáadás** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-271">Select **Add** on the Action Pane to add a new line to the grid.</span></span> 
1. <span data-ttu-id="ee0fc-272">Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-272">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="ee0fc-273">![Útmutató hozzáadása receptúraverzióhoz](media/instruction-guides-FormulaVersionAddGuide.png "Útmutató hozzáadása receptúraverzióhoz")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-273">![Adding a Guide to a formula version](media/instruction-guides-FormulaVersionAddGuide.png "Adding a Guide to a formula version")</span></span>

## <a name="associate-a-guide-to-a-bill-of-materials"></a><a name="bom"></a><span data-ttu-id="ee0fc-274">Útmutató társítása anyagjegyzékhez</span><span class="sxs-lookup"><span data-stu-id="ee0fc-274">Associate a Guide to a bill of materials</span></span>

<span data-ttu-id="ee0fc-275">Minden [anyagjegyzékhez](bill-of-material-bom.md) (AJ) hozzáadható útmutató.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-275">You can add a guide to any [bill of materials](bill-of-material-bom.md) (BOM).</span></span>

### <a name="typical-scenario-using-bills-of-materials"></a><span data-ttu-id="ee0fc-276">Jellemző példa anyagjegyzékek használatára</span><span class="sxs-lookup"><span data-stu-id="ee0fc-276">Typical scenario using bills of materials</span></span>

<span data-ttu-id="ee0fc-277">Az anyagjegyzékhez csatolt útmutatók az üzemi dolgozóknak utasításokat adnak, amelyek elmagyarázzák, hogyan kell az anyagjegyzék anyagait előkészíteni és kezelni.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-277">Guides attached to a BOM provide shop floor workers with instructions that explain how to prepare and handle material from a BOM.</span></span> <span data-ttu-id="ee0fc-278">Útmutató anyagjegyzékhez is hozzárendelhető.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-278">Guides can also be assigned to versions of a BOM.</span></span>

> [!NOTE]
> <span data-ttu-id="ee0fc-279">Útmutató jelenleg nem csatolható az anyagjegyzék egyes soraihoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-279">Guides can't currently be attached to individual BOM lines.</span></span>

### <a name="add-a-guide-to-a-bill-of-materials"></a><span data-ttu-id="ee0fc-280">Útmutató hozzáadása anyagjegyzékhez</span><span class="sxs-lookup"><span data-stu-id="ee0fc-280">Add a Guide to a bill of materials</span></span>

<span data-ttu-id="ee0fc-281">Útmutató hozzáadása egy anyagjegyzékhez:</span><span class="sxs-lookup"><span data-stu-id="ee0fc-281">To add a Guide to a bill of material:</span></span>

1. <span data-ttu-id="ee0fc-282">Válassza a **Termelési adatok kezelése \> Anyagjegyzékek és receptúrák \> Anyagjegyzékek** .</span><span class="sxs-lookup"><span data-stu-id="ee0fc-282">Go to **Production information management \> Bills of materials and formulas \> Bills of materials** .</span></span>
1. <span data-ttu-id="ee0fc-283">Nyissa meg az anyagjegyzéket, amelyhez útmutatót szeretne hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-283">Open the bill of materials that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="ee0fc-284">Nyissa meg a **Fejléc** lapot a felső gyorslap fölött.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-284">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="ee0fc-285">Bontsa ki a **Társított útmutatók** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-285">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="ee0fc-286">Válassza a **Hozzáadás** elemet a **Társított útmutatók** eszköztárból.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-286">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="ee0fc-287">A program új sort ad hozzá a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-287">A new line is added to the grid.</span></span>
1. <span data-ttu-id="ee0fc-288">Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-288">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="ee0fc-289">![Útmutató hozzáadása anyagjegyzékhez](media/instruction-guides-BOM.png "Útmutató hozzáadása anyagjegyzékhez")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-289">![Adding a Guide to a BOM](media/instruction-guides-BOM.png "Adding a Guide to a BOM")</span></span>

## <a name="associate-a-guide-to-a-bill-of-materials-version"></a><a name="bom-versions"></a><span data-ttu-id="ee0fc-290">Útmutató társítása anyagjegyzék-verzióhoz</span><span class="sxs-lookup"><span data-stu-id="ee0fc-290">Associate a Guide to a bill of materials version</span></span>

<span data-ttu-id="ee0fc-291">Minden [anyagjegyzék-verzióhoz](bill-of-material-bom.md#bom-and-formula-versions) hozzáadható útmutató.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-291">You can add a guide to any [bill of materials version](bill-of-material-bom.md#bom-and-formula-versions).</span></span>

### <a name="typical-scenario-using-bill-of-materials-versions"></a><span data-ttu-id="ee0fc-292">Jellemző példa anyagjegyzék-verziók használatára</span><span class="sxs-lookup"><span data-stu-id="ee0fc-292">Typical scenario using bill of materials versions</span></span>

<span data-ttu-id="ee0fc-293">Az egyes anyagjegyzék-verziókhoz csatolt útmutatók az üzemi dolgozóknak utasításokat adnak, amelyek elmagyarázzák, hogyan kell az általános anyagjegyzéktől vagy más verzióktól eltérő anyagjegyzék-verzió anyagait előkészíteni és kezelni.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-293">Guides attached to an individual BOM version provide shop floor workers with instructions that explain how to prepare and handle material for a version of a BOM that is different from the generic BOM or other versions of it.</span></span>

> [!NOTE]
> <span data-ttu-id="ee0fc-294">Útmutató jelenleg nem csatolható az anyagjegyzék egyes soraihoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-294">Guides can't currently be attached to individual BOM lines.</span></span>

### <a name="add-a-guide-to-a-bill-of-materials-version"></a><span data-ttu-id="ee0fc-295">Útmutató hozzáadása anyagjegyzék-verzióhoz</span><span class="sxs-lookup"><span data-stu-id="ee0fc-295">Add a Guide to a bill of materials version</span></span>

<span data-ttu-id="ee0fc-296">Útmutató hozzáadása egy anyagjegyzék-verzióhoz:</span><span class="sxs-lookup"><span data-stu-id="ee0fc-296">To add a Guide to a bill of materials version:</span></span>

1. <span data-ttu-id="ee0fc-297">Válassza a **Termelési adatok kezelése \> Anyagjegyzékek és receptúrák \> Anyagjegyzékek** .</span><span class="sxs-lookup"><span data-stu-id="ee0fc-297">Go to **Production information management \> Bills of materials and formulas \> Bills of materials** .</span></span>
1. <span data-ttu-id="ee0fc-298">Nyissa meg azt az anyagjegyzéket, amely tartalmazza azt a verziót, amelyhez útmutatót szeretne rendelni.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-298">Open the BOM that includes a version that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="ee0fc-299">Nyissa meg a **Fejléc** lapot a felső gyorslap fölött.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-299">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="ee0fc-300">Válassza ki az **Anyagjegyzék-verziók** gyorslapján azt a verziót, amelyhez útmutatót szeretne társítani.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-300">On the **BOM versions** FastTab, select the version you want to assign a Guide to.</span></span>
1. <span data-ttu-id="ee0fc-301">Az **Anyagjegyzék-verziók** eszköztáron válassza a **Társított útmutatók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-301">On the **BOM versions** toolbar, select **Associated Guides** .</span></span>
    <span data-ttu-id="ee0fc-302">![Kiválasztott anyagjegyzék-verzióhoz társított útmutatók megnyitása](media/instruction-guides-BOMVersion.png "Kiválasztott anyagjegyzék-verzióhoz társított útmutatók megnyitása")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-302">![Open the Guides associated with a selected BOM version](media/instruction-guides-BOMVersion.png "Open the Guides associated with a selected BOM version")</span></span>
1. <span data-ttu-id="ee0fc-303">Megjelenik az anyagjegyzék-verzió **Társított útmutatók** lapja.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-303">The **Associated Guides** page opens for your BOM version.</span></span>
1. <span data-ttu-id="ee0fc-304">A Művelet panelen válassza a **Hozzáadás** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-304">Select **Add** on the Action Pane to add a new line to the grid.</span></span>
1. <span data-ttu-id="ee0fc-305">Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-305">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="ee0fc-306">![Útmutató hozzáadása anyagjegyzék-verzióhoz](media/instruction-guides-BOMVersionAddGuide.png "Útmutató hozzáadása anyagjegyzék-verzióhoz")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-306">![Adding a Guide to a BOM version](media/instruction-guides-BOMVersionAddGuide.png "Adding a Guide to a BOM version")</span></span>

## <a name="associate-a-guide-to-a-route"></a><a name="routes"></a><span data-ttu-id="ee0fc-307">Útmutató társítása útvonallal</span><span class="sxs-lookup"><span data-stu-id="ee0fc-307">Associate a Guide to a route</span></span>

<span data-ttu-id="ee0fc-308">Minden [útvonalhoz](routes-operations.md) hozzáadhat útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-308">You can add a guide to any [route](routes-operations.md).</span></span>

### <a name="typical-scenario-using-routes"></a><span data-ttu-id="ee0fc-309">Jellemző példa útvonalak használatára</span><span class="sxs-lookup"><span data-stu-id="ee0fc-309">Typical scenario using routes</span></span>

<span data-ttu-id="ee0fc-310">Az útvonalak általában annak meghatározására szolgálnak, hogy egy adott kiadott termék hogyan készül egy anyagjegyzék vagy anyagjegyzék-verzió alapján, és milyen erőforrások vagy erőforráscsoportok szükségesek a gyártáshoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-310">Routes are typically used to specify how a certain released product shall be produced based on a BOM or BOM version and with a set of resources or resource groups.</span></span>

<span data-ttu-id="ee0fc-311">Rendeljen hozzá útmutatót egy útvonalhoz, hogy részletes utasításokat adhasson az adott gyártási folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-311">Assign a Guide to a route to provide step-by-step instructions for the respective production process.</span></span>

### <a name="add-a-guide-to-a-route"></a><span data-ttu-id="ee0fc-312">Útmutató hozzáadása útvonalhoz</span><span class="sxs-lookup"><span data-stu-id="ee0fc-312">Add a Guide to a route</span></span>

<span data-ttu-id="ee0fc-313">Útmutató hozzáadása egy útvonalhoz:</span><span class="sxs-lookup"><span data-stu-id="ee0fc-313">To add a Guide to a route:</span></span>

1. <span data-ttu-id="ee0fc-314">Válassza a **Gyártásvezérlés \> Minden útvonal** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-314">Go to **Production control \> All routes** .</span></span>
1. <span data-ttu-id="ee0fc-315">Nyissa meg az útvonalat, amelyhez útmutatót szeretne hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-315">Open the route that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="ee0fc-316">Bontsa ki a **Társított útmutatók** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-316">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="ee0fc-317">Válassza a **Hozzáadás** elemet a **Társított útmutatók** eszköztárból.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-317">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="ee0fc-318">A program új sort ad hozzá a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-318">A new line is added to the grid.</span></span>
1. <span data-ttu-id="ee0fc-319">Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-319">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="ee0fc-320">![Útmutató hozzáadása útvonalhoz](media/instruction-guides-Route.png "Útmutató hozzáadása útvonalhoz")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-320">![Adding a Guide to a route](media/instruction-guides-Route.png "Adding a Guide to a route")</span></span>

## <a name="associate-a-guide-to-a-route-version"></a><a name="route-versions"></a><span data-ttu-id="ee0fc-321">Útmutató társítása útvonalverzióval</span><span class="sxs-lookup"><span data-stu-id="ee0fc-321">Associate a Guide to a route version</span></span>

<span data-ttu-id="ee0fc-322">Minden [útvonalverzióhoz](routes-operations.md#route-versions) hozzáadhat útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-322">You can add a guide to any [route version](routes-operations.md#route-versions).</span></span>

### <a name="typical-scenario-using-route-versions"></a><span data-ttu-id="ee0fc-323">Jellemző példa útvonalverziók használatára</span><span class="sxs-lookup"><span data-stu-id="ee0fc-323">Typical scenario using route versions</span></span>

<span data-ttu-id="ee0fc-324">Az útvonalverziók általában meglévő útvonalon alapuló termelési folyamatok változatainak meghatározására szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-324">Routes versions are typically used to specify variants of production processes based on an existing route.</span></span> <span data-ttu-id="ee0fc-325">Minden útvonalverzióhoz különböző útmutatók rendelhetők hozzá.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-325">You can assign different Guides to each route version.</span></span>

### <a name="add-a-guide-to-a-route-version"></a><span data-ttu-id="ee0fc-326">Útmutató hozzáadása útvonalverzióhoz</span><span class="sxs-lookup"><span data-stu-id="ee0fc-326">Add a Guide to a route version</span></span>

<span data-ttu-id="ee0fc-327">Útmutató hozzáadása egy útvonalverzióhoz:</span><span class="sxs-lookup"><span data-stu-id="ee0fc-327">To add a Guide to a route version:</span></span>

1. <span data-ttu-id="ee0fc-328">Válassza a **Gyártásvezérlés \> Minden útvonal** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-328">Go to **Production control \> All routes** .</span></span>
1. <span data-ttu-id="ee0fc-329">Nyissa meg az útvonalat, amelyhez útmutatót szeretne hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-329">Open the route that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="ee0fc-330">Válassza ki a **Verziók** gyorslapján azt a verziót, amelyhez útmutatót szeretne társítani.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-330">On the **Versions** FastTab, select the version you want to assign a Guide to.</span></span>
1. <span data-ttu-id="ee0fc-331">A **Verziók** eszköztáron válassza a **Társított útmutatók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-331">On the **Versions** toolbar, select **Associated Guides** .</span></span>
    <span data-ttu-id="ee0fc-332">![Kiválasztott útvonalverzióhoz társított útmutatók megnyitása](media/instruction-guides-RouteVersion.png "Kiválasztott útvonalverzióhoz társított útmutatók megnyitása")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-332">![Open the Guides associated with a selected route version](media/instruction-guides-RouteVersion.png "Open the Guides associated with a selected route version")</span></span>
1. <span data-ttu-id="ee0fc-333">Megjelenik az anyagjegyzék-verzió **Társított útmutatók** lapja.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-333">The **Associated Guides** page opens for your BOM version.</span></span>
1. <span data-ttu-id="ee0fc-334">A Művelet panelen válassza a **Hozzáadás** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-334">Select **Add** on the Action Pane to add a new line to the grid.</span></span>
1. <span data-ttu-id="ee0fc-335">Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-335">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="ee0fc-336">![Útmutató hozzáadása útvonalverzióhoz](media/instruction-guides-RouteVersionAddGuide.png "Útmutató hozzáadása útvonalverzióhoz")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-336">![Adding a Guide to a route version](media/instruction-guides-RouteVersionAddGuide.png "Adding a Guide to a route version")</span></span>

## <a name="associate-a-guide-to-a-route-operation-relation"></a><a name="route-operation-relations"></a><span data-ttu-id="ee0fc-337">Útmutató társítása útvonalműveleti kapcsolattal</span><span class="sxs-lookup"><span data-stu-id="ee0fc-337">Associate a Guide to a route operation relation</span></span>

<span data-ttu-id="ee0fc-338">Minden [útvonalműveleti kapcsolathoz](routes-operations.md#operation-relations) hozzáadhat útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-338">You can add a guide to any [route operation relation](routes-operations.md#operation-relations).</span></span>

### <a name="typical-scenario-using-route-operation-relations"></a><span data-ttu-id="ee0fc-339">Jellemző példa útvonalműveleti kapcsolatok használatára</span><span class="sxs-lookup"><span data-stu-id="ee0fc-339">Typical scenario using route operation relations</span></span>

<span data-ttu-id="ee0fc-340">A műveleti kapcsolatok a legspecifikusabb módja annak, hogy útmutatást adjunk a termékfolyamathoz és a kapcsolódó műveletekhez.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-340">Operation relations are the most specific way to add guidance to a product process and its related operations.</span></span> <span data-ttu-id="ee0fc-341">Megadhat útmutatást az útvonal minden egyes műveletéhez, és különböző útmutatást adhat meg az útvonalhoz megadott bármilyen típusú objektumkapcsolat-kontextushoz, például adott cikkekhez, konfigurációkhoz és egyebekhez.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-341">You can specify guidance for each operation in a route and specify different guidance for any type of relation context specified for a route, such as for specific items, configurations, and more.</span></span> <span data-ttu-id="ee0fc-342">Meghatározhatja azt is, hogy a művelet mely szakaszaira vonatkozzon az útmutató (például beállítás, várakozás, feldolgozás vagy szállítás).</span><span class="sxs-lookup"><span data-stu-id="ee0fc-342">You can also specify to which stages in the operation the guidance applies (such as setup, queueing, process, or transport).</span></span>

> [!NOTE]
> <span data-ttu-id="ee0fc-343">Ha egy útvonal több működési relációjához ad meg útmutatót, akkor ezek között az útmutatók között csak a létrehozott munkához tartozó legspecifikusabb kapcsolat útmutatója jelenik meg az üzemben.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-343">If you specify guides for several operation relations of a route, among those guides, only the guide from the most specific relation will be show on the shop floor for the generated job.</span></span>

### <a name="add-a-guide-to-a-route-operation-relation"></a><span data-ttu-id="ee0fc-344">Útmutató hozzáadása útvonalműveleti kapcsolathoz</span><span class="sxs-lookup"><span data-stu-id="ee0fc-344">Add a Guide to a route operation relation</span></span>

<span data-ttu-id="ee0fc-345">Útmutató hozzáadása egy útvonalműveleti kapcsolathoz:</span><span class="sxs-lookup"><span data-stu-id="ee0fc-345">To add a Guide to a route operation relation:</span></span>

1. <span data-ttu-id="ee0fc-346">Válassza a **Gyártásvezérlés \> Minden útvonal** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-346">Go to **Production control \> All routes** .</span></span>
1. <span data-ttu-id="ee0fc-347">Nyissa meg az útvonalat, amelyhez útmutatót szeretne hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-347">Open the route that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="ee0fc-348">A Művelet panelen nyissa meg az **Útvonal** lapot, és a **Karbantartás** csoportban válassza az **Útvonal részletei** elemet.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-348">On the Action Pane, open the **Route** tab and from the **Maintain** group, select **Route details** .</span></span>
1. <span data-ttu-id="ee0fc-349">A kiválasztott útvonalhoz megnyílik az **Útvonal részletei** oldal.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-349">The **Route details** page opens for your selected rout.</span></span>
1. <span data-ttu-id="ee0fc-350">A felső rácsban válassza ki azt a műveletet, amelyhez útmutatást szeretne megadni.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-350">In the top grid, select the operation you want to provide guidance for.</span></span>
1. <span data-ttu-id="ee0fc-351">Az alsó rácsban válasszon egy adott kapcsolatot (vagy az általános **Minden** kapcsolatot).</span><span class="sxs-lookup"><span data-stu-id="ee0fc-351">In the bottom grid, select a specific relation (or the generic **All** relation).</span></span>
    <span data-ttu-id="ee0fc-352">![Válasszon egy műveletet, majd egy kapcsolatot.](media/instruction-guides-RouteOperationRelation.png "Művelet, majd egy kapcsolat kiválasztása")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-352">![Select an operation and then a relation](media/instruction-guides-RouteOperationRelation.png "Select an operation and then a relation")</span></span>
1. <span data-ttu-id="ee0fc-353">Az alsó rács fölött nyissa meg a **Társított útmutatók** lapot.  ![A Társított útmutatók lap](media/instruction-guides-RouteOperationRelation-AddGuide.png "Társított útmutatók lap")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-353">Above the bottom gird, open the **Associated Guides** tab.  ![The Associated Guides tab](media/instruction-guides-RouteOperationRelation-AddGuide.png "The Associated Guides tab")</span></span>
1. <span data-ttu-id="ee0fc-354">Válassza az alsó rács tetején látható eszköztár **Hozzáadás** elemét, ha új sort szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-354">Select **Add** from the toolbar at the top of the bottom grid to add a new line to the grid.</span></span>
1. <span data-ttu-id="ee0fc-355">Az új sorhoz a **Név** oszlop legördülő listájából válassza ki a hozzárendelni kívánt útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-355">For the new row, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span> <span data-ttu-id="ee0fc-356">A sor többi részén jelölje be a megfelelő jelölőnégyzetet, ha a kiválasztott útmutatónak elérhetőnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-356">In the rest of the row, select the check box for each context where the selected Guide should be available.</span></span>

> [!NOTE]
> <span data-ttu-id="ee0fc-357">A műveletek mindegyik szakaszához hozzáadhat egy vagy több útmutatót.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-357">You can add one or more guides for each stage of each operation.</span></span>

## <a name="select-guides-from-the-shop-floor-execution-interface"></a><span data-ttu-id="ee0fc-358">Útmutatók kiválasztása az üzemi végrehajtási felületen</span><span class="sxs-lookup"><span data-stu-id="ee0fc-358">Select guides from the shop floor execution interface</span></span>

<span data-ttu-id="ee0fc-359">Amikor egy dolgozó megnyit egy feladatlistát az üzemi végrehajtási felületen, a Supply Chain Management megkeresi az adott feladathoz tartozó útmutatókat.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-359">When a worker opens a job list on the shop floor execution interface, Supply Chain Management finds the relevant guides for the jobs shown.</span></span> <span data-ttu-id="ee0fc-360">Az **Útmutatók** gomb megnyomása kilistázza a megfelelő útmutatókat.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-360">Use the **Guides** button to view the relevant guides.</span></span>

<span data-ttu-id="ee0fc-361">![Útmutatók gomb az üzemi végrehajtási felületen](media/instruction-guides-Shopfloor1.png "Útmutatók gomb az üzemi végrehajtási felületen")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-361">![Guides button in the shop floor execution interface](media/instruction-guides-Shopfloor1.png "Guides button in the shop floor execution interface")</span></span>

<span data-ttu-id="ee0fc-362">Ezután tegyen fel egy HoloLens-t, majd pillantson a QR-kódra, és aktiválja a megfelelő útmutatót, és elérhetővé válik a megfelelő útmutató.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-362">Then put on a HoloLens and access the respective guide by glancing at the QR code and activating the respective Guide.</span></span>

<span data-ttu-id="ee0fc-363">![QR-kód az útmutató eléréséhez HoloLens](media/instruction-guides-Shopfloor2.png "QR-kód az útmutatók HoloLens segítségével való eléréséhez") segítségével</span><span class="sxs-lookup"><span data-stu-id="ee0fc-363">![QR code to access guides using a HoloLens](media/instruction-guides-Shopfloor2.png "QR code to access guides using a HoloLens")</span></span>

## <a name="resolving-the-logic-for-selecting-guides"></a><a name="logic"></a><span data-ttu-id="ee0fc-364">Az útmutatók kiválasztásánál alkalmazott logika meghatározása</span><span class="sxs-lookup"><span data-stu-id="ee0fc-364">Resolving the logic for selecting Guides</span></span>

<span data-ttu-id="ee0fc-365">Útmutatókat hozzáadhat a következő gyártási adatokhoz:</span><span class="sxs-lookup"><span data-stu-id="ee0fc-365">You can add Guides to the following production data:</span></span>

- [<span data-ttu-id="ee0fc-366">Erőforrások</span><span class="sxs-lookup"><span data-stu-id="ee0fc-366">Resources</span></span>](#resources)
- [<span data-ttu-id="ee0fc-367">Erőforráscsoportok</span><span class="sxs-lookup"><span data-stu-id="ee0fc-367">Resource groups</span></span>](#resource-groups)
- [<span data-ttu-id="ee0fc-368">Kiadott termékek</span><span class="sxs-lookup"><span data-stu-id="ee0fc-368">Released products</span></span>](#released-products)
- [<span data-ttu-id="ee0fc-369">Receptúrák</span><span class="sxs-lookup"><span data-stu-id="ee0fc-369">Formulas</span></span>](#formulas)
- [<span data-ttu-id="ee0fc-370">Receptúraverziók</span><span class="sxs-lookup"><span data-stu-id="ee0fc-370">Formula versions</span></span>](#formula-versions)
- [<span data-ttu-id="ee0fc-371">Anyagjegyzékek (AJ-k)</span><span class="sxs-lookup"><span data-stu-id="ee0fc-371">Bills of material (BOMs)</span></span>](#bom)
- [<span data-ttu-id="ee0fc-372">Anyagjegyzék-verziók</span><span class="sxs-lookup"><span data-stu-id="ee0fc-372">BOM versions</span></span>](#bom-versions)
- [<span data-ttu-id="ee0fc-373">Útvonalak</span><span class="sxs-lookup"><span data-stu-id="ee0fc-373">Routes</span></span>](#routes)
- [<span data-ttu-id="ee0fc-374">Útvonalverziók</span><span class="sxs-lookup"><span data-stu-id="ee0fc-374">Route versions</span></span>](#route-versions)
- [<span data-ttu-id="ee0fc-375">Útvonalműveleti kapcsolatok</span><span class="sxs-lookup"><span data-stu-id="ee0fc-375">Route operation relations</span></span>](#route-operation-relations)

<span data-ttu-id="ee0fc-376">Amikor a Supply Chain Management létrehozza a termelés számára a feladatokat, akkor ezekből a forrásokból összegyűjti a vonatkozó útmutatókat.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-376">When Supply Chain Management generates the jobs for the production floor, it will collect the relevant Guides from those sources.</span></span> <span data-ttu-id="ee0fc-377">Vegye figyelembe a következő fontos szabályokat.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-377">Take note of the following important rules.</span></span>

- <span data-ttu-id="ee0fc-378">Ha anyagjegyzék-verziót vagy receptúraverziót csatol útvonalhoz vagy termelési rendeléshez, akkor az ehhez a verzióhoz kapcsolódó útmutatók, valamint a verzió szülő anyagjegyzékéhez vagy receptúrájához csatolt útmutatók is megjelennek a feladaton.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-378">If you attach a BOM version or formula version to a route or production order, then any Guides attached to this version, and also the Guides attached to the parent BOM or formula of that version, will be shown on the job.</span></span>
- <span data-ttu-id="ee0fc-379">Ha útvonalverziót csatol termelési rendeléshez, akkor az ehhez a verzióhoz kapcsolódó útmutatók, valamint a verzió szülő útvonalhoz csatolt útmutatói is megjelennek a feladaton.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-379">If you attach a route version to a production order, then any Guides attached to this version, and also the Guides attached to the parent route of that version, will be shown on the job.</span></span>
- <span data-ttu-id="ee0fc-380">Ha több útvonalműveleti kapcsolatot határoz meg, amelyek tartalmazzák az *összes* kapcsolatot, és útmutatókat rendelnek hozzájuk, akkor csak munkához tartozó legspecifikusabb kapcsolat útmutatói jelennek meg a feladaton.</span><span class="sxs-lookup"><span data-stu-id="ee0fc-380">If you define several route operation relations that include the *All* relation and assign Guides to those, only the Guides from the most specific relation will be shown for the job.</span></span>  

<span data-ttu-id="ee0fc-381">![Diagram a vonatkozó útmutatók feloldásához](media/instruction-guides-Resolve.png "Diagram a vonatkozó útmutatók feloldásához")</span><span class="sxs-lookup"><span data-stu-id="ee0fc-381">![Diagram on resolving the relevant Guides](media/instruction-guides-Resolve.png "Diagram on resolving the relevant Guides")</span></span>