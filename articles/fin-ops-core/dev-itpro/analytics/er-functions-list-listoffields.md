---
title: LISTOFFIELDS ER-függvény
description: A témakör tájékoztatást nyújt a LISTOFFIELDS Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d51b59c437bd216c6d229546136bb604239fa92
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041998"
---
# <span data-ttu-id="5b2dd-103"><a name="LISTOFFIELDS">LISTOFFIELDS ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="5b2dd-103"><a name="LISTOFFIELDS">LISTOFFIELDS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b2dd-104">A `LISTOFFIELDS` függvény egy *Rekordlista*-értéket ad vissza, amely a *Felsorolás* vagy a *Tároló (rekord)* típus megadott argumentumának szerkezete alapján jön létre.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-104">The `LISTOFFIELDS` function returns a *Record list* value that is created based on the structure of the specified argument of the *Enumeration* or *Container (record)* type.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="5b2dd-105">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="5b2dd-105">Syntax 1</span></span>

```vb
LISTOFFIELDS (path)
```

## <a name="syntax-2"></a><span data-ttu-id="5b2dd-106">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="5b2dd-106">Syntax 2</span></span>

```vb
LISTOFFIELDS (path, language)
```

## <a name="arguments"></a><span data-ttu-id="5b2dd-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="5b2dd-107">Arguments</span></span>

<span data-ttu-id="5b2dd-108">`path`: Adatforrás hivatkozása</span><span class="sxs-lookup"><span data-stu-id="5b2dd-108">`path`: Data source reference</span></span>

<span data-ttu-id="5b2dd-109">A következő adattípusok egyikéhez tartozó adatforrás érvényes hivatkozási útvonala:</span><span class="sxs-lookup"><span data-stu-id="5b2dd-109">The valid reference path of a data source of one of the following data types:</span></span>

- <span data-ttu-id="5b2dd-110">Modellfelsorolás</span><span class="sxs-lookup"><span data-stu-id="5b2dd-110">Model enumeration</span></span>
- <span data-ttu-id="5b2dd-111">Formátumok felsorolása</span><span class="sxs-lookup"><span data-stu-id="5b2dd-111">Format enumeration</span></span>
- <span data-ttu-id="5b2dd-112">Alkalmazásfelsorolás</span><span class="sxs-lookup"><span data-stu-id="5b2dd-112">Application enumeration</span></span>
- <span data-ttu-id="5b2dd-113">Tároló (rekord)</span><span class="sxs-lookup"><span data-stu-id="5b2dd-113">Container (record)</span></span>

<span data-ttu-id="5b2dd-114">`language`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="5b2dd-114">`language`: *String*</span></span>

<span data-ttu-id="5b2dd-115">Nyelvkódot jelölő szöveg.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-115">Text that represents a language code.</span></span>

## <a name="return-values"></a><span data-ttu-id="5b2dd-116">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="5b2dd-116">Return values</span></span>

<span data-ttu-id="5b2dd-117">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="5b2dd-117">*Record list*</span></span>

<span data-ttu-id="5b2dd-118">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5b2dd-119">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="5b2dd-119">Usage notes</span></span>

<span data-ttu-id="5b2dd-120">A létrehozott lista olyan rekordokból áll, amelyek a következő mezőket tartalmazzák:</span><span class="sxs-lookup"><span data-stu-id="5b2dd-120">The list that is created consists of records that have the following fields:</span></span>

- <span data-ttu-id="5b2dd-121">**Név** (*Karakterlánc* adattípus)</span><span class="sxs-lookup"><span data-stu-id="5b2dd-121">**Name** (*String* data type)</span></span>
- <span data-ttu-id="5b2dd-122">**Címke** (*Karakterlánc* adattípus)</span><span class="sxs-lookup"><span data-stu-id="5b2dd-122">**Label** (*String* data type)</span></span>
- <span data-ttu-id="5b2dd-123">**Leírás** (*Karakterlánc* adattípus)</span><span class="sxs-lookup"><span data-stu-id="5b2dd-123">**Description** (*String* data type)</span></span>
- <span data-ttu-id="5b2dd-124">**IsTranslated** (*Logikai* adattípus)</span><span class="sxs-lookup"><span data-stu-id="5b2dd-124">**IsTranslated** (*Boolean* data type)</span></span>

<span data-ttu-id="5b2dd-125">Ha a `path` argumentum egy *Tároló (rekord)* típusú adatforrásra hivatkozik, akkor a hivatkozott tárolórekord minden mezőjéhez új bejegyzés kerül hozzáadásra a létrehozott listára.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-125">If the `path` argument refers to a data source of the *Container (Record)* type, for every field of the referenced container record, a new record is added to the list that is created.</span></span> <span data-ttu-id="5b2dd-126">Minden létrehozott rekord esetén a **Név** mező annak a hivatkozott tárolórekordnak a nevét adja vissza, amelyhez az aktuális rekord készült.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-126">For every record that is created, the **Name** field returns the name of the field of the referenced container record that the current record was created for.</span></span>

<span data-ttu-id="5b2dd-127">Ha a `path` argumentum a *Felsorolás* típusú adatforrások egyikére hivatkozik, akkor a hivatkozott felsorolás minden felsorolási értékéhez új bejegyzés kerül hozzáadásra a létrehozott listára.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-127">If the `path` argument refers to a data source of one of the *Enumeration* types, for every enumeration value of the referenced enumeration, a new record is added to the list that is created.</span></span> <span data-ttu-id="5b2dd-128">A **Név** mező minden létrehozott rekord esetében visszaadja a hivatkozott felsorolást, amelyhez az aktuális rekord létrehozásra került. A **Leírás** mező a felsorolás leírását, a **Címke** mező pedig a felsorolás címkéjét adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-128">For every record that is created, the **Name** field returns the value of the referenced enumeration that the current record was created for, the **Description** field returns the description of that enumeration, and the **Label** field returns the label of that enumeration.</span></span>

<span data-ttu-id="5b2dd-129">Futásidőben, ha az 1-es szintaxist használja, a **Címke** és a **Leírás** mezőknek a futó Elektronikus jelentési (ER) formátum nyelvi beállításain alapuló visszaadott értéket kell eredményül adniuk:</span><span class="sxs-lookup"><span data-stu-id="5b2dd-129">At runtime, when syntax 1 is used, the **Label** and **Description** fields must return values that are based on the language settings of the Electronic reporting (ER) format that is running:</span></span>

- <span data-ttu-id="5b2dd-130">Ha a kért nyelv címkéi és leírása rendelkezésre állnak, a **Címke** és a **Leírás** mezők a nyelven alapuló értékeket adnak eredményül, az **IsTranslated** mező pedig az **Igaz** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-130">If the labels and descriptions for the requested language are available, the **Label** and **Description** fields return values that are based on that language, and the **IsTranslated** field returns **True**.</span></span>
- <span data-ttu-id="5b2dd-131">Ha a kért nyelv címkéi és leírása nem állnak rendelkezésre, a **Címke** és **Leírás** mezők az alapértelmezett **EN-US** nyelven alapuló értékeket adnak eredményül, az **IsTranslated** mező pedig a **Hamis** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-131">If the labels and descriptions for the requested language aren't available, the **Label** and **Description** fields return values that are based on the default **EN-US** language, and the **IsTranslated** field returns **False**.</span></span>

<span data-ttu-id="5b2dd-132">Futásidőben, ha az 2-es szintaxist használja, a **Címke** és a **Leírás** mezőknek a meghívott függvény második argumentumaként megadott nyelven alapuló visszaadott értéket kell eredményül adniuk:</span><span class="sxs-lookup"><span data-stu-id="5b2dd-132">At runtime, when syntax 2 is used, the **Label** and **Description** fields must return values that are based on the language that is defined as the second argument of the called function:</span></span>

- <span data-ttu-id="5b2dd-133">Ha a kért nyelv címkéi és leírása rendelkezésre állnak, a **Címke** és a **Leírás** mezők a nyelven alapuló értékeket adnak eredményül, az **IsTranslated** mező pedig az **Igaz** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-133">If the labels and descriptions for the requested language are available, the **Label** and **Description** fields return values that are based on that language, and the **IsTranslated** field returns **True**.</span></span>
- <span data-ttu-id="5b2dd-134">Ha a kért nyelv címkéi és leírása nem állnak rendelkezésre, a **Címke** és **Leírás** mezők az **EN-US** nyelven alapuló értékeket adnak eredményül, az **IsTranslated** mező pedig a **Hamis** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-134">If the labels and descriptions for the requested language aren't available, the **Label** and **Description** fields return values that are based on the **EN-US** language, and the **IsTranslated** field returns **False**.</span></span>

## <a name="example-1"></a><span data-ttu-id="5b2dd-135">1. példa</span><span class="sxs-lookup"><span data-stu-id="5b2dd-135">Example 1</span></span>

<span data-ttu-id="5b2dd-136">A következő ábra az ER-adatmodellbe bevezetett sorszámozást mutatja be.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-136">In the following illustration, an enumeration is introduced in an ER data model.</span></span>

<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

<span data-ttu-id="5b2dd-137">A következő ábrán ezek a részletek láthatók:</span><span class="sxs-lookup"><span data-stu-id="5b2dd-137">The following illustration shows these details:</span></span>

- <span data-ttu-id="5b2dd-138">A modell felsorolása adatforrásként kerül be egy jelentésbe.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-138">The model enumeration is inserted into a report as a data source.</span></span>
- <span data-ttu-id="5b2dd-139">Az ER kifejezés a modellfelsorolást a `LISTOFFIELDS` függvény paramétereként használja.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-139">An ER expression uses the model enumeration as a parameter of the `LISTOFFIELDS` function.</span></span>
- <span data-ttu-id="5b2dd-140">A *Rekordlista* típus adatforrása beillesztésre kerül egy jelentésbe a létrehozott ER-kifejezés használatával.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-140">A data source of the *Record list* type is inserted into a report by using the ER expression that is created.</span></span>

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a>

<span data-ttu-id="5b2dd-141">A következő példa azokat az ER formázási elemeket mutat be, amelyek ahhoz a *Rekordlista* típusú adatforráshoz vannak kötve, amelyet a `LISTOFFIELDS` függvénnyel hoztak létre.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-141">The following example shows the ER format elements that are bound to the data source of the *Record list* type that was created by using the `LISTOFFIELDS` function.</span></span>

<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

<span data-ttu-id="5b2dd-142">Az alábbi ábrán a tervezett formátum futtatásának eredménye látható.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-142">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a>

> [!NOTE] 
> <span data-ttu-id="5b2dd-143">A címkék és leírások fordított szövege az ER formátumú kimenetbe kerül bevitelre, a szülő **FILE** és **FOLDER** formátumelemekhez konfigurált nyelvi beállításainak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-143">Based on the language settings of the parent **FILE** and **FOLDER** format elements, translated text for labels and descriptions is entered in the output of the ER format.</span></span>

## <a name="example-2"></a><span data-ttu-id="5b2dd-144">2. példa</span><span class="sxs-lookup"><span data-stu-id="5b2dd-144">Example 2</span></span>

<span data-ttu-id="5b2dd-145">Használhatja a *Számított mező* adatforrástípust az **enumType\_de** és **enumType\_deCH** adatforrásoknak az **enumType** adatmodell-felsoroláshoz való konfigurálására:</span><span class="sxs-lookup"><span data-stu-id="5b2dd-145">You use the *Calculated field* data source type to configure **enumType\_de** and **enumType\_deCH** data sources for the **enumType** data model enumeration:</span></span>

- <span data-ttu-id="5b2dd-146">**enumType\_de** = `LISTOFFIELDS (enumType, "de")`</span><span class="sxs-lookup"><span data-stu-id="5b2dd-146">**enumType\_de** = `LISTOFFIELDS (enumType, "de")`</span></span>
- <span data-ttu-id="5b2dd-147">**enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`</span><span class="sxs-lookup"><span data-stu-id="5b2dd-147">**enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`</span></span>

<span data-ttu-id="5b2dd-148">Ebben az esetben a következő kifejezést használhatja a felsorolási érték címkéjének svájci német nyelven történő lekéréséhez, ha ez a fordítás elérhető.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-148">In this case, you can use the following expression to get the label of the enumeration value in Swiss German, if that translation is available.</span></span> <span data-ttu-id="5b2dd-149">Ha a svájci német fordítás nem érhető el, a címke németül szerepel.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-149">If the Swiss German translation isn't available, the label is in German.</span></span>

```vb
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
```

## <a name="additional-resources"></a><span data-ttu-id="5b2dd-150">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="5b2dd-150">Additional resources</span></span>

[<span data-ttu-id="5b2dd-151">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="5b2dd-151">List functions</span></span>](er-functions-category-list.md)
