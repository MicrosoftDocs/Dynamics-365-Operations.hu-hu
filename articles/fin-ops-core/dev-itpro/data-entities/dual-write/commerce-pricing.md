---
title: A Dynamics 365 Commerce díjszabási motor használata a Dynamics 365 Sales alkalmazással
description: Ez a témakör azt mutatja be, hogyan kell használni a Microsoft Dynamics 365 Commerce árképzési motorját értékesítési árajánlatok a Dynamics 365 Sales alkalmazásból.
author: ShalabhjainMSFT
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: shajain
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-11-03
ms.openlocfilehash: 364cc5adf0358ffa952750149ad31d62cbd35e87
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751434"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a><span data-ttu-id="52c5a-103">A Dynamics 365 Commerce díjszabási motor használata a Dynamics 365 Sales alkalmazással</span><span class="sxs-lookup"><span data-stu-id="52c5a-103">Use the Dynamics 365 Commerce pricing engine with Dynamics 365 Sales</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="52c5a-104">Ez a témakör azt mutatja be, hogyan kell használni a Microsoft Dynamics 365 Commerce árképzési motorját értékesítési árajánlatok a Dynamics 365 Sales alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="52c5a-104">This topic describes how to use the Microsoft Dynamics 365 Commerce pricing engine to create sales quotations in Dynamics 365 Sales.</span></span>

<span data-ttu-id="52c5a-105">Az Dynamics 365 Commerce árképzési motor a legtöbb cég és ügyfél közötti (B2C) árképzési forgatókönyveket támogatja, így például az üzlet szintjének árképzését, a tagságon alapuló és a hűségprogramon alapuló árképzést, a kombinációs engedményeket, a mennyiségi kedvezményeket és a küszöbérték-kedvezményeket.</span><span class="sxs-lookup"><span data-stu-id="52c5a-105">The Dynamics 365 Commerce pricing engine supports most business-to-consumer (B2C) pricing scenarios, such as store-level pricing, affiliation-based and loyalty-based pricing, mix-and-match discounts, quantity discounts, and threshold discounts.</span></span> <span data-ttu-id="52c5a-106">Az árképzési motor összetett szabályokat használ egy adott árajánlat vagy rendelés legjobb árának megállapításához.</span><span class="sxs-lookup"><span data-stu-id="52c5a-106">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span>

<span data-ttu-id="52c5a-107">Ha [kettős írást](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview) használ , akkor három lehetősége van az árképzési szükségletek kielégítésére.</span><span class="sxs-lookup"><span data-stu-id="52c5a-107">When you use [dual-write](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview), you have three options for your pricing needs.</span></span> <span data-ttu-id="52c5a-108">Használhatja azt az árképzést, ami a Dynamics 365 Sales árlistáin alapul, a Dynamics 365 Supply Chain Management árképzési motorját vagy a Dynamics 365 Commerce árképzési motorját.</span><span class="sxs-lookup"><span data-stu-id="52c5a-108">You can use the static pricing that comes from the price list in Dynamics 365 Sales, the pricing engine in Dynamics 365 Supply Chain Management, or the pricing engine in Dynamics 365 Commerce.</span></span> <span data-ttu-id="52c5a-109">Ezek közül a lehetőségek közül a Commerce árképzési motorja a legalkalmasabb a B2C esetekhez.</span><span class="sxs-lookup"><span data-stu-id="52c5a-109">Among these options, the Commerce pricing engine is best suited to B2C scenarios.</span></span>

## <a name="use-the-commerce-pricing-engine-in-sales"></a><span data-ttu-id="52c5a-110">A Commerce árképzási motorjának használata a Sales alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="52c5a-110">Use the Commerce pricing engine in Sales</span></span>

> [!NOTE]
> <span data-ttu-id="52c5a-111">Jelenleg a Commerce árképzési motor csak a árajánlat létrehozásához használható a Salesben.</span><span class="sxs-lookup"><span data-stu-id="52c5a-111">Currently, the Commerce pricing engine can be used only for quotation creation in the Sales.</span></span> <span data-ttu-id="52c5a-112">Még nem érhető el az értékesítési rendelés integrációja a Commerce árképzési motorjával.</span><span class="sxs-lookup"><span data-stu-id="52c5a-112">Sales order integration with the Commerce pricing engine isn't yet available.</span></span>

<span data-ttu-id="52c5a-113">Amikor a felhasználók árajánlatot kezdeményeznek a Sales alkalmazásban, a kettős írás keretrendszer a Commerce-be másolja az árajánlat adatait.</span><span class="sxs-lookup"><span data-stu-id="52c5a-113">When users initiate a quotation in Sales, the dual-write framework copies the quotation details to Commerce.</span></span> <span data-ttu-id="52c5a-114">A program átmásolja a meglévő ajánlati sorok vagy az összes újonnan hozzáadott árajánlati sor változását a Commerce rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="52c5a-114">Any changes to existing quotation lines or any newly added quotation lines in Sales are copied to Commerce.</span></span> <span data-ttu-id="52c5a-115">Amikor a felhasználók a Commerce árképzési motort szeretnék az árajánlat áraihoz használni, az árajánlatot az **Árajánlat** lehetőséget választva frissíthetik az árajánlat árait a Commerce árképzési motorja alapján.</span><span class="sxs-lookup"><span data-stu-id="52c5a-115">When users want to use the Commerce pricing engine to price the quotation, they can select **Price quote** to update the prices of the quotation, based on the Commerce pricing engine.</span></span> <span data-ttu-id="52c5a-116">Az árak automatikusan frissülnek mind a Sales és a Commerce alkalmazásokban is.</span><span class="sxs-lookup"><span data-stu-id="52c5a-116">Prices are then automatically updated in both Sales and Commerce.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="52c5a-117">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="52c5a-117">Prerequisites</span></span>

- <span data-ttu-id="52c5a-118">Ahhoz, hogy a Commerce árképzési motort a Salesben használhassa, el kell végeznie a [Potenciális vevők készpénzre váltása a kettős írás szolgáltatásban](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/) lépéseit.</span><span class="sxs-lookup"><span data-stu-id="52c5a-118">Before you can use the Commerce pricing engine in Sales, you must follow the steps in [Prospect-to-cash in dual-write](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/).</span></span>
- <span data-ttu-id="52c5a-119">A következő lépések végrehajtásával ki kell kapcsolni a kereskedelmi megállapodás értékelését kézi bevitelhez:</span><span class="sxs-lookup"><span data-stu-id="52c5a-119">You must turn off trade agreement evaluation for manual entry by following these steps:</span></span>

    1. <span data-ttu-id="52c5a-120">A Commerce környezetében **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.</span><span class="sxs-lookup"><span data-stu-id="52c5a-120">In your Commerce environment, go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
    1. <span data-ttu-id="52c5a-121">Az **Árak** lapon a **Kereskedelmi megállapodás értékelése** gyorslapon törölje a **Manuális bevitel** jelölőnégyzet jelölését.</span><span class="sxs-lookup"><span data-stu-id="52c5a-121">On the **Prices** tab, on the **Trade agreement evaluation** FastTab, clear the **Manual entry** check box.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="52c5a-122">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="52c5a-122">Additional resources</span></span>

[<span data-ttu-id="52c5a-123">Potenciális vevők készpénzre váltása kettős írásban</span><span class="sxs-lookup"><span data-stu-id="52c5a-123">Prospect-to-cash in dual-write</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]