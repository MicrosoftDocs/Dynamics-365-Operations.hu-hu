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
ms.openlocfilehash: 7813b0c6002e47aef6a8c119c72728a49584401b
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041229"
---
# <span data-ttu-id="19e88-103"><a name="CHAR">CHAR ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="19e88-103"><a name="CHAR">CHAR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="19e88-104">A `CHAR` függvény olyan *Karakterlánc* értéket ad eredményül, amely egyetlen karaktert mutat be, amelyre a megadott Unicode szám hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="19e88-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="19e88-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="19e88-105">Syntax</span></span>

```vb
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="19e88-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="19e88-106">Arguments</span></span>

<span data-ttu-id="19e88-107">`number`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="19e88-107">`number`: *Integer*</span></span>

<span data-ttu-id="19e88-108">A várt egyetlen karakternek megfelelő szám.</span><span class="sxs-lookup"><span data-stu-id="19e88-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="19e88-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="19e88-109">Return values</span></span>

<span data-ttu-id="19e88-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="19e88-110">*String*</span></span>

<span data-ttu-id="19e88-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="19e88-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="19e88-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="19e88-112">Usage notes</span></span>

<span data-ttu-id="19e88-113">A funkció által visszaadott karakterlánc a szülő **FÁJL** formátumelemben kiválasztott kódolástól függ.</span><span class="sxs-lookup"><span data-stu-id="19e88-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="19e88-114">A támogatott kódolások listájához lásd: [Kódolási osztály](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="19e88-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="19e88-115">Példa</span><span class="sxs-lookup"><span data-stu-id="19e88-115">Example</span></span>

<span data-ttu-id="19e88-116">A `CHAR (255)` a **"ÿ"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="19e88-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="19e88-117">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="19e88-117">Additional resources</span></span>

[<span data-ttu-id="19e88-118">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="19e88-118">Text functions</span></span>](er-functions-category-text.md)
