---
title: Bejövő dokumentumok elemzése JSON-formátumban
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a bejövő dokumentumok JavaScript Object Notation (JSON) formátumú elemzéséhez szükséges elektronikus jelentéskészítés (ER) formátumait.
author: kfend
manager: AnnBe
ms.date: 05/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 92ef83bc1783b00a4d7d9739ca1c17e863c7ff44
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185267"
---
# <a name="parse-incoming-documents-in-json-format"></a>Bejövő dokumentumok elemzése JSON-formátumban

[!include[banner](../includes/banner.md)]

Az elektronikus jelentéskészítési (ER) formátumokat úgy tudja kialakítani, hogy elemzi a JavaScripten alapuló szöveges formátumú adatokat tartalmazó elektronikus dokumentumokat (más szóval a JavaScript Object Notation \[JSON\] formátumú fájlokat).

Ha további tájékoztatást szeretne erről a funkcióról, töltse le a fájlokat a következő táblázatban, majd a külső JSON-fájl feladat-útmutatójából származó adatok importálásához hozzon létre formátumkonfigurációt. Ez a feladat-útmutató azt mutatja be, hogyan lehet ER-formátummal elemezni egy bejövő JSON-fájl adatait az alkalmazásadatok frissítéséhez.

| Beosztás                                  | Fájlnév |
|----------------------------------------|-----------|
| ER-formátum konfigurációja                | [A szállítók trans_JSON.xml fájljának importálási formátuma](https://go.microsoft.com/fwlink/?linkid=874111) |
| Minta a .csv formátumú bejövő fájlra | [1099entries_JSON.txt](https://go.microsoft.com/fwlink/?linkid=874111) |

## <a name="requirements"></a>Követelmények

Mielőtt elvégzi a külső JSON-fájl feladat-útmutatójából származó adatok importálásához szükséges formátumkonfigurációt, teljesülnie kell a következő követelménynek:

- A JSON-fájlok szülőelemei csak objektumelemek lehetnek.
- Egy objektum beágyazott elemének tulajdonságelemnek kell lennie ahhoz, hogy érvényes JSON-struktúrát hozzon létre.
- A JSON-tömbök csak egy objektum tulajdonságelemeinek beágyazott elemeit tartalmazhatják.
- A JSON-tömbök csak JSON-objektumokat tartalmazhatnak. Nem tartalmazhatnak közvetlen karakterlánc/numerikus értékeket és beágyazott tömböket. Ezeknek a tömböknek az elemeit a program sorrendben elemzi, mivel azok a formátumban vannak meghatározva. Mindegyik JSON-objektumnál különböző beállításokat kell figyelembe venni.

Ezenkívül be kell fejeznie a [Kötelező konfigurációk létrehozása külső fájlból történő adatok importálásához az elektronikus jelentéskészítéshez](tasks/er-required-configurations-import-data.md) feladat-útmutatót, ha még nem tette meg. A feladat-útmutató befejezéséhez töltse le a következő fájlt.

| Beosztás                  | Fájlnév |
|------------------------|-----------|
| ER modell konfigurációja | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=874111) |
