---
title: ADLS engedélyezése a Dynamics 365 Commerce környezetben
description: Ez a témakör azt mutatja be, hogyan lehet engedélyezni és tesztelni az Azure Data Lake Storage (ADLS) megoldást egy Dynamics 365 Commerce környezet számára, amely előfeltétele a termékajánlások engedélyezésének.
author: bebeale
manager: AnnBe
ms.date: 03/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 553e1512ba72559923403eef741ce08222172a09
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127767"
---
# <a name="enable-adls-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="03d0f-103">ADLS engedélyezése a Dynamics 365 Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="03d0f-103">Enable ADLS in a Dynamics 365 Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="03d0f-104">Ez a témakör azt mutatja be, hogyan lehet engedélyezni és tesztelni az Azure Data Lake Storage (ADLS) megoldást egy Dynamics 365 Commerce környezet számára, amely előfeltétele a termékajánlások engedélyezésének.</span><span class="sxs-lookup"><span data-stu-id="03d0f-104">This topic explains how to enable and test Azure Data Lake Storage (ADLS) for a Dynamics 365 Commerce environment, which is a prerequisite for enabling product recommendations.</span></span>

## <a name="overview"></a><span data-ttu-id="03d0f-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="03d0f-105">Overview</span></span>

<span data-ttu-id="03d0f-106">A Dynamics 365 Commerce megoldásban minden termék- és tranzakciós adatot nyomon követése megtörténik a környezet Entitás tárában.</span><span class="sxs-lookup"><span data-stu-id="03d0f-106">In the Dynamics 365 Commerce solution, all product and transaction information is tracked in the environment's Entity store.</span></span> <span data-ttu-id="03d0f-107">Ha az adatokat elérhetővé szeretné tenni a Dynamics 365 más szolgáltatásaihoz (például az adatelemzéshez, az üzleti intelligenciához és a személyre szabott ajánlásokhoz), akkor a környezetet egy vevő által birtokolt Azure Data Lake Storage Gen 2 (ADLS) megoldáshoz kell csatlakoztatni.</span><span class="sxs-lookup"><span data-stu-id="03d0f-107">To make this data accessible to other Dynamics 365 services, such as data analytics, business intelligence, and personalized recommendations, it is necessary to connect the environment to a customer-owned Azure Data Lake Storage Gen 2 (ADLS) solution.</span></span>

<span data-ttu-id="03d0f-108">Mivel az ADLS egy környezetben konfigurálható, az összes szükséges adatot tükrözni kell az Entitás tárból, miközben továbbra is védve vannak, az ügyfél felügyelete alatt.</span><span class="sxs-lookup"><span data-stu-id="03d0f-108">As ADLS is configured in an environment, all necessary data is mirrored from the Entity store while still being protected and under customer's control.</span></span>

<span data-ttu-id="03d0f-109">Ha a termékajánlások vagy a személyre szabott javaslatok is engedélyezve vannak a környezetben, akkor a termékajánlások készlete hozzáférési jogosultságot kap az ADLS dedikált mappájához, hogy beolvassa a vevő adatait, és kiszámítsa a javaslatokat ez alapján.</span><span class="sxs-lookup"><span data-stu-id="03d0f-109">If product recommendations or personalized recommendations are also enabled in the environment, then the product recommendations stack will be granted access to the dedicated folder in ADLS to retrieve the customer’s data and compute recommendations based on it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="03d0f-110">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="03d0f-110">Prerequisites</span></span>

<span data-ttu-id="03d0f-111">A vevőknek a saját Azure-előfizetésben kell konfigurálniuk az ADLS-t.</span><span class="sxs-lookup"><span data-stu-id="03d0f-111">Customers need to have ADLS configured in an Azure subscription that they own.</span></span> <span data-ttu-id="03d0f-112">Ez a témakör nem terjed ki egy Azure-előfizetés vagy egy ADLS-alapú tárolási fiók beállításainak beszerzésére.</span><span class="sxs-lookup"><span data-stu-id="03d0f-112">This topic does not cover the purchase of an Azure subscription or the setup of an ADLS-enabled storage account.</span></span>

<span data-ttu-id="03d0f-113">Az ADLS-sel kapcsolatos további tudnivalókért lásd: [ADLS hivatalos dokumentációja](https://azure.microsoft.com/pricing/details/storage/data-lake).</span><span class="sxs-lookup"><span data-stu-id="03d0f-113">For more information about ADLS, see [ADLS official documentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span></span>
  
## <a name="configuration-steps"></a><span data-ttu-id="03d0f-114">Konfigurációs lépések</span><span class="sxs-lookup"><span data-stu-id="03d0f-114">Configuration steps</span></span>

<span data-ttu-id="03d0f-115">Ez a szakasz azokat a konfigurációs lépéseket ismerteti, amelyek szükségesek az ADLS-nek egy környezetben történő engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="03d0f-115">This section covers the configuration steps necessary for enabling ADLS in an environment.</span></span>

### <a name="enable-adls-in-the-environment"></a><span data-ttu-id="03d0f-116">ADLS engedélyezése a környezetben</span><span class="sxs-lookup"><span data-stu-id="03d0f-116">Enable ADLS in the environment</span></span>

1. <span data-ttu-id="03d0f-117">Jelentkezzen be a környezet back office portáljára.</span><span class="sxs-lookup"><span data-stu-id="03d0f-117">Log in to the environment's back office portal.</span></span>
1. <span data-ttu-id="03d0f-118">Keresse meg a **Rendszerparamétereket**, és navigáljon az **Adatkapcsolatok** lapra.</span><span class="sxs-lookup"><span data-stu-id="03d0f-118">Search for **System Parameters** and navigate to the **Data connections** tab.</span></span> 
1. <span data-ttu-id="03d0f-119">Állíts az **Data Lake-integráció engedélyezése** elemet **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="03d0f-119">Set **Enable Data Lake integration** to **Yes**.</span></span>
1. <span data-ttu-id="03d0f-120">Állíts a **Data Lake folyamatos frissítése** elemet **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="03d0f-120">Set **Trickle update Data Lake** to **Yes**.</span></span>
1. <span data-ttu-id="03d0f-121">Adja meg a következő kötelező adatokat:</span><span class="sxs-lookup"><span data-stu-id="03d0f-121">Next, enter the following required information:</span></span>
    1. <span data-ttu-id="03d0f-122">**Alkalmazásazonosító** // **Alkalmazástitok** // **DNS-név** – Az ADLS titok tárolására szolgáló KeyVaulthoz való csatlakozáshoz szükséges.</span><span class="sxs-lookup"><span data-stu-id="03d0f-122">**Application ID** // **Application Secret** // **DNS Name** - Needed to connect to KeyVault where the ADLS secret is stored.</span></span>
    1. <span data-ttu-id="03d0f-123">**Titok neve** – A KeyVaultban tárolt titkos név, amely az ADLS-sel történő hitelesítéshez használatos.</span><span class="sxs-lookup"><span data-stu-id="03d0f-123">**Secret name** - The secret name stored in KeyVault and used to authenticate with ADLS.</span></span>
1. <span data-ttu-id="03d0f-124">Mentse a módosításokat a lap bal felső sarkában.</span><span class="sxs-lookup"><span data-stu-id="03d0f-124">Save your changes in the top left corner of the page.</span></span>

<span data-ttu-id="03d0f-125">A következő kép egy példát mutat az ADLS-konfigurációra.</span><span class="sxs-lookup"><span data-stu-id="03d0f-125">The following image shows an example ADLS configuration.</span></span>

![Minta ADLS-konfiguráció](./media/exampleADLSConfig1.png)

### <a name="test-the-adls-connection"></a><span data-ttu-id="03d0f-127">ADLS-kapcsolat ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="03d0f-127">Test the ADLS connection</span></span>

1. <span data-ttu-id="03d0f-128">Ellenőrizze a kapcsolatot a kulcstárolóval az **Azure Key Vault tesztelése** link segítségével.</span><span class="sxs-lookup"><span data-stu-id="03d0f-128">Test the connection to KeyVault using the **Test Azure Key Vault** link.</span></span>
1. <span data-ttu-id="03d0f-129">Ellenőrizze a kapcsolatot az ADLS-lel az **Azure Storage tesztelése** link segítségével.</span><span class="sxs-lookup"><span data-stu-id="03d0f-129">Test the connection to ADLS using the **Test Azure Storage** link.</span></span>

> [!NOTE]
> <span data-ttu-id="03d0f-130">Ha a tesztek sikertelenek, ellenőrizze, hogy a fentiekben hozzáadott összes KeyVault-információ helyes-e, majd próbálkozzon újra.</span><span class="sxs-lookup"><span data-stu-id="03d0f-130">If the tests fail, double-check that all of the KeyVault information added above is correct, then try again.</span></span>

<span data-ttu-id="03d0f-131">A csatlakozási tesztek sikeres végrehajtása után engedélyeznie kell az Entitás tároló automatikus frissítését.</span><span class="sxs-lookup"><span data-stu-id="03d0f-131">Once the connection tests are successful, you must enable automatic refresh for Entity store.</span></span>

<span data-ttu-id="03d0f-132">Az Entitás tároló automatikus frissítésének engedélyezéséhez hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="03d0f-132">To enable automatic refresh for Entity store, follow these steps.</span></span>

1. <span data-ttu-id="03d0f-133">Az **Entitás tároló**keresése.</span><span class="sxs-lookup"><span data-stu-id="03d0f-133">Search for **Entity Store**.</span></span>
1. <span data-ttu-id="03d0f-134">A bal oldali listában navigáljon a **RetailSales** bejegyzéshez, majd válassza a **Szerkesztés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="03d0f-134">In the list on the left, navigate to the **RetailSales** entry, and select **Edit**.</span></span>
1. <span data-ttu-id="03d0f-135">Győződjön meg arról, hogy **Az automatikus frissítés engedélyezve van** beállítása **Igen**, válassza a **Frissítés** elemet, majd válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="03d0f-135">Ensure that **Automatic Refresh Enabled** is set to **Yes**, select **Refresh**, and then select **Save**.</span></span>

<span data-ttu-id="03d0f-136">A következő kép egy példát mutat be az Entitás tárra az automatikus frissítés engedélyezve beállítással.</span><span class="sxs-lookup"><span data-stu-id="03d0f-136">The following image shows an example of Entity store with automatic refresh enabled.</span></span>

![Példa az automatikus frissítést engedélyező Entitás tárra](./media/exampleADLSConfig2.png)

<span data-ttu-id="03d0f-138">Az ADLS most be van állítva a környezethez.</span><span class="sxs-lookup"><span data-stu-id="03d0f-138">ADLS is now configured for the environment.</span></span> 

<span data-ttu-id="03d0f-139">Ha nem fejeződött be, akkor kövesse a [termékajánlások és a környezet személyre szabásának](enable-product-recommendations.md) engedélyezésének lépéseit.</span><span class="sxs-lookup"><span data-stu-id="03d0f-139">If not completed already, follow the steps for [enabling product recommendations and personalization](enable-product-recommendations.md) for the environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="03d0f-140">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="03d0f-140">Additional resources</span></span>

[<span data-ttu-id="03d0f-141">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="03d0f-141">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="03d0f-142">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="03d0f-142">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="03d0f-143">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="03d0f-143">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="03d0f-144">Személyre szabott termékajánlatok kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="03d0f-144">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="03d0f-145">Ajánlat listáinak hozzáadása egy e-Commerce webhelyhez</span><span class="sxs-lookup"><span data-stu-id="03d0f-145">Add recommendation lists to an e-Commerce site</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="03d0f-146">Termékajánlások hozzáadása a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="03d0f-146">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="03d0f-147">Ajánlatok hozzáadása a tranzakciós képernyőhöz</span><span class="sxs-lookup"><span data-stu-id="03d0f-147">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="03d0f-148">AI-ML ajánlások eredményeinek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="03d0f-148">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="03d0f-149">Válogatott ajánlások manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="03d0f-149">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="03d0f-150">Ajánlások létrehozása bemutató adatokkal</span><span class="sxs-lookup"><span data-stu-id="03d0f-150">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="03d0f-151">Termékajánlatok GYIK-je</span><span class="sxs-lookup"><span data-stu-id="03d0f-151">Product recommendations FAQ</span></span>](faq-recommendations.md)


