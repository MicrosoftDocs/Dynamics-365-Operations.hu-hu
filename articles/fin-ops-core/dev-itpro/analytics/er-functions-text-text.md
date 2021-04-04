---
title: TEXT ER-függvény
description: A témakör tájékoztatást nyújt a TEXT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 5da7375020be827f432ba97740da37abe48962fc
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560061"
---
# <a name="text-er-function"></a><span data-ttu-id="515f3-103">TEXT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="515f3-103">TEXT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="515f3-104">A `TEXT` függvény a megadott számot egy *Karakterlánc* értékként adja vissza, miután az aktuális alkalmazás példányának kiszolgálója területi beállításainak megfelelően formázott szöveges karakterlánccá alakítja.</span><span class="sxs-lookup"><span data-stu-id="515f3-104">The `TEXT` function returns the specified number as a *String* value after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span>

## <a name="syntax"></a><span data-ttu-id="515f3-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="515f3-105">Syntax</span></span>

```vb
TEXT (number)
```

## <a name="arguments"></a><span data-ttu-id="515f3-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="515f3-106">Arguments</span></span>

<span data-ttu-id="515f3-107">`number`: *Egész* vagy *Valós*</span><span class="sxs-lookup"><span data-stu-id="515f3-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="515f3-108">Olyan szám, amelyet szöveges karakterlánccá kell konvertálni.</span><span class="sxs-lookup"><span data-stu-id="515f3-108">A number that must be converted to a text string.</span></span>

## <a name="return-values"></a><span data-ttu-id="515f3-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="515f3-109">Return values</span></span>

<span data-ttu-id="515f3-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="515f3-110">*String*</span></span>

<span data-ttu-id="515f3-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="515f3-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="515f3-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="515f3-112">Usage notes</span></span>

<span data-ttu-id="515f3-113">A *Valós* típus értékeihez a karakterlánc-konverzió két tizedesjegyre korlátozódik.</span><span class="sxs-lookup"><span data-stu-id="515f3-113">For values of the *Real* type, the string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="515f3-114">Példa</span><span class="sxs-lookup"><span data-stu-id="515f3-114">Example</span></span>

<span data-ttu-id="515f3-115">Ha a Microsoft Dynamics 365 Finance példány kiszolgáló területi beállítása **EN-US**, a `TEXT (NOW ())` a jelenlegi Finance munkamenet dátumát (2015. december 17.) **"12/17/2015 07:59:23 AM"** szöveges karakterláncként adja vissza.</span><span class="sxs-lookup"><span data-stu-id="515f3-115">If the server locale of the Microsoft Dynamics 365 Finance instance is defined as **EN-US**, `TEXT (NOW ())` returns the current Finance session date, December 17, 2015, as the text string **"12/17/2015 07:59:23 AM"**.</span></span> <span data-ttu-id="515f3-116">A `TEXT (1/3)` a **"0.33"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="515f3-116">`TEXT (1/3)` returns **"0.33"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="515f3-117">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="515f3-117">Additional resources</span></span>

[<span data-ttu-id="515f3-118">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="515f3-118">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]