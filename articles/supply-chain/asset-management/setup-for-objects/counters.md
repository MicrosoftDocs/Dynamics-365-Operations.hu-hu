---
title: Eszköz mértékei
description: A témakör bemutatja, hogyan lehet eszközmérték típusokat létrehozni az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9c445832a649c4f6a6642036ecab325e8aa2079
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783329"
---
# <a name="asset-measures"></a><span data-ttu-id="04509-103">Eszköz mértékei</span><span class="sxs-lookup"><span data-stu-id="04509-103">Asset measures</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="04509-104">A témakör bemutatja, hogyan lehet eszközmérték típusokat létrehozni az Eszközkezelés modulban.</span><span class="sxs-lookup"><span data-stu-id="04509-104">The topic explains how to create asset measure types in Asset Management.</span></span> <span data-ttu-id="04509-105">Az eszközmérték-típusokkal lehet mérni a méréseket lehet regisztrálni eszközökön, például a termelési órák száma vagy a tárgyi eszközön termelt mennyiség tekintetében.</span><span class="sxs-lookup"><span data-stu-id="04509-105">Asset measure types are used to make measurement registrations on assets, for example, regarding number of production hours, or quantity produced on the asset.</span></span> <span data-ttu-id="04509-106">Az eszköztípusok az eszközmérték-típusokhoz kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="04509-106">Asset types are related to the asset measure types.</span></span> <span data-ttu-id="04509-107">Ez azt jelenti, hogy egy eszköz esetében csak akkor használható egy eszközmérték, ha az eszköz típusánál be van állítva az eszközmérték.</span><span class="sxs-lookup"><span data-stu-id="04509-107">This means that an asset measure can only be used on an asset if the asset measure is set up on the asset type used on the asset.</span></span>

<span data-ttu-id="04509-108">Az eszközökre vonatkozó mértékregisztrációk előtt létre kell hoznia a **Számlálókban**használni kívánt eszközmérték-típusokat.</span><span class="sxs-lookup"><span data-stu-id="04509-108">Before you can make measurement registrations on assets, you first create the asset measure types you want to use in **Counters**.</span></span> <span data-ttu-id="04509-109">Ezután az eszközökre vonatkozó mértékregisztrációkat kell létrehoznia az **Eszközök mértékei**helyen.</span><span class="sxs-lookup"><span data-stu-id="04509-109">Next, you can create measurement registrations on assets in **Asset measures**.</span></span> 

<span data-ttu-id="04509-110">Az eszközmértékek a karbantartási tervekben használhatók.</span><span class="sxs-lookup"><span data-stu-id="04509-110">Asset measures can be used on maintenance plans.</span></span> <span data-ttu-id="04509-111">Egy karbantartási terv sora lehet „Számláló” típusú például, amely a termelési órák számához vagy a termelt mennyiséggel kapcsolatos.</span><span class="sxs-lookup"><span data-stu-id="04509-111">A maintenance plan line can be of type "Counter", for example, relating to number of production hours or quantity produced.</span></span> 

<span data-ttu-id="04509-112">Az eszközmértékek regisztrálása manuálisan vagy automatikusan történhet, a termelési órák vagy a termelt mennyiségek alapján.</span><span class="sxs-lookup"><span data-stu-id="04509-112">An asset measurement registration can be updated manually or automatically based on production hours or quantity produced.</span></span> <span data-ttu-id="04509-113">Egy eszközmértéket úgy is be lehet állítani, hogy a három frissítési mód egyikét használja (a **Frissítés** mezőben választható ki a **Számlálók** alatt):</span><span class="sxs-lookup"><span data-stu-id="04509-113">An asset measure can be set up to use one of three update methods (selected in the **Update** field in **Counters**):</span></span>
  
- <span data-ttu-id="04509-114">Manuális – manuálisan kell regisztrálni az eszközmérték-értékeket.</span><span class="sxs-lookup"><span data-stu-id="04509-114">Manual - you must manually register asset measurement values.</span></span>  
- <span data-ttu-id="04509-115">Termelési órák – a számláló automatikusan frissül a termelési órák száma alapján.</span><span class="sxs-lookup"><span data-stu-id="04509-115">Production hours - the counter is automatically updated based on number of production hours.</span></span>  
- <span data-ttu-id="04509-116">Termelt mennyiség– a számláló automatikusan frissül a termelt mennyiség alapján.</span><span class="sxs-lookup"><span data-stu-id="04509-116">Production quantity - the counter is automatically updated based on number of quantity produced.</span></span>  

>[!NOTE]
><span data-ttu-id="04509-117">Ha a termelt mennyiséget használja, az *összes* regisztrált cikk szerepel a mértékregisztrációban, a jó mennyiség is és a hibás mennyiség is.</span><span class="sxs-lookup"><span data-stu-id="04509-117">If quantity produced is used, *all* registered items are included in the measurement registration, good quantity as well as error quantity.</span></span> <span data-ttu-id="04509-118">Ha szükséges, manuálisan is be lehet állítani eszközmérték-regisztrációkat.</span><span class="sxs-lookup"><span data-stu-id="04509-118">It is always possible to make manual asset measurement registrations, if required.</span></span>

## <a name="create-counter-types-for-asset-counter-registrations"></a><span data-ttu-id="04509-119">Számlálótípusok létrehozása eszközszámláló regisztrációkhoz</span><span class="sxs-lookup"><span data-stu-id="04509-119">Create counter types for asset counter registrations</span></span>

1. <span data-ttu-id="04509-120">Válassza az **Eszközkezelés** > **Beállítás** > **Eszköztípusok** > **Számlálók**lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="04509-120">Select **Asset management** > **Setup** > **Asset types** > **Counters**.</span></span>
2. <span data-ttu-id="04509-121">Válassza az **Új** lehetőséget egy új eszközmérték-típus.</span><span class="sxs-lookup"><span data-stu-id="04509-121">Select **New** to create a new asset measure type.</span></span>
3. <span data-ttu-id="04509-122">Szúrjon be egy azonosítót a **Számláló** mezőbe, és a számláló nevét a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="04509-122">Insert an ID in the **Counter** field, and a counter name in the **Name** field.</span></span>
4. <span data-ttu-id="04509-123">Az **Általános** gyorslapon válassza ki a mértékegységet az **Egység** mezőben.</span><span class="sxs-lookup"><span data-stu-id="04509-123">On the **General** FastTab, select a measurement unit in the **Unit** field.</span></span>
5. <span data-ttu-id="04509-124">A **Frissítés** mezőben válassza ki az eszközhöz használandó frissítési módot.</span><span class="sxs-lookup"><span data-stu-id="04509-124">In the **Update** field, select the update method to be used for the asset measure.</span></span>
6. <span data-ttu-id="04509-125">Válassza az „igen” beállítást a **Számlálóértékek öröklése** választógombon ha a tárgyieszköz-szerkezethez tartozó tárgyi eszközöknek automatikusan örökölniük kell a fölérendelt eszközön végzett regisztrációkat.</span><span class="sxs-lookup"><span data-stu-id="04509-125">Select "Yes" on the **Inherit counter values** toggle button if child assets in an asset structure should automatically inherit asset measure registrations made on the parent asset.</span></span>
7. <span data-ttu-id="04509-126">A **Teljes összesítés** mezőben válassza ki a tárgyi eszközmértékhez ezen eszközmérték felhasználásával használandó összesítési módszert.</span><span class="sxs-lookup"><span data-stu-id="04509-126">In the **Total aggregate** field, select the summation method to be used for an asset measure using this asset measure type.</span></span> <span data-ttu-id="04509-127">Az „összeg” az alapbeállítás, amellyel a program folyamatosan hozzáadja a regisztrált értékeket a teljes értékhez.</span><span class="sxs-lookup"><span data-stu-id="04509-127">"Sum" is the standard selection used to continuously add registered values to the total value.</span></span> <span data-ttu-id="04509-128">Az „Átlag” akkor használható, ha egy eszköz esetében be van állítva egy eszköz küszöbértékének figyelése, például a hőmérséklet, rezgés vagy kopás az eszközön.</span><span class="sxs-lookup"><span data-stu-id="04509-128">"Average" can be used if an asset measure is set up to monitor a threshold, for example, regarding temperature, vibrations, or wear and tear on an asset.</span></span> 
8. <span data-ttu-id="04509-129">Az **Eltérés felfelé** mezőbe írja be a felső szintet százalékban annak ellenőrzéséhez, hogy a manuális eszközmérték-regisztrációk egy elvárt tartományon belül vannak-e.</span><span class="sxs-lookup"><span data-stu-id="04509-129">In the **Deviation over** field, insert the upper level in percent for validating if manual asset measure registrations are within an expected range.</span></span> <span data-ttu-id="04509-130">Az ellenőrzés alapja a meglévő eszközmérték-regisztrációk lineáris növekedése.</span><span class="sxs-lookup"><span data-stu-id="04509-130">The validation is based on a linear increase in existing asset measure registrations.</span></span>
9. <span data-ttu-id="04509-131">Az **Eltérés lefelé** mezőbe írja be az alsó szintet százalékban annak ellenőrzéséhez, hogy a manuális eszközmérték-regisztrációk egy elvárt tartományon belül vannak-e.</span><span class="sxs-lookup"><span data-stu-id="04509-131">In the **Deviation under** field, insert the lower level in percent for validating if manual asset measure registrations are within an expected range.</span></span> <span data-ttu-id="04509-132">Az ellenőrzés alapja a meglévő eszközmérték-regisztrációk lineáris csökkenése.</span><span class="sxs-lookup"><span data-stu-id="04509-132">The validation is based on a linear decrease in existing asset measure registrations.</span></span>
10. <span data-ttu-id="04509-133">A **Típus** mezőben válassza ki, hogy milyen típusú üzenetet (tájékoztatás, figyelmeztetés, hiba) kíván megjeleníteni, ha a megadott tartományon kívüli eltérések következnek be, amikor manuális eszközmérték-regisztrációkat hajt végre.</span><span class="sxs-lookup"><span data-stu-id="04509-133">In the **Type** field, select the type of message (information, warning, error) to be shown if deviations outside the defined range occur when you make manual asset measure registrations.</span></span>
11. <span data-ttu-id="04509-134">Az **Eszköztípusok** gyorslapon adja meg azokat az eszköztípusokat, amelyeket az eszközmérték használhat.</span><span class="sxs-lookup"><span data-stu-id="04509-134">On the **Asset types** FastTab, add the asset types that should be able to use the asset measure.</span></span>
12. <span data-ttu-id="04509-135">A **Kapcsolódó eszközmértékek** gyorslapon adja meg azokat az eszközmértékeket, amelyeket automatikusan frissíteni szeretne az ezsközmérték frissítésekor.</span><span class="sxs-lookup"><span data-stu-id="04509-135">On the **Related asset measures** FastTab, add the asset measures that you want to be automatically updated when this asset measure is updated.</span></span>


>[!NOTE]
><span data-ttu-id="04509-136">A kapcsolódó eszközmértéket csak akkor frissíti automatikusan a program, ha a kapcsolódó eszközmérték tárgyieszköz-típusa szerepel az eszközmérték beállításaiban.</span><span class="sxs-lookup"><span data-stu-id="04509-136">A related asset measure is automatically updated only if the related asset measure has the asset type, to which it is related, in the asset measure setup.</span></span> <span data-ttu-id="04509-137">Például: Beállít egy eszközmértéket a „Termelési órák” elemhez és hozzáadja a „Teherautómotor” eszköztípust.</span><span class="sxs-lookup"><span data-stu-id="04509-137">For example: You set up an asset measure for "Production hours" and add the asset type "Truck Engine".</span></span> <span data-ttu-id="04509-138">Ha a tárgyi az eszközmérték frissítése megtörtént, akkor a program a kapcsolódó „Olaj” számlálót is frissíti ugyanazzal az eszközmérték-értékkel.</span><span class="sxs-lookup"><span data-stu-id="04509-138">When that asset measure is updated, a related counter "Oil" is also updated with the same asset measure values.</span></span> <span data-ttu-id="04509-139">A **Számlálók** beállítása tartalmazza az „Órák” beállítást.</span><span class="sxs-lookup"><span data-stu-id="04509-139">The setup in **Counters** includes the setup on "Hours".</span></span> <span data-ttu-id="04509-140">Ezenkívül az „Olaj" eszközmérték esetében a „Teherautómotor” eszköztípust hozzá kell adni az **Eszköztípusok** gyorslaphoz, hogy biztosítva legyen az eszközmérték kapcsolata.</span><span class="sxs-lookup"><span data-stu-id="04509-140">Also, on the "Oil" asset measure, the asset type "Truck Engine" should be added to the **Asset types** FastTab to ensure the asset measure relation.</span></span> <span data-ttu-id="04509-141">Az alábbi képernyőképek láthatók az Óra és Olaj eszközmértékek beállításával kapcsolatos példa.</span><span class="sxs-lookup"><span data-stu-id="04509-141">See the screenshots below for an example of the setup on the Hours and Oil asset measures.</span></span>

<span data-ttu-id="04509-142">Ha eszköztípusokat ad egy eszközmértékhez a **Számlálók**alatt, akkor az eszközmérték automatikusan hozzá lesz adva az eszköztípusokhoz **Számlálók** gyorslapon az [Eszköztípusok](../setup-for-objects/object-types.md) alatt.</span><span class="sxs-lookup"><span data-stu-id="04509-142">When asset types are added to an asset measure type in **Counters**, that asset measure is automatically added to the asset types on the **Counters** FastTab in [Asset types](../setup-for-objects/object-types.md).</span></span>

![1. ábra](media/071-setup-for-objects.png)


