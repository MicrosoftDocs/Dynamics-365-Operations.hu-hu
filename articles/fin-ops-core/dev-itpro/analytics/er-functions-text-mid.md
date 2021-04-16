---
title: MID ER-függvény
description: A témakör tájékoztatást nyújt a MID Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 9a9ff3f1055f6757d6d4073dbb816773d8bfc8ba
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746267"
---
# <a name="mid-er-function"></a><span data-ttu-id="2f29f-103">MID ER-függvény</span><span class="sxs-lookup"><span data-stu-id="2f29f-103">MID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2f29f-104">A `MID` függvény olyan *Karakterlánc* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc adott pozíciójától kiindulva.</span><span class="sxs-lookup"><span data-stu-id="2f29f-104">The `MID` function returns a *String* value that presents the specified number of characters from the specified string, starting at the specified position.</span></span>

## <a name="syntax"></a><span data-ttu-id="2f29f-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="2f29f-105">Syntax</span></span>

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a><span data-ttu-id="2f29f-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="2f29f-106">Arguments</span></span>

<span data-ttu-id="2f29f-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="2f29f-107">`text`: *String*</span></span>

<span data-ttu-id="2f29f-108">Egy *Karakterlánc* érték, amely megadja, hogy milyen szövegből legyenek visszaadva karakterek.</span><span class="sxs-lookup"><span data-stu-id="2f29f-108">A *String* value that specifies the text to return characters from.</span></span>

<span data-ttu-id="2f29f-109">`starting position`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="2f29f-109">`starting position`: *Integer*</span></span>

<span data-ttu-id="2f29f-110">Egy *Egész* érték, amely megadja az első karakter pozícióját, amelyet a megadott szövegből vissza kell adni.</span><span class="sxs-lookup"><span data-stu-id="2f29f-110">An *Integer* value that specifies the position of the first character that must be returned from the specified text.</span></span>

<span data-ttu-id="2f29f-111">`number of characters`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="2f29f-111">`number of characters`: *Integer*</span></span>

<span data-ttu-id="2f29f-112">Egy *Egész* érték, amely megadja a visszaadni szánt karakterek számát, a megadott kezdőpozíciótól kiindulva.</span><span class="sxs-lookup"><span data-stu-id="2f29f-112">An *Integer* value that specifies the number of characters that must be returned, starting at the specified starting position.</span></span>

## <a name="return-values"></a><span data-ttu-id="2f29f-113">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="2f29f-113">Return values</span></span>

<span data-ttu-id="2f29f-114">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="2f29f-114">*String*</span></span>

<span data-ttu-id="2f29f-115">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="2f29f-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2f29f-116">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2f29f-116">Usage notes</span></span>

<span data-ttu-id="2f29f-117">Ha a `starting position` argumentum értéke kisebb, mint 0 (nulla), a visszaadott karakterek a megadott karakterlánc első pozíciójától számítanak.</span><span class="sxs-lookup"><span data-stu-id="2f29f-117">If the value of the `starting position` argument is less than 0 (zero), the characters that are returned are counted from the first position in the specified string.</span></span>

<span data-ttu-id="2f29f-118">Ha a `starting position` argumentum értéke meghaladja a megadott karakterlánc hosszát, üres karakterláncot ad eredményül.</span><span class="sxs-lookup"><span data-stu-id="2f29f-118">If the value of the `starting position` argument exceeds length of the specified string, an empty string is returned.</span></span>

## <a name="example"></a><span data-ttu-id="2f29f-119">Példa</span><span class="sxs-lookup"><span data-stu-id="2f29f-119">Example</span></span>

<span data-ttu-id="2f29f-120">A `MID ("Sample", 2, 3)` az **„amp”** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2f29f-120">`MID ("Sample", 2, 3)` returns **"amp"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2f29f-121">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2f29f-121">Additional resources</span></span>

[<span data-ttu-id="2f29f-122">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="2f29f-122">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]