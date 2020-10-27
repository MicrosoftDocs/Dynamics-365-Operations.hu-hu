---
title: Helyutasítás beállítása beszerzési rendelés eltárolásához
description: Ez a témakör bemutatja, hogyan állíthat be egyszerű helyutasítást.
author: ShylaThompson
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c14fb92103fdd3c32ebc287a74a5dc4f4882b0e
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981945"
---
# <a name="set-up-a-location-directive-for-purchase-order-put-away"></a>Helyutasítás beállítása beszerzési rendelés eltárolásához

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogyan állíthat be egyszerű helyutasítást. A példa egy helyutasítást hoz létre ahhoz, hogy a beszerzési rendelés bevételezett cikkeinek helyét meg lehessen határozni. Ezt a feladatleírást lejátszhatja az USMF bemutatócégnél említett adatokkal. Előzetes feltételek: Intézkedési kódot kell létrehoznia. Ebben az eljárásban egy Relabel nevű intézkedési kódot alkalmazunk. Ha helyutasítást hoz létre a saját adataiban, a raktárhoz és a cikkekhez speciális raktárkezelési beállítást kell megadnia. Ezt az eljárást a raktári vezető használja.

1. A navigációs ablaktáblán ugorjon a **Modulok > Raktárkezelés > Beállítás > Helyutasítások** lehetőségre.
2. A **Munka rendeléstípusa** mezőben válassza ki a **Beszerzési rendelések** elemet.

## <a name="create-a-location-directive-header"></a>Helyutasítási műveletek fejléc létrehozása
1. Válassza az **Új** lehetőséget.
2. Adjon meg egy számot a **Sorozatszám** mezőben. Ez az a sorrend, ahogyan a helyutasítás feldolgozása történik a kijelölt munkatétel típusához. A sorrendet módosíthatja ha szükséges.  
3. Írjon be egy értéket a **Név** mezőbe. Ez ennek az utasításnak az egyedi azonosítója.  
4. A **Munkatípus** mezőben válassza a **Betárolás** lehetőséget. A másolandó mezőtípusok kijelölése. A Beszerzési rendelés munkarendelés-típusnál az utasítás egyetlen támogatott értéke a **Betárolás** .  
5. Adjon meg egy értéket a **Telephely** mezőben.
6. Érték beírása a **Raktár** mezőbe. Az Irányelv kódja mezőt hagyja üresen.  Az utasításkódokat a Betárolási típusú munkarendeléssor csatolásához használjuk egy adott irányelvhez. A beszerzési rendelések esetében a betárolás típusú utolsó munkarendeléssor feloldása a munkasablon meghatározása előtt történik meg. Ezért nem lehet hozzákapcsolódni a munkasablon utolsó sorát egy adott irányelvhez.   
7. Adjon meg egy értéket az **Intézkedési kód** mezőben. Az Intézkedési kód korlátozza a helyutasítás használatát, így a helyutasítás csak akkor használható, ha a raktári dolgozó bevisz egy adott értéket a cikk regisztrálása során a mobileszközön.  
8. Válassza a **Mentés** lehetőséget.

## <a name="edit-the-query-for-directive"></a>Az utasítás lekérdezésének szerkesztése
1. Válassza ki a **Lekérdezés szerkesztése** lehetőséget. Ennek az irányelvnek a felhasználása már korlátozódik az adott raktárban regisztrált cikkekre, az adott intézkedési kóddal. A lekérdezéssel egyéb korlátokat is hozzáadhat.  
2. Válassza ki az **OK** lehetőséget.

## <a name="add-directive-lines"></a>Összes helyutasítási sor
1. Válassza az **Új** lehetőséget. Ez az a sorrend, ahogyan a helyutasítási sorok feldolgozása történik a kijelölt munkatétel típusához. A sorrendet módosíthatja ha szükséges.  
2. Adjon meg egy számot a **Kezdőmennyiség** mezőben. Ez az a legkisebb mennyiség, amely alapján ehhez a sorhoz az irányelv érvényes.  
3. Adjon meg egy számot a **Célmennyiség** mezőben.
4. Írjon be egy értéket a **Mértékegység** mezőbe. A Forrásmennyiség egysége és a Célmennyiség egysége van kifejezve. Ha ezt a mezőt üresen hagyja, a program a cikk készletegységét fogja használni.  
5. Válassza ki az egyik lehetőséget a **Mennyiség megkeresése** mezőben.
    - Nincs vagy azonosítótábla mennyisége: az egyes azonosítótáblákon regisztrált mennyiség.  
    - Egységekre bontott mennyiség: A teljes mennyiség, amely regisztrálva van.  
    - Fennmaradó mennyiség: A mennyiség, amit a beszerzési rendelési sorban regisztrálni kell.  
    - Várt mennyiség: A beszerzési rendelési sorban megadott teljes mennyiség.  
6. Jelölje be a **Korlátozások egység szerint** jelölőnégyzetet, vagy törölje a jelölést. Ha ezt a beállítást választja, és az egységet megadja a **Korlátozás egység szerint** oldalon, csak a mértékegységgel rendelkező cikkeket teheti a helyre. Például ha a mértékegység PL (raklapok), csak a raklap cikkeit sorolhatja egy adott helyre.  
7. Jelölje be az **Osztás engedélyezése** jelölőnégyzetet, vagy törölje a jelölést. Így az utasítás a mennyiséget több helyen szétoszthatja.  
8. Válassza a **Mentés** lehetőséget.

## <a name="restrict-the-directive-line-to-a-specific-unit"></a>Az utasítási sor korlátozása egy meghatározott egységre
1. Válassza ki a **Korlátozás egység szerint** lehetőséget. Ez a gomb csak akkor használható, ha lenyomja a **Mentés** gombot, miután bejelölte a **Korlátozás egység szerint** jelölőnégyzetet.  
2. Írjon be egy értéket a **Mértékegység** mezőbe.
3. Zárja be a lapot.

## <a name="add-a-location-directive-action-line"></a>Helyutasítás műveleti sor hozzáadása
1. Válassza az **Új** lehetőséget. Ez az a sorrend, ahogyan a helyutasítási műveletsorok feldolgozása történik a kijelölt munkatétel típusához. A sorrendet módosíthatja ha szükséges.  
2. Írjon be egy értéket a **Név** mezőbe. Ez az utasítási művelet egyedi azonosítója.  
3. Válassza ki az egyik lehetőséget a **Rögzített hely használata** mezőben.
    - Rögzített és nem rögzített helyek: A nem rögzített helyek érvényesek, valamint a termék saját rögzített helyei is, a lekérdezésben megadott tartományon belül.  
    - Csak a termék rögzített helyei: A termék rögzített helyei érvényesek, és az összes termékváltozat ugyanazokat a rögzített helyeket osztja meg.  
    - Csak a termékváltozatok rögzített helye: Csak az egyes termékváltozatokhoz megadott rögzített helyek érvényesek.  
4. Válassza ki az egyik lehetőséget a **Stratégia** mezőben. A beszerzési rendelés típus munkarendelései a következő stratégiák támogatják: 
    - Egyik sem: a cikk az első talált helyre kerül.  
    - Konszolidáció: A cikk arra a helyre kerül, ahol hasonló cikkek már elérhetők.  
    - Üres hely bejövő munkák nélkül: a cikk az első üres helyre kerül. A hely üresnek minősül, ha nincs fizikailag megjelenő készlete vagy bejövő munkája.  
5. Válassza a **Mentés** lehetőséget.

## <a name="edit-the-query-for-directive-action-line"></a>Az utasítási műveletsor lekérdezésének szerkesztése
1. Válassza ki a **Lekérdezés szerkesztése** lehetőséget.
2. Válassza a **Hozzáadás** lehetőséget.
3. A **Mező** mezőben adja meg a `location profile ID` értéket. Ebben a példában a helyprofil-azonosítót használó lehetséges helyeket korlátozzuk.  
4. Adjon meg egy értéket a **Feltétel** mezőben.
5. Válassza ki az **OK** lehetőséget. Az irányelvsorokat és a műveletek irányelveit mindaddig hozzáadhatja, amíg a raktárban minden lehetséges esetet belefoglal.  

