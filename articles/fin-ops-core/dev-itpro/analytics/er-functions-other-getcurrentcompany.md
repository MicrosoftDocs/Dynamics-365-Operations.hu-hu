---
title: GETCURRENTCOMPANY ER-függvény
description: A témakör tájékoztatást nyújt a GETCURRENTCOMPANY Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 7e3c164c6d54d8387eed5018219da5fd82c765c8
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744121"
---
# <a name="getcurrentcompany-er-function"></a><span data-ttu-id="47822-103">GETCURRENTCOMPANY ER-függvény</span><span class="sxs-lookup"><span data-stu-id="47822-103">GETCURRENTCOMPANY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="47822-104">A `GETCURRENTCOMPANY` függvény egy olyan *Karakterlánc* értéket ad vissza, amely annak a jogi személynek (vállalat) a kódját képviseli, amelybe egy felhasználó jelenleg be van jelentkezve.</span><span class="sxs-lookup"><span data-stu-id="47822-104">The `GETCURRENTCOMPANY` function returns a *String* value that represents the code for the legal entity (company) that a user is currently signed in to.</span></span>

## <a name="syntax"></a><span data-ttu-id="47822-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="47822-105">Syntax</span></span>

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a><span data-ttu-id="47822-106">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="47822-106">Return values</span></span>

<span data-ttu-id="47822-107">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="47822-107">*String*</span></span>

<span data-ttu-id="47822-108">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="47822-108">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="47822-109">Példa</span><span class="sxs-lookup"><span data-stu-id="47822-109">Example</span></span>

<span data-ttu-id="47822-110">A `GETCURRENTCOMPANY ()` az **USMF** értéket adja vissza a programban a **Contoso Entertainment System USA** vállalatba bejelentkezett felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="47822-110">`GETCURRENTCOMPANY ()` returns **USMF** for a user who is signed in to the **Contoso Entertainment System USA** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="47822-111">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="47822-111">Additional resources</span></span>

[<span data-ttu-id="47822-112">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="47822-112">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
