---
title: SUMIF ER-függvény
description: A témakör tájékoztatást nyújt a SUMIF Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 04/27/2020
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
ms.openlocfilehash: 6f5069d197abf2e38d09012defeb982a9e5e1234
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565964"
---
# <a name="sumif-er-function"></a><span data-ttu-id="831fb-103">SUMIF ER-függvény</span><span class="sxs-lookup"><span data-stu-id="831fb-103">SUMIF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="831fb-104">A `SUMIF` függvény egy *Valós* értéket ad eredményül, amely a formátumelemek kötései által visszaadott értékek összegét mutatja, amelyeket akkor gyűjtöttek össze, amikor a formázási elemek a formátum futtatása során kimenő dokumentumok létrehozására kerültek felhasználásra, és amelyek kielégítik a megadott feltételt.</span><span class="sxs-lookup"><span data-stu-id="831fb-104">The `SUMIF` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="831fb-105">A feltétel egy kulcstartományt és egy kulcsértéket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="831fb-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="831fb-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="831fb-106">Syntax</span></span>

```vb
SUMIF (key name for summing, condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="831fb-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="831fb-107">Arguments</span></span>

<span data-ttu-id="831fb-108">`key name for summing`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="831fb-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="831fb-109">Az az érték, amelyet az Elektronikus jelentéskészítési (ER) formátum összetevő **Gyűjtött adatkulcs neve** tulajdonságában konfigurált kifejezés ad vissza, amelynek az összegzéshez a kötés értékét kell használni.</span><span class="sxs-lookup"><span data-stu-id="831fb-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="831fb-110">Az **Gyűjtött adatkulcs értéke** tulajdonság az ER-formátum **Sorrend** összetevőjéhez vagy **XML-elem** összetevőjéhez konfigurálható, amely a **Common\\File** összetevő alatt található, ahol a **Kimeneti részletek gyűjtése** beállítás be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="831fb-110">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="831fb-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="831fb-111">Return values</span></span>

<span data-ttu-id="831fb-112">*Valós*</span><span class="sxs-lookup"><span data-stu-id="831fb-112">*Real*</span></span>

<span data-ttu-id="831fb-113">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="831fb-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="831fb-114">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="831fb-114">Usage notes</span></span>

<span data-ttu-id="831fb-115">Ez a függvény **0** (nulla) értéket ad vissza, ha az aktuális **Common\\File** összetevő **Kimeneti részletek gyűjtése** beállítása ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="831fb-115">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="831fb-116">A `condition range` argumentumban a **„\*”** helyettesítő karakter használható tetszőleges többszörös karakter ábrázolására.</span><span class="sxs-lookup"><span data-stu-id="831fb-116">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="831fb-117">A `condition value` argumentumban a **„\*”** helyettesítő karakter használható tetszőleges többszörös karakter ábrázolására.</span><span class="sxs-lookup"><span data-stu-id="831fb-117">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="831fb-118">Példa</span><span class="sxs-lookup"><span data-stu-id="831fb-118">Example</span></span>

<span data-ttu-id="831fb-119">Ha többet szeretne megtudni e függvény használatáról, tekintse meg az [ER kimeneti adatformátum használata számlálás és összegzés céljából](tasks/er-format-counting-summing-1.md) című feladat-útmutatót (ez az **Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése** üzleti folyamat része).</span><span class="sxs-lookup"><span data-stu-id="831fb-119">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

<span data-ttu-id="831fb-120">A funkció használatával kapcsolatos további példákat és tudnivalókat lásd: [A szekvenciaelemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-sequence-element.md#Example) és [Az XML-elemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-xml-element.md#Example).</span><span class="sxs-lookup"><span data-stu-id="831fb-120">For more information and examples about using this function, see [Defer the execution of sequence elements in ER formats](er-defer-sequence-element.md#Example) and [Defer the execution of XML elements in ER formats](er-defer-xml-element.md#Example).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="831fb-121">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="831fb-121">Additional resources</span></span>

[<span data-ttu-id="831fb-122">Adatgyűjtési függvények</span><span class="sxs-lookup"><span data-stu-id="831fb-122">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]