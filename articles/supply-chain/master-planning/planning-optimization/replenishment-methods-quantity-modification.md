---
title: Feltöltési módok és a mennyiség módosítása
description: Ez a témakör a Tervezési optimalizálásban szereplő feltöltési módokról szolgál információval. Azt is ismerteti, hogy hogyan befolyásolja egy termék több rendelési mennyisége az eredményt.
author: crytt
ms.date: 6/1/2021
ms.topic: article
ms.search.form: ReqGroup, ReqItemTable, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d5e0e671e624de2646a47647ef08d3567599b884
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261696"
---
# <a name="replenishment-methods-and-quantity-modification"></a><span data-ttu-id="61f3f-104">Feltöltési módok és a mennyiség módosítása</span><span class="sxs-lookup"><span data-stu-id="61f3f-104">Replenishment methods and quantity modification</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="61f3f-105">Ez a témakör a Tervezési optimalizálásban szereplő feltöltési módokról szolgál információval.</span><span class="sxs-lookup"><span data-stu-id="61f3f-105">This topic provides information about replenishment methods in Planning Optimization.</span></span> <span data-ttu-id="61f3f-106">Azt is ismerteti, hogy hogyan befolyásolja egy termék több rendelési mennyisége az eredményt.</span><span class="sxs-lookup"><span data-stu-id="61f3f-106">It also explains how the multiple order quantity for a product affects the result.</span></span>

<span data-ttu-id="61f3f-107">A feltöltési módszerek fedezeti vagy adagméretezési módszerekként is ismertek.</span><span class="sxs-lookup"><span data-stu-id="61f3f-107">Replenishment methods are also known as coverage methods and lot-sizing methods.</span></span>

## <a name="coverage-codes"></a><span data-ttu-id="61f3f-108">Fedezeti kódok</span><span class="sxs-lookup"><span data-stu-id="61f3f-108">Coverage codes</span></span>

<span data-ttu-id="61f3f-109">A Tervezési optimalizálás beállítható úgy, hogy különböző feltöltési módokat használjon.</span><span class="sxs-lookup"><span data-stu-id="61f3f-109">Planning Optimization can be configured to use different replenishment methods.</span></span> <span data-ttu-id="61f3f-110">A feltöltési módok olyan technikák, amelyekkel a rendszer a termékek követelményeit számítja ki.</span><span class="sxs-lookup"><span data-stu-id="61f3f-110">The replenishment methods are the techniques that the system uses to calculate requirements for a product.</span></span> <span data-ttu-id="61f3f-111">A feltöltési módokat olyan fedezeti kódok határozzák meg, amelyek a fedezeti csoportban vagy a termékben állíthatók be.</span><span class="sxs-lookup"><span data-stu-id="61f3f-111">Replenishment methods are defined by coverage codes that you can set up on either the coverage group or the product.</span></span>

<span data-ttu-id="61f3f-112">A Tervezési optimalizálásban a következő fedezeti kódok használhatók:</span><span class="sxs-lookup"><span data-stu-id="61f3f-112">The following coverage codes can be used in Planning Optimization:</span></span>

- <span data-ttu-id="61f3f-113">**Időszak** – Ez a feltöltési módszer az adott időszakra vonatkozó összes igényt egy rendelésbe egyesíti a termékre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="61f3f-113">**Period** – The replenishment method combines all the demand for a period into one order for the product.</span></span> <span data-ttu-id="61f3f-114">A rendelés tervezése az időszak első napjához történik, és a rendelés mennyisége teljesíti a nettó szükségletet a meghatározott időszakban.</span><span class="sxs-lookup"><span data-stu-id="61f3f-114">The order will be planned for the first day of the period, and its quantity will fulfill the net requirements during the established period.</span></span> <span data-ttu-id="61f3f-115">Az időszak a termék első igényével kezdődik és a megadott időtartamra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="61f3f-115">The period starts with the first demand of the product and covers the defined length of time.</span></span> <span data-ttu-id="61f3f-116">A következő időszak a termék következő igényével kezdődik.</span><span class="sxs-lookup"><span data-stu-id="61f3f-116">The next period will start with the next requirements of the product.</span></span> <span data-ttu-id="61f3f-117">Az *Időszak* fedezeti kód gyakran használatos előre nem jelezhető készletkérésre, szezonális termékekre vagy magas költségű termékekhez.</span><span class="sxs-lookup"><span data-stu-id="61f3f-117">The *Period* coverage code is often used for non-predictable inventory draw, season-influenced products, or high-cost products.</span></span> <span data-ttu-id="61f3f-118">A következő ábrán egy példa látható.</span><span class="sxs-lookup"><span data-stu-id="61f3f-118">The following illustration shows an example.</span></span>

    <span data-ttu-id="61f3f-119">![Példa az Időszak fedezeti kód használatára](./media/coverage-code-period.png "Példa az Időszak fedezeti kód használatára")</span><span class="sxs-lookup"><span data-stu-id="61f3f-119">![Example of Period coverage code use](./media/coverage-code-period.png "Example of Period coverage code use")</span></span>

- <span data-ttu-id="61f3f-120">**Igény** – A feltöltési módszerben a rendszer a termékre vonatkozó szükséglet alapján tervezett beszerzési, átmozgatási vagy termelési rendelést hoz létre.</span><span class="sxs-lookup"><span data-stu-id="61f3f-120">**Requirement** – In the replenishment method, the system creates a planned purchase, transfer, or production order per requirement for the product.</span></span> <span data-ttu-id="61f3f-121">Ez a módszer olyan költséges termékeknél használatos, amelyekre időszakos igény van.</span><span class="sxs-lookup"><span data-stu-id="61f3f-121">This method is used for expensive products that have intermittent demand.</span></span> <span data-ttu-id="61f3f-122">Az *Igény* fedezeti kódot gyakran használják konfigurálható termékekhez és rendelésre történő gyártás esetén.</span><span class="sxs-lookup"><span data-stu-id="61f3f-122">The *Requirement* coverage code is often used for configurable products or make-to-order scenarios.</span></span> <span data-ttu-id="61f3f-123">A következő ábrán egy példa látható.</span><span class="sxs-lookup"><span data-stu-id="61f3f-123">The following illustration shows an example.</span></span>

    <span data-ttu-id="61f3f-124">![Példa az Igény fedezeti kód használatára](./media/coverage-code-requirement.png "Példa az Igény fedezeti kód használatára")</span><span class="sxs-lookup"><span data-stu-id="61f3f-124">![Example of Requirement coverage code use](./media/coverage-code-requirement.png "Example of Requirement coverage code use")</span></span>

- <span data-ttu-id="61f3f-125">**Min./max.**</span><span class="sxs-lookup"><span data-stu-id="61f3f-125">**Min./Max.**</span></span> <span data-ttu-id="61f3f-126">– A feltöltési módszer a készlet szintjén alapul.</span><span class="sxs-lookup"><span data-stu-id="61f3f-126">– The replenishment method is based on the inventory level.</span></span> <span data-ttu-id="61f3f-127">Ha az előrejelzett aktuális szint egy konkrét küszöbérték alatt van, akkor meghatározza a készlet adott szintig történő feltöltését.</span><span class="sxs-lookup"><span data-stu-id="61f3f-127">It defines the replenishment of inventory up to a specific level when the predicted on-hand level is below a specific threshold.</span></span> <span data-ttu-id="61f3f-128">A feltöltési mennyiség a maximális szint és az előre jelzett aktuális szint közötti különbség lesz.</span><span class="sxs-lookup"><span data-stu-id="61f3f-128">The replenishment quantity will be the difference between the maximum level and the predicted on-hand level.</span></span> <span data-ttu-id="61f3f-129">A *Min./max.*</span><span class="sxs-lookup"><span data-stu-id="61f3f-129">The *Min./Max.*</span></span> <span data-ttu-id="61f3f-130">fedezeti kódot gyakran használják kiszámítható készletkérésre, a legkeresettebb vagy a kevésbé drága termékeknél.</span><span class="sxs-lookup"><span data-stu-id="61f3f-130">coverage code is often used for predictable inventory draw, high runners, or less expensive products.</span></span> <span data-ttu-id="61f3f-131">A következő ábrán egy példa látható.</span><span class="sxs-lookup"><span data-stu-id="61f3f-131">The following illustration shows an example.</span></span>

    <span data-ttu-id="61f3f-132">![Példa a Min./max. fedezeti kód használatára](./media/coverage-code-min-max.png "Példa a Min./max. fedezeti kód használatára")</span><span class="sxs-lookup"><span data-stu-id="61f3f-132">![Example of Min./Max. coverage code use](./media/coverage-code-min-max.png "Example of Min./Max. coverage code use")</span></span>

- <span data-ttu-id="61f3f-133">**Manuális** – A feltöltési módszernél a rendszer nem javasol beszerzési, átviteli vagy termelési rendeléseket a termékhez.</span><span class="sxs-lookup"><span data-stu-id="61f3f-133">**Manual** – In the replenishment method, the system doesn't suggest purchase, transfer, or production orders for the product.</span></span> <span data-ttu-id="61f3f-134">Ehelyett a termék tervezője felelős a termék feltöltéséhez szükséges rendelések létrehozásáért.</span><span class="sxs-lookup"><span data-stu-id="61f3f-134">Instead, the planner for the product is responsible for creating the required orders for the replenishment of the product.</span></span> <span data-ttu-id="61f3f-135">A *Manuális* fedezeti kódot gyakran használják olyan termékekhez, amelyeknél nincs szükség rendszer által generált tervezett rendelésekre.</span><span class="sxs-lookup"><span data-stu-id="61f3f-135">The *Manual* coverage code is often used for products that system-generated planned orders aren't wanted for.</span></span>

## <a name="impact-of-the-order-quantity-from-default-order-settings"></a><span data-ttu-id="61f3f-136">Az alapértelmezett rendelési beállításokból származó rendelési mennyiség hatása</span><span class="sxs-lookup"><span data-stu-id="61f3f-136">Impact of the order quantity from default order settings</span></span>

<span data-ttu-id="61f3f-137">A kiadott termékekhez tartozó **Alapértelmezett rendelésbeállítások** oldalon megadhatók a **Beszerzési rendelés**, a **Készlet** és az **Értékesítési rendelés** gyorslapon lévő következő mennyiségi beállítások.</span><span class="sxs-lookup"><span data-stu-id="61f3f-137">On the **Default order setting** page for a released product, you can specify each of following quantity settings on the **Purchase order**, **Inventory**, and **Sales order** FastTabs.</span></span> <span data-ttu-id="61f3f-138">(A **Készlet** gyorslap az átmozgatási és a termelési rendelésekhez is használható.)</span><span class="sxs-lookup"><span data-stu-id="61f3f-138">(The **Inventory** FastTab is used for both transfer orders and production orders.)</span></span>

- <span data-ttu-id="61f3f-139">**Többszörös** – A tervezett rendelések ennek a mennyiségnek a többszörösei lesznek.</span><span class="sxs-lookup"><span data-stu-id="61f3f-139">**Multiple** – Planned orders will be a multiple of this quantity.</span></span>

    <span data-ttu-id="61f3f-140">Ha a **Többszörös** mező értéke például *5*, akkor a rendelés mennyisége 10, 15, 20, stb. lehet.</span><span class="sxs-lookup"><span data-stu-id="61f3f-140">For example, if the **Multiple** field is set to *5*, an order can be for a quantity of 5, 10, 15, 20, and so on.</span></span>

- <span data-ttu-id="61f3f-141">**Minimális rendelési mennyiség** – A tervezett rendelések nem lesznek kisebbek, mint a megadott érték.</span><span class="sxs-lookup"><span data-stu-id="61f3f-141">**Min. order quantity** – Planned orders won't be less than the specified value.</span></span>

    <span data-ttu-id="61f3f-142">Ha a **Minimális rendelési mennyiség** mező értéke például *10*, akkor a rendszer által létrehozott tervezett rendelés mennyisége még akkor is 10 lesz, ha az igény kielégítéséhez csak 4 szükséges.</span><span class="sxs-lookup"><span data-stu-id="61f3f-142">For example, if the **Min. order quantity** field is set to *10*, a planned order for a quantity of 10 will be created, even if only four are required to fulfill the demand.</span></span>

- <span data-ttu-id="61f3f-143">**Maximális rendelési mennyiség** – A tervezett rendelések nem lesznek nagyobbak, mint a megadott érték.</span><span class="sxs-lookup"><span data-stu-id="61f3f-143">**Max. order quantity** – Planned orders won't exceed the specified value.</span></span> <span data-ttu-id="61f3f-144">Ha az igény több, mint a **Maximális rendelési mennyiség**, akkor több tervezett rendelés jön létre a fedezéséhez.</span><span class="sxs-lookup"><span data-stu-id="61f3f-144">If the demand is more than the **Max. order quantity** value, multiple planned orders will be created to cover it.</span></span>

    <span data-ttu-id="61f3f-145">Ha például a **Maximális rendelés mennyisége** mező értéke *100*, 100-ra van állítva, és az igény 450, akkor négy 100 mennyiségű és egy 50 mennyiségű tervezett rendelés jön létre.</span><span class="sxs-lookup"><span data-stu-id="61f3f-145">For example, if the **Max. order quantity** field is set to *100*, and the demand is 450, four planned orders for a quantity of 100 and one planned order for a quantity of 50 will be created.</span></span>

## <a name="examples-of-replenishment-that-use-the-minmax-coverage-code"></a><span data-ttu-id="61f3f-146">Példák a Min./max. fedezeti kódot használó</span><span class="sxs-lookup"><span data-stu-id="61f3f-146">Examples of replenishment that use the Min./Max.</span></span> <span data-ttu-id="61f3f-147">feltöltésre</span><span class="sxs-lookup"><span data-stu-id="61f3f-147">coverage code</span></span>

<span data-ttu-id="61f3f-148">Ha egy terméknél nem ad meg értéket a **Többszörös** mezőben az **Alapértelmezett rendelésbeállítások** oldalon, és ha a *Min./max.*</span><span class="sxs-lookup"><span data-stu-id="61f3f-148">If you don't specify a value in the **Multiple** field for a product on the **Default order setting** page, and if you're using the *Min./Max.*</span></span> <span data-ttu-id="61f3f-149">feltöltési módot használja, akkor a Tervezési optimalizálás egy konkrét szintig feltölti a készletet, amikor az előrejelzett készletszint egy adott küszöbérték alá csökken.</span><span class="sxs-lookup"><span data-stu-id="61f3f-149">replenishment method, Planning Optimization will replenish the inventory up to a specific level when the predicted on-hand level is below a specific threshold.</span></span>

<span data-ttu-id="61f3f-150">Ha egy termékhez több mennyiséget ad meg, akkor a *Min./max.*</span><span class="sxs-lookup"><span data-stu-id="61f3f-150">If you define a multiple quantity for a product, the *Min./Max.*</span></span> <span data-ttu-id="61f3f-151">feltöltési mód viselkedése módosul, és figyelembe veszi a **Többszörös** értéket.</span><span class="sxs-lookup"><span data-stu-id="61f3f-151">replenishment method changes its behavior and considers the **Multiple** value.</span></span>

<span data-ttu-id="61f3f-152">Más szóval, a Tervezési optimalizálás akkor is feltölti a megadott maximális szintig a készletet, ha az előrejelzett készletszint kisebb, mint a megadott minimális szint.</span><span class="sxs-lookup"><span data-stu-id="61f3f-152">In other words, Planning Optimization will still replenish the inventory up to the defined maximum level when the predicted on-hand level is less than the defined minimum level.</span></span> <span data-ttu-id="61f3f-153">A feltöltési mennyiségnek azonban a **Többszörös** érték többszörösének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="61f3f-153">However, the replenishment quantity must be a multiple of the **Multiple** value.</span></span>

<span data-ttu-id="61f3f-154">Ha a feltöltési mennyiség (a maximális szint és az előrejelzett tényleges szint különbsége) nem a megadott többszörös mennyiség többszöröse, akkor a Tervezési optimalizálás az első olyan lehetséges értéket használja, amely az előrejelzett készletszinttel együtt a maximális szint alá kerül.</span><span class="sxs-lookup"><span data-stu-id="61f3f-154">If the replenishment quantity (the difference between the maximum level and the predicted on-hand level) isn't a multiple of the defined multiple quantity, Planning Optimization uses the first possible value that, together with predicted on-hand level, will be below the maximum level.</span></span> <span data-ttu-id="61f3f-155">Ha az összeg kisebb a minimális szintnél, akkor a Tervezési optimalizálás az első olyan értéket használja, amely az előrejelzett tényleges szinttel a maximális szint felett lesz.</span><span class="sxs-lookup"><span data-stu-id="61f3f-155">If the sum is less than the minimum level, Planning Optimization uses the first value that, together with predicted on-hand, will be above the maximum level.</span></span>

<span data-ttu-id="61f3f-156">Az alábbi alszakaszokban néhány olyan példa látható, amely bemutatja, hogy egy termék több rendelési mennyisége milyen hatással van a *Min./max.*</span><span class="sxs-lookup"><span data-stu-id="61f3f-156">The following subsections provide some examples that show how the multiple order quantity for a product affects the result of the *Min./Max.*</span></span> <span data-ttu-id="61f3f-157">feltöltési módra.</span><span class="sxs-lookup"><span data-stu-id="61f3f-157">replenishment method.</span></span>

### <a name="example-1"></a><span data-ttu-id="61f3f-158">1. példa</span><span class="sxs-lookup"><span data-stu-id="61f3f-158">Example 1</span></span>

<span data-ttu-id="61f3f-159">Egy termék a következő konfigurációval rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="61f3f-159">A product has the following configuration:</span></span>

- <span data-ttu-id="61f3f-160">**Fedezeti kód:** *Min./max.*</span><span class="sxs-lookup"><span data-stu-id="61f3f-160">**Coverage code:** *Min./Max.*</span></span>
- <span data-ttu-id="61f3f-161">**Minimum:** *15*</span><span class="sxs-lookup"><span data-stu-id="61f3f-161">**Minimum:** *15*</span></span>
- <span data-ttu-id="61f3f-162">**Maximum:** *22*</span><span class="sxs-lookup"><span data-stu-id="61f3f-162">**Maximum:** *22*</span></span>
- <span data-ttu-id="61f3f-163">**Többszörös:** *0*</span><span class="sxs-lookup"><span data-stu-id="61f3f-163">**Multiple:** *0*</span></span>

<span data-ttu-id="61f3f-164">A termékhez 10 darab az aktuális készlet, és nincs más igény vagy ellátás.</span><span class="sxs-lookup"><span data-stu-id="61f3f-164">There are 10 pieces of on-hand inventory for the product, and there is no other demand or supply.</span></span>

<span data-ttu-id="61f3f-165">Az alaptervezés futtatásakor egy 12 darabos tervezett rendelés jön létre, amely a maximális mennyiségre feltölti a készletet.</span><span class="sxs-lookup"><span data-stu-id="61f3f-165">When master planning runs, a planned order for 12 pieces is created to replenish inventory to the maximum quantity.</span></span>

### <a name="example-2"></a><span data-ttu-id="61f3f-166">2. példa</span><span class="sxs-lookup"><span data-stu-id="61f3f-166">Example 2</span></span>

<span data-ttu-id="61f3f-167">Egy termék a következő konfigurációval rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="61f3f-167">A product has the following configuration:</span></span>

- <span data-ttu-id="61f3f-168">**Fedezeti kód:** *Min./max.*</span><span class="sxs-lookup"><span data-stu-id="61f3f-168">**Coverage code:** *Min./Max.*</span></span>
- <span data-ttu-id="61f3f-169">**Minimum:** *15*</span><span class="sxs-lookup"><span data-stu-id="61f3f-169">**Minimum:** *15*</span></span>
- <span data-ttu-id="61f3f-170">**Maximum:** *22*</span><span class="sxs-lookup"><span data-stu-id="61f3f-170">**Maximum:** *22*</span></span>
- <span data-ttu-id="61f3f-171">**Többszörös:** *5*</span><span class="sxs-lookup"><span data-stu-id="61f3f-171">**Multiple:** *5*</span></span>

<span data-ttu-id="61f3f-172">A termékhez 10 darab az aktuális készlet, és nincs más igény vagy ellátás.</span><span class="sxs-lookup"><span data-stu-id="61f3f-172">There are 10 pieces of on-hand inventory for the product, and there is no other demand or supply.</span></span>

<span data-ttu-id="61f3f-173">Az alaptervezés futtatásakor egy 10 darabos tervezett rendelés jön létre (mivel a feltöltés 15 darab, az aktuális készlet pedig 10, és ez meghaladja a maximális mennyiséget).</span><span class="sxs-lookup"><span data-stu-id="61f3f-173">When master planning runs, a planned order for 10 pieces is created (because 15 pieces of replenishment plus 10 pieces of on-hand inventory will exceed the maximum quantity).</span></span>

### <a name="example-3"></a><span data-ttu-id="61f3f-174">3. példa</span><span class="sxs-lookup"><span data-stu-id="61f3f-174">Example 3</span></span>

<span data-ttu-id="61f3f-175">Egy termék a következő konfigurációval rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="61f3f-175">A product has the following configuration:</span></span>

- <span data-ttu-id="61f3f-176">**Fedezeti kód:** *Min./max.*</span><span class="sxs-lookup"><span data-stu-id="61f3f-176">**Coverage code:** *Min./Max.*</span></span>
- <span data-ttu-id="61f3f-177">**Minimum:** *21*</span><span class="sxs-lookup"><span data-stu-id="61f3f-177">**Minimum:** *21*</span></span>
- <span data-ttu-id="61f3f-178">**Maximum:** *24*</span><span class="sxs-lookup"><span data-stu-id="61f3f-178">**Maximum:** *24*</span></span>
- <span data-ttu-id="61f3f-179">**Többszörös:** *5*</span><span class="sxs-lookup"><span data-stu-id="61f3f-179">**Multiple:** *5*</span></span>

<span data-ttu-id="61f3f-180">A termékhez 10 darab az aktuális készlet, és nincs más igény vagy ellátás.</span><span class="sxs-lookup"><span data-stu-id="61f3f-180">There are 10 pieces of on-hand inventory for the product, and there is no other demand or supply.</span></span>

<span data-ttu-id="61f3f-181">Az alaptervezés futtatásakor egy 15 darabos tervezett rendelés jön létre (mivel a feltöltés 10 darab, az aktuális készlet pedig 10, és ez kisebb a minimális mennyiségnél).</span><span class="sxs-lookup"><span data-stu-id="61f3f-181">When master planning runs, the planned order for 15 pieces is created (because 10 pieces of replenishment plus 10 pieces of on-hand inventory will be less than the minimum quantity).</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
