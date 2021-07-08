---
title: Késleltetési tűréshatár (negatív napok)
description: Ez a témakör a késleltetett tűréshatár kiszámításáról, valamint arról nyújt tájékoztatást, hogy hogyan befolyásolja a tervezett rendelések létrehozását a tervezési optimalizálásban.
author: crytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 748e047e89747f2eabccc04a40c79bcb1e6f3dea
ms.sourcegitcommit: f21659f1c23bc2cd65bbe7fb7210910d5a8e1cb9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306463"
---
# <a name="delay-tolerance-negative-days"></a><span data-ttu-id="d1c4a-103">Késleltetési tűréshatár (negatív napok)</span><span class="sxs-lookup"><span data-stu-id="d1c4a-103">Delay tolerance (negative days)</span></span>

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="d1c4a-104">A késleltetett tűréshatár funkcióval a tervezési optimalizálás figyelembe veszi a **Negatív napok** értékét, amely be van állítva a fedezetcsoportokhoz.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-104">The delay tolerance functionality enables Planning Optimization to consider the **Negative days** value that is set for coverage groups.</span></span> <span data-ttu-id="d1c4a-105">Az alaptervezés során alkalmazott késleltetett tűréshatár időszakának meghosszabbítása.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-105">It's used to extend the delay tolerance period that is applied during master planning.</span></span> <span data-ttu-id="d1c4a-106">Ily módon elkerülheti az új ellátási rendelések létrehozását, ha a meglévő készlet képes lesz fedezni az igényt egy rövid késleltetés után.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-106">In this way, you can avoid creating new supply orders if existing supply will be able to cover the demand after a short delay.</span></span> <span data-ttu-id="d1c4a-107">A funkció célja annak meghatározása, hogy van-e értelme új ellátási rendelést létrehozni egy adott igényre.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-107">The purpose of the functionality is to determine whether it makes sense to create a new supply order for a given demand.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="d1c4a-108">A funkció bekapcsolása a rendszerben</span><span class="sxs-lookup"><span data-stu-id="d1c4a-108">Turn on the feature in your system</span></span>

<span data-ttu-id="d1c4a-109">Ha a késleltetési tűréshatár funkciót elérhetővé szeretné tenni a rendszerben, menjen a [Funkciókezelés](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) elemre, és kapcsolja be a *Negatív napok tervezési optimalizáláshoz* funkciót.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-109">To make the delay tolerance functionality available in your system, go to [Feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Negative days for Planning Optimization* feature.</span></span>

## <a name="delay-tolerance-in-planning-optimization"></a><span data-ttu-id="d1c4a-110">A tervezési optimalizálás késleltetési tűréshatára</span><span class="sxs-lookup"><span data-stu-id="d1c4a-110">Delay tolerance in Planning Optimization</span></span>

<span data-ttu-id="d1c4a-111">A késleltetési tűréshatár azt jelzi, hogy hány napot kell várnia az átfutási idő után, mielőtt új feltöltést rendel, amikor a meglévő készlet már meg van tervezve.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-111">Delay tolerance represents the number of days beyond the lead time that you're willing to wait before you order new replenishment when existing supply is already planned.</span></span> <span data-ttu-id="d1c4a-112">A késleltetési tűréshatárt naptári napok, nem pedig munkanapok határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-112">Delay tolerance is defined by using calendar days, not business days.</span></span>

<span data-ttu-id="d1c4a-113">Az alaptervezéskor, amikor a rendszer kiszámítja a késleltetési tűréshatárt, figyelembe veszi a **Negatív napok** beállítását.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-113">At the time of master planning, when the system calculates the delay tolerance, it considers the **Negative days** setting.</span></span> <span data-ttu-id="d1c4a-114">A **Negatív napok** értéket a **Fedezeti csoportok** vagy a **Cikk fedezete** oldalakon állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-114">You can set the **Negative days** value on either the **Coverage groups** page or the **Item coverage** page.</span></span>

<span data-ttu-id="d1c4a-115">A rendszer a késleltetett tűréshatár számítását a *legkorábbi feltöltési dátumhoz* – amely a mai dátum és az átfutási idő értékével egyenlő – összeköti.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-115">The system links the delay tolerance calculation to the *earliest replenishment date*, which equals today's date plus the lead time.</span></span> <span data-ttu-id="d1c4a-116">A késleltetési tűréshatár számítása a következő képlettel történik, ahol a *max()* függvény két érték közül a nagyobbat találja meg:</span><span class="sxs-lookup"><span data-stu-id="d1c4a-116">The delay tolerance is calculated by using following formula, where *max()* finds the larger of two values:</span></span>

<span data-ttu-id="d1c4a-117">*max(Legkorábbi feltöltési dátum, Igény esedékesség dátuma)* – *Igény esedékesség dátuma* + *Negatív napok*</span><span class="sxs-lookup"><span data-stu-id="d1c4a-117">*max(Earliest replenishment date, Demand due date)* – *Demand due date* + *Negative days*</span></span>

<span data-ttu-id="d1c4a-118">Ez a képlet gondoskodik arról, hogy az alaptervezés ne hozzon létre új ellátási rendeléseket, ha a termék átfutási ideje alatt elegendő készlet létezik.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-118">This formula ensures that master planning doesn't create new supply orders when enough supply exists during the product lead time.</span></span>

> [!NOTE]
> <span data-ttu-id="d1c4a-119">A Tervezési optimalizálásnál a késleltetett tűréshatár számítása mindig a beépített alaptervezés dinamikus negatív napszámítását használja.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-119">The delay tolerance calculation in Planning Optimization always uses the dynamic negative days calculation from built-in master planning.</span></span> <span data-ttu-id="d1c4a-120">Az **Alaptervezés paraméterei** lapon a **Dinamikus negatív napok** használata beállítás nincs hatással erre a viselkedésre.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-120">The **Use dynamic negative days** setting on the **Master planning parameters** page has no effect on this behavior.</span></span>

<span data-ttu-id="d1c4a-121">Ha a meglévő készlet a számított késleltetési tűréshatárnál kisebb vagy azzal egyenlő igény-késleltetést jelent, akkor a Tervezési optimalizálás a meglévő készletet az igénynek megfelelő mennyiséggel egyenlíti ki.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-121">If the existing supply implies a demand delay that is less than or equal to the calculated delay tolerance, Planning Optimization pegs existing supply with the demand.</span></span> <span data-ttu-id="d1c4a-122">Bizonyos esetekben jobb késleltetni az igényt, mint ha a végén túl sok idő lenne.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-122">In some cases, it's better to delay the demand than to end up with oversupply.</span></span>

<span data-ttu-id="d1c4a-123">Az alábbi alszakaszok olyan példákat mutatnak be, amelyek bemutatják, hogy a késleltetés tűréshatára hogyan befolyásolja a tervezett rendelések létrehozását a tervezési optimalizálásban.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-123">The following subsections provide examples that show how delay tolerance affects the creation of planned orders in Planning Optimization.</span></span>

### <a name="example-1"></a><span data-ttu-id="d1c4a-124">1. példa</span><span class="sxs-lookup"><span data-stu-id="d1c4a-124">Example 1</span></span>

<span data-ttu-id="d1c4a-125">Egy termék a következő konfigurációval rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="d1c4a-125">A product has the following configuration:</span></span>

- <span data-ttu-id="d1c4a-126">**Átfutási idő:** *10*</span><span class="sxs-lookup"><span data-stu-id="d1c4a-126">**Lead time:** *10*</span></span>
- <span data-ttu-id="d1c4a-127">**Negatív napok:** *2*</span><span class="sxs-lookup"><span data-stu-id="d1c4a-127">**Negative days:** *2*</span></span>

<span data-ttu-id="d1c4a-128">A termékre a következő ellátás és igény létezik:</span><span class="sxs-lookup"><span data-stu-id="d1c4a-128">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="d1c4a-129">**Igény a mai napra:** Értékesítési rendelés 10 mennyiségre</span><span class="sxs-lookup"><span data-stu-id="d1c4a-129">**Demand for today:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="d1c4a-130">**Készlet 12 napon belül:** Beszerzési rendelés 10 mennyiségre</span><span class="sxs-lookup"><span data-stu-id="d1c4a-130">**Supply in 12 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="d1c4a-131">A meglévő készlet 12 napon belül fedezheti az igényt, és ez az időszak megegyezik a késleltetett tűréshatársal.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-131">Existing supply can cover the demand within 12 days, and that period equals the delay tolerance.</span></span> <span data-ttu-id="d1c4a-132">Ezért az alaptervezés futtatásakor nem jön létre tervezett rendelés.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-132">Therefore, when master planning runs, no planned orders are created.</span></span>

### <a name="example-2"></a><span data-ttu-id="d1c4a-133">2. példa</span><span class="sxs-lookup"><span data-stu-id="d1c4a-133">Example 2</span></span>

<span data-ttu-id="d1c4a-134">Egy termék a következő konfigurációval rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="d1c4a-134">A product has the following configuration:</span></span>

- <span data-ttu-id="d1c4a-135">**Átfutási idő:** *10*</span><span class="sxs-lookup"><span data-stu-id="d1c4a-135">**Lead time:** *10*</span></span>
- <span data-ttu-id="d1c4a-136">**Negatív napok:** *0*</span><span class="sxs-lookup"><span data-stu-id="d1c4a-136">**Negative days:** *0*</span></span>

<span data-ttu-id="d1c4a-137">A termékre a következő ellátás és igény létezik:</span><span class="sxs-lookup"><span data-stu-id="d1c4a-137">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="d1c4a-138">**Igény a mai napra:** Értékesítési rendelés 10 mennyiségre</span><span class="sxs-lookup"><span data-stu-id="d1c4a-138">**Demand for today:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="d1c4a-139">**Készlet 12 napon belül:** Beszerzési rendelés 10 mennyiségre</span><span class="sxs-lookup"><span data-stu-id="d1c4a-139">**Supply in 12 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="d1c4a-140">A meglévő készlet csak 12 nap után fedezheti az igényt.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-140">Existing supply can cover the demand only after 12 days.</span></span> <span data-ttu-id="d1c4a-141">A késleltetési tűréshatár azonban 10 nap.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-141">However, the delay tolerance is 10 days.</span></span> <span data-ttu-id="d1c4a-142">Ezért az alaptervezés futtatásakor egy 10 mennyiségű tervezett rendelés jön létre.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-142">Therefore, when master planning runs, a planned order for a quantity of 10 is created.</span></span>

### <a name="example-3"></a><span data-ttu-id="d1c4a-143">3. példa</span><span class="sxs-lookup"><span data-stu-id="d1c4a-143">Example 3</span></span>

<span data-ttu-id="d1c4a-144">Egy termék a következő konfigurációval rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="d1c4a-144">A product has the following configuration:</span></span>

- <span data-ttu-id="d1c4a-145">**Átfutási idő:** *10*</span><span class="sxs-lookup"><span data-stu-id="d1c4a-145">**Lead time:** *10*</span></span>
- <span data-ttu-id="d1c4a-146">**Negatív napok:** *2*</span><span class="sxs-lookup"><span data-stu-id="d1c4a-146">**Negative days:** *2*</span></span>

<span data-ttu-id="d1c4a-147">A termékre a következő ellátás és igény létezik:</span><span class="sxs-lookup"><span data-stu-id="d1c4a-147">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="d1c4a-148">**Igény 11 napon belül:** Értékesítési rendelés 10 mennyiségre</span><span class="sxs-lookup"><span data-stu-id="d1c4a-148">**Demand in 11 days:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="d1c4a-149">**Készlet 14 napon belül:** Beszerzési rendelés 10 mennyiségre</span><span class="sxs-lookup"><span data-stu-id="d1c4a-149">**Supply in 14 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="d1c4a-150">A meglévő készlet csak három nap után fedezheti az igényt.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-150">Existing supply can cover the demand only after three days.</span></span> <span data-ttu-id="d1c4a-151">A késleltetési tűréshatár azonban két nap.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-151">However, the delay tolerance is two days.</span></span> <span data-ttu-id="d1c4a-152">(Ebben az esetben a késleltetési tűréshatár csak a két negatív napot tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-152">(In this case, the delay tolerance includes only the two negative days.</span></span> <span data-ttu-id="d1c4a-153">Az igény dátuma nem szerepel, mert a termék átfutási ideje után van.) Ezért az alaptervezés futtatásakor egy 10 mennyiségű tervezett rendelés jön létre.</span><span class="sxs-lookup"><span data-stu-id="d1c4a-153">The demand date isn't included because it's after the product lead time.) Therefore, when master planning runs, a planned order for a quantity of 10 is created.</span></span>
