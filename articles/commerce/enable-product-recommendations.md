---
title: Termékajánlatok engedélyezése
description: Ez a témakör azt mutatja be, hogyan lehet olyan termékjavaslatokat létrehozni, amelyek a Microsoft Dynamics 365 Commerce-felhasználók számára elérhető mesterséges intelligencia gépi tanulás (AI-ML) technológián alapulnak.
author: bebeale
manager: AnnBe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d38d7b0e98d84e23d7a51c5d8ee65df4a3b9e4a7
ms.sourcegitcommit: dbff1c6bb371a443a0cd2a310f5a48d5c21b08ca
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2020
ms.locfileid: "3259794"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="c78ab-103">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="c78ab-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c78ab-104">Ez a témakör azt mutatja be, hogyan lehet olyan termékjavaslatokat létrehozni, amelyek a Microsoft Dynamics 365 Commerce-felhasználók számára elérhető mesterséges intelligencia gépi tanulás (AI-ML) technológián alapulnak.</span><span class="sxs-lookup"><span data-stu-id="c78ab-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="c78ab-105">A termékajánlási listákkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="c78ab-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="c78ab-106">Javaslatok előzetes ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="c78ab-106">Recommendations pre-check</span></span>

<span data-ttu-id="c78ab-107">Az engedélyezés előtt felhívjuk figyelmét, hogy a termékjavaslatok csak azok számára a Commerce-ügyfelek számára támogatott, akik a tárhelyüket áttelepítették, és az Azure Data Lake Storage (ADLS) felhasználói.</span><span class="sxs-lookup"><span data-stu-id="c78ab-107">Before enabling, note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage (ADLS).</span></span> 

<span data-ttu-id="c78ab-108">Az ajánlások engedélyezése előtt engedélyeznie kell a következő konfigurációkat a háttérirodában:</span><span class="sxs-lookup"><span data-stu-id="c78ab-108">The following configurations must be enabled in the back office before enabling recommendations:</span></span>

1. <span data-ttu-id="c78ab-109">Győződjön meg róla, hogy a ADLS-t megvásárolták és sikeresen hitelesítették a környezetben.</span><span class="sxs-lookup"><span data-stu-id="c78ab-109">Ensure that ADLS has been purchased and successfully verified in the environment.</span></span> <span data-ttu-id="c78ab-110">További információ: [Győződjön meg róla, hogy a ADLS-t megvásárolták és sikeresen hitelesítették a környezetben](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="c78ab-110">For more information, see [Ensure that ADLS has been purchased and successfully verified in the environment](enable-ADLS-environment.md).</span></span>
2. <span data-ttu-id="c78ab-111">Győződjön meg róla, hogy az entitástár frissítés automatizált.</span><span class="sxs-lookup"><span data-stu-id="c78ab-111">Ensure that the entity store refresh has been automated.</span></span> <span data-ttu-id="c78ab-112">A további tudnivalókat lásd: [Győződjön meg róla, hogy az entitástár frissítés automatizált](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="c78ab-112">For more information, see [Ensure that the Entity store refresh has been automated](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>
3. <span data-ttu-id="c78ab-113">Győződjön meg róla, hogy az Azure AD identitáskonfiguráció tartalmaz egy Ajánlási bejegyzést.</span><span class="sxs-lookup"><span data-stu-id="c78ab-113">Confirm that Azure AD Identity configuration contains an entry for Recommendations.</span></span> <span data-ttu-id="c78ab-114">A művelet végrehajtásával kapcsolatos további információk az alábbiakban láthatók.</span><span class="sxs-lookup"><span data-stu-id="c78ab-114">More information on how to do this action is below.</span></span>

<span data-ttu-id="c78ab-115">Ezenkívül győződjön meg arról, hogy a RetailSale-mértékek engedélyezve vannak.</span><span class="sxs-lookup"><span data-stu-id="c78ab-115">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="c78ab-116">A beállítással kapcsolatos további tudnivalókat lásd: [Intézkedések használata](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).</span><span class="sxs-lookup"><span data-stu-id="c78ab-116">To learn more about this set up process, see [Work with measures](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).</span></span>

## <a name="azure-ad-identity-configuration"></a><span data-ttu-id="c78ab-117">Azure AD identitáskonfiguráció</span><span class="sxs-lookup"><span data-stu-id="c78ab-117">Azure AD Identity configuration</span></span>

<span data-ttu-id="c78ab-118">Ezt a lépést kötelező megadni az összes olyan vevőnek, aki infrastruktúra szolgáltatásként (IaaS) konfigurációt futtat.</span><span class="sxs-lookup"><span data-stu-id="c78ab-118">This step is required for all customers running an infra-structure as a service (IaaS) configuration.</span></span> <span data-ttu-id="c78ab-119">A Service Fabric (SF) modulban futó vevők esetében ennek a lépésnek automatikusnak kell lennie, és javasoljuk, hogy ellenőrizze, hogy ez a beállítás a várakozásoknak megfelelően van-e konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="c78ab-119">For customers running on service fabric (SF), this step should be automatic and we recommend verifying the setting is configured as expected.</span></span>

### <a name="setup"></a><span data-ttu-id="c78ab-120">Beállítás</span><span class="sxs-lookup"><span data-stu-id="c78ab-120">Setup</span></span>

1. <span data-ttu-id="c78ab-121">Keresse meg az **Azure Active Directory alkalmazások** lapot a háttér-irodában.</span><span class="sxs-lookup"><span data-stu-id="c78ab-121">From the back office, search for the **Azure Active Directory applications** page.</span></span>
2. <span data-ttu-id="c78ab-122">Ellenőrizze, hogy létezik-e bejegyzés a következőhöz: „RecommendationSystemApplication-1”.</span><span class="sxs-lookup"><span data-stu-id="c78ab-122">Verify if an entry exists for "RecommendationSystemApplication-1".</span></span>

<span data-ttu-id="c78ab-123">Ha a bejegyzés nem létezik, adjon hozzá egy új bejegyzést a következő adatokkal:</span><span class="sxs-lookup"><span data-stu-id="c78ab-123">If the entry does not exist, add a new entry with the following information:</span></span>

- <span data-ttu-id="c78ab-124">**Ügyfélazonosító** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span><span class="sxs-lookup"><span data-stu-id="c78ab-124">**Client Id** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span></span>
- <span data-ttu-id="c78ab-125">**Név** – RecommendationSystemApplication-1</span><span class="sxs-lookup"><span data-stu-id="c78ab-125">**Name** - RecommendationSystemApplication-1</span></span>
- <span data-ttu-id="c78ab-126">**Felhasználói azonosító** – RetailServiceAccount</span><span class="sxs-lookup"><span data-stu-id="c78ab-126">**User Id** - RetailServiceAccount</span></span>

<span data-ttu-id="c78ab-127">Mentés és a képernyő bezárása.</span><span class="sxs-lookup"><span data-stu-id="c78ab-127">Save and close the page.</span></span> 

## <a name="turn-on-recommendations"></a><span data-ttu-id="c78ab-128">Termékjavaslatok bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="c78ab-128">Turn on recommendations</span></span>

<span data-ttu-id="c78ab-129">A termékajánlások bekapcsolásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c78ab-129">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="c78ab-130">Válassza a **Retail and Commerce &gt; Termékjavaslatok &gt; Ajánlási paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="c78ab-130">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="c78ab-131">A megosztott paraméterek listáján válassza az **Ajánlati listák** elemet.</span><span class="sxs-lookup"><span data-stu-id="c78ab-131">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="c78ab-132">Állítsa a **Javaslatok engedélyezése** beállítást **Igen** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c78ab-132">Set the **Enable recommendations** option to **Yes**.</span></span>

![Termékjavaslatok bekapcsolása](./media/enablepersonalization.png)

> [!NOTE]
> <span data-ttu-id="c78ab-134">Ez az eljárás elindítja a termékjavaslati listák létrehozásának folyamatát.</span><span class="sxs-lookup"><span data-stu-id="c78ab-134">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="c78ab-135">A listák elérhetővé tételéhez akár több óra szükséges lehet, és a pénztárban (POS) vagy a Dynamics 365 Commerce szolgáltatásban lehet megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="c78ab-135">It may take several hours before the lists are available and can be viewed at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="c78ab-136">A javaslati lista paramétereinek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c78ab-136">Configure recommendation list parameters</span></span>

<span data-ttu-id="c78ab-137">Alapértelmezés szerint az AI-ML-alapú termékjavaslati lista javasolt értékeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="c78ab-137">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="c78ab-138">Az alapértelmezett javasolt értékek módosíthatók, hogy megfeleljenek az Ön vállalatának.</span><span class="sxs-lookup"><span data-stu-id="c78ab-138">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="c78ab-139">Az alapértelmezett paraméterek módosításával kapcsolatos további tudnivalókat az [AI-ML-alapú termékajánlás eredményeinek kezelése](modify-product-recommendation-results.md) témakörben talál.</span><span class="sxs-lookup"><span data-stu-id="c78ab-139">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="c78ab-140">Javaslatok megjelenítése pénztáreszközökön</span><span class="sxs-lookup"><span data-stu-id="c78ab-140">Show recommendations on POS devices</span></span>

<span data-ttu-id="c78ab-141">Miután engedélyezte a javaslatokat a Commerce háttérirodában, hozzá kell adnia a javaslatok panelt a vezérlő pénztárképernyőhöz az elrendezés eszközzel.</span><span class="sxs-lookup"><span data-stu-id="c78ab-141">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="c78ab-142">A folyamattal kapcsolatos további tudnivalókat lásd: [Ajánlások hozzáadása egy a POS-eszközök tranzakció lapjának vezérléséhez](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="c78ab-142">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="c78ab-143">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="c78ab-143">Enable personalized recommendations</span></span>

<span data-ttu-id="c78ab-144">A Dynamics 365 Commerce programban a kiskereskedők a személyre szabott termékajánlatokat (más néven személyre szabásokat) tehetnek elérhetővé.</span><span class="sxs-lookup"><span data-stu-id="c78ab-144">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="c78ab-145">Ily módon a személyre szabott ajánlások belefoglalhatók az online felhasználói élménybe és a pénztárba.</span><span class="sxs-lookup"><span data-stu-id="c78ab-145">In this way, personalized recommendations can be incorporated into the online customer experience and at the point of sale.</span></span> <span data-ttu-id="c78ab-146">Ha be van kapcsolva a személyre szabási funkció, akkor a rendszer társíthatja a felhasználó beszerzési és termékinformációit az egyéni ajánlások előállításához.</span><span class="sxs-lookup"><span data-stu-id="c78ab-146">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

<span data-ttu-id="c78ab-147">Ha további tájékoztatást szeretne a személyre szabott ajánlásokról, lásd: [Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="c78ab-147">To learn more about personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c78ab-148">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c78ab-148">Additional resources</span></span>

[<span data-ttu-id="c78ab-149">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="c78ab-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="c78ab-150">ADLS engedélyezése a Dynamics 365 Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="c78ab-150">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="c78ab-151">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="c78ab-151">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="c78ab-152">Személyre szabott termékajánlatok kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="c78ab-152">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="c78ab-153">Termékajánlások hozzáadása a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="c78ab-153">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="c78ab-154">Ajánlatok hozzáadása a tranzakciós képernyőhöz</span><span class="sxs-lookup"><span data-stu-id="c78ab-154">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="c78ab-155">AI-ML ajánlások eredményeinek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="c78ab-155">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="c78ab-156">Válogatott ajánlások manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="c78ab-156">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="c78ab-157">Ajánlások létrehozása bemutató adatokkal</span><span class="sxs-lookup"><span data-stu-id="c78ab-157">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="c78ab-158">Termékajánlatok GYIK-je</span><span class="sxs-lookup"><span data-stu-id="c78ab-158">Product recommendations FAQ</span></span>](faq-recommendations.md)

