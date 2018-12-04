--- 
title: "Helyutasítás beállítása beszerzési rendelés eltárolásához"
description: "Ez az eljárás bemutatja, hogyan állíthat be egyszerű helyutasítást."
author: ShylaThompson
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 4bb4af7cb7aff101a8b9e6162823515f63b12886
ms.openlocfilehash: 98ce3ad38dddda33be5466490fcd39d81251679c
ms.contentlocale: hu-hu
ms.lasthandoff: 11/02/2017

---
# <a name="set-up-a-location-directive-for-purchase-order-put-away"></a>Helyutasítás beállítása beszerzési rendelés eltárolásához

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan állíthat be egyszerű helyutasítást. A példa egy helyutasítást hoz létre ahhoz, hogy a beszerzési rendelés bevételezett cikkeinek helyét meg lehessen határozni. Ezt a feladatleírást lejátszhatja az USMF bemutatócégnél említett adatokkal. Előzetes feltételek: Intézkedési kódot kell létrehoznia. Ebben az eljárásban egy Relabel nevű intézkedési kódot alkalmazunk. Ha helyutasítást hoz létre a saját adataiban, a raktárhoz és a cikkekhez speciális raktárkezelési beállítást kell megadnia.  Ezt az eljárást a raktári vezető használja.

1. Ugrás a Raktárkezelés > Beállítás > Helyutasítások elemre.
2. A Munka rendeléstípus mezőben válassza ki a „Beszerzési rendelések” elemet.

## <a name="create-a-location-directive-header"></a>Helyutasítási műveletek fejléc létrehozása
1. Kattintson az Új lehetőségre.
2. Adjon meg egy számot a Sorozatszám mezőben.
    * Ez az a sorrend, ahogyan a helyutasítás feldolgozása történik a kijelölt munkatétel típusához. A sorrendet módosíthatja ha szükséges.  
3. Írjon be egy értéket a Név mezőbe.
    * Ez ennek az utasításnak az egyedi azonosítója.  
4. A Munkatípus mezőben válassza a „Betárolás” lehetőséget.
    * A másolandó mezőtípusok kijelölése. A Beszerzési rendelés munkarendelés-típushoz az utasításhoz a betárolás az egyetlen támogatott érték.  
5. Érték beírása a Telephely mezőbe.
6. Érték beírása a Raktár mezőbe.
    * Az Irányelv kódja mezőt hagyja üresen.  Az utasításkódokat a Betárolási típusú munkarendeléssor csatolásához használjuk egy adott irányelvhez. A beszerzési rendelések esetében a betárolás típusú utolsó munkarendeléssor feloldása a munkasablon meghatározása előtt történik meg. Ezért nem lehet hozzákapcsolódni a munkasablon utolsó sorát egy adott irányelvhez.   
7. Írjon be egy értéket az Intézkedési kód mezőbe.
    * Az Intézkedési kód korlátozza a helyutasítás használatát, így a helyutasítás csak akkor használható, ha a raktári dolgozó bevisz egy adott értéket a cikk regisztrálása során a mobileszközön.  
8. Kattintson a Mentés gombra.

## <a name="edit-the-query-for-directive"></a>Az utasítás lekérdezésének szerkesztése
1. Kattintson A lekérdezés szerkesztése elemre.
    * Ennek az irányelvnek a felhasználása már korlátozódik az adott raktárban regisztrált cikkekre, az adott intézkedési kóddal. A lekérdezéssel egyéb korlátokat is hozzáadhat.  
2. Kattintson az OK gombra.

## <a name="add-directive-lines"></a>Összes helyutasítási sor
1. Kattintson az Új lehetőségre.
    * Ez az a sorrend, ahogyan a helyutasítási sorok feldolgozása történik a kijelölt munkatétel típusához. A sorrendet módosíthatja ha szükséges.  
2. Adjon meg egy számot a Kezdőmennyiség mezőben.
    * Ez az a legkisebb mennyiség, amely alapján ehhez a sorhoz az irányelv érvényes.  
3. Adjon meg egy számot a Célmennyiség mezőben.
4. Írjon be egy értéket a Mértékegység mezőbe.
    * A Forrásmennyiség egysége és a Célmennyiség egysége van kifejezve. Ha ezt a mezőt üresen hagyja, a program a cikk készletegységét fogja használni.  
5. Egy lehetőség kiválasztása a Helymennyiség mezőben
    * Nincs vagy azonosítótábla mennyisége: az egyes azonosítótáblákon regisztrált mennyiség. Egységekre bontott mennyiség: A teljes mennyiség, amely regisztrálva van. Fennmaradó mennyiség: A mennyiség, amit a beszerzési rendelési sorban regisztrálni kell. Várt mennyiség: A beszerzési rendelési sorban megadott teljes mennyiség.  
6. Jelölje be a Korlátozások egység szerint jelölőnégyzetet, vagy törölje a jelölést.
    * Ha ezt a beállítást választja, és az egységet megadja a Korlátozás egység szerint oldalon, csak a mértékegységgel rendelkező cikkeket teheti a helyre. Például ha a mértékegység PL (raklapok), csak a raklap cikkeit sorolhatja egy adott helyre.  
7. Az Osztás engedélyezése jelölőnégyzet bejelölése vagy a jelölés törlése.
    * Így az utasítás a mennyiséget több helyen szétoszthatja.  
8. Kattintson a Mentés gombra.

## <a name="restrict-the-directive-line-to-a-specific-unit"></a>Az utasítási sor korlátozása egy meghatározott egységre
1. Kattintson a Korlátozás egység szerint elemre.
    * Ez a gomb csak akkor használható, ha lenyomja a Mentés gombot, miután bejelölte a Korlátozás egység szerint jelölőnégyzetet.  
2. Írjon be egy értéket a Mértékegység mezőbe.
3. Zárja be a lapot.

## <a name="add-a-location-directive-action-line"></a>Helyutasítás műveleti sor hozzáadása
1. Kattintson az Új lehetőségre.
    * Ez az a sorrend, ahogyan a helyutasítási műveletsorok feldolgozása történik a kijelölt munkatétel típusához. A sorrendet módosíthatja ha szükséges.  
2. Írjon be egy értéket a Név mezőbe.
    * Ez az utasítási művelet egyedi azonosítója.  
3. Egy lehetőség kiválasztása a Rögzített hely használata mezőben.
    * Rögzített és nem rögzített helyek: A nem rögzített helyek érvényesek, valamint a termék saját rögzített helyei is, a lekérdezésben megadott tartományon belül.  Csak a termék rögzített helyei: A termék rögzített helyei érvényesek, és az összes termékváltozat ugyanazokat a rögzített helyeket osztja meg. Csak a termékváltozatok rögzített helye: Csak az egyes termékváltozatokhoz megadott rögzített helyek érvényesek.  
4. Egy lehetőség kiválasztása a Stratégia mezőben.
    * A Beszerzési rendelés típusú munkarendelések a következő stratégiákat támogatják: nincs: a cikk az első helyen lesz elhelyezve. Konszolidáció: A cikk arra a helyre kerül, ahol hasonló cikkek már elérhetők. Üres hely bejövő munkák nélkül: a cikk az első üres helyre kerül. A hely üresnek minősül, ha nincs fizikailag megjelenő készlete vagy bejövő munkája.  
5. Kattintson a Mentés gombra.

## <a name="edit-the-query-for-directive-action-line"></a>Az utasítási műveletsor lekérdezésének szerkesztése
1. Kattintson A lekérdezés szerkesztése elemre.
2. Kattintson a Hozzáadás gombra.
3. Írja be a „Helyprofil azonosítója” értéket a Mező mezőbe.
    * Ebben a példában a helyprofil-azonosítót használó lehetséges helyeket korlátozzuk.  
4. Érték beírása a Feltétel mezőbe.
5. Kattintson az OK gombra.
    * Az irányelvsorokat és a műveletek irányelveit mindaddig hozzáadhatja, amíg a raktárban minden lehetséges esetet belefoglal.  


