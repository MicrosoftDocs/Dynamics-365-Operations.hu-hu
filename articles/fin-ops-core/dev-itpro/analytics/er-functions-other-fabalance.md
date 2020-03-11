---
title: FA_BALANCE ER-függvény
description: A témakör tájékoztatást nyújt a FA_BALANCE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 76a087157ae53e2c571654ade7383d7bd7a005c3
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041446"
---
# <span data-ttu-id="d7ca0-103"><a name="FA_BALANCE">FA_BALANCE ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="d7ca0-103"><a name="FA_BALANCE">FA_BALANCE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d7ca0-104">A `FA_BALANCE` függvény egy *Tároló (rekord)* értéket ad vissza, amely a megadott tárgyieszköz-cikk, értékmodellkód, jelentési év és jelentési dátum tárgyieszköz-egyenlegének adatait tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="d7ca0-104">The `FA_BALANCE` function returns a *Container (record)* value that consists of data for the fixed asset balance for the specified fixed asset item, value model code, reporting year, and reporting date.</span></span>

## <a name="syntax"></a><span data-ttu-id="d7ca0-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="d7ca0-105">Syntax</span></span>

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a><span data-ttu-id="d7ca0-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="d7ca0-106">Arguments</span></span>

<span data-ttu-id="d7ca0-107">`fixed asset code`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="d7ca0-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="d7ca0-108">Egy *Karakterlánc* érték, amely egy olyan tárgyieszköz-cikk kódját jelöli, amelyhez az egyenleg számítása történik.</span><span class="sxs-lookup"><span data-stu-id="d7ca0-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="d7ca0-109">`value model code`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="d7ca0-109">`value model code`: *String*</span></span>

<span data-ttu-id="d7ca0-110">Egy *Karakterlánc* érték, amely egy olyan értékmodell kódját jelöli, amelyhez az egyenleg számítása történik.</span><span class="sxs-lookup"><span data-stu-id="d7ca0-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="d7ca0-111">`reporting year`: *Felsorolási érték*</span><span class="sxs-lookup"><span data-stu-id="d7ca0-111">`reporting year`: *Enumeration value*</span></span>

<span data-ttu-id="d7ca0-112">Az **AssetYear** alkalmazás felsorolási értéke, amely meghatároz egy időszakot az egyenlegszámításhoz.</span><span class="sxs-lookup"><span data-stu-id="d7ca0-112">An enumeration value of the **AssetYear** application enumeration that defines a period for the balance calculation.</span></span>

<span data-ttu-id="d7ca0-113">`reporting date`: *Dátum*</span><span class="sxs-lookup"><span data-stu-id="d7ca0-113">`reporting date`: *Date*</span></span>

<span data-ttu-id="d7ca0-114">Egy *Dátum* érték, amely meghatározza az egyenleg kiszámításának dátumát.</span><span class="sxs-lookup"><span data-stu-id="d7ca0-114">A *Date* value that defines a date for the balance calculation.</span></span>

## <a name="return-values"></a><span data-ttu-id="d7ca0-115">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="d7ca0-115">Return values</span></span>

<span data-ttu-id="d7ca0-116">*Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="d7ca0-116">*Container (record)*</span></span>

<span data-ttu-id="d7ca0-117">Az eredményül kapott rekordérték.</span><span class="sxs-lookup"><span data-stu-id="d7ca0-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="d7ca0-118">Példa</span><span class="sxs-lookup"><span data-stu-id="d7ca0-118">Example</span></span>

<span data-ttu-id="d7ca0-119">A `FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` a **COMP-000001** tárgyieszköz-egyenlegek **Aktuális** értékmodellhez előkészített adattárolóját adja vissza az aktuális alkalmazás-munkamenet dátumán.</span><span class="sxs-lookup"><span data-stu-id="d7ca0-119">`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` returns the data container of balances for fixed asset **COMP-000001** that has been prepared for the **Current** value model on the current application session date.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d7ca0-120">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d7ca0-120">Additional resources</span></span>

[<span data-ttu-id="d7ca0-121">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="d7ca0-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
