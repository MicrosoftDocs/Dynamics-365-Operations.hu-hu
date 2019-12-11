---
title: Termékajánlatok engedélyezése
description: Ez a témakör azt mutatja be, hogyan lehet olyan termékjavaslatokat létrehozni, amelyek a Microsoft Dynamics 365 Commerce-felhasználók számára elérhető mesterséges intelligencia gépi tanulás (AI-ML) technológián alapulnak.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
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
ms.openlocfilehash: ecda571a356c6968196d09cc19923105cf4544ab
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770139"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="aa1ec-103">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="aa1ec-103">Enable product recommendations</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="aa1ec-104">Ez a témakör azt mutatja be, hogyan lehet olyan termékjavaslatokat létrehozni, amelyek a Microsoft Dynamics 365 Commerce-felhasználók számára elérhető mesterséges intelligencia gépi tanulás (AI-ML) technológián alapulnak.</span><span class="sxs-lookup"><span data-stu-id="aa1ec-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="aa1ec-105">A termékajánlási listákkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="aa1ec-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="aa1ec-106">Javaslatok előzetes ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="aa1ec-106">Recommendations pre-check</span></span>
<span data-ttu-id="aa1ec-107">Az engedélyezés előtt fekhívjuk figyelmét, hogy a termékjavaslatok csak azok számára a F&O-ügyfelek számára támogatott, akik 10.0.6-os builddel rendelkeznek, és tárhelyüket BDL használatával áttelepítették.</span><span class="sxs-lookup"><span data-stu-id="aa1ec-107">Before enabling, please note that product recommendations are only supported for F&O customers supporting build 10.0.6 and have migrated their storage to using BDL.</span></span> 

<span data-ttu-id="aa1ec-108">Ezenkívül győződjön meg arról, hogy a RetailSale-mértékek engedélyezve vannak.</span><span class="sxs-lookup"><span data-stu-id="aa1ec-108">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="aa1ec-109">Ha további tájékoztatást szeretne erről a beállítási folyamatról, kattintson [ide.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="aa1ec-109">To Learn more about this set up process, go [here.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="aa1ec-110">Termékjavaslatok bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="aa1ec-110">Turn on recommendations</span></span>

<span data-ttu-id="aa1ec-111">A termékajánlások bekapcsolásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="aa1ec-111">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="aa1ec-112">Válassza a **Retail** &gt; **Termékjavaslatok** &gt; **Ajánlási paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="aa1ec-112">Go to **Retail** &gt; **Product recommendations** &gt; **Recommendation parameters**.</span></span>
1. <span data-ttu-id="aa1ec-113">A kiskereskedelmi megosztott paraméterek listáján válassza az **Ajánlati listák** elemet.</span><span class="sxs-lookup"><span data-stu-id="aa1ec-113">In the list of retail shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="aa1ec-114">Állítsa a **Javaslatok engedélyezése** beállítást **Igen** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aa1ec-114">Set the **Enable recommendations** option to **Yes**.</span></span>

![termékjavaslatok engedélyezése](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="aa1ec-116">Ez az eljárás elindítja a termékjavaslati listák létrehozásának folyamatát.</span><span class="sxs-lookup"><span data-stu-id="aa1ec-116">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="aa1ec-117">A listák elérhetővé tételéhez akár több óra szükséges lehet, és a pénztárban (POS) vagy a Dynamics 365 for Commerce szolgáltatásban lehet megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="aa1ec-117">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 for Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="aa1ec-118">A javaslati lista paramétereinek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="aa1ec-118">Configure recommendation list parameters</span></span>
<span data-ttu-id="aa1ec-119">Alapértelmezés szerint az AI-ML-alapú termékjavaslati lista javasolt értékeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="aa1ec-119">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="aa1ec-120">Az alapértelmezett javasolt értékek módosíthatók, hogy megfeleljenek az Ön vállalatának.</span><span class="sxs-lookup"><span data-stu-id="aa1ec-120">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="aa1ec-121">Az alapértelmezett paraméterek módosításával kapcsolatos további tudnivalókat az [AI-ML-alapú termékajánlás eredményeinek kezelése](modify-product-recommendation-results.md) témakörben talál.</span><span class="sxs-lookup"><span data-stu-id="aa1ec-121">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="aa1ec-122">Javaslatok megjelenítése pénztáreszközökön</span><span class="sxs-lookup"><span data-stu-id="aa1ec-122">Show recommendations on POS devices</span></span>
<span data-ttu-id="aa1ec-123">Miután engedélyezte a javaslatokat a háttérirodában, hozzá kell adnia a javaslatok panelt a vezérlő pénztárképernyőhöz az elrendezés eszközzel.</span><span class="sxs-lookup"><span data-stu-id="aa1ec-123">After enabling recommendations in the back office, the recommendations pannel must be added to the control POS screen via the layout tool.</span></span> <span data-ttu-id="aa1ec-124">Ha további tájékoztatást szeretne erről a folyamatról, lépjen [ide.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)</span><span class="sxs-lookup"><span data-stu-id="aa1ec-124">To learn about this process, go [here.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)</span></span>


## <a name="additional-resources"></a><span data-ttu-id="aa1ec-125">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="aa1ec-125">Additional resources</span></span>

[<span data-ttu-id="aa1ec-126">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="aa1ec-126">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="aa1ec-127">Termékjavaslat-listák hozzáadása az oldalakhoz</span><span class="sxs-lookup"><span data-stu-id="aa1ec-127">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="aa1ec-128">Ajánlások panel hozzáadása a pénztáreszközökhöz</span><span class="sxs-lookup"><span data-stu-id="aa1ec-128">Add recommendations panel to POS devices</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


