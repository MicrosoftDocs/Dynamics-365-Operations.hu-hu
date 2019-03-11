---
title: Ismételt beszerzési rendelés létrehozása
description: Ez az eljárás bemutatja, hogy hogyan lehet egy ismételt beszerzési rendelést (PO) létrehozni azáltal, hogy a sorokat egy korábbi beszerzési rendelési dokumentumból egy új, vagy egy már létező beszerzési rendelésbe másol.
author: FrankDahl
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchCopying
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 74dcee8a614363cf1f1ebc71e3e39a14c59bb774
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "345881"
---
# <a name="create-a-repeat-purchase-order"></a>Ismételt beszerzési rendelés létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogy hogyan lehet egy ismételt beszerzési rendelést (PO) létrehozni azáltal, hogy a sorokat egy korábbi beszerzési rendelési dokumentumból egy új, vagy egy már létező beszerzési rendelésbe másol. Kétféleképpen lehetséges az ismételt rendelések létrehozása. Vagy a Művelet Panel dokumentum szintjén elérhető műveleteket vagy a sorrészletek műveleteit használhatja. A dokumentumszintű műveletek leginkább egy új beszerzési rendelés létrehozására szolgálnak a sorok és egy másik rendelés fejléc információinak hozzáadásával, viszont a soradatok művelete a sorok egy már meglévő rendeléshez történő hozzáadására szolgál. Az útmutatóban mutatott példa használható az USMF demo adatok cégben. Ezt a feladatot általában a beszerzési ügynök végzi el.


## <a name="create-a-new-repeat-purchase-order"></a>Új ismételt beszerzési rendelés létrehozása
1. Ugorjon a Beszerzés és forrás > Beszerzési rendelés > Összes beszerzési rendelés pontra.
    * Ajánlatos először elvégezni az információk másolását az új rendeléshez.  
2. Kattintson az Új lehetőségre.
3. Írja be az „IS-101” értéket a Szállítói számla mezőbe.
4. Kattintson az OK gombra.
5. Kattintson a Beszerzési rendelés lehetőségre a Művelet Panelen.
6. Kattintson az Összesből lehetőségre.
    * Ez az az oldal, ahonnan elvégezheti a másolást a meglévő megrendelésekből az Ön megrendeléséhez. Különböző módon lehet elvégezni a sorok másolását, illetve különböző dokumentumtípusokat lehet másolni. Ajánlatos először megtekinteni a sorok másolásának módját.   
7. Bontsa ki a Paraméterek szakaszt.
    * A Mennyiségi tényező akkor hasznos, ha egy olyan mennyiséget kell használnia, amely eltér azon soron található mennyiségtől, amelyből éppen a másolást végzi. Például, ha kétszer annyi mennyiséget szeretne rendelni, mint amennyi azon a soron szerepel, amelyből a másolást végzi, írjon be „2” értéket ebbe a mezőbe, majd ezt követően a rendszer hozzáadja azokat a sorokat, ahol kétszeres az eredeti mennyiség.  
    * Az Előjel megfordítása mező szintén támogatja a megrendelt mennyiséget a hozzáadott megrendelési sorokra vonatkozó mennyiség előjelének módosításával. Ez akkor lehet hasznos, ha sztorníroznia kell a tranzakciót azon sorok létrehozásával, amelyek megsemmisítik a tranzakciót. Ez a beállítás automatikusan ki van jelölve a lap Jóváírás létrehozása műveletből történő megnyitásakor.  
    * A Másolási díjak beállítás lehetővé teszi Önnek a költségek új rendelésbe történő másolását azon dokumentumból, amelyből éppen a rendelési sorokat másolja.  
    * Az Árak újraszámítása beállítás az aktuális árakat és engedményeket használja, ahelyett hogy ezeket az információkat azon dokumentumból másolná, ahonnan a többi információ másolását végzi.  
    * A Pontos másolás beállítás pontos másolatot készít azon értékekről, amelyek a rendelési dokumentum fejlécén, illetve sorain található mezőkben szerepelnek. Ez a lehetőség nincs bejelölve, ha a rendszer az alapértelmezett értékeket a szállítóhoz és a termékekhez kapcsolódó mezők többségére vonatkozóan használja, csakúgy, mint akkor, ha manuálisan hozta létre az új megrendelést. Például, ha felülírta a szállítóra vonatkozó alapértelmezett Számlafogadót azon rendelés, amelyből éppen a másolást végzi, akkor ugyanazt a Számlafogadót fogja másolni a rendszer az Ön megrendeléséhez. Ha nem jelölte ki a Pontos másolás beállítást, akkor a szállítóra vonatkozó, alapértelmezett Számlafogadót fogja használni helyette a rendszer a rendelésén.  
    * A Beszerzési sorok törlése beállítás törli az összes olyan beszerzési rendelési sort, amely már létezik azon beszerzési rendelésen, amelybe a másolást végzi, az új sorok alkalmazása előtt. Körültekintően kell használni ezt a lehetőséget, mert minden további figyelmeztetés nélkül törli az összes meglévő sort.  
    * Ha a Rendelési fejléc másolása beállítást használja, nem kell manuálisan létrehoznia a fejléc adatait az új rendelésen. Jegyezze meg, hogy ez a beállítás határozza meg azokat az alapértelmezett értékeket, amelyeket a rendszer a szállítóhoz társított mezőkre vonatkozóan használ. Ha az a dokumentum, amelyből a másolást végzi, olyan nem alapértelmezett értékekkel rendelkezik, amelyeket másolni kíván, használja a Pontos másolás beállítást is.  
8. Zárja be a Paraméterek szakaszt.
    * Különböző dokumentumforrások vannak, ahonnan a másolást végezheti és mindegyik külön szakasszal rendelkezik ezen az oldalon. Például a Beszerzési rendelések szakasz lehetővé teszi a meglévő beszerzési rendelésekből történő másolást.  
9. Kattintson a 00015 azonosítóval rendelkező beszerzési rendelés sorra. 
10. Válassza ki a sort, a jelölőnégyzetre kattintva.
11. Törölje a sorhoz tartozó jelölőnégyzetet, így azt nem másolja a rendszer a rendeléséhez.
    * Jelenleg négy olyan sor van kiválasztva, amelyet a beszerzési rendeléséhez kíván másolni. Kijelölheti a további beszerzési rendelési sorokat az egyéb beszerzési rendelésekből, illetve másolhatja is azokat az Ön rendeléseibe. Más típusú beszerzési bizonylatokból is hozzáadhat sorokat. A következő néhány lépés különböző beállításokat ismertet.  
12. Zárja be a Beszerzési rendelések szakaszt.
13. Bontsa ki Megerősítés szakaszt.
    * Itt választhatja ki azokat a beszerzési rendelések visszaigazolásokat, amelyekből a másolást végezni szeretné. A beszerzési napló azonosító vagy a beszerzési rendelési azonosító azonosítja a beszerzési rendelések visszaigazolásait.  
14. Zárja be a Megerősítés szakaszt
15. Bontsa ki a Termékbevételezések szakaszt.
    * Itt választhatja ki azokat a Termékbevételezési naplókat, amelyekből a másolást végezni szeretné. A termékbevételezési bizonylat vagy a beszerzési rendelés azonosítója azonosítja a termékbevételezési naplókat.   
16. Zárja be a Termékbevételezések szakaszt.
17. Bontsa ki a Számlák szakaszt.
    * Itt választhatja ki azokat a szállítói számlákat, amelyekből a másolást végezni szeretné. A számlabizonylat vagy a beszerzési rendelés azonosítója azonosítja a számlákat.   
18. Zárja be a Számlák szakaszt.
19. Bontsa ki a Másolandó kijelölt sorok és fejléc szakaszt.
    * Ez a nézet az összes olyan dokumentum és sor összegzését megjeleníti, amelyet kiválasztott az Ön rendelésébe történő másoláshoz.   
20. Zárja be a Másolandó kijelölt sorok és fejléc szakaszt.
21. Kattintson az OK gombra.
    * A rendszer átmásolta a 4 kiválasztott sort az új beszerzési rendeléshez.   

## <a name="copy-lines-to-an-existing-purchase-order"></a>Sorok másolása egy meglévő beszerzési rendelésbe
    * A teljes rendelés másolása helyett inkább azt ajánljuk, hogy hozzon létre egy új beszerzési rendelést és töltse ki a beszerzési rendelés fejlécén lévő információkat, majd ezt követően másolja át a meglévő rendelésekből az egyes sorokat.  
1. Kattintson a Beszerzési-rendelés sorra.
2. Kattintson az Összesből lehetőségre.
    * A megjelenő lap azonos a korábban megjelent lappal, de különböző beállítások vannak érvényben, ha a rendelési sorok nézetből van megnyitva. Ellenőrizze a paramétereket.   
3. Bontsa ki a Paraméterek szakaszt.
    * Nincs bejelölve a Beszerzési sorok törlése beállítás. Ez azt jelenti, hogy az új sorokat a meglévő sorok törlése nélkül végezheti el a másolást a megrendelésébe.   
    * A Rendelési fejléc másolása beállítás sincs bejelölve, mert a rendszer csak további sorokat ad a megrendeléshez.   
4. Zárja be a Paraméterek szakaszt.
    * Ebben a példában egy meglévő beszerzési rendelésből másoljuk a sorokat.   
5. Kattintson a 00034 azonosítóval rendelkező beszerzési rendelés sorra. 
6. Válassza ki a sort, a jelölőnégyzetre kattintva.
    * Jegyezze meg, hogy a beszerzési rendelésen egy rendelési sor van kiválasztva.  
7. Kattintson az OK gombra.
    * A további rendelési sor már hozzá lett adva a beszerzési rendeléshez.  

