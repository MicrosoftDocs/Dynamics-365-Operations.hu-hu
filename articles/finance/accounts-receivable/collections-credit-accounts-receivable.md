---
title: Beszedések a Kinnlevőségek modulban
description: A kinnlevőségek kezelésével kapcsolatos adatokat egyetlen központi nézetből, a Microsoft Dynamics 365 Finance Beszedések oldalán kezelheti. A hitelezési és beszedési kezelő ezt a központi vezérlőt használja a beszedések kezelésére. A pénzbehajtó elkezdheti a beszedési folyamatot az előre meghatározott beszedési feltételek használata által létrehozott vevői listából vagy a Vevők oldalon.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustAgingSnapshot, CustBankAccounts, CustCollections, CustCollectionsActivitiesListPage, CustCollectionsAgent, CustCollectionsCaseListPage, CustCollectionsPool, CustCollectionsPoolsListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 3061
ms.assetid: fd851520-8d93-434b-845b-be127d6ac3a6
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 985d3cbba4ab662a11987152eb66941da6dbb7eb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003381"
---
# <a name="collections-in-accounts-receivable"></a>Beszedések a Kinnlevőségek modulban

[!include [banner](../includes/banner.md)]

A kinnlevőségek kezelésével kapcsolatos adatokat egyetlen központi nézetből, a Microsoft Dynamics 365 Finance Beszedések oldalán kezelheti. A hitelezési és beszedési kezelő ezt a központi vezérlőt használja a beszedések kezelésére. A pénzbehajtó elkezdheti a beszedési folyamatot az előre meghatározott beszedési feltételek használata által létrehozott vevői listából vagy a vevői listából.

Mielőtt elkezdené beállítani a beszedéseket vagy elkezdene dolgozni velük, ismerje meg a következő fogalmakat:
-   Vevő korosítási pillanatképei egy időpontban tartalmazzák Korosított egyenleget
-   Beszedések vevőgyűjtő segíthet a munkáját megszervezni
-   A pénzbehajtók saját vevőgyűjtővel rendelkezhetnek
-   A listalapok megszervezik a vevők összegyűjtését, a tevékenységeket és az eseteket
-   A vevővel kapcsolatos minden összegyűjtött információ rajta van a lapon, és itt végezhet műveleteket is
-   Kamat vagy díjak elengedése, visszaállítása vagy sztornírozása elvégezhető egy lépésben
-   Leírási tranzakciók létrehozása elvégezhető egy lépésben
-   Elégtelen fedezet (NSF) fizetések feldolgozása egy lépésben elvégezhető

A következő részek az egyes fogalmakat mutatják be.

## <a name="customer-aging-snapshots"></a>Vevő korosítási pillanatképek
A korosítási pillanatkép kiszámítja egy vevő korosított egyenlegeit egy időpontra. Ez az információ megjelenik a Korosított egyenlegek listaoldalon és a Beszedés lapon. A korosítási pillanatképet létre kell hozni, mielőtt megtekintheti a Beszedési lista oldalakon lévő információkat. 

A korosítási pillanatkép minden vevőre tartalmaz egy korosítási pillanatkép fejlécet, és az egyes korosítási időszak definícióban lévő korosítási időszaknak megfelelő adatrekordot. 

A korosítási pillanatkép fejléce tartalmazza az teljes esedékes összeget, a hitelkeret, szállítólevél összegét, az értékesítési rendelés összegét, vitatott tranzakciók számát, illetve a vevőkód vitatott tranzakcióinak teljes összegét. A vevőhöz tartozó összes tranzakció szerepelni fog ezeknek az összegeknek a számításában. A teljes esedékes összeg, a hitelkeret, a bizonylat összege és az értékesítési rendelés összege megjelenik a Beszedési lap Hitelinformációk adatterületén. 

A rendszer korosítási időszak definícióban lévő egyes korosítási időszakokhoz létrehoz egy korosítási pillanatkép adatrekordot. Minden egyes korosítási pillanatkép adat rekord tartalmazza a korosítási időszak azonosítót és az korosítási időszakban lévő adatokhoz tartozó tranzakciók teljes összegét. A tranzakciókat egy korosítási időszakhoz rendeli hozzá a rendszer, például 30 meghaladott naphoz. A dátum a Korosításhoz relatív, mivel akkor határozza meg azt, amikor létrehozza a korosítási pillanatképet. Ez az információ megjelenik a Korosított egyenlegek listaoldalon és a Korosítási egyenleg adatterületen a Beszedés lapon.

## <a name="collections-customer-pools"></a>Beszedések vevőgyűjtők
A vevőgyűjtők olyan lekérdezések, amelyek meghatározzák a beszedési vagy korosítási folyamathoz megjeleníthető és kezelhető vevőkódok egy adott rekordját. Használja a vevőgyűjtőket a Korosított egyenlegek, Beszedési tevékenységek és Beszedési esetek listaoldalon található adatok szűréséhez. Vevőgyűjtők segítségével továbbá szűrheti a vevői számlákat, amelyek akkor szerepelnek, ha korosítási pillanatképek kerülnek létrehozásra.

## <a name="collections-agents"></a>Kintlevőségkezelők
Alapértelmezés szerint a felhasználók láthatják az összes vevői adatot a beszedési listaoldalakon. Használhatja a pénzbehajtók rekordjait azoknak a vevőgyűjtőknek a meghatározásához, amelyek elérhetők a beszedési listaoldalakon és a Beszedési oldalon lévő információk szűréséhez. 

A beszedéskezelő olyan személy, aki a vevőkkel együttműködik annak biztosítására, hogy a kifizetések beszedésre kerüljenek a kellő időben. A pénzbehajtók olyan dolgozók, akik a Felhasználó beállítások oldalon lévő felhasználókhoz vannak hozzárendelve.

## <a name="collections-list-pages"></a>Beszedési listaoldalak
A következő listaoldalak megkönnyítik beszedési információk rendezését.
-   Korosítási egyenlegek – A listaoldal oszlopai a vevői egyenlegeket és a korosított összegeket mutatják korosítási időszak szerint. A program egy korosítási pillanatképben tárolja ezt az információt. A korosítási időszakok meghatározása a korosítási időszak használt definíciója alapján történik. A korosítási időszak definíciója a vevőgyűjtőből származik, ha meg volt adva a gyűjtő lekérdezéséhez. Ha a gyűjtő nem tartalmazza a korosítási időszak definícióját, akkor a program a korosítási időszaknak a Kinnlevőségek paraméterei oldalon megadott alapértelmezett definícióját használja. Ha nincs megadva alapértelmezett korosítási időszak definíció, akkor a Korosítási időszak definíciók lapon található első korosítási időszak definíció kerül használatra.
-   Beszedési tevékenységek – A listaoldalon lévő oszlopok a beszerzési tevékenységként azonosított tevékenységeket jelenítik meg. Ezeket a tevékenységeket a Beszedés lap használatával hozza létre. A tevékenységek segítségével nyomon követheti a beszedésekkel kapcsolatosan elvégzett munkát.
-   Beszedési esetek – A listaoldalon lévő oszlopok azoknak az eseteknek az információját jelenítik meg, amelyek esetkategóriája Beszerzés típusú eset.

> [!NOTE]
> A korosítási pillanatképet létre kell hozni, mielőtt megtekintheti ezeken az oldalakon lévő információkat. Csak olyan vevők adatai jelennek meg, akikről készült korosítási pillanatkép. A listalapon megjelenített rekordokat szűrni is lehet, a következőképpen:
> <li>Alapértelmezés szerint a Finance and Operations felhasználók hozzáféréssel rendelkeznek az összes korosítási pillanatképpel rendelkező vevőhöz.</li>
> <li>Ha léteznek vevőgyűjtők, a felhasználót pénzbehajtóként kell beállítani, hogy használhassa a gyűjtőt a beszedési listaoldalon lévő információk szűréséhez. A kiválasztott vevőgyűjtőben lévő vevők számára az információ korlátozott.</li>
> <li>Ha egy felhasználó pénzbehajtóként van beállítva, csak annak a pénzbehajtónak kiválasztott gyűjtők érhetők el a listaoldalon. Ha a Beszedéskezelő megtekintheti az összes vevőgyűjtőt váltás van kiválasztva a Pénzbehajtó oldalon a pénzbehajtó számára, minden gyűjtő elérhető számára.</li>


## <a name="collections-page"></a>Beszedések lap
Használja a „Beszedések” oldalt a vevővel kapcsolatos beszedési információk, tevékenységek és esetek megtekintéséhez, kezeléséhez és műveletek végrehajtásához. 

A felső panel a kiválasztott vevő eseteit jeleníti meg. A középső panel a vevő tranzakcióit jeleníti meg. Az alsó ablaktábla a vevőhöz tartozó tevékenységeket jeleníti meg. Beszedési eseteket hozhat létre egy vagy több tranzakcióhoz és a tevékenységhez tartozó kintlévőségek adatainak követésére. A felső és alsó ablaktáblán található információkat az eset alapján szűrni lehet. 

Az adatterületek megjelenítik a kiválasztott vevőhöz tartozó korosítási egyenlegeket és a hitelkeret információt. A program a korosítási pillanatképben tárolja ezt az információt. Ha szükséges, frissítheti a korosítási pillanatképet az aktuális információkkal. 

A műveleti ablak gombokat tartalmaz, amelyek a kiválasztott vevőhöz, esethez, a tranzakcióhoz vagy a tevékenységhez kapcsolódó információkat jelenítik meg. Végrehajthat általános tevékenységeket, mint például a tranzakciók beszedési állapotának megváltoztatása, e-mailek küldése az integráción keresztül az e-mail szolgáltatójával, visszatérítés a vevőknek, elégtelen fedezetű kifizetések végrehajtása és behajthatatlan egyenlegek leírása.

## <a name="waive-reinstate-or-reverse-interest-and-fees"></a>Kamat és díjak elengedése, visszaállítása vagy sztornírozása
Elengedhet, visszaállíthat vagy sztornírozhat teljes kamatleveleket, vagy olyan díjakat és tranzakciókamatokat, amelyek egy kamatlevél részei. Ezt a Minden vevő listaoldalon lévő Műveleti ablaktábla Gyűjtés lapján teheti meg, ha rákattint a Kamatlevél, Tranzakciókamat, vagy Díjak opcióra. 

Ezek a kiigazítások csak a kamatleveleket és azokat a kamatokat és díjakat érinti, amiket azok tartalmaznak. Használja a „Leírási tranzakciók létrehozása egy lépésben” szakaszban megadott lépéseket, hogy leírjon a vevőhöz tartozó minden költséget.

További tudnivalókat lásd a [Kamatkód létrehozása tartománnyal](tasks/create-interest-code-range.md) és a [Kamatfeldolgozás](tasks/process-interest.md) pontokban. 

## <a name="create-writeoff-transactions"></a>Leírási tranzakciók létrehozása
Leírhatja a behajtatlan tartozásokat, ha a Beszedések képernyőn és a Korosítási egyenlegek, Vevők és Nyitott vevői számlák listaoldalon a Leírás opcióra kattint. 

Amikor leír egy vevői tranzakciót, a vevő minden tranzakciója automatikusan kiegyenlítésre lesz megjelölve. A leírt összes a megjelölt tranzakció nettó összegétől függ. A program ilyenkor létrehoz egy leírási tranzakciót egy általános naplóban, ez legfeljebb három típusú naplósort tartalmazhat.

-   A naplósor első típusa tartalmazza a vevői leírási bejegyzést. Ha a megjelölt tranzakció több pénznemkód kombinációt, dimenziót és feladási profilt tartalmaz, egy külön naplóba sor jön létre minden egyes kombinációhoz.
-   A naplósor második típusa tartalmazza a főkönyvi leírási bejegyzést. Ha a megjelölt tranzakció több pénznemkód kombinációt, dimenziót és feladási profilt tartalmaz, egy külön naplóba sor jön létre minden egyes kombinációhoz.
-   A naplósor harmadik típusa tartalmazza az áfa főkönyvi leírási adatait. A naplósor csak akkor jön létre, ha a Külön áfa váltó van kiválasztva a Kintlévőségek paraméterei oldalon. Ha a megjelölt tranzakció több fizetendő áfa számla kombinációt, dimenziót és áfakódot tartalmaz, egy külön naplóba sor jön létre minden egyes kombinációhoz.

A leírási tranzakció létrehozása a tranzakció pénznemében történik.

További tudnivalókat lásd: [Leírási napló létrehozása vevőhöz](tasks/create-write-off-journal-customer.md).

<a name="process-not-sufficient-funds-nsf-payments"></a>Elégtelen fedezetű (NSF) fizetések feldolgozása 
--------------------------------------------

Feldolgozhatja az Elégtelen fedezetű kifizetéseket, ha rákattint a Beszedések oldalon az Elégtelen fedezetű kifizetés opcióra. Ha erre a gombra kattint, a kifizetés érvénytelenítve lesz. Ha alkalmazni kell elégtelen fedezet miatti díjat a vevőre, a program létrehoz egy költségtranzakciót a fizetési naplóban. A díj összege az automatikus költségek beállításaitól függ. Az elégtelen fedezetű kifizetésekre vonatkozó automatikus költségeket az a költségcsoport szabja meg, amelyik ki van választva az érintett bankszámlához a Bankszámlák képernyőn.





