---
title: "Szállítás kezelés áttekintése"
description: "Ez a témakör a Microsoft Dynamics 365 for Finance and Operations rendszer szállításkezelési funkcióját mutatja be."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 30251
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1c71c8f6c4f94342ac18cbfb7dfbc02ddb3f9f35
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="transportation-management-overview"></a><span data-ttu-id="7fe19-103">Szállítás kezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="7fe19-103">Transportation management overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="7fe19-104">Ez a témakör a Microsoft Dynamics 365 for Finance and Operations rendszer szállításkezelési funkcióját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="7fe19-104">This topic gives an overview of the transportation management functionality in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="7fe19-105">A Szállításkezelés lehetővé teszi, hogy a vállalata szállítását használja, továbbá hogy azonosítsa a szállítót és az útvonal-tervezési megoldásokat a bejövő és a kimenő rendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="7fe19-105">Transportation management lets you use your company’s transportation, and also lets you identify vendor and routing solutions for inbound and outbound orders.</span></span> <span data-ttu-id="7fe19-106">Például azonosíthatja a leggyorsabb vagy a legolcsóbb útvonalat a szállítmányhoz.</span><span class="sxs-lookup"><span data-stu-id="7fe19-106">For example, you can identify the fastest route or the least expensive rate for a shipment.</span></span> <span data-ttu-id="7fe19-107">A következő táblázat bemutatja a szállításkezelésben használatos fő eseteket a Microsoft Dynamics 365 for Finance and Operations rendszerben.</span><span class="sxs-lookup"><span data-stu-id="7fe19-107">The following table describes the main scenarios for using Transportation management in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fe19-108">Eset</span><span class="sxs-lookup"><span data-stu-id="7fe19-108">Scenario</span></span></th>
<th><span data-ttu-id="7fe19-109">A szállításkezelés segíthet:</span><span class="sxs-lookup"><span data-stu-id="7fe19-109">How Transportation management can help</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="7fe19-110">A külső logisztikai szolgáltatók használatában a szállítási tevékenységekhez.</span><span class="sxs-lookup"><span data-stu-id="7fe19-110">Use external logistics providers for transportation activities.</span></span></td>
<td><span data-ttu-id="7fe19-111">A szállításkezelés használatában a bejövő és/vagy kimenő szállításhoz.</span><span class="sxs-lookup"><span data-stu-id="7fe19-111">Use Transportation management for inbound and/or outbound transportation.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7fe19-112">A vállalat saját flottája elérhető kiszállításhoz/felvételhez, és a szállítási költségek a vevőkre vannak terhelve.</span><span class="sxs-lookup"><span data-stu-id="7fe19-112">The company's own fleet is available for delivery/pickup, and delivery charges are passed on to customers.</span></span></td>
<td><span data-ttu-id="7fe19-113">A kimenő folyamatokhoz használhatja a szállításkezelést, hogy meghatározza a szállítási díjakat és a vevőkre terhelje azokat.</span><span class="sxs-lookup"><span data-stu-id="7fe19-113">For the outbound processes, you can use Transportation management to determine the transportation charges and pass them on to customers.</span></span> <span data-ttu-id="7fe19-114">Azonban a szállítói számlák egyeztetési folyamata nem szükséges.</span><span class="sxs-lookup"><span data-stu-id="7fe19-114">However, the carrier invoice reconciliation process isn't required.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7fe19-115">A vállalat saját flottája elérhető kiszállításhoz/felvételhez, de a szállítási díjak nincsenek a vevőkre terhelve, mert a termékárak tartalmazzák a szállítást.</span><span class="sxs-lookup"><span data-stu-id="7fe19-115">The company's own fleet is available for delivery/pickup, but delivery charges aren't passed on to customers, because product prices include transportation.</span></span></td>
<td><span data-ttu-id="7fe19-116">Sok szállításkezelési funkcióra nincs szükség.</span><span class="sxs-lookup"><span data-stu-id="7fe19-116">A lot of the Transportation management functionality isn't required.</span></span> <span data-ttu-id="7fe19-117">Azonban használhatja a szállításkezelést, hogy meghatározza a szállítási díjakat, és ennek megfelelően állítsa be az eladási árat.</span><span class="sxs-lookup"><span data-stu-id="7fe19-117">However, you can use Transportation management to determine the transportation rates and adjust the sales price accordingly.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7fe19-118">A logisztikai szolgáltatást egy másik jogi személy biztosítja, ugyanazon vállalatból.</span><span class="sxs-lookup"><span data-stu-id="7fe19-118">Logistics service is provided by another legal entity in the same company.</span></span></td>
<td><ul>
<li><span data-ttu-id="7fe19-119">Úgy használhatja a szállításkezelést, hogy a másik jogi személyt úgy kezeli, mint bármely másik szállítmányozót.</span><span class="sxs-lookup"><span data-stu-id="7fe19-119">You can use Transportation management by treating the other legal entity like any other shipping carrier.</span></span> <span data-ttu-id="7fe19-120">Nem automatizálhatja a gazdasági tranzakciókat jogi személyek között.</span><span class="sxs-lookup"><span data-stu-id="7fe19-120">You can't automate the economic transactions between legal entities.</span></span> <span data-ttu-id="7fe19-121">Ezért ezeket a tranzakciókat manuálisan kell kezelnie (például egy beszerzési rendelés létrehozásával).</span><span class="sxs-lookup"><span data-stu-id="7fe19-121">Therefore, you must handle these transactions manually (for example, by creating a purchase order).</span></span></li>
<li><span data-ttu-id="7fe19-122">Abban a jogi személyben, amely a logisztikai szolgáltatást biztosítja a szállításkezelés használható a szállítási díjak megállapításához.</span><span class="sxs-lookup"><span data-stu-id="7fe19-122">In the legal entity that provides the logistics services, Transportation management can be used to determine transportation rates.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-finance-and-operations"></a><span data-ttu-id="7fe19-123">Szállítási tervezés a Finance and Operations rendszerben</span><span class="sxs-lookup"><span data-stu-id="7fe19-123">Planning transportation in Finance and Operations</span></span>
<span data-ttu-id="7fe19-124">A szállításkezelésben a szállítási tervezés alapulhat rendeléseken vagy az adott rendelések alapján létrehozott szállítmányokon.</span><span class="sxs-lookup"><span data-stu-id="7fe19-124">In Transportation management, transportation planning can be based either on orders or on the shipments that are created based on those orders.</span></span> <span data-ttu-id="7fe19-125">A szállítmány mindig létezik valamikor a folyamat során, de nem szükséges a szállítási tervezéshez.</span><span class="sxs-lookup"><span data-stu-id="7fe19-125">The shipments always exist at some point in time but aren't required for transportation planning.</span></span> <span data-ttu-id="7fe19-126">Az átmozgatási rendelések a kimeneti eset részei, és megtervezhetők az értékesítési rendelésekkel közösen.</span><span class="sxs-lookup"><span data-stu-id="7fe19-126">Transfer orders are part of the outbound scenario and can be planned together with sales orders.</span></span> 

![Rajz betöltése](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a><span data-ttu-id="7fe19-128">Kimenő szállítás</span><span class="sxs-lookup"><span data-stu-id="7fe19-128">Inbound transportation</span></span>
<span data-ttu-id="7fe19-129">Amikor cikkeket rendel szállítótól, és a cikkeket a raktárába kell szállítani, akkor érdemes saját magának elrendeznie a cikkek szállítását.</span><span class="sxs-lookup"><span data-stu-id="7fe19-129">When you order items from a vendor, and the items must be delivered to your warehouse, you might want to arrange the transport of the items yourself.</span></span> <span data-ttu-id="7fe19-130">Arra használhatja a Finance and Operations rendszert, hogy megtervezze egy beérkező rakomány fogadását.</span><span class="sxs-lookup"><span data-stu-id="7fe19-130">You can use Finance and Operations to plan the transportation and receipt of the inbound load.</span></span> <span data-ttu-id="7fe19-131">A következő ábra bemutatja a szállítás bejövő terhelésének tervezéséhez és feldolgozásához használatos üzleti folyamatokat.</span><span class="sxs-lookup"><span data-stu-id="7fe19-131">The following illustration shows the business process flow for planning transportation for an inbound load.</span></span> 

![Üzleti folyamatábra: bejövő szállítási rakományok](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a><span data-ttu-id="7fe19-133">Kimenő szállítás</span><span class="sxs-lookup"><span data-stu-id="7fe19-133">Outbound transportation</span></span>
<span data-ttu-id="7fe19-134">Megtervezheti és feldolgozhat egy kimenő terhelést bizonyos cikkek szállításához a cég raktárából a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="7fe19-134">You can plan and process an outbound load to ship specific items from a company’s warehouse to a customer.</span></span> <span data-ttu-id="7fe19-135">Arra használhatja a Finance and Operations rendszert, hogy megtervezze egy kimenő rakomány szállítását.</span><span class="sxs-lookup"><span data-stu-id="7fe19-135">You can use Finance and Operations to plan the transportation and shipping of an outbound load.</span></span> <span data-ttu-id="7fe19-136">A következő ábra bemutatja a szállítás kimenő terhelésének tervezéséhez és feldolgozásához használatos üzleti folyamatokat.</span><span class="sxs-lookup"><span data-stu-id="7fe19-136">The following illustration shows the business process flow for planning and processing outbound loads for shipping.</span></span> 

![Kimenő rakományok tervezése és feldolgozása](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a><span data-ttu-id="7fe19-138">Rakomány-összeállítás</span><span class="sxs-lookup"><span data-stu-id="7fe19-138">Load building</span></span>
<span data-ttu-id="7fe19-139">A Finance and Operations biztosít egy rakomány-összeállítási stratégiát, amely a Térfogaton alapuló rakomány-összeállítási stratégia nevet viseli.</span><span class="sxs-lookup"><span data-stu-id="7fe19-139">Finance and Operations provides a load building strategy that is named the Volume-based load building strategy.</span></span> <span data-ttu-id="7fe19-140">Ez a stratégia lehetővé teszi a rakomány-sablonban megadott maximális magasság- és súlyértékek használatát, vagy a beállítások felülírását új értékek megadásával.</span><span class="sxs-lookup"><span data-stu-id="7fe19-140">This strategy lets you use the maximum values that are specified for height and weight in the load template, or you can override the settings by entering new values.</span></span> <span data-ttu-id="7fe19-141">A használatához válassza ki a stratégiát a **Rakomány-összeállító munkaterület** oldal **Beállítások** gyorslapján található **Rakomány-összeállítási stratégia** mezőben.</span><span class="sxs-lookup"><span data-stu-id="7fe19-141">To use this strategy, select it in the **Load building strategy** field on the **Setup** FastTab on the **Load building workbench** page.</span></span> <span data-ttu-id="7fe19-142">Ezenkívül hozzáadhatja a saját rakomány-összeállítási stratégiáját egy új osztály létrehozásával az alkalmazásobjektum-fán (AOT) belül.</span><span class="sxs-lookup"><span data-stu-id="7fe19-142">In addition, you can add your own load-building strategies by creating a new class in the Application Object Tree (AOT).</span></span>




