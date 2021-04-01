---
title: A beszedéskezelés kulcsfogalmai
description: A témakörök a beszedések kezelésének kulcsfogalmait határozzák meg.
author: mikefalkner
manager: AnnBe
ms.date: 11/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7d71d436f561f0c9b0d8caef00191d1eb9b56580
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257681"
---
# <a name="collections-management-key-concepts"></a>A beszedéskezelés kulcsfogalmai

[!include [banner](../includes/banner.md)]

Mielőtt elkezdené beállítani a beszedéseket vagy elkezdene dolgozni velük, ismerje meg a következő fogalmakat:

- Vevő korosítási pillanatképei egy adott időpontban tartalmazzák Korosított egyenleget.
- Beszedések vevőgyűjtő segíthet a munkáját megszervezni.
- A pénzbehajtók saját vevőgyűjtővel rendelkezhetnek.
- A listalapok megszervezik a vevők összegyűjtését, a tevékenységeket és az eseteket.
- A vevővel kapcsolatos minden összegyűjtött információ rajta van a lapon, és itt végezhet műveleteket is.
- Kamatok vagy díjak elengedése, visszaállítása vagy sztornírozása elvégezhető egy lépésben.
- A leírási tranzakciók létrehozása elvégezhető egy lépésben.
- Az Elégtelen fedezetű (NSF) fizetések feldolgozása egy lépésben elvégezhető.

Ez a témakör leírja az egyes fogalmakat.

## <a name="customer-aging-snapshots"></a>Vevő korosítási pillanatképek

A korosítási pillanatkép kiszámítja egy vevő korosított egyenlegeit egy adott időpontra. Ez az információ megjelenik a **Korosított egyenlegek** listaoldalon és a **Beszedés** lapon. Létre kell hozni egy korosítási pillanatképet mielőtt megtekinthetne információkat a beszedési lista lapokon (**Korosított egyenlegek**, **Beszedési tevékenységek** és **Beszedési esetek**).

A korosítási pillanatkép minden vevőre tartalmaz egy korosítási pillanatkép fejlécet, és az egyes korosítási időszak definícióban lévő korosítási időszaknak megfelelő adatrekordot.

A korosítási pillanatkép fejléce tartalmazza a teljes esedékes összeget, a hitelkeret, szállítólevél összegét, az értékesítési rendelés összegét, vitatott tranzakciók számát, illetve a vevőkód vitatott tranzakcióinak teljes összegét. A vevőhöz tartozó összes tranzakció szerepelni fog ezeknek az összegeknek a számításában. A teljes esedékes összeg, a hitelkeret, a bizonylat összege és az értékesítési rendelés összege megjelenik a **Beszedési** lap **Hitelinformációk** adatterületén.

A rendszer korosítási időszak definícióban lévő egyes korosítási időszakokhoz létrehoz egy korosítási pillanatképet. Minden egyes korosítási pillanatkép adat rekord tartalmazza a korosítási időszak azonosítóját és az korosítási időszakban lévő adatokhoz tartozó tranzakciók teljes összegét. A tranzakciókat egy korosítási időszakhoz rendeli hozzá a rendszer, például 30 meghaladott naphoz. A dátum a **Korosításhoz** relatív, mivel akkor határozza meg azt, amikor létrehozza a korosítási pillanatképet. Ez az információ megjelenik a **Korosított egyenlegek** listaoldalon és a **Korosítási egyenleg** adatterületen a **Beszedések** lapon.

## <a name="collections-customer-pools"></a>Beszedések vevőgyűjtők

A vevőgyűjtők olyan lekérdezések, amelyek a vevői rekordok egy csoportját határozzák meg. Ezeknek a csoportosított rekordoknak a használatával lehet megtekinteni a vevői számlákkal kapcsolatos információkat, illetve a hozzájuk tartozó gyűjtemények és korosítási folyamatok kezelését. Használhatja a vevőgyűjtőket a beszedés listaoldalakon található adatok szűréséhez. Segítségükkel továbbá szűrheti a vevői számlákat, amelyek akkor szerepelnek, ha korosítási pillanatképek kerülnek létrehozásra.

## <a name="collections-agents"></a>Kintlevőségkezelők

Alapértelmezés szerint a felhasználók láthatják az összes vevői adatot a beszedési listaoldalakon. A pénzbehajtók rekordjaival azoknak a vevőgyűjtőket határozhatja meg, amelyek elérhetők a beszedési listaoldalakon és a **Beszedések** oldalon lévő információk szűréséhez.

A beszedéskezelő a vevőkkel együttműködik annak biztosítására, hogy a kifizetések beszedésre kerüljenek a kellő időben. Olyan dolgozók, akik a **Felhasználó beállítások** oldalon lévő felhasználókhoz vannak hozzárendelve.

## <a name="collections-list-pages"></a>Beszedési listaoldalak

A következő listaoldalak megkönnyítik beszedési információk rendezését:

- **Korosítási egyenlegek** – Ennek a listaoldalnak az oszlopai a vevői egyenlegeket és a korosított összegeket mutatnak korosítási időszak szerint. A program egy korosítási pillanatképben tárolja ezt az információt. A korosítási időszakok meghatározása a korosítási időszak használt definíciója alapján történik. A korosítási időszak definíciója a vevőgyűjtőből származik, ha meg volt vevőgyűjtő adva a gyűjtő lekérdezéséhez. Ha a gyűjtő nem tartalmazza a korosítási időszak definícióját, akkor a program a korosítási időszaknak a **Kinnlevőségek paraméterei** oldalon megadott alapértelmezett definícióját használja. Ha nincs megadva alapértelmezett korosításiidőszak-definíció, akkor a **korosításiidőszak-definíciók** lapon található első korosításiidőszak-definíció kerül használatra.
- **Beszedési tevékenységek** – Az ezen e listaoldalon lévő oszlopok a beszerzési tevékenységként azonosított tevékenységeket jelenítik meg. Ezeket a tevékenységeket a **Beszedések** lap használatával hozza létre. A tevékenységek segítségével nyomon követheti a beszedésekkel kapcsolatosan elvégzett munkát.
- **Beszedési esetek** – A listaoldalon lévő oszlopok azoknak az eseteknek az információját jelenítik meg, amelyek esetkategóriája **Beszerzés** típusú eset.

### <a name="aging-snapshots"></a>Korosítási pillanatképek

A korosítási pillanatképet létre kell hozni, mielőtt megtekintheti a beszedési lista oldalakon lévő információkat. Csak olyan vevők adatai jelennek meg, akikről készült korosítási pillanatkép. A listalapon megjelenített rekordokat szűrni is lehet, a következők szerint:

- Alapértelmezés szerint a felhasználók hozzáféréssel rendelkeznek az összes korosítási pillanatképpel rendelkező vevőhöz.
- Ha léteznek vevőgyűjtők, a felhasználót pénzbehajtóként kell beállítani, hogy használhassa a gyűjtőt a beszedési listaoldalon lévő információk szűréséhez. A kiválasztott vevőgyűjtőben lévő vevők számára az információ korlátozott.
- Ha egy felhasználó pénzbehajtóként van beállítva, csak annak a pénzbehajtónak kiválasztott gyűjtők érhetők el a beszedési listaoldalakon. Ha a **Beszedéskezelő megtekintheti az összes vevőgyűjtőt** beállítás van kiválasztva a **Pénzbehajtó** oldalon a pénzbehajtó számára, minden gyűjtő elérhető számára.

## <a name="collections-page"></a>Beszedések lap

Használhatja a **Beszedések** oldalt a vevővel kapcsolatos beszedési információk, tevékenységek és esetek megtekintéséhez, kezeléséhez és műveletek végrehajtásához.

A lap felső része a kiválasztott vevő eseteit jeleníti meg, a középső szakasz a vevőhöz kapcsolódó tranzakciókat jeleníti meg, az alsó szakasz pedig a vevőhöz kapcsolódó tevékenységeket jeleníti meg. Beszedési eseteket hozhat létre egy vagy több tranzakcióhoz és a tevékenységhez tartozó kintlévőségek adatainak követésére. A felső és alsó szakaszokban található információkat az eset alapján szűrni lehet.

Az adatterületek megjelenítik a kiválasztott vevőhöz tartozó korosítási egyenlegeket és a hitelkeret információt. A program a korosítási pillanatképben tárolja ezt az információt. Igény szerint frissítheti a korosítási pillanatképet az aktuális információkkal.

A műveleti ablak gombokat tartalmaz, amelyek a kiválasztott vevőhöz, esethez, a tranzakcióhoz vagy a tevékenységhez kapcsolódó információkat jelenítik meg. Végrehajthat általános tevékenységeket, mint például a tranzakciók beszedési állapotának megváltoztatása, e-mailek küldése az integráción keresztül az e-mail szolgáltatójával, visszatérítés a vevőknek, elégtelen fedezetű kifizetések végrehajtása és behajthatatlan egyenlegek leírása.

## <a name="waiving-reinstating-or-reversing-interest-and-fees"></a>Kamat és díjak elengedése, visszaállítása vagy sztornírozása 

Elengedhet, visszaállíthat vagy sztornírozhat teljes kamatleveleket, vagy olyan díjakat és tranzakciókamatokat, amelyek egy kamatlevél részei. Ezt a **Minden vevő** listaoldalon lévő Műveleti ablaktábla **Gyűjtés** lapján teheti meg, ha rákattint a **Kamatlevél**, **Tranzakciókamat** vagy **Díjak** opcióra.

Ezek a kiigazítások csak a kamatleveleket és azokat a kamatokat és díjakat érinti, amiket azok tartalmaznak. Ha további tájékoztatást szeretne kapni arról, hogyan kell leírni a vevő által fizetendő összes költséget, tekintse meg a témakör [Leírási tranzakciók létrehozása](#creating-write-off-transactions) szakaszát.

További tudnivalókat lásd a Kamatkód létrehozása tartománnyal és a Kamatfeldolgozás pontokban.

## <a name="creating-write-off-transactions"></a>Leírási tranzakciók létrehozása

A behajthatatlan tartozásokat leírhatja a **Leírás** elem kiválasztásával a **Beszedések** lapon és beszedési listák lapokon.

Amikor leír egy vevői tranzakciót, a vevő minden tranzakciója automatikusan kiegyenlítésre lesz megjelölve. A leírt összes a megjelölt tranzakció nettó összegétől függ. A program ilyenkor létrehoz egy leírási tranzakciót egy általános naplóban, ez legfeljebb három típusú naplósort tartalmazhat:

- A naplósor első típusa tartalmazza a vevői leírási bejegyzést. Ha a megjelölt tranzakció több pénznemkód kombinációt, dimenziót és feladási profilt tartalmaz, egy külön naplóba sor jön létre minden egyes kombinációhoz.
- A naplósor második típusa tartalmazza a főkönyvi leírási bejegyzést. Ha a megjelölt tranzakció több pénznemkód kombinációt, dimenziót és feladási profilt tartalmaz, egy külön naplóba sor jön létre minden egyes kombinációhoz.
- A naplósor harmadik típusa tartalmazza az áfa főkönyvi leírási adatait. A naplósor csak akkor jön létre, ha a **Külön áfa** lehetőség van kiválasztva a **Kintlévőségek paraméterei** oldalon. Ha a megjelölt tranzakció több fizetendő áfa számla kombinációt, dimenziót és áfakódot tartalmaz, egy külön naplóba sor jön létre minden egyes kombinációhoz. A leírási tranzakció létrehozása a tranzakció pénznemében történik. További tudnivalókat lásd: Leírási napló létrehozása vevőhöz.

## <a name="process-nsf-payments"></a>Elégtelen fedezetű kifizetések feldolgozása

Feldolgozhatja az Elégtelen fedezetű kifizetéseket, ha rákattint a **Beszedések** oldalon az **Elégtelen fedezetű kifizetés** opcióra. Ha ezt a gombot választja, a kifizetés érvénytelenítve lesz. Ha alkalmazni kell elégtelen fedezet miatti díjat a vevőre, a program létrehoz egy költségtranzakciót a fizetési naplóban. A díj összege az automatikus költségek beállításaitól függ. Az elégtelen fedezetű kifizetésekre vonatkozó automatikus költségeket az a költségcsoport szabja meg, amelyik ki van választva az érintett bankszámlához a **Bankszámlák** képernyőn.

## <a name="additional-resources"></a>További erőforrások

[Vásárlói hitelkezelési pereméterek beállítása](./cm-credit-mgmt-setup.md)

[Vásárlói hitelkezelési pereméterek beállításával kapcsolatos információk](./cm-setup-information.md)

[Hitelkezelési információk hozzáadása egy ügyfélhez](./cm-add-credit-mgmt-information-customer.md)

[Vevői hitelcsoportok](./cm-customer-credit-groups.md)

[Vevői hitelkeret helyesbítései](./cm-credit-limit-adjustments.md)

[Hitelkeret felfüggesztése értékesítési rendelésekhez](./cm-sales-order-credit-holds.md)

[Vevői hitelkockázatkezelés – időszakos feladatok](./cm-periodic-tasks.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]