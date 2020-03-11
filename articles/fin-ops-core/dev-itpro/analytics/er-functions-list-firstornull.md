---
title: FIRSTORNULL ER függvény
description: A témakör tájékoztatást nyújt a FIRSTORNULL Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 11/29/2019
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
ms.openlocfilehash: 86c8a0ae21ffeb6268efbbd198f7c709c2ad54f6
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042113"
---
# <span data-ttu-id="775be-103"><a name="FIRSTORNULL">FIRSTORNULL ER függvény</a></span><span class="sxs-lookup"><span data-stu-id="775be-103"><a name="FIRSTORNULL">FIRSTORNULL ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="775be-104">A `FIRSTORNULL` függvény a megadott lista első rekordját *Tároló (rekord)* értékként adja vissza, ha a rekord nem üres.</span><span class="sxs-lookup"><span data-stu-id="775be-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="775be-105">Ha a rekord üres, a függvény null *Tároló (rekord)* értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="775be-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="775be-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="775be-106">Syntax</span></span>

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="775be-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="775be-107">Arguments</span></span>

<span data-ttu-id="775be-108">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="775be-108">`list`: *Record list*</span></span>

<span data-ttu-id="775be-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="775be-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="775be-110">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="775be-110">Return values</span></span>

<span data-ttu-id="775be-111">*Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="775be-111">*Container (record)*</span></span>

<span data-ttu-id="775be-112">Az eredményül kapott rekordérték.</span><span class="sxs-lookup"><span data-stu-id="775be-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="775be-113">Példa</span><span class="sxs-lookup"><span data-stu-id="775be-113">Example</span></span>

<span data-ttu-id="775be-114">A `FIRSTORNULL(SPLIT("",1)).Value` kifejezés üres karakterláncot ad eredményül (**""**).</span><span class="sxs-lookup"><span data-stu-id="775be-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="775be-115">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="775be-115">Additional resources</span></span>

[<span data-ttu-id="775be-116">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="775be-116">List functions</span></span>](er-functions-category-list.md)
