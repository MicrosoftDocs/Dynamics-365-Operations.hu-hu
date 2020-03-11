---
title: REVERSE ER-függvény
description: A témakör tájékoztatást nyújt a REVERSE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: a6134ae7eb1a8044cf906f2a8d02eb153522a6cf
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041929"
---
# <span data-ttu-id="e8cd8-103"><a name="REVERSE">REVERSE ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="e8cd8-103"><a name="REVERSE">REVERSE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e8cd8-104">A `REVERSE` függvény a megadott listát *Rekordlista* értékként adja vissza fordított rendezési sorrendben.</span><span class="sxs-lookup"><span data-stu-id="e8cd8-104">The `REVERSE` function returns the specified list as a *Record list* value in reversed sort order.</span></span>

## <a name="syntax"></a><span data-ttu-id="e8cd8-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="e8cd8-105">Syntax</span></span>

```vb
REVERSE (list)
```

## <a name="arguments"></a><span data-ttu-id="e8cd8-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="e8cd8-106">Arguments</span></span>

<span data-ttu-id="e8cd8-107">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="e8cd8-107">`list`: *Record list*</span></span>

<span data-ttu-id="e8cd8-108">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="e8cd8-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="e8cd8-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="e8cd8-109">Return values</span></span>

<span data-ttu-id="e8cd8-110">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="e8cd8-110">*Record list*</span></span>

<span data-ttu-id="e8cd8-111">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="e8cd8-111">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="e8cd8-112">1. példa</span><span class="sxs-lookup"><span data-stu-id="e8cd8-112">Example 1</span></span>

<span data-ttu-id="e8cd8-113">Ha megadja a *Számított mező* típusú **DS** adatforrást és az tartalmazza a `SPLIT ("C|B|A", "|")` kifejezést, akkor a `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` kifejezés a **„C”** szöveges értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="e8cd8-113">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` returns the text value **"C"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="e8cd8-114">2. példa</span><span class="sxs-lookup"><span data-stu-id="e8cd8-114">Example 2</span></span>

<span data-ttu-id="e8cd8-115">Ha **Szállító** a VendTable táblára hivatkozó Elektronikus jelentéskészítési (ER) adatforrásként van konfigurálva, akkor a `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` kifejezés megjeleníti a név szerinti csökkenő sorrendben rendezett szállítók listáját.</span><span class="sxs-lookup"><span data-stu-id="e8cd8-115">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` returns a list of vendors that is sorted by name in descending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e8cd8-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e8cd8-116">Additional resources</span></span>

[<span data-ttu-id="e8cd8-117">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="e8cd8-117">List functions</span></span>](er-functions-category-list.md)
