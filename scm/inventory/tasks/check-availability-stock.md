--- 
title: "A készlet elérhetőségének ellenőrzése"
description: "Ez az eljárás bemutatja, hogy hogyan ellenőrizheti egy adott cikkszám aktuális, illetve ténylegesen rendelkezésre álló készletét."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: d103eb52a498e6273b1fdb43fc10dae4133e76b2
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# A készlet elérhetőségének ellenőrzése

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogy hogyan ellenőrizheti egy adott cikkszám aktuális, illetve ténylegesen rendelkezésre álló készletét. Az eljárás azt is bemutatja, hogy hogyan jelenítheti meg az adott cikkel kapcsolatos szállítói adatokat. A tényleges aktuális készlet a ténylegesen rendelkezésre álló, azaz a beszerzett, átvett és nyilvántartásba vett készletet mutatja meg. Az aktuális készlet nem csak a ténylegesen rendelkezésre álló, azaz a tényleges aktuális készletet, hanem a már megrendelt, viszont még nem át- vagy nyilvántartásba vett készletet is tartalmazza. Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti. A USMF használata esetén alkalmazhatja az itt megjelenő, példa jellegű értékeket. Ezeket a feladatokat jellemzően egy raktári dolgozó végzi el.


## Ellenőrizze az adott cikk aktuális készletét
1. Nyissa meg a következőt: Készletkezelés > Lekérdezések és jelentések > Aktuális készlet.
2. Válassza ki a Cikkszám sort.
    * Az aktuális készlet cikkszám szerinti lekérdezéséhez válassza ki azt a sort, ahol a Táblázat beállítása Aktuális készlet, a Mező beállítása pedig cikkszám.  
3. A Feltételek mezőben válassza ki a lekérdezni kívánt cikket.
    * Ha a USMF vállalat bemutató adatait alkalmazza, úgy használhatja az „M9201” értéket.  
4. Kattintson az OK gombra.
5. Kattintson a Dimenziókra.
    * A Dimenziók lapon tudja beállítani az aktuális készletre vonatkozó információk részletességét. A foglalással kapcsolatos adatok megtekintéséhez a speciális raktározási (WHS) folyamatokat használó cikkek kapcsán meg kell jelenítenie az összes készletdimenziót.  
6. Kattintson az OK gombra.
7. A Műveleti ablakban kattintson a Kapcsolódó információ elemre.
    * Ha nem ez jelenik meg, úgy elképzelhetően rá kell kattintania az Ellipszis gomb (...) parancsra a további műveleti ablak opciók megjelenítéséhez.  
8. Kattintson a Szállítmány-összesítés lehetőségre.
    * A Szállítmány-áttekintés lap olyan konkrét cikkről szolgáltat információt, mint az aktuális mennyiség, az átfutási idő vagy a szállítói adatok.  
9. Bontsa ki a Aktuális részt.
10. Bontsa ki a Szállító szakaszt.
11. Zárja be a lapot.
12. Zárja be a lapot.

## Ellenőrizze az adott cikk tényleges aktuális készletét
1. Nyissa meg a következőt: Készletkezelés > Lekérdezések és jelentések > Tényleges aktuális készlet.
2. A cikkmezőbe írjon egy értéket.
    * A cikklistát a Telephely és Raktár mezők segítségével tudja szűrni.  
3. Frissítse a lapot..
4. Kattintson a Dimenziók megjelenítése elemre.
    * A Dimenziókat megjelenítő lapon tudja beállítani az aktuális készletre vonatkozó információk részletességét.  
5. Kattintson az OK gombra.
6. Zárja be a lapot.

## Ellenőrizze az aktuális készletet hely szerint.
1. Nyissa meg a következőt: Készletkezelés > Lekérdezések és jelentések > Aktuális helyenként.
2. Érték beírása a Raktár mezőbe.
    * Ha a USMF vállalat bemutató adatait alkalmazza, úgy használhatja az „51” értéket.  
3. Frissítse a lapot..
4. Kattintson a Dimenziók megjelenítése elemre.
5. Kattintson az OK gombra.
6. Zárja be a lapot.


