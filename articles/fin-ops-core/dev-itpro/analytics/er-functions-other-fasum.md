---
title: FA_SUM ER-függvény
description: A témakör tájékoztatást nyújt a FA_SUM Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: c31722537e2a6bae502800953939ca01da4527b9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567568"
---
# <a name="fa_sum-er-function"></a><span data-ttu-id="e0ee5-103">FA_SUM ER-függvény</span><span class="sxs-lookup"><span data-stu-id="e0ee5-103">FA_SUM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0ee5-104">A `FA_SUM` függvény egy *Tároló (rekord)* értéket ad vissza, amely a megadott tárgyieszköz-cikk, értékmodellkód és dátumperiódusok tárgyieszközösszegének adatait tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="e0ee5-104">The `FA_SUM` function returns a *Container (record)* value that consists of data for the fixed asset amounts for the specified fixed asset item, value model code, and period of dates.</span></span>

## <a name="syntax"></a><span data-ttu-id="e0ee5-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="e0ee5-105">Syntax</span></span>

```vb
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a><span data-ttu-id="e0ee5-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="e0ee5-106">Arguments</span></span>

<span data-ttu-id="e0ee5-107">`fixed asset code`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="e0ee5-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="e0ee5-108">Egy *Karakterlánc* érték, amely egy olyan tárgyieszköz-cikk kódját jelöli, amelyhez az egyenleg számítása történik.</span><span class="sxs-lookup"><span data-stu-id="e0ee5-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="e0ee5-109">`value model code`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="e0ee5-109">`value model code`: *String*</span></span>

<span data-ttu-id="e0ee5-110">Egy *Karakterlánc* érték, amely egy olyan értékmodell kódját jelöli, amelyhez az egyenleg számítása történik.</span><span class="sxs-lookup"><span data-stu-id="e0ee5-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="e0ee5-111">`start date`: *Dátum*</span><span class="sxs-lookup"><span data-stu-id="e0ee5-111">`start date`: *Date*</span></span>

<span data-ttu-id="e0ee5-112">Egy *Dátum* érték, amely a tárgyieszköz-összegek számítási időszakának kezdési dátumát jelzi.</span><span class="sxs-lookup"><span data-stu-id="e0ee5-112">A *Date* value that represents the start date of a period that the fixed asset amounts are calculated for.</span></span>

<span data-ttu-id="e0ee5-113">`end date`: *Dátum*</span><span class="sxs-lookup"><span data-stu-id="e0ee5-113">`end date`: *Date*</span></span>

<span data-ttu-id="e0ee5-114">Egy *Dátum* érték, amely a tárgyieszköz-összegek számítási időszakának befejezési dátumát jelzi.</span><span class="sxs-lookup"><span data-stu-id="e0ee5-114">A *Date* value that represents the end date of a period that the fixed asset amounts are calculated for.</span></span>

## <a name="return-values"></a><span data-ttu-id="e0ee5-115">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="e0ee5-115">Return values</span></span>

<span data-ttu-id="e0ee5-116">*Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="e0ee5-116">*Container (record)*</span></span>

<span data-ttu-id="e0ee5-117">Az eredményül kapott rekordérték.</span><span class="sxs-lookup"><span data-stu-id="e0ee5-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="e0ee5-118">Példa</span><span class="sxs-lookup"><span data-stu-id="e0ee5-118">Example</span></span>

<span data-ttu-id="e0ee5-119">A `FA_SUM ("COMP-000001", "Current", Date1, Date2)` a **COMP-000001** tárgyi eszköz adattárolóját adja vissza, amely fel van készítve az **Aktuális** értékmodellhez és a **Dátum1** és **Dátum2** közötti időszakhoz.</span><span class="sxs-lookup"><span data-stu-id="e0ee5-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` returns the data container for fixed asset **COMP-000001** that has been prepared for the **Current** value model and for a period from **Date1** to **Date2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e0ee5-120">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e0ee5-120">Additional resources</span></span>

[<span data-ttu-id="e0ee5-121">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="e0ee5-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]