---
title: Köteg és azonosítótábla megerősítése
description: Ez a témakör a kötegalkalmazás és az azonosítótábla-megerősítés mobileszközről való beállítását és alkalmazását mutatja be.
author: Mirzaab
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a953b677b1188750241772d7ae966a1dba77b92e
ms.sourcegitcommit: 9f32389715b226c11e74c53547527e0a8b51e300
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/12/2020
ms.locfileid: "4514302"
---
# <a name="batch-and-license-plate-confirmation"></a><span data-ttu-id="9a5d4-103">Köteg és azonosítótábla megerősítése</span><span class="sxs-lookup"><span data-stu-id="9a5d4-103">Batch and license plate confirmation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9a5d4-104">A kötegelés megerősítésével meggyőződhet arról, hogy a helyes tételt tárolta ki a mobileszközről.</span><span class="sxs-lookup"><span data-stu-id="9a5d4-104">Batch confirmation allows you to confirm that the correct batch is being picked from the mobile device.</span></span> <span data-ttu-id="9a5d4-105">A csak a fenti tételek kitárolásánál, amennyiben a fentiek kötegelése azt jelzi, hogy a köteg tartománya magasabb, mint a hely a keresési hierarchiában, így ellenőriznie kell, hogy a kitárolt köteg egyezik a munkasoron lévő köteggel.</span><span class="sxs-lookup"><span data-stu-id="9a5d4-105">On the initial pick of work for batch above-items only, where batch above indicates that batch ranges higher than location in the search hierarchy, you must verify that the batch that is picked matches the batch on the work line.</span></span>

<span data-ttu-id="9a5d4-106">Az azonosítótábla megerősítésével meggyőződhet arról, hogy a helyes azonosítótáblát tárolta ki a mobileszközről.</span><span class="sxs-lookup"><span data-stu-id="9a5d4-106">License plate confirmation allows you to confirm that the correct license plate is being picked from the mobile device.</span></span> <span data-ttu-id="9a5d4-107">Amikor egy betervezett helyről tárol ki munkát, ellenőriznie kell, hogy a kitárolni kívánt azonosítótábla egyezik-e a munkához kapcsolódó azonosítótáblával.</span><span class="sxs-lookup"><span data-stu-id="9a5d4-107">When picking work from a stage location, you must verify that the license plate that is picked matches the license plate that is associated with the work.</span></span> <span data-ttu-id="9a5d4-108">Ha a munka azonosítótábla leolvasásával kezdődik, akkor ezt a megerősítő lépést átugorja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="9a5d4-108">If the work is started by scanning a license plate, this confirmation step will be skipped.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="9a5d4-109">Alkalmazási kör</span><span class="sxs-lookup"><span data-stu-id="9a5d4-109">Where it applies</span></span>

<span data-ttu-id="9a5d4-110">A visszaigazolás az alábbi esetekben alkalmazandó:</span><span class="sxs-lookup"><span data-stu-id="9a5d4-110">Confirmation applies in the following scenarios:</span></span>

- <span data-ttu-id="9a5d4-111">A kötegelés megerősítése a fenti cikkek munkáinak kezdeti kitárolására vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="9a5d4-111">Batch confirmation applies to the initial picks of work for batch above-items.</span></span>
- <span data-ttu-id="9a5d4-112">Az azonosítótábla megerősítése az előkészítési helyeknél lévő kitárolásokra érvényes.</span><span class="sxs-lookup"><span data-stu-id="9a5d4-112">License plate confirmation applies to picks from stage locations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a5d4-113">A feltöltés nem támogatott az azonosítótábla megerősítéséhez.</span><span class="sxs-lookup"><span data-stu-id="9a5d4-113">Replenishment is not supported for license plate confirmation.</span></span> <span data-ttu-id="9a5d4-114">A feltöltési munka végrehajtásakor nem jön létre azonosítótábla-megerősítési lépés.</span><span class="sxs-lookup"><span data-stu-id="9a5d4-114">When executing replenishment work, no license plate confirmation step is created.</span></span>

## <a name="set-up-batch-and-license-plate-confirmation"></a><span data-ttu-id="9a5d4-115">Köteg és azonosítótábla beállításának megerősítése</span><span class="sxs-lookup"><span data-stu-id="9a5d4-115">Set up batch and license plate confirmation</span></span>

<span data-ttu-id="9a5d4-116">Ez a témakör a kötegalkalmazás és az azonosítótábla-megerősítés mobileszközről való beállítását és alkalmazását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="9a5d4-116">You can configure batch and license plate confirmation from the mobile device menu items.</span></span>

1. <span data-ttu-id="9a5d4-117">Lépjen be a munka-visszaigazolás beállításához a mobileszköz menüelemeitől.</span><span class="sxs-lookup"><span data-stu-id="9a5d4-117">From the mobile device menu items, enter the work confirmation setup.</span></span>  
1. <span data-ttu-id="9a5d4-118">Válassza ki, hogy kötegelést vagy azonosítótábla-megerősítést szeretne végezni.</span><span class="sxs-lookup"><span data-stu-id="9a5d4-118">Select the option for either batch or license plate confirmation.</span></span> <span data-ttu-id="9a5d4-119">Mindkét lehetőség rendelkezésre áll azoknál a munkatípus-kitárolásoknál, amelyeknél nincs engedélyezve az automatikus visszaigazolás.</span><span class="sxs-lookup"><span data-stu-id="9a5d4-119">Both options are available for work type picks that do not have automatic confirmation enabled.</span></span>  
