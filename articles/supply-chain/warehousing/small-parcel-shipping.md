---
title: Kis csomagok szállítása
description: Ez a témakör a kis csomagok szállítása (SPS) funkcióról nyújt tájékoztatást. Ez a funkció lehetővé teszi, hogy a Microsoft Dynamics 365 Supply Chain Management részleteket bocsásson a szállítmányozó rendelkezésére egy csomagolt tárolóról, majd egy szállítási címkét, szállítási díjat és nyomon követési számot fogadjon a szállítmányozótól.
author: Mirzaab
manager: tfehr
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRateEngine, TMSCarrier, CustTable, TMSShippingCarrierCustomerAccount, TMSSmallParcelShippingFeature
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-08
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 37f07139853c30da25c067a3d736b4b9bf4eb361
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501174"
---
# <a name="small-parcel-shipping"></a><span data-ttu-id="6b048-104">Kis csomagok szállítása</span><span class="sxs-lookup"><span data-stu-id="6b048-104">Small parcel shipping</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="6b048-105">A kis csomagszállítás (SPS) szolgáltatás lehetővé teszi a Microsoft Dynamics 365 Supply Chain Management számára, hogy közvetlenül kommunikáljon a szállítmányozókkal azáltal, hogy keretrendszert biztosít a szolgáltatói API-kon keresztüli kommunikációhoz.</span><span class="sxs-lookup"><span data-stu-id="6b048-105">The small parcel shipping (SPS) feature enables Microsoft Dynamics 365 Supply Chain Management to interact directly with shipping carriers by providing a framework for communication through carrier APIs.</span></span> <span data-ttu-id="6b048-106">Ez a funkció akkor hasznos, ha az egyes értékesítési rendeléseket kereskedelmi szállítmányozókon keresztül szállítja ki, nem pedig konténeres vagy kisebb, mint a truckload szállítással.</span><span class="sxs-lookup"><span data-stu-id="6b048-106">This functionality is useful when you're shipping individual sales orders via commercial shipping carriers instead of using container shipping or less-than-truckload (LTL) shipping.</span></span>

<span data-ttu-id="6b048-107">Az SPS szolgáltatás egy külön *Díjazási motoron* keresztül kommunikál a szállítmányozóval.</span><span class="sxs-lookup"><span data-stu-id="6b048-107">The SPS feature interacts with your shipping carrier through a dedicated *rate engine*.</span></span> <span data-ttu-id="6b048-108">A szervezetnek a szállítmányozói vagy szállítmányozói központ szolgáltatással együttműködve ki kell dolgoznia ezt a díjazási motort.</span><span class="sxs-lookup"><span data-stu-id="6b048-108">Your organization must develop this rate engine in collaboration with your carrier or carrier hub service.</span></span> <span data-ttu-id="6b048-109">Ez díjazási motor lehetővé teszi, hogy a Supply Chain Management részleteket bocsásson az ön szállítmányozója rendelkezésére egy csomagolt tárolóról, majd egy szállítási címkét, szállítási díjat és nyomon követési számot fogadjon a szállítmányozótól.</span><span class="sxs-lookup"><span data-stu-id="6b048-109">The rate engine enables Supply Chain Management to submit details about a packed container to your carrier, and then receive a shipping label, shipping rate, and tracking number back from that carrier.</span></span>

<span data-ttu-id="6b048-110">A visszaküldött szállítási díj vegyes költségként hozzáadódik a kapcsolódó értékesítési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="6b048-110">The shipping rate that is returned is added to the associated sales order as a miscellaneous charge.</span></span> <span data-ttu-id="6b048-111">A visszaküldött levélcímke ezután automatikusan kinyomtatható egy Zebra programnyelvet (ZPL) használó nyomtató segítségével, és alkalmazható a szállítmányra.</span><span class="sxs-lookup"><span data-stu-id="6b048-111">The shipping label that is returned can then automatically be printed by using a Zebra Programming Language (ZPL) printer and applied to the shipment.</span></span> <span data-ttu-id="6b048-112">A szállítmányozó leolvassa ezt a levélcímkét, amikor felveszi a csomagokat a raktárban.</span><span class="sxs-lookup"><span data-stu-id="6b048-112">The carrier will scan this shipping label when it picks up the packages at your warehouse.</span></span>

## <a name="prepare-your-system-to-support-sps"></a><span data-ttu-id="6b048-113">A rendszer előkészítése az SPS támogatására</span><span class="sxs-lookup"><span data-stu-id="6b048-113">Prepare your system to support SPS</span></span>

<span data-ttu-id="6b048-114">Az SPS funkció használatához először be kell kapcsolnia az SPS szolgáltatást a Funkciókezelésben, hozzá kell adnia az ön díjazási motorját, és be kell állítani a **Szállításkezelés** és a **Raktárkezelés** modulokat a támogatására.</span><span class="sxs-lookup"><span data-stu-id="6b048-114">Before you can start to use SPS functionality, you must turn on the SPS feature in Feature management, add your rate engine, and set up the **Transportation management** and **Warehouse management** modules to support it.</span></span>

### <a name="turn-on-the-sps-feature"></a><span data-ttu-id="6b048-115">Az SPS funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="6b048-115">Turn on the SPS feature</span></span>

<span data-ttu-id="6b048-116">Az SPS funkció használata előtt be kell azt kapcsolnia saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="6b048-116">Before you can use the SPS feature, it must be turned on in your system.</span></span> <span data-ttu-id="6b048-117">A rendszergazdák használhatják a [Funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterület a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="6b048-117">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="6b048-118">A funkció a következő módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="6b048-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="6b048-119">**Modul:** *Szállításkezelés*</span><span class="sxs-lookup"><span data-stu-id="6b048-119">**Module:** *Transportation management*</span></span>
- <span data-ttu-id="6b048-120">**Funkció neve:** *Kiscsomagos szállítás*</span><span class="sxs-lookup"><span data-stu-id="6b048-120">**Feature name:** *Small parcel shipping*</span></span>

### <a name="deploy-and-set-up-rate-engines"></a><span data-ttu-id="6b048-121">Díjazási motorok telepítése és beállítása</span><span class="sxs-lookup"><span data-stu-id="6b048-121">Deploy and set up rate engines</span></span>

<span data-ttu-id="6b048-122">A Supply Chain Management nem tartalmaz díjazási motorokat.</span><span class="sxs-lookup"><span data-stu-id="6b048-122">Supply Chain Management doesn't include any rate engines.</span></span> <span data-ttu-id="6b048-123">Be kell szereznie vagy létre kell hoznia minden szükséges díjazási motort, majd hozzá kell őket adni a rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="6b048-123">You must obtain or create any rate engines that you require, and then add them to your system.</span></span> <span data-ttu-id="6b048-124">A Microsoft azonban egy bemutató díjazási motort biztosít, amely használható tesztelésre.</span><span class="sxs-lookup"><span data-stu-id="6b048-124">However, Microsoft provides a demo rate engine that you can use for testing.</span></span>

#### <a name="download-and-deploy-the-demo-rate-engine"></a><span data-ttu-id="6b048-125">A bemutató díjazási motor letöltése és telepítése</span><span class="sxs-lookup"><span data-stu-id="6b048-125">Download and deploy the demo rate engine</span></span>

<span data-ttu-id="6b048-126">Kövesse az alábbi lépéseket a bemutató díjazási motor letöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="6b048-126">Follow these steps to get the demo rate engine.</span></span>

1. <span data-ttu-id="6b048-127">A GitHub szolgáltatásban töltse le a [dinamikus csatolású függvénytárat (DLL) a bemutató díjazási motorjához](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).</span><span class="sxs-lookup"><span data-stu-id="6b048-127">On GitHub, download the [dynamic-link library (DLL) for the demo rate engine](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).</span></span>
1. <span data-ttu-id="6b048-128">Mentse a DLL-fájlt a Supply Chain Management kiszolgálóra az **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin** mappába.</span><span class="sxs-lookup"><span data-stu-id="6b048-128">On your Supply Chain Management server, save the DLL in the **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin** folder.</span></span>

#### <a name="create-and-deploy-functional-rate-engines"></a><span data-ttu-id="6b048-129">Funkcionális díjazási motorok létrehozása és telepítése</span><span class="sxs-lookup"><span data-stu-id="6b048-129">Create and deploy functional rate engines</span></span>

<span data-ttu-id="6b048-130">A funkcionális díjazási motorok termelési vagy tesztkörnyezetben való felhasználhatósága érdekében történő létrehozásával és telepítésével kapcsolatban a következő témakörök tartalmaznak tájékoztatást:</span><span class="sxs-lookup"><span data-stu-id="6b048-130">For information about how to create and deploy functional rate engines so that they can be used in a production or test environment, see the following topics:</span></span>

- [<span data-ttu-id="6b048-131">Új szállításkezelő motor létrehozása</span><span class="sxs-lookup"><span data-stu-id="6b048-131">Create a new transportation management engine</span></span>](../transportation/create-new-transportation-management-engine.md)
- [<span data-ttu-id="6b048-132">Szállításkezelő kalkulátorok beállítása</span><span class="sxs-lookup"><span data-stu-id="6b048-132">Set up transportation management engines</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-transportation-management-engines)

<span data-ttu-id="6b048-133">Az SPS díjazási motor létrehozásáról további információ: [Kiscsomagos szállítás: A kiscsomagos szállítás funkcióinak alkalmazása a Microsoft Dynamics 365 szolgáltatásban](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).</span><span class="sxs-lookup"><span data-stu-id="6b048-133">For more information about how to create an SPS rate engine, see the following blog post: [Small Parcel Shipping: How to leverage small parcel shipping functionality in Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).</span></span>

#### <a name="set-up-a-rate-engine-in-supply-chain-management"></a><span data-ttu-id="6b048-134">Díjazási motor beállítása a Supply Chain Management szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="6b048-134">Set up a rate engine in Supply Chain Management</span></span>

<span data-ttu-id="6b048-135">Miután létrehozta és telepítette az SPS díjazási motorját, a következő lépések szerint állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="6b048-135">After you've created and deployed a rate engine for SPS, follow these steps to set it up.</span></span>

1. <span data-ttu-id="6b048-136">Lépjen a **Szállításkezelés \> Beállítás \> Motorok \> Díjazási motor** elemre.</span><span class="sxs-lookup"><span data-stu-id="6b048-136">Go to **Transportation management \> Setup \> Engines \> Rate engine**.</span></span>
1. <span data-ttu-id="6b048-137">A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="6b048-137">On the Action Pane, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="6b048-138">Az új sorban állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="6b048-138">In the new row, set the following fields:</span></span>

    - <span data-ttu-id="6b048-139">**Minősítési motor** – adja meg a díjazási motor egyedi nevét.</span><span class="sxs-lookup"><span data-stu-id="6b048-139">**Rating engine** – Enter a unique name for the rate engine.</span></span> <span data-ttu-id="6b048-140">Ha bemutató díjazási motort használ, adja meg a *Bemutató díjazási motor* értéket.</span><span class="sxs-lookup"><span data-stu-id="6b048-140">If you're using the demo rate engine, enter *Demo rate engine*.</span></span>
    - <span data-ttu-id="6b048-141">**Név** – adja meg a díjazási motor rövid leírását.</span><span class="sxs-lookup"><span data-stu-id="6b048-141">**Name** – Enter a short description of the rate engine.</span></span> <span data-ttu-id="6b048-142">Ha bemutató díjazási motort használ, adja meg a *Bemutató díjazási motor* értéket.</span><span class="sxs-lookup"><span data-stu-id="6b048-142">If you're using the demo rate engine, enter *Demo rate engine*.</span></span>
    - <span data-ttu-id="6b048-143">**Minősítési metaadatok azonosítója** – válassza ki a díjszámítás alapját.</span><span class="sxs-lookup"><span data-stu-id="6b048-143">**Rating metadata ID** – Select the basis that should be used to calculate your rate.</span></span> <span data-ttu-id="6b048-144">Például a díj a távolság alapján számítható ki.</span><span class="sxs-lookup"><span data-stu-id="6b048-144">For example, your rate might be calculated based on distance.</span></span> <span data-ttu-id="6b048-145">Ha bemutató díjazási motort használ, ezt a mezőt üresen hagyhatja.</span><span class="sxs-lookup"><span data-stu-id="6b048-145">If you're using the demo rate engine, you can leave this field blank.</span></span>
    - <span data-ttu-id="6b048-146">**Kalkulátorszerelvény** – adja meg a telepített DLL-csomag fájlnevét.</span><span class="sxs-lookup"><span data-stu-id="6b048-146">**Engine assembly** – Enter the file name of the DLL package that you deployed.</span></span> <span data-ttu-id="6b048-147">Ha bemutató díjazási motort használ, adja meg a *TMSSmallParcelShippingEngine.dll* értéket.</span><span class="sxs-lookup"><span data-stu-id="6b048-147">If you're using the demo rate engine, enter *TMSSmallParcelShippingEngine.dll*.</span></span>
    - <span data-ttu-id="6b048-148">**Kalkulátorosztály** – adja meg a díjazási motorban meghatározott osztálynevet.</span><span class="sxs-lookup"><span data-stu-id="6b048-148">**Engine class** – Enter the class name that was established for your rate engine.</span></span> <span data-ttu-id="6b048-149">Ha bemutató díjazási motort használ, adja meg a *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine* értéket.</span><span class="sxs-lookup"><span data-stu-id="6b048-149">If you're using the demo rate engine, enter *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="6b048-150">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="6b048-150">Example scenario</span></span>

<span data-ttu-id="6b048-151">A példa azt mutatja be, hogyan lehet beállítani és használni az SPS-t, miután a témakörben korábban leírtak szerint előkészítette a rendszert.</span><span class="sxs-lookup"><span data-stu-id="6b048-151">This example scenario shows how to set up and use SPS after you've prepared your system as described earlier in this topic.</span></span> <span data-ttu-id="6b048-152">Ez az eset a korábban említett bemutató díjazási motort használja.</span><span class="sxs-lookup"><span data-stu-id="6b048-152">This scenario uses the previously mentioned demo rate engine.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="6b048-153">A bemutató adatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="6b048-153">Make demo data available</span></span>

<span data-ttu-id="6b048-154">Ha ezt a forgatókönyvet az itt megadott bemutatórekordok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [bemutatóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak.</span><span class="sxs-lookup"><span data-stu-id="6b048-154">To work through this scenario by using the demo records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="6b048-155">Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.</span><span class="sxs-lookup"><span data-stu-id="6b048-155">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="6b048-156">Forgatókönyv beállítása</span><span class="sxs-lookup"><span data-stu-id="6b048-156">Set up the scenario</span></span>

<span data-ttu-id="6b048-157">Ebben a példában bemutató szállítmányozónak, szállítmányozócsoportnak, csomagolási irányelvnek és csomagolási profilnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="6b048-157">For this example scenario, you must have a demo carrier, carrier group, packing policy, and packing profile.</span></span> <span data-ttu-id="6b048-158">Az alábbi alszakaszok az esethez szükséges rekordok előkészítését ismertetik.</span><span class="sxs-lookup"><span data-stu-id="6b048-158">The following subsections explain how to prepare the records that are required for the scenario.</span></span> <span data-ttu-id="6b048-159">Termelési forgatókönyv esetében a beállítási folyamat általában hasonló az itt ismertetett folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="6b048-159">In a production scenario, the setup process typically resembles the process that is described here.</span></span> <span data-ttu-id="6b048-160">Eltérő értékeket azonban beállíthat.</span><span class="sxs-lookup"><span data-stu-id="6b048-160">However, you will set different values.</span></span>

#### <a name="set-up-carriers"></a><span data-ttu-id="6b048-161">Szállítmányozók beállítása</span><span class="sxs-lookup"><span data-stu-id="6b048-161">Set up carriers</span></span>

<span data-ttu-id="6b048-162">Szállítmányozó beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6b048-162">Follow these steps to set up a carrier.</span></span>

1. <span data-ttu-id="6b048-163">Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozók \> Szállítmányozók** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6b048-163">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="6b048-164">Jelölje be a Műveleti ablaktáblán az **Új** lehetőséget szállítmányozó hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="6b048-164">On the Action Pane, select **New** to add a carrier.</span></span>
1. <span data-ttu-id="6b048-165">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6b048-165">On the header, set the following values:</span></span>

    - <span data-ttu-id="6b048-166">**Szállítmányozó:** *Bemutató szállítmányozó*</span><span class="sxs-lookup"><span data-stu-id="6b048-166">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="6b048-167">**Név:** *Bemutató szállítmányozó*</span><span class="sxs-lookup"><span data-stu-id="6b048-167">**Name:** *Demo Carrier*</span></span>
    - <span data-ttu-id="6b048-168">**Mód:** *földi*</span><span class="sxs-lookup"><span data-stu-id="6b048-168">**Mode:** *Ground*</span></span>

1. <span data-ttu-id="6b048-169">Az **Áttekintés** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6b048-169">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6b048-170">**A szállítmányozói felületek aktiválása:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="6b048-170">**Activate shipping carrier:** *Yes*</span></span>
    - <span data-ttu-id="6b048-171">**A szállítmányozó minősítésének aktiválása:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="6b048-171">**Activate carrier rating:** *Yes*</span></span>

1. <span data-ttu-id="6b048-172">A **Szolgáltatások** gyorslapon válassza az **Új** parancsot, ha egy szolgáltatást szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="6b048-172">On the **Services** FastTab, select **New** to add a service to the grid.</span></span>
1. <span data-ttu-id="6b048-173">Állítsa be a következő értékeket az új szolgáltatáshoz:</span><span class="sxs-lookup"><span data-stu-id="6b048-173">Set the following values for the new service:</span></span>

    - <span data-ttu-id="6b048-174">**Szállítmányozói szolgáltatás:** *Bemutató szállítmányozói szolgáltatás*</span><span class="sxs-lookup"><span data-stu-id="6b048-174">**Carrier service:** *Demo carrier service*</span></span>
    - <span data-ttu-id="6b048-175">**Név:** *Bemutató szállítmányozói szolgáltatás*</span><span class="sxs-lookup"><span data-stu-id="6b048-175">**Name:** *Demo carrier service*</span></span>
    - <span data-ttu-id="6b048-176">**Szállítási mód:** *Földi*</span><span class="sxs-lookup"><span data-stu-id="6b048-176">**Transportation method:** *Ground*</span></span>

    <span data-ttu-id="6b048-177">Igény szerint adjon meg tetszőleges értékeket a minden egyéb mezőben.</span><span class="sxs-lookup"><span data-stu-id="6b048-177">Enter arbitrary values for all the other fields, as required.</span></span> <span data-ttu-id="6b048-178">(Amikor menti az új szállítmányozói rekordot, létrejön egy új szállítási mód, és a **Szállítási mód** mező beállítása automatikus lesz.)</span><span class="sxs-lookup"><span data-stu-id="6b048-178">(When you save the new shipping carrier record, a new mode of delivery will be created, and the **Mode of delivery** field will be set automatically.)</span></span>

1. <span data-ttu-id="6b048-179">A **Díjazási profilok** gyorslapon válassza az **Új** lehetőséget a díjazási profil rácshoz történő hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="6b048-179">On the **Rating profiles** FastTab, select **New** to add a rating profile to the grid.</span></span>
1. <span data-ttu-id="6b048-180">Állítsa be a következő értékeket az új profilhoz:</span><span class="sxs-lookup"><span data-stu-id="6b048-180">Set the following values for the new profile:</span></span>

    - <span data-ttu-id="6b048-181">**Díjazási profil:** *Bemutató szállítmányozói szolgáltatás*</span><span class="sxs-lookup"><span data-stu-id="6b048-181">**Rating profile:** *Demo carrier service*</span></span>
    - <span data-ttu-id="6b048-182">**Név:** *Bemutató szállítmányozói szolgáltatás*</span><span class="sxs-lookup"><span data-stu-id="6b048-182">**Name:** *Demo carrier service*</span></span>
    - <span data-ttu-id="6b048-183">**Díjazási motor:** *Bemutató díjazási motor*</span><span class="sxs-lookup"><span data-stu-id="6b048-183">**Rate engine:** *Demo rate engine*</span></span>

    <span data-ttu-id="6b048-184">Igény szerint adjon meg tetszőleges értékeket a minden egyéb mezőben.</span><span class="sxs-lookup"><span data-stu-id="6b048-184">Enter arbitrary values for all the other fields, as required.</span></span>

1. <span data-ttu-id="6b048-185">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6b048-185">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="6b048-186">A szállítmányozók beállításának módjáról bővebben lásd: [Szállítmányozók beállítása](../transportation/tasks/set-up-shipping-carriers.md).</span><span class="sxs-lookup"><span data-stu-id="6b048-186">For more information about how to set up carriers, see [Set up shipping carriers](../transportation/tasks/set-up-shipping-carriers.md).</span></span>

#### <a name="set-up-carrier-service-accounts"></a><span data-ttu-id="6b048-187">Szállítmányozói szolgáltatás fiókjainak beállítása</span><span class="sxs-lookup"><span data-stu-id="6b048-187">Set up carrier service accounts</span></span>

<span data-ttu-id="6b048-188">Szállítmányozói szolgáltatási fiók beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6b048-188">Follow these steps to set up a carrier service account.</span></span>

1. <span data-ttu-id="6b048-189">Lépjen a **Szállításkezelés \> Beállítás \> Díjazás \> Szállítmányozó szolgáltatási fiókja** elemre.</span><span class="sxs-lookup"><span data-stu-id="6b048-189">Go to **Transportation management \> Setup \> Rating \> Carrier service account**.</span></span>
1. <span data-ttu-id="6b048-190">A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy szállítmányozói szolgáltatási fiókot.</span><span class="sxs-lookup"><span data-stu-id="6b048-190">On the Action Pane, select **New** to add a carrier service account.</span></span>
1. <span data-ttu-id="6b048-191">Állítsa be a következő értékeket az új fiókhoz:</span><span class="sxs-lookup"><span data-stu-id="6b048-191">Set the following values for the new account:</span></span>

    - <span data-ttu-id="6b048-192">**Szállítmányozó:** *Bemutató szállítmányozó*</span><span class="sxs-lookup"><span data-stu-id="6b048-192">**Shipping Carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="6b048-193">**Szállítmányozói szolgáltatás:** *Bemutató szállítmányozói szolgáltatás*</span><span class="sxs-lookup"><span data-stu-id="6b048-193">**Carrier service:** *Demo carrier service*</span></span>
    - <span data-ttu-id="6b048-194">**Szállítmányozó vevői számlaszáma:** Az a szállítmányozói vevői számlaszám, amely a szállítmányozóval létesíthető kapcsolat ellenőrzésére és hitelesítésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="6b048-194">**Carrier customer account number:** The carrier customer account number that is used to verify and authenticate the connection to the shipping carrier.</span></span> <span data-ttu-id="6b048-195">A szállítmányozó meg fogja adni ezt az értéket.</span><span class="sxs-lookup"><span data-stu-id="6b048-195">Your carrier will provide this value.</span></span> <span data-ttu-id="6b048-196">Ha bemutatószolgáltatást használ, akkor megadhat egy tetszőleges értéket.</span><span class="sxs-lookup"><span data-stu-id="6b048-196">If you're using the demo service, you can enter an arbitrary value.</span></span>
    - <span data-ttu-id="6b048-197">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="6b048-197">**Site:** *6*</span></span>
    - <span data-ttu-id="6b048-198">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="6b048-198">**Warehouse:** *62*</span></span>

    > [!NOTE]
    > <span data-ttu-id="6b048-199">Gyakran a **Szállítmányozó vevői számlaszáma** az egyetlen olyan érték, amely a kapcsolat hitelesítéséhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="6b048-199">Often, the **Carrier customer account number** value is the only value that is required to authenticate the connection.</span></span> <span data-ttu-id="6b048-200">Ha azonban a szállítmányozó további hitelesítési paramétereket igényel, a szervezetnek testre kell szabnia ezt a lapot, hogy szükség szerint további mezőket adjon hozzá.</span><span class="sxs-lookup"><span data-stu-id="6b048-200">However, if your carrier requires additional authentication parameters, your organization should customize this page to add extra fields as appropriate.</span></span>

#### <a name="set-up-a-container-packing-policy"></a><span data-ttu-id="6b048-201">Tárolók csomagolási irányelvének beállítása</span><span class="sxs-lookup"><span data-stu-id="6b048-201">Set up a container packing policy</span></span>

<span data-ttu-id="6b048-202">Tárolók csomagolási irányelvének beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6b048-202">Follow these steps to set up a container packing policy.</span></span>

1. <span data-ttu-id="6b048-203">Ha még nem állított be ZPL-nyomtatódefiníciót, állítsa be a Dokumentumirányítási ügynök alkalmazás segítségével.</span><span class="sxs-lookup"><span data-stu-id="6b048-203">If you haven't already set up a ZPL printer definition, use the Document Routing Agent application to set it up.</span></span> <span data-ttu-id="6b048-204">További információk: [Dokumentumnyomtatás áttekintése](../../fin-ops-core/dev-itpro/analytics/print-documents.md) és kapcsolódó témakörök.</span><span class="sxs-lookup"><span data-stu-id="6b048-204">For more information, see [Document printing overview](../../fin-ops-core/dev-itpro/analytics/print-documents.md) and related topics.</span></span>
1. <span data-ttu-id="6b048-205">Ugorjon a **Raktárkezelés \> Beállítás \> Tárolók \> Tárolócsomagolási házirendek** pontra.</span><span class="sxs-lookup"><span data-stu-id="6b048-205">Go to **Warehouse Management \> Setup \> Containers \> Container packing policies**.</span></span>
1. <span data-ttu-id="6b048-206">A műveleti ablakpanelen válassza ki az **Új** lehetőséget egy tárolócsomagolási irányelv hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="6b048-206">On the Action Pane, select **New** to add a container packing policy.</span></span>
1. <span data-ttu-id="6b048-207">Az új irányelv fejlécében adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6b048-207">On the header of the new policy, set the following values:</span></span>

    - <span data-ttu-id="6b048-208">**Tárolócsomagolási irányelv:** *Bemutató csomagolási irányelv*</span><span class="sxs-lookup"><span data-stu-id="6b048-208">**Container packing policy:** *Demo packing policy*</span></span>
    - <span data-ttu-id="6b048-209">**Leírás:** Az irányelv leírása</span><span class="sxs-lookup"><span data-stu-id="6b048-209">**Description:** A description of the policy</span></span>

1. <span data-ttu-id="6b048-210">Az **Áttekintés** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6b048-210">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6b048-211">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="6b048-211">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="6b048-212">**Végső szállítmány alapértelmezett helye:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="6b048-212">**Default location for final shipment:** *Baydoor*</span></span>
    - <span data-ttu-id="6b048-213">**Tömegegység:** *KG*</span><span class="sxs-lookup"><span data-stu-id="6b048-213">**Weight unit:** *KG*</span></span>
    - <span data-ttu-id="6b048-214">**Tároló záró irányelve:** *Automatikus kiadás*</span><span class="sxs-lookup"><span data-stu-id="6b048-214">**Container closing policy:** *Automatic release*</span></span>
    - <span data-ttu-id="6b048-215">**Tárolókiadási irányelv:** *Elérhetővé tétel a végleges kiszállítási helyen*</span><span class="sxs-lookup"><span data-stu-id="6b048-215">**Container release policy:** *Make available at final shipping location*</span></span>

1. <span data-ttu-id="6b048-216">A **Tároló jegyzékfájlja** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6b048-216">On the **Container manifest** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6b048-217">**Automatikus jegyzékfájl tárolózáráskor:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="6b048-217">**Automatic manifest at container close:** *Yes*</span></span>
    - <span data-ttu-id="6b048-218">**Tárolóra vonatkozó jegyzékfájl-követelmények:** *Szállításkezelés*</span><span class="sxs-lookup"><span data-stu-id="6b048-218">**Manifest requirements for container:** *Transportation management*</span></span>
    - <span data-ttu-id="6b048-219">**Tároló tartalmának nyomtatása:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="6b048-219">**Print container contents:** *No*</span></span>

1. <span data-ttu-id="6b048-220">A **Szállítmányozói címke nyomtatása** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6b048-220">On the **Carrier label printing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6b048-221">**Tároló levélcímkéjének nyomtatása:** *Mindig*</span><span class="sxs-lookup"><span data-stu-id="6b048-221">**Print container shipping label:** *Always*</span></span>
    - <span data-ttu-id="6b048-222">**Nyomtató neve:** Annak a ZPL-nyomtatónak a neve, amely a levélcímkéket nyomtatja</span><span class="sxs-lookup"><span data-stu-id="6b048-222">**Printer name:** The name of the ZPL printer that should print shipping labels</span></span>

#### <a name="set-up-a-packing-profile"></a><span data-ttu-id="6b048-223">Csomagolási profil beállítása</span><span class="sxs-lookup"><span data-stu-id="6b048-223">Set up a packing profile</span></span>

<span data-ttu-id="6b048-224">Csomagolási profil beállításához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="6b048-224">Follow these steps to set up a packing profile.</span></span>

1. <span data-ttu-id="6b048-225">Ugorjon a **Raktárkezelés \> Beállítás \> Csomagolás \> Csomagolási profilok** pontra.</span><span class="sxs-lookup"><span data-stu-id="6b048-225">Go to **Warehouse Management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="6b048-226">A Művelet panelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy csomagolási profilt a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="6b048-226">On the Action Pane, select **New** to add a packing profile to the grid.</span></span>
1. <span data-ttu-id="6b048-227">Állítsa be a következő értékeket az új profilhoz:</span><span class="sxs-lookup"><span data-stu-id="6b048-227">Set the following values for the new profile:</span></span>

    - <span data-ttu-id="6b048-228">**Csomagolási profil azonosítója:** *Bemutató csomagolási profil*</span><span class="sxs-lookup"><span data-stu-id="6b048-228">**Packing profile ID:** *Demo packing profile*</span></span>
    - <span data-ttu-id="6b048-229">**Leírás:** A profil leírása</span><span class="sxs-lookup"><span data-stu-id="6b048-229">**Description:** A description of the profile</span></span>
    - <span data-ttu-id="6b048-230">**Tárolócsomagolási irányelv:** *Bemutató csomagolási irányelv*</span><span class="sxs-lookup"><span data-stu-id="6b048-230">**Container packing policy:** *Demo packing policy*</span></span>
    - <span data-ttu-id="6b048-231">**Tároló-azonosító mód:** *Automatikus*</span><span class="sxs-lookup"><span data-stu-id="6b048-231">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="6b048-232">**Tárolótípus:** *SmallBox*</span><span class="sxs-lookup"><span data-stu-id="6b048-232">**Container type:** *SmallBox*</span></span>

#### <a name="set-up-a-customer-to-use-the-sps-carrier"></a><span data-ttu-id="6b048-233">Vevő beállítása az SPS-szállítmányozó használatára</span><span class="sxs-lookup"><span data-stu-id="6b048-233">Set up a customer to use the SPS carrier</span></span>

<span data-ttu-id="6b048-234">A következő lépések szerint beállíthatja a vevőt, hogy a létrehozott szállítmányozót használni tudja.</span><span class="sxs-lookup"><span data-stu-id="6b048-234">Follow these steps to set up a customer so that it can use the carrier that you created.</span></span>

1. <span data-ttu-id="6b048-235">Ugorjon a **Kintlevőségek \> Vevők \> Minden vevő** pontra.</span><span class="sxs-lookup"><span data-stu-id="6b048-235">Go to **Accounts receivable \> customers \> All customers**.</span></span>
1. <span data-ttu-id="6b048-236">Keresse meg és válassza ki az *US-027* vevőt a rácson.</span><span class="sxs-lookup"><span data-stu-id="6b048-236">In the grid, find and select customer *US-027*.</span></span>
1. <span data-ttu-id="6b048-237">A Művelet panel **Általános** lapján, a **Beállítás** csoportban válassza a **Szállítmányozó vevői számla** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6b048-237">On the Action Pane, on the **General** tab, in the **Set up** group, select **Carrier customer accounts**.</span></span>
1. <span data-ttu-id="6b048-238">A **Szállítmányozó vevői számlák** lapon, a Műveleti panelen válassza az **Új lehetőséget**, ha számlát szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="6b048-238">On the **Carrier customer accounts** page, on the Action Pane, select **New** to add an account to the grid.</span></span>
1. <span data-ttu-id="6b048-239">Állítsa be a következő értékeket az új fiókhoz:</span><span class="sxs-lookup"><span data-stu-id="6b048-239">Set the following values for the new account:</span></span>

    - <span data-ttu-id="6b048-240">**Szállítmányozó:** *Bemutató szállítmányozó*</span><span class="sxs-lookup"><span data-stu-id="6b048-240">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="6b048-241">**Szállítmányozó vevői számlaszáma:** *12345* (Az érték ebben az esetben nem fontos, de hivatkozni fognak rá a következő szakaszban.)</span><span class="sxs-lookup"><span data-stu-id="6b048-241">**Carrier customer account number:** *12345* (The value isn't important for this scenario, but it will be referred to in the next section.)</span></span>

### <a name="go-through-the-example-scenario"></a><span data-ttu-id="6b048-242">A példaforgatókönyv áttekintése</span><span class="sxs-lookup"><span data-stu-id="6b048-242">Go through the example scenario</span></span>

<span data-ttu-id="6b048-243">Miután az előző szakaszban leírt módon beállította az összes mintaadatot, készen áll a példaforgatókönyv áttekintésére.</span><span class="sxs-lookup"><span data-stu-id="6b048-243">After you've set up all the sample data as described in the previous section, you're ready to go through the example scenario.</span></span>

#### <a name="create-a-sales-order-and-process-the-work"></a><span data-ttu-id="6b048-244">Értékesítési rendelés létrehozása és a munka feldolgozása</span><span class="sxs-lookup"><span data-stu-id="6b048-244">Create a sales order and process the work</span></span>

<span data-ttu-id="6b048-245">Értékesítési rendelés létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6b048-245">Follow these steps to create a sales order.</span></span>

1. <span data-ttu-id="6b048-246">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="6b048-246">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="6b048-247">Új értékesítési rendelés létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="6b048-247">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="6b048-248">Az **Értékesítési rendelés létrehozása** párbeszédpanelen, a **Vevői számla** mezőben állítsa a mező értékét *US-027* értékre.</span><span class="sxs-lookup"><span data-stu-id="6b048-248">In the **Create sales order** dialog box, set the **Customer account** field to *US-027*.</span></span>
1. <span data-ttu-id="6b048-249">Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.</span><span class="sxs-lookup"><span data-stu-id="6b048-249">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="6b048-250">A program megnyitja az új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="6b048-250">The new sales order is opened.</span></span> <span data-ttu-id="6b048-251">Az **Értékesítési rendelés fejléc** gyorslapon állítsa a **Szállítmányozó vevői számlaszáma** mezőt arra az értékre, amelyet korábban kiválasztott ehhez a vevőhöz(*12345*).</span><span class="sxs-lookup"><span data-stu-id="6b048-251">On the **Sales order header** FastTab, set the **Carrier customer account number** field to the value that you selected for this customer earlier (*12345*).</span></span>
1. <span data-ttu-id="6b048-252">Az **Értékesítésirendelés-sorok** szakaszban adjon hozzá egy értékesítési sort, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6b048-252">In the **Sales order lines** section, add a sales line, and set the following values for it:</span></span>

    - <span data-ttu-id="6b048-253">**Cikkszám:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="6b048-253">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="6b048-254">**Mennyiség:** *1*</span><span class="sxs-lookup"><span data-stu-id="6b048-254">**Quantity:** *1*</span></span>
    - <span data-ttu-id="6b048-255">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="6b048-255">**Site:** *6*</span></span>
    - <span data-ttu-id="6b048-256">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="6b048-256">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="6b048-257">Váltson a **Fejléc** nézetre.</span><span class="sxs-lookup"><span data-stu-id="6b048-257">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="6b048-258">A **Szállítás** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6b048-258">On the **Delivery** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6b048-259">**Szállítmányozó:** *Bemutató szállítmányozó*</span><span class="sxs-lookup"><span data-stu-id="6b048-259">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="6b048-260">**Szállítmányozói szolgáltatás:** *Bemutató szállítmányozói szolgáltatás*</span><span class="sxs-lookup"><span data-stu-id="6b048-260">**Carrier service:** *Demo carrier service*</span></span>

1. <span data-ttu-id="6b048-261">Váltson vissza a **Sorok** nézetre.</span><span class="sxs-lookup"><span data-stu-id="6b048-261">Switch back to the **Lines** view.</span></span> <span data-ttu-id="6b048-262">Ha a program megkérdezi, hogy frissíti-e a szállítási módot az értékesítési sorokban, válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6b048-262">If you're prompted to update the mode of delivery for the sales lines, select **Yes**.</span></span>
1. <span data-ttu-id="6b048-263">Az **Értékesítésirendelés-sorok** szakaszban válassza ki a korábban beállított rendeléssort, majd válassza a **Készlet \> Foglalás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6b048-263">In the **Sales order lines** section, select the order line that you set up earlier, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="6b048-264">A **Foglalás** oldalon válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.</span><span class="sxs-lookup"><span data-stu-id="6b048-264">On the **Reservation** page, select **Reserve lot** to reserve the selected line's full quantity in the warehouse.</span></span>
1. <span data-ttu-id="6b048-265">Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="6b048-265">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="6b048-266">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6b048-266">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="6b048-267">A létrehozott munka a kitárolási helyről a csomagolóhelyre mozgatja a cikkeket.</span><span class="sxs-lookup"><span data-stu-id="6b048-267">Work is created to move items from the picking location to the packing station.</span></span>

1. <span data-ttu-id="6b048-268">Az **Értékesítési rendelés sorai** szakaszban válassza ki a **Raktár \> Szállítmány részletes adatai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6b048-268">In the **Sales order lines** section, select **Warehouse \> Shipment details**.</span></span>
1. <span data-ttu-id="6b048-269">A **Szállítmány részletei** lapon jegyezze fel a szállítmány azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="6b048-269">On the **Shipment details** page, make a note of the shipment ID.</span></span> <span data-ttu-id="6b048-270">Erre akkor lesz szüksége, amikor a szállítmányt a csomagolóállomáson csomagolja.</span><span class="sxs-lookup"><span data-stu-id="6b048-270">You will need it when you pack the pack the shipment at the packing station.</span></span>
1. <span data-ttu-id="6b048-271">Zárja be a **Szállítmány adatai** lapot, hogy visszatérjen az értékesítési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="6b048-271">Close the **Shipment details** page to return to the sales order.</span></span>
1. <span data-ttu-id="6b048-272">Jegyezze fel az értékesítési rendelés számát, majd kattintson a **Raktárkezelés \> Munka \> Minden munka** pontra.</span><span class="sxs-lookup"><span data-stu-id="6b048-272">Make a note of the sales order number, and then go to **Warehouse management \> Work \> All work**.</span></span>
1. <span data-ttu-id="6b048-273">Az értékesítési rendelés számának használatával keresse meg és válassza ki a rendeléshez létrehozott munkát.</span><span class="sxs-lookup"><span data-stu-id="6b048-273">Use the sales order number to find and select the work that was created for the order.</span></span>
1. <span data-ttu-id="6b048-274">A Művelet panelen a **Munka** lapon válassza a **Munka befejezése** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="6b048-274">On the Action Pane, on the **Work** tab, select **Complete work**.</span></span>
1. <span data-ttu-id="6b048-275">A **Munka befejezése** lapon, a **Felhasználói azonosító** mezőben válassza ki a felhasználói azonosítót.</span><span class="sxs-lookup"><span data-stu-id="6b048-275">On the **Work completion** page, in the **User ID** field, select a user ID.</span></span> <span data-ttu-id="6b048-276">Majd a műveleti ablaktáblán válassza ki a **Munka ellenőrzése** elemet.</span><span class="sxs-lookup"><span data-stu-id="6b048-276">Then, on the Action Pane, select **Validate work**.</span></span>
1. <span data-ttu-id="6b048-277">Ha a munka megfelel az ellenőrzésen, válassza a **Munka befejezése** elemet a Művelet panelen.</span><span class="sxs-lookup"><span data-stu-id="6b048-277">If the work passes validation, select **Complete work** on the Action Pane.</span></span>

    <span data-ttu-id="6b048-278">A munka készként van megjelölve a cikkeknek a csomagoló állomásra való mozgásának szimulálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="6b048-278">The work is marked as completed to simulate the movement of items to the packing station.</span></span>

#### <a name="pack-the-shipment"></a><span data-ttu-id="6b048-279">A szállítmány csomagolása</span><span class="sxs-lookup"><span data-stu-id="6b048-279">Pack the shipment</span></span>

<span data-ttu-id="6b048-280">A szállítmány csomagolásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6b048-280">Follow these steps to pack the shipment.</span></span>

1. <span data-ttu-id="6b048-281">Ugorjon a **Raktárkezelés \> Beállítás \> Dolgozó** pontra, és győződjön meg róla, hogy a felhasználói fiók társítva van egy dolgozói fiókhoz a raktárkezelésnél.</span><span class="sxs-lookup"><span data-stu-id="6b048-281">Go to **Warehouse management \> Setup \> Worker**, and make sure that your user account is associated with a worker account for warehouse management.</span></span>
1. <span data-ttu-id="6b048-282">Nyissa meg a **Raktárkezelés \> Kitárolás és tárolólétrehozás \> Csomagolás** menüt.</span><span class="sxs-lookup"><span data-stu-id="6b048-282">Go to **Warehouse management \> Picking and containerization \> Pack**.</span></span>
1. <span data-ttu-id="6b048-283">A **Csomagolóállomás kiválasztása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6b048-283">In the **Select packing station** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6b048-284">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="6b048-284">**Site:** *6*</span></span>
    - <span data-ttu-id="6b048-285">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="6b048-285">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="6b048-286">**Hely:** *Csomag*</span><span class="sxs-lookup"><span data-stu-id="6b048-286">**Location:** *Pack*</span></span>
    - <span data-ttu-id="6b048-287">**Csomagolási profil azonosítója:** *Bemutató csomagolási profil*</span><span class="sxs-lookup"><span data-stu-id="6b048-287">**Packing profile ID:** *Demo packing profile*</span></span>

1. <span data-ttu-id="6b048-288">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6b048-288">Select **OK**.</span></span>
1. <span data-ttu-id="6b048-289">Megjelenik a **Csomag** oldal.</span><span class="sxs-lookup"><span data-stu-id="6b048-289">The **Pack** page appears.</span></span> <span data-ttu-id="6b048-290">Egy termelési forgatókönyvben a dolgozó beolvas egy azonosítótáblát vagy szállítmányazonosítót.</span><span class="sxs-lookup"><span data-stu-id="6b048-290">In a production scenario, a worker will scan a license plate or shipment ID.</span></span> <span data-ttu-id="6b048-291">Ehhez a forgatókönyvhöz azonban nyissa meg a **Minden szállítmány** lapot, és keresse meg a szállítmányhoz most létrehozott számot.</span><span class="sxs-lookup"><span data-stu-id="6b048-291">However, for this scenario, open the **All shipments** page, and look up the shipment number for the shipment that you just created.</span></span> <span data-ttu-id="6b048-292">Ezt követően írja be ezt az értéket az **Azonosítótábla vagy szállítmány** mezőjébe a **Csomag** oldalon.</span><span class="sxs-lookup"><span data-stu-id="6b048-292">Then enter this value in the **License plate or shipment** field on the **Pack** page.</span></span> <span data-ttu-id="6b048-293">Másik lehetőségként adja meg annak a szállítmánynak az azonosítóját, amelyről korábban megjegyzést készített.</span><span class="sxs-lookup"><span data-stu-id="6b048-293">Alternatively, enter the shipment ID that you made a note of earlier.</span></span>
1. <span data-ttu-id="6b048-294">A műveleti ablaktáblán kattintson az **Új tároló** elemre.</span><span class="sxs-lookup"><span data-stu-id="6b048-294">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="6b048-295">A megjelenő párbeszédpanelen megjelennek az új tároló részletei.</span><span class="sxs-lookup"><span data-stu-id="6b048-295">The dialog box that appears shows details about the new container.</span></span> <span data-ttu-id="6b048-296">Hagyja meg az alapértelmezett értékeket, majd válassza az **OK** elemet.</span><span class="sxs-lookup"><span data-stu-id="6b048-296">Leave the default values, and then select **OK**.</span></span>
1. <span data-ttu-id="6b048-297">A **Csomag** lapon a **Cikk csomagolása** gyorslapon az **Azonosító** mezőjében válassza az *A0002* elemet a cikk csomagolására.</span><span class="sxs-lookup"><span data-stu-id="6b048-297">On the **Pack** page, on the **Item packing** FastTab, in the **Identifier** field, select *A0002* to pack that item.</span></span> <span data-ttu-id="6b048-298">A cikk bekerül a tárolóba.</span><span class="sxs-lookup"><span data-stu-id="6b048-298">The item is added to the container.</span></span>
1. <span data-ttu-id="6b048-299">A Művelet panelen válassza a **Szállítmányhoz tartozó tárolók** elemet.</span><span class="sxs-lookup"><span data-stu-id="6b048-299">On the Action Pane, select **Containers for shipment**.</span></span>

    <span data-ttu-id="6b048-300">A megjelenő **Szállítmányhoz tartozó tárolók** oldalon található egy sor az imént létrehozott tárolóhoz.</span><span class="sxs-lookup"><span data-stu-id="6b048-300">The **Containers for shipment** page that appears has a row for the container that you just created.</span></span> <span data-ttu-id="6b048-301">A sor **Tároló jegyzékfájl-azonosító** mezője azonban jelenleg üres, mivel ön még nem kapta meg a levélcímkét és a követési számot a szállítmányozótól.</span><span class="sxs-lookup"><span data-stu-id="6b048-301">However, the **Container manifest ID** field in that row is currently blank, because you haven't yet received the shipping label and tracking number from the carrier.</span></span>

1. <span data-ttu-id="6b048-302">A műveleti ablaktáblán kattintson az **Tároló bezárása** elemre.</span><span class="sxs-lookup"><span data-stu-id="6b048-302">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="6b048-303">A **Tároló bezárása** párbeszédpanelen állítsa *1 kg-ra* a **Bruttó tömeg** mezőt, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="6b048-303">In the **Close container** dialog box, set the **Gross weight** field to *1 kg*, and then select **OK**.</span></span>

    <span data-ttu-id="6b048-304">A korábban kiválasztott ZPL-nyomtatóra most rá kell nyomtatni a levélcímkét.</span><span class="sxs-lookup"><span data-stu-id="6b048-304">The shipping label should now be printed on the ZPL printer that you selected earlier.</span></span> <span data-ttu-id="6b048-305">Az alábbi példához hasonlóan jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="6b048-305">It should resemble the following example.</span></span>

    <span data-ttu-id="6b048-306">![Példa levélcímkére](media/sps-label-example.png "Példa levélcímkére")</span><span class="sxs-lookup"><span data-stu-id="6b048-306">![Example shipping label](media/sps-label-example.png "Example shipping label")</span></span>

1. <span data-ttu-id="6b048-307">Figyelje meg, hogy a **Tároló jegyzékfájl-azonosítója** és a **Teljes fuvar** érték hozzá lett adva a címkéhez.</span><span class="sxs-lookup"><span data-stu-id="6b048-307">Notice that the **Container manifest ID** and **Total freight** values have been added as received from the carrier.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]