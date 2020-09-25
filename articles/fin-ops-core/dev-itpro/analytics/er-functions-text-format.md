---
title: FORMAT ER-függvény
description: A témakör tájékoztatást nyújt a FORMAT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f3e8e5f6676c26b8d604ed950470463f04c0473
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743879"
---
# <a name="format-er-function"></a><span data-ttu-id="aad49-103">FORMAT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="aad49-103">FORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aad49-104">A `FORMAT` függvény a megadott karakterláncot egy *Karakterlánc* értékként adja vissza, miután az **%N** minden előfordulását az *N*. argumentummal helyettesítve formázza.</span><span class="sxs-lookup"><span data-stu-id="aad49-104">The `FORMAT` function returns the specified string as a *String* value after it has been formatted by substituting any occurrences of **%N** with the *N*th argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="aad49-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="aad49-105">Syntax</span></span>

```vb
FORMAT (string, argument 1[, argument 2, …, argument N])
```

## <a name="arguments"></a><span data-ttu-id="aad49-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="aad49-106">Arguments</span></span>

<span data-ttu-id="aad49-107">`string`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="aad49-107">`string`: *String*</span></span>

<span data-ttu-id="aad49-108">Hivatkozás olyan *Karakterlánc* típusú adatforrásra, amelyet formázni kell.</span><span class="sxs-lookup"><span data-stu-id="aad49-108">A reference to a data source of the *String* type that must be formatted.</span></span> <span data-ttu-id="aad49-109">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="aad49-109">This argument is required.</span></span>

<span data-ttu-id="aad49-110">`argument 1`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="aad49-110">`argument 1`: *String*</span></span>

<span data-ttu-id="aad49-111">Az első argumentum, amely a **%1** előfordulásainak lecserélésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="aad49-111">The first argument, which is used to replace occurrences of **%1**.</span></span> <span data-ttu-id="aad49-112">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="aad49-112">This argument is required.</span></span>

<span data-ttu-id="aad49-113">`argument N`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="aad49-113">`argument N`: *String*</span></span>

<span data-ttu-id="aad49-114">Az *N*. argumentum, amely a **%2**, **%3** stb. előfordulásainak lecserélésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="aad49-114">The *N*th argument, which is used to replace occurrences of **%2**, **%3**, and so on.</span></span> <span data-ttu-id="aad49-115">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="aad49-115">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="aad49-116">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="aad49-116">Return values</span></span>

<span data-ttu-id="aad49-117">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="aad49-117">*String*</span></span>

<span data-ttu-id="aad49-118">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="aad49-118">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="aad49-119">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="aad49-119">Usage notes</span></span>

<span data-ttu-id="aad49-120">Ha egy argumentum nem érhető el a paraméter számára, a paraméter a karakterláncban **„%N”** elemként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="aad49-120">If an argument isn't provided for a parameter, the parameter is returned as **"%N"** in the string.</span></span> <span data-ttu-id="aad49-121">A *Valós* típus értékeihez az alapértelmezett karakterlánc-konverzió két tizedesjegyre korlátozódik.</span><span class="sxs-lookup"><span data-stu-id="aad49-121">For values of the *Real* type, the default string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="aad49-122">Példa</span><span class="sxs-lookup"><span data-stu-id="aad49-122">Example</span></span>

<span data-ttu-id="aad49-123">A következő ábrán a **PaymentModel** adatforrás a **Vevő** összetevő használatával visszaadja a vevői rekordok listáját.</span><span class="sxs-lookup"><span data-stu-id="aad49-123">In the following illustration, the **PaymentModel** data source returns a list of customer records by using the **Customer** component.</span></span> <span data-ttu-id="aad49-124">A feldolgozás dátumértékét a **ProcessingDate** mező segítségével adja vissza.</span><span class="sxs-lookup"><span data-stu-id="aad49-124">It returns the processing date value by using the **ProcessingDate** field.</span></span>

<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>

<span data-ttu-id="aad49-125">A kijelölt vevőkre vonatkozó elektronikus fájlok létrehozására tervezett Elektronikus jelentéskészítés (ER) formátumban a **PaymentModel** adatforrásként van kijelölve, és ellenőrzi a munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="aad49-125">In the Electronic reporting (ER) format that is designed to generate an electronic file for selected customers, **PaymentModel** is selected as a data source, and it controls the process flow.</span></span> <span data-ttu-id="aad49-126">A felhasználó tájékoztatásul kivételt kap, amikor a kiválasztott vevő le van állítva a jelentés feldolgozásának dátumára.</span><span class="sxs-lookup"><span data-stu-id="aad49-126">If a selected customer is stopped for the date when the report is processed, an exception is thrown to notify the user.</span></span> <span data-ttu-id="aad49-127">Az ellenőrzés feldolgozásának ezen típusára vonatkozóan tervezett formula a következő forrásokat használhatja:</span><span class="sxs-lookup"><span data-stu-id="aad49-127">The formula that is designed for this type of processing control can use the following resources:</span></span>

- <span data-ttu-id="aad49-128">A SYS70894 címke, amely a következő szöveggel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="aad49-128">Label SYS70894, which has the following text:</span></span>

    - <span data-ttu-id="aad49-129">**A EN-US nyelvhez:** „Nothing to print”</span><span class="sxs-lookup"><span data-stu-id="aad49-129">**For the EN-US language:** "Nothing to print"</span></span>
    - <span data-ttu-id="aad49-130">**DE nyelvhez:** „Nichts zu drucken”</span><span class="sxs-lookup"><span data-stu-id="aad49-130">**For the DE language:** "Nichts zu drucken"</span></span>

- <span data-ttu-id="aad49-131">A SYS18389 címke, amely a következő szöveggel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="aad49-131">Label SYS18389, which has the following text:</span></span>

    - <span data-ttu-id="aad49-132">**A HU nyelvhez:** „A(z) %1 vevő le van állítva a következő esetében: %2.”</span><span class="sxs-lookup"><span data-stu-id="aad49-132">**For the EN-US language:** "Customer %1 is stopped for %2."</span></span>
    - <span data-ttu-id="aad49-133">**A DE nyelvhez:** "Debitor '%1' wird für %2 gesperrt."</span><span class="sxs-lookup"><span data-stu-id="aad49-133">**For the DE language:** "Debitor '%1' wird für %2 gesperrt."</span></span>

<span data-ttu-id="aad49-134">Íme a tervezhető kifejezés.</span><span class="sxs-lookup"><span data-stu-id="aad49-134">Here is the expression that can be designed.</span></span>

```vb
FORMAT (CONCATENATE (@"SYS70894", ". ", @"SYS18389"), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, "d"))
```

<span data-ttu-id="aad49-135">Ha a jelentés feldolgozása a **Litware Retail** vevőre vonatkozóan 2015. december 17-én folyik, az **EN-US** területi beállításban és az **EN-US** nyelvben ez a képlet a következő szöveget jeleníti meg, amely a felhasználó számára egy kivételre vonatkozó üzenetként jeleníthető meg:</span><span class="sxs-lookup"><span data-stu-id="aad49-135">If a report is processed for the **Litware Retail** customer on December 17, 2015, in the **EN-US** culture and the **EN-US** language, this formula returns the following text, which can be presented to the user as an exception message:</span></span>

<span data-ttu-id="aad49-136">*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*</span><span class="sxs-lookup"><span data-stu-id="aad49-136">*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*</span></span>

<span data-ttu-id="aad49-137">Ha ugyanazt a jelentést 2015. december 17-én a **Litware Retail** vevőre vonatkozóan a **DE** területi beállítással és a **DE** nyelven dolgozzák fel, ez a képlet a következő, eltérő dátumformátumot használó szöveget jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="aad49-137">If the same report is processed for the **Litware Retail** customer on December 17, 2015, in the **DE** culture and the **DE** language, the formula returns the following text, which uses a different date format:</span></span>

<span data-ttu-id="aad49-138">*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*</span><span class="sxs-lookup"><span data-stu-id="aad49-138">*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*</span></span>

>[!NOTE]
> <span data-ttu-id="aad49-139">A címkék ER-képleteinél a következő szintaxis kerül alkalmazásra:</span><span class="sxs-lookup"><span data-stu-id="aad49-139">The following syntax is applied in ER formulas for labels:</span></span>
>
> - <span data-ttu-id="aad49-140">**A Microsoft Dynamics 365 Finance alkalmazás erőforrásaiból származó címkék esetében:** **\@X**, ahol **X** a címkeazonosító az alkalmazásobjektum-fában (AOT)</span><span class="sxs-lookup"><span data-stu-id="aad49-140">**For labels from resources in the Microsoft Dynamics 365 Finance app:** **\@X**, where **X** is the label ID in the Application Object Tree (AOT)</span></span>
> - <span data-ttu-id="aad49-141">**Az ER-konfigurációkban található címkékhez:** **@"GER_LABEL:X"**, ahol **X** az ER-konfigurációban található címkeazonosító</span><span class="sxs-lookup"><span data-stu-id="aad49-141">**For labels that reside in ER configurations:** **@"GER_LABEL:X"**, where **X** is the label ID in the ER configuration</span></span>

## <a name="additional-resources"></a><span data-ttu-id="aad49-142">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="aad49-142">Additional resources</span></span>

[<span data-ttu-id="aad49-143">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="aad49-143">Text functions</span></span>](er-functions-category-text.md)
