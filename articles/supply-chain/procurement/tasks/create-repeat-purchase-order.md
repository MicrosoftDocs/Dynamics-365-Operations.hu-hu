---
title: Ismételt beszerzési rendelés létrehozása
description: Ez a témakör bemutatja, hogy hogyan lehet egy ismételt beszerzési rendelést (PO) létrehozni azáltal, hogy a sorokat egy korábbi beszerzési rendelési dokumentumból egy új, vagy egy már létező beszerzési rendelésbe másol.
author: kamaybac
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, PurchCopying
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b75d8414e40d65267494eb495bf99daa62b3e2d5850db27ecae99f30d543c870
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719599"
---
# <a name="create-a-repeat-purchase-order"></a>Ismételt beszerzési rendelés létrehozása

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogy hogyan lehet egy ismételt beszerzési rendelést (PO) létrehozni azáltal, hogy a sorokat egy korábbi beszerzési rendelési dokumentumból egy új, vagy egy már létező beszerzési rendelésbe másol. Kétféleképpen lehetséges az ismételt rendelések létrehozása. Vagy a Művelet Panel dokumentum szintjén elérhető műveleteket vagy a sorrészletek műveleteit használhatja. A dokumentumszintű műveletek leginkább egy új beszerzési rendelés létrehozására szolgálnak a sorok és egy másik rendelés fejléc információinak hozzáadásával, viszont a soradatok művelete a sorok egy már meglévő rendeléshez történő hozzáadására szolgál. Az útmutatóban mutatott példa használható az USMF demo adatok cégben. Ezt a feladatot általában a beszerzési ügynök végzi el.


## <a name="create-a-new-repeat-purchase-order"></a>Új ismételt beszerzési rendelés létrehozása
1. Navigációs ablaktáblán ugorjon a **Modulok > Beszerzés és forrás > Beszerzési rendelések > Összes beszerzési rendelés** elemre. Ajánlatos először elvégezni az információk másolását az új rendeléshez.  
2. Válassza az **Új** lehetőséget.
3. Adja meg az `US-101` értéket a **Szállítói számla** mezőben.
4. Válassza ki az **OK** lehetőséget.
5. Kattintson a Művelet panelen a **Beszerzési rendelés** lehetőségre.
6. Válassza ki az **Összesből** elemet. Ez az az oldal, ahonnan elvégezheti a másolást a meglévő megrendelésekből az Ön megrendeléséhez. Különböző módon lehet elvégezni a sorok másolását, illetve különböző dokumentumtípusokat lehet másolni. Ajánlatos először megtekinteni a sorok másolásának módját. 
7. Bontsa ki a **Paraméterek** szakaszt.

    - A **Mennyiségi tényező** akkor hasznos, ha egy olyan mennyiséget kell használnia, amely eltér azon soron található mennyiségtől, amelyből éppen a másolást végzi. Például, ha kétszer annyi mennyiséget szeretne rendelni, mint amennyi azon a soron szerepel, amelyből a másolást végzi, írjon be „2” értéket ebbe a mezőbe, majd ezt követően a rendszer hozzáadja azokat a sorokat, ahol kétszeres az eredeti mennyiség.  
    - Az **Előjel megfordítása** mező szintén támogatja a megrendelt mennyiséget a hozzáadott megrendelési sorokra vonatkozó mennyiség előjelének módosításával. Ez akkor lehet hasznos, ha sztorníroznia kell a tranzakciót azon sorok létrehozásával, amelyek megsemmisítik a tranzakciót. Ez a beállítás automatikusan ki van jelölve a lap **Jóváírás létrehozása műveletből** történő megnyitásakor.  
    - A **Költségek másolása** beállítás lehetővé teszi Önnek a költségek új rendelésbe történő másolását azon dokumentumból, amelyből éppen a rendelési sorokat másolja.  
    - Az **Árak újraszámítása** beállítás az aktuális árakat és engedményeket használja, ahelyett hogy ezeket az információkat azon dokumentumból másolná, ahonnan a többi információ másolását végzi.  
    - A **Pontos másolás** beállítás pontos másolatot készít azon értékekről, amelyek a rendelési dokumentum fejlécén, illetve sorain található mezőkben szerepelnek. Ez a lehetőség nincs bejelölve, ha a rendszer az alapértelmezett értékeket a szállítóhoz és a termékekhez kapcsolódó mezők többségére vonatkozóan használja, csakúgy, mint akkor, ha manuálisan hozta létre az új megrendelést. Például, ha felülírta a szállítóra vonatkozó alapértelmezett Számlafogadót azon rendelés, amelyből éppen a másolást végzi, akkor ugyanazt a Számlafogadót fogja másolni a rendszer az Ön megrendeléséhez. Ha nem jelölte ki a **Pontos másolás** beállítást, akkor a szállítóra vonatkozó, alapértelmezett Számlafogadót fogja használni helyette a rendszer a rendelésén.  
    - A **Beszerzési sorok törlése** beállítás törli az összes olyan beszerzési rendelési sort, amely már létezik azon beszerzési rendelésen, amelybe a másolást végzi, az új sorok alkalmazása előtt. Körültekintően kell használni ezt a lehetőséget, mert minden további figyelmeztetés nélkül törli az összes meglévő sort.  
    - Ha a **Rendelési fejléc másolása** beállítást használja, nem kell manuálisan létrehoznia a fejléc adatait az új rendelésen. Jegyezze meg, hogy ez a beállítás határozza meg azokat az alapértelmezett értékeket, amelyeket a rendszer a szállítóhoz társított mezőkre vonatkozóan használ. Ha az a dokumentum, amelyből a másolást végzi, olyan nem alapértelmezett értékekkel rendelkezik, amelyeket másolni kíván, használja a **Pontos másolás** beállítást is.   
    - Különböző dokumentumforrások vannak, ahonnan a másolást végezheti és mindegyik külön szakasszal rendelkezik ezen az oldalon. Például a **Beszerzési rendelések** szakasz lehetővé teszi a meglévő beszerzési rendelésekből történő másolást.  

8. A **Beszerzési rendelések** szakaszban válassza ki azokat a sorokat, amelyeket másolni szeretne a vágólapra. Kijelölheti a további beszerzési rendelési sorokat az egyéb beszerzési rendelésekből, illetve másolhatja is azokat az Ön rendeléseibe. Más típusú beszerzési bizonylatokból is hozzáadhat sorokat. A következő néhány lépés különböző beállításokat ismertet.  
9. Bontsa ki a **Megerősítés** szakaszt. Itt választhatja ki azokat a beszerzési rendelések visszaigazolásokat, amelyekből a másolást végezni szeretné. A beszerzési napló azonosító vagy a beszerzési rendelési azonosító azonosítja a beszerzési rendelések visszaigazolásait.  
10. Bontsa ki a **Termékbevételezések** szakaszt. Itt választhatja ki azokat a Termékbevételezési naplókat, amelyekből a másolást végezni szeretné. A termékbevételezési bizonylat vagy a beszerzési rendelés azonosítója azonosítja a termékbevételezési naplókat.   
11. Bontsa ki a **Számlák** szakaszt. Itt választhatja ki azokat a szállítói számlákat, amelyekből a másolást végezni szeretné. A számlabizonylat vagy a beszerzési rendelés azonosítója azonosítja a számlákat.   
12. Bontsa ki a **Másolandó kijelölt sorok és fejléc** szakaszt. Ez a nézet az összes olyan dokumentum és sor összegzését megjeleníti, amelyet kiválasztott az Ön rendelésébe történő másoláshoz.   
13. Válassza ki az **OK** lehetőséget. A rendszer átmásolta a kiválasztott sorokat az új beszerzési rendeléshez.   

## <a name="copy-lines-to-an-existing-purchase-order"></a>Sorok másolása egy meglévő beszerzési rendelésbe  

A teljes rendelés másolása helyett inkább azt ajánljuk, hogy hozzon létre egy új beszerzési rendelést és töltse ki a beszerzési rendelés fejlécén lévő információkat, majd ezt követően másolja át a meglévő rendelésekből az egyes sorokat.  

1. Válasszon **Beszerzési rendelés** sort.
2. Válassza ki az **Összesből** elemet. A megjelenő lap azonos a korábban megjelent lappal, de különböző beállítások vannak érvényben, ha a rendelési sorok nézetből van megnyitva. Ellenőrizze a paramétereket.   
3. Bontsa ki a **Paraméterek** szakaszt.

    - Nincs bejelölve a **Beszerzési sorok törlése** beállítás. Ez azt jelenti, hogy az új sorokat a meglévő sorok törlése nélkül végezheti el a másolást a megrendelésébe.   
    - A **Rendelési fejléc másolása** beállítás sincs bejelölve, mert a rendszer csak további sorokat ad a megrendeléshez.   
    - Ebben a példában egy meglévő beszerzési rendelésből másoljuk a sorokat.   

4. Válassza ki a sort a kívánt beszerzési rendeléshez. Jegyezze meg, hogy a beszerzési rendelésen egy rendelési sor van kiválasztva.  
5. Válassza ki az **OK** lehetőséget. A további rendelési sor már hozzá lett adva a beszerzési rendeléshez.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]