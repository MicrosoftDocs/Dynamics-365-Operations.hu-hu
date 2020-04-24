---
title: Hullámlépéskódok
description: Ez a témakör áttekintést nyújt a hullámlépéskódokról és használatukról.
author: josaw1
manager: tfehr
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7a5a62c184b229142673981777da026c3f4103dc
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204539"
---
# <a name="wave-step-codes"></a><span data-ttu-id="91d42-103">Hullámlépéskódok</span><span class="sxs-lookup"><span data-stu-id="91d42-103">Wave step codes</span></span>

[!include [banner](../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

<span data-ttu-id="91d42-104">A hullámlépcsőkódok olyan kódok, amelyeket a felhasználók úgy állíthatnak be és használhatnak, hogy azok a hullámmetódusok meghatározott példányait a megfelelő sablonhoz kapcsolja.</span><span class="sxs-lookup"><span data-stu-id="91d42-104">Wave step codes are codes that users can set up and use to link specific instances of wave methods to a corresponding template.</span></span> <span data-ttu-id="91d42-105">A sablonok tartalmazzák a feltöltéshez, a tárolóra bontáshoz, a címkék nyomtatásához, a rakomány építéséhez és a sorba rendezéshez szükséges sablonokat.</span><span class="sxs-lookup"><span data-stu-id="91d42-105">The templates include templates for replenishment, containerization, label printing, load building, and sorting.</span></span>

<span data-ttu-id="91d42-106">Ha nem használja a hullámlépéskódokat, a felhasználóknak szabad szöveget kell beírniuk ahhoz, hogy a meghatározott sablonra hivatkozzanak a hullámmetódus-példányból.</span><span class="sxs-lookup"><span data-stu-id="91d42-106">When wave step codes aren't used, users must enter free text to reference a specific template from the wave method instance.</span></span> <span data-ttu-id="91d42-107">A szabad szövegben előfordulhatnak hibák, mivel a felhasználóknak ellenőrizniük kell, hogy a hullámlépés szövege, amelyet egy meghatározott hullámlépés-metódushoz a hullámsablonban hozzá akarnak adni, megegyezik a hullámlépés szövegével a célsablonban.</span><span class="sxs-lookup"><span data-stu-id="91d42-107">Free text is prone to errors because users must make sure that the wave step text that they add for a specific wave step method in a wave template exactly matches the wave step text in the target template.</span></span>

<span data-ttu-id="91d42-108">Az adott hullámlépéstípus hullámlépéskódjait külön oldalon állítják be.</span><span class="sxs-lookup"><span data-stu-id="91d42-108">Wave step codes for a specific wave step type are set up on a separate page.</span></span> <span data-ttu-id="91d42-109">Egy hullámsablon minden egyes hullámlépésmetódus-példányához, amelyhez hullámlépéskód szükséges, egy legördülő listából kell kiválasztani a hullámlépéskódot.</span><span class="sxs-lookup"><span data-stu-id="91d42-109">For every wave step method instance in a wave template that requires a wave step code, the wave step code must be selected in a drop-down list.</span></span> <span data-ttu-id="91d42-110">A legördülő listában szereplő választék helyettesíti a szabadszöveges bevitelt, így csökkenti az emberi hiba kockázatát és hatását.</span><span class="sxs-lookup"><span data-stu-id="91d42-110">Selection in a drop-down list replaces free text entry and helps reduce the risk and impact of human error.</span></span> <span data-ttu-id="91d42-111">A beállítási kódok a hullámsablon hullámlépés-metódusának és a metódushoz tartozó célsablon összekapcsolására használatos.</span><span class="sxs-lookup"><span data-stu-id="91d42-111">Setup codes are used to link a wave step method in a wave template to a target template for the method.</span></span>

> [!NOTE]
> <span data-ttu-id="91d42-112">A hullámlépéskódok funkció használata nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="91d42-112">Use of the wave step codes feature is optional.</span></span> <span data-ttu-id="91d42-113">A teljes szervezetben, minden jogalanynál engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="91d42-113">It is enabled organization-wide for all legal entities.</span></span>

## <a name="setup-demo"></a><span data-ttu-id="91d42-114">Demo beállítása</span><span class="sxs-lookup"><span data-stu-id="91d42-114">Setup demo</span></span> 

<span data-ttu-id="91d42-115">Ennél a bemutatónál a bemutatóadatokat kell telepíteni, és az **USMF** demó adatvállalatot kell használnia.</span><span class="sxs-lookup"><span data-stu-id="91d42-115">For this demo, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="enable-wave-step-codes"></a><span data-ttu-id="91d42-116">Hullámlépéskódok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="91d42-116">Enable wave step codes</span></span>

<span data-ttu-id="91d42-117">Hajtsa végre az alábbi lépéseket a hullámlépéskód-funkció bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="91d42-117">Follow these steps to turn on the wave step codes feature.</span></span>

1. <span data-ttu-id="91d42-118">Lépjen a **Funkciókezelés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="91d42-118">Go to **Feature Management**.</span></span>
2. <span data-ttu-id="91d42-119">Jelölje be a **Szervezet egészére kiterjedő hullámlépéskód** nevű szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="91d42-119">Select to enable the feature called **Organization-wide Wave Step Code**.</span></span>

<span data-ttu-id="91d42-120">A program az új struktúrára frissíti az összes meglévő hullámlépés szabadszöveges bejegyzését minden jogi személyben.</span><span class="sxs-lookup"><span data-stu-id="91d42-120">All existing wave step free texts in all legal entities are upgraded to the new structure.</span></span> <span data-ttu-id="91d42-121">Miután a frissítés befejeződött minden jogi személynél, a szolgáltatás engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="91d42-121">After this upgrade is completed for all legal entities, then the feature is enabled.</span></span> <span data-ttu-id="91d42-122">Ha a szolgáltatást nem lehet engedélyezni egy vagy több jogi személynél, akkor a szolgáltatás nincs engedélyezve semelyik jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="91d42-122">If the feature cannot be enabled for one or more legal entities, then the feature is not enabled for any legal entities.</span></span>

<span data-ttu-id="91d42-123">Az engedélyezés során az érvényesítés az adatfrissítés során történik meg.</span><span class="sxs-lookup"><span data-stu-id="91d42-123">During the enablement, validations are done during the data upgrade.</span></span> <span data-ttu-id="91d42-124">Ha a frissítés nem sikerül, hibaüzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="91d42-124">If the upgrade fails, you receive an error message.</span></span> <span data-ttu-id="91d42-125">Előfordulhat, hogy a frissítés a következő ütközések miatt nem sikerül:</span><span class="sxs-lookup"><span data-stu-id="91d42-125">An upgrade might fail because of the following conflicts:</span></span>

- <span data-ttu-id="91d42-126">Ismétlődő hullámlépéshez tartozó szabad szövegek léteznek.</span><span class="sxs-lookup"><span data-stu-id="91d42-126">Duplicate wave step free texts exist.</span></span>
- <span data-ttu-id="91d42-127">Testreszabások találhatók.</span><span class="sxs-lookup"><span data-stu-id="91d42-127">Customizations exist.</span></span>
- <span data-ttu-id="91d42-128">A hullámlépés szabadszövege, amely egy adott hullámlépésmetódus-példányhoz van társítva, nem egyezik meg az elvárt sablontípussal.</span><span class="sxs-lookup"><span data-stu-id="91d42-128">A wave step free text that is associated with a wave step method instance doesn't match the expected template type.</span></span>

<span data-ttu-id="91d42-129">Miután feloldotta az ellenőrzések során azonosított ütközéseket, próbálja újra engedélyezni a funkciót.</span><span class="sxs-lookup"><span data-stu-id="91d42-129">After you've resolved any conflicts that are identified during the validations, you can retry to enable the feature.</span></span>

<span data-ttu-id="91d42-130">Amikor a funkció engedélyezve van, elérhetővé válik a **Hullámlépéskódok** oldal (**Raktárkezelés \> Beállítás \> Hullámok \> Hullámlépéskódok**).</span><span class="sxs-lookup"><span data-stu-id="91d42-130">When the feature has been enabled, the **Wave step codes** page (**Warehouse management \> Setup \> Waves \> Wave step codes**) becomes available.</span></span> <span data-ttu-id="91d42-131">Ez a lap felsorolja azokat a hullámlépéskódokat, amelyek a Szervezet egészére kiterjedő hullámlépéskód funkció bekapcsolásakor engedélyezve lettek.</span><span class="sxs-lookup"><span data-stu-id="91d42-131">This page lists the wave step codes that were upgraded when the Organization-wide Wave Step Code feature was enabled.</span></span>

### <a name="create-new-wave-step-codes"></a><span data-ttu-id="91d42-132">Új hullámlépéskódok létrehozása</span><span class="sxs-lookup"><span data-stu-id="91d42-132">Create new wave step codes</span></span>

<span data-ttu-id="91d42-133">A **Hullámlépéskódok** lapon hozhat létre és törölhet hullámlépéskódokat.</span><span class="sxs-lookup"><span data-stu-id="91d42-133">You can use the **Wave step codes** page to create and delete wave step codes.</span></span>

<span data-ttu-id="91d42-134">Minden új hullámlépéskódnak és a hozzárendelt azonosítónak egyedinek kell lennie az összes hullámlépéstípus tekintetében, és egy meghatározott hullámlépéstípushoz kell megadni.</span><span class="sxs-lookup"><span data-stu-id="91d42-134">Every new wave step code and its associated ID must be unique across all wave step types, and they must be defined for a specific wave step type.</span></span>

### <a name="apply-wave-step-codes"></a><span data-ttu-id="91d42-135">Hullámlépéskódok alkalmazása</span><span class="sxs-lookup"><span data-stu-id="91d42-135">Apply wave step codes</span></span>

<span data-ttu-id="91d42-136">Miután definiálta a megfelelő hullámlépéskódokat, alkalmazhatók a hullámfeldolgozási módszerekre.</span><span class="sxs-lookup"><span data-stu-id="91d42-136">After you've defined the appropriate wave step codes, they can be applied to the wave process methods.</span></span>

<span data-ttu-id="91d42-137">A hullámlépéskódok alkalmazása érdekében lépjen a megfelelő célsablonra.</span><span class="sxs-lookup"><span data-stu-id="91d42-137">To apply wave step codes, go to the appropriate target template.</span></span> <span data-ttu-id="91d42-138">Itt találhatók a célsablonok, amelyre a tervezés alapján a hullámlépéskódokat irányítják:</span><span class="sxs-lookup"><span data-stu-id="91d42-138">Here are the target templates that the wave step codes are designated to point to:</span></span>

- <span data-ttu-id="91d42-139">**Feltöltési sablonok:** Raktárkezelés \> Beállítás \> Feltöltés \> Feltöltési sablonok</span><span class="sxs-lookup"><span data-stu-id="91d42-139">**Replenishment templates:** Warehouse management \> Setup \> Replenishment \> Replenishment templates</span></span>
- <span data-ttu-id="91d42-140">**Rakományépítési sablonok:** Raktárkezelés \> Beállítás \> Rakomány \> Rakományépítési sablonok</span><span class="sxs-lookup"><span data-stu-id="91d42-140">**Load build templates:** Warehouse management \> Setup \> Load \> Load build templates</span></span>
- <span data-ttu-id="91d42-141">**Rendezési sablonok:** Raktárkezelés \> Beállítás \> Csomagolás \> Kimenő rendezési sablonok</span><span class="sxs-lookup"><span data-stu-id="91d42-141">**Sort templates:** Warehouse management \> Setup \> Packing \> Outbound sorting templates</span></span>
- <span data-ttu-id="91d42-142">**Tárolóra bontási sablonok:** Raktárkezelés \> Beállítás \> Tárolók \> Tárolóépítési sablonok</span><span class="sxs-lookup"><span data-stu-id="91d42-142">**Containerization templates:** Warehouse management \> Setup \> Containers \> Container build templates</span></span>
- <span data-ttu-id="91d42-143">**Címkenyomtatási sablonok:** Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímkesablonok</span><span class="sxs-lookup"><span data-stu-id="91d42-143">**Label printing templates:** Warehouse management \> Setup \> Document routing \> Wave label templates</span></span>

<span data-ttu-id="91d42-144">A listában szereplő sablonokat akkor alkalmazza a program, ha a hullámsablonban kiválasztott hullámfeldolgozási metódusból hivatkoznak rájuk.</span><span class="sxs-lookup"><span data-stu-id="91d42-144">The templates in this list are applied when they are referenced from a wave process method that is selected in a wave template.</span></span> <span data-ttu-id="91d42-145">Ha a hullámsablon hullámfeldolgozási metódusán szereplő hullámlépéskód megegyezik az egyik sablontípuson található hullámlépéskóddal, akkor a rendszer alkalmazza a sablont.</span><span class="sxs-lookup"><span data-stu-id="91d42-145">When the wave step code on a wave process method in a wave template matches the wave step code in one of the templates types, the template is applied.</span></span>

### <a name="sample-scenario"></a><span data-ttu-id="91d42-146">Mintaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="91d42-146">Sample scenario</span></span>

<span data-ttu-id="91d42-147">A következő eljárás segít annak biztosításában, hogy a létrehozott feltöltési sablont a rendszer alkalmazza a hullámsablonra.</span><span class="sxs-lookup"><span data-stu-id="91d42-147">The following procedure helps guarantee that the replenishment template that you created will be applied for the wave template.</span></span>

1. <span data-ttu-id="91d42-148">Lépjen a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámlépéskódok** pontra, és hozzon létre egy hullámlépéskódot a **Feltöltés** típushoz.</span><span class="sxs-lookup"><span data-stu-id="91d42-148">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**, and create a wave step code for the **Replenishment** type.</span></span>
2. <span data-ttu-id="91d42-149">Lépjen a **Raktárkezelés \> Beállítás \> Feltöltés \> Feltöltési sablonok** pontra, és hozzon létre egy feltöltési sablont.</span><span class="sxs-lookup"><span data-stu-id="91d42-149">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**, and create a replenishment template.</span></span>
3. <span data-ttu-id="91d42-150">A feltöltési sablonban válassza ki a **Feltöltés** típushoz létrehozott hullámlépés kódját.</span><span class="sxs-lookup"><span data-stu-id="91d42-150">In the replenishment template, select the wave step code that you created for the **Replenishment** type.</span></span>
4. <span data-ttu-id="91d42-151">Lépjen a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra, és hozza létre a használni kívánt hullámsablont.</span><span class="sxs-lookup"><span data-stu-id="91d42-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**, and select the wave template that you intend to use.</span></span>
5. <span data-ttu-id="91d42-152">A sablon **Metódusok** gyorslapján válassza a **Feltöltés** metódust.</span><span class="sxs-lookup"><span data-stu-id="91d42-152">In the template, on the **Methods** FastTab, select the **Replenishment** method.</span></span>
6. <span data-ttu-id="91d42-153">A **Hullámlépéskód** mezőben válassza ki a feltöltési sablonban kiválasztott hullámlépéskódot.</span><span class="sxs-lookup"><span data-stu-id="91d42-153">In the **Wave step code** field, select the wave step code that you selected in the replenishment template.</span></span>

<span data-ttu-id="91d42-154">Ezeket a lépéseket minden egyes jogi személynél végre kell hajtani.</span><span class="sxs-lookup"><span data-stu-id="91d42-154">You perform these steps for each legal entity.</span></span>
