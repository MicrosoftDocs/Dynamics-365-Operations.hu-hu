--- 
title: "Termelési folyamat verziójának deaktiválása"
description: "Ha már nincs szükség egy aktív termelésifolyamat-verzióra, inaktiválható."
author: cvocph
manager: AnnBe
ms.date: 10/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 06daa5e7d2b8e88bca281dc9bcaa73927253553c
ms.contentlocale: hu-hu
ms.lasthandoff: 07/28/2017

---
# <a name="deactivate-a-production-flow-version"></a>Termelési folyamat verziójának deaktiválása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ha már nincs szükség egy aktív termelésifolyamat-verzióra, inaktiválható. A beállítás használata csak akkor ajánlott, ha az összes kanbanszabály és -tevékenység befejeződött, és nem lesznek újra aktiválva. Fontos megjegyezni, hogy a rendszer a termelésifolyamat-verzióhoz kapcsolódó összes kanbanszabály lejárati dátumát frissíti az aktuális dátummal és idővel. 

Egy aktív termelésifolyamat-verzió módosításához vegye fontolóra az aktív verzió lejárati dátumának beállítását, majd egy új verzió létrehozását. Ez lehetővé teszi a termelési műveletek folyatását az új verzió és a kapcsolódó kanbanszabályok előkészítésével párhuzamosan. 

Az aktív termelésifolyamat-verzió lejáratának kikényszerítéséhez be kell állítani egy lejárati dátumot. Ebben az értelemben az inaktiválás inkább kivétel, mint szabály. 

Az eljáráshoz szükség van egy termelési folyamatra, amelynek a verziója inaktiválható. Ezt csak akkor próbálja meg éles környezetben, ha biztos abban, hogy a verzió teljesen elavult.


## <a name="deactivate-a-production-flow-version"></a>Termelési folyamat verziójának deaktiválása
1. Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Keresse meg és jelölje ki a kívánt rekordot a listán.
5. Kattintson az Inaktiválás gombra.
    * Ne folytassa, ha nem teljesen biztos abban, hogy a termelési folyamat verziója elavult. Az OK gombra kattintva az összes aktív kanbanszabály lejár, és azonnal leáll a termelésifolyamat-verzió összes termelési és feltöltési tevékenysége.  
6. Kattintson az OK gombra.


