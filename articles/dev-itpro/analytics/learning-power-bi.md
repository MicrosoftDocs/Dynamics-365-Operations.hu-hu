---
title: Tanulás Power BI tartalom
description: Ez a témakör ismerteti a Tanulás Power BI-tartalmat.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a4ea4606f9987bc08565d43a1f05243acf88883c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553763"
---
# <a name="learning-power-bi-content"></a>Tanulás Power BI tartalom

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti a **Tanulás** Microsoft Power BI-tartalmat.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Jelentések, amelyek a Power BI-tartalomban szerepelnek

A **Tanulás** Power BI-tartalomban szereplő jelentések táblázatokkal és diagramokkal jelenítenek meg információkat. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés                | Tartalom |
|-----------------------|----------|
| Tanulás – áttekintés     | További jelentések összefoglalása |
| Tanfolyamelemzés       | Regisztráció hely szerint, résztvevő állapot szerint, tanfolyamok típus szerint vállalatonként és tanfolyamon való részvételt feladat szerint |
| Regisztráció elemzése | Regisztrációs lista |
| Tanfolyamtípusok          | Tanfolyamtípusok szakértelem szerint |
| Oktatóelemzés   | Tanfolyamok és oktatók aránya, oktatók száma, tanfolyamok oktatók szerint, tanfolyamok oktatónként, valamint tanfolyami napirend oktató szerint |
| Elérhető tanfolyamok       | Tanfolyamok listája |
| Tanfolyamok tervezés        | Tanfolyami napirend |

Az e jelentésekben szereplő diagramokat és csempéket szűrheti, a diagramokat és csempéket pedig rögzítheti az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lásd: [Irányítópult létrehozása és konfigurálása](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése

A **Tanulás** Power BI-tartalom jelentéseinek kitöltésére a következő adatok szolgálnak. Ez a táblázat megjeleníti azokat az entitásokat, amelyeken a tartalom alapul.

| Entitás           | Tartalom                                                         | Más entitásokkal való kapcsolatok |
|------------------|------------------------------------------------------------------|-----------------------------------|
| Naptáreltolás  | Naptáreltolások, részletes jelentések                                | Tanfolyami napirend, Tanfolyamrésztvevők |
| Cég          | Vállalatok a jelentések szűréséhez                                   | Tanfolyami napirend, Tanfolyamrésztvevők |
| Tanfolyam           | Tanfolyam, leírás, oktató neve, hely, szoba és állapot | Tanfolyami napirend, Tanfolyamrésztvevők, Tanfolyamkészség |
| Tanfolyami napirend    | Napirend, tanfolyam, kezdő és záró időpontok                          | Vállalat, naptáreltolás, dátum, tanfolyam |
| Tanfolyamrésztvevők | Név, állapot, feladat és regisztráció dátuma                         | Vállalat, Naptáreltolás, Dátum, Tanfolyam, Demográfia, Alkalmazás, Tanfolyam, Alkalmazott neve, Alkalmazott beosztása, Feladat, Beosztás |
| Tanfolyamkészség     | Szakértelem, szakértelem típusa és szintje                                     | Tanfolyam |
| Dátum             | Napok, hetek, hónapok és évek                                   | Tanfolyami napirend, Tanfolyamrésztvevők |
| Demográfia     | Születési idő, nemek, etnikaum és családi állapot         | Tanfolyami napirend, Tanfolyamrésztvevők |
| Alkalmazás       | Kezdő dátum, záró dátum és átállási dátum                        | Tanfolyami napirend, Tanfolyamrésztvevők |
| Munka              | Funkció, típus és a cím                                        | Tanfolyami napirend, Tanfolyamrésztvevők |
| Pozíció         | Beosztás, cím és teljes munkaidős egyenérték (FTE)                  | Tanfolyami napirend, Tanfolyamrésztvevők |
| Alkalmazott neve    | Keresztnév, vezetéknév és teljes név                             | Tanfolyamrésztvevők |
| Alkalmazott beosztása   | Cím és szolgálati idő dátuma                                         | Tanfolyamrésztvevők |
