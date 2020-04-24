---
title: Azonosítótábla fogadása a Raktárkezelő mobilalkalmazáson keresztül
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a Raktárkezelő mobilalkalmazást a tényleges készlet fogadására használt azonosítótábla-feldolgozási folyamathoz.
author: perlynne
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 98cd608edea1d5365d0d3532244f1fcdb6293d3c
ms.sourcegitcommit: 3a823444005d316bd95fc663e2dbc8252ac7d93a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261338"
---
# <a name="license-plate-receiving-via-the-warehousing-mobile-app"></a><span data-ttu-id="2304c-103">Azonosítótábla fogadása a Raktárkezelő mobilalkalmazáson keresztül</span><span class="sxs-lookup"><span data-stu-id="2304c-103">License plate receiving via the Warehousing mobile app</span></span>

<span data-ttu-id="2304c-104">Ez a témakör azt mutatja be, hogyan lehet beállítani a Raktárkezelő mobilalkalmazást a tényleges készlet fogadására használt azonosítótábla-feldolgozási folyamat támogatásához.</span><span class="sxs-lookup"><span data-stu-id="2304c-104">This topic explains how to set up the Warehousing mobile app so that it supports using a license plate receiving process to receive physical inventory.</span></span>

<span data-ttu-id="2304c-105">Ezen funkció segítségével gyorsan rögzítheti az előzetes kiszállítási értesítéshez (ASN) kapcsolódó bejövő készlet bevételezését.</span><span class="sxs-lookup"><span data-stu-id="2304c-105">You can use this functionality to quickly record the receipt of inbound inventory that is related to an advance ship notice (ASN).</span></span> <span data-ttu-id="2304c-106">A rendszer automatikusan létrehoz egy ASN-t, amikor a raktárkezelési folyamatokat egy átmozgatási rendelés szállítására használják.</span><span class="sxs-lookup"><span data-stu-id="2304c-106">The system automatically creates an ASN when warehouse management processes are used to ship a transfer order.</span></span> <span data-ttu-id="2304c-107">A beszerzési rendelés folyamatahoz egy ASN manuálisan is rögzíthető, vagy automatikusan importálható a bejövő ASN adatentitás folyamata segítségével.</span><span class="sxs-lookup"><span data-stu-id="2304c-107">For the purchase order process, an ASN can be manually recorded, or it can be automatically imported by using an inbound ASN data entity process.</span></span>

<span data-ttu-id="2304c-108">Az ASN-adatok a rakományokhoz és a szállítmányokhoz a *csomagolási struktúrákon* keresztül kapcsolhatók, ahol a raklapok (a szülő azonosítótáblák) tartalmazhatnak eseteket (beágyazott azonosítótáblák).</span><span class="sxs-lookup"><span data-stu-id="2304c-108">The ASN data is linked to loads and shipments via the *packing structures*, where pallets (parent license plates) can contain cases (nested license plates).</span></span>

> [!NOTE]
> <span data-ttu-id="2304c-109">Hogy csökkentse a készlettranzakciók számát, amikor beágyazott azonosítótáblákkal rendelkező csomagolási struktúrák vannak használatban a rendszer rögzíti a fizikai aktuális készletet a szülő azonosítótáblára.</span><span class="sxs-lookup"><span data-stu-id="2304c-109">To reduce the number of inventory transactions when packing structures that have nested license plates are used, the system records the physical on-hand inventory on the parent license plate.</span></span> <span data-ttu-id="2304c-110">Ha azt szeretné, hogy a rendszer a tényleges aktuális készletet a szülő rendszámtábla és a beágyazott rendszámtábla között a csomagolási struktúra adatainak megfelelően mozgassa, a mobileszköznek egy olyan menüelemet kell biztosítania, amely a *Csomagolás beágyazott azonosítótáblákhoz* munkalétrehozási folyamaton alapul.</span><span class="sxs-lookup"><span data-stu-id="2304c-110">To trigger the movement of the physical on-hand inventory from the parent license plate to the nested license plates, based on the packing structure data, the mobile device must provide a menu item that is based on the *Pack to nested license plates* work creation process.</span></span>

<!-- To be used later (will require further editing):
## Warehousing mobile device app processing

When a worker scans an incoming license plate ID, the system initializes a license plate receiving process. Based on this information, the content of the license plate (data coming from the ASN) gets physically registered at the inbound dock location. The flows that follow will depend your business process needs.

## Work policies

As with (for example) the *Report as finished* mobile device menu item process, the license plate receiving process supports several workflows based on the defined setup.

### Work policies with work creation

Registration of physical on-hand where either the same warehouse worker immediately process a put-away work process following the inbound receiving (License plate receiving and put away) or where the registration and put away process gets handled as two different warehouse operations (License plate receiving) following the processing of the put-away work by using the existing work process via another mobile device menu item.

## Work policies without work creation

You can use the license plate receiving process without creating work by using the *License plate receiving without creating work* feature.

By defining **Work policies** with a **Work order type** of *Transfer receipt* and/or *Purchase orders*, and using the **Process** for **License plate receiving (and put away)**, the two Warehousing app process:

- License plate receiving
- License plate receiving and put away

will not create work, but only register the inbound physical inventory on the license plate at the inbound receiving dock.

For more information about the *Report as finished* production scenario, see the [Warehouse work policies overview](warehouse-work-policies.md).

-->

## <a name="show-or-skip-the-receiving-summary-page"></a><span data-ttu-id="2304c-111">A bevételezési összesítő lap megjelenítése vagy kihagyása</span><span class="sxs-lookup"><span data-stu-id="2304c-111">Show or skip the receiving summary page</span></span>

<span data-ttu-id="2304c-112">Az *Annak szabályzása, hogy meg legyen-e jelenítve egy fogadás összegzése lap a mobileszközökön* funkció használatával kihasználhatja egy további részletes Raktári alkalmazásfolyamat előnyeit az azonosítótábla-fogadási folyamat részeként.</span><span class="sxs-lookup"><span data-stu-id="2304c-112">You can use the *Control whether to display a receiving summary page on mobile devices* feature to take advantage of an additional detailed Warehouse app flow as part of the license plate receiving process.</span></span>

<span data-ttu-id="2304c-113">A funkció használata előtt be kell azt kapcsolnia saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="2304c-113">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="2304c-114">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="2304c-114">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="2304c-115">A **Funkció kezelése** munkaterületen ez a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="2304c-115">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="2304c-116">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="2304c-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="2304c-117">**Funkció neve:** *Annak beállítása hogy megjelenjen-e bevételezési összesítő lap a mobileszközökön*</span><span class="sxs-lookup"><span data-stu-id="2304c-117">**Feature name:** *Control whether to display a receiving summary page on mobile devices*</span></span>

<span data-ttu-id="2304c-118">Ha ez a funkció be van kapcsolva, akkor az azonosítótábla fogadására és betárolására szolgáló menüelemek tartalmazzák a **Fogadó összesítő lap megjelenítése** beállítást.</span><span class="sxs-lookup"><span data-stu-id="2304c-118">When this feature is turned on, mobile device menu items for license plate receiving or license plate receiving and put-away will provide a **Display receiving summary page** setting.</span></span> <span data-ttu-id="2304c-119">Ez a beállítás a következő lehetőségeket biztosítja:</span><span class="sxs-lookup"><span data-stu-id="2304c-119">This setting has the following options:</span></span>

- <span data-ttu-id="2304c-120">**Részletes összefoglalás megjelenítése** – Az azonosítótábla fogadása során a dolgozók egy külön lapot fognak látni, amely a teljes ASN-információt jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="2304c-120">**Display a detailed summary** – During license plate receiving, workers will see an extra page that shows the full ASN information.</span></span>
- <span data-ttu-id="2304c-121">**Az összefoglalás kihagyása** – A dolgozók nem fogják látni a teljes ASN-információt.</span><span class="sxs-lookup"><span data-stu-id="2304c-121">**Skip the summary** – Workers won't see the full ASN information.</span></span> <span data-ttu-id="2304c-122">A raktári dolgozók nem állíthatnak be intézkedési kódot sem, illetve kivételeket adhatnak meg a bevételezési folyamat során.</span><span class="sxs-lookup"><span data-stu-id="2304c-122">Warehouse workers also won't be able to set a disposition code or add exceptions during the receiving process.</span></span>

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a><span data-ttu-id="2304c-123">Átmozgatási rendeléssel szállított azonosítótáblák használatának megakadályozása a célraktártól eltérő raktárban</span><span class="sxs-lookup"><span data-stu-id="2304c-123">Prevent transfer order–shipped license plates from being used at warehouses other than the destination warehouse</span></span>

<span data-ttu-id="2304c-124">Az azonosítótábla-bevételezési folyamat nem használható, ha az ASN tartalmaz egy rendszámtábla-azonosítót, amely már létezik, és tényleges aktuális adatokkal rendelkezik egy olyan raktári helyen, amely nem az a raktári hely, ahol az azonosítótábla regisztrációja történik.</span><span class="sxs-lookup"><span data-stu-id="2304c-124">A license plate receiving process can't be used if an ASN contains a license plate ID that already exists and has physical on-hand data at a warehouse location other than the warehouse location where the license plate registration is occurring.</span></span>

<span data-ttu-id="2304c-125">Az átmozgatási rendelés esetében, amikor az átmozgatási raktár nem követi nyomon az azonosítótáblákat (és ezért nem követi a tényleges aktuális készletet azonosítótáblánként) használhatja a *Átmozgatási rendeléssel szállított azonosítótáblák használatának megakadályozása a célraktártól eltérő raktárban* funkciót, amellyel megakadályozható az átvitel alatt lévő azonosítótáblák tényleges aktuális frissítése.</span><span class="sxs-lookup"><span data-stu-id="2304c-125">For transfer order scenarios where the transit warehouse doesn't track license plates (and therefore also doesn't track physical on-hand inventory per license plate), you can use the *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse* feature to prevent physical on-hand updates of license plates that are in transit.</span></span>

<span data-ttu-id="2304c-126">A funkció használata előtt be kell azt kapcsolnia saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="2304c-126">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="2304c-127">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="2304c-127">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="2304c-128">A **Funkció kezelése** munkaterületen ez a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="2304c-128">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="2304c-129">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="2304c-129">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="2304c-130">**Funkció neve:** *Átmozgatási rendeléssel szállított azonosítótáblák használatának megakadályozása a célraktártól eltérő raktárakban*</span><span class="sxs-lookup"><span data-stu-id="2304c-130">**Feature name:** *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse*</span></span>

<span data-ttu-id="2304c-131">Ha elérhetővé szeretné tenni ezt a funkciót, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="2304c-131">To manage the functionality when this feature is available, follow these steps.</span></span>

1. <span data-ttu-id="2304c-132">Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.</span><span class="sxs-lookup"><span data-stu-id="2304c-132">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="2304c-133">Az **Általános** lap **Azonosítótáblák** gyorslapján a következő értékek valamelyikére állítsa be a **Tranzitraktár azonosítótábla-irányelvei** mezőt:</span><span class="sxs-lookup"><span data-stu-id="2304c-133">On the **General** tab, on the **License plates** FastTab, set the **Transit warehouse license plate policy** field to one of the following values:</span></span>

    - <span data-ttu-id="2304c-134">**Nem nyomon követett rendszámtábla újrafelhasználásának engedélyezése** – A rendszer ugyanúgy működik, mint amikor a *Átmozgatási rendeléssel szállított azonosítótáblák használatának megakadályozása a célraktártól eltérő raktárakban* funkció nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="2304c-134">**Allow reuse of non-tracked license plate** – The system works the same way that it works when the *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse* feature isn't available.</span></span> <span data-ttu-id="2304c-135">Ez az érték az alapértelmezett beállítás a funkció első aktiválása alkalmával.</span><span class="sxs-lookup"><span data-stu-id="2304c-135">This value is the default setting when you first activate the feature.</span></span>
    - <span data-ttu-id="2304c-136">**Nem nyomon követett azonosítótáblák újrahasznosításának megakadályozása** – Csak a szállítót azonosítótáblákhoz kapcsolódó aktuális frissítések engedélyezettek a cél raktárban mindaddig, amíg az átmozgatási rendelés nem érkezett meg.</span><span class="sxs-lookup"><span data-stu-id="2304c-136">**Prevent reuse of non-tracked license plate** – Only on-hand updates that are related to a shipped license plate will be allowed at the destination warehouse until the transfer order has been received.</span></span>

## <a name="more-information"></a><span data-ttu-id="2304c-137">További információ</span><span class="sxs-lookup"><span data-stu-id="2304c-137">More information</span></span>

<!-- To read more about inbound loads, see [Link for Inbound load (Olga's doc.)] -->

<span data-ttu-id="2304c-138">A mobileszköz-menüelemek beállításával kapcsolatos további tudnivalókat lásd: [Mobileszközök beállítása raktári munkához](configure-mobile-devices-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="2304c-138">For more information about mobile device menu items, see [Set up mobile devices for warehouse work](configure-mobile-devices-warehouse.md).</span></span>
