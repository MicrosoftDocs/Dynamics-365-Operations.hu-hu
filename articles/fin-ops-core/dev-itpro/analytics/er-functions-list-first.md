---
title: FIRST ER-függvény
description: A témakör tájékoztatást nyújt a FIRST Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 4d10abcf15b93961bd2ba4aec22914825d9ac38c
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042090"
---
# <span data-ttu-id="dd850-103"><a name="FIRST">FIRST ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="dd850-103"><a name="FIRST">FIRST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dd850-104">A `FIRST` függvény a megadott lista első rekordját *Tároló (rekord)* értékként adja vissza, ha a lista nem üres.</span><span class="sxs-lookup"><span data-stu-id="dd850-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="dd850-105">Ha a lista üres, a függvény kivételt dob.</span><span class="sxs-lookup"><span data-stu-id="dd850-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="dd850-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="dd850-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="dd850-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="dd850-107">Arguments</span></span>

<span data-ttu-id="dd850-108">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="dd850-108">`list`: *Record list*</span></span>

<span data-ttu-id="dd850-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="dd850-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="dd850-110">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="dd850-110">Return values</span></span>

<span data-ttu-id="dd850-111">*Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="dd850-111">*Container (record)*</span></span>

<span data-ttu-id="dd850-112">Az eredményül kapott rekordérték.</span><span class="sxs-lookup"><span data-stu-id="dd850-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="dd850-113">1. példa</span><span class="sxs-lookup"><span data-stu-id="dd850-113">Example 1</span></span>

<span data-ttu-id="dd850-114">Az `FIRST(SPLIT("ABC",1)).Value` kifejezés az **„A”** szöveges értéket adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="dd850-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="dd850-115">2. példa</span><span class="sxs-lookup"><span data-stu-id="dd850-115">Example 2</span></span>

<span data-ttu-id="dd850-116">A `FIRST(SPLIT("",1)).Value` kifejezés futásidőben kivételt dob.</span><span class="sxs-lookup"><span data-stu-id="dd850-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dd850-117">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="dd850-117">Additional resources</span></span>

[<span data-ttu-id="dd850-118">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="dd850-118">List functions</span></span>](er-functions-category-list.md)
