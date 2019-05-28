---
title: Szállítási ütemezéssel ellátott beszerzési rendelés létrehozása
description: Ez az eljárás bemutatja, hogy hogyan lehet létrehozni egy szállítási ütemezést egy beszerzési rendeléshez.
author: FrankDahl
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchDeliverySchedule, PurchEditLines
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a9b7b233339d41605e1b115bd14a18b706ef226
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547537"
---
# <a name="create-a-purchase-order-with-a-delivery-schedule"></a>Szállítási ütemezéssel ellátott beszerzési rendelés létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogy hogyan lehet létrehozni egy szállítási ütemezést egy beszerzési rendeléshez. A szállítási ütemezés akkor használatos, ha egy rendeléshez vagy egy naplóhoz tartozó mennyiséget több részletben kell elszállítani. Az útmutatóban mutatott példa használható az USMF demo adatok cégben. Ezt az eljárást általában a beszerzési ügynök végzi el.


## <a name="create-a-delivery-schedule"></a>Szállítási ütemezés létrehozása
1. Ugorjon a Beszerzés és forrás > Beszerzési rendelés > Összes beszerzési rendelés pontra.
2. Kattintson az Új lehetőségre.
3. Írja be az „IS-101” értéket a Szállítói számla mezőbe.
4. Kattintson az OK gombra.
5. Adja meg a „M0001” értéket a Cikkszám mezőben.
6. Írja be a „10” értéket a Mennyiség mezőbe.
7. Kattintson a Beszerzési-rendelés sorra.
8. Kattintson a Szállítási ütemezés elemre.
    * A Szállítási ütemezés lap lehetővé teszi azoknak a szállítmányoknak a számának a megadását, amely során a rendszer a rendelési sor teljes mennyiségét elküldi a szállítótól.  
    * Alapértelmezés szerint a rendszer átmásolja az eredeti beszerzési sor egyéb szállítási részleteit és a teljes mennyiséget az első szállítási ütemezés sorába. Ebben a példában két szállítmányhoz hoztunk létre ütemezést a második szállítmány dátumával, amely egy héttel tér el az első szállítmányétól.  
9. A Mennyiség mező értékét módosítsa 4-re.
10. Kattintson az Új lehetőségre.
11. Adja meg a 6-os értéket visszamaradó mennyiségként a Mennyiség mezőben.
    * A szállítási dátum mezőben válasszon ki egy olyan dátumot, amely egy héttel későbbi az első szállítási sorban lévő dátumnál.  
    * Nyomon követheti a teljes mennyiséget, ami a szállítási ütemezés soraihoz van rendelve ha megtekinti az Összes és Maradvány mezőket. Ha a maradvány mennyisége nulla, akkor a teljes mennyiség az eredeti sorból az ütemezéshez lett rendelve.  
12. Bontsa ki a Költségek átalakítása szakaszt.
    * Az itt található beállítások lehetővé teszi a költségek szállítási ütemezés sorai között történő elosztási módjának az ellenőrzését. Ha a Bruttó összegek másolása lehetőséget választja, akkor a rendszer minden egyes szállítási sorba átmásolja az eredeti rendelési soron található költség számlát. A Felosztás szállítmánysorokra beállítás az eredeti sor költségét az egyes sorokon lévő mennyiség szerint osztja fel.  
13. Zárja be a Költségek átalakítása szakaszt.
14. Kattintson az OK gombra.
    * A rendszer a szállítási ütemezést alkalmazta a rendeléshez.  
    * A rendszer több szállítással együtt konvertálta a jelenleg Kereskedelmi sorként hivatkozott, eredeti rendelési sort a Rendelési sorhoz. Ezt egy külön ikon jelzi, és fejlécként szolgál a szállítási sorokhoz.  
15. Válassza ki azt a második rendelési sort, amely az első a két szállítási sor közül.
    * A szállítási sorként hivatkozott két új sor egy szállítási ütemezést képez. A rendelés szembeni ezen sorok és nem az eredeti sor szerint kerül feldolgozásra. Ha ki vannak nyomtatva az olyan dokumentumok, mint például a megerősítések, a Termékbevételezési naplók, vagy a számlák, akkor csak a szállítási sorok jelennek meg.  

## <a name="change-the-delivery-schedule"></a>A szállítási ütemezés módosítása
    * A mennyiséget a szállítási sorokban meg lehet változtatni. Ha ezt hajtja végre, akkor a rendszer automatikusan frissíti a kereskedelmi sort a szállítási sor teljes mennyiségére.  
1. Módosítsa a mennyiséget 4-ről 5-re az első szállítási sor Mennyiség mezőben.
2. Válassza ki az első rendelési sort (a kereskedelmi sor).
    * A kereskedelmi sorban szereplő mennyiség 11-re lett módosítva.  

## <a name="process-product-receipt-using-delivery-schedules"></a>A Termékbevételezések feldolgozása a szállítási ütemezéssel használatával
    * A termékbevételezés végrehajtása előtt meg kell erősíteni a beszerzési rendelést. Ebben a példában a bevételezést közvetlenül a beszerzési rendelésen rögzítik. A bevételezés rögzítése akkor is megtörténhetett, amikor az áruk beérkeztek a raktárba.  
1. A Művelet panelen kattintson a Beszerzés elemre.
2. Kattintson a Megerősítés gombra.
3. A Művelet panelen kattintson a Bevételezés elemre.
4. Kattintson a Termékbevételezés elemre.
5. Írjon be egy értéket a Termék bevételezés mezőbe.
    * Ezzel a mezővel lehet megadni olyan hivatkozást, ami bizonylatként lesz használva a termék bevételezési naplójához.  
    * Válassza ki a „Megrendelt mennyiség” lehetőséget a Mennyiség mezőben. Ez a beállítás azt jelenti, hogy a bevételezés azt a dolgozza fel, amellyel együtt a rendszer létrehozta a rendelési sorokat.  
    * Győződjön meg arról, hogy a Termékbevételezés nyomtatása mező értéke Nem lehetőségre van beállítva. Ebben a példában nem szükséges a nyomtatás.  
6. Bontsa ki a Sorok szakaszt.
    * Ne feledje, hogy a rendszer a termékbevételezést a két szállítási sorhoz hozta létre, és nem az eredeti rendelési sorhoz. Ha a Bevételezés rögzítve van a raktárban, akkor a szállítási ütemezési sorokban is rögzítve van.  
7. Csukja össze Sorok szakaszt.
8. Kattintson az OK gombra a bevételezés feladásához.

