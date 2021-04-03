---
title: COUNTIF ER-függvény
description: A témakör tájékoztatást nyújt a COUNTIF Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 19ceb8d3023aadeb6307ed5d930587a8f00f63b7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561374"
---
# <a name="countif-er-function"></a><span data-ttu-id="2eaee-103">COUNTIF ER-függvény</span><span class="sxs-lookup"><span data-stu-id="2eaee-103">COUNTIF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2eaee-104">A `COUNTIF` függvény egy *Egész* értéket ad eredményül, amely azoknak a formátumelemeknek a számát adja vissza, amelyeket akkor gyűjtöttek össze, amikor a formázási elemek a formátum futtatása során kimenő dokumentumok létrehozására kerültek felhasználásra, és amelyek kielégítik a megadott feltételt.</span><span class="sxs-lookup"><span data-stu-id="2eaee-104">The `COUNTIF` function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="2eaee-105">A feltétel egy kulcstartományt és egy kulcsértéket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="2eaee-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="2eaee-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="2eaee-106">Syntax</span></span>

```vb
COUNTIF (condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="2eaee-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="2eaee-107">Arguments</span></span>

<span data-ttu-id="2eaee-108">`condition range`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="2eaee-108">`condition range`: *String*</span></span>

<span data-ttu-id="2eaee-109">Olyan érték, amelyet az Elektronikus jelentéskészítési (ER) formátum összetevő **Gyűjtött adatkulcs neve** tulajdonságában konfigurált kifejezés adott vissza.</span><span class="sxs-lookup"><span data-stu-id="2eaee-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span>

<span data-ttu-id="2eaee-110">`condition value`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="2eaee-110">`condition value`: *String*</span></span>

<span data-ttu-id="2eaee-111">Olyan érték, amelyet egy ER-formátum összetevő **Gyűjtött adatkulcs értéke** tulajdonságában konfigurált kifejezés adott vissza.</span><span class="sxs-lookup"><span data-stu-id="2eaee-111">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span>

## <a name="return-values"></a><span data-ttu-id="2eaee-112">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="2eaee-112">Return values</span></span>

<span data-ttu-id="2eaee-113">*Egész*</span><span class="sxs-lookup"><span data-stu-id="2eaee-113">*Integer*</span></span>

<span data-ttu-id="2eaee-114">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="2eaee-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2eaee-115">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2eaee-115">Usage notes</span></span>

<span data-ttu-id="2eaee-116">Az **Gyűjtött adatkulcs neve** és a **Gyűjtött adatkulcs értéke** tulajdonság az ER-formátum **Sorrend** összetevőjéhez vagy **XML-elem** összetevőjéhez konfigurálható, amely a **Common\\File** alatt található, ahol a **Kimeneti részletek gyűjtése** be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="2eaee-116">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="2eaee-117">Ez a függvény **0** (nulla) értéket ad vissza, ha az aktuális **Common\\File** összetevő **Kimeneti részletek gyűjtése** beállítása ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="2eaee-117">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="2eaee-118">A `condition range` argumentumban a **„\*”** helyettesítő karakter használható tetszőleges többszörös karakter ábrázolására.</span><span class="sxs-lookup"><span data-stu-id="2eaee-118">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="2eaee-119">A `condition value` argumentumban a **„\*”** helyettesítő karakter használható tetszőleges többszörös karakter ábrázolására.</span><span class="sxs-lookup"><span data-stu-id="2eaee-119">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="2eaee-120">Példa</span><span class="sxs-lookup"><span data-stu-id="2eaee-120">Example</span></span>

<span data-ttu-id="2eaee-121">Ha többet szeretne megtudni e függvény használatáról, tekintse meg az [ER kimeneti adatformátum használata számlálás és összegzés céljából](tasks/er-format-counting-summing-1.md) című feladat-útmutatót (ez az **Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése** üzleti folyamat része).</span><span class="sxs-lookup"><span data-stu-id="2eaee-121">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2eaee-122">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2eaee-122">Additional resources</span></span>

[<span data-ttu-id="2eaee-123">Adatgyűjtési függvények</span><span class="sxs-lookup"><span data-stu-id="2eaee-123">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]