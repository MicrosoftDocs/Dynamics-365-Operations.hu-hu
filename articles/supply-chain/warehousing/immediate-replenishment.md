---
title: Azonnali feltöltés
description: Ez a témakör leírja, hogyan lehet az azonnali feltöltés segítségével feltölteni a készletet, ha egy helyutasításnak nem sikerül készletet felosztania.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSReplenishmentTemplates
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 3def95ac272a424591ed4382d5cd5841bc663654
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5235388"
---
# <a name="immediate-replenishment"></a><span data-ttu-id="a1b6c-103">Azonnali feltöltés</span><span class="sxs-lookup"><span data-stu-id="a1b6c-103">Immediate replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1b6c-104">Az azonnali feltöltés segítségével azonnal fel lehet tölteni a készletet, ha egy helyutasítási sornak nem sikerül készletet felosztania.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-104">Immediate replenishment lets you replenish inventory immediately after a location directive line fails to allocate inventory.</span></span> <span data-ttu-id="a1b6c-105">A feltöltés a helyutasítás beállításai közötti egyetlen soron alapul.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-105">The replenishment is based on a single line in the setup of the location directive.</span></span> <span data-ttu-id="a1b6c-106">Ha a készlet nem aktuális készlet, a sor által meghatározott mértékegységben, az adott mértékegység feltöltése azonnal megtörténik.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-106">If inventory isn't on hand in the unit of measure that is specified by that line, replenishment of that unit of measure occurs immediately.</span></span>

<span data-ttu-id="a1b6c-107">Az azonnali feltöltés mód alternatívát jelent ahhoz a módszerhez képest, ahol a készlet felosztásának alapját a helyutasítás több sora adja, és ahol az igény össze van foglalva a felosztás végén, és a feltöltés azon mértékegység szerint történik, amely a helyutasítás utolsó sorában van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-107">Immediate replenishment provides an alternative to the method where the allocation of inventory is based on more lines in the location directive, and where the demand is summed at the end of the allocation and replenished in the unit of measure that is specified by the last line in the location directive.</span></span>

<span data-ttu-id="a1b6c-108">Az azonnali feltöltés előnyei, hogy a feltöltés a megadott egységekre korlátozható, és a mennyiség meghatározott helyekre irányítható.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-108">The benefits of using immediate replenishment are that replenishment can be limited by specific units and the quantity can be directed to specific locations.</span></span>

## <a name="business-scenario"></a><span data-ttu-id="a1b6c-109">Üzleti eset</span><span class="sxs-lookup"><span data-stu-id="a1b6c-109">Business scenario</span></span>

<span data-ttu-id="a1b6c-110">Például tegyük fel, hogy van egy raktár, amely külön kitárolási területekkel rendelkezik a „doboz” és az „mindegyik” mértékegységekhez.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-110">For example, you have a warehouse that has separate picking areas for the "box" and "each" units of measure.</span></span> <span data-ttu-id="a1b6c-111">A kitárolási folyamatot optimalizálni szeretnénk a lehető legnagyobb számú doboz kitárolásával, majd a doboznál kevesebb maradék mennyiség a „mindegyik” területen bonyolított kitárolásával.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-111">You want to optimize the picking process by picking as many boxes as possible and then picking any remaining quantity that is less than a box from the "each" area.</span></span>

<span data-ttu-id="a1b6c-112">Ebben az esetben az azonnali feltöltést is használhatja.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-112">In this case, you can use immediate replenishment.</span></span> <span data-ttu-id="a1b6c-113">A helyutasításban beállíthat azonnali feltöltést a dobozokhoz, így az igényfeltöltés használatára azonnal sor kerül, amint hiány van az igényelt mennyiség kitárolásához használható dobozokból.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-113">In the location directive, you can set up immediate replenishment for boxes so that demand replenishment is used as soon as there is a shortage of boxes that can be picked for the demand quantity.</span></span> <span data-ttu-id="a1b6c-114">Ezzel a módszerrel optimalizálhatja a kitárolási folyamat úgy, hogy kitárolás a lehető legmagasabb számú dobozt foglalja magában.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-114">In this way, you optimize the picking process so that picking includes as many boxes as possible.</span></span> <span data-ttu-id="a1b6c-115">Az azonnali feltöltési biztosítja a dobozok feltöltését, az igényt nem kell továbbadni úgy, hogy a mennyiségek kitárolására a „mindegyik” mértékegységben kerüljön sor.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-115">Immediate replenishment will generate replenishment of the boxes, and the demand won't be passed on so that the quantities are picked in the "each" unit of measure.</span></span> <span data-ttu-id="a1b6c-116">Ez azt jelenti, hogy csak az eleve a „mindegyik” mértékegységben kitárolandó mennyiség (azaz a doboznál kisebb mennyiség) kitárolása fog a „mindegyik” területen zajlani.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-116">In other words, only the quantities that are supposed to be picked in the "each" unit of measure (that is, quantities that are less than a box) will be picked from the "each" area.</span></span> <span data-ttu-id="a1b6c-117">Ha a „doboz” területen hiány jelentkezik, a lehető legtöbb doboz kitárolható a teljes igényből.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-117">If a shortage occurs in the "box" area, you can pick as many boxes as possible out of the total demand.</span></span> <span data-ttu-id="a1b6c-118">A fennmaradó mennyiség kitárolása a „mindegyik” területről történik.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-118">The remaining quantities will then be picked from the "each" area.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="a1b6c-119">Alkalmazási kör</span><span class="sxs-lookup"><span data-stu-id="a1b6c-119">Where it applies</span></span>

<span data-ttu-id="a1b6c-120">Az azonnali feltöltés használatos hullám-végrehajtásnál, ha a felosztás sikertelen egy olyan helyutasítás sorművelete esetén, amelyhez feltöltési sablon van beállítva.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-120">Immediate replenishment is used during wave execution if allocation fails for a location directive line that a replenishment template is set for.</span></span>

## <a name="set-up-immediate-replenishment"></a><span data-ttu-id="a1b6c-121">Azonnali feltöltés beállítása</span><span class="sxs-lookup"><span data-stu-id="a1b6c-121">Set up immediate replenishment</span></span>

- <span data-ttu-id="a1b6c-122">Lépjen a **Raktárkezelés** \> **Beállítás** \> **Helyutasítások** elemre, majd a **Sorok** lapon az **Azonnali feltöltési sablon** listában válasszon feltöltési sablont a hullámigényhez.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-122">Go to **Warehouse management** \> **Setup** \> **Location directives**, and then, on the **Lines** tab, in the **Immediate replenishment template** list, select a replenishment template for wave demand.</span></span>

<span data-ttu-id="a1b6c-123">A feltöltési sablon alkalmazásra kerül, ha a helyutasítás sorának nem sikerül erre a célra kijelöltt mértékegységet lefoglalni.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-123">The replenishment template is applied if the location directive line fails to allocate a dedicated unit of measure.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a1b6c-124">Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="a1b6c-124">Troubleshooting</span></span>

<span data-ttu-id="a1b6c-125">Ha egy helyutasítási sornál azonnali feltöltés van kijelölve, de nem jön létre feltöltési munka, amikor az adott helyutasítási sorhoz igényfeltöltési sablont használ, két fő okot kell megvizsgálni:</span><span class="sxs-lookup"><span data-stu-id="a1b6c-125">If immediate replenishment is selected for a location directive line, but no replenishment work is generated when you use demand replenishment templates for that location directive line, two main causes must be investigated:</span></span>

- <span data-ttu-id="a1b6c-126">Győződjön meg arról, hogy az alkalmazott igényfeltöltési sablon be van állítva a megfelelő, **Feltöltési** típusú helysablonok és erőforrás-sablonokat használatára.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-126">Make sure that the demand replenishment template that is applied is set up to use the correct location templates and work templates of the **Replenishment** type.</span></span>
- <span data-ttu-id="a1b6c-127">Győződjön meg arról, hogy van elegendő aktuális készlet azon helyeken, ahol az igényfeltöltési sablonnak aktuális készletet keres a feltöltéshez.</span><span class="sxs-lookup"><span data-stu-id="a1b6c-127">Make sure that there is enough on-hand inventory at the locations where the demand replenishment template searches for on-hand inventory for replenishment.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]