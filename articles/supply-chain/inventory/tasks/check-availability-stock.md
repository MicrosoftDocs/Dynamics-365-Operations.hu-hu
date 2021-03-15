---
title: A készlet elérhetőségének ellenőrzése
description: Ez az eljárás bemutatja, hogy hogyan ellenőrizheti egy adott cikkszám aktuális, illetve ténylegesen rendelkezésre álló készletét.
author: ShylaThompson
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand, InventOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d04abae36e144b429b8ebc73b4c110389fecd1f0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000159"
---
# <a name="check-the-availability-of-stock"></a>A készlet elérhetőségének ellenőrzése

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogy hogyan ellenőrizheti egy adott cikkszám aktuális, illetve ténylegesen rendelkezésre álló készletét. Az eljárás azt is bemutatja, hogy hogyan jelenítheti meg az adott cikkel kapcsolatos szállítói adatokat. A tényleges aktuális készlet a ténylegesen rendelkezésre álló, azaz a beszerzett, átvett és nyilvántartásba vett készletet mutatja meg. Az aktuális készlet nem csak a ténylegesen rendelkezésre álló, azaz a tényleges aktuális készletet, hanem a már megrendelt, viszont még nem át- vagy nyilvántartásba vett készletet is tartalmazza. Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti. A USMF használata esetén alkalmazhatja az itt megjelenő, példa jellegű értékeket. Ezeket a feladatokat jellemzően egy raktári dolgozó végzi el.


## <a name="check-on-hand-inventory-for-an-item"></a>Ellenőrizze az adott cikk aktuális készletét
1. Nyissa meg a következőt: **Navigációs panel > Készletkezelés > Lekérdezések és jelentések > Aktuális készlet**.
2. Válassza ki a **Cikkszám** sort. Az aktuális készlet cikkszám szerinti lekérdezéséhez válassza ki azt a sort, ahol a Táblázat beállítása **Aktuális készlet**, a Mező beállítása pedig **Cikkszám**.
3. A **Feltételek** mezőben válassza ki a lekérdezni kívánt cikket. Ha a USMF vállalat bemutató adatait alkalmazza, úgy használhatja az „M9201” értéket.  
4. Kattintson az **OK** gombra.
5. A **Művelet panelen** kattintson a **Dimenziók** elemre. A **Dimenziók** lapon tudja beállítani az aktuális készletre vonatkozó információk részletességét. A foglalással kapcsolatos adatok megtekintéséhez a speciális raktározási (WMS) folyamatokat használó cikkek kapcsán meg kell jelenítenie az összes készletdimenziót.
6. Kattintson az **OK** gombra.
7. A **Műveleti ablakban** kattintson a **Kapcsolódó információ** elemre. Ha nem jelenik meg ez a lehetőség, úgy elképzelhetően rá kell kattintania az Ellipszis gomb (...) parancsra a további műveleti ablaktábla opciók megjelenítéséhez.
8. Kattintson a **Szállítmány-összesítés** lehetőségre. A **Szállítmány-áttekintés** lap olyan konkrét cikkről szolgáltat információt, mint az aktuális mennyiség, az átfutási idő vagy a szállítói adatok.  
9. Bontsa ki a **Aktuális** részt.
10. Bontsa ki a **Szállító** szakaszt.
11. Zárja be a lapot.
12. Zárja be a lapot.

## <a name="check-physical-on-hand-inventory"></a>Ellenőrizze az adott cikk tényleges aktuális készletét
1. Nyissa meg a következőt: **Navigációs panel > Raktárkezelés > Lekérdezések és jelentések > Aktuális fizikai készlet**.
2. A **Cikkszám** mezőbe írjon egy értéket. A cikklistát a Telephely és Raktár mezők segítségével tudja szűrni. 
3. Frissítse a lapot..
4. A **Műveleti panel** modulon kattintson a **Dimenziók megjelenítése** elemre. A Dimenziókat megjelenítő lapon tudja beállítani az aktuális készletre vonatkozó információk részletességét.
5. Kattintson az **OK** gombra.
6. Zárja be a lapot.

## <a name="check-on-hand-inventory-by-location"></a>Ellenőrizze az aktuális készletet hely szerint.
1. Nyissa meg a következőt: **Navigációs panel > Raktárkezelés > Lekérdezések és jelentések > Aktuális készlet hely szerint**.
2. Érték beírása a **Raktár** mezőbe. Ha a USMF vállalat bemutató adatait alkalmazza, úgy használhatja az „51” értéket.  
3. Frissítse a lapot..
4. Kattintson a **Dimenziók megjelenítése** elemre.
5. Kattintson az **OK** gombra.
6. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]