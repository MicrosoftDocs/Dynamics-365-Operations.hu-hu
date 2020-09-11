---
title: A logikai kategóriába tartozó ER-függvények listája
description: A témakör tájékoztatást nyújt az Elektronikus jelentéskészítésben (ER) támogatott logikai függvényekről.
author: NickSelin
manager: kfend
ms.date: 08/19/2020
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
ms.openlocfilehash: e622778c60646e5cc84cd6e23a5d4954a0fe0bb3
ms.sourcegitcommit: 38ad6f791c3d5688a5dc201a234ba89f155f7f03
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/19/2020
ms.locfileid: "3705095"
---
# <a name="list-of-er-functions-in-the-logical-category"></a><span data-ttu-id="66cc3-103">A logikai kategóriába tartozó ER-függvények listája</span><span class="sxs-lookup"><span data-stu-id="66cc3-103">List of ER functions in the logical category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="66cc3-104">Az Elektronikus jelentéskészítés (ER) logikai függvényei segítségével logikai értékekkel dolgozhat, és egynél több összehasonlítást hajthat végre egyetlen kifejezésben, vagy több feltételt tesztelhet.</span><span class="sxs-lookup"><span data-stu-id="66cc3-104">Electronic reporting (ER) logical functions can be used to work with logical values to perform more than one comparison in a single expression or test multiple conditions.</span></span> <span data-ttu-id="66cc3-105">Ez a témakör ezeknek a függvényeknek az összefoglalása.</span><span class="sxs-lookup"><span data-stu-id="66cc3-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="66cc3-106">Támogatott függvények listája</span><span class="sxs-lookup"><span data-stu-id="66cc3-106">List of supported functions</span></span>

| <span data-ttu-id="66cc3-107">Funkció</span><span class="sxs-lookup"><span data-stu-id="66cc3-107">Function</span></span> | <span data-ttu-id="66cc3-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="66cc3-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="66cc3-109">És</span><span class="sxs-lookup"><span data-stu-id="66cc3-109">And</span></span>](er-functions-logical-and.md)                       | <span data-ttu-id="66cc3-110">Ez a függvény **IGAZ** *Logikai* értéket ad eredményül, ha a megadott feltételek mindegyike igaz.</span><span class="sxs-lookup"><span data-stu-id="66cc3-110">This function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="66cc3-111">Ellenkező esetben **HAMIS** *logikai* eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="66cc3-111">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="66cc3-112">Láda</span><span class="sxs-lookup"><span data-stu-id="66cc3-112">Case</span></span>](er-functions-logical-case.md)                     | <span data-ttu-id="66cc3-113">Ez a függvény kiértékeli a megadott kifejezés értékét a megadott alternatív beállításokkal, és visszaadja az első beállítás eredményét, amely megegyezik a megadott kifejezés értékével.</span><span class="sxs-lookup"><span data-stu-id="66cc3-113">This function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="66cc3-114">Ellenkező esetben a nem kötelező alapértelmezett eredményt adja vissza, ha az alapértelmezett eredmény a hívott függvény utolsó argumentumaként van megadva, amelyet nem előz meg beállítás.</span><span class="sxs-lookup"><span data-stu-id="66cc3-114">Otherwise, it returns an optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="66cc3-115">A visszaadott érték bármely támogatott adattípus értéke lehet.</span><span class="sxs-lookup"><span data-stu-id="66cc3-115">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="66cc3-116">Ha</span><span class="sxs-lookup"><span data-stu-id="66cc3-116">If</span></span>](er-functions-logical-if.md)                         | <span data-ttu-id="66cc3-117">A függvény az első megadott értéket adja vissza a megadott feltétel teljesülése esetén.</span><span class="sxs-lookup"><span data-stu-id="66cc3-117">This function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="66cc3-118">Ellenkező esetben a második megadott értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="66cc3-118">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="66cc3-119">A visszaadott érték bármely támogatott adattípus értéke lehet.</span><span class="sxs-lookup"><span data-stu-id="66cc3-119">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="66cc3-120">Nem</span><span class="sxs-lookup"><span data-stu-id="66cc3-120">Not</span></span>](er-functions-logical-not.md)                       | <span data-ttu-id="66cc3-121">Ez a függvény a megadott feltétel sztornírozott logikai értékét adja eredményül *logikai* értékként.</span><span class="sxs-lookup"><span data-stu-id="66cc3-121">This function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span> |
| [<span data-ttu-id="66cc3-122">Or</span><span class="sxs-lookup"><span data-stu-id="66cc3-122">Or</span></span>](er-functions-logical-or.md)                         | <span data-ttu-id="66cc3-123">Ez a függvény **HAMIS** *Logikai* értéket ad eredményül, ha a megadott feltételek mindegyike hamis.</span><span class="sxs-lookup"><span data-stu-id="66cc3-123">This function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="66cc3-124">Ez a függvény **IGAZ** *Logikai* értéket ad eredményül, ha a megadott feltételek bármelyike igaz.</span><span class="sxs-lookup"><span data-stu-id="66cc3-124">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span> |
| [<span data-ttu-id="66cc3-125">ValueIn</span><span class="sxs-lookup"><span data-stu-id="66cc3-125">ValueIn</span></span>](er-functions-logical-valuein.md)               | <span data-ttu-id="66cc3-126">Ez a függvény azt határozza meg, hogy a megadott bemenet megegyezik-e a megadott lista valamelyik megadott elemének bármilyen értékével.</span><span class="sxs-lookup"><span data-stu-id="66cc3-126">This function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="66cc3-127">A függvény *Logikai* **IGAZ** értéket ad eredményül, ha a megadott bemenet megegyezik a megadott kifejezésnek a megadott lista legalább egy rekordján való futtatásának eredményével.</span><span class="sxs-lookup"><span data-stu-id="66cc3-127">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="66cc3-128">Ellenkező esetben **HAMIS** *logikai* eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="66cc3-128">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="66cc3-129">ValueInLarge</span><span class="sxs-lookup"><span data-stu-id="66cc3-129">ValueInLarge</span></span>](er-functions-logical-valueinlarge.md)     | <span data-ttu-id="66cc3-130">Ez a függvény azt határozza meg, hogy a megadott *Int64* vagy *Egész szám* típusú bemenet megegyezik-e a megadott lista valamelyik megadott elemének bármilyen értékével.</span><span class="sxs-lookup"><span data-stu-id="66cc3-130">This function determines whether the specified input of the *Int64* or *Integer* type matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="66cc3-131">A függvény *Logikai* **IGAZ** értéket ad eredményül, ha a megadott bemenet megegyezik a megadott kifejezésnek a megadott lista legalább egy rekordján való futtatásának eredményével.</span><span class="sxs-lookup"><span data-stu-id="66cc3-131">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="66cc3-132">Ellenkező esetben **HAMIS** *logikai* eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="66cc3-132">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |


## <a name="additional-resources"></a><span data-ttu-id="66cc3-133">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="66cc3-133">Additional resources</span></span>

[<span data-ttu-id="66cc3-134">Elektronikus jelentések áttekintése</span><span class="sxs-lookup"><span data-stu-id="66cc3-134">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="66cc3-135">Képletszerkesztő az Elektronikus jelentéskészítésben</span><span class="sxs-lookup"><span data-stu-id="66cc3-135">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="66cc3-136">Elektronikus jelentéskészítés képletének nyelve</span><span class="sxs-lookup"><span data-stu-id="66cc3-136">Electronic reporting formula language</span></span>](er-formula-language.md)
