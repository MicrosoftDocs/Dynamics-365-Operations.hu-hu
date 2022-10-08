---
title: Ismételt beszerzési rendelés létrehozása
description: Ez a cikk bemutatja, hogyan hozhat létre ismétlődő beszerzési rendelést (PO) úgy, hogy sorokat másol egy korábbi beszerzésirendelés-dokumentumból egy új beszerzési rendelésbe vagy egy meglévő beszerzési rendelésbe.
author: GalynaFedorova
ms.date: 09/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, PurchCopying
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 335461d60fa0bc92e9711806c6e42643a3f75d02
ms.sourcegitcommit: 073604c07116e0a87f78ab2c76cb89ae83ebba3c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2022
ms.locfileid: "9608111"
---
# <a name="create-a-repeat-purchase-order"></a>Ismételt beszerzési rendelés létrehozása

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja, hogyan hozhat létre ismétlődő beszerzési rendelést (PO) úgy, hogy sorokat másol egy korábbi beszerzésirendelés-dokumentumból egy új beszerzési rendelésbe vagy egy meglévő beszerzési rendelésbe. Kétféleképpen lehetséges az ismételt rendelések létrehozása. Vagy a Művelet Panel dokumentum szintjén elérhető műveleteket vagy a sorrészletek műveleteit használhatja. A dokumentumszintű műveletek célja egy új beszerzési rendelés létrehozása egy másik rendelés sorainak és fejlécadatainak hozzáadásával, míg a sor részletei művelet elsősorban sorok hozzáadására szolgál egy meglévő rendeléshez. Az útmutatóban mutatott példa használható az USMF demo adatok cégben. Ezt a feladatot általában a beszerzési ügynök végzi el.

## <a name="create-a-new-repeat-purchase-order"></a>Új ismételt beszerzési rendelés létrehozása

1. A navigációs ablaktáblán lépjen **a Modulok \> beszerzése és beszerzése \> Beszerzési rendelések \> Minden beszerzési rendelés elemre**. Ajánlatos először elvégezni az információk másolását az új rendeléshez.  
1. Válassza az **Új** lehetőséget.
1. Adja meg az `US-101` értéket a **Szállítói számla** mezőben.
1. Válassza ki az **OK** lehetőséget.
1. A műveleti ablaktáblán nyissa meg a **Beszerzési rendelés** lapot, és a Másolás **csoportban válassza az** Összesből **lehetőséget**. Megnyílik a **Másolás más dokumentumokból** párbeszédpanel. Innen átmásolhatja a meglévő megrendelésekből a megrendelésébe. Különböző módon lehet elvégezni a sorok másolását, illetve különböző dokumentumtípusokat lehet másolni. Ajánlatos először megtekinteni a sorok másolásának módját.
1. Bontsa ki a **Paraméterek** gyorslapot.

    - A **Mennyiségi tényező** akkor hasznos, ha egy olyan mennyiséget kell használnia, amely eltér azon soron található mennyiségtől, amelyből éppen a másolást végzi. Például, ha kétszer annyi mennyiséget szeretne rendelni, mint amennyi azon a soron szerepel, amelyből a másolást végzi, írjon be „2” értéket ebbe a mezőbe, majd ezt követően a rendszer hozzáadja azokat a sorokat, ahol kétszeres az eredeti mennyiség.  
    - Az **Előjel megfordítása** mező szintén támogatja a megrendelt mennyiséget a hozzáadott megrendelési sorokra vonatkozó mennyiség előjelének módosításával. Ez akkor lehet hasznos, ha sztorníroznia kell a tranzakciót azon sorok létrehozásával, amelyek megsemmisítik a tranzakciót. Ez a beállítás automatikusan ki van jelölve a lap **Jóváírás létrehozása műveletből** történő megnyitásakor.  
    - A **Költségek másolása** beállítás lehetővé teszi Önnek a költségek új rendelésbe történő másolását azon dokumentumból, amelyből éppen a rendelési sorokat másolja.  
    - Az **Árak újraszámítása** beállítás az aktuális árakat és engedményeket használja, ahelyett hogy ezeket az információkat azon dokumentumból másolná, ahonnan a többi információ másolását végzi.  
    - A **Pontos másolás** beállítás több mező értékét másolja a rendelés fejlécében és soraiban. Ha ez a beállítás nincs bejelölve, a rendszer az alapértelmezett értékeket használja a szállítóhoz és a termékekhez kapcsolódó számos mezőhöz, akárcsak amikor manuálisan hoz létre új rendelést. Ha például a Másolás pontosan **beállítást Igen** értékre *állítja*, és olyan rendelést másol, amely felülbírálja a szállító alapértelmezett számlaszámláját, akkor ugyanez a számlaszámla átmásolódik az új rendelésbe. Ha a Másolás beállítást pontosan **Nem** értékre *állítja*, akkor a rendszer a szállító alapértelmezett számlaszámláját használja az új rendelésnél. A következő mezők értékeit másolja a rendszer, ha **a Pontos másolás** beállítása *Igen*:
        - Nyelv
        - Fizetési feltételek
        - Fizetési mód
        - Fizetési előírás
        - Számsorozatcsoport
        - Készpénzfizetési engedmény
        - Engedmény százaléka
        - Pénznem
        - Szállítási feltételek
        - Szállítás módja
        - Dimenzió
        - Áfacsoport
        - Áfa felülírása
        - Az árak tartalmazzák az áfát
        - Átvitel
        - Kikötő
        - Statisztikai eljárás
        - Sablon azonosítója
        - Szállítási név
        - Postai cím
        - Hivatkozás
        - Hivatkozási tábla azonosítója
    - A **Beszerzési sorok törlése** beállítás törli az összes olyan beszerzési rendelési sort, amely már létezik azon beszerzési rendelésen, amelybe a másolást végzi, az új sorok alkalmazása előtt. Körültekintően kell használni ezt a lehetőséget, mert minden további figyelmeztetés nélkül törli az összes meglévő sort.  
    - Ha a **Rendelési fejléc másolása** beállítást használja, nem kell manuálisan létrehoznia a fejléc adatait az új rendelésen. Ez a beállítás azt eredményezi, hogy a rendszer az alapértelmezett értékeket használja a szállítóhoz társított mezőkhöz. Ha az a dokumentum, amelyből a másolást végzi, olyan nem alapértelmezett értékekkel rendelkezik, amelyeket másolni kíván, használja a **Pontos másolás** beállítást is.
    - Különböző dokumentumforrások vannak, ahonnan a másolást végezheti és mindegyik külön szakasszal rendelkezik ezen az oldalon. Például a **Beszerzési rendelések** szakasz lehetővé teszi a meglévő beszerzési rendelésekből történő másolást.  

1. A **Beszerzési rendelések** szakaszban válassza ki azokat a sorokat, amelyeket másolni szeretne a vágólapra. Kijelölheti a további beszerzési rendelési sorokat az egyéb beszerzési rendelésekből, illetve másolhatja is azokat az Ön rendeléseibe. Más típusú beszerzési bizonylatokból is hozzáadhat sorokat. A következő néhány lépés különböző beállításokat ismertet.  
1. Bontsa ki a **Megerősítés** szakaszt. Itt választhatja ki azokat a beszerzési rendelések visszaigazolásokat, amelyekből a másolást végezni szeretné. A beszerzési napló azonosító vagy a beszerzési rendelési azonosító azonosítja a beszerzési rendelések visszaigazolásait.  
1. Bontsa ki a **Termékbevételezések** szakaszt. Itt választhatja ki azokat a Termékbevételezési naplókat, amelyekből a másolást végezni szeretné. A termékbevételezési bizonylat vagy a beszerzési rendelés azonosítója azonosítja a termékbevételezési naplókat.
1. Bontsa ki a **Számlák** szakaszt. Itt választhatja ki azokat a szállítói számlákat, amelyekből a másolást végezni szeretné. A számlabizonylat vagy a beszerzési rendelés azonosítója azonosítja a számlákat.
1. Bontsa ki a **Másolandó kijelölt sorok és fejléc** szakaszt. Ez a nézet az összes olyan dokumentum és sor összegzését megjeleníti, amelyet kiválasztott az Ön rendelésébe történő másoláshoz.
1. Válassza ki az **OK** lehetőséget. A rendszer átmásolta a kiválasztott sorokat az új beszerzési rendeléshez.

## <a name="copy-lines-to-an-existing-purchase-order"></a>Sorok másolása egy meglévő beszerzési rendelésbe  

A teljes rendelés másolása helyett inkább azt ajánljuk, hogy hozzon létre egy új beszerzési rendelést és töltse ki a beszerzési rendelés fejlécén lévő információkat, majd ezt követően másolja át a meglévő rendelésekből az egyes sorokat.  

1. Válasszon **Beszerzési rendelés** sort.
1. Válassza ki az **Összesből** elemet. A megjelenő lap azonos a korábban megjelent lappal, de különböző beállítások vannak érvényben, ha a rendelési sorok nézetből van megnyitva. Ellenőrizze a paramétereket.
1. Bontsa ki a **Paraméterek** szakaszt.

    - A **Beszerzési sorok** törlése lehetőség nincs bejelölve. Ez azt jelenti, hogy az új sorokat a meglévő sorok törlése nélkül végezheti el a másolást a megrendelésébe.
    - A **Rendelési fejléc másolása** beállítás sincs bejelölve, mert a rendszer csak további sorokat ad a megrendeléshez.
    - Ebben a példában egy meglévő beszerzési rendelésből másoljuk a sorokat.

1. Válassza ki a sort a kívánt beszerzési rendeléshez. Jegyezze meg, hogy a beszerzési rendelésen egy rendelési sor van kiválasztva.  
1. Válassza ki az **OK** lehetőséget. A további rendelési sor már hozzá lett adva a beszerzési rendeléshez.  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]