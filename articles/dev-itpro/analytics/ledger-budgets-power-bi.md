---
title: "Tényleges és költségvetési Power BI-tartalom"
description: "Ez a témakör a Tényleges és költségvetési Power BI-tartalmat ismerteti. Leírja, hogy hogyan kell hozzáférni a tartalomcsomagban szereplő jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban."
author: ryansandness
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: aac6439bb54b3b9cab066b06c01763e880efef8e
ms.openlocfilehash: fa0c56f4773b9062d616772e2bca9a576ad37ce2
ms.contentlocale: hu-hu
ms.lasthandoff: 12/18/2017

---

# <a name="actual-vs-budget-power-bi-content"></a>Tényleges és költségvetési Power BI-tartalom

[!include [banner](../includes/banner.md)]

Ez a témakör a **Tényleges és költségvetési** Power BI-tartalmat ismerteti. Leírja, hogy hogyan kell hozzáférni Power BI-jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="overview"></a>Áttekintés

A **Tényleges és költségvetési** Power BI-tartalmat azoknak hoztuk létre, akik a valós és a költségvetési teljesítmény összevetéséért felelősek a szervezetnél. A **Tényleges és költségvetési** Power BI-tartalom a költségvetés-eltérésekbe nyújt betekintést. Az aktuális év költségvetését elemezheti számlakategória, költségvetési kód, fő számla, fő számla leírása vagy pénzügyi időszak szerint, hogy jobban megérthesse az esetleges eltérések okát.

## <a name="accessing-the-power-bi-content"></a>Power BI-tartalom elérése
A **Tényleges a költségvetéssel szemben** Power BI-tartalom jelentései a **Tényleges a költségvetéssel szemben** és a **Pénzügyi igazgató** munkaterületen jelennek meg.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>A Power BI-tartalomhoz tartozó jelentések
A következő táblázat ismerteti a **Tényleges és költségvetési** Power BI-tartalom egyes jelentésoldalain található mutatókat.

| Jelentés                      | Mutatók                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| Költségek – Tényleges - költségvetés | <ul><li>Az idei teljes kiadás</li><li>Költségvetés szerinti idei teljes kiadás</li></ul>  |
| Bevétel - Tényleges és költségvetés  | <ul><li>Az idei teljes bevétel</li><li>Költségvetés szerinti idei teljes bevétel</li><ul>     |
| Kiadás                     | <ul><li>Az idei teljes kiadás</li><li>Költségcél a költségvetési alapján</li><ul> |
| Bevétel                     | <ul><li>Az idei teljes bevétel</li><li>Bevételi cél a költségvetési alapján</li><ul>   |
| Nettó árbevétel                  | <ul><li>Az idei nettó bevétel</li><li>Nettó bevételi cél a költségvetési alapján</li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése

| Entitás                    | Tartalom                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| Főkönyvi tevékenységek | Tranzakciós összegek a főkönyvbe                                       |
| Költségvetési tevékenységek         | Tranzakciós összegek a költségvetési jegyzékbe                                      |
| Fő számlák             | Fő számlák a jelentések szűréséhez                                               |
| Pénzügyi naptárak          | Pénzügyi naptárak a jelentések szűréséhez                                            |
| Főkönyvek                   | A jelenlegi főkönyvi jelentés szűréséhez használható főkönyvek              |
| Költségvetési kódok              | Költségvetési kódok a jelentések szűréséhez                                                |
| Jogi személyek            | A jelenlegi jogi személyre vonatkozó jelentés szűréséhez használható jogi személyek |

