---
title: LIST ER-függvény
description: A témakör tájékoztatást nyújt a LIST Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: c7f8e701ec2836206d2299abba5e5b8542b4cf92
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683087"
---
# <a name="list-er-function"></a><span data-ttu-id="0edad-103">LIST ER-függvény</span><span class="sxs-lookup"><span data-stu-id="0edad-103">LIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0edad-104">A `LIST` függvény egy *Rekordlista* értéket ad vissza, amely a megadott argumentumokból létrehozott új rekordlistából áll.</span><span class="sxs-lookup"><span data-stu-id="0edad-104">The `LIST` function returns a *Record list* value that consists of a new list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="0edad-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="0edad-105">Syntax</span></span>

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a><span data-ttu-id="0edad-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="0edad-106">Arguments</span></span>

<span data-ttu-id="0edad-107">`record 1`: *Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="0edad-107">`record 1`: *Container (record)*</span></span>

<span data-ttu-id="0edad-108">Hivatkozás a *Rekord* adattípusú adatforrásra.</span><span class="sxs-lookup"><span data-stu-id="0edad-108">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="0edad-109">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="0edad-109">This argument is required.</span></span>

<span data-ttu-id="0edad-110">`record N`: *Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="0edad-110">`record N`: *Container (record)*</span></span>

<span data-ttu-id="0edad-111">Hivatkozás a *Rekord* adattípusú adatforrásra.</span><span class="sxs-lookup"><span data-stu-id="0edad-111">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="0edad-112">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="0edad-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="0edad-113">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="0edad-113">Return values</span></span>

<span data-ttu-id="0edad-114">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="0edad-114">*Record list*</span></span>

<span data-ttu-id="0edad-115">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="0edad-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0edad-116">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="0edad-116">Usage notes</span></span>

<span data-ttu-id="0edad-117">A létrehozott lista szerkezete csak azokat a mezőket tartalmazza, amelyek az argumentumban szereplő minden rekord struktúrájában láthatók.</span><span class="sxs-lookup"><span data-stu-id="0edad-117">The structure of the list that is created contains only the fields that are presented in the structure of every record that is mentioned in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="0edad-118">Példa</span><span class="sxs-lookup"><span data-stu-id="0edad-118">Example</span></span>

<span data-ttu-id="0edad-119">Adja meg a *Tároló* típus **1. rekord** adatforrását.</span><span class="sxs-lookup"><span data-stu-id="0edad-119">You enter data source **Record 1** of the *Container* type.</span></span> <span data-ttu-id="0edad-120">Ez az adatforrás a *Kiszámított mező* típus alábbi beágyazott mezőit tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="0edad-120">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="0edad-121">**Kód:** Ez a mező egy olyan kifejezést tartalmaz, amely a *Karakterlánc* típus értékét adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="0edad-121">**Code:** This field contains an expression that returns a value of the *String* type.</span></span>
- <span data-ttu-id="0edad-122">**Mennyiség:** Ez a mező egy olyan kifejezést tartalmaz, amely a *Valós* típus értékét adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="0edad-122">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>

<span data-ttu-id="0edad-123">Ezután adja meg a *Tároló* típus **2. rekord** adatforrását.</span><span class="sxs-lookup"><span data-stu-id="0edad-123">You then enter data source **Record 2** of the *Container* type.</span></span> <span data-ttu-id="0edad-124">Ez az adatforrás a *Kiszámított mező* típus alábbi beágyazott mezőit tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="0edad-124">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="0edad-125">**Mennyiség:** Ez a mező egy olyan kifejezést tartalmaz, amely a *Valós* típus értékét adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="0edad-125">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>
- <span data-ttu-id="0edad-126">**IsValid:** Ez a mező egy olyan kifejezést tartalmaz, amely a *Logikai* típus értékét adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="0edad-126">**IsValid:** This field contains an expression that returns a value of the *Boolean* type.</span></span>

<span data-ttu-id="0edad-127">Ebben az esetben a `LIST('Record 1', 'Record 2')` kifejezés egy új, két rekordot tartalmazó listát ad eredményül.</span><span class="sxs-lookup"><span data-stu-id="0edad-127">In this case, the expression `LIST('Record 1', 'Record 2')` returns a new list that contains two records.</span></span> <span data-ttu-id="0edad-128">A lista szerkezete a *valós* típus egyetlen **Mennyiség** mezőjéből áll, mivel ez a mező az egyetlen olyan mező, amely szerepel a hívott függvény minden argumentumában megjelenik.</span><span class="sxs-lookup"><span data-stu-id="0edad-128">The structure of this list consists of a single **Amount** field of the *Real* type, because this field is the only field that is presented in every argument of the called function.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0edad-129">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0edad-129">Additional resources</span></span>

[<span data-ttu-id="0edad-130">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="0edad-130">List functions</span></span>](er-functions-category-list.md)
