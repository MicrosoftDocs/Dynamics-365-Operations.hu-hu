---
title: Base64StringToContainer ER-függvény
description: A témakör tájékoztatást nyújt a Base64StringToContainer Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/14/2020
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 612590dacc1887b87677c12eddaef42660a7a154
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561542"
---
# <a name="base64stringtocontainer-er-function"></a><span data-ttu-id="b0345-103">Base64StringToContainer ER-függvény</span><span class="sxs-lookup"><span data-stu-id="b0345-103">Base64StringToContainer ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b0345-104">A `BASE64STRINGTOCONTAINER` [függvény](er-formula-language.md#functions) a megadott *Karakterlánc* típusú bemenetet *[Tároló](er-functions-category-container.md)* típusú adatelemmé konvertálja.</span><span class="sxs-lookup"><span data-stu-id="b0345-104">The `BASE64STRINGTOCONTAINER` [function](er-formula-language.md#functions) converts the specified input of the *String* type to a data item of the *[Container](er-functions-category-container.md)* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="b0345-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="b0345-105">Syntax</span></span>

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a><span data-ttu-id="b0345-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="b0345-106">Arguments</span></span>

<span data-ttu-id="b0345-107">`input`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="b0345-107">`input`: *String*</span></span>

<span data-ttu-id="b0345-108">A *Karakterlánc* típus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="b0345-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="b0345-109">Visszatérési értékek</span><span class="sxs-lookup"><span data-stu-id="b0345-109">Return values</span></span>

<span data-ttu-id="b0345-110">*Konténer*</span><span class="sxs-lookup"><span data-stu-id="b0345-110">*Container*</span></span>

<span data-ttu-id="b0345-111">A kapott bináris érték bináris nagy objektum (BLOB) formátumban.</span><span class="sxs-lookup"><span data-stu-id="b0345-111">The resulting binary value in binary large object (BLOB) format.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b0345-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b0345-112">Usage notes</span></span>

<span data-ttu-id="b0345-113">A „Paraméter érvénytelen” kivétel akkor lép fel, ha a bemeneti karakterlánc nem ad meg megfelelő Base64-csoportot a bináris-szöveg kódolási sémákhoz.</span><span class="sxs-lookup"><span data-stu-id="b0345-113">The "Parameter is not valid" exception is thrown if the input string doesn't provide a correct Base64 group of binary-to-text encoding schemes.</span></span>

## <a name="example"></a><span data-ttu-id="b0345-114">Példa</span><span class="sxs-lookup"><span data-stu-id="b0345-114">Example</span></span>

<span data-ttu-id="b0345-115">A következő adatforrás megadása a modell-hozzárendelésben:</span><span class="sxs-lookup"><span data-stu-id="b0345-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="b0345-116">A *Dynamics 365 for Operations / Enumeráció* típusú gyökér **DocuTypeGroupEnum** adatforrása, amey a **DocuTypeGroup** alkalmazás enumerációra hivatkozik</span><span class="sxs-lookup"><span data-stu-id="b0345-116">The root **DocuTypeGroupEnum** data source of the *Dynamics 365 for Operations / Enumeration* type that refers to the **DocuTypeGroup** application enumeration</span></span>
- <span data-ttu-id="b0345-117">A *Dynamics 365 for Operations / Táblarekordok* típus **Customer** adatforrása, amely a **CustTable** alkalmazástáblára hivatkozik</span><span class="sxs-lookup"><span data-stu-id="b0345-117">The root **Customer** data source of the *Dynamics 365 for Operations / Table records* type that refers to the **CustTable** application table</span></span>
- <span data-ttu-id="b0345-118">A *Számított mező* típus **\#Média** adatforrása, amely a következőképpen van beállítva:</span><span class="sxs-lookup"><span data-stu-id="b0345-118">The **\#Media** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="b0345-119">A **Vevő** adatforrás gyermek adatforrásaként van hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="b0345-119">It's added as a child data source of the **Customer** data source.</span></span>
    - <span data-ttu-id="b0345-120">A `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)` kifejezést tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b0345-120">It contains the expression `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.</span></span>

- <span data-ttu-id="b0345-121">A *Számított mező* típus **\#MediaAsBase64String** adatforrása, amely a következőképpen van beállítva:</span><span class="sxs-lookup"><span data-stu-id="b0345-121">The **\#MediaAsBase64String** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="b0345-122">A **Vevő\#Média** adatforrás gyermek adatforrásaként van hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="b0345-122">It's added as a child data source of the **Customer.'\#Media'** data source.</span></span>
    - <span data-ttu-id="b0345-123">A `Customer.'#Media'.'getFileContentAsBase64String()'` kifejezést tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b0345-123">It contains the expression `Customer.'#Media'.'getFileContentAsBase64String()'`.</span></span>

- <span data-ttu-id="b0345-124">A *Számított mező* típus **\#BlobFomBase64** adatforrása, amely a következőképpen van beállítva:</span><span class="sxs-lookup"><span data-stu-id="b0345-124">The **\#BlobFomBase64** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="b0345-125">A **Vevő\#Média** adatforrás gyermek adatforrásaként van hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="b0345-125">It's added as a child data source of the **Customer.'\#Media'** data source.</span></span>
    - <span data-ttu-id="b0345-126">A `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'` kifejezést tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b0345-126">It contains the expression `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.</span></span>

<span data-ttu-id="b0345-127">Ebben a példában a **\#MediaAsBase64String** adatforrás az aktuális médiamelléklet bináris tartalmát szövegként kódolja, amely a bináris-szöveg kódolási sémák Base64-csoportját képviseli.</span><span class="sxs-lookup"><span data-stu-id="b0345-127">In this example, the **\#MediaAsBase64String** data source encodes the binary content of the current media attachment as text that represents a Base64 group of binary-to-text encoding schemes.</span></span> <span data-ttu-id="b0345-128">A **\#BlobFomBase64** adatforrás dekódolja a Base64-karakterláncot, és BLOB-formátumú bináris értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="b0345-128">The **\#BlobFomBase64** data source decodes the Base64 string and returns a binary value in BLOB format.</span></span>

![Minta adatforrások az ER-modell-leképezés tervező oldalán](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a><span data-ttu-id="b0345-130">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b0345-130">Additional resources</span></span>

[<span data-ttu-id="b0345-131">Tárolófunkciók</span><span class="sxs-lookup"><span data-stu-id="b0345-131">Container functions</span></span>](er-functions-category-container.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]