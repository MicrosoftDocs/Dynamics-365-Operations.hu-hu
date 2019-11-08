---
title: Eszköz mértékei
description: A témakör bemutatja, hogyan lehet eszközmérték típusokat létrehozni az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bc6b9e944a7ecf6b769a8e3c2f9b1fbafaa60734
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626108"
---
# <a name="counters"></a><span data-ttu-id="9bcf4-103">Számlálók</span><span class="sxs-lookup"><span data-stu-id="9bcf4-103">Counters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9bcf4-104">A témakör bemutatja, hogyan lehet számláló típusokat létrehozni az Eszközkezelés modulban.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-104">The topic explains how to create counter types in Asset Management.</span></span> <span data-ttu-id="9bcf4-105">Az számlálótípusokkal lehet mérni a számlálókat lehet regisztrálni eszközökön, például a termelési órák száma vagy a tárgyi eszközön termelt mennyiség tekintetében.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-105">Counter types are used to make counter registrations on assets, for example, regarding number of production hours, or quantity produced on the asset.</span></span> <span data-ttu-id="9bcf4-106">Az eszköztípusok az számlálótípusokhoz kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-106">Asset types are related to the counter types.</span></span> <span data-ttu-id="9bcf4-107">Ez azt jelenti, hogy egy eszköz esetében csak akkor használható egy számláló, ha az eszköz típusánál be van állítva a számláló.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-107">This means that a counter can only be used on an asset if the counter is set up on the asset type used on the asset.</span></span>

<span data-ttu-id="9bcf4-108">Az eszközökre vonatkozó számlálóregisztrációk előtt létre kell hoznia a **Számlálókban**használni kívánt számlálótípusokat.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-108">Before you can make counter registrations on assets, you first create the counter types you want to use in **Counters**.</span></span> <span data-ttu-id="9bcf4-109">Ezután az eszközökre vonatkozó számlálóregisztrációkat kell létrehoznia a **Számlálók**helyen.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-109">Next, you can create counter registrations on assets in **Counters**.</span></span> 

<span data-ttu-id="9bcf4-110">Az számlálók a karbantartási tervekben használhatók.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-110">Counters can be used on maintenance plans.</span></span> <span data-ttu-id="9bcf4-111">Egy karbantartási terv sora lehet „Számláló” típusú például, amely a termelési órák számához vagy a termelt mennyiséggel kapcsolatos.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-111">A maintenance plan line can be of type "Counter", for example, relating to number of production hours or quantity produced.</span></span> 

<span data-ttu-id="9bcf4-112">Az számláló regisztrálása manuálisan vagy automatikusan történhet, a termelési órák vagy a termelt mennyiségek alapján.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-112">A counter registration can be updated manually or automatically based on production hours or quantity produced.</span></span> <span data-ttu-id="9bcf4-113">Egy számlálót úgy is be lehet állítani, hogy a három frissítési mód egyikét használja (a **Frissítés** mezőben választható ki a **Számlálók** alatt):</span><span class="sxs-lookup"><span data-stu-id="9bcf4-113">A counter can be set up to use one of three update methods (selected in the **Update** field in **Counters**):</span></span>
  
- <span data-ttu-id="9bcf4-114">Manuális – manuálisan kell regisztrálni az számlálóértékeket.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-114">Manual - you must manually register counter values.</span></span>  
- <span data-ttu-id="9bcf4-115">Termelési órák – a számláló automatikusan frissül a termelési órák száma alapján.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-115">Production hours - the counter is automatically updated based on number of production hours.</span></span>  
- <span data-ttu-id="9bcf4-116">Termelt mennyiség– a számláló automatikusan frissül a termelt mennyiség alapján.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-116">Production quantity - the counter is automatically updated based on number of quantity produced.</span></span>  

>[!NOTE]
><span data-ttu-id="9bcf4-117">Ha a termelt mennyiséget használja, az *összes* regisztrált cikk szerepel a számlálóregisztrációban, a jó mennyiség is és a hibás mennyiség is.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-117">If quantity produced is used, *all* registered items are included in the counter registration, good quantity as well as error quantity.</span></span> <span data-ttu-id="9bcf4-118">Ha szükséges, manuálisan is be lehet állítani számlálóregisztrációkat.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-118">It is always possible to make manual counter registrations, if required.</span></span>

## <a name="create-counter-types-for-asset-counter-registrations"></a><span data-ttu-id="9bcf4-119">Számlálótípusok létrehozása eszközszámláló regisztrációkhoz</span><span class="sxs-lookup"><span data-stu-id="9bcf4-119">Create counter types for asset counter registrations</span></span>

1. <span data-ttu-id="9bcf4-120">Válassza az **Eszközkezelés** > **Beállítás** > **Eszköztípusok** > **Számlálók**lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-120">Select **Asset management** > **Setup** > **Asset types** > **Counters**.</span></span>
2. <span data-ttu-id="9bcf4-121">Válassza ki az **Új** lehetőséget egy új számlálótípus létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-121">Select **New** to create a new counter type.</span></span>
3. <span data-ttu-id="9bcf4-122">Szúrjon be egy azonosítót a **Számláló** mezőbe, és a számláló nevét a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-122">Insert an ID in the **Counter** field, and a counter name in the **Name** field.</span></span>
4. <span data-ttu-id="9bcf4-123">Az **Általános** gyorslapon válassza ki a számlálóegységet az **Egység** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-123">On the **General** FastTab, select a counter unit in the **Unit** field.</span></span>
5. <span data-ttu-id="9bcf4-124">A **Frissítés** mezőben válassza ki a számlálóhoz használandó frissítési módot.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-124">In the **Update** field, select the update method to be used for the counter.</span></span>
6. <span data-ttu-id="9bcf4-125">Válassza az „igen” beállítást a **Számlálóértékek öröklése** választógombon ha a tárgyieszköz-szerkezethez tartozó tárgyi eszközöknek automatikusan örökölniük kell a fölérendelt a számlálóregisztrációkat.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-125">Select "Yes" on the **Inherit counter values** toggle button if child assets in an asset structure should automatically inherit counter registrations made on the parent asset.</span></span>
7. <span data-ttu-id="9bcf4-126">A **Teljes összesítés** mezőben válassza ki a számlálóhoz ezen számlálótípus felhasználásával használandó összesítési módszert.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-126">In the **Total aggregate** field, select the summation method to be used for a counter using this counter type.</span></span> <span data-ttu-id="9bcf4-127">Az „összeg” az alapbeállítás, amellyel a program folyamatosan hozzáadja a regisztrált értékeket a teljes értékhez.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-127">"Sum" is the standard selection used to continuously add registered values to the total value.</span></span> <span data-ttu-id="9bcf4-128">Az „Átlag” akkor használható, ha egy számláló esetében be van állítva egy eszköz küszöbértékének figyelése, például a hőmérséklet, rezgés vagy kopás az eszközön.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-128">"Average" can be used if a counter is set up to monitor a threshold, for example, regarding temperature, vibrations, or wear and tear on an asset.</span></span> 
8. <span data-ttu-id="9bcf4-129">Az **Eltérés felfelé** mezőbe írja be a felső szintet százalékban annak ellenőrzéséhez, hogy a manuális számlálóregisztrációk egy elvárt tartományon belül vannak-e.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-129">In the **Deviation over** field, insert the upper level in percent for validating if manual counter registrations are within an expected range.</span></span> <span data-ttu-id="9bcf4-130">Az ellenőrzés alapja a meglévő számlálóregisztrációk lineáris növekedése.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-130">The validation is based on a linear increase in existing counter registrations.</span></span>
9. <span data-ttu-id="9bcf4-131">Az **Eltérés lefelé** mezőbe írja be az alsó szintet százalékban annak ellenőrzéséhez, hogy a manuális számlálóregisztrációk egy elvárt tartományon belül vannak-e.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-131">In the **Deviation under** field, insert the lower level in percent for validating if manual counter registrations are within an expected range.</span></span> <span data-ttu-id="9bcf4-132">Az ellenőrzés alapja a meglévő számlálóregisztrációk lineáris csökkenése.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-132">The validation is based on a linear decrease in existing counter registrations.</span></span>
10. <span data-ttu-id="9bcf4-133">A **Típus** mezőben válassza ki, hogy milyen típusú üzenetet (tájékoztatás, figyelmeztetés, hiba) kíván megjeleníteni, ha a megadott tartományon kívüli eltérések következnek be, amikor manuális számlálóregisztrációkat hajt végre.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-133">In the **Type** field, select the type of message (information, warning, error) to be shown if deviations outside the defined range occur when you make manual counter registrations.</span></span>
11. <span data-ttu-id="9bcf4-134">Az **Eszköztípusok** gyorslapon adja meg azokat az eszköztípusokat, amelyeket a számláló használhat.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-134">On the **Asset types** FastTab, add the asset types that should be able to use the counter.</span></span>
12. <span data-ttu-id="9bcf4-135">A **Kapcsolódó eszközszámlálók** gyorslapon adja meg azokat azt a számlálót, amelyeket automatikusan frissíteni szeretne az számláló frissítésekor.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-135">On the **Related asset counters** FastTab, add the counter that you want to be automatically updated when this counter is updated.</span></span>


>[!NOTE]
><span data-ttu-id="9bcf4-136">A kapcsolódó számlálót csak akkor frissíti automatikusan a program, ha a kapcsolódó számláló tárgyieszköz-típusa szerepel a számláló beállításaiban.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-136">A related counter is automatically updated only if the related counter has the asset type, to which it is related, in the counter setup.</span></span> <span data-ttu-id="9bcf4-137">Például: Beállít egy számlálót a „Termelési órák” elemhez és hozzáadja a „Teherautómotor” eszköztípust.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-137">For example: You set up a counter for "Production hours" and add the asset type "Truck Engine".</span></span> <span data-ttu-id="9bcf4-138">Ha a számláló frissítése megtörtént, akkor a program a kapcsolódó „Olaj” számlálót is frissíti ugyanazzal az számlálóértékkel.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-138">When that counter is updated, a related counter "Oil" is also updated with the same counter values.</span></span> <span data-ttu-id="9bcf4-139">A **Számlálók** beállítása tartalmazza az „Órák” beállítást.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-139">The setup in **Counters** includes the setup on "Hours".</span></span> <span data-ttu-id="9bcf4-140">Ezenkívül az „Olaj" számláló esetében a „Teherautómotor” eszköztípust hozzá kell adni az **Eszköztípusok** gyorslaphoz, hogy biztosítva legyen a számláló kapcsolata.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-140">Also, on the "Oil" counter, the asset type "Truck Engine" should be added to the **Asset types** FastTab to ensure the counter relation.</span></span> <span data-ttu-id="9bcf4-141">Az alábbi képernyőképek láthatók az Óra és Olaj számlálók beállításával kapcsolatos példa.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-141">See the screenshots below for an example of the setup on the Hours and Oil counters.</span></span>

<span data-ttu-id="9bcf4-142">Ha eszköztípusokat ad egy számlálóhoz a **Számlálók**alatt, akkor a számláló automatikusan hozzá lesz adva az eszköztípusokhoz **Számlálók** gyorslapon az [Eszköztípusok](../setup-for-objects/object-types.md) alatt.</span><span class="sxs-lookup"><span data-stu-id="9bcf4-142">When asset types are added to a counter type in **Counters**, that counter is automatically added to the asset types on the **Counters** FastTab in [Asset types](../setup-for-objects/object-types.md).</span></span>

![1. ábra](media/071-setup-for-objects.png)

