---
title: Helyettesítési kanbanszabály létrehozása
description: Ez az eljárás egy meglévő kanbanszabály egy új kanbanszabállyal történő lecserélésére irányul az adott dátumon.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2db44c1b43a6dc5e0ab37a7756c4eecaab468e15
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570057"
---
# <a name="create-a-replacement-kanban-rule"></a>Helyettesítési kanbanszabály létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás egy meglévő kanbanszabály egy új kanbanszabállyal történő lecserélésére irányul az adott dátumon. Ez akkor hasznos, amikor koordinálni és ütemezni kell a gyártási folyamatban vagy a feltöltési szabályokban történt módosításokat. Az USMF bemutatócéget segítségével jött létre az eljárás. Ez az eljárás a folyamatmérnök vagy az érték-előállítási vezető munkáját segíti, amikor előkészítik a termelést a módosított termelési folyamathoz vagy az új feltöltési szabályhoz. Ez a feladat a 000022-es kanbanszabályt egy új szabállyal cseréli ki, illetve a maximális mennyiséget 48-ról 100-ra növeli az új szabályra vonatkozóan.


## <a name="select-a-kanban-rule-to-replace"></a>Válassza ki a lecserélni kívánt kanbanszabályt.
1. Ugorjon a Kanbanszabályokhoz.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válasszon ki a 000022 kanbanszabályt.  

## <a name="create-a-replacement-kanban-rule"></a>Helyettesítési kanbanszabály létrehozása
1. Kattintson a Kanbanszabály lecserélése lehetőségre.
2. Az Érvényesség dátuma mezőben adjon meg egy dátumot és időpontot.
    * Válassza ki egy jövőbeli dátumot, például egy héttel későbbi dátumot. Ez az a dátum és időpont, amikor az új kanbanszabály aktívvá válik és helyettesíti a régi kanbanszabályt.  
    * Ha a kanbanszabály módosítja a termelési folyamat elérési útját, akkor ki lehet választani egy másik tevékenységet.  Ebben az eljárásban ajánlott változatlanul hagyni a tevékenységet.  
3. Kattintson az OK gombra.
    * Figyelje meg, hogy a rendszer már létrehozott egy új kanbanszabályt a 000022 kanbanszabály helyettesítésére.  
    * Az érvényességi dátumot azon kiválasztott dátum szerint állítják be, amikor kicseréli a kanbanszabályt.  
4. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a cserélt 000022 kanbanszabályt.  
    * Vegye figyelembe, hogy a cserélt kanbanszabály dátuma ugyanaz, mint a Lejárati dátum, mert ez az a dátum, amikor a kanbanszabály lejár.  
5. Jelölje ki az 1. sort a listában.
    * Válassza ki a lista tetején az új kanbanszabályt. Ez a legnagyobb kanbanszabály számmal rendelkező kanbanszabály.  
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Kattintson a kanbanszabály-számra a kanbanszabály megnyitásához.  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a>Módosítsa a maximális mennyiségét a Helyettesítési kanbanszabályra vonatkozóan
1. Állítsa a Maximális mennyiséget „100” értékre.
    * Bontsa ki a Mennyiségek gyorslapot a Maximális mennyiség mező megtekintéséhez. A maximális mennyiség 100-ra történő módosítása legfeljebb 100 kanban feldolgozását teszi lehetővé.    Ez az feladat utolsó lépése.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]