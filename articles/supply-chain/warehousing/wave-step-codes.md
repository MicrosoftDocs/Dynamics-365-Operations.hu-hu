---
title: Hullámlépéskódok
description: Ez a témakör áttekintést nyújt a hullámlépéskódokról és használatukról.
author: josaw1
manager: AnnBe
ms.date: 09/06/2019
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
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0f89c6098db9e2e3a9aa4ee3666e4b9ae608f054
ms.sourcegitcommit: d8f1135cdbc2deca70bc4b2805a0519253c9a31f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/06/2019
ms.locfileid: "1992357"
---
# <a name="wave-step-codes"></a><span data-ttu-id="71312-103">Hullámlépéskódok</span><span class="sxs-lookup"><span data-stu-id="71312-103">Wave step codes</span></span>

[!include [banner](../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

## <a name="about-wave-step-codes"></a><span data-ttu-id="71312-104">A hullámlépéskódokról</span><span class="sxs-lookup"><span data-stu-id="71312-104">About wave step codes</span></span>

<span data-ttu-id="71312-105">A hullámlépcsőkódok olyan kódok, amelyeket a felhasználók úgy állíthatnak be és használhatnak, hogy azok a hullámmetódusok meghatározott példányait a megfelelő sablonhoz kapcsolja.</span><span class="sxs-lookup"><span data-stu-id="71312-105">Wave step codes are codes that users can set up and use to link specific instances of wave methods to a corresponding template.</span></span> <span data-ttu-id="71312-106">A sablonok tartalmazzák a feltöltéshez, a tárolóra bontáshoz, a címkék nyomtatásához, a rakomány építéséhez és a sorba rendezéshez szükséges sablonokat.</span><span class="sxs-lookup"><span data-stu-id="71312-106">The templates include templates for replenishment, containerization, label printing, load building, and sorting.</span></span>

<span data-ttu-id="71312-107">Ha nem használja a hullámlépéskódokat, a felhasználóknak szabad szöveget kell beírniuk ahhoz, hogy a meghatározott sablonra hivatkozzanak a hullámmetódus-példányból.</span><span class="sxs-lookup"><span data-stu-id="71312-107">When wave step codes aren't used, users must enter free text to reference a specific template from the wave method instance.</span></span> <span data-ttu-id="71312-108">A szabad szövegben előfordulhatnak hibák, mivel a felhasználóknak ellenőrizniük kell, hogy a hullámlépés szövege, amelyet egy meghatározott hullámlépés-metódushoz a hullámsablonban hozzá akarnak adni, megegyezik a hullámlépés szövegével a célsablonban.</span><span class="sxs-lookup"><span data-stu-id="71312-108">Free text is prone to error, because users must make sure that the wave step text that they add for a specific wave step method in a wave template exactly matches the wave step text in the target template.</span></span>

<span data-ttu-id="71312-109">Az adott hullámlépéstípus hullámlépéskódjait külön oldalon állítják be.</span><span class="sxs-lookup"><span data-stu-id="71312-109">Wave step codes for a specific wave step type are set up on a separate page.</span></span> <span data-ttu-id="71312-110">Egy hullámsablon minden egyes hullámlépésmetódus-példányához, amelyhez hullámlépéskód szükséges, egy legördülő listából kell kiválasztani a hullámlépéskódot.</span><span class="sxs-lookup"><span data-stu-id="71312-110">For every wave step method instance in a wave template that requires a wave step code, the wave step code must be selected in a drop-down list.</span></span> <span data-ttu-id="71312-111">A legördülő listában szereplő választék helyettesíti a szabadszöveges bevitelt, így csökkenti az emberi hiba kockázatát és hatását.</span><span class="sxs-lookup"><span data-stu-id="71312-111">Selection in a drop-down list replaces free text entry and helps reduce the risk and impact of human error.</span></span> <span data-ttu-id="71312-112">A beállítási kódok a hullámsablon hullámlépés-metódusának és a metódushoz tartozó célsablon összekapcsolására használatos.</span><span class="sxs-lookup"><span data-stu-id="71312-112">Setup codes are used to link a wave step method in a wave template to a target template for the method.</span></span>

> [!NOTE]
> <span data-ttu-id="71312-113">A hullámlépéskód-funkció használata nem kötelező, és az alkalmazás jogi személyenként történik.</span><span class="sxs-lookup"><span data-stu-id="71312-113">Use of the wave step codes feature is optional, and uptake is per legal entity.</span></span> <span data-ttu-id="71312-114">Ezért ha egy adott jogi személy használja a funkciót, akkor a jogi személy összes meglévő hullámlépéskódja frissül az új struktúrára.</span><span class="sxs-lookup"><span data-stu-id="71312-114">Therefore, if a specific legal entity uses the feature, all existing wave step codes in that legal entity are upgraded to the new structure.</span></span>

## <a name="setup-demo"></a><span data-ttu-id="71312-115">Demo beállítása</span><span class="sxs-lookup"><span data-stu-id="71312-115">Setup demo</span></span> 

<span data-ttu-id="71312-116">Ennél a bemutatónál a bemutatóadatokat kell telepíteni, és az **USMF** demó adatvállalatot kell használnia.</span><span class="sxs-lookup"><span data-stu-id="71312-116">For this demo, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="enable-wave-step-codes"></a><span data-ttu-id="71312-117">Hullámlépéskódok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="71312-117">Enable wave step codes</span></span>

<span data-ttu-id="71312-118">Hajtsa végre az alábbi lépéseket a hullámlépéskód-funkció bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="71312-118">Follow these steps to turn on the wave step codes feature.</span></span>

1. <span data-ttu-id="71312-119">Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.</span><span class="sxs-lookup"><span data-stu-id="71312-119">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
2. <span data-ttu-id="71312-120">Az **Általános** lapon, a **Hullám feldolgozása** gyorslapon állítsa a **Hullámlépéskódok engedélyezése** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="71312-120">On the **General** tab, on the **Wave processing** FastTab, set the **Enable wave step codes** option to **Yes**.</span></span>

<span data-ttu-id="71312-121">A program az új struktúrára frissíti az összes meglévő hullámlépés szabadszöveges bejegyzését.</span><span class="sxs-lookup"><span data-stu-id="71312-121">All existing wave step free texts are upgraded to the new structure.</span></span> <span data-ttu-id="71312-122">Miután a frissítés befejeződött egy jogi személyhez, a **Hullámlépéskódok engedélyezése** funkció már nem elérhető a **Raktárkezelési paraméterek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="71312-122">After this upgrade is completed for a legal entity, the **Enable wave step codes** option is no longer available on the **Warehouse management parameters** page.</span></span>

<span data-ttu-id="71312-123">A frissítés során ellenőrzés történik, és ha a frissítés sikertelen, egy hibaüzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="71312-123">Validations are done during the upgrade, and if the upgrade fails, you receive an error message.</span></span> <span data-ttu-id="71312-124">Előfordulhat, hogy a frissítés a következő ütközések miatt nem sikerül:</span><span class="sxs-lookup"><span data-stu-id="71312-124">An upgrade might fail because of the following conflicts:</span></span>

- <span data-ttu-id="71312-125">Ismétlődő hullámlépéshez tartozó szabad szövegek léteznek.</span><span class="sxs-lookup"><span data-stu-id="71312-125">Duplicate wave step free texts exist.</span></span>
- <span data-ttu-id="71312-126">Testreszabások találhatók.</span><span class="sxs-lookup"><span data-stu-id="71312-126">Customizations exist.</span></span>
- <span data-ttu-id="71312-127">A hullámlépés szabadszövege, amely egy adott hullámlépésmetódus-példányhoz van társítva, nem egyezik meg az elvárt sablontípussal.</span><span class="sxs-lookup"><span data-stu-id="71312-127">A wave step free text that is associated with a wave step method instance doesn't match the expected template type.</span></span>

<span data-ttu-id="71312-128">Miután feloldotta az ellenőrzések során azonosított ütközéseket, újrafuttathatja a frissítési folyamatot.</span><span class="sxs-lookup"><span data-stu-id="71312-128">After you've resolved any conflicts that are identified during the validations, you can rerun the upgrade process.</span></span>

<span data-ttu-id="71312-129">Amikor a frissítés sikerül, elérhetővé válik a **Hullámlépéskódok** oldal (**Raktárkezelés \> Beállítás \> Hullámok \> Hullámlépéskódok**).</span><span class="sxs-lookup"><span data-stu-id="71312-129">When the upgrade succeeds, the **Wave step codes** page (**Warehouse management \> Setup \> Waves \> Wave step codes**) becomes available.</span></span> <span data-ttu-id="71312-130">Ez a lap felsorolja azokat a hullámlépés kódokat, amelyek a hullámlépéskódok funkció bekapcsolásakor frissültek.</span><span class="sxs-lookup"><span data-stu-id="71312-130">This page lists the wave step codes that were upgraded when the wave step codes feature was turned on.</span></span>

### <a name="create-new-wave-step-codes"></a><span data-ttu-id="71312-131">Új hullámlépéskódok létrehozása</span><span class="sxs-lookup"><span data-stu-id="71312-131">Create new wave step codes</span></span>

<span data-ttu-id="71312-132">A **Hullámlépéskódok** lapon hozhat létre és törölhet hullámlépéskódokat.</span><span class="sxs-lookup"><span data-stu-id="71312-132">You can use the **Wave step codes** page to create and delete wave step codes.</span></span>

<span data-ttu-id="71312-133">Minden új hullámlépéskódnak és a hozzárendelt azonosítónak egyedinek kell lennie az összes hullámlépéstípus tekintetében, és egy meghatározott hullámlépéstípushoz kell megadni.</span><span class="sxs-lookup"><span data-stu-id="71312-133">Every new wave step code and its associated ID must be unique across all wave step types, and they must be defined for a specific wave step type.</span></span>

### <a name="apply-wave-step-codes"></a><span data-ttu-id="71312-134">Hullámlépéskódok alkalmazása</span><span class="sxs-lookup"><span data-stu-id="71312-134">Apply wave step codes</span></span>

<span data-ttu-id="71312-135">Miután definiálta a megfelelő hullámlépéskódokat, alkalmazhatók a hullámfeldolgozási módszerekre.</span><span class="sxs-lookup"><span data-stu-id="71312-135">After you've defined the appropriate wave step codes, they can be applied to the wave process methods.</span></span>

<span data-ttu-id="71312-136">A hullámlépéskódok alkalmazása érdekében lépjen a megfelelő célsablonra.</span><span class="sxs-lookup"><span data-stu-id="71312-136">To apply wave step codes, go to the appropriate target template.</span></span> <span data-ttu-id="71312-137">Itt találhatók a célsablonok, amelyre a tervezés alapján a hullámlépéskódokat irányítják:</span><span class="sxs-lookup"><span data-stu-id="71312-137">Here are the target templates that the wave step codes are designated to point to:</span></span>

- <span data-ttu-id="71312-138">**Feltöltési sablonok:** Raktárkezelés \> Beállítás \> Feltöltés \> Feltöltési sablonok</span><span class="sxs-lookup"><span data-stu-id="71312-138">**Replenishment templates:** Warehouse management \> Setup \> Replenishment \> Replenishment templates</span></span>
- <span data-ttu-id="71312-139">**Rakományépítési sablonok:** Raktárkezelés \> Beállítás \> Rakomány \> Rakományépítési sablonok</span><span class="sxs-lookup"><span data-stu-id="71312-139">**Load build templates:** Warehouse management \> Setup \> Load \> Load build templates</span></span>
- <span data-ttu-id="71312-140">**Rendezési sablonok:** Raktárkezelés \> Beállítás \> Csomagolás \> Kimenő rendezési sablonok</span><span class="sxs-lookup"><span data-stu-id="71312-140">**Sort templates:** Warehouse management \> Setup \> Packing \> Outbound sorting templates</span></span>
- <span data-ttu-id="71312-141">**Tárolóra bontási sablonok:** Raktárkezelés \> Beállítás \> Tárolók \> Tárolóépítési sablonok</span><span class="sxs-lookup"><span data-stu-id="71312-141">**Containerization templates:** Warehouse management \> Setup \> Containers \> Container build templates</span></span>
- <span data-ttu-id="71312-142">**Címkenyomtatási sablonok:** Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímkesablonok</span><span class="sxs-lookup"><span data-stu-id="71312-142">**Label printing templates:** Warehouse management \> Setup \> Document routing \> Wave label templates</span></span>

<span data-ttu-id="71312-143">A listában szereplő sablonokat akkor alkalmazza a program, ha a hullámsablonban kiválasztott hullámfeldolgozási metódusból hivatkoznak rájuk.</span><span class="sxs-lookup"><span data-stu-id="71312-143">The templates in this list are applied when they are referenced from a wave process method that is selected in a wave template.</span></span> <span data-ttu-id="71312-144">Ha a hullámsablon hullámfeldolgozási metódusán szereplő hullámlépéskód megegyezik az egyik sablontípuson található hullámlépéskóddal, akkor a rendszer alkalmazza a sablont.</span><span class="sxs-lookup"><span data-stu-id="71312-144">When the wave step code on a wave process method in a wave template matches the wave step code in one of the templates types, the template is applied.</span></span>

### <a name="sample-scenario"></a><span data-ttu-id="71312-145">Mintaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="71312-145">Sample scenario</span></span>

<span data-ttu-id="71312-146">A következő eljárás segít annak biztosításában, hogy a létrehozott feltöltési sablont a rendszer alkalmazza a hullámsablonra.</span><span class="sxs-lookup"><span data-stu-id="71312-146">The following procedure helps guarantee that the replenishment template that you created will be applied for the wave template.</span></span>

1. <span data-ttu-id="71312-147">Lépjen a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámlépéskódok** pontra, és hozzon létre egy hullámlépéskódot a **Feltöltés** típushoz.</span><span class="sxs-lookup"><span data-stu-id="71312-147">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**, and create a wave step code for the **Replenishment** type.</span></span>
2. <span data-ttu-id="71312-148">Lépjen a **Raktárkezelés \> Beállítás \> Feltöltés \> Feltöltési sablonok** pontra, és hozzon létre egy feltöltési sablont.</span><span class="sxs-lookup"><span data-stu-id="71312-148">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**, and create a replenishment template.</span></span>
3. <span data-ttu-id="71312-149">A feltöltési sablonban válassza ki a **Feltöltés** típushoz létrehozott hullámlépés kódját.</span><span class="sxs-lookup"><span data-stu-id="71312-149">In the replenishment template, select the wave step code that you created for the **Replenishment** type.</span></span>
4. <span data-ttu-id="71312-150">Lépjen a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra, és hozza létre a használni kívánt hullámsablont.</span><span class="sxs-lookup"><span data-stu-id="71312-150">Go to **Warehouse management \> Setup \> Waves \> Wave templates**, and select the wave template that you intend to use.</span></span>
5. <span data-ttu-id="71312-151">A sablon **Metódusok** gyorslapján válassza a **Feltöltés** metódust.</span><span class="sxs-lookup"><span data-stu-id="71312-151">In the template, on the **Methods** FastTab, select the **Replenishment** method.</span></span>
6. <span data-ttu-id="71312-152">A **Hullámlépéskód** mezőben válassza ki a feltöltési sablonban kiválasztott hullámlépéskódot.</span><span class="sxs-lookup"><span data-stu-id="71312-152">In the **Wave step code** field, select the wave step code that you selected in the replenishment template.</span></span>
