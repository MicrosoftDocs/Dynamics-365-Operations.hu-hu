---
title: Munkafolyamatok beállítása költségekhez
description: Beállíthat egy munkafolyamatot, amelynek a használatával áttekintheti és jóváhagyhatja az utazások és a költségek dokumentumait.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86cadf7277fbb7e08dad4b5dc2a46e1c6ce5a888
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840961"
---
# <a name="set-up-workflows-for-expense"></a>Munkafolyamatok beállítása költségekhez

[!include [banner](../includes/banner.md)]

 Beállíthat egy munkafolyamatot, amelynek a használatával áttekintheti és jóváhagyhatja az utazások és a költségek dokumentumait. A dokumentumok, amelyekhez munkafolyamatokat lehet adni, többek között magukban foglalják a költségjelentéseket, az utazási igényléseket és a készpénzelőleg-igényléseket.

A munkafolyamat egy üzleti folyamatot jelent. Meghatározza, hogy hogyan halad végig egy dokumentum a rendszeren keresztül, és megmutatja, kinek kell elvégznie a feladatot és jóváhagynia a dokumentumot. A munkafolyamat-rendszer használata számos előnnyel jár a szervezeténél:

-   **Egységes folyamatok** — Meghatározhatja az egyes dokumentumok jóváhagyási folyamatát, például a beszerzési igénylésekét és költségjelentésekét. A munafolyamat-rendszer segítségével biztosítható, hogy a dokumentumok feldolgozása és jóváhagyása egységes és hatékony módon történjen.

-   A folyamat láthatósága – Nyomon követheti egy meghatározott munkafolyamat-példány állapotát, előzményeit és teljesítmény metrikáit. Ennek segítségével meghatározhatja, hogy kell-e módosításokat végezni a munkafolyamatban a hatékonyság növelésének érdekében.

-   Központi munkalista – A felhasználók megjeleníthetik a centralizált munkalistát, amelyben megnézhetik a hozzájuk rendelt munkafolyamat-feladatokat és jóváhagyásokat. 

**A létrehozható munkafolyamat-típusok**

Az alábbi táblázatban a **Költség** modulban létrehozható munkafolyamatok típusai szerepelnek.


|              <strong>Típus</strong>              |                   <strong>Típus</strong>                   |
|-------------------------------------------------|-----------------------------------------------------------------------|
|         <strong>Költségjelentés</strong>         |            Jóváhagyási munkafolyamatok létrehozása a költségjelentésekhez.             |
|  <strong>Költségjelentés automatikus feladása</strong>   |        Hozzon létre automatikus dokumentumfeladási munkafolyamatokat a költségjelentésekhez.        |
|       <strong>Költségsortétel</strong>        |     Jóváhagyási munkafolyamatok létrehozása a költségjelentések sortételeihez.      |
| <strong>Költségsortétel automatikus feladása</strong> | Automatikus feladási munkafolyamatok létrehozása a költségjelentések sortételeihez. |
|       <strong>Utazási igénylés</strong>       |          Jóváhagyási munkafolyamatok létrehozása az utazási igénylésekhez.           |
|      <strong>Készpénzelőleg-igénylés</strong>      |         Hozza létre a készpénzelőleg-igénylések jóváhagyási munkafolyamatait.          |
|        <strong>Áfa-visszaigénylés</strong>        | Hozzon létre munkafolyamatokat az áfa-visszaigénylések jóváhagyására.  |

