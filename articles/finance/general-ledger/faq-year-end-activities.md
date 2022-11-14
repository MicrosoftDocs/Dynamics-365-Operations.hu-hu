---
title: Év végi tevékenységek – GYIK
description: Ebben a cikkben láthatja az év lezárásakor felmerülő kérdéseket, valamint azokat a válaszokat, az év végi zárással kapcsolatos tevékenységek terén nyújtanak segítséget.
author: moaamer
ms.date: 11/08/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2a75d1e3e68837a437b2369ba369b0063e015b12
ms.sourcegitcommit: 78cbb125f20a33df38bda0546203b8f837cbcd93
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/09/2022
ms.locfileid: "9751957"
---
# <a name="year-end-activities-faq"></a>Év végi tevékenységek – GYIK 

[!include [banner](../includes/banner.md)]

Ebben a cikkben láthatja az év lezárásakor felmerülő kérdéseket, valamint azokat a válaszokat, az év végi zárással kapcsolatos tevékenységek terén nyújtanak segítséget. Ez a cikk elsősorban a főkönyvhöz és a kötelezettségekhez kapcsolódó, év végi zárással kapcsolatos tevékenységekkel foglalkozik.

## <a name="general-ledger-year-end-enhancements"></a>Főkönyv év végi fejlesztései 
A 10.0.20-as verzió egy év végi zárási funkciót is bevezetett, amely a 10.0.25-ös verziótól kezdődően már alapértelmezett módon aktiválva lesz. Ha szervezete a 10.0.25-ösnél korábbi verziót használ, javasoljuk, hogy az év végi zárási folyamat megkezdése előtt aktiválja ezt a funkciót. Ahhoz, hogy használhassa a funkciót, először aktiválnia kell a rendszerében. A rendszergazdák a Funkciókezelés munkaterület segítségével ellenőrizhetik a funkció állapotát, és szükség esetén bekapcsolhatják. A funkció a következő módon jelenik meg:

 - Modul: Főkönyv
 - Funkció neve: Főkönyv év végi fejlesztései

Az év végi zárási sablonok beállításai egy új beállítási lapon, az **Év végi zárási sablonok beállítása** oldalon érhetők el. Az év végi zárás meglévő lapja a Főkönyvi devizaátértékeléshez hasonló módon fog változni, ahol egy lista tartalmazza az év végi zárás futtatásának vagy sztornírozásának összes időpontját. A főkönyvelő az év végi zárást az új oldalról kezdeményezheti. 

Az év végi zárás sztornírozásához válassza ki a megfelelő jogi személy legutóbbi pénzügyi évét, majd nyomja meg az **Év végi zárás sztornírozása** gombot. A sztornírozás törli az előző év végi zárásra vonatkozó könyvelési tételeket, és nem futtatja automatikusan újra az év végi zárást. 

Az év végi zárás újrafuttatásához indítsa újra a pénzügyi évre és a jogi személyre vonatkozó folyamatot. A folyamat továbbra is a Főkönyv paraméterbeállításával határozza meg, hogy az év végi zárás újrafuttatása csak az új vagy módosított tranzakciókat veszi-e figyelembe, vagy teljesen sztornírozza a korábbi lezárásokat, és az összes tranzakcióra vonatkozóan újrafuttatja a folyamatot.  

## <a name="general-ledger-how-do-i-know-that-were-running-year-end-close-and-not-undoing-year-end-close"></a>Főkönyv: Hogyan tudok megbizonyosodni arról, hogy elvégezzük, és nem visszavonjuk az év végi zárást?
Több szervezetet is láttunk már, amely az év végi zárás lefuttatása helyett véletlenül visszavonta a zárást. Ha az év végi zárás művelete rendkívül gyorsan lefut, vagy az év végi zárás nem hoz létre nyitó egyenlegeket, ellenőrizze az **Előző zárás visszavonása** beállítást az **Év végi zárás** menüben (**Főkönyv > Időszak lezárása > Év végi zárás > Pénzügyi zárás futtatása**). 

[![Az év végi zárás futtatása és az év végi zárás visszavonása.](./media/faq-2020-yr-end-01.png)](./media/faq-2020-yr-end-01.png)

Ha az **Előző zárás visszavonása** beállításnál az **Igen** érték szerepel, a rendszer vissza fogja vonni az előző év végi zárást. A visszavonás futtatásakor a program a záró és nyitó egyenlegekhez kapcsolódó összes bejegyzést törli, mintha az év végi zárást még nem futtatták volna le. A program a bizonylatokat is törli. A program nem indítja el automatikusan újra az év végi zárást. A folyamatot Önnek kell újraindítania. Ügyeljen rá, hogy az **Előző zárás visszavonása** lehetőségnél a **Nem** érték legyen beállítva. 

> [!NOTE]
> A lezárás alatt álló évnél opcionálisan létrejön a záró egyenleg bejegyzése. Ez csak akkor történik meg, ha a **Záró tranzakciók létrehozása átvezetés közben** főkönyvi paraméter az **Igen** értékre van állítva. A nyitó egyenleg bejegyzését a program mindig létrehozza, mert ez a következő év nyitó egyenlege.  
 
## <a name="general-ledger-what-is-the-difference-between-undo-and-delete-gl-parameter-for-year-end-close"></a>Főkönyv: Az év végi zárást tekintve mi a különbség a Visszavonás és a Törlés főkönyvi paraméterek között?
Talán nem minden felhasználó számára egyértelmű, hogy mi a különbség az **Előző zárás visszavonása** paraméter (amely az **Év végi zárás** párbeszédpanelen található) és az **Évzáró tranzakciók törlése átvezetés közben** főkönyvi paraméter között (**Főkönyv > Időszak zárása > Év végi zárás > Pénzügyi zárás futtatása**).  

[![A Visszavonás és a Törlés főkönyvi paraméterek közötti különbség az év végi zárásnál.](./media/faq-2020-yr-end-02.png)](./media/faq-2020-yr-end-02.png)

Ha az év végi zárási folyamat futtatása közben szeretné törölni az összes záró és nyitó egyenleggel kapcsolatos bejegyzést, a párbeszédpanel legördülő menüjéből válassza az **Előző zárás visszavonása** lehetőséget. Így olyan lesz, mintha az év végi zárást még nem futtatták volna le. A program a bizonylatokat is törli. A program nem indítja el automatikusan újra az év végi zárást. Az év végi zárás futtatásához a felhasználók ismét el kell indítania a folyamatot. Ebben az esetben módosítsa az **Előző zárás visszavonása** beállítást a **Nem** értékre (**Főkönyv > Főkönyv beállítása > Főkönyvi paraméterek**). 

[![Főkönyvi paraméterek beállítása.](./media/faq-2020-yr-end-03.png)](./media/faq-2020-yr-end-03.png)

A főkönyv **Évzáró tranzakciók törlése átvezetés közben** paramétere csak az év végi zárás futtatása során használatos (amikor az **Előző zárás visszavonása** lehetőség a **Nem** értékre van állítva), tehát a zárás visszavonásakor nem. Ha a paraméter az **Igen** értékre van állítva, a rendszer törli a záró egyenleghez és a nyitó egyenleghez kapcsolódó bejegyzéseket, és újra lefuttatja az év végi zárást. Ezt a folyamatot akkor használják, ha a szervezet egyetlen, a záró és a nyitó egyenleg bejegyzéseihez kapcsolódó könyvelési bejegyzésben szeretné feladni az összes tranzakciót, ideértve az előző év zárása óta végzett korrekciókat. 

Ha a paraméter beállítása **Nem**, a záró és a nyitó egyenleghez kapcsolódó összes bejegyzés megmarad. A program nem törli őket. Ehelyett létrejön egy új bejegyzés a nyitó és a záró egyenleghez, amely csak a változásokat, azaz az adott pénzügyi év előző év végi zárása óta feladott új tranzakciókat tartalmazza.  

> [!NOTE]
> A záró egyenleghez kapcsolódó bejegyzést a rendszer a zárás alatt álló évben hozza létre. Ez csak akkor történik meg, ha a főkönyv **Záró tranzakciók létrehozása átvezetés közben** paramétere az **Igen** értékre van állítva. A nyitó egyenleg bejegyzését a program mindig létrehozza, mert ez a következő év nyitó egyenlege. 

## <a name="general-ledger-what-can-be-changed-to-enhance-performance-of-year-end-processing"></a>Főkönyv: Milyen módosításokkal lehet javítani az év végi zárás feldolgozásának teljesítményét? 
Számos módosítás segíthet az év végi zárás teljesítményének javításában. Javasoljuk, hogy értékelje ki az itt ajánlott módosításokat, és fontolja meg, hogy megfelelőek-e az Ön szervezete számára.  

### <a name="dimension-sets"></a>Dimenziókészletek
Az év végi zárás futtatásakor a rendszernek minden dimenziókészlet egyenlegét újra kell építenie, ami közvetlenül befolyásolja a teljesítményt. Egyes szervezetek felesleges, a korábbiakban valaha használt vagy a jövőben használni tervezett dimenziókészleteket hoznak létre.  A program ezeket a szükségtelen dimenziókészleteket is újraépíti az év végi zárás során, ami meghosszabbítja a folyamatot. Alaposan értékelje ki a dimenziókészleteket, és törölje a szükségtelen elemeket.

A szükségtelen dimenziókészletek a **BudgetDimensionFocusInitializeBalance** kötegelt feladatot is befolyásolják (**Főkönyv > Számlatükör > Dimenziók > Pénzügyi dimenziókészletek**).

[![Pénzügyi dimenziókészletek.](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Év végi zárásra vonatkozó sablon konfigurálása
Az év végi zárásra vonatkozó sablon segítségével a szervezetek kiválaszthatják a pénzügyidimenzió-szintet, amelyet az eredményegyenlegek mérleg szerinti egyenlegbe való átviteléhez szeretnének használni. A beállítások segítségével a szervezetek kezelhetik a részletes pénzügyi dimenziókat (**Az összes lezárása**), amikor az egyenlegeket átviszik a mérleg szerinti eredménybe, vagy ha úgy döntenek, hogy az összegeket egyetlen dimenzióértékben szeretnék összegezni (**Egyetlen lezárása**). Ezt minden pénzügyi dimenziónál meg lehet határozni. A beállításokkal kapcsolatos további információkért lásd az [Év végi zárás](year-end-close.md) című cikket.

A teljesítmény javítása érdekében javasoljuk, hogy értékelje ki a szervezet igényeit, és ha lehetséges, zárjon le a lehető legtöbb dimenziót az **Egyetlen lezárása** év végi lehetőséggel. Ha egyetlen dimenzióértékre (amely üres érték is lehet) végez lezárást, a rendszer kevésbé részletes számításokat végez az eredmény-zárószámla bejegyzéseire vonatkozó egyenleg meghatározásakor.

## <a name="degenerate-dimensions"></a>Ténybe ágyazott dimenziók

A ténybe ágyazott dimenzió csupán kevés vagy semmilyen lehetőséget nem nyújt arra, hogy önmagában, illetve további dimenziókkal együtt újból felhasználhassák. Kétféle típusú ténybe ágyazott dimenziót különböztethetünk meg. Az első típus egy olyan dimenzió, amely egyénileg ténybe ágyazott. Ez a dimenziótípus rendszerint csak egyetlen tranzakcióban vagy csupán kevés tranzakciókészletben jelenik meg. A második típus egy vagy több olyan dimenzióval együtt válik ténybe ágyazottá, amelyek a lehetséges generálható permutációk alapján megegyező potenciállal rendelkeznek. A ténybe ágyazott dimenziók jelentős mértékben befolyásolhatják az év végi zárási folyamat teljesítményét. A teljesítménnyel kapcsolatos problémák csökkentése érdekében az év végi zárási beállításban határozza meg az összes ténybe ágyazott dimenziót **Egyetlen lezárása** dimenzióként az előző szakaszban ismertetett eljárás segítségével.

## <a name="general-ledger-what-does-the-period-close-year-end-close-do"></a>Főkönyv: Mi történik az Időszak lezárása – Év végi zárás lehetőség használatakor?
 
[![Időszak lezárása, év végi zárás.](./media/faq-2020-yr-end-05.png)](./media/faq-2020-yr-end-05.png)

### <a name="performance-improvements-for-rebuilding-financial-dimension-sets"></a>Teljesítményjavítások a pénzügyi dimenziókészletek újraépítéséhez
A 10.0.16-os verzióban bevezetett új funkció javítja az év végi zárási és konszolidálási folyamatok teljesítményét. A funkció neve: Teljesítménnyel kapcsolatos fejlesztések a pénzügyi dimenziókészletek újraépítéséhez. Ez a funkció módosítja a dimenziókészletek újraépítésének módját, amelyeket így csak egy adott időkeretben lehet újraépíteni. A korábbi verziókban a program az összes dátumhoz újraépítette a dimenziókészleteket. Ha például a 2020-as évet zárja, a rendszer csak a 2020-as pénzügyi évhez tartozó tranzakciók egyenlegeit építi újra. Ha például a 2020. november 1. és 2020. november 30. közötti dátumtartományban futtat konszolidációt, a rendszer csak az erre a dátumtartományra vonatkozó egyenlegeket építi újra.

Ahhoz, hogy használhassa a funkciót, először aktiválnia kell a rendszerében. A rendszergazdák a Funkciókezelés munkaterület segítségével ellenőrizhetik a funkció állapotát, és szükség esetén bekapcsolhatják. A funkció a következő módon jelenik meg:
 
- Modul: Főkönyv
- Funkció neve: Teljesítménnyel kapcsolatos fejlesztések a pénzügyi dimenziókészletek újraépítéséhez

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2021"></a>Kötelezettségek: Milyen módosításokat vezettek be 2021-ben az 1099-es év végi jelentés támogatásához?

2021-ben a DIV-, NEC-, és MISC-űrlapok kisebb változáson estek át, és néhány további mezővel egészültek ki.

#### <a name="div-new-box2e-2f"></a>DIV: új mezők – 2e, 2f
 
- 2e mező. Megmutatja az 1a mezőben lévő összeg azon részét, amely a FIRPTA-törvény 897-es szakaszának értelmében az egyesült államokbeli ingatlanérdekeltség (USRPI) átruházásából származó tulajdonnak minősül.  
- 2f mező. Megmutatja az 2a mezőben lévő összeg azon részét, amely a FIRPTA-törvény 897-es szakaszának értelmében az egyesült államokbeli ingatlanérdekeltség (USRPI) átruházásából származó tulajdonnak minősül. Ne feledje, hogy a 2e. és a 2f. mezők csak azon külföldi személyekre és entitásokra vonatkoznak, amelyek bevétele megőrzi karakterét a közvetlen vagy közvetett külföldi tulajdonosokon vagy kedvezményezetteken keresztül történő továbbítás vagy a közöttük történő szétosztás során. Általában az Egyesült Államokon belüli kereskedelemhez vagy üzleti tevékenységhez kapcsolódóként kezelik. Tekintse meg az adóbevallásra vonatkozó utasításokat. 
 
#### <a name="nec-new-box-2"></a>NEC: új mező – 2 
 
Ha a 2. mező be van pipálva, azokat az 5000 dollár összeget elérő vagy meghaladó fogyasztói termékeket kell jelentenie, amelyeket továbbértékesítés, vétel/eladás, betéti jutalék vagy egyéb alapján adtak el Önnek. Rendszerint az ezen termékek értékesítéséből származó bevételeket a C ütemtervben kell jelenteni (1040-es űrlap). 
 
Mindeközben módosult a NEC-űrlap mérete. A nyomtatás során három űrlap szerepel oldalanként. 
 
#### <a name="misc-new-box-11"></a>MISC: új mező – 11 
 
A 11-es mező megmutatja azt az összeget, amelyet a továbbértékesítéshez vásárolt halmennyiségnek a halfogással kereskedő vagy ezzel kapcsolatos üzleti tevékenységet végző személytől történő beszerzésére költött. Az említett jövedelem bevallásához tekintse meg az adóbevallásra vonatkozó utasításokat. 
 
#### <a name="electronic-filing"></a>Elektronikus benyújtás 
Az elektronikus benyújtásról szóló további információkért forduljon a következőhöz: [Tájékoztatás az elektronikus benyújtás követelményeivel kapcsolatban](https://www.irs.gov/pub/irs-pdf/p1220.pdf).

Formátumspecifikációk és rekordelrendezések frissítése a 2021-es e-jelentéshez 
- 2. szakasz. Kibocsátó: „A” rekord. 
- Összegkódok – a mezők pozíciója 28–45-re, hosszuk 18-ra nőtt. 
 
#### <a name="sec-2-issuer-a-record-for-reporting-payments-on-form-1099-div"></a>2. szakasz, kibocsátó: „A” rekord, a 1099-DIV űrlapon történő, kifizetésekre vonatkozó jelentéskészítéshez: 
- Összegtípus – Hozzáadva a 897-es szakasz: Törzsrészvények osztaléka és a H összegkód. 
- Összegtípus – Hozzáadva a 897-es szakasz: Tőkenyereség és a J összegkód. 
 
#### <a name="sec-3-payee-b-record"></a>3. szakasz. Kedvezményezett: „B” rekord 
- Általános információs rekordok – a harmadik felsorolásban a kifizetett összeghez tartozó mezők száma 16-ról 18-ra bővült. 
- Mezőcím kifizetés H – Frissítettük a 247–258-as mezők pozícióját, a mező címét, hosszúságát és a mező általános leírását. 
- Mezőcím kifizetés J – Frissítettük a 259–270-as mezők pozícióját, a mező címét, hosszúságát és a mező általános leírását. 
- Az üres mezőt a 271–286-os mezőkhöz frissítettük. 
- A külföldi ország jelét a 287-es mezőhöz frissítettük. 
- Az első kedvezményezett nevéhez tartozó mezőt a 288–327 mezőkhöz frissítettük. 
- A második kedvezményezett nevéhez tartozó mezőt a 328–367 mezőkhöz frissítettük. 
- Rekordelrendezés-pozíciók, 1099-MISC űrlap – Töröltük az 548-as mezőt és a FATCA Bejelentési kötelezettség jelzője (Filing Requirement Indicator) mezőcímet. 
- Rekordelrendezés-pozíciók, NEC 1099-es űrlap – Az 545–546-os mezők helyére üres mezőket illesztettünk, az 547-es mezőhöz frissítettük a Közvetlen értékesítések mutatóját, hosszúságát, leírását és a megjegyzéseket, az 548–722-es mezőket pedig üres mezőkre módosítottuk. 
 
#### <a name="sec-4-end-of-issuer-c-record"></a>4. szakasz. A kibocsátó „C” rekordjának vége 
- Mezőcím kifizetés H – Frissítettük a 304–321-as mezők pozícióját, a mező címét, hosszúságát és a mező általános leírását. 
- Mezőcím kifizetés J – Frissítettük a 322–339-as mezők pozícióját, a mező címét, hosszúságát és a mező általános leírását. 
- Mezőcím 340–499 – A hosszúságot 160-ra frissítettük. 
 
#### <a name="sec-5-state-totals-k-record"></a>5. szakasz. Állami végösszegek: „K” rekord 
- Mezőcím kifizetés H – Frissítettük a 304–321-as mezők pozícióját, a mező címét, hosszúságát és a mező általános leírását. 
- Mezőcím kifizetés J – Frissítettük a 322–339-as mezők pozícióját, a mező címét, hosszúságát és a mező általános leírását. 
- Mezőcím 340–499 – A hosszúságot 160-ra frissítettük.  

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Kötelezettségek: 1099 – Hogyan módosítom az 1099-es űrlap mezőértékeit, valamint az olyan szállítók értékeit, amely az év során nem követte az 1099-es adatokat?
Az „1099 frissítése” funkció (**Kötelezettségek > Szállítók > Minden szállító > Szállító kiválasztása > Szállító fül a menüszalagon > 1099 frissítése**) segítségével áttekintheti a korábban kifizetett számlatranzakciókat, hogy megfelelően újból hozzárendelhesse az 1099-es adatokat az **Adó – 1099** fülön megadott beállítások alapján (lásd a **Szállító** oldalon).

## <a name="can-i-run-the-update-1099-for-all-my-vendors-at-once"></a>Futtathatom az „1099 frissítése” funkciót az összes szállítónál egyszerre?
Nem. A „1099 frissítése” rutint egyszerre csak egy szállítón lehet lefuttatni. Ha szervezeténél szükség lenne erre a lehetőségre, szavazzon [A szállítók 1099-es adatainak kötegfolyamata](https://experience.dynamics.com/ideas/idea/?ideaid=5493d608-350e-eb11-b5d9-0003ff68ded8) nevű ötletre.

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-versus-update-all-in-the-update-1099-utility"></a>Kötelezettségek: 1099 – A meglévő 1099-es összegek újraszámítása és az Összes frissítése lehetőség összehasonlítása az 1099 frissítése segédprogramban
**A meglévő 1099-es összegek újraszámítása** jelölőnégyzet a teljes kifizetett értékre állítja vissza az 1099-es összeget, amennyiben az **Összes frissítése** jelölőnégyzettel együtt használják. 

[![1099-es adótranzakciók: a frissítési rutin futtatása előtt.](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

**A meglévő 1099-es összegek újraszámítása** jelölőnégyzet csak akkor használható, ha a számlán részleges 1099-es értékek szerepelnek, vagy ha az 1099-es adóűrlapon módosították. Ha például a számla értéke 1000,00 $, de a felhasználó manuálisan megadja az űrlapon az 500,00 $ értéket az 1099-es funkciónál.

[![1099-es adótranzakciók: Az Összes frissítése és A meglévő 1099-es összegek újraszámítása lehetőségek megjelölése.](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

Ha ezt kifizetik, az 500,00 $ lesz a kifizetett 1099-es összeg. Ha lefuttatja az újraszámítási rutint, a rendszer 1000,00 $-re módosítja az 1099-es összeget, amely a teljes kifizetett összeg.

[![1099-es adótranzakciók: Az 1099-es rutin futtatása után.](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Kötelezettségek: 1099 – Az 1099-es tranzakciók manuális létrehozása
Előfordulhat, hogy egy szervezetnek manuálisan kell létrehoznia azokat az 1099-es tranzakciókat, amelyek nincsenek számlához társítva. Manuálisan is hozzáadhat 1099-es tranzakciókat, amelyhez a **Kötelezettségek > Időszakos feladatok > Adó - 1099 > Szállítói kiegyenlítések az 1099-es jelentéshez** menüpontot használhatja. Válassza a **Manuális 1099-es tranzakciók** gombot. 

A manuálisan létrehozott 1099-es tranzakciók nem frissülnek az **Összes frissítése** folyamattal, sem **A meglévő 1099-es összegek újraszámítása** folyamattal az **1099-es frissítés** segédprogramban.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Kötelezettségek: 1099 – Támogatja a Dynamics 365 Finance az 1096-os űrlapot? 

A Dynamics 365 Finance nem nyomtatja ki az 1096-os éves összesítés és az egyesült államokbeli információküldés átvitele űrlapot.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Kötelezettségek: 1099 – Vannak olyan új funkciók, amelyek támogatják az állami szektor számára az 1099-es jelentéseket? 
A program az állami szektor számára készült új funkcióval, az **1099-es adatok frissítése fő számla szerint** funkcióval bővült, amelyet a **Funkciókezelés** munkaterületen lehet engedélyezni. Ezzel a funkcióval a fő számla alapján lehet társítani a szállító 1099-es értékeit a könyvelési felosztásban, nem pedig a szállítói rekordon található alapértelmezett számla alapján.

További információkért lásd: [Szállítók beállítása az 1099-es kimutatáshoz](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
