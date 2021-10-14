---
title: Lean igénykövetés az értékelési rendelésekből
description: Ez az eljárás arra irányul, hogy ellenőrizze az igénykövetési fát egy olyan értékesítési sorból, ahol a cikk létrehozása kanbanokkal történik.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8eca21f8bd988ca352c07e839295b3edd9669929
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580624"
---
# <a name="lean-pegging-from-sales-orders"></a>Lean igénykövetés az értékelési rendelésekből

[!include [banner](../../includes/banner.md)]

Ez az eljárás arra irányul, hogy ellenőrizze az igénykövetési fát egy olyan értékesítési sorból, ahol a cikk létrehozása kanbanokkal történik. Az igénykövetési fa ellenőrzése után minden kanbanfeladat tervezetté válik. Ez olyan rendelési esetekben hasznos, ahol a rendelés végrehajtójának biztosítania kell a termelés azonnali elindítását. Ez az eljárás az USMF bemutatócéget használja. Az eljárás a lean vállalatnak dolgozó haladó rendelésvégrehajtók számára ajánlott.


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a>Hozzon létre egy kanban által szabályozott cikkre vonatkozó értékesítési sort
1. Ugrás az összes értékesítési rendelésre.
2. Kattintson az Új lehetőségre.
3. A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.
    * Használja a következőt: US-001.  
4. Kattintson az OK gombra.
5. A Cikkszám mezőbe írja be az „L0001” értéket.
6. Állítsa a mennyiséget 30 értékre.
    * Az esemény kanbanszabály elindítása miatt fontos, hogy a mennyiség 24-nél nagyobb legyen.  

## <a name="open-a-pegging-tree"></a>Igénykövetési fa megnyitása 
1. Kattintson a Termék és készlet menüpontra.
2. Az igénykövetési fa megtekintése lehetőségre.
    * Figyelje meg, hogy az igénykövetési fa megjeleníti az értékesítési rendelési sorhoz szükséges igénykövetés minden szintjét. Ebben az esetben a kanbanoknak és minden szükséges összetevőnek két szintje van.  

## <a name="plan-the-pegging-tree"></a>Igénykövetési fa megtervezése
1. A fán válassza ki a következőt: „Értékesítési sor: 000832\Kanban: 000558”.
2. Bontsa ki a Kanbanfeladatok szakaszt.
    * Figyelje meg, hogy a kanbanfeladat állapota Nem tervezett.  
3. Kattintson A teljes igénykövetési fa megtervezése lehetőségre.
    * Ez megtervezi az igénykövetési fában szereplő összes kanbanfeladatot, amelynek során a Feladat állapota megváltozik: Nem tervezett helyett Tervezett lesz.  
4. Frissítse a lapot..
    * Figyelje meg, hogy a kanban Feladat állapota megváltozott: Nem tervezett helyett Tervezett lett.  
5. A fán válassza ki a következőt: „Értékesítési sor: 000832\Kanban: 000558\Kiadás: L0001\Kanban: 000559”.
    * A második kanbanhoz tartozó feladat szintén tervezett, mivel az egész igénykövetési fa tervezett. Figyelje meg, hogy a kanbanfeladat állapota megváltozott: Nem tervezett helyett Tervezett lett.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]