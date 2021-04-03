---
title: FIRSTORNULL ER függvény
description: A témakör tájékoztatást nyújt a FIRSTORNULL Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 11/29/2019
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
ms.openlocfilehash: 53284333507ef1264d3eb66b0c7141eb69f32392
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564625"
---
# <a name="firstornull-er-function"></a><span data-ttu-id="c29d0-103">FIRSTORNULL ER függvény</span><span class="sxs-lookup"><span data-stu-id="c29d0-103">FIRSTORNULL ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c29d0-104">A `FIRSTORNULL` függvény a megadott lista első rekordját *Tároló (rekord)* értékként adja vissza, ha a rekord nem üres.</span><span class="sxs-lookup"><span data-stu-id="c29d0-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="c29d0-105">Ha a rekord üres, a függvény null *Tároló (rekord)* értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="c29d0-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="c29d0-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="c29d0-106">Syntax</span></span>

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="c29d0-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="c29d0-107">Arguments</span></span>

<span data-ttu-id="c29d0-108">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="c29d0-108">`list`: *Record list*</span></span>

<span data-ttu-id="c29d0-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="c29d0-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="c29d0-110">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="c29d0-110">Return values</span></span>

<span data-ttu-id="c29d0-111">*Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="c29d0-111">*Container (record)*</span></span>

<span data-ttu-id="c29d0-112">Az eredményül kapott rekordérték.</span><span class="sxs-lookup"><span data-stu-id="c29d0-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="c29d0-113">Példa</span><span class="sxs-lookup"><span data-stu-id="c29d0-113">Example</span></span>

<span data-ttu-id="c29d0-114">A `FIRSTORNULL(SPLIT("",1)).Value` kifejezés üres karakterláncot ad eredményül (**""**).</span><span class="sxs-lookup"><span data-stu-id="c29d0-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c29d0-115">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c29d0-115">Additional resources</span></span>

[<span data-ttu-id="c29d0-116">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="c29d0-116">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]