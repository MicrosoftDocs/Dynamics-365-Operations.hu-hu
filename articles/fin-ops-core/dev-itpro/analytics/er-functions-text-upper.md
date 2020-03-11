---
title: UPPER ER-függvény
description: A témakör tájékoztatást nyújt az UPPER Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 77854d645ba5b65a2819437af510fcd67be6d99d
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040940"
---
# <span data-ttu-id="61aea-103"><a name="UPPER">UPPER ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="61aea-103"><a name="UPPER">UPPER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61aea-104">Az `UPPER` függvény *Karakterlánc* értékként adja vissza a megadott karakterláncot, miután a program nagybetűssé alakította.</span><span class="sxs-lookup"><span data-stu-id="61aea-104">The `UPPER` function returns the specified text string as a *String* value after it has been converted to uppercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="61aea-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="61aea-105">Syntax</span></span>

```vb
UPPER (text )
```

## <a name="arguments"></a><span data-ttu-id="61aea-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="61aea-106">Arguments</span></span>

<span data-ttu-id="61aea-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="61aea-107">`text`: *String*</span></span>

<span data-ttu-id="61aea-108">A *Karakterlánc* típus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="61aea-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="61aea-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="61aea-109">Return values</span></span>

<span data-ttu-id="61aea-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="61aea-110">*String*</span></span>

<span data-ttu-id="61aea-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="61aea-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="61aea-112">Példa</span><span class="sxs-lookup"><span data-stu-id="61aea-112">Example</span></span>

<span data-ttu-id="61aea-113">Az `UPPER ("Sample")` a **"SAMPLE"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="61aea-113">`UPPER ("Sample")` returns **"SAMPLE"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="61aea-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="61aea-114">Additional resources</span></span>

[<span data-ttu-id="61aea-115">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="61aea-115">Text functions</span></span>](er-functions-category-text.md)
