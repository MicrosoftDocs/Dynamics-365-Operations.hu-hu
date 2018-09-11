--- 
title: "A készlet elérhetőségének ellenőrzése"
description: "Ez az eljárás bemutatja, hogy hogyan ellenőrizheti egy adott cikkszám aktuális, illetve ténylegesen rendelkezésre álló készletét."
author: 
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand
audience: Application User
ms.reviewer: 
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: 
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 62338fe11c30781f264e626fad835a2ba9dca837
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="check-the-availability-of-stock"></a>A készlet elérhetőségének ellenőrzése

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogy hogyan ellenőrizheti egy adott cikkszám aktuális, illetve ténylegesen rendelkezésre álló készletét. Az eljárás azt is bemutatja, hogy hogyan jelenítheti meg az adott cikkel kapcsolatos szállítói adatokat. A tényleges aktuális készlet a ténylegesen rendelkezésre álló, azaz a beszerzett, átvett és nyilvántartásba vett készletet mutatja meg. Az aktuális készlet nem csak a ténylegesen rendelkezésre álló, azaz a tényleges aktuális készletet, hanem a már megrendelt, viszont még nem át- vagy nyilvántartásba vett készletet is tartalmazza. Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti. A USMF használata esetén alkalmazhatja az itt megjelenő, példa jellegű értékeket. Ezeket a feladatokat jellemzően egy raktári dolgozó végzi el.


## <a name="check-on-hand-inventory-for-an-item"></a>Ellenőrizze az adott cikk aktuális készletét
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

## <a name="check-physical-on-hand-inventory"></a>Ellenőrizze az adott cikk tényleges aktuális készletét
1. Nyissa meg a következőt: Készletkezelés > Lekérdezések és jelentések > Tényleges aktuális készlet.
2. A cikkmezőbe írjon egy értéket.
    * A cikklistát a Telephely és Raktár mezők segítségével tudja szűrni.  
3. Frissítse a lapot..
4. Kattintson a Dimenziók megjelenítése elemre.
    * A Dimenziókat megjelenítő lapon tudja beállítani az aktuális készletre vonatkozó információk részletességét.  
5. Kattintson az OK gombra.
6. Zárja be a lapot.

## <a name="check-on-hand-inventory-by-location"></a>Ellenőrizze az aktuális készletet hely szerint.
1. Nyissa meg a következőt: Készletkezelés > Lekérdezések és jelentések > Aktuális helyenként.
2. Érték beírása a Raktár mezőbe.
    * Ha a USMF vállalat bemutató adatait alkalmazza, úgy használhatja az „51” értéket.  
3. Frissítse a lapot..
4. Kattintson a Dimenziók megjelenítése elemre.
5. Kattintson az OK gombra.
6. Zárja be a lapot.


