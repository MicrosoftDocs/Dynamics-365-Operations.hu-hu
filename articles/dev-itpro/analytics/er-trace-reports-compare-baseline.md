---
title: A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a kiindulási értékekkel
description: Ez a témakör ismerteti, hogyan hasonlíthatja össze a generált ER jelentések eredményeit a kiindulási jelentés értékekkel.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
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
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 7f7877ccaa0c45ab5f0032d6808280e3c47a43ca
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "317936"
---
# <a name="trace-generated-report-results-and-compare-them-with-baseline-values"></a>A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a kiindulási értékekkel

[!include[banner](../includes/banner.md)]

A kimenő elektronikus bizonylatokat létrehozó ER formátumok eredményei nyomon követhetők. Nyomkövetés létrehozásának bekapcsolásakor (ER felhasználó paraméter: **Futtatás hibakeresési módban**), új nyomon követés rekord jön létre az ER formátum végrehajtási naplóban, valahányszor egy ER jelentés fut. A következő adatok minden egyes létrehozott nyomkövetésben megtalálhatók:

- Ellenőrzési szabályok által generált összes figyelmeztetés
- Ellenőrzési szabályok által generált összes hiba
- Az összes létrehozott fájl, amely tárolva van mellékleteként a nyomkövetési bejegyzésnek

Egyéni kiindulási alkalmazásfájlok bármely ER formátumhoz tárolhatók. Fájlok kiindulási fájlnak számítanak, amikor leírják a várt eredményét a jelentéseknek, amelyek futnak. Ha kiindulási fájl érhető el egy ER formátumhoz, amely a nyomkövetés generálása bekapcsolva helyzetben volt futtatva, a nyomkövetés a korábban említett részletek mellett tárolja a létrehozott elektronikus dokumentum és a kiindulási fájl összehasonlításának eredményét. Egy kattintással lekérheti a létrehozott elektronikus dokumentumot és a kiindulási fájlt egy tömörített fájlban. Részletes összehasonlítás egy külső eszköz segítségével végezhető el, például Windiff.

A nyomkövetés elemezhetők annak az eldöntéséhez, hogy a generált elektronikus dokumentumok tartalmazzák-e a várt tartalmat. Megteheti, hogy ezt az értékelést a felhasználói elfogadás tesztelési (UAT) környezetben végzik el, az alapkód módosításakor (például amikor áttelepített egy új alkalmazáspéldányba, gyorsjavítás csomagokat telepített, vagy telepítette a kód módosításait). Ezzel a módszerrel biztosíthatja, hogy az értékelés nem befolyásolja a használt ER jelentések végrehajtását. Számos ER jelentésnél az értékelés felügyelet nélküli üzemmódban is megtehető.

Ezzel a funkcióval kapcsolatos további tudnivalókért játssza le: **ER Jelentések előállítása és eredmények összehasonlítása (1. rész)** és **ER Jelentések előállítása és eredmények összehasonlítása (2. rész)** útmutatókat, amelyek részei a következőnek: **7.5.4.3 Teszt informatikai szolgáltatások/megoldások (10679)** üzleti folyamat, valamint letölthetők innen: [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684). A feladatútmutatók elmagyarázza az ER keretrendszer konfigurálásának folyamatát, hogy kiindulási fájlok segítségével értékeljék ki az előállított elektronikus dokumentumokat.
