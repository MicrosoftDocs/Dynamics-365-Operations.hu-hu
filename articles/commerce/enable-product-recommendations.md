---
title: Termékajánlatok engedélyezése
description: Ez a témakör azt mutatja be, hogyan lehet olyan termékjavaslatokat létrehozni, amelyek a Microsoft Dynamics 365 Commerce-felhasználók számára elérhető mesterséges intelligencia gépi tanulás (AI-ML) technológián alapulnak.
author: bebeale
manager: AnnBe
ms.date: 03/19/2020
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
ms.openlocfilehash: d8a579be5df3c5e7718a6fb4720341f3bd01a64c
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154413"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="6707c-103">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="6707c-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6707c-104">Ez a témakör azt mutatja be, hogyan lehet olyan termékjavaslatokat létrehozni, amelyek a Microsoft Dynamics 365 Commerce-felhasználók számára elérhető mesterséges intelligencia gépi tanulás (AI-ML) technológián alapulnak.</span><span class="sxs-lookup"><span data-stu-id="6707c-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="6707c-105">A termékajánlási listákkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="6707c-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="6707c-106">Javaslatok előzetes ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="6707c-106">Recommendations pre-check</span></span>

<span data-ttu-id="6707c-107">Az engedélyezés előtt fekhívjuk figyelmét, hogy a termékjavaslatok csak azok számára a Commerce-ügyfelek számára támogatott, akik a tárhelyüket áttelepítették, és az Azure Data Lake Storage (ADLS) felhasználói.</span><span class="sxs-lookup"><span data-stu-id="6707c-107">Before enabling, please note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage (ADLS).</span></span> 

<span data-ttu-id="6707c-108">Az ADLS engedélyezésével kapcsolatos lépéseket lásd [ADLS engedélyezése a Dynamics 365 környezetben](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6707c-108">For steps on enabling ADLS, see [How to enable ADLS in a Dynamics 365 environment](enable-ADLS-environment.md).</span></span>

<span data-ttu-id="6707c-109">Ezenkívül győződjön meg arról, hogy a RetailSale-mértékek engedélyezve vannak.</span><span class="sxs-lookup"><span data-stu-id="6707c-109">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="6707c-110">Ha további tájékoztatást szeretne erről a beállítási folyamatról, kattintson [ide.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="6707c-110">To learn more about this set up process, go [here.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="6707c-111">Termékjavaslatok bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="6707c-111">Turn on recommendations</span></span>

<span data-ttu-id="6707c-112">A termékajánlások bekapcsolásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6707c-112">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="6707c-113">Válassza a **Retail and Commerce &gt; Termékjavaslatok &gt; Ajánlási paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="6707c-113">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="6707c-114">A megosztott paraméterek listáján válassza az **Ajánlati listák** elemet.</span><span class="sxs-lookup"><span data-stu-id="6707c-114">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="6707c-115">Állítsa a **Javaslatok engedélyezése** beállítást **Igen** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6707c-115">Set the **Enable recommendations** option to **Yes**.</span></span>

![termékjavaslatok engedélyezése](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="6707c-117">Ez az eljárás elindítja a termékjavaslati listák létrehozásának folyamatát.</span><span class="sxs-lookup"><span data-stu-id="6707c-117">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="6707c-118">A listák elérhetővé tételéhez akár több óra szükséges lehet, és a pénztárban (POS) vagy a Dynamics 365 Commerce szolgáltatásban lehet megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="6707c-118">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="6707c-119">A javaslati lista paramétereinek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="6707c-119">Configure recommendation list parameters</span></span>

<span data-ttu-id="6707c-120">Alapértelmezés szerint az AI-ML-alapú termékjavaslati lista javasolt értékeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="6707c-120">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="6707c-121">Az alapértelmezett javasolt értékek módosíthatók, hogy megfeleljenek az Ön vállalatának.</span><span class="sxs-lookup"><span data-stu-id="6707c-121">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="6707c-122">Az alapértelmezett paraméterek módosításával kapcsolatos további tudnivalókat az [AI-ML-alapú termékajánlás eredményeinek kezelése](modify-product-recommendation-results.md) témakörben talál.</span><span class="sxs-lookup"><span data-stu-id="6707c-122">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="6707c-123">Javaslatok megjelenítése pénztáreszközökön</span><span class="sxs-lookup"><span data-stu-id="6707c-123">Show recommendations on POS devices</span></span>

<span data-ttu-id="6707c-124">Miután engedélyezte a javaslatokat a Commerce háttérirodában, hozzá kell adnia a javaslatok panelt a vezérlő pénztárképernyőhöz az elrendezés eszközzel.</span><span class="sxs-lookup"><span data-stu-id="6707c-124">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="6707c-125">A folyamattal kapcsolatos további tudnivalókat lásd: [Ajánlások hozzáadása egy a POS-eszközök tranzakció lapjának vezérléséhez](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="6707c-125">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="6707c-126">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="6707c-126">Enable personalized recommendations</span></span>

<span data-ttu-id="6707c-127">Ha további tájékoztatást szeretne arról, hogyan lehet személyre szabott ajánlásokat kapni, lásd: [Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="6707c-127">To learn more about how to receive personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6707c-128">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6707c-128">Additional resources</span></span>

[<span data-ttu-id="6707c-129">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="6707c-129">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="6707c-130">ADLS engedélyezése a Dynamics 365 Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="6707c-130">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="6707c-131">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="6707c-131">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="6707c-132">Személyre szabott termékajánlatok kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="6707c-132">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="6707c-133">Termékajánlások hozzáadása a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="6707c-133">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="6707c-134">Ajánlatok hozzáadása a tranzakciós képernyőhöz</span><span class="sxs-lookup"><span data-stu-id="6707c-134">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="6707c-135">AI-ML ajánlások eredményeinek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="6707c-135">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="6707c-136">Válogatott ajánlások manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="6707c-136">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="6707c-137">Ajánlások létrehozása bemutató adatokkal</span><span class="sxs-lookup"><span data-stu-id="6707c-137">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="6707c-138">Termékajánlatok GYIK-je</span><span class="sxs-lookup"><span data-stu-id="6707c-138">Product recommendations FAQ</span></span>](faq-recommendations.md)

