---
title: NULLDATE ER-függvény
description: A témakör tájékoztatást nyújt a NULLDATE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: edf43cc19636f51387504a7d9da73d757d96e558
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744287"
---
# <a name="nulldate-er-function"></a><span data-ttu-id="12fbf-103">NULLDATE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="12fbf-103">NULLDATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="12fbf-104">A `NULLDATE` függvény egy *Dátum* értéket ad vissza, amely a **nulla** dátumot (1900. január 1.) jelöli.</span><span class="sxs-lookup"><span data-stu-id="12fbf-104">The `NULLDATE` function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span>

## <a name="syntax"></a><span data-ttu-id="12fbf-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="12fbf-105">Syntax</span></span>

```vb
NULLDATE () as 
```

## <a name="return-values"></a><span data-ttu-id="12fbf-106">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="12fbf-106">Return values</span></span>

<span data-ttu-id="12fbf-107">*Dátum*</span><span class="sxs-lookup"><span data-stu-id="12fbf-107">*Date*</span></span>

<span data-ttu-id="12fbf-108">Az eredményül kapott dátumérték.</span><span class="sxs-lookup"><span data-stu-id="12fbf-108">The resulting date value.</span></span>

## <a name="example-1"></a><span data-ttu-id="12fbf-109">1. példa</span><span class="sxs-lookup"><span data-stu-id="12fbf-109">Example 1</span></span>

<span data-ttu-id="12fbf-110">A `DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` a **nulla** dátumot (1900. január 1.) adja vissza **"1900-01-01"** értékként, a megadott egyéni formátumban.</span><span class="sxs-lookup"><span data-stu-id="12fbf-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` returns the **null** date, January 1, 1900, as **"1900-01-01"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="12fbf-111">2. példa</span><span class="sxs-lookup"><span data-stu-id="12fbf-111">Example 2</span></span>

<span data-ttu-id="12fbf-112">Az `IF( Invoice.DocumentDate = NULLDATE(), true, false)` kifejezés **Igaz** értéket ad vissza, ha a **DocumentDate** mező értéke a **nulla** dátumnak felel meg.</span><span class="sxs-lookup"><span data-stu-id="12fbf-112">The expression `IF( Invoice.DocumentDate = NULLDATE(), true, false)` returns **True** when the value of the **DocumentDate** field equals the **null** date.</span></span> <span data-ttu-id="12fbf-113">Ebben a példában a **Számla** a **Finance/Táblarekordok** típus Elektronikus jelentéskészítési (ER) adatforrása, és a CustInvoiceJour táblára hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="12fbf-113">In this example, **Invoice** is an Electronic reporting (ER) data source of the **Finance/Table records** type, and it refers to the CustInvoiceJour table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="12fbf-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="12fbf-114">Additional resources</span></span>

[<span data-ttu-id="12fbf-115">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="12fbf-115">Date and time functions</span></span>](er-functions-category-datetime.md)
