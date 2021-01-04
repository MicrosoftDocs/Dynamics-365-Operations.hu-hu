---
title: TABLENAME2ID ER-függvény
description: A témakör tájékoztatást nyújt a TABLENAME2ID Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a68a8e1f4afa378ab446eae12bc90cdb3aba8b19
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681158"
---
# <a name="tablename2id-er-function"></a><span data-ttu-id="6d974-103">TABLENAME2ID ER-függvény</span><span class="sxs-lookup"><span data-stu-id="6d974-103">TABLENAME2ID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6d974-104">A `TABLENAME2ID` függvény a megadott táblanév táblaazonosítóját adja vissza *Egész* értékként.</span><span class="sxs-lookup"><span data-stu-id="6d974-104">The `TABLENAME2ID` function returns a numeric representation of the table ID for the specified table name as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="6d974-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="6d974-105">Syntax</span></span>

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a><span data-ttu-id="6d974-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="6d974-106">Arguments</span></span>

<span data-ttu-id="6d974-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="6d974-107">`text`: *String*</span></span>

<span data-ttu-id="6d974-108">Érvényes táblanevet képviselő szöveges érték.</span><span class="sxs-lookup"><span data-stu-id="6d974-108">A text value that represents a valid table name.</span></span>

## <a name="return-values"></a><span data-ttu-id="6d974-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="6d974-109">Return values</span></span>

<span data-ttu-id="6d974-110">*Egész*</span><span class="sxs-lookup"><span data-stu-id="6d974-110">*Integer*</span></span>

<span data-ttu-id="6d974-111">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="6d974-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="6d974-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6d974-112">Usage notes</span></span>

<span data-ttu-id="6d974-113">Ennek a funkciónak a végrehajtása különböző eredményeket hozhat a Microsoft Dynamics 365 Finance különböző példányain, még akkor is, ha ugyanazt a vállalatnevet használják.</span><span class="sxs-lookup"><span data-stu-id="6d974-113">Execution of this function can have different results in different instances of Microsoft Dynamics 365 Finance, even if the same company name is used.</span></span>

## <a name="example"></a><span data-ttu-id="6d974-114">Példa</span><span class="sxs-lookup"><span data-stu-id="6d974-114">Example</span></span>

<span data-ttu-id="6d974-115">A `TABLENAME2ID ("Intrastat")` az **1510** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="6d974-115">`TABLENAME2ID ("Intrastat")` returns **1510**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6d974-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6d974-116">Additional resources</span></span>

[<span data-ttu-id="6d974-117">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="6d974-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
