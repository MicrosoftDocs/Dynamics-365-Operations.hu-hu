---
title: Meglévő tevékenység hozzáadása termelési folyamat verziójához
description: A termelési folyamatok új verzióinak létrehozásakor lehetőség van a régebbi verziókhoz létrehozott tevékenységek hozzáadására az új verzióhoz.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityAddExisting, PlanActivityAddExistingLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f95958e57b1b1a93e43eb2cf02d2651ccb9587b6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429252"
---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a>Meglévő tevékenység hozzáadása termelési folyamat verziójához

[!include [banner](../../includes/banner.md)]

A termelési folyamatok új verzióinak létrehozásakor lehetőség van a régebbi verziókhoz létrehozott tevékenységek hozzáadására az új verzióhoz. Ez az eljárás azt mutatja be, hogyan lehet új verziót létrehozni egy meglévő termelési folyamathoz a tevékenységek másolása nélkül. A következő lépésben egy meglévő tevékenységet adunk az új verzióhoz. 

A feladathoz már létrehozott verzióval és tevékenységekkel rendelkező termelési folyamatra van szükség.


## <a name="create-a-new-production-flow-version"></a>Termelési folyamat új verziójának létrehozása
1. Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Kattintson a Szerkesztés lehetőségre.
5. A listában jelölje meg a kiválasztott sort.
6. Az Lejárati dátum mezőben adjon meg egy dátumot és időpontot.
    * Megjegyzés: egy új termelésifolyamat-verzió létrehozása előtt ellenőrizze az aktív verzió lejárati dátumát és időpontját. Az új verzió az érvényesség kezdő dátumával jön létre, amely a kijelölt verzió lejárati dátumához kapcsolódik.  
7. Kattintson a Hozzáadás gombra.
8. Válassza a Nem lehetőséget a Másolás verzióból mezőben.
    * Válassza a Nem lehetőséget, ha üres verzióval szeretne kezdeni, abban az esetben, ha a másolt verzió tevékenységeinek legtöbbje új tevékenységekre lesz cserélve. A változatlan tevékenységeket manuálisan adja hozzá a tevékenység űrlap Meglévő hozzáadása funkciójával.  
9. Válassza a Nem lehetőséget az Ismétlődő kanbanszabályok mezőben.
    * Ha a tevékenységeket nem másolja át az új verzióba, nincs lehetőség a kanbanszabályok átmásolására az új verzió létrehozásakor.   Ehelyett a helyettesítő kanban létrehozása funkciót használjuk a későbbiekben a kanbanszabály képernyőn a régi termelésifolyamat-verziójának kanbanszabályainak lecserélésére az új verzió a tevékenységeit használó kanbanszabályokra.  
10. Kattintson az OK gombra.
11. Keresse meg és jelölje ki a kívánt rekordot a listán.

## <a name="add-an-existing-activity"></a>Meglévő tevékenység hozzáadása
1. Kattintson a Tevékenységek lehetőségre.
2. Kattintson a Meglévő hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.
    * Keressen meg és jelöljön ki egy meglévő tevékenységet az új termelésifolyamat-verzióhoz való hozzáadáshoz.  Ne feledje, hogy a lista minden olyan tevékenységet megjelenít, amelyet a termelési folyamathoz hoztak létre, a folyamat összes korábbi verziójában.  
3. A Tevékenység mezőben adjon meg vagy válasszon ki egy értéket.
4. Kattintson az OK gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]