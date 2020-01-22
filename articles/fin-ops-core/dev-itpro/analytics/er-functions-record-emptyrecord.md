---
title: EMPTYRECORD ER-függvény
description: A témakör tájékoztatást nyújt az EMPTYRECORD Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 1cf23f11fa92adfb7a050efd9c68e80e1bee621f
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916890"
---
# <span data-ttu-id="df806-103"><a name="EMPTYRECORD">EMPTYRECORD ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="df806-103"><a name="EMPTYRECORD">EMPTYRECORD ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="df806-104">Az `EMPTYRECORD` függvény egy nulla *Tároló (rekord)* értéket ad vissza, amely ugyanazzal a struktúrával rendelkezik, mint a megadott rekordlista vagy rekord.</span><span class="sxs-lookup"><span data-stu-id="df806-104">The `EMPTYRECORD` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="df806-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="df806-105">Syntax</span></span>

```
EMPTYRECORD (list)
```

## <a name="arguments"></a><span data-ttu-id="df806-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="df806-106">Arguments</span></span>

<span data-ttu-id="df806-107">`list`: *Rekordlista* vagy *Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="df806-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="df806-108">A *Rekordlista* vagy *Tároló (rekord)* típusú adatforrás érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="df806-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="df806-109">Visszatérési értékek</span><span class="sxs-lookup"><span data-stu-id="df806-109">Return values</span></span>

<span data-ttu-id="df806-110">*Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="df806-110">*Container (record)*</span></span>

<span data-ttu-id="df806-111">Az eredményül kapott rekordérték.</span><span class="sxs-lookup"><span data-stu-id="df806-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="df806-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="df806-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="df806-113">A null rekord olyan rekord, amelyben minden mezőhöz üres érték tartozik.</span><span class="sxs-lookup"><span data-stu-id="df806-113">A null record is a record where all fields have an empty value.</span></span> <span data-ttu-id="df806-114">Az üres érték **0** (nulla) a számok esetén, üres karakterlánc a karakterláncoknál stb.</span><span class="sxs-lookup"><span data-stu-id="df806-114">An empty value is **0** (zero) for numbers, an empty string for strings, and so on.</span></span>

## <a name="example"></a><span data-ttu-id="df806-115">Példa</span><span class="sxs-lookup"><span data-stu-id="df806-115">Example</span></span>

<span data-ttu-id="df806-116">A `EMPTYRECORD (SPLIT ("abc", 1))` új üres rekordot ad vissza, amelynek ugyanolyan szerkezete van, mint a `SPLIT` funkció által megjelenített listának.</span><span class="sxs-lookup"><span data-stu-id="df806-116">`EMPTYRECORD (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="df806-117">További tudnivalók: [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="df806-117">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="df806-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="df806-118">Additional resources</span></span>

[<span data-ttu-id="df806-119">Rekord függvények</span><span class="sxs-lookup"><span data-stu-id="df806-119">Record functions</span></span>](er-functions-category-record.md)
