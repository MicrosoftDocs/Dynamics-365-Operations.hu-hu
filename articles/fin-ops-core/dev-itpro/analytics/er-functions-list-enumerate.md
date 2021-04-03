---
title: ENUMERATE ER-függvény
description: A témakör tájékoztatást nyújt az ENUMERATE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 0827fe33a548970c7673ac2ab830bb22d367c8cc
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567868"
---
# <a name="enumerate-er-function"></a><span data-ttu-id="28db7-103">ENUMERATE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="28db7-103">ENUMERATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="28db7-104">Az `ENUMERATE` függvény egy új *Rekordlista* értéket ad vissza, amely a megadott lista felsorolt rekordjaiból áll.</span><span class="sxs-lookup"><span data-stu-id="28db7-104">The `ENUMERATE` function returns a new *Record list* value that consists of enumerated records of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="28db7-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="28db7-105">Syntax</span></span>

```vb
ENUMERATE (list)
```

## <a name="arguments"></a><span data-ttu-id="28db7-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="28db7-106">Arguments</span></span>

<span data-ttu-id="28db7-107">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="28db7-107">`list`: *Record list*</span></span>

<span data-ttu-id="28db7-108">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="28db7-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="28db7-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="28db7-109">Return values</span></span>

<span data-ttu-id="28db7-110">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="28db7-110">*Record list*</span></span>

<span data-ttu-id="28db7-111">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="28db7-111">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="28db7-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="28db7-112">Usage notes</span></span>

<span data-ttu-id="28db7-113">A felsorolt rekordok listája a következő további elemeket jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="28db7-113">The list of enumerated records that is returned exposes the following additional elements:</span></span>

- <span data-ttu-id="28db7-114">A mezők rekordja (**Érték** összetevő)</span><span class="sxs-lookup"><span data-stu-id="28db7-114">The record of fields (**Value** component)</span></span>
- <span data-ttu-id="28db7-115">Az aktuális rekord index (**Szám** összetevő)</span><span class="sxs-lookup"><span data-stu-id="28db7-115">The current record index (**Number** component)</span></span>

## <a name="example"></a><span data-ttu-id="28db7-116">Példa</span><span class="sxs-lookup"><span data-stu-id="28db7-116">Example</span></span>

<span data-ttu-id="28db7-117">A következő ábrán az **Sorszámozott** adatforrás a szállítói rekordok sorszámozott listájaként jött létre a **Szállítók** adatforrásból, amely a VendTable táblára hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="28db7-117">In the following illustration, an **Enumerated** data source is created as an enumerated list of vendor records from the **Vendors** data source that refers to the VendTable table.</span></span>

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

<span data-ttu-id="28db7-118">A következő ábrán az Elektronikus jelentéskészítési (ER) formátum látható.</span><span class="sxs-lookup"><span data-stu-id="28db7-118">The following illustration shows the Electronic reporting (ER) format.</span></span> <span data-ttu-id="28db7-119">Ebben a formátumelrendezésben adatkötések jönnek létre a kimenet XML-formátumú előállításához.</span><span class="sxs-lookup"><span data-stu-id="28db7-119">In this format, data bindings are created to generate output in XML format.</span></span> <span data-ttu-id="28db7-120">A kimenet az egyes szállítókat sorszámozott csomópontként jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="28db7-120">This output presents individual vendors as enumerated nodes.</span></span>

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

<span data-ttu-id="28db7-121">Az alábbi ábrán a tervezett formátum futtatásának eredménye látható.</span><span class="sxs-lookup"><span data-stu-id="28db7-121">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a><span data-ttu-id="28db7-122">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="28db7-122">Additional resources</span></span>

[<span data-ttu-id="28db7-123">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="28db7-123">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]