---
title: Szállítási ütemezéssel ellátott beszerzési rendelés létrehozása
description: Ez a témakör bemutatja, hogy hogyan lehet létrehozni egy szállítási ütemezést egy beszerzési rendeléshez.
author: kamaybac
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchDeliverySchedule, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d788aaf3dc45542e20745cb295d77efdc277a4be
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812350"
---
# <a name="create-a-purchase-order-with-a-delivery-schedule"></a>Szállítási ütemezéssel ellátott beszerzési rendelés létrehozása

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogy hogyan lehet létrehozni egy szállítási ütemezést egy beszerzési rendeléshez. A szállítási ütemezés akkor használatos, ha egy rendeléshez vagy egy naplóhoz tartozó mennyiséget több részletben kell elszállítani. Az útmutatóban mutatott példa használható az USMF demo adatok cégben. Ezt az eljárást általában a beszerzési ügynök végzi el.

## <a name="create-a-delivery-schedule"></a>Szállítási ütemezés létrehozása
1. Navigációs ablaktáblán ugorjon a **Modulok > Beszerzés és forrás > Beszerzési rendelések > Összes beszerzési rendelés** elemre.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. Adja meg az `US-101` értéket a **Szállítói számla** mezőben.
4. Válassza ki az **OK** lehetőséget.
5. Adja meg az `M0001` értéket a **Cikkszám** mezőben.
6. Adja meg az `10` értéket a **Mennyiség** mezőben.
7. Válasszon **Beszerzési rendelés sort**
8. Válassza a **Szállítási ütemezés** lehetőséget.
- A **Szállítási ütemezés** lap lehetővé teszi azoknak a szállítmányoknak a számának a megadását, amely során a rendszer a rendelési sor teljes mennyiségét elküldi a szállítótól.  
- Alapértelmezés szerint a rendszer átmásolja az eredeti beszerzési sor egyéb szállítási részleteit és a teljes mennyiséget az első szállítási ütemezés sorába. Ebben a példában két szállítmányhoz hoztunk létre ütemezést a második szállítmány dátumával, amely egy héttel tér el az első szállítmányétól.  
9. A **Mennyiség** mező értékét módosítsa `4` értékre.
10. Válassza az **Új** lehetőséget.
11. Adja meg a `6` értéket visszamaradó mennyiségként a **Mennyiség** mezőben.
- A szállítási dátum mezőben válasszon ki egy olyan dátumot, amely egy héttel későbbi az első szállítási sorban lévő dátumnál.  
- Nyomon követheti a teljes mennyiséget, ami a szállítási ütemezés soraihoz van rendelve ha megtekinti az **Összes** és **Maradvány** mezőket. Ha a maradvány mennyisége nulla, akkor a teljes mennyiség az eredeti sorból az ütemezéshez lett rendelve.  
12. Bontsa ki a **Költségek átalakítása** szakaszt.
- Az itt található beállítások lehetővé teszi a költségek szállítási ütemezés sorai között történő elosztási módjának az ellenőrzését. Ha a **Bruttó összegek másolása** lehetőséget választja, akkor a rendszer minden egyes szállítási sorba átmásolja az eredeti rendelési soron található költség számlát. A **Felosztás szállítmánysorokra** beállítás az eredeti sor költségét az egyes sorokon lévő mennyiség szerint osztja fel.  
13. Zárja be a **Költségek átalakítása** szakaszt.
14. Válassza ki az **OK** lehetőséget.
- A rendszer a szállítási ütemezést alkalmazta a rendeléshez.  
- A rendszer több szállítással együtt konvertálta a jelenleg Kereskedelmi sorként hivatkozott, eredeti rendelési sort a Rendelési sorhoz. Ezt egy külön ikon jelzi, és fejlécként szolgál a szállítási sorokhoz.  
15. Válassza ki azt a második rendelési sort, amely az első a két szállítási sor közül.
- A szállítási sorként hivatkozott két új sor egy szállítási ütemezést képez. A rendelés szembeni ezen sorok és nem az eredeti sor szerint kerül feldolgozásra. Ha ki vannak nyomtatva az olyan dokumentumok, mint például a megerősítések, a Termékbevételezési naplók, vagy a számlák, akkor csak a szállítási sorok jelennek meg.  

## <a name="change-the-delivery-schedule"></a>A szállítási ütemezés módosítása
A mennyiséget a szállítási sorokban meg lehet változtatni. Ha ezt hajtja végre, akkor a rendszer automatikusan frissíti a kereskedelmi sort a szállítási sor teljes mennyiségére.  
1. Módosítsa a mennyiséget `4`-ről `5`-re az első szállítási sor **Mennyiség** mezőben.
2. Válassza ki az első rendelési sort (a kereskedelmi sor).  
- A kereskedelmi sorban szereplő mennyiség 11-re lett módosítva.  

## <a name="process-product-receipt-using-delivery-schedules"></a>A Termékbevételezések feldolgozása a szállítási ütemezéssel használatával
A termékbevételezés végrehajtása előtt meg kell erősíteni a beszerzési rendelést. Ebben a példában a bevételezést közvetlenül a beszerzési rendelésen rögzítik. A bevételezés rögzítése akkor is megtörténhetett, amikor az áruk beérkeztek a raktárba.  
1. A Műveleti ablaktáblán válassza ki a **Beszerzés** lehetőséget.
2. Válassza ki a **Megerősítés** elemet.
3. A Művelet ablaktáblán válassza ki a **Bevételezés** elemet.
4. Válassza ki a **Termékbevételezés** elemet. Adjon meg egy értéket a **Termékbevételezés** mezőben.
- Ezzel a mezővel lehet megadni olyan hivatkozást, ami bizonylatként lesz használva a termék bevételezési naplójához.  
- Válassza ki a **Megrendelt mennyiség** lehetőséget a **Mennyiség** mezőben. Ez a beállítás azt jelenti, hogy a bevételezés azt a dolgozza fel, amellyel együtt a rendszer létrehozta a rendelési sorokat.  
- Győződjön meg arról, hogy a **Termékbevételezés nyomtatása** mező értéke **Nem** lehetőségre van beállítva. Ebben a példában nem szükséges a nyomtatás.  
5. Bontsa ki a **Sorok** szakaszt.
- Ne feledje, hogy a rendszer a termékbevételezést a két szállítási sorhoz hozta létre, és nem az eredeti rendelési sorhoz. Ha a Bevételezés rögzítve van a raktárban, akkor a szállítási ütemezési sorokban is rögzítve van.  
6. Csukja össze a **Sorok** szakaszt.
7. Kattintson az **OK** gombra a bevételezés feladásához.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]