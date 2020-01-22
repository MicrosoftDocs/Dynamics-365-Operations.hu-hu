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
ms.openlocfilehash: a0b4c93a4705cd0e382b9b6c7af1d199beeceabe
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915993"
---
# <span data-ttu-id="92caa-103"><a name="GETCURRENTCOMPANY">GETCURRENTCOMPANY ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="92caa-103"><a name="GETCURRENTCOMPANY">GETCURRENTCOMPANY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="92caa-104">A `GETCURRENTCOMPANY` függvény egy olyan *Karakterlánc* értéket ad vissza, amely annak a jogi személynek (vállalat) a kódját képviseli, amelybe egy felhasználó jelenleg be van jelentkezve.</span><span class="sxs-lookup"><span data-stu-id="92caa-104">The `GETCURRENTCOMPANY` function returns a *String* value that represents the code for the legal entity (company) that a user is currently signed in to.</span></span>

## <a name="syntax"></a><span data-ttu-id="92caa-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="92caa-105">Syntax</span></span>

```
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a><span data-ttu-id="92caa-106">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="92caa-106">Return values</span></span>

<span data-ttu-id="92caa-107">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="92caa-107">*String*</span></span>

<span data-ttu-id="92caa-108">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="92caa-108">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="92caa-109">Példa</span><span class="sxs-lookup"><span data-stu-id="92caa-109">Example</span></span>

<span data-ttu-id="92caa-110">A `GETCURRENTCOMPANY ()` az **USMF** értéket adja vissza a programban a **Contoso Entertainment System USA** vállalatba bejelentkezett felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="92caa-110">`GETCURRENTCOMPANY ()` returns **USMF** for a user who is signed in to the **Contoso Entertainment System USA** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="92caa-111">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="92caa-111">Additional resources</span></span>

[<span data-ttu-id="92caa-112">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="92caa-112">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
