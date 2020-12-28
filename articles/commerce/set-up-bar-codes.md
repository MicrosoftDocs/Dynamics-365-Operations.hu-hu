---
title: Vonalkódok beállítása
description: Ez a cikk a vonalkódok használatának módját ismerteti a Dynamics 365 Commerce rendszerben.
author: jblucher
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0785f499a3e106e36b803ae61a9acbdbb072ce17
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412959"
---
# <a name="set-up-bar-codes"></a><span data-ttu-id="63e4b-103">Vonalkódok beállítása</span><span class="sxs-lookup"><span data-stu-id="63e4b-103">Set up bar codes</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="63e4b-104">Ez a cikk a vonalkódok használatának módját ismerteti a Dynamics 365 Commerce rendszerben.</span><span class="sxs-lookup"><span data-stu-id="63e4b-104">This article describes how to use bar codes in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="63e4b-105">A vonalkódok segítségével beszerzéseket és értékesítéseket is kezelhet, termékváltozatokat követhet nyomon, és vevőket és alkalmazottakat állíthat be.</span><span class="sxs-lookup"><span data-stu-id="63e4b-105">You can use bar codes to purchase and sell products, track product variants, and set up customers and employees.</span></span> <span data-ttu-id="63e4b-106">A vonalkódokkal emellett utalványokat, ajándékutalványokat és jóváírásokat adhat ki és hitelesíthet.</span><span class="sxs-lookup"><span data-stu-id="63e4b-106">You can also use bar codes to issue and endorse coupons, gift cards, and credit memos.</span></span> <span data-ttu-id="63e4b-107">A termékekhez szabványos vonalkódok, és egyéni, saját kódolású alkalmazott vonalkódok is beállíthatók.</span><span class="sxs-lookup"><span data-stu-id="63e4b-107">You can set up products so that they have standard bar codes or custom, in-house bar codes.</span></span> <span data-ttu-id="63e4b-108">Egy termékhez egynél több vonalkód is tartozhat.</span><span class="sxs-lookup"><span data-stu-id="63e4b-108">Products can have more than one bar code.</span></span> <span data-ttu-id="63e4b-109">Például egy termék több vonalkóddal rendelkezhet, ha különböző gyártóktól származik, vagy ha méret, stílus és szín tekintetében különböző variánsai vannak.</span><span class="sxs-lookup"><span data-stu-id="63e4b-109">For example, a product might have multiple bar codes if it comes from various manufacturers, or if it has variants that are based on size, style, or color.</span></span> <span data-ttu-id="63e4b-110">A vonalkódok a termék súlyát és árát is magukban foglalhatják.</span><span class="sxs-lookup"><span data-stu-id="63e4b-110">Bar codes can include the weight or price of the product.</span></span> <span data-ttu-id="63e4b-111">A vonalkódmaszkok a vonalkódok létrehozásához használt sablonok.</span><span class="sxs-lookup"><span data-stu-id="63e4b-111">Bar code masks are templates that are used to create bar codes.</span></span>

> [!NOTE]
> <span data-ttu-id="63e4b-112">Ha az egyes változatokhoz egyedi vonalkódot rendel, akkor a termék vonalkódjának pénztárgépnél történő leolvasásával lehetővé válik, hogy a program megtalálja az éppen értékesített változatot.</span><span class="sxs-lookup"><span data-stu-id="63e4b-112">If you assign a unique bar code to each variant combination, you can scan the bar code at the register and let the program determine which variant of the product is being sold.</span></span> <span data-ttu-id="63e4b-113">Emellett ez lehetővé teszi, hogy változatok szerinti értékesítési statisztikát készítsen és jelenítsen meg.</span><span class="sxs-lookup"><span data-stu-id="63e4b-113">You can also collect and view statistics about sales by variant.</span></span> <span data-ttu-id="63e4b-114">Minden egyes méret-, szín- és stíluscsoporthoz egy egyedi szám társítható, amely egy vonalkódba csoportosul.</span><span class="sxs-lookup"><span data-stu-id="63e4b-114">Each size, color, and style group can be assigned a unique number that identifies that group in the bar code.</span></span> <span data-ttu-id="63e4b-115">A Commerce a vonalkódmaszk segítségével automatikusan előállítja minden egyes változatkombináció vonalkódját.</span><span class="sxs-lookup"><span data-stu-id="63e4b-115">Commerce uses the bar code mask to automatically generate bar codes for each variant combination.</span></span> <span data-ttu-id="63e4b-116">Ez a funkció hasznos lehet, ha sok méret, szín vagy stílus fordul elő, mivel a kombinációk száma az egyes változatkódok hozzáadásával jelentősen nő.</span><span class="sxs-lookup"><span data-stu-id="63e4b-116">This functionality can be useful if there are many sizes, colors, and styles, because the number of combinations increases significantly as each variant code is added.</span></span> <span data-ttu-id="63e4b-117">Ha nem használják ezt a funkciót, akkor a vonalkódokat kézzel kell hozzárendelni a termékváltozatot képviselő minden egyes kombinációhoz.</span><span class="sxs-lookup"><span data-stu-id="63e4b-117">If this functionality isn't used, bar codes must be manually assigned to each combination that represents a product variant.</span></span>

<span data-ttu-id="63e4b-118">A vonalkódokat manuálisan és automatikusan is létre lehet hozni.</span><span class="sxs-lookup"><span data-stu-id="63e4b-118">You can create bar codes manually or automatically.</span></span> <span data-ttu-id="63e4b-119">A vonalkódok létrehozásához kövesse az alábbi feladatokat a megadott sorrendben.</span><span class="sxs-lookup"><span data-stu-id="63e4b-119">To create bar codes, complete the following tasks in the order in which they are listed.</span></span>

1. <span data-ttu-id="63e4b-120">[Vonalkódmaszk-karakterek beállítása](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="63e4b-120">[Set up bar code mask characters](set-up-bar-code-masks.md).</span></span>
2. <span data-ttu-id="63e4b-121">[Vonalkódmaszkok beállítása](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="63e4b-121">[Set up bar code masks](set-up-bar-code-masks.md).</span></span>
3. <span data-ttu-id="63e4b-122">Vonalkód-beállítások konfigurálása.</span><span class="sxs-lookup"><span data-stu-id="63e4b-122">Configure bar code setups.</span></span>
4. <span data-ttu-id="63e4b-123">[Termékek vonalkódjainak létrehozása](../supply-chain/pim/tasks/create-bar-code-product.md).</span><span class="sxs-lookup"><span data-stu-id="63e4b-123">[Create bar codes for products](../supply-chain/pim/tasks/create-bar-code-product.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="63e4b-124">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="63e4b-124">Additional resources</span></span>

[<span data-ttu-id="63e4b-125">Vonalkódmaszkok beállítása</span><span class="sxs-lookup"><span data-stu-id="63e4b-125">Set up bar code masks</span></span>](set-up-bar-code-masks.md)
