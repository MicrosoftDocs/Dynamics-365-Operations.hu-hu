---
title: CONVERTCURRENCY ER-függvény
description: A témakör tájékoztatást nyújt a CONVERTCURRENCY Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: bf972c6c2cc798811a9fb3bd3a355ac6ffca5a60
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915947"
---
# <span data-ttu-id="71438-103"><a name="CONVERTCURRENCY">CONVERTCURRENCY ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="71438-103"><a name="CONVERTCURRENCY">CONVERTCURRENCY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="71438-104">A `CONVERTCURRENCY` függvény egy *Real* értéket ad vissza, ami a megadott forráspénzösszeg konvertálását képviseli az eredeti pénznemről a megadott cél pénznemre a megadott vállalat beállításainak használata segítségével a megadott időpontban.</span><span class="sxs-lookup"><span data-stu-id="71438-104">The `CONVERTCURRENCY` function returns a *Real* value that represents the result of converting the specified monetary amount from the specified source currency to the specified target currency by using the settings of the specified company on the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="71438-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="71438-105">Syntax</span></span>

```
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a><span data-ttu-id="71438-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="71438-106">Arguments</span></span>

<span data-ttu-id="71438-107">`amount`: *Egész* vagy *Valós*</span><span class="sxs-lookup"><span data-stu-id="71438-107">`amount`: *Integer* or *Real*</span></span>

<span data-ttu-id="71438-108">A konvertálni kívánt pénzösszeget jelölő numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="71438-108">A numeric value that represents the monetary amount that must be converted.</span></span>

<span data-ttu-id="71438-109">`source currency`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="71438-109">`source currency`: *String*</span></span>

<span data-ttu-id="71438-110">A forráspénznem kódja.</span><span class="sxs-lookup"><span data-stu-id="71438-110">The code of the source currency.</span></span>

<span data-ttu-id="71438-111">`target currency`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="71438-111">`target currency`: *String*</span></span>

<span data-ttu-id="71438-112">A célpénznem kódja.</span><span class="sxs-lookup"><span data-stu-id="71438-112">The code of the target currency.</span></span>

<span data-ttu-id="71438-113">`date`: *Dátum*</span><span class="sxs-lookup"><span data-stu-id="71438-113">`date`: *Date*</span></span>

<span data-ttu-id="71438-114">Egy *Dátum* érték, amely a konverzió árfolyamát meghatározó dátumot jelöli.</span><span class="sxs-lookup"><span data-stu-id="71438-114">A *Date* value that represents the date that is used to determine the exchange rate for the conversion.</span></span>

<span data-ttu-id="71438-115">`company`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="71438-115">`company`: *String*</span></span>

<span data-ttu-id="71438-116">Egy *Karakterlánc* érték, amely egy olyan vállalat kódját jelöli, amely a konvertáláshoz használt beállításokat szolgáltatja.</span><span class="sxs-lookup"><span data-stu-id="71438-116">A *String* value that represents the code of a company that supplies the settings that are used for the conversion.</span></span>

## <a name="return-values"></a><span data-ttu-id="71438-117">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="71438-117">Return values</span></span>

<span data-ttu-id="71438-118">*Valós*</span><span class="sxs-lookup"><span data-stu-id="71438-118">*Real*</span></span>

<span data-ttu-id="71438-119">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="71438-119">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="71438-120">Példa</span><span class="sxs-lookup"><span data-stu-id="71438-120">Example</span></span>

<span data-ttu-id="71438-121">A `CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` egy euró egyenértékét jeleníti meg USA-dollárban az aktuális munkameneti napon a **DEMF** vállalat beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="71438-121">`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` returns the equivalent of one euro in US dollars on the current session date, based on settings for the **DEMF** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="71438-122">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="71438-122">Additional resources</span></span>

[<span data-ttu-id="71438-123">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="71438-123">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
