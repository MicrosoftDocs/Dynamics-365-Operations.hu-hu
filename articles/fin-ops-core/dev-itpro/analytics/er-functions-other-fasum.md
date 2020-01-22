---
title: FA_SUM ER-függvény
description: A témakör tájékoztatást nyújt a FA_SUM Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 32eb07689598a3b6c852f272b480106670b88cd0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916982"
---
# <span data-ttu-id="d3309-103"><a name="FA_SUM">FA_SUM ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="d3309-103"><a name="FA_SUM">FA_SUM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d3309-104">A `FA_SUM` függvény egy *Tároló (rekord)* értéket ad vissza, amely a megadott tárgyieszköz-cikk, értékmodellkód és dátumperiódusok tárgyieszközösszegének adatait tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="d3309-104">The `FA_SUM` function returns a *Container (record)* value that consists of data for the fixed asset amounts for the specified fixed asset item, value model code, and period of dates.</span></span>

## <a name="syntax"></a><span data-ttu-id="d3309-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="d3309-105">Syntax</span></span>

```
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a><span data-ttu-id="d3309-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="d3309-106">Arguments</span></span>

<span data-ttu-id="d3309-107">`fixed asset code`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="d3309-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="d3309-108">Egy *Karakterlánc* érték, amely egy olyan tárgyieszköz-cikk kódját jelöli, amelyhez az egyenleg számítása történik.</span><span class="sxs-lookup"><span data-stu-id="d3309-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="d3309-109">`value model code`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="d3309-109">`value model code`: *String*</span></span>

<span data-ttu-id="d3309-110">Egy *Karakterlánc* érték, amely egy olyan értékmodell kódját jelöli, amelyhez az egyenleg számítása történik.</span><span class="sxs-lookup"><span data-stu-id="d3309-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="d3309-111">`start date`: *Dátum*</span><span class="sxs-lookup"><span data-stu-id="d3309-111">`start date`: *Date*</span></span>

<span data-ttu-id="d3309-112">Egy *Dátum* érték, amely a tárgyieszköz-összegek számítási időszakának kezdési dátumát jelzi.</span><span class="sxs-lookup"><span data-stu-id="d3309-112">A *Date* value that represents the start date of a period that the fixed asset amounts are calculated for.</span></span>

<span data-ttu-id="d3309-113">`end date`: *Dátum*</span><span class="sxs-lookup"><span data-stu-id="d3309-113">`end date`: *Date*</span></span>

<span data-ttu-id="d3309-114">Egy *Dátum* érték, amely a tárgyieszköz-összegek számítási időszakának befejezési dátumát jelzi.</span><span class="sxs-lookup"><span data-stu-id="d3309-114">A *Date* value that represents the end date of a period that the fixed asset amounts are calculated for.</span></span>

## <a name="return-values"></a><span data-ttu-id="d3309-115">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="d3309-115">Return values</span></span>

<span data-ttu-id="d3309-116">*Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="d3309-116">*Container (record)*</span></span>

<span data-ttu-id="d3309-117">Az eredményül kapott rekordérték.</span><span class="sxs-lookup"><span data-stu-id="d3309-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="d3309-118">Példa</span><span class="sxs-lookup"><span data-stu-id="d3309-118">Example</span></span>

<span data-ttu-id="d3309-119">A `FA_SUM ("COMP-000001", "Current", Date1, Date2)` a **COMP-000001** tárgyi eszköz adattárolóját adja vissza, amely fel van készítve az **Aktuális** értékmodellhez és a **Dátum1** és **Dátum2** közötti időszakhoz.</span><span class="sxs-lookup"><span data-stu-id="d3309-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` returns the data container for fixed asset **COMP-000001** that has been prepared for the **Current** value model and for a period from **Date1** to **Date2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d3309-120">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d3309-120">Additional resources</span></span>

[<span data-ttu-id="d3309-121">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="d3309-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
