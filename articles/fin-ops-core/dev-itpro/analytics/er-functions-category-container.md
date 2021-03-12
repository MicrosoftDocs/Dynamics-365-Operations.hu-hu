---
title: A tároló kategóriába tartozó ER-függvények listája
description: A témakör tájékoztatást nyújt az Elektronikus jelentéskészítésben (ER) támogatott tároló függvényekről.
author: NickSelin
manager: kfend
ms.date: 12/14/2020
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 46d1af85773f6c3d07865658c554dee74fae625f
ms.sourcegitcommit: e8a46e127d70986539c138b27a641bff6f6874d0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/15/2020
ms.locfileid: "4739082"
---
# <a name="list-of-er-functions-in-the-container-category"></a><span data-ttu-id="956bf-103">A tároló kategóriába tartozó ER-függvények listája</span><span class="sxs-lookup"><span data-stu-id="956bf-103">List of ER functions in the container category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="956bf-104">Az [Elektronikus jelentéskészítés (ER)](general-electronic-reporting.md) tároló [függvényei](er-formula-language.md#functions) a *Tároló* adattípusok adatforrásokon történő műveletek végrehajtására használhatók.</span><span class="sxs-lookup"><span data-stu-id="956bf-104">[Electronic reporting (ER)](general-electronic-reporting.md) container [functions](er-formula-language.md#functions) can be used to perform operations that involve data sources of the *Container* data type.</span></span> <span data-ttu-id="956bf-105">Ezek a műveletek akkor fordulnak elő, amikor a feldolgozási adatok bináris adatok gyűjteményét képviselik bináris nagy objektum (BLOB) formátumban.</span><span class="sxs-lookup"><span data-stu-id="956bf-105">These operations occur when the processing data represents a collection of binary data in binary large object (BLOB) format.</span></span> <span data-ttu-id="956bf-106">Ez a témakör ezeknek a függvényeknek az összefoglalása.</span><span class="sxs-lookup"><span data-stu-id="956bf-106">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="956bf-107">Támogatott függvények listája</span><span class="sxs-lookup"><span data-stu-id="956bf-107">List of supported functions</span></span>

| <span data-ttu-id="956bf-108">Függvény</span><span class="sxs-lookup"><span data-stu-id="956bf-108">Function</span></span> | <span data-ttu-id="956bf-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="956bf-109">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="956bf-110">Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="956bf-110">Base64StringToContainer</span></span>](er-functions-container-base64stringtocontainer.md) | <span data-ttu-id="956bf-111">Ez a függvény egy bináris tartalomból álló *Tároló* értéket ad vissza, amely abból a megadott ASCII-karakterláncból van dekódolva, amely a bináris-szöveg kódolási sémák Base64-csoportját képviseli.</span><span class="sxs-lookup"><span data-stu-id="956bf-111">This function returns a *Container* value that consists of binary content that is decoded from the specified ASCII string that represents a Base64 group of binary-to-text encoding schemes.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="956bf-112">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="956bf-112">Additional resources</span></span>

[<span data-ttu-id="956bf-113">Elektronikus jelentések áttekintése</span><span class="sxs-lookup"><span data-stu-id="956bf-113">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="956bf-114">Képletszerkesztő az Elektronikus jelentéskészítésben</span><span class="sxs-lookup"><span data-stu-id="956bf-114">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="956bf-115">Elektronikus jelentéskészítés képletének nyelve</span><span class="sxs-lookup"><span data-stu-id="956bf-115">Electronic reporting formula language</span></span>](er-formula-language.md)