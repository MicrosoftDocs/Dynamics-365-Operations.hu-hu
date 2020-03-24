---
title: Termékajánlatok engedélyezése
description: Ez a témakör azt mutatja be, hogyan lehet olyan termékjavaslatokat létrehozni, amelyek a Microsoft Dynamics 365 Commerce-felhasználók számára elérhető mesterséges intelligencia gépi tanulás (AI-ML) technológián alapulnak.
author: bebeale
manager: AnnBe
ms.date: 03/12/2020
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
ms.openlocfilehash: 879fccb063ca0b74e0f022a9edf6a15f7d1311ae
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127882"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="ddf60-103">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="ddf60-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ddf60-104">Ez a témakör azt mutatja be, hogyan lehet olyan termékjavaslatokat létrehozni, amelyek a Microsoft Dynamics 365 Commerce-felhasználók számára elérhető mesterséges intelligencia gépi tanulás (AI-ML) technológián alapulnak.</span><span class="sxs-lookup"><span data-stu-id="ddf60-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="ddf60-105">A termékajánlási listákkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="ddf60-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="ddf60-106">Javaslatok előzetes ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="ddf60-106">Recommendations pre-check</span></span>

<span data-ttu-id="ddf60-107">Az engedélyezés előtt fekhívjuk figyelmét, hogy a termékjavaslatok csak azok számára a Commerce-ügyfelek számára támogatott, akik a tárhelyüket áttelepítették, és az Azure Data Lake Storage (ADLS) felhasználói.</span><span class="sxs-lookup"><span data-stu-id="ddf60-107">Before enabling, please note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage (ADLS).</span></span> 

<span data-ttu-id="ddf60-108">Az ADLS engedélyezésével kapcsolatos lépéseket lásd [ADLS engedélyezése a Dynamics 365 környezetben](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="ddf60-108">For steps on enabling ADLS, see [How to enable ADLS in a Dynamics 365 environment](enable-ADLS-environment.md).</span></span>

<span data-ttu-id="ddf60-109">Ezenkívül győződjön meg arról, hogy a RetailSale-mértékek engedélyezve vannak.</span><span class="sxs-lookup"><span data-stu-id="ddf60-109">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="ddf60-110">Ha további tájékoztatást szeretne erről a beállítási folyamatról, kattintson [ide.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="ddf60-110">To learn more about this set up process, go [here.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="ddf60-111">Termékjavaslatok bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="ddf60-111">Turn on recommendations</span></span>

<span data-ttu-id="ddf60-112">A termékajánlások bekapcsolásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ddf60-112">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="ddf60-113">Válassza a **Retail and Commerce &gt; Termékjavaslatok &gt; Ajánlási paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="ddf60-113">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="ddf60-114">A megosztott paraméterek listáján válassza az **Ajánlati listák** elemet.</span><span class="sxs-lookup"><span data-stu-id="ddf60-114">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="ddf60-115">Állítsa a **Javaslatok engedélyezése** beállítást **Igen** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ddf60-115">Set the **Enable recommendations** option to **Yes**.</span></span>

![termékjavaslatok engedélyezése](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="ddf60-117">Ez az eljárás elindítja a termékjavaslati listák létrehozásának folyamatát.</span><span class="sxs-lookup"><span data-stu-id="ddf60-117">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="ddf60-118">A listák elérhetővé tételéhez akár több óra szükséges lehet, és a pénztárban (POS) vagy a Dynamics 365 Commerce szolgáltatásban lehet megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="ddf60-118">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="ddf60-119">A javaslati lista paramétereinek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ddf60-119">Configure recommendation list parameters</span></span>

<span data-ttu-id="ddf60-120">Alapértelmezés szerint az AI-ML-alapú termékjavaslati lista javasolt értékeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="ddf60-120">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="ddf60-121">Az alapértelmezett javasolt értékek módosíthatók, hogy megfeleljenek az Ön vállalatának.</span><span class="sxs-lookup"><span data-stu-id="ddf60-121">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="ddf60-122">Az alapértelmezett paraméterek módosításával kapcsolatos további tudnivalókat az [AI-ML-alapú termékajánlás eredményeinek kezelése](modify-product-recommendation-results.md) témakörben talál.</span><span class="sxs-lookup"><span data-stu-id="ddf60-122">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="ddf60-123">Javaslatok megjelenítése pénztáreszközökön</span><span class="sxs-lookup"><span data-stu-id="ddf60-123">Show recommendations on POS devices</span></span>

<span data-ttu-id="ddf60-124">Miután engedélyezte a javaslatokat a Commerce háttérirodában, hozzá kell adnia a javaslatok panelt a vezérlő pénztárképernyőhöz az elrendezés eszközzel.</span><span class="sxs-lookup"><span data-stu-id="ddf60-124">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="ddf60-125">A folyamattal kapcsolatos további tudnivalókat lásd: [Ajánlások hozzáadása egy a POS-eszközök tranzakció lapjának vezérléséhez](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="ddf60-125">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="ddf60-126">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="ddf60-126">Enable personalized recommendations</span></span>

<span data-ttu-id="ddf60-127">Ha további tájékoztatást szeretne arról, hogyan lehet személyre szabott ajánlásokat kapni, lásd: [Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="ddf60-127">To learn more about how to receive personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ddf60-128">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ddf60-128">Additional resources</span></span>

[<span data-ttu-id="ddf60-129">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="ddf60-129">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="ddf60-130">ADLS engedélyezése a Dynamics 365 Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="ddf60-130">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="ddf60-131">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="ddf60-131">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="ddf60-132">Személyre szabott termékajánlatok kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="ddf60-132">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="ddf60-133">Ajánlat listáinak hozzáadása egy e-Commerce webhelyhez</span><span class="sxs-lookup"><span data-stu-id="ddf60-133">Add recommendation lists to an e-Commerce site</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="ddf60-134">Termékajánlások hozzáadása a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="ddf60-134">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="ddf60-135">Ajánlatok hozzáadása a tranzakciós képernyőhöz</span><span class="sxs-lookup"><span data-stu-id="ddf60-135">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="ddf60-136">AI-ML ajánlások eredményeinek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="ddf60-136">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="ddf60-137">Válogatott ajánlások manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="ddf60-137">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="ddf60-138">Ajánlások létrehozása bemutató adatokkal</span><span class="sxs-lookup"><span data-stu-id="ddf60-138">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="ddf60-139">Termékajánlatok GYIK-je</span><span class="sxs-lookup"><span data-stu-id="ddf60-139">Product recommendations FAQ</span></span>](faq-recommendations.md)

