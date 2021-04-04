---
title: EMPTYRECORD ER-függvény
description: A témakör tájékoztatást nyújt az EMPTYRECORD Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 2d3c34cbff8551b84121201b9489250c07c7799e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563246"
---
# <a name="emptyrecord-er-function"></a><span data-ttu-id="c74e2-103">EMPTYRECORD ER-függvény</span><span class="sxs-lookup"><span data-stu-id="c74e2-103">EMPTYRECORD ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c74e2-104">Az `EMPTYRECORD` függvény egy nulla *Tároló (rekord)* értéket ad vissza, amely ugyanazzal a struktúrával rendelkezik, mint a megadott rekordlista vagy rekord.</span><span class="sxs-lookup"><span data-stu-id="c74e2-104">The `EMPTYRECORD` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="c74e2-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="c74e2-105">Syntax</span></span>

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a><span data-ttu-id="c74e2-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="c74e2-106">Arguments</span></span>

<span data-ttu-id="c74e2-107">`list`: *Rekordlista* vagy *Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="c74e2-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="c74e2-108">A *Rekordlista* vagy *Tároló (rekord)* típusú adatforrás érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="c74e2-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="c74e2-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="c74e2-109">Return values</span></span>

<span data-ttu-id="c74e2-110">*Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="c74e2-110">*Container (record)*</span></span>

<span data-ttu-id="c74e2-111">Az eredményül kapott rekordérték.</span><span class="sxs-lookup"><span data-stu-id="c74e2-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c74e2-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c74e2-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="c74e2-113">A null rekord olyan rekord, amelyben minden mezőhöz üres érték tartozik.</span><span class="sxs-lookup"><span data-stu-id="c74e2-113">A null record is a record where all fields have an empty value.</span></span> <span data-ttu-id="c74e2-114">Az üres érték **0** (nulla) a számok esetén, üres karakterlánc a karakterláncoknál stb.</span><span class="sxs-lookup"><span data-stu-id="c74e2-114">An empty value is **0** (zero) for numbers, an empty string for strings, and so on.</span></span>

## <a name="example"></a><span data-ttu-id="c74e2-115">Példa</span><span class="sxs-lookup"><span data-stu-id="c74e2-115">Example</span></span>

<span data-ttu-id="c74e2-116">A `EMPTYRECORD (SPLIT ("abc", 1))` új üres rekordot ad vissza, amelynek ugyanolyan szerkezete van, mint a `SPLIT` funkció által megjelenített listának.</span><span class="sxs-lookup"><span data-stu-id="c74e2-116">`EMPTYRECORD (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="c74e2-117">További tudnivalók: [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="c74e2-117">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c74e2-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c74e2-118">Additional resources</span></span>

[<span data-ttu-id="c74e2-119">Rekord függvények</span><span class="sxs-lookup"><span data-stu-id="c74e2-119">Record functions</span></span>](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]