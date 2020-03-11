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
ms.openlocfilehash: d91caff1a1b89e060a16833e53f3647208ed3826
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041423"
---
# <span data-ttu-id="4ae88-103"><a name="GETCURRENTCOMPANY">GETCURRENTCOMPANY ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="4ae88-103"><a name="GETCURRENTCOMPANY">GETCURRENTCOMPANY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4ae88-104">A `GETCURRENTCOMPANY` függvény egy olyan *Karakterlánc* értéket ad vissza, amely annak a jogi személynek (vállalat) a kódját képviseli, amelybe egy felhasználó jelenleg be van jelentkezve.</span><span class="sxs-lookup"><span data-stu-id="4ae88-104">The `GETCURRENTCOMPANY` function returns a *String* value that represents the code for the legal entity (company) that a user is currently signed in to.</span></span>

## <a name="syntax"></a><span data-ttu-id="4ae88-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="4ae88-105">Syntax</span></span>

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a><span data-ttu-id="4ae88-106">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="4ae88-106">Return values</span></span>

<span data-ttu-id="4ae88-107">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="4ae88-107">*String*</span></span>

<span data-ttu-id="4ae88-108">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="4ae88-108">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="4ae88-109">Példa</span><span class="sxs-lookup"><span data-stu-id="4ae88-109">Example</span></span>

<span data-ttu-id="4ae88-110">A `GETCURRENTCOMPANY ()` az **USMF** értéket adja vissza a programban a **Contoso Entertainment System USA** vállalatba bejelentkezett felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="4ae88-110">`GETCURRENTCOMPANY ()` returns **USMF** for a user who is signed in to the **Contoso Entertainment System USA** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ae88-111">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="4ae88-111">Additional resources</span></span>

[<span data-ttu-id="4ae88-112">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="4ae88-112">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
