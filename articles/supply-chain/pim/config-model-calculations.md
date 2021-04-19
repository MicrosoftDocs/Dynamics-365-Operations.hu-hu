---
title: Termékkonfigurációs modell számításai
description: Ez a témakör azt mutatja be, hogyan hozhat létre számításokat attribútumokhoz egy termékkonfigurációs modellben
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eaf6264f060d33575740ad38e7a65158baba296b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829618"
---
# <a name="product-configuration-model-calculations"></a><span data-ttu-id="83788-103">Termékkonfigurációs modell számításai</span><span class="sxs-lookup"><span data-stu-id="83788-103">Product configuration model calculations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="83788-104">Ez a témakör azt mutatja be, hogyan hozhat létre számításokat attribútumokhoz egy termékkonfigurációs modellben.</span><span class="sxs-lookup"><span data-stu-id="83788-104">This topic describes how to create calculations for attributes in a product configuration model.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="83788-105">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="83788-105">Prerequisites</span></span>

<span data-ttu-id="83788-106">A számításokkal számíthatók ki egy termékkonfigurációs modellben a termék konfigurációs értékei.</span><span class="sxs-lookup"><span data-stu-id="83788-106">Calculations are used in a product configuration model to calculate the configuration values for a product.</span></span> <span data-ttu-id="83788-107">A számítások beállításának megkezdése előtt a kapcsolódó termékkonfigurációs modellnek léteznie kell.</span><span class="sxs-lookup"><span data-stu-id="83788-107">Before you can start to set up calculations, the related product configuration model must exist.</span></span> <span data-ttu-id="83788-108">A konfigurációs modellek beállítási folyamatának és a kapcsolódó feladatoknak az áttekintését [Termékkonfigurációs modell beállítása](set-up-maintain-product-configuration-model.md) témakörben találja.</span><span class="sxs-lookup"><span data-stu-id="83788-108">For an overview of the setup process for configuration models and the related tasks, see [Set up a product configuration model](set-up-maintain-product-configuration-model.md).</span></span>

## <a name="create-a-calculation"></a><span data-ttu-id="83788-109">Számítások létrehozása</span><span class="sxs-lookup"><span data-stu-id="83788-109">Create a calculation</span></span>

<span data-ttu-id="83788-110">A számítás egy kifejezésből és egy célattribútumból áll.</span><span class="sxs-lookup"><span data-stu-id="83788-110">A calculation consists of an expression and a target attribute.</span></span> <span data-ttu-id="83788-111">További információért lásd: [Kalkulációk a termékkonfigurációs modellekhez - GYIK](calculate-product-configuration-models.md).</span><span class="sxs-lookup"><span data-stu-id="83788-111">For more information, see [Calculations for product configuration models FAQ](calculate-product-configuration-models.md).</span></span>

<span data-ttu-id="83788-112">Meglévő termékmodell számításának létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="83788-112">To create a calculation for an existing product model, follow these steps.</span></span>

1. <span data-ttu-id="83788-113">Lépjen a **Termékinformációk kezelése \> Közös \> Termékkonfigurációs modellek** elemre.</span><span class="sxs-lookup"><span data-stu-id="83788-113">Go to **Product information management \> Common \> Product configuration models**.</span></span>
1. <span data-ttu-id="83788-114">Nyisson meg egy termékkonfigurációs modellt, majd válassza a **Szerkesztés** elemet.</span><span class="sxs-lookup"><span data-stu-id="83788-114">Open a product configuration model, and then select **Edit**.</span></span>
1. <span data-ttu-id="83788-115">A **Számítások** gyorslapon válassza a **Hozzáadás** parancsot egy számítás hozzáadásához, majd állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="83788-115">On the **Calculations** FastTab, select **Add** to add a calculation, and then set the following fields:</span></span>

    - <span data-ttu-id="83788-116">**Név** – Adjon meg egy nevet a számításnak.</span><span class="sxs-lookup"><span data-stu-id="83788-116">**Name** – Enter a name for the calculation.</span></span>
    - <span data-ttu-id="83788-117">**Leírás** – Adja meg a számítás leírását.</span><span class="sxs-lookup"><span data-stu-id="83788-117">**Description** – Enter a description of the calculation.</span></span>
    - <span data-ttu-id="83788-118">**Célattribútum** – Válassza ki azt az attribútumot, amelyhez a számítást végzi.</span><span class="sxs-lookup"><span data-stu-id="83788-118">**Target attribute** – Select the attribute that you're making the calculation for.</span></span>

1. <span data-ttu-id="83788-119">Válassza a **Kifejezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83788-119">Select **Edit expression**.</span></span>
1. <span data-ttu-id="83788-120">A **Számítás megadása** párbeszédpanelben adja hozzá a kifejezéshez a szükséges attribútumokat, operátorokat és értékeket.</span><span class="sxs-lookup"><span data-stu-id="83788-120">In the **Enter a calculation** dialog box, add the required attributes, operators, and values to the expression.</span></span> <span data-ttu-id="83788-121">További tudnivalók ezeknek az elemeknek a kezeléséről: [A termékkonfigurációs modellek kifejezés- és táblamegszorításai](expression-constraints-table-constraints-product-configuration-models.md).</span><span class="sxs-lookup"><span data-stu-id="83788-121">For more information about how to work with these elements, see [Expression constraints and table constraints in product configuration models](expression-constraints-table-constraints-product-configuration-models.md).</span></span>
1. <span data-ttu-id="83788-122">Amikor a kifejezés elkészült, válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83788-122">When your expression is ready, select **OK**.</span></span>

## <a name="calculation-examples"></a><span data-ttu-id="83788-123">Számítási példák</span><span class="sxs-lookup"><span data-stu-id="83788-123">Calculation examples</span></span>

<span data-ttu-id="83788-124">Ez a szakasz néhány példát mutat be arra, hogyan működnek a számítások.</span><span class="sxs-lookup"><span data-stu-id="83788-124">This section provides a few examples that show how calculations work.</span></span>

### <a name="example-1"></a><span data-ttu-id="83788-125">1. példa</span><span class="sxs-lookup"><span data-stu-id="83788-125">Example 1</span></span>

<span data-ttu-id="83788-126">A célattribútum logikai típusú, és a számítás a következő feltételes kifejezést használja:</span><span class="sxs-lookup"><span data-stu-id="83788-126">The target attribute is Boolean, and the calculation uses the following conditional expression:</span></span>

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

<span data-ttu-id="83788-127">A kifejezés *Igaz* értéket ad ki a célattribútumnak, ha a `decimalAttribute2` nagyobb vagy egyenlő a `decimalAttribute1` értékénél.</span><span class="sxs-lookup"><span data-stu-id="83788-127">This expression returns a value of *True* to the target attribute if `decimalAttribute2` is greater than or equal to `decimalAttribute1`.</span></span> <span data-ttu-id="83788-128">Ellenkező esetben *Hamis* eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="83788-128">Otherwise, it returns a value of *False*.</span></span>

### <a name="example-2"></a><span data-ttu-id="83788-129">2. példa</span><span class="sxs-lookup"><span data-stu-id="83788-129">Example 2</span></span>

<span data-ttu-id="83788-130">Ez a példa a `textFixedList` szöveges attribútumot használja célattribútumként.</span><span class="sxs-lookup"><span data-stu-id="83788-130">This example uses the text attribute `textFixedList` as the target attribute.</span></span> <span data-ttu-id="83788-131">Ez az attribútum a következő rögzített listát tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="83788-131">This attribute contains the following fixed list.</span></span>

| <span data-ttu-id="83788-132">Érték</span><span class="sxs-lookup"><span data-stu-id="83788-132">Value</span></span> | <span data-ttu-id="83788-133">A feloldó érték</span><span class="sxs-lookup"><span data-stu-id="83788-133">Solver value</span></span> |
|---|---|
| <span data-ttu-id="83788-134">A</span><span class="sxs-lookup"><span data-stu-id="83788-134">A</span></span> | <span data-ttu-id="83788-135">1a</span><span class="sxs-lookup"><span data-stu-id="83788-135">1a</span></span> |
| <span data-ttu-id="83788-136">milliárd</span><span class="sxs-lookup"><span data-stu-id="83788-136">B</span></span> | <span data-ttu-id="83788-137">2b</span><span class="sxs-lookup"><span data-stu-id="83788-137">2b</span></span> |
| <span data-ttu-id="83788-138">K</span><span class="sxs-lookup"><span data-stu-id="83788-138">C</span></span> | <span data-ttu-id="83788-139">2c</span><span class="sxs-lookup"><span data-stu-id="83788-139">2c</span></span> |

<span data-ttu-id="83788-140">A következő képernyőkép bemutatja, hogy hogyan nézhetnek ki az attribútum beállításai a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="83788-140">The following screenshot shows how the settings for this attribute might look in your system.</span></span>

<span data-ttu-id="83788-141">![Attribútumtípus-beállítások a 2. példához](media/model-calculations-example2.png "Attribútumtípus-beállítások a 2. példához")</span><span class="sxs-lookup"><span data-stu-id="83788-141">![Attribute type settings for example 2](media/model-calculations-example2.png "Attribute type settings for example 2")</span></span>

<span data-ttu-id="83788-142">Az attribútumot a következő feltételes utasítás használja:</span><span class="sxs-lookup"><span data-stu-id="83788-142">The attribute is used in the following conditional statement:</span></span>

`If[integerAttribute < 150, 0, 2]`

<span data-ttu-id="83788-143">Ha az `integerAttribute` értéke kisebb, mint 150, akkor ez az utasítás az *A* rögzített lista első rekordját adja vissza. Ellenkező esetben a *C* rögzített lista harmadik rekordjának szövegértéke szerepel benne.</span><span class="sxs-lookup"><span data-stu-id="83788-143">If `integerAttribute` is less than 150, this statement returns the text value of the first record in the fixed list, *A*. Otherwise, it returns the text value of the third record in the fixed list, *C*.</span></span>

> [!NOTE]
> <span data-ttu-id="83788-144">A rögzített lista egy nulla alapú felsorolásnak (enum) felel meg, és értékeit a megfelelő egész érték érheti el.</span><span class="sxs-lookup"><span data-stu-id="83788-144">The fixed list is equivalent to a zero-based enumeration (enum), and its values are accessed by the appropriate integer value.</span></span> <span data-ttu-id="83788-145">Ebből következően az első rögzített listaérték (*A*) a *0*-nak felel meg, a második (*B*) *1* értéknek, a harmadik (*C*) *2* értéknek felel meg.</span><span class="sxs-lookup"><span data-stu-id="83788-145">Therefore, the first fixed list value (*A*) is matched to *0*, the second value (*B*) is matched to *1*, and the third value (*C*) is matched to *2*.</span></span>

### <a name="example-3"></a><span data-ttu-id="83788-146">3. példa</span><span class="sxs-lookup"><span data-stu-id="83788-146">Example 3</span></span>

<span data-ttu-id="83788-147">Ez a példa a `textFixedList` célattribútumot használja az előző példából.</span><span class="sxs-lookup"><span data-stu-id="83788-147">This example uses the `textFixedList` target attribute from the previous example.</span></span> <span data-ttu-id="83788-148">Másik szöveges attribútumot (`textAttribute`) is használ, amely a következő rögzített listát tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="83788-148">It also uses another text attribute, `textAttribute`, that contains the following fixed list.</span></span>

| <span data-ttu-id="83788-149">Érték</span><span class="sxs-lookup"><span data-stu-id="83788-149">Value</span></span> | <span data-ttu-id="83788-150">A feloldó érték</span><span class="sxs-lookup"><span data-stu-id="83788-150">Solver value</span></span> |
|---|---|
| <span data-ttu-id="83788-151">AA</span><span class="sxs-lookup"><span data-stu-id="83788-151">AA</span></span> | <span data-ttu-id="83788-152">1aa</span><span class="sxs-lookup"><span data-stu-id="83788-152">1aa</span></span> |
| <span data-ttu-id="83788-153">BB</span><span class="sxs-lookup"><span data-stu-id="83788-153">BB</span></span> | <span data-ttu-id="83788-154">2bb</span><span class="sxs-lookup"><span data-stu-id="83788-154">2bb</span></span> |

<span data-ttu-id="83788-155">A következő képernyőkép bemutatja, hogy hogyan nézhetnek ki az attribútum beállításai a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="83788-155">The following screenshot shows how the settings for this attribute might look in your system.</span></span>

<span data-ttu-id="83788-156">![Attribútumtípus-beállítások a 3. példához](media/model-calculations-example3.png "Attribútumtípus-beállítások a 3. példához")</span><span class="sxs-lookup"><span data-stu-id="83788-156">![Attribute type settings for example 3](media/model-calculations-example3.png "Attribute type settings for example 3")</span></span>

<span data-ttu-id="83788-157">A `textFixedList` attribútum értékét a következő feltételes kimutatás használatával számítja ki a program:</span><span class="sxs-lookup"><span data-stu-id="83788-157">The value for the `textFixedList` attribute is calculated by using the following conditional statement:</span></span>

`If[textAttribute == "1aa", 0, 2]`

<span data-ttu-id="83788-158">Ha a `textAttribute` értékének feloldási értéke *1aa*, akkor ez a kifejezés az *A* `textFixedList` rögzített lista első rekordját adja vissza. Ellenkező esetben a *C* `textFixedList` rögzített lista harmadik rekordjának szövegértéke szerepel benne.</span><span class="sxs-lookup"><span data-stu-id="83788-158">If the `textAttribute` value has a solver value that equals *1aa*, this expression returns the text value of the first record in the `textFixedList` fixed list, *A*. Otherwise, it returns the text value of the third record in the `textFixedList` fixed list, *C*.</span></span>

> [!NOTE]
> - <span data-ttu-id="83788-159">A feltételes utasításnak az attribútum feloldási értékét kell használnia.</span><span class="sxs-lookup"><span data-stu-id="83788-159">The conditional statement must use the solver value of the attribute.</span></span>
> - <span data-ttu-id="83788-160">A számításokban csak rögzített lista szöveges attribútumok használhatók.</span><span class="sxs-lookup"><span data-stu-id="83788-160">Only fixed-list text attributes can be used in calculations.</span></span>

## <a name="see-also"></a><span data-ttu-id="83788-161">Lásd még</span><span class="sxs-lookup"><span data-stu-id="83788-161">See also</span></span>

- [<span data-ttu-id="83788-162">Kalkulációk a termékkonfigurációs modellekhez - GYIK</span><span class="sxs-lookup"><span data-stu-id="83788-162">Calculations for product configuration models FAQ</span></span>](calculate-product-configuration-models.md)
- [<span data-ttu-id="83788-163">Kifejezésmegszorítás hozzáadása a termékkonfigurációs modellhez</span><span class="sxs-lookup"><span data-stu-id="83788-163">Add an expression constraint to a product configuration model</span></span>](tasks/add-expression-constraint-product-configuration-model.md)
- [<span data-ttu-id="83788-164">Termékkonfigurálási modellek áttekintése</span><span class="sxs-lookup"><span data-stu-id="83788-164">Product configuration models overview</span></span>](product-configuration-models.md)
