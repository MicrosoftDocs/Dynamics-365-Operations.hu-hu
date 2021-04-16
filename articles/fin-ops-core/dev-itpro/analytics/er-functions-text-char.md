---
title: CHAR ER-függvény
description: A témakör tájékoztatást nyújt a CHAR Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
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
ms.openlocfilehash: a621328817171be7df0622507c84f5c6f6fe90a1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746435"
---
# <a name="char-er-function"></a><span data-ttu-id="e541f-103">CHAR ER-függvény</span><span class="sxs-lookup"><span data-stu-id="e541f-103">CHAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e541f-104">A `CHAR` függvény olyan *Karakterlánc* értéket ad eredményül, amely egyetlen karaktert mutat be, amelyre a megadott Unicode szám hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="e541f-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="e541f-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="e541f-105">Syntax</span></span>

```vb
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="e541f-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="e541f-106">Arguments</span></span>

<span data-ttu-id="e541f-107">`number`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="e541f-107">`number`: *Integer*</span></span>

<span data-ttu-id="e541f-108">A várt egyetlen karakternek megfelelő szám.</span><span class="sxs-lookup"><span data-stu-id="e541f-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="e541f-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="e541f-109">Return values</span></span>

<span data-ttu-id="e541f-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="e541f-110">*String*</span></span>

<span data-ttu-id="e541f-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="e541f-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e541f-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e541f-112">Usage notes</span></span>

<span data-ttu-id="e541f-113">A funkció által visszaadott karakterlánc a szülő **FÁJL** formátumelemben kiválasztott kódolástól függ.</span><span class="sxs-lookup"><span data-stu-id="e541f-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="e541f-114">A támogatott kódolások listájához lásd: [Kódolási osztály](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="e541f-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="e541f-115">Példa</span><span class="sxs-lookup"><span data-stu-id="e541f-115">Example</span></span>

<span data-ttu-id="e541f-116">A `CHAR (255)` a **"ÿ"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="e541f-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e541f-117">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e541f-117">Additional resources</span></span>

[<span data-ttu-id="e541f-118">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="e541f-118">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]