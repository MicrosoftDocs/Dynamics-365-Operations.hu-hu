---
title: Jelentések készítése tartalom nyers XML-kódként való hozzáadásával
description: Elektronikus jelentési (ER) formátumokat tervezhet kimenő dokumentumok XML-formátumú előállításához.
author: NickSelin
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 160f27f4f44ab6982addb7294db889e2a8dbfcfbc03f7849548c44364b070aa9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749680"
---
# <a name="generate-reports-by-adding-content-as-raw-xml"></a>Jelentések készítése tartalom nyers XML-kódként való hozzáadásával

[!include[banner](../includes/banner.md)]

Használhatja az új **Nyers XML** formátum elemet elektronikus jelentési (ER) formátumok kimenő dokumentumok XML-formátumú előállításához. Bizonyos esetekben előfordulhat, hogy szeretné nyers XML-adatok hozzáadása ezeket a jelentéseket, a következő okok valamelyikéből:

- A nyers XML használata kényelmesebb a jelentés eredeti tervezésére és karbantartásához, mert az XML-szerkezetet automatikusan létre lehet hozni egy futásidejű kifejezés végrehajtásával. Többszörös kötéseket emiatt nem kell a tervezéskor több formátumelemhez meghatározni. Akkor lehetséges, ha az éppen használt adatforrások tartalmaznak információkat, amelyek a jelentés előállításakor XML-elemek létrehozásához használhatók.
- Nincs semmilyen más módszer, amellyel korábban már kapott, és a rendszerben tárolt XML-tartalommal tölthető lenne fel a jelentés. Például a létrehozott XML-válasznak előfordulhat, hogy tartalmaznia kell a korábban elküldött XML-kérés tartalmát.
- Nincs más módszer, amelynek a használatával lehetne karaktereket beszúrni a generált dokumentumba a numerikus kódjuk alapján. Bizonyos nyelvek és karakterek esetében az ilyen típus nem létezik. Példák a görög betű rhó (ρ) és a HTML-entitás kódok, például \&eacute; az egy *e*, amelynek ékezete van (é).

> [!NOTE]
> Ne feledje, hogy a keretrendszer nem ellenőrzi, hogy **Nyers XML** formátum segítségével a generált dokumentumba kerülő XML-tartalom helyes-e.

A funkcióval kapcsolatos további tudnivalókért játssza le az **ER Nyers XML-adatok használata XML-jelentések létrehozásához (1. rész: Adatmodell tervezése)** és **ER Nyers XML-adatok használata XML-jelentések létrehozásához (2. rész: Jelentés tervezése és futtatása)** feladatútmutatókat, amelyek részei a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamatnak, és letölthetők innen: [Microsoft letöltőközpont](https://go.microsoft.com/fwlink/?linkid=874684). A feladatútmutató tájékoztatást ad az eljárásról, amellyel az ER formátum konfigurálható nyers XML-adatok beszúrására az előállított fájlokba.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]