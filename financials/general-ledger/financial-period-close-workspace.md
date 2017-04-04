---
title: "Pénzügyi időszak lezárása munkaterület"
description: "Ez a cikk betekintést nyújt a Pénzügyi időszak zárásának munkaterületébe és az ehhez társított beállításokba."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerPeriodCloseProjectWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13791
ms.assetid: 6ee51758-639b-448e-9cb2-56cf1d804273
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: ba0d709d123f56edb2a5287376c06c1f41181b1c
ms.lasthandoff: 03/31/2017


---

# <a name="financial-period-close-workspace"></a>Pénzügyi időszak lezárása munkaterület

Ez a cikk betekintést nyújt a Pénzügyi időszak zárásának munkaterületébe és az ehhez társított beállításokba.

Pénzügyi időszak lezárása munkaterület

A **a pénzügyi időszak lezárása** munkaterület segítségével nyomon követhetők a záró pénzügyi folyamatok a vállalatok, a területek és a személyek között. Attól függően, hogy a nézet a **a pénzügyi időszak lezárása** munkaterület, látni fogja, vagy a feladatok és a záró ütemezés, vagy csak az Önhöz rendelt feladatok állapotokat. 

A munkaterület tetején záró ütemezés először ki kell választania. Minden adat a munkaterületen megjelenő majd a kijelölt záró ütemezés szerint van szűrve.

### <a name="summary-tiles"></a>Összesítő csempék

Az **Összefoglaló** csempéken áttekintheti a folyamatokat és az indikátorok segítenek a zárási folyamat kivitelezésében. Feladatok múltbeli esedékes, a fennmaradó tevékenységek ma, ma esedékesek, de a függőségek miatt blokkolt feladatok és a folyamat további feladatok láthatók. Ez az információ a kijelölt záró engedményes listában szereplő összes vállalat szolgál.

### <a name="tasks-and-status-section"></a>Feladatok és állapot szakasz

A a **feladatok és állapot** szakaszban, a teljes állapotának záró ütemezés többféle módon oszlanak meg: vállalat, területenként állapot és állapot szerint felelős személy állapota. A záró feladatok ütemezése, csak feladatok határidejeként a mai napon, az állapota megtekinthető vagy feladatok, amelyek lejárt határidejű úgy módosítani a szűrőt a kártya lista tetején. Egy adott vállalat állapotának megtekintése a vállalat szűrőt is megadhat. Minden állapota lap adja meg százalékban elkészült és a maradó feladatok száma szerinti bontásban. Kattintson a kártyára vagy a **részletek megtekintése** művelet a kijelölt kártya részletes tevékenység szűrni. 

Az utolsó lapon van részletes a feladatlista. A lista mutatja a teljes és szűrhetők, hogy csak azok a feladatok, amelyek a bennünket érdeklő. A feladatlista többféle módon végezhet. Szűrhet például feladat dátuma, a társult vállalkozás és a hozzá tartozó terület. Választhatja azt is, megjelenítése vagy elrejtése a befejezett feladatokat a feladatlistában. 

Két kijelző használatos a feladatokhoz:

-   Egy felkiáltójel-ikon azt jelzi, hogy a tevékenység lejárt. Lejárt határidejű feladatok esetében a határidő is vörös színnel lesz kiemelve.
-   Egy lakatot ábrázoló ikon azt jelzi, hogy a feladat függ, egyéb feladatok, amelyek nem fejeződött be. Egy tevékenység, amely blokkolja a függőségek nem lehet megjelölni, befejezését követően. Egy tevékenység függőségei segítségével állíthatjuk be a **függőség beállítása** művelet.

A tevékenység neve a Műveletek lap vagy más weblap Microsoft Dynamics 365 mutató hivatkozás, ahol a felhasználónak kell lépnie a munka elvégzéséhez. E hivatkozás segítségével is beállíthatjuk a **tevékenységkapcsolat** mezőt a tevékenység létrehozása vagy szerkesztése. 

Csatolhat fájlokat, jegyzetek, képek és URL-címek egy feladat segítségével a **a mellékletek** művelet. Például jelzik a napló számok, amelyek a tevékenység részeként, megjegyzéseket fűzhet az adott tevékenységre, vagy fájlt csatol egy jelentésben kinyomtatott feladat. Egy ikon jelenik meg a **melléklet** a feladat, ha a melléklet e oszlop. 

A **tevékenység teljes** kézi beállítást a feladat befejezése után. A tevékenység befejezésekor jelölt a **dátum szerzett** mező automatikusan frissül az aktuális dátum és idő. Függőség mutatók szükség szerint frissül.

## <a name="all-financial-period-close-tasks-list-page"></a>Összes pénzügyi időszak lezárási feladatainak listaoldala
Minden jelenlegi és az előző időszak bezárás feladatokat is megtekintheti a **tevékenységek minden pénzügyi időszak lezárása** lista lap. A lista lap leginkább használatos a zárási folyamat történeti elemzésre, mert az ütemezett kapcsolatos információkat tartalmaz határidejét, a tényleges befejezési dátuma, valamint az a személy, aki végrehajtotta a feladatot. Jelentések és vizsgálati célokból egyszerűen exportálja a lista lapon található információkat Microsoft Excel.

## <a name="financial-period-close-configuration-page"></a>Pénzügyi időszak lezárási konfigurációs oldala
Használata előtt a **a pénzügyi időszak lezárása** munkaterület, be kell állítania a folyamat a Microsoft Dynamics 365 műveletek segítségével a **pénzügyi időszak lezárása konfigurációs** oldalon. (Kattintson a **főkönyvi**&gt;**időszak zárja be a**&gt;**pénzügyi időszak lezárása konfigurációs**.)

### <a name="resources"></a>Erőforrások

A a **erőforrásokat** lapon megadhatja a zárási folyamat részt vevő személyek. Minden alkalmazott, aki felelős a záró feladat lesz először itt kell rendelni. Meg kell adnia az alkalmazott nézet a munkaterület. Az alábbi lehetőségek közül választhat:

-   **Kizárólag hozzárendelt tevékenységek** – A felhasználó csak a hozzárendelt feladatait látja.
-   **Feladatok és állapot** – A felhasználó teljes folyamat minden lezárási feladatot és állapotot lát.

A felhasználók, akik csak a saját feladataik megtekintéséhez rendelkeznek engedéllyel nem tudnak feladatot adni a feladatlistához, feladatot szerkeszteni vagy feladatot eltávolítani a feladatlistáról.

### <a name="task-areas"></a>Feladatterületek

Használhat logikai feladatterületeket a szervezeten belül, csoportos zárási feladatokhoz. Például a Kötelezettségek, Kinnlevőségek vagy a Főkönyv használható feladatterületként.

### <a name="calendars"></a>Naptárak

Létrehozása és szerkesztése a záró pénzügyi naptárak naptárak lapján.  Ez az, ahol határozza meg a munkanap záró folyamatokat, és zárási feladatok ütemezése fogja használni.  Új naptár létrehozása, és adja meg a munkanap a tevékenységek ütemezésére használható.  A legcélszerűbb naptár létrehozása hosszú ideig, mint egy év vagy több év óta létrehozása után is módosíthatók.  Miután létrehozta a naptár, kattintson a Szerkesztés gombra az adott napra, például a munkaszüneti napokat a naptárban frissítése.  Feladat bezárása azokon a napokon, amikor a vezérlőelem értéke nyitott lesz ütemezve.  Záró feladatok ütemezése egy meghatározott napon nem lehet, ha azt a napot kell a vezérlőelemben lévő érték lezárva értékűre.

### <a name="templates"></a>Sablonok

Pénzügyi szoros sablont használ a zárási folyamat részét képező összes feladatok definiálásához. A záró feladat egy ismétlődő munka tevékenység elvégzéséhez minden zárási folyamat részeként az egyén rendelt. A sablon egy relatív határidő dátumát meg kell adni minden záró feladat. A relatív esedékességi dátum előtti napok száma, vagy a meghatározott időszak záró dátuma után a feladatnak el kell készülnie minden időszakban. Esedékesség időpontja is minden tevékenységhez van rendelve. Az esedékességi idő környezetével az időzónát állítja be, és minden felhasználó számára az időzóna konvertálja. 

Feladat a sablon rendelhet egy vagy több társaság, ahol ez a feladat vonatkozik. Ha egy másik személy töltse ki, hogy minden egyes vállalat munka erőkifejtés van rendelve, akkor hasznos lehet az azonos munka erőfeszítések több feladatok létrehozása. Külön feladat létrehozása minden egyes vállalathoz. 

A **tevékenységkapcsolat** menüpont társítva a tevékenység munka erőfeszítés, és a munkaterület feladat hivatkozás közvetlenül a kapcsolódó lap megnyitásához is használható. Például össze kell kapcsolni a záró feladat futtatása kötelezettségek pénznem átértékelés folyamatát és a hozzájuk kapcsolódó **árfolyam-korrekció** a Microsoft Dynamics 365 műveletek lap. Külső URL-címet is hivatkozhat. 

> [! Emlékeztető] Ha szeretné egy adott Management Reporter jelentés a pénzügyi időszak bezárás tevékenységre mutató hivatkozás, használhatja a jelentés URL-címe. A jelentés URL-cím elérésére a report designer nyissuk meg a jelentést, és kattintson **fájl**&gt;**jelentés megtekintése**, egy webböngészőben nyissa meg a jelentést. Ezután bemásolhatja az URL-címet a böngésző címsorába, és beillesztheti a **Feladathivatkozás** **URL** cím mezőbe. 

Tevékenységfüggőségek meghatározhatja a sablonban. Ha egy feladat függ, hogy egy vagy több feladatot is van, ezt a feladatot nem lehet megjelölni, befejezését követően a függőségeket befejezéséig. 

Pénzügyi szoros több sablont is létrehozhat. A különböző sablonokat használ különböző zárási folyamatok nyomon követésére vagy különböző időszaktípusok Záró hónap vagy év végén, a zárási folyamatok nyomon követésére használhatja. Egy sablon létrehozását követően másolja azt egy új sablont, és végezze el a szükséges módosításokat. Csak egy sablon rendelhet minden egyes záró ütemezés.

### <a name="closing-schedules"></a>Lezárási ütemezések

Ütemterv záró pénzügyi szoros sablon rendelhet egy adott pénzügyi időszakban, be kell zárni. A feladatokat a sablonból majd automatikusan létrehozza az adott időszakra vonatkozóan, és az új záró ütemezés kell hozzáadni a munkaterülethez. Egy új záró ütemezés létrehozása a **időszak záró dátuma** mező segítségével meghatározható, hogy a tényleges fizetési dátuma a relatív alapuló záró feladatok teljesítési határidejét a pénzügyi szoros sablon hozzá van rendelve. 

Rendelje hozzá a naptár megfelelő záró ütemezés, a tevékenységek ütemezésére használható munkanapon belül jelzi. Ha nem definiálunk egy naptárat, az esedékes Tevékenységdátumok fogják használni a hét minden napján. 

A vállalatok a záró ütemezés rendelendő is meg kell adni. Ha több vállalat sablon tevékenységeket rendel, külön feladatokat minden vállalathoz, amely a záró ütemezését, és a sablon tevékenységhez rendelt hozható létre. 

Záró ütemezés befejezése után jelölje ki a **zárt** lehetőség. A feladatelőzmények továbbra is elérhetők legyenek a **tevékenységek minden pénzügyi időszak lezárása** lista lap, de a záró ütemezés eltávolítása a munkaterületről. Után záró ütemezés jelölése: **zárt**, nem fogunk tudni, tevékenységek hozzáadása, feladatok szerkesztése vagy feladatok eltávolítása.


