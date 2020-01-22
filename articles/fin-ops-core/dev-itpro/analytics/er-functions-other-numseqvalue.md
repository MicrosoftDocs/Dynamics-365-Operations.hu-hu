---
title: NUMSEQVALUE ER-függvény
description: A témakör tájékoztatást nyújt a NUMSEQVALUE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: d68784524a5639d8d447daa2cda940680d795542
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915832"
---
# <span data-ttu-id="62428-103"><a name="NUMSEQVALUE">NUMSEQVALUE ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="62428-103"><a name="NUMSEQVALUE">NUMSEQVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="62428-104">A `NUMSEQVALUE` függvény egy *Karakterlánc* értéket ad vissza, amely a megadott számsorozat, hatókör és hatókör-azonosító alapján egy számsorozat új generált értékét jelzi.</span><span class="sxs-lookup"><span data-stu-id="62428-104">The `NUMSEQVALUE` function returns a *String* value that represents the new generated value of a number sequence, based on the specified number sequence, scope, and scope ID.</span></span> <span data-ttu-id="62428-105">A hatókör-azonosító egyenlő a vállalati kóddal, amelyet az Elektronikus jelentéskészítési (ER) formátumot futtató kontextus biztosít.</span><span class="sxs-lookup"><span data-stu-id="62428-105">The scope ID equals the company code that is supplied by the context that the Electronic reporting (ER) format is run under.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="62428-106">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="62428-106">Syntax 1</span></span>

```
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a><span data-ttu-id="62428-107">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="62428-107">Syntax 2</span></span>

```
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a><span data-ttu-id="62428-108">Szintaxis 3</span><span class="sxs-lookup"><span data-stu-id="62428-108">Syntax 3</span></span>

```
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a><span data-ttu-id="62428-109">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="62428-109">Arguments</span></span>

<span data-ttu-id="62428-110">`number sequence code`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="62428-110">`number sequence code`: *String*</span></span>

<span data-ttu-id="62428-111">Szöveges érték, amely annak a számsorozatnak a kódját jelöli, amelyben az új érték szükséges.</span><span class="sxs-lookup"><span data-stu-id="62428-111">A text value that represents the code of the number sequence that a new value is required in.</span></span>

<span data-ttu-id="62428-112">`number sequence record ID`: *Int64*</span><span class="sxs-lookup"><span data-stu-id="62428-112">`number sequence record ID`: *Int64*</span></span>

<span data-ttu-id="62428-113">Az *Int64* érték a NumberSequenceTable tábla rekordjának rekordazonosítóját jelzi, amely annak a számsorozatnak a definícióját tartalmazza, amelyben az új érték szükséges.</span><span class="sxs-lookup"><span data-stu-id="62428-113">An *Int64* value that represents the record ID of a record in the NumberSequenceTable table that contains the definition of the number sequence that a new value is required in.</span></span>

<span data-ttu-id="62428-114">`scope type`: *Felsorolási érték*</span><span class="sxs-lookup"><span data-stu-id="62428-114">`scope type`: *Enum value*</span></span>

<span data-ttu-id="62428-115">Az **ERExpressionNumberSequenceScopeType** felsorolási értéke, amely meghatározza annak a számsorozatnak a hatókörét, amelyhez az új érték szükséges.</span><span class="sxs-lookup"><span data-stu-id="62428-115">An enumeration value of the **ERExpressionNumberSequenceScopeType** enumeration that defines the scope of the number sequence that a new value is required in.</span></span> <span data-ttu-id="62428-116">A rendelkezésre álló hatókörtípusok a **Megosztott**, a **Jogi entitás** és a **Vállalat**.</span><span class="sxs-lookup"><span data-stu-id="62428-116">The available scope types are **Shared**, **Legal entity**, and **Company**.</span></span>

<span data-ttu-id="62428-117">`scope ID`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="62428-117">`scope ID`: *String*</span></span>

<span data-ttu-id="62428-118">Egy *Karakterlánc* érték, amely a megadott hatókörtípus alapján azonosítja a hatókört.</span><span class="sxs-lookup"><span data-stu-id="62428-118">A *String* value that identifies the scope, based on the specified scope type.</span></span>

## <a name="return-values"></a><span data-ttu-id="62428-119">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="62428-119">Return values</span></span>

<span data-ttu-id="62428-120">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="62428-120">*String*</span></span>

<span data-ttu-id="62428-121">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="62428-121">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="62428-122">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="62428-122">Usage notes</span></span>

<span data-ttu-id="62428-123">A **Megosztott** hatókörtípus esetében egy üres karakterláncot adjon meg a hatókör-azonosítóként.</span><span class="sxs-lookup"><span data-stu-id="62428-123">For the **Shared** scope type, specify an empty string as the scope ID.</span></span>

<span data-ttu-id="62428-124">A **Vállalat** és a **Jogi személy** hatókörtípusoknál a vállalat azonosítóját adja meg a hatókör-azonosítóként.</span><span class="sxs-lookup"><span data-stu-id="62428-124">For the **Company** and **Legal entity** scope types, specify the company code as the scope ID.</span></span> <span data-ttu-id="62428-125">Ha ezeknél a hatókörtípusoknál egy üres karakterláncot ad meg a hatókör-azonosítóként, az aktuális vállalati azonosító lesz használatos.</span><span class="sxs-lookup"><span data-stu-id="62428-125">If you specify an empty string as the scope ID for these scope types, the current company code is used.</span></span>

<span data-ttu-id="62428-126">Az 1-es szintaxis használatakor a rendszer a **Vállalati** hatókörtípus számsorozatát kéri, és a vállalati kódot az a környezet adja, amely alatt az ER formátum fut.</span><span class="sxs-lookup"><span data-stu-id="62428-126">When syntax 1 is used, the number sequence is requested for the **Company** scope type, and the company code is supplied by the context that the ER format is run under.</span></span>

## <a name="example-1"></a><span data-ttu-id="62428-127">1. példa</span><span class="sxs-lookup"><span data-stu-id="62428-127">Example 1</span></span>

<span data-ttu-id="62428-128">Az ER-formátumában adja meg az **AskNumSeq** adatforrást a *Felhasználó által megadott paraméterek* típusaként.</span><span class="sxs-lookup"><span data-stu-id="62428-128">In your ER format, you define the **AskNumSeq** data source of the *User input parameter* type.</span></span> <span data-ttu-id="62428-129">Ez az adatforrás a **Leírás** kiterjesztett adattípusra (EDT) vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="62428-129">This data source refers to the **Description** extended data type (EDT).</span></span> <span data-ttu-id="62428-130">Ezután adja meg a **NumSeq** adatforrást a *Kiszámított mező* típushoz.</span><span class="sxs-lookup"><span data-stu-id="62428-130">Next, you define the **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="62428-131">Az adatforrás tartalmazza a `NUMSEQVALUE (AskNumSeq)` kifejezést.</span><span class="sxs-lookup"><span data-stu-id="62428-131">This data source contains the expression `NUMSEQVALUE (AskNumSeq)`.</span></span> <span data-ttu-id="62428-132">Amikor a **NumSeq** adatforrást hívják, az eredményül adott számsorozat új generált értékét adja vissza, amely futásidőben, a kódnak a párbeszédpanelen való beírásával került megadásra.</span><span class="sxs-lookup"><span data-stu-id="62428-132">When the **NumSeq** data source is called, it returns the new generated value of the number sequence that was specified at runtime by entering its code in the dialog box.</span></span> <span data-ttu-id="62428-133">A számsorozatot a **Vállalat** hatókörtípus igényli.</span><span class="sxs-lookup"><span data-stu-id="62428-133">The number sequence is requested for the **Company** scope type.</span></span> <span data-ttu-id="62428-134">A vállalati kódot az a kontextus biztosítja, amely alatt az ER-formátum fut.</span><span class="sxs-lookup"><span data-stu-id="62428-134">The company code is supplied by the context that the ER format is run under.</span></span>

## <a name="example-2"></a><span data-ttu-id="62428-135">2. példa</span><span class="sxs-lookup"><span data-stu-id="62428-135">Example 2</span></span>

<span data-ttu-id="62428-136">A következő adatforrások megadása a modell-hozzárendelésben történik:</span><span class="sxs-lookup"><span data-stu-id="62428-136">The following data sources are defined in your model mapping:</span></span>

- <span data-ttu-id="62428-137">A *Tábla* típus **LedgerParms** adatforrása.</span><span class="sxs-lookup"><span data-stu-id="62428-137">The **LedgerParms** data source of the *Table* type.</span></span> <span data-ttu-id="62428-138">Ez az adatforrás az LedgerParameters táblára hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="62428-138">This data source refers to the LedgerParameters table.</span></span>
- <span data-ttu-id="62428-139">A *Számított mező* típus **NumSeq** adatforrása.</span><span class="sxs-lookup"><span data-stu-id="62428-139">The **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="62428-140">Az adatforrás tartalmazza a `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)` kifejezést.</span><span class="sxs-lookup"><span data-stu-id="62428-140">This data source contains the expression `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.</span></span>

<span data-ttu-id="62428-141">Ha a **NumSeq** adatforrást hívják meg, az új létrehozott értékét ad vissza a számsorozatnak, amely a vállalathoz van beállítva a főkönyvi paraméterekben, amely a kontextust adja, amely alatt az ER-formátumot futtatják.</span><span class="sxs-lookup"><span data-stu-id="62428-141">When the **NumSeq** data source is called, it returns the new generated value of the number sequence that has been configured in the General ledger parameters for the company that supplies the context that the ER format is run under.</span></span> <span data-ttu-id="62428-142">Ez a számsorozat egyértelműen azonosítja naplókat, és kötegszámként viselkedik, amely összekapcsolja a tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="62428-142">This number sequence uniquely identifies journals and acts as a batch number that links the transactions together.</span></span>

## <a name="example-3"></a><span data-ttu-id="62428-143">3. példa</span><span class="sxs-lookup"><span data-stu-id="62428-143">Example 3</span></span>

<span data-ttu-id="62428-144">A következő adatforrások megadása a modell-hozzárendelésben történik:</span><span class="sxs-lookup"><span data-stu-id="62428-144">The following data sources are defined in your model mapping:</span></span>

- <span data-ttu-id="62428-145">A Microsoft Dynamics 365 Finance *felsorolási típus* **enumScope** adatforrása.</span><span class="sxs-lookup"><span data-stu-id="62428-145">The **enumScope** data source of the Microsoft Dynamics 365 Finance *enumeration* type.</span></span> <span data-ttu-id="62428-146">Ez az adatforrás az **ERExpressionNumberSequenceScopeType** felsorolásra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="62428-146">This data source refers to the **ERExpressionNumberSequenceScopeType** enumeration.</span></span>
- <span data-ttu-id="62428-147">A *Számított mező* típus **NumSeq** adatforrása.</span><span class="sxs-lookup"><span data-stu-id="62428-147">The **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="62428-148">Az adatforrás tartalmazza a `NUMSEQVALUE ("Gene_1", enumScope.Company, "")` kifejezést.</span><span class="sxs-lookup"><span data-stu-id="62428-148">This data source contains the expression `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.</span></span>

<span data-ttu-id="62428-149">Ha a **NumSeq** adatforrást hívják meg, az új létrehozott értékét ad vissza a **Gene\_1** számsorozatnak, amely a vállalathoz van beállítva, amely a kontextust adja, amely alatt az ER-formátumot futtatják.</span><span class="sxs-lookup"><span data-stu-id="62428-149">When the **NumSeq** data source is called, it returns the new generated value of the **Gene\_1** number sequence that has been configured for the company that supplies the context that the ER format is run under.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="62428-150">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="62428-150">Additional resources</span></span>

[<span data-ttu-id="62428-151">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="62428-151">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
