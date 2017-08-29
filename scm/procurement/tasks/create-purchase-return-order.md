--- 
title: "Beszerzési visszárurendelés létrehozása"
description: "Ez az eljárás bemutatja, hogyan hozzon létre beszerzési visszárurendelést a Jóváírás művelettel, hogy átmásolja a sorokat a szállítói számla dokumentumából egy új Beszerzési rendelésbe."
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 45d5eb62abd916316ffc323727035b77760cd30d
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-purchase-return-order"></a>Beszerzési visszárurendelés létrehozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan hozzon létre beszerzési visszárurendelést a Jóváírás művelettel, hogy átmásolja a sorokat a szállítói számla dokumentumából egy új Beszerzési rendelésbe. Azt is bemutatja, hogyan lehet a rendelést megerősíteni és visszaküldeni árukat a szállítónak. Az eljárásban mutatott példa használható az USMF demo adatok cégben. Ezt a feladatot általában a beszerzési ügynök végzi el.


## <a name="create-a-new-purchase-return-order"></a>Új visszárurendelés létrehozása
1. Ugorjon a Beszerzés és forrás > Beszerzési rendelés > Összes beszerzési rendelés pontra.
    * Az első lépés, egy új beszerzési rendelés létrehozása, amit a beszerzési visszárurendeléshez fog használni.  
2. Kattintson az Új lehetőségre.
3. Írja be az „IS-102” értéket a Szállítói számla mezőbe.
4. Kattintson az OK gombra.
5. A Művelet panelen kattintson a Beszerzés elemre.
6. Kattintson a Jóváírás elemre.
    * Ez az az oldal, ahonnan elvégezheti a másolást a meglévő szállítói számlákból az Ön visszárurendeléséhez. Ez ugyanaz az oldal, amit az egyéb másolások során használt. De mivel a Jóváírás tevékenységből nyitottuk meg, az oldal a szállítói számlákat ellentételező visszárurendelés létrehozásának támogatására van beállítva.  
7. Bontsa ki a Paraméterek szakaszt.
    * Az Előjel megfordítása beállítás automatikusan be van jelölve, és nem lehet módosítani. Ez biztosítja, hogy a mennyiségek előjele megváltozik és a felvett rendelési sorok ellentételezni fogják a szállítói számlát.  
    * A Díjak másolása beállítás automatikusan be van jelölve, és nem lehet módosítani. Ez azt jelenti, hogy a szállítói számla költségek hozzáadódnak a beszerzési visszárurendeléshez, így ellentételezve az eredeti költséget. Később lehet módosítani a változásokat a rendelés fejlécében és soraiban.  
    * A Pontos másolás beállítás automatikusan be van jelölve, és nem lehet módosítani. Ez biztosítja, hogy egy pontos másolat készül a szállítói számla fejlécének és sorainak összes mezőjének értékeiről. Ez azt jelenti, hogy egy beszerzési visszárurendelés készült a szállítói számla dokumentumán használt összes feltételnek megfelelő értékekkel.  
    * A Beszerzési sorok törlése beállítás törli az összes olyan beszerzési rendelési sort, amely már létezik azon beszerzési rendelésen, az új sorok hozzáadása előtt. Ebben a példában még nem adtunk hozzá semmilyen beszerzési visszárurendelés sort, így ennek nem lesz hatása. Körültekintően kell használni ezt a lehetőséget, mert minden további figyelmeztetés nélkül törli az összes meglévő sort.  
    * A Rendelés fejlécének másolása beállítás automatikusan be van jelölve, és nem lehet módosítani. Ez biztosítja, hogy az adatot átmásolja a szállítói számláról és alkalmazza a beszerzési visszárurendelés fejlécére. Ez azért hasznos, mert ez elősegíti, hogy a beszerzési visszárurendelés hasonló feltételek használatával ellentételezze a számlát.  
8. Zárja be a Paraméterek szakaszt.
9. Bontsa ki a Számlák szakaszt.
    * Az oldalt a Jóváírás műveletből nyitottuk meg, így az egyetlen elérhető lehetőség a szállítói számláról történő adatok másolása. Ezen a lapon láthatók a rendelkezésre álló számlák, amelyek szerepelnek az Ön által korábban létrehozott beszerzési visszárurendelésben megadott szállítói számlában.   A számlákat a számlabizonylat vagy a beszerzési rendelés azonosítója azonosítja.  
10. Keresse meg az AP-0006 számlaszámmal jelzett szállítói számlát, és kattintson a sor bármelyik mezőjére, hogy kiemelje a sort.
11. Válassza ki a sort, a sorhoz tartozó jelölőnégyzetre kattintva. 
    * Vegye észre, hogy a szállítói számlán elérhető sorok a rendeléssel együtt automatikusan ki vannak választva. Ez az adott szállítói számla 2 rendeléssorral rendelkezik. Ebben a példában, a második sorban lévő mennyiségnek egy részét fogjuk visszaküldeni.  
12. Jelölje ki a második sort (az M0006 elemmel) olyan mezőre kattintva, ami ebben a sorban szerepel.
13. A Mennyiség mező értékét módosítsa 10-re. Ez az a mennyiség, amelyet a szállítónak vissza fognak küldeni. 
14. Jelölje ki az első sort (az M0005 elemmel), olyan mezőre kattintva, ami ebben a sorban szerepel.
15. Törölje az első sorhoz tartozó jelölőnégyzetet.
    * Csak az Ön által kiválasztott sorok lesznek átmásolva a rendelésébe.  
16. Zárja be a Számlák szakaszt.
17. Bontsa ki a Másolandó kijelölt sorok és fejléc szakaszt.
    * Ez a nézet jeleníti meg az összes rendelésbe másolásra kijelölt dokumentum és sor összegzését.  
18. Zárja be a Másolandó kijelölt sorok és fejléc szakaszt.
19. Kattintson az OK gombra.
    * A kiválasztott sor most át lett másolva a beszerzési visszárurendeléséhez. A mennyiség mező -10-et mutat.   
20. Kattintson a Készlet parancsra.
21. Kattintson a Jelölés lehetőségre.
    * A létrehozott rendelési sor a szállítói számlából származó készlettranzakció ellentételeként van megjelölve. Ez biztosítja, hogy a szállítónak visszaküldött készlet ugyanaz, mint a korábban tőlük beérkeztetett készlet. Vannak olyan helyzetek, amikor a jelölés nem történik meg, például, ha a készlet már Felhasználtnak lett jelölve, vagy ha a termék olyan, amin nem használható jelölés.  
22. Kattintson az OK gombra.

## <a name="confirm-and-record-the-shipment-of-goods"></a>Erősítse meg, és rögzítse az áruk szállítását
1. Kattintson a Megerősítés gombra.
2. A Művelet panelen kattintson a Bevételezés elemre.
3. Kattintson a Termékbevételezés elemre.
    * Ez a lap termékbevételezés beszerzési rendelésekhez és az áru visszaküldése a szállítónak folyamat rögzítésére szolgál. A negatív mennyiséget tartalmazó rendeléssorok az jelentik, hogy ezek visszárukat a szállítónak, és az ezen a lapon generálható dokumentum szállítólevélként is használható.   
    * A Mennyiség mezőben, válassza ki az ennél a példánál a Megrendelt mennyiséget.   Ez biztosítja, hogy a szállítmány fel lesz dolgozva a teljes megrendelt mennyiségre, amivel a rendeléssorokat készítették.   
4. Írjon be egy értéket a Termékbevételezés mezőbe.
    * Ezzel a mezővel lehet megadni olyan hivatkozást, ami egy bizonylatként lesz használva a termék bevételezési naplójához.  
5. Kattintson az OK gombra.
    * Az áruk most már szállítottként szerepelnek a beszerzési visszáru rendelésen és egy termékbevételezési napló lett létrehozva. Használhatja a Termék-bevételezési műveletet, hogy áttekintse a beszerzési rendeléshez létrehozott naplókat, és láthatja, hogy mi érkezett vagy lett visszaszállítva és mikor.  


