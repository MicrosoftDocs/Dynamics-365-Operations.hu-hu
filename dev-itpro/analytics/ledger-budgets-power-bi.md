---
title: "Tényleges és költségvetési Power BI-tartalom"
description: "Ez a témakör a Tényleges és költségvetési Power BI-tartalmat ismerteti. Leírja, hogy hogyan kell hozzáférni a tartalomcsomagban szereplő jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban."
author: ryansandness
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30T00:00:00.000Z
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 5d52cce3cccb16f0645d9de1832ebeffbfaf3a09
ms.contentlocale: hu-hu
ms.lasthandoff: 06/13/2017

---

# <a name="actual-vs-budget-power-bi-content"></a>Tényleges és költségvetési Power BI-tartalom

[!include[banner](../includes/banner.md)]


Ez a témakör a **Tényleges és költségvetési** Power BI-tartalmat ismerteti. Leírja, hogy hogyan kell hozzáférni Power BI-jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban. 

# <a name="overview"></a>Áttekintés

A **Tényleges és költségvetési** Power BI-tartalmat azoknak hoztuk létre, akik a valós és a költségvetési teljesítmény összevetéséért felelősek a szervezetnél. A **Tényleges és költségvetési** Power BI-tartalom a költségvetés-eltérésekbe nyújt betekintést. Az aktuális év költségvetését elemezheti számlakategória, költségvetési kód, fő számla, fő számla leírása vagy pénzügyi időszak szerint, hogy jobban megérthesse az esetleges eltérések okát. 

# <a name="accessing-the-power-bi-content"></a>Power BI-tartalom elérése
A Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás 2017 júliusi frissítésének használata esetén a **Tényleges és költségvetési** Power BI-tartalom a **Főkönyvi költségvetések és előrejelzések** és a **Pénzügyi igazgató** munkaterületen jelenik meg.

# <a name="reports-that-are-included-in-the-power-bi-content"></a>A Power BI-tartalomhoz tartozó jelentések
A következő táblázat ismerteti a **Tényleges és költségvetési** Power BI-tartalom egyes jelentésoldalain található mutatókat.

| Jelentés                      | Mutatók |
|-----------------------------|---------|
| Költségek – Tényleges - költségvetés | <ul><li>Az idei teljes kiadás</li><li>Költségvetés szerinti idei teljes kiadás</li></ul> |
| Bevétel - Tényleges és költségvetés  | <ul><li>Az idei teljes bevétel</li><li>Költségvetés szerinti idei teljes bevétel</li><ul> |
| Kiadás                     | <ul><li>Az idei teljes kiadás</li><li>Költségcél a költségvetési alapján </li><ul> |
| Bevétel                     | <ul><li>Az idei teljes bevétel</li><li>Bevételi cél a költségvetési alapján </li><ul> |
| Nettó árbevétel                  | <ul><li>Az idei nettó bevétel</li><li>Nettó bevételi cél a költségvetési alapján </li><ul> |

## <a name="extending-the-power-bi-content"></a>Power BI-tartalom kibővítése
A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban található tartalomcsomagok révén nagyszerű elemzési lehetőségeket nyújthat azoknak a személyeknek, akik nem jelentkeztek be a Microsoft Dynamics 365 szolgáltatásba. Ezek a tartalomcsomagok módosíthatók, hogy más jelentéseket vagy megjelenítéseket is tartalmazhassanak, majd a tartalomcsomagok elemzés céljából közzétehetők a Power BI.com-bérlőjénél. 

A **Tényleges és költségvetési** Power BI-tartalmat az LCS Megosztott eszközök könyvtárában találja. A tartalom letöltésére és szervezeténél való megvalósítására vonatkozó további információért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](power-bi-content-microsoft-partners.md). Ha meg szeretne tekinteni egy demót, amely bemutatja a Power BI-tartalmak megvalósítását, lásd a [Power BI-tartalom a Microsofttól és az Ön partnereitől a Dynamics Lifecycle Services szolgáltatásban](https://mix.office.com/watch/9puyb1b2xs1w) című részt (Office Mix).

# <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése

| Entitás                    | Tartalom |
|---------------------------|----------|
| Főkönyvi tevékenységek | Tranzakciós összegek a főkönyvbe |
| Költségvetési tevékenységek         | Tranzakciós összegek a költségvetési jegyzékbe |
| Fő számlák             | Fő számlák a jelentések szűréséhez |
| Pénzügyi naptárak          | Pénzügyi naptárak a jelentések szűréséhez |
| Főkönyvek                   | A jelenlegi főkönyvi jelentés szűréséhez használható főkönyvek |
| Költségvetési kódok              | Költségvetési kódok a jelentések szűréséhez |
| Jogi személyek            | A jelenlegi jogi személyre vonatkozó jelentés szűréséhez használható jogi személyek |

