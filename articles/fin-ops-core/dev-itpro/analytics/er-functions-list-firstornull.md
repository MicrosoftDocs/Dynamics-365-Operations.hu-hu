---
title: FIRSTORNULL ER függvény
description: A témakör tájékoztatást nyújt a FIRSTORNULL Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
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
ms.openlocfilehash: 1ccc094fc468470ffc857c729b6d8402796785d7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753216"
---
# <a name="firstornull-er-function"></a><span data-ttu-id="b9e7d-103">FIRSTORNULL ER függvény</span><span class="sxs-lookup"><span data-stu-id="b9e7d-103">FIRSTORNULL ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b9e7d-104">A `FIRSTORNULL` függvény a megadott lista első rekordját *Tároló (rekord)* értékként adja vissza, ha a rekord nem üres.</span><span class="sxs-lookup"><span data-stu-id="b9e7d-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="b9e7d-105">Ha a rekord üres, a függvény null *Tároló (rekord)* értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="b9e7d-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="b9e7d-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="b9e7d-106">Syntax</span></span>

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="b9e7d-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="b9e7d-107">Arguments</span></span>

<span data-ttu-id="b9e7d-108">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="b9e7d-108">`list`: *Record list*</span></span>

<span data-ttu-id="b9e7d-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="b9e7d-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="b9e7d-110">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="b9e7d-110">Return values</span></span>

<span data-ttu-id="b9e7d-111">*Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="b9e7d-111">*Container (record)*</span></span>

<span data-ttu-id="b9e7d-112">Az eredményül kapott rekordérték.</span><span class="sxs-lookup"><span data-stu-id="b9e7d-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="b9e7d-113">Példa</span><span class="sxs-lookup"><span data-stu-id="b9e7d-113">Example</span></span>

<span data-ttu-id="b9e7d-114">A `FIRSTORNULL(SPLIT("",1)).Value` kifejezés üres karakterláncot ad eredményül (**""**).</span><span class="sxs-lookup"><span data-stu-id="b9e7d-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b9e7d-115">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b9e7d-115">Additional resources</span></span>

[<span data-ttu-id="b9e7d-116">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="b9e7d-116">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]