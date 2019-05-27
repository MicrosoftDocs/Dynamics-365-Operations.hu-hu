---
title: Tevékenységkapcsolat létrehozása – Követő
description: Lean termelési folyamat esetén a tevékenységek folyamata tevékenységkapcsolatokon keresztül kerül dokumentálásra.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e5e5844939e1eb40e31530c434c096c5b3be7abe
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562415"
---
# <a name="create-activity-relation-successor"></a>A tevékenységkapcsolat létrehozása: Követő

[!include [task guide banner](../../includes/task-guide-banner.md)]

Lean termelési folyamat esetén a tevékenységek folyamata tevékenységkapcsolatokon keresztül kerül dokumentálásra. Ez a felvétel bemutatja, hogyan hozhat létre tevékenységkapcsolatot.

Előfeltételek:

- Termelési folyamat és verzió vázlat módban. 

- Két olyan tevékenység, amelyek követik egymást a termelési folyamatban létrejött ugyan, de nem kapcsolódnak egymáshoz.


## <a name="find-the-production-flow-version"></a>Termelési folyamat verziójának megkeresése 
1. Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. A listában jelölje meg a kiválasztott sort.
5. Válasszon egy vázlatverziót a listából.
    * A tevékenységi kapcsolatok a termelési folyamat során a vázlatokhoz és az aktív verziókhoz is hozzáadhatók.  

## <a name="open-the-activity-overview"></a>Tevékenység áttekintésének megnyitása
1. Kattintson a Tevékenységek lehetőségre.
    * Vegye figyelembe, hogy a képernyő a termelési folyamat minden olyan tevékenységét megjeleníti, amely az Ön által használt termelési folyamatok verziójához tartozik.  

## <a name="add-a-successor"></a>Követő hozzáadása
1. Kattintson a Követő hozzáadása lehetőségre.
2. A Tevékenység mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. A kívánt rekord megkeresése és kijelölése a listán
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Jelölje be a Megszorítás jelölőnégyzetet.
6. Adjon meg egy számot a Megszorítás értéke mezőben.
    * A megszorítási idő a megelőző ütemezett vége (lejárati dátum és idő) és a követő ütemezett kezdete között ütemezendő idő.  
7. Írjon be egy értéket az Egységek mezőbe.
8. Írjon be egy számot a Ciklusidőarány mezőbe.
    * Ha mindkét tevékenység ugyanazon taktidőben fut, a ciklusidő aránya kötelezően 1. Ha a megelőző a követő tevékenység dupla sebességével fut, az arány kötelezően 2.   A termelési folyamat tevékenységeihez tartozó egyedi ciklusidők kiszámításához a ciklusidő-arányokat használjuk.  
9. Kattintson az OK gombra.
10. Zárja be a lapot.
11. Kattintson a GridPanel fülre.
12. Zárja be a lapot.
13. Frissítse a lapot..

