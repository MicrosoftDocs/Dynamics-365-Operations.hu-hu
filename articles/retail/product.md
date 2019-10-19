---
title: Termékajánlatok a POS esetében
description: Ez a témakör leírja a termék ajánlásainak használatát a pénztári eszközön (POS).
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c78fc1f2f1bb08d01828a8b71ad5d3c16ad31b86
ms.sourcegitcommit: 5b53bdafa5cb9a1279576bfece0452a50383b122
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/01/2019
ms.locfileid: "2278380"
---
# <a name="product-recommendations-on-pos"></a><span data-ttu-id="97d72-103">Termékajánlatok a POS esetében</span><span class="sxs-lookup"><span data-stu-id="97d72-103">Product recommendations on POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="97d72-104">A termék ajánlásai egy átalakító üzleti alkalmazás, amely az összes kiskereskedelmi területen átível a gazdag, vonzó és testreszabott termék-felfedezési élmények létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="97d72-104">At its core, product Recommendations are a transformative business application that span across all retail spaces to create rich, engaging, and tailored product discovery experiences.</span></span> <span data-ttu-id="97d72-105">Ha a POS rendszerhez szeretné végrehajtani ezt a funkciót, [akkor kövesse a lépéseket a POS-eszközökkel kapcsolatos javaslatok hozzáadásához.](add-recommendations-control-pos-screen.md)</span><span class="sxs-lookup"><span data-stu-id="97d72-105">To implement this feature on POS, follow the steps on [how to add recommendations to your POS devices.](add-recommendations-control-pos-screen.md)</span></span> 

<span data-ttu-id="97d72-106">A termék ajánlásaival kapcsolatos további tudnivalókat lásd a [termék ajánlásainak áttekintése című témakörben.](../commerce/product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="97d72-106">For more information about product recommendations features, read the [product recommendations overview.](../commerce/product-recommendations.md)</span></span> 

## <a name="scenarios"></a><span data-ttu-id="97d72-107">Esetek</span><span class="sxs-lookup"><span data-stu-id="97d72-107">Scenarios</span></span>

<span data-ttu-id="97d72-108">Az alábbi POS-esetekben engedélyezettek a termékajánlások.</span><span class="sxs-lookup"><span data-stu-id="97d72-108">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="97d72-109">A felhő POS vagy a modern POS (MPOS) esetében állnak rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="97d72-109">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1. <span data-ttu-id="97d72-110">A **Termékadatok kezelése** oldalon:</span><span class="sxs-lookup"><span data-stu-id="97d72-110">On the **Product details** page:</span></span>

    - <span data-ttu-id="97d72-111">• Ha az üzlet alkalmazottja megnyitja valamelyik **Termékadatok** oldalt, amikor az előző tranzakciókat nézi meg különböző csatornákat lefedve, az ajánlások szolgáltatás további elemeket javasol, amelyek várhatóan együtt fognak megvásárolni.</span><span class="sxs-lookup"><span data-stu-id="97d72-111">• If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendations service suggests additional items that are likely to be purchased together.</span></span>

    <span data-ttu-id="97d72-112">[![Javaslatok a Termék részletei oldalon](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="97d72-112">[![Recommendations on the Product details page](./media/proddetails.png)](./media/proddetails.png)</span></span>

2. <span data-ttu-id="97d72-113">A **Tranzakció** oldalon:</span><span class="sxs-lookup"><span data-stu-id="97d72-113">On the **Transaction** page:</span></span>

    - <span data-ttu-id="97d72-114">• Az ajánlási motor a kosárban lévő, gyakran együttesen vásárolt cikkek teljes listája alapján javasolja a cikkek elemeit.</span><span class="sxs-lookup"><span data-stu-id="97d72-114">• The recommendation engine suggests items based on the entire list of items in the basket that are frequently bought together.</span></span>

    > [!NOTE]
    > <span data-ttu-id="97d72-115">Javaslatok megjelenítéséhez a **Tranzakció** lapon a kiskereskedőnek frissítenie kell a képernyő-elrendezést a Dynamics 365 for Retail rendszerben.</span><span class="sxs-lookup"><span data-stu-id="97d72-115">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 for Retail.</span></span> <span data-ttu-id="97d72-116">Az **Ajánlások** vezérlőt rá kell húzni a **Tranzakció** oldalra.</span><span class="sxs-lookup"><span data-stu-id="97d72-116">The **Recommendations** control must be dropped onto the **Transaction** page.</span></span>

    <span data-ttu-id="97d72-117">[![Javaslatok a Tranzakció oldalon](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="97d72-117">[![Recommendations on the Transaction page](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

## <a name="configure-dynamics-365-retail-to-enable-pos-recommendations"></a><span data-ttu-id="97d72-118">A Dynamics 365 Retail konfigurálása pénztárjavaslatok engedélyezéséhez</span><span class="sxs-lookup"><span data-stu-id="97d72-118">Configure Dynamics 365 Retail to enable POS recommendations</span></span>

<span data-ttu-id="97d72-119">A termékajánlások beállításához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="97d72-119">To set up product recommendations, follow these steps:</span></span>

1. <span data-ttu-id="97d72-120">Győződjön meg arról, hogy a szolgáltatás frissítve lett a **10.0.6 build számára.**</span><span class="sxs-lookup"><span data-stu-id="97d72-120">Ensure your service has been updated to the **10.0.6 build.**</span></span>
2. <span data-ttu-id="97d72-121">Kövesse a [termékajánlások](../commerce/enable-product-recommendations.md) a saját vállalkozása számára történő engedélyezésének utasításait.</span><span class="sxs-lookup"><span data-stu-id="97d72-121">Follow the instructions on how to [enable product recommendations](../commerce/enable-product-recommendations.md) for your business.</span></span>
3. <span data-ttu-id="97d72-122">Választható lehetőség: Javaslatok megjelenítéséhez a tranzakciók képernyőn, menjen a **Képernyőelrendezés** lehetőséghez, válassza ki a képernyőelrendezést, indítsa el a **Képernyő-elrendezés tervezőjét**, majd helyezze az **ajánlások** vezérlőjét oda, ahová szükséges.</span><span class="sxs-lookup"><span data-stu-id="97d72-122">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**, and then drop the **recommendations** control where needed.</span></span>
4. <span data-ttu-id="97d72-123">Keresse fel a **Kiskereskedelmi paraméterek** elemet, válassza **Gépi tanulás** elemet, jelölje be az **Igen** lehetőséget **POS-ajánlások engedélyezése** alatt.</span><span class="sxs-lookup"><span data-stu-id="97d72-123">Go to **Retail parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5. <span data-ttu-id="97d72-124">A javaslatok megtekintéséhez a POS-on, futtassa az **1110** globális konfigurációs feladatot.</span><span class="sxs-lookup"><span data-stu-id="97d72-124">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="97d72-125">A POS képernyő-elrendezés tervezőjén végzett módosítások megjelenítéséhez futtassa az **1070** csatorna konfigurációs feladatot.</span><span class="sxs-lookup"><span data-stu-id="97d72-125">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>



## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a><span data-ttu-id="97d72-126">Már engedélyezett termékajánlások esetében problémák elhárítása</span><span class="sxs-lookup"><span data-stu-id="97d72-126">Troubleshoot issues where you have Product recommendations already enabled</span></span>

- <span data-ttu-id="97d72-127">Keresse meg a **Kiskereskedelmi paraméterek** \> **Ajánlási lista** \> **Termékajánlások letiltása** elemet, és futtassa a **Globális konfiguráció feladat \[9999\]** elemet.</span><span class="sxs-lookup"><span data-stu-id="97d72-127">Navigate to **Retail Parameters** \> **Recommendation lists** \> **Disable product recommendations** and run **Global configuration job \[9999\]**.</span></span> 
- <span data-ttu-id="97d72-128">Ha az **Ajánlások vezérlőelem** hozzá van adva a tranzakcióképernyőhöz a **Képernyő-elrendezés tervezője** használatával, távolítsa el azt is.</span><span class="sxs-lookup"><span data-stu-id="97d72-128">If you added the **Recommendations control** to your transaction screen using the **Screen layout designer**, please remove that as well.</span></span>
- <span data-ttu-id="97d72-129">További tájékoztatásért tekintse meg: [Javaslatok GYIK](../commerce/faq-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="97d72-129">If you have additional questions, check out the [Recommendations FAQ](../commerce/faq-recommendations.md) for more information.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="97d72-130">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="97d72-130">Additional resources</span></span>

<span data-ttu-id="97d72-131">[Ajánlások vezérlő hozzáadása egy POS-eszköz tranzakció lapján](add-recommendations-control-pos-screen.md)
[Termékajánlatok áttekintése](../commerce/product-recommendations.md)
[Termékajánlatok engedélyezése](../commerce/enable-product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="97d72-131">[Add a recommendations control to the transaction page on a POS device](add-recommendations-control-pos-screen.md)
[Product recommendations overview](../commerce/product-recommendations.md)
[Enable product recommendations](../commerce/enable-product-recommendations.md)</span></span> 
