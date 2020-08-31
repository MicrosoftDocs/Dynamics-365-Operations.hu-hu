---
title: Az Azure Data Lake Storage engedélyezése Dynamics 365 Commerce környezetben
description: Ez a témakör azt mutatja be, hogyan lehet engedélyezni és tesztelni az Azure Data Lake Storage megoldást egy Dynamics 365 Commerce környezet számára, amely előfeltétele a termékajánlások engedélyezésének.
author: bebeale
manager: AnnBe
ms.date: 04/13/2020
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
ms.openlocfilehash: 27e4f1c751ee865b0df536f3c1912cb1d8946032
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "3665002"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="73223-103">Az Azure Data Lake Storage engedélyezése Dynamics 365 Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="73223-103">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="73223-104">Ez a témakör azt mutatja be, hogyan lehet engedélyezni és tesztelni az Azure Data Lake Storage megoldást egy Dynamics 365 Commerce környezet számára, amely előfeltétele a termékajánlások engedélyezésének.</span><span class="sxs-lookup"><span data-stu-id="73223-104">This topic explains how to enable and test Azure Data Lake Storage for a Dynamics 365 Commerce environment, which is a prerequisite for enabling product recommendations.</span></span>

## <a name="overview"></a><span data-ttu-id="73223-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="73223-105">Overview</span></span>

<span data-ttu-id="73223-106">A Dynamics 365 Commerce megoldásban minden termék- és tranzakciós adatot nyomon követése megtörténik a környezet Entitás tárában.</span><span class="sxs-lookup"><span data-stu-id="73223-106">In the Dynamics 365 Commerce solution, all product and transaction information is tracked in the environment's Entity store.</span></span> <span data-ttu-id="73223-107">Ha az adatokat elérhetővé szeretné tenni a Dynamics 365 más szolgáltatásaihoz (például az adatelemzéshez, az üzleti intelligenciához és a személyre szabott ajánlásokhoz), akkor a környezetet egy vevő által birtokolt Azure Data Lake Storage Gen 2 megoldáshoz kell csatlakoztatni.</span><span class="sxs-lookup"><span data-stu-id="73223-107">To make this data accessible to other Dynamics 365 services, such as data analytics, business intelligence, and personalized recommendations, it is necessary to connect the environment to a customer-owned Azure Data Lake Storage Gen 2 solution.</span></span>

<span data-ttu-id="73223-108">Mivel az Azure Data Lake Storage egy környezetben konfigurálható, az összes szükséges adatot tükrözni kell az Entitás tárból, miközben továbbra is védve vannak, az ügyfél felügyelete alatt.</span><span class="sxs-lookup"><span data-stu-id="73223-108">As Azure Data Lake Storage is configured in an environment, all necessary data is mirrored from the Entity store while still being protected and under customer's control.</span></span>

<span data-ttu-id="73223-109">Ha a termékajánlások vagy a személyre szabott javaslatok is engedélyezve vannak a környezetben, akkor a termékajánlások készlete hozzáférési jogosultságot kap az Azure Data Lake Storage dedikált mappájához, hogy beolvassa a vevő adatait, és kiszámítsa a javaslatokat ez alapján.</span><span class="sxs-lookup"><span data-stu-id="73223-109">If product recommendations or personalized recommendations are also enabled in the environment, then the product recommendations stack will be granted access to the dedicated folder in Azure Data Lake Storage to retrieve the customer’s data and compute recommendations based on it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73223-110">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="73223-110">Prerequisites</span></span>

<span data-ttu-id="73223-111">A vevőknek a saját Azure-előfizetésben kell konfigurálniuk az Azure Data Lake Storage-t.</span><span class="sxs-lookup"><span data-stu-id="73223-111">Customers need to have Azure Data Lake Storage configured in an Azure subscription that they own.</span></span> <span data-ttu-id="73223-112">Ez a témakör nem terjed ki egy Azure-előfizetés vagy egy Azure Data Lake Storage-alapú tárolási fiók beállításainak beszerzésére.</span><span class="sxs-lookup"><span data-stu-id="73223-112">This topic does not cover the purchase of an Azure subscription or the setup of an Azure Data Lake Storage-enabled storage account.</span></span>

<span data-ttu-id="73223-113">Az Azure Data Lake Storage-dzsel kapcsolatos további tudnivalókért lásd: [Azure Data Lake Storage Gen 2hivatalos dokumentációja](https://azure.microsoft.com/pricing/details/storage/data-lake).</span><span class="sxs-lookup"><span data-stu-id="73223-113">For more information about Azure Data Lake Storage, see [Azure Data Lake Storage Gen2 official documentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span></span>
  
## <a name="configuration-steps"></a><span data-ttu-id="73223-114">Konfigurációs lépések</span><span class="sxs-lookup"><span data-stu-id="73223-114">Configuration steps</span></span>

<span data-ttu-id="73223-115">Ez a szakasz azokat a konfigurációs lépéseket ismerteti, amelyek szükségesek ahhoz, hogy az Azure Data Lake Storage engedélyezve legyen egy környezetben, mivel a termékajánlásokhoz kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="73223-115">This section covers the configuration steps necessary for enabling Azure Data Lake Storage in an environment as it relates to product recommendations.</span></span>
<span data-ttu-id="73223-116">Az Azure Data Lake Storage engedélyezéséhez szükséges lépésekről a további tudnivalókat lásd: [Entitástár elérhetővé tétele Data Lake alkalmazásként](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="73223-116">For a more in-depth overview of the steps required to enable Azure Data Lake Storage, see [Make entity store available as a Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>

### <a name="enable-azure-data-lake-storage-in-the-environment"></a><span data-ttu-id="73223-117">Azure Data Lake Storage engedélyezése a környezetben</span><span class="sxs-lookup"><span data-stu-id="73223-117">Enable Azure Data Lake Storage in the environment</span></span>

1. <span data-ttu-id="73223-118">Jelentkezzen be a környezet back office portáljára.</span><span class="sxs-lookup"><span data-stu-id="73223-118">Log in to the environment's back office portal.</span></span>
1. <span data-ttu-id="73223-119">Keresse meg a **Rendszerparamétereket**, és navigáljon az **Adatkapcsolatok** lapra.</span><span class="sxs-lookup"><span data-stu-id="73223-119">Search for **System Parameters** and navigate to the **Data connections** tab.</span></span> 
1. <span data-ttu-id="73223-120">Állíts az **Data Lake-integráció engedélyezése** elemet **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="73223-120">Set **Enable Data Lake integration** to **Yes**.</span></span>
1. <span data-ttu-id="73223-121">Állíts a **Data Lake folyamatos frissítése** elemet **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="73223-121">Set **Trickle update Data Lake** to **Yes**.</span></span>
1. <span data-ttu-id="73223-122">Adja meg a következő kötelező adatokat:</span><span class="sxs-lookup"><span data-stu-id="73223-122">Next, enter the following required information:</span></span>
    1. <span data-ttu-id="73223-123">**Alkalmazásazonosító** // **Alkalmazástitok** // **DNS-név** – Az Azure Data Lake Storage titok tárolására szolgáló KeyVaulthoz való csatlakozáshoz szükséges.</span><span class="sxs-lookup"><span data-stu-id="73223-123">**Application ID** // **Application Secret** // **DNS Name** - Needed to connect to KeyVault where the Azure Data Lake Storage secret is stored.</span></span>
    1. <span data-ttu-id="73223-124">**Titok neve** – A KeyVaultban tárolt titkos név, amely az Azure Data Lake Storage-dzsel történő hitelesítéshez használatos.</span><span class="sxs-lookup"><span data-stu-id="73223-124">**Secret name** - The secret name stored in KeyVault and used to authenticate with Azure Data Lake Storage.</span></span>
1. <span data-ttu-id="73223-125">Mentse a módosításokat a lap bal felső sarkában.</span><span class="sxs-lookup"><span data-stu-id="73223-125">Save your changes in the top left corner of the page.</span></span>

<span data-ttu-id="73223-126">A következő kép egy példát mutat az Azure Data Lake Storage-konfigurációra.</span><span class="sxs-lookup"><span data-stu-id="73223-126">The following image shows an example Azure Data Lake Storage configuration.</span></span>

![Minta Azure Data Lake Storage-konfiguráció](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a><span data-ttu-id="73223-128">Azure Data Lake Storage-kapcsolat ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="73223-128">Test the Azure Data Lake Storage connection</span></span>

1. <span data-ttu-id="73223-129">Ellenőrizze a kapcsolatot a kulcstárolóval az **Azure Key Vault tesztelése** link segítségével.</span><span class="sxs-lookup"><span data-stu-id="73223-129">Test the connection to KeyVault using the **Test Azure Key Vault** link.</span></span>
1. <span data-ttu-id="73223-130">Ellenőrizze a kapcsolatot az Azure Data Lake Storage-dzsel az **Azure Storage tesztelése** link segítségével.</span><span class="sxs-lookup"><span data-stu-id="73223-130">Test the connection to Azure Data Lake Storage using the **Test Azure Storage** link.</span></span>

> [!NOTE]
> <span data-ttu-id="73223-131">Ha a tesztek sikertelenek, ellenőrizze, hogy a fentiekben hozzáadott összes KeyVault-információ helyes-e, majd próbálkozzon újra.</span><span class="sxs-lookup"><span data-stu-id="73223-131">If the tests fail, double-check that all of the KeyVault information added above is correct, then try again.</span></span>

<span data-ttu-id="73223-132">A csatlakozási tesztek sikeres végrehajtása után engedélyeznie kell az Entitás tároló automatikus frissítését.</span><span class="sxs-lookup"><span data-stu-id="73223-132">Once the connection tests are successful, you must enable automatic refresh for Entity store.</span></span>

<span data-ttu-id="73223-133">Az Entitás tároló automatikus frissítésének engedélyezéséhez hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="73223-133">To enable automatic refresh for Entity store, follow these steps.</span></span>

1. <span data-ttu-id="73223-134">Az **Entitás tároló**keresése.</span><span class="sxs-lookup"><span data-stu-id="73223-134">Search for **Entity Store**.</span></span>
1. <span data-ttu-id="73223-135">A bal oldali listában navigáljon a **RetailSales** bejegyzéshez, majd válassza a **Szerkesztés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="73223-135">In the list on the left, navigate to the **RetailSales** entry, and select **Edit**.</span></span>
1. <span data-ttu-id="73223-136">Győződjön meg arról, hogy **Az automatikus frissítés engedélyezve van** beállítása **Igen**, válassza a **Frissítés** elemet, majd válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="73223-136">Ensure that **Automatic Refresh Enabled** is set to **Yes**, select **Refresh**, and then select **Save**.</span></span>

<span data-ttu-id="73223-137">A következő kép egy példát mutat be az Entitás tárra az automatikus frissítés engedélyezve beállítással.</span><span class="sxs-lookup"><span data-stu-id="73223-137">The following image shows an example of Entity store with automatic refresh enabled.</span></span>

![Példa az automatikus frissítést engedélyező Entitás tárra](./media/exampleADLSConfig2.png)

<span data-ttu-id="73223-139">Az Azure Data Lake Storage most be van állítva a környezethez.</span><span class="sxs-lookup"><span data-stu-id="73223-139">Azure Data Lake Storage is now configured for the environment.</span></span> 

<span data-ttu-id="73223-140">Ha nem fejeződött be, akkor kövesse a [termékajánlások és a környezet személyre szabásának](enable-product-recommendations.md) engedélyezésének lépéseit.</span><span class="sxs-lookup"><span data-stu-id="73223-140">If not completed already, follow the steps for [enabling product recommendations and personalization](enable-product-recommendations.md) for the environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="73223-141">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="73223-141">Additional resources</span></span>

[<span data-ttu-id="73223-142">Entitástár elérhetővé tétele data lake alkalmazásként</span><span class="sxs-lookup"><span data-stu-id="73223-142">Make entity store available as a data lake</span></span>](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[<span data-ttu-id="73223-143">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="73223-143">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="73223-144">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="73223-144">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="73223-145">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="73223-145">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="73223-146">Személyre szabott termékajánlatok kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="73223-146">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="73223-147">A hasonlóak megvásárlására vonatkozó javaslatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="73223-147">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="73223-148">Termékajánlatok hozzáadása a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="73223-148">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="73223-149">Ajánlatok hozzáadása a tranzakció képernyőjéhez</span><span class="sxs-lookup"><span data-stu-id="73223-149">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="73223-150">AI-ML ajánlások eredményeinek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="73223-150">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="73223-151">Válogatott ajánlások manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="73223-151">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="73223-152">Ajánlások létrehozása bemutató adatokkal</span><span class="sxs-lookup"><span data-stu-id="73223-152">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="73223-153">Termékajánlatok GYIK-je</span><span class="sxs-lookup"><span data-stu-id="73223-153">Product recommendations FAQ</span></span>](faq-recommendations.md)
