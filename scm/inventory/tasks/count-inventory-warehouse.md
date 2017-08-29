--- 
title: "Készlet számlálása egy raktárban"
description: "Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készletleltározási napló a raktárban egy adott helyen található konkrét cikk leltározásához."
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 1d2ecf1cd80e05b59f206fb5f684d6a86fa5733e
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="count-inventory-in-a-warehouse"></a>Készlet számlálása egy raktárban

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készletleltározási napló a raktárban egy adott helyen található konkrét cikk leltározásához. Ez az eljárás az „alapvető raktározás” szolgáltatásra vonatkozik, amely a Készletgazdálkodás modul része, és nem a „raktározás” szolgáltatásra, amely a Raktárkezelés modul része. Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti. Ha a saját adatait használja, ügyeljen rá, hogy legyenek beállított termékek és helyek, és hogy létrehozzon egy készletnaplónevet a leltárnaplókhoz. A készletleltározást általában egy raktári alkalmazott végzi el.


## <a name="create-an-inventory-counting-journal"></a>Készletleltározási napló létrehozása
1. Lépjen a Készletgazdálkodás > Naplóbejegyzések > Cikkleltár > Leltár menüpontba.
2. Kattintson az Új lehetőségre.
3. A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A listában kattintson a készletleltározási naplónévre, amelyet használni kíván.
    * Ki lesz töltve néhány más mező a kiválasztott készletleltározási naplónév beállításai alapján.  
5. A Dolgozó mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. A listából válassza ki a használni kívánt dolgozót.
7. Kattintson a Kiválasztás lehetőségre.
8. Kattintson az OK gombra.

## <a name="create-journal-lines"></a>Naplósorok létrehozása
1. Kattintson az Új lehetőségre.
2. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Az USMF bemutatócég használata esetén válassza az „A0001” lehetőséget.  
4. A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Az USMF bemutatócég használata esetén válassza a2 „2” telephelyet.  
6. A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Az USMF bemutatócég használata esetén válassza az „24” raktárat.  
8. A Hely mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
9. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Az USMF bemutatócég használata esetén válassza az „BULK-001” helyet  
10. Adjon meg egy számot a Leltározva mezőben.
    * Ha olyan megszámolt darabszámot ír be, amely különbözik az Aktuális készlet mezőben láthatótól, akkor a Mennyiség mező frissül, hogy mutassa az értékeltérést.  
11. Kattintson a Mentés gombra.

## <a name="post-the-inventory-counting-journal"></a>Készletleltározási napló feladása
1. Kattintson a Feladás lehetőségre.
    * Készletleltározási napló feladásakor, ha a megszámolt darabszám különbözik az Aktuális készlet mezőben láthatótól, feladásra kerül egy készletbevétel vagy -kiadás, módosul a készletszint és a készletérték, és főkönyvi tranzakciók jönnek létre.  
2. Kattintson az OK gombra.

## <a name="view-inventory-transactions"></a>Készlettranzakciók megtekintése
1. Kattintson a Készlet parancsra.
2. Kattintson a Tranzakciók elemre.
    * Itt láthatók a kapcsolódó tranzakciók, amelyek a készletleltározási napló feladásakor jönnek létre.   


