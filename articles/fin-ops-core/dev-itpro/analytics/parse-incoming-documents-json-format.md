---
title: Bejövő dokumentumok elemzése JSON-formátumban
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a bejövő dokumentumok JavaScript Object Notation (JSON) formátumú elemzéséhez szükséges elektronikus jelentéskészítés (ER) formátumait.
author: kfend
ms.date: 05/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 4e598dc15b619c2f6a0525ea18c371484ca26fa4
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755154"
---
# <a name="parse-incoming-documents-in-json-format"></a><span data-ttu-id="6d165-103">Bejövő dokumentumok elemzése JSON-formátumban</span><span class="sxs-lookup"><span data-stu-id="6d165-103">Parse incoming documents in JSON format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="6d165-104">Az elektronikus jelentéskészítési (ER) formátumokat úgy tudja kialakítani, hogy elemzi a JavaScripten alapuló szöveges formátumú adatokat tartalmazó elektronikus dokumentumokat (más szóval a JavaScript Object Notation \[JSON\] formátumú fájlokat).</span><span class="sxs-lookup"><span data-stu-id="6d165-104">You can design Electronic reporting (ER) formats to parse incoming electronic documents that represent data in a text format that is based on JavaScript (in other words, files in JavaScript Object Notation \[JSON\] format).</span></span>

<span data-ttu-id="6d165-105">Ha további tájékoztatást szeretne erről a funkcióról, töltse le a fájlokat a következő táblázatban, majd a külső JSON-fájl feladat-útmutatójából származó adatok importálásához hozzon létre formátumkonfigurációt.</span><span class="sxs-lookup"><span data-stu-id="6d165-105">To learn more about this feature, download the files in the following table, and then play the ER Create a format configuration to import data from an external JSON file task guide.</span></span> <span data-ttu-id="6d165-106">Ez a feladat-útmutató azt mutatja be, hogyan lehet ER-formátummal elemezni egy bejövő JSON-fájl adatait az alkalmazásadatok frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="6d165-106">This task guide shows how an ER format can be used to parse an incoming JSON file to update application data.</span></span>

| <span data-ttu-id="6d165-107">Beosztás</span><span class="sxs-lookup"><span data-stu-id="6d165-107">Title</span></span>                                  | <span data-ttu-id="6d165-108">Fájlnév</span><span class="sxs-lookup"><span data-stu-id="6d165-108">File name</span></span> |
|----------------------------------------|-----------|
| <span data-ttu-id="6d165-109">ER-formátum konfigurációja</span><span class="sxs-lookup"><span data-stu-id="6d165-109">ER format configuration</span></span>                | [<span data-ttu-id="6d165-110">A szállítók trans_JSON.xml fájljának importálási formátuma</span><span class="sxs-lookup"><span data-stu-id="6d165-110">Format for importing vendors' trans_JSON.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |
| <span data-ttu-id="6d165-111">Minta a .csv formátumú bejövő fájlra</span><span class="sxs-lookup"><span data-stu-id="6d165-111">Sample of incoming file in .csv format</span></span> | [<span data-ttu-id="6d165-112">1099entries_JSON.txt</span><span class="sxs-lookup"><span data-stu-id="6d165-112">1099entries_JSON.txt</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |

## <a name="requirements"></a><span data-ttu-id="6d165-113">Követelmények</span><span class="sxs-lookup"><span data-stu-id="6d165-113">Requirements</span></span>

<span data-ttu-id="6d165-114">Mielőtt elvégzi a külső JSON-fájl feladat-útmutatójából származó adatok importálásához szükséges formátumkonfigurációt, teljesülnie kell a következő követelménynek:</span><span class="sxs-lookup"><span data-stu-id="6d165-114">Before you complete the ER Create a format configuration to import data from an external JSON file task guide, the following requirement must be met:</span></span>

- <span data-ttu-id="6d165-115">A JSON-fájlok szülőelemei csak objektumelemek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="6d165-115">Parent elements in the JSON file can be only object elements.</span></span>
- <span data-ttu-id="6d165-116">Egy objektum beágyazott elemének tulajdonságelemnek kell lennie ahhoz, hogy érvényes JSON-struktúrát hozzon létre.</span><span class="sxs-lookup"><span data-stu-id="6d165-116">Nested elements for an object should be property elements, so that a valid JSON structure is created.</span></span>
- <span data-ttu-id="6d165-117">A JSON-tömbök csak egy objektum tulajdonságelemeinek beágyazott elemeit tartalmazhatják.</span><span class="sxs-lookup"><span data-stu-id="6d165-117">JSON arrays can be only nested elements of the property elements of an object.</span></span>
- <span data-ttu-id="6d165-118">A JSON-tömbök csak JSON-objektumokat tartalmazhatnak.</span><span class="sxs-lookup"><span data-stu-id="6d165-118">JSON arrays can contain only JSON objects.</span></span> <span data-ttu-id="6d165-119">Nem tartalmazhatnak közvetlen karakterlánc/numerikus értékeket és beágyazott tömböket.</span><span class="sxs-lookup"><span data-stu-id="6d165-119">They can't contain direct string/numeric values and nested arrays.</span></span> <span data-ttu-id="6d165-120">Ezeknek a tömböknek az elemeit a program sorrendben elemzi, mivel azok a formátumban vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="6d165-120">Elements in these arrays will be parsed in order, as they are specified in the format.</span></span> <span data-ttu-id="6d165-121">Mindegyik JSON-objektumnál különböző beállításokat kell figyelembe venni.</span><span class="sxs-lookup"><span data-stu-id="6d165-121">Multiplicity settings on each JSON object will be considered.</span></span>

<span data-ttu-id="6d165-122">Ezenkívül be kell fejeznie a [ER Kötelező konfigurációk létrehozása külső fájlból történő adatok importálásához](tasks/er-required-configurations-import-data.md) feladat-útmutatót, ha még nem tette meg.</span><span class="sxs-lookup"><span data-stu-id="6d165-122">Additionally, you must complete the [ER Create required configurations to import data from an external file](tasks/er-required-configurations-import-data.md) task guide if you haven't already completed it.</span></span> <span data-ttu-id="6d165-123">A feladat-útmutató befejezéséhez töltse le a következő fájlt.</span><span class="sxs-lookup"><span data-stu-id="6d165-123">Download the following file to complete the task guide.</span></span>

| <span data-ttu-id="6d165-124">Beosztás</span><span class="sxs-lookup"><span data-stu-id="6d165-124">Title</span></span>                  | <span data-ttu-id="6d165-125">Fájlnév</span><span class="sxs-lookup"><span data-stu-id="6d165-125">File name</span></span> |
|------------------------|-----------|
| <span data-ttu-id="6d165-126">ER modell konfigurációja</span><span class="sxs-lookup"><span data-stu-id="6d165-126">ER model configuration</span></span> | [<span data-ttu-id="6d165-127">1099model.xml</span><span class="sxs-lookup"><span data-stu-id="6d165-127">1099model.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]