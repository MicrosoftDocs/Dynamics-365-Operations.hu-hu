--- 
title: "Kiskereskedelmi üzlet kimutatásának létrehozása, kiszámítása és feladása"
description: "Ez az eljárás végigveszi egy üzlet kimutatása létrehozásának, kiszámításának és feladásának manuális lépéseit."
author: jashanno
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 33ebb28196baa9ae944dbd124274b05cb587fea4
ms.contentlocale: hu-hu
ms.lasthandoff: 02/07/2018

---
# <a name="create-calculate-and-post-a-statement-for-a-retail-store"></a>Kiskereskedelmi üzlet kimutatásának létrehozása, kiszámítása és feladása

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

Ez az eljárás végigveszi egy üzlet kimutatása létrehozásának, kiszámításának és feladásának manuális lépéseit. Kötegelt feladatok is léteznek, amelyek ugyanazon eljárásokhoz konfigurálhatók. A kötegelt feladatok konfigurálásának és futtatásának lépései egy másik témakörben találhatók meg. Az eljárás végrehajtásához rendelkeznie kell olyan tranzakciókkal, amelyeket a pénztárban hajtottak végre, majd átvezették a Dynamics AX programba. Ez a bejegyzés az USRT cég adatait használja, mint bemutatóadatokat. Ez az eljárás a Microsoft Dynamics AX rendszerre vonatkozhat. Ne feledje, hogy a Dynamics AX új neve Microsoft Dynamics 365 for Operations.

1. Lépjen Az összes munkaterület > .. > Kiskereskedelmi üzlet pénzügyei lehetőségre.
2. Kattintson az Új kimutatás lehetőségre.
3. Az Üzlet száma mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Kattintson az OK gombra.
    * A Beállítások csoportban beállíthatja, hogy mely tranzakciók szerepeljenek a kimutatásban, és hogy azok hogyan legyenek sorokba csoportosítva. Megnyithatja a Beállítások csoportot és megváltoztathatja a beállításokat, vagy használhatja az alapértelmezett beállításokat is.  
    * A Kimutatás módja mező megadja, hogy a kimutatás sorai hogyan lesznek csoportosítva.  
    * Válasszon ki egy munkatársat vagy egy jegyzéket, ha a kimutatást csak egy bizonyos munkatársra vagy jegyzékre vonatkozóan szeretné elkészíteni.  
6. Válassza ki valamelyik lehetőséget a Zárási mód mezőben.
7. Kattintson a Kimutatás számítása lehetőségre.
8. Kattintson az Igen gombra.
    * A kimutatás elkészítése után külön sorokban kell szerepelnie a teljes összegnek minden alkalmazott fizetési mód és kimutatási mód esetén.  
    * Adjon meg egy leszámolt összeget minden sorban, amelyben meg kell adni vagy frissíteni kell az értéket. A leszámolt értéket tartalmazó mező a pénztárban végrehajtott fizetőeszköz-elszámolások során kapott összeggel van kitöltve.  
9. Kattintson a Kimutatás feladása lehetőségre.
10. Kattintson a Bezárás gombra.
11. Ugorjon a következő oldalra: Kiskereskedelem és kereskedelem > Csatornák > Kiskereskedelmi üzlet pénzügyei.
12. Kattintson a Feladott kimutatások fülre.


