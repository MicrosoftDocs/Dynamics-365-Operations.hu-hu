--- 
title: "Beszerzési rendelés létrehozása"
description: "Ez az eljárás bemutatja, hogy hogyan lehet manuálisan létrehozni beszerzési rendelést."
author: FrankDahl
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchCreateOrder, InventDimParmFixed, InventItemIdLookupPurchase, InventProductDimensionLookup, PurchTotals
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 27ed15e6d9a376c4203e5446d056f221bd3eb730
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogy hogyan lehet manuálisan létrehozni beszerzési rendelést. Sokkal jobban megfigyelhető, hogy a rendszer az alaptervezés, a közvetlen kiszállítás és más folyamatok eredményeként automatikusan hozza létre a beszerzési rendeléseket. Általában a beszerzési ügynök hozza létre a beszerzési rendeléseket. Az itt bemutatott példát az USMF bemutatócégben használhatja a különböző lépések megjegyzéseiben javasolt értékek használatával.


## <a name="create-the-purchase-order-header"></a>Beszerzési rendelési fejléc létrehozása
1. Ugorjon a Beszerzés és forrás > Beszerzési rendelés > Összes beszerzési rendelés pontra.
2. Kattintson az Új lehetőségre.
3. Válassza ki a US-101 szállítókódot.
    * Amikor kiválaszt egy szállítót, a szállítórekorddal kapcsolatos információk, mint például a cím, a számlafogadó, szállítási feltételek és a szállítási mód alapértelmezett értékként kerülnek másolásra a rendelési fejlécbe. A paraméterek ezen értékei bármikor módosíthatók.  
4. Bontsa ki az Általános szakaszt.
    * A Hely mező a Raktár mezővel együtt azt határozza meg, hogy hova kell a beszerzett termékeket vagy szolgálatásokat küldeni. A telephely az alapértelmezett szállítási cím. Mindkét mezőt fel lehet tölteni a kiválasztott szállítóra vonatkozó értékekkel, vagy manuálisan is meg lehet adni az értékeket.  
    * A Szállítási dátum mező arra szolgál, hogy meghatározza, hogy mikor kell a beszerzett árukat és szolgáltatásokat kézbesíteni. Megadhatja az egyes szállítási dátumot a rendeléshez, illetve az egyes rendeléssorokat az egyedi kézbesítési dátumokhoz. Ha az itt megadott szállítási dátum nem teljesíthető a specifikus termékekre vagy szolgáltatásokra vonatkozóan, mert hosszabb az átfutási idejük, akkor ezeket a sorokat egy későbbi szállítási dátummal kell létrehozni az ehhez történő elhelyezéshez.  
5. Zárja be az Általános szakaszt.
6. Bontsa ki az Adminisztráció szakaszt.
    * A Megrendelő mező segítségével adja meg azt a személyt, aki elhelyezi a rendelést. A szállítóval történő megosztás hasznos lehet abban az esetben, ha kapcsolatba kell lépnie azzal a személlyel. A mezőt automatikusan hozzá lehet rendelni egy értékhez, ha a jelenlegi felhasználót társította a Felhasználók lapon található névvel.  
7. Zárja be az Adminisztráció szakaszt.
8. Kattintson az OK gombra.
    * A rendelési fejléc létrehozása megtörtént. Amikor a beszerzésirendelés-sorokkal dolgozik, csak a fejlécadatok összesítője jelenik meg. HA meg szeretné tekinteni a többi információt, kattintson a Fejléc lehetőségre.  

## <a name="add-a-purchase-order-line"></a>Beszerzési rendelési sor hozzáadása
1. Kattintson a Beszerzési-rendelés sorra.
2. Kattintson a Dimenziókra.
    * A termékek azon különböző változatokban jelenhetnek meg, amelyek dimenziók alapján vannak megkülönböztetve, például a szín, méret vagy stílus szerint. A termékeket be lehet állítani a tárolási dimenziók, például a hely és raktár használatára. Vannak nem kötelező nyomon követési dimenziók is, például a Köteg- és sorozatszámok. A rendelésbevitel hatékonyságának javítása érdekében megadhatja azokat a dimenziómezőket, amiket gyakran használ közvetlenül a rendelés rácshoz.  
3. Válassza ki a Szín jelölőnégyzetet.
    * Választható: Ha a Mentés beállítása mezőt bejelöli, a kiválasztott dimenziók is megjelennek a rendelési sorok rácsában a beszerzési rendelés lap következő megnyitásakor.  
4. Kattintson az OK gombra.
5. A Cikkszám mezőben válassza ki a T0004 értéket.
    * A rendszer a rendelési sorokat a termékre és a szolgáltatóra vonatkozóan egy cikkszám meghatározásával vagy kiadásként a beszerzési kategória meghatározásával hozza létre.  
    * A beszerzési kategória mező azon sorok hozzáadására szolgál, ahol a beszerzett termékeket közvetlenül kiadják, a készletbe történő szállítás helyett. Ez azt jelenti, hogy ha ki szeretne adni egy beszerzést, akkor ezt azon beszerzési rendelés létrehozásával teheti meg, amely meghatározza a beszerzési kategóriát egy sor cikkszámmal történő létrehozása helyett. A cikkeket a beszerzési kategóriával is társíthatja és ebben az esetben a beszerzési kategória csak tájékoztatás jelleggel jelenik meg.  
6. A Szín mezőben adjon meg vagy válasszon ki egy értéket.
    * A rendszer általában feltölti a hely és raktár mezőket a rendelési fejlécből származó értékekkel, de akár felül is írhatja a mezőket, ha néhány sort különböző helyekre kell küldeni.  
7. Adjon meg egy számot a Mennyiség mezőben.
    * Válassza ki a beszerezni kívánt mennyiséget. A rendszer automatikusan kitölti a mennyiség mezőt a minimális rendelési mennyiséggel, ha be van állítva vagy pedig az „1” értékkel.  
    * Az Egység mező a megrendelt mennyiségre vonatkozó mértékegységet jelenti. Általában a rendszer automatikusan létrehozza az egységet a termék alapadataiban a beszerzési egységből, de ezt nem lehet módosítani.  
    * Az egységár mező általában vagy a beszerzési szerződésből vagy a kereskedelmi megállapodásból származó értéket tartalmazza. Lehetőség van arra, hogy módosítsa az egységárat az egyes rendelési sorokban, ha például az egyedi ár meg van beszélve a szállítóval.  
    * Az Engedmény mező az engedmény összegét jeleníti meg a termékegységre vetítve. Ezért az engedmény csökkenti az egységárat az engedmény alapján. Ezt az engedményt gyakran a beszerzési szerződésekből vagy a kereskedelmi megállapodásból alkalmazzák, de felül is lehet írni az egyéni sorokban, ha a szállítóval meg vannak tárgyalva az egyedi engedmények.  
    * Meg lehet adni az engedmény százalékát, ami csökkenti a sor nettó összegét a sornak megfelelően. Az engedmény százalékát gyakran a beszerzési szerződésekből vagy a kereskedelmi megállapodásból alkalmazzák, de felül is lehet írni az egyéni sorokban, ha a szállítóval meg van tárgyalva az egyedi engedmény százaléka.  
    * A rendszer a Nettó Összeg mező értéket a mennyiséget, az egységárat, az engedményt, és az engedmény százalékát tartalmazó sorban található mezőkből számolja ki. Módosítani lehet a Nettó összeget, de ezt követően az Egységár, az Engedmény, és az Engedmény százalék mező üres lesz, és amikor feladja a sorhoz, a feladott összeg a nettó összeggel lesz arányos. A nettó összeg mezőt általában csak a sor nettó összegének megjelenítésére használják.  
8. Bontsa ki a Soradatok szakaszt.
9. Kattintson a Kiszállítás lapra.
    * Mindegyik rendelési sorhoz hozzá lehet rendelni az egyedi szállítási dátumot. A dátum a beszerzési rendelés fejlécén található mezőből öröklődik, de ez módosítható.  
10. Csukja össze a Soradatok szakaszt.

## <a name="review-order-totals"></a>A rendelés összegeinek ellenőrzése
1. Kattintson az Összegek lehetőségre.
    * Ha nem jelenik meg az Összegek művelet, kattintson az műveletsávon a Beszerzési rendelés fülre.  
    * Ez a párbeszédpanel megjeleníti a teljes rendelésre vonatkozó összesítést.  
    * A kiválasztási mező lehetővé teszi az összegek kiszámítási módjának alapjának módosítását. Például kiválaszthatja a Termékbevételezési mennyiséget azon termék(ek) összegéhez kapcsolódó összesítések megjelenítéséhez, amelyeket megkapott, vagy a Rendelési mennyiséget a megrendelt termék összegének megjelenítéséhez.  
2. Kattintson az OK gombra.


