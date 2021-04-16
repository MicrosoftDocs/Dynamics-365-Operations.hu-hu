---
title: GETENUMVALUEBYNAME ER-függvény
description: A témakör tájékoztatást nyújt a GETENUMVALUEBYNAME Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 72b5831e3d2bc2e839b0a569fb314a8ec074a5a1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746411"
---
# <a name="getenumvaluebyname-er-function"></a><span data-ttu-id="3e869-103">GETENUMVALUEBYNAME ER-függvény</span><span class="sxs-lookup"><span data-stu-id="3e869-103">GETENUMVALUEBYNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3e869-104">A `GETENUMVALUEBYNAME` függvény egy adott *Felsorolás* értéket keres a megadott felsorolási adatforrásban a *Karakterlánc* értékként megadott felsorolási név használatával.</span><span class="sxs-lookup"><span data-stu-id="3e869-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="3e869-105">Ha a *Felsorolás* értéke megtalálható, a függvény azt visszaadja.</span><span class="sxs-lookup"><span data-stu-id="3e869-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="3e869-106">Ellenkező esetben a függvény **null** értékű felsorolási értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="3e869-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e869-107">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="3e869-107">Syntax</span></span>

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="3e869-108">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="3e869-108">Arguments</span></span>

<span data-ttu-id="3e869-109">`enumeration data source path`: *Felsorolás*</span><span class="sxs-lookup"><span data-stu-id="3e869-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="3e869-110">A következő felsorolástípusok egyikéhez tartozó adatforrás érvényes útvonala:</span><span class="sxs-lookup"><span data-stu-id="3e869-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="3e869-111">Elektronikus jelentéskészítési (ER) modell felsorolása</span><span class="sxs-lookup"><span data-stu-id="3e869-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="3e869-112">ER-formátum felsorolása</span><span class="sxs-lookup"><span data-stu-id="3e869-112">ER format enumeration</span></span>
- <span data-ttu-id="3e869-113">Microsoft Dynamics 365 Finance felsorolás</span><span class="sxs-lookup"><span data-stu-id="3e869-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="3e869-114">`enumeration value text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="3e869-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="3e869-115">Egy karakterláncérték, amely egy felsorolási érték nevét jelöli.</span><span class="sxs-lookup"><span data-stu-id="3e869-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="3e869-116">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="3e869-116">Return values</span></span>

<span data-ttu-id="3e869-117">Nullázható *Felsorolás*</span><span class="sxs-lookup"><span data-stu-id="3e869-117">Nullable *Enum*</span></span>

<span data-ttu-id="3e869-118">Az eredményül kapott felsorolási érték.</span><span class="sxs-lookup"><span data-stu-id="3e869-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="3e869-119">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="3e869-119">Usage notes</span></span>

<span data-ttu-id="3e869-120">Nem történik kivétel, ha a *Felsorolás* érték nem található a *Karakterlánc* értékként megadott felsorolási érték nevével.</span><span class="sxs-lookup"><span data-stu-id="3e869-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="3e869-121">1. példa</span><span class="sxs-lookup"><span data-stu-id="3e869-121">Example 1</span></span>

<span data-ttu-id="3e869-122">A következő ábra az adatmodellbe bevezetett **ReportDirection** sorszámozást mutatja be.</span><span class="sxs-lookup"><span data-stu-id="3e869-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="3e869-123">Vegye figyelembe, hogy a címkék a felsorolási értékekhez vannak megadva.</span><span class="sxs-lookup"><span data-stu-id="3e869-123">Notice that labels are defined for the enumeration values.</span></span>

![Az adatmodell-felsorolásához elérhető értékek](./media/ER-data-model-enumeration-values.PNG)

<span data-ttu-id="3e869-125">A következő ábrán ezek a részletek láthatók:</span><span class="sxs-lookup"><span data-stu-id="3e869-125">The following illustration shows these details:</span></span>

- <span data-ttu-id="3e869-126">A **$Direction** -adatforrást egy ER-jelentés konfigurálja.</span><span class="sxs-lookup"><span data-stu-id="3e869-126">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="3e869-127">Ez az adatforrás a **ReportDirection** modell felsorolása alapján van konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="3e869-127">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="3e869-128">Az `$IsArrivals` kifejezés a modellfelsorolás-alapú **$Direction** adatforrást a jelen függvény paramétereként használja.</span><span class="sxs-lookup"><span data-stu-id="3e869-128">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="3e869-129">Az összehasonlító kifejezés értéke **IGAZ**.</span><span class="sxs-lookup"><span data-stu-id="3e869-129">The value of this comparison expression is **TRUE**.</span></span>

![Egy adatmodell-felsorolás példája](./media/ER-data-model-enumeration-usage.PNG)

## <a name="example-2"></a><span data-ttu-id="3e869-131">2. példa</span><span class="sxs-lookup"><span data-stu-id="3e869-131">Example 2</span></span>

<span data-ttu-id="3e869-132">A `GETENUMVALUEBYNAME` és a [`LISTOFFIELDS`](er-functions-list-listoffields.md) funkció lehetővé teszi a támogatott felsorolások értékeinek és címkéinek szöveges értékként történő beolvasását.</span><span class="sxs-lookup"><span data-stu-id="3e869-132">The `GETENUMVALUEBYNAME` and [`LISTOFFIELDS`](er-functions-list-listoffields.md) functions let you fetch values and labels of supported enumerations as text values.</span></span> <span data-ttu-id="3e869-133">(A támogatott felsorolások alkalmazás-felsorolások, adatmodell-felsorolások, valamint formátum-felsorolások.)</span><span class="sxs-lookup"><span data-stu-id="3e869-133">(The supported enumerations are application enumerations, data model enumerations, and format enumerations.)</span></span>

<span data-ttu-id="3e869-134">A következő ábra a modell-leképezésben bevezetett **TransType** adatforrást mutatja be.</span><span class="sxs-lookup"><span data-stu-id="3e869-134">In the following illustration, the **TransType** data source is introduced in a model mapping.</span></span> <span data-ttu-id="3e869-135">Ez az adatforrás az **LedgerTransType** alkalmazás-felsorolásra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="3e869-135">This data source refers to the **LedgerTransType** application enumeration.</span></span>

![Egy alkalmazás-felsorolásra hivatkozó modell-leképezési adatforrás](./media/er-functions-text-getenumvaluebyname-example2-1.png)

<span data-ttu-id="3e869-137">A következő ábra a modell-leképezésben konfigurált **TransTypeList** adatforrást mutatja be.</span><span class="sxs-lookup"><span data-stu-id="3e869-137">The following illustration shows the **TransTypeList** data source that is configured in a model mapping.</span></span> <span data-ttu-id="3e869-138">Ez az adatforrás a **TransType** alkalmazás felsorolása alapján van konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="3e869-138">This data source is configured based on the **TransType** application enumeration.</span></span> <span data-ttu-id="3e869-139">A `LISTOFFIELDS` funkció használatával az összes felsorolási érték visszatéríthető mezőket tartalmazó rekordok listájaként.</span><span class="sxs-lookup"><span data-stu-id="3e869-139">The `LISTOFFIELDS` function is used to return all enumeration values as a list of records that contain fields.</span></span> <span data-ttu-id="3e869-140">Így az összes felsorolási érték részletei megjeleníthetők.</span><span class="sxs-lookup"><span data-stu-id="3e869-140">In this way, the details of every enumeration value are exposed.</span></span>

> [!NOTE]
> <span data-ttu-id="3e869-141">Az **EnumValue** mező a **TransTypeList** adatforráshoz a `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)` kifejezés használatával van konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="3e869-141">The **EnumValue** field is configured for the **TransTypeList** data source by using the `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)` expression.</span></span> <span data-ttu-id="3e869-142">Ez a mező a lista minden rekordjához egy felsorolási értéket juttat vissza.</span><span class="sxs-lookup"><span data-stu-id="3e869-142">This field returns an enumeration value for every record in this list.</span></span>

![Egy modell-leképezés adatforrása, amely egy kiválasztott felsorolás összes felsorolási értékét rekordok listájaként juttatja vissza](./media/er-functions-text-getenumvaluebyname-example2-2.png)

<span data-ttu-id="3e869-144">A következő ábra a modell-leképezésben konfigurált **VendTrans** adatforrást mutatja be.</span><span class="sxs-lookup"><span data-stu-id="3e869-144">The following illustration shows the **VendTrans** data source that is configured in a model mapping.</span></span> <span data-ttu-id="3e869-145">Ez az adatforrás szállítói tranzakciórekordokat juttat vissza a **VendTrans** alkalmazástáblából.</span><span class="sxs-lookup"><span data-stu-id="3e869-145">This data source returns vendor transaction records from the **VendTrans** application table.</span></span> <span data-ttu-id="3e869-146">Minden tranzakció főkönyvi típusát a **TransType** mező értéke határozza meg.</span><span class="sxs-lookup"><span data-stu-id="3e869-146">The ledger type of every transaction is defined by the value of the **TransType** field.</span></span>

> [!NOTE]
> <span data-ttu-id="3e869-147">Az **TransTypeTitle** mező a **VendTrans** adatforráshoz a `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label` kifejezés használatával van konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="3e869-147">The **TransTypeTitle** field is configured for the **VendTrans** data source by using the `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label` expression.</span></span> <span data-ttu-id="3e869-148">Ha elérhető a felsorolási érték, akkor ez a mező szövegként juttatja vissza az aktuális tranzakció felsorolási értékének címkéjét.</span><span class="sxs-lookup"><span data-stu-id="3e869-148">This field returns the label of an enumeration value of the current transaction as text, if this enumeration value is available.</span></span> <span data-ttu-id="3e869-149">Ellenkező esetben üres karakterláncértéket jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="3e869-149">Otherwise, it returns a blank string value.</span></span>
>
> <span data-ttu-id="3e869-150">A **TransTypeTitle** mező egy olyan adatmodell **LedgerType** mezőjéhez van kötve, amely lehetővé teszi, hogy ez az információ minden olyan ER-formátumban használható legyen, amely az adatmodellt adatforrásként használja.</span><span class="sxs-lookup"><span data-stu-id="3e869-150">The **TransTypeTitle** field is bound to the **LedgerType** field of a data model that enables this information to be used in every ER format that uses the data model as a source of data.</span></span>

![Szállítói tranzakciókat visszaadó modell-leképezési adatforrás](./media/er-functions-text-getenumvaluebyname-example2-3.png)

<span data-ttu-id="3e869-152">A következő ábra bemutatja, hogyan használható az [adatforrás hibakeresője](er-debug-data-sources.md) a konfigurált modell-leképezés teszteléséhez.</span><span class="sxs-lookup"><span data-stu-id="3e869-152">The following illustration shows how you can use the [data source debugger](er-debug-data-sources.md) to test the configured model mapping.</span></span>

![A konfigurált modell-leképezés tesztelése az adatforrás hibakeresőjének segítségével](./media/er-functions-text-getenumvaluebyname-example2-4.gif)

<span data-ttu-id="3e869-154">Az adatmodell **LedgerType** mezője a várt módon jeleníti meg a tranzakciótípusok címkéit.</span><span class="sxs-lookup"><span data-stu-id="3e869-154">The **LedgerType** field of a data model exposes labels of transaction types as expected.</span></span>

<span data-ttu-id="3e869-155">Ha nagy mennyiségű tranzakciós adathoz kívánja használni ezt a tervet, akkor figyelembe kell vennie a végrehajtás teljesítményt.</span><span class="sxs-lookup"><span data-stu-id="3e869-155">If you plan to use this approach for a large amount of transactional data, you must consider execution performance.</span></span> <span data-ttu-id="3e869-156">További információkért lásd: [Az ER-formátumok végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárítása érdekében](trace-execution-er-troubleshoot-perf.md).</span><span class="sxs-lookup"><span data-stu-id="3e869-156">For more information, see [Trace the execution of ER formats to troubleshoot performance issues](trace-execution-er-troubleshoot-perf.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e869-157">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="3e869-157">Additional resources</span></span>

[<span data-ttu-id="3e869-158">Szöveges függvények</span><span class="sxs-lookup"><span data-stu-id="3e869-158">Text functions</span></span>](er-functions-category-text.md)

[<span data-ttu-id="3e869-159">Az ER-formátumok végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárítása érdekében</span><span class="sxs-lookup"><span data-stu-id="3e869-159">Trace the execution of ER formats to troubleshoot performance issues</span></span>](trace-execution-er-troubleshoot-perf.md)

[<span data-ttu-id="3e869-160">LISTOFFIELDS ER-függvény</span><span class="sxs-lookup"><span data-stu-id="3e869-160">LISTOFFIELDS ER function</span></span>](er-functions-list-listoffields.md)

[<span data-ttu-id="3e869-161">FIRSTORNULL ER függvény</span><span class="sxs-lookup"><span data-stu-id="3e869-161">FIRSTORNULL ER function</span></span>](er-functions-list-firstornull.md)

[<span data-ttu-id="3e869-162">WHERE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="3e869-162">WHERE ER function</span></span>](er-functions-list-where.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]