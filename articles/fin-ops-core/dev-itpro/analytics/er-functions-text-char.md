---
title: CHAR ER-függvény
description: A témakör tájékoztatást nyújt a CHAR Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: d42afcf97690351763138fd9e16265aa104a6bc4
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915740"
---
# <span data-ttu-id="bbb80-103"><a name="CHAR">CHAR ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="bbb80-103"><a name="CHAR">CHAR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bbb80-104">A `CHAR` függvény olyan *Karakterlánc* értéket ad eredményül, amely egyetlen karaktert mutat be, amelyre a megadott Unicode szám hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="bbb80-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="bbb80-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="bbb80-105">Syntax</span></span>

```
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="bbb80-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="bbb80-106">Arguments</span></span>

<span data-ttu-id="bbb80-107">`number`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="bbb80-107">`number`: *Integer*</span></span>

<span data-ttu-id="bbb80-108">A várt egyetlen karakternek megfelelő szám.</span><span class="sxs-lookup"><span data-stu-id="bbb80-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="bbb80-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="bbb80-109">Return values</span></span>

<span data-ttu-id="bbb80-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="bbb80-110">*String*</span></span>

<span data-ttu-id="bbb80-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="bbb80-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bbb80-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="bbb80-112">Usage notes</span></span>

<span data-ttu-id="bbb80-113">A funkció által visszaadott karakterlánc a szülő **FÁJL** formátumelemben kiválasztott kódolástól függ.</span><span class="sxs-lookup"><span data-stu-id="bbb80-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="bbb80-114">A támogatott kódolások listájához lásd: [Kódolási osztály](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="bbb80-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="bbb80-115">Példa</span><span class="sxs-lookup"><span data-stu-id="bbb80-115">Example</span></span>

<span data-ttu-id="bbb80-116">A `CHAR (255)` a **"ÿ"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="bbb80-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bbb80-117">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="bbb80-117">Additional resources</span></span>

[<span data-ttu-id="bbb80-118">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="bbb80-118">Text functions</span></span>](er-functions-category-text.md)
