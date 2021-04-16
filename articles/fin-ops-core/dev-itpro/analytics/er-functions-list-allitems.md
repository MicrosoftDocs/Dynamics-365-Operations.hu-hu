---
title: ALLITEMS ER-függvény
description: A témakör tájékoztatást nyújt az ALLITEMS Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 5ddcf989bdfd1d1f5d0a412a2ffefe0e3037ca79
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746723"
---
# <a name="allitems-er-function"></a><span data-ttu-id="c4c0f-103">ALLITEMS ER-függvény</span><span class="sxs-lookup"><span data-stu-id="c4c0f-103">ALLITEMS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4c0f-104">Az `ALLITEMS` függvény a memóriában lévő kiválasztásként fut, és egy új, összevont *Rekordlista* értéket ad eredményül rekordok listájaként, amely a megadott elérési útnak megfelelő összes elemet képviseli.</span><span class="sxs-lookup"><span data-stu-id="c4c0f-104">The `ALLITEMS` function runs as an in-memory selection and returns a new flattened *Record list* value as a list of records that represents all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="c4c0f-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="c4c0f-105">Syntax</span></span>

```vb
ALLITEMS (path)
```

## <a name="arguments"></a><span data-ttu-id="c4c0f-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="c4c0f-106">Arguments</span></span>

<span data-ttu-id="c4c0f-107">`path`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="c4c0f-107">`path`: *Record list*</span></span>

<span data-ttu-id="c4c0f-108">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="c4c0f-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="c4c0f-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="c4c0f-109">Return values</span></span>

<span data-ttu-id="c4c0f-110">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="c4c0f-110">*Record list*</span></span>

<span data-ttu-id="c4c0f-111">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="c4c0f-111">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c4c0f-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c4c0f-112">Usage notes</span></span>

<span data-ttu-id="c4c0f-113">Az elérési utat egy érvényes adatforrás útvonalaként kell megadni a *Rekordlista* adattípus adatforrásához.</span><span class="sxs-lookup"><span data-stu-id="c4c0f-113">The path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="c4c0f-114">Adatelemek (például az elérési út karakterlánc és dátum eleme) hibaüzenetet jelenítenek meg az Elektronikus jelentéskészítés (ER) kifejezésszerkesztőben tervezéskor.</span><span class="sxs-lookup"><span data-stu-id="c4c0f-114">Data elements such as the path string and date should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="c4c0f-115">Ezt a függvényt nem ajánlott olyan tranzakciós adatforrásokhoz használni, amelyek nagy mennyiségű adatot tartalmazhatnak.</span><span class="sxs-lookup"><span data-stu-id="c4c0f-115">We don't recommend that you use this function for transactional data sources that might contain a large volume of data.</span></span> <span data-ttu-id="c4c0f-116">Ehelyett érdemes az [ALLTEMSQUERY](er-functions-list-allitemsquery.md) függvényt használni.</span><span class="sxs-lookup"><span data-stu-id="c4c0f-116">Instead, consider using the [ALLTEMSQUERY](er-functions-list-allitemsquery.md) function.</span></span>

## <a name="example-1"></a><span data-ttu-id="c4c0f-117">1. példa</span><span class="sxs-lookup"><span data-stu-id="c4c0f-117">Example 1</span></span>

<span data-ttu-id="c4c0f-118">Ha megadja a `SPLIT("abcdef" , 2)` kifejezést **DS** adatforrásként, akkor a `COUNT( ALLITEMS (DS))` kifejezés a **3** értéket adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="c4c0f-118">If you enter `SPLIT("abcdef" , 2)` as data source **DS**, the expression `COUNT( ALLITEMS (DS))` returns **3**.</span></span>

## <a name="example-2"></a><span data-ttu-id="c4c0f-119">2. példa</span><span class="sxs-lookup"><span data-stu-id="c4c0f-119">Example 2</span></span>

<span data-ttu-id="c4c0f-120">Ha a **Szállító** értéket adja meg a *Rekordlista* adattípus adatforrásaként, amely a VendTable alkalmazástáblára hivatkozik, az `ALLITEMS (Vend.'<Relations'.ContactPerson)` kifejezés egy olyan összevont rekordlistát ad eredményül, amely tartalmazza a **ContactPerson** táblaszerkezetet, és minden olyan kapcsolattartót tartalmaz, amely a **ContactPerson.ContactForParty == VendTable.Party** objektumkapcsolat használatával hozzáférhető, és a hivatkozott szállítói tábla összes szállítója számára elérhető.</span><span class="sxs-lookup"><span data-stu-id="c4c0f-120">If you enter **Vend** as the data source of the *Record list* data type that refers to the VendTable application table, the expression `ALLITEMS (Vend.'<Relations'.ContactPerson)` returns a flattened list of records that has the **ContactPerson** table structure and contains all contact persons that can be accessed by using the **ContactPerson.ContactForParty == VendTable.Party** relation, and that is available for all vendors from the referenced vendor table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c4c0f-121">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c4c0f-121">Additional resources</span></span>

[<span data-ttu-id="c4c0f-122">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="c4c0f-122">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]