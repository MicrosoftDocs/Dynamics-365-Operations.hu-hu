---
title: Év végi tevékenységek – GYIK
description: Ebben a cikkben láthatja az év lezárásakor felmerülő kérdéseket, valamint azokat a válaszokat, az év végi zárással kapcsolatos tevékenységek terén nyújtanak segítséget.
author: moaamer
ms.date: 12/01/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2e33c1dcbfa4da74f2e8acc6e29f04fda3abd185
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853040"
---
# <a name="year-end-activities-faq"></a>Év végi tevékenységek – GYIK 

[!include [banner](../includes/banner.md)]

Ebben a cikkben láthatja az év lezárásakor felmerülő kérdéseket, valamint azokat a válaszokat, az év végi zárással kapcsolatos tevékenységek terén nyújtanak segítséget. Ez a cikk elsősorban a főkönyvhöz és a kötelezettségekhez kapcsolódó, év végi zárással kapcsolatos tevékenységekkel foglalkozik.

## <a name="general-ledger-year-end-enhancements"></a>Főkönyv év végi fejlesztései

A Microsoft Dynamics 365 Finance 10.0.20-as verziója év végi zárási funkció javítását vezetett be. Ez a javítás alapértelmezés szerint engedélyezve van a 10.0.25-ös verzióban, és a 10.0.29-es verziótól kötelező. Ha szervezete a 10.0.25-ösnél korábbi verziót használ, javasoljuk, hogy az év végi zárási folyamat megkezdése előtt engedélyezze ezt a funkciót. Ahhoz, hogy használhassa a funkciót, először aktiválnia kell a rendszerében. A rendszergazdák a **Funkciókezelés** munkaterület segítségével ellenőrizhetik a funkció állapotát, és szükség esetén bekapcsolhatják. A funkció a következő módon jelenik meg:

- **Modul:** Főkönyv
- **Funkció neve:** Főkönyv év végi fejlesztései

Az év végi zárási sablonok beállításai egy új beállítási lapon, az **Év végi zárási sablonok beállítása** oldalon érhetők el. Az év végi zárás meglévő lapja a **Főkönyvi devizaátértékelés** oldalhoz hasonló lesz, ahol egy lista megmutatja az év végi zárás futtatásának vagy sztornírozásának összes időpontját. A lap nem mutatja a funkció engedélyezése előtt végzett év végi zárásokkal kapcsolatos korábbi adatokat. A főkönyvelő az év végi zárást az új oldalról kezdeményezheti.

Az év végi zárás sztornírozásához válassza ki a megfelelő jogi személy legutóbbi pénzügyi évét, majd válassza az **Év végi zárás sztornírozása** lehetőséget. A sztornírozás törli az előző év végi zárásra vonatkozó könyvelési tételeket, és nem futtatja újra automatikusan az év végi zárást. Ha az év végi zárás befejezése után engedélyezi a **Főkönyv év végi fejlesztések** funkciót, és szeretné sztornírozni az előző év végi eredményeket, akkor futtassa újra a korábbi év végi zárást, miután engedélyezi a **Meglévő év végi zárási bejegyzések törlése az év újbóli lezárása** Főkönyvi paramétert.

Az év végi zárás újrafuttatásához indítsa újra a pénzügyi évre és a jogi személyre vonatkozó folyamatot. A folyamat továbbra is a Főkönyv paraméterbeállításával határozza meg, hogy az év végi zárás újrafuttatása csak az új vagy módosított tranzakciókat veszi-e figyelembe, vagy a folyamat újból le lesz futtatva az összes tranzakcióhoz, és teljesen sztornírozza a korábbi lezárásokat.

## <a name="general-ledger-the-general-ledger-year-end-enhancements-feature-is-enabled-why-cant-i-view-my-previous-year-closings-in-the-history-section-of-the-year-end-close-page"></a>Főkönyv: A Főkönyv év végi fejlesztései funkció engedélyezve van. Miért nem tudom megtekinteni az előző évi zárásokat az Év végi zárás lap Előzmények szakaszában?

A **Főkönyv év végi fejlesztések** funkció engedélyezése előtt nyomon követte a rendszer a legutóbbi év végi zárási folyamat futtatásának időpontját. Nem követte nyomon az előzményeket minden év végi zárás elvégzésekor. Így nem érhetők el az összes év végi zárás futtatási részletei. A funkció engedélyezése után a következő év végi zárási folyamatadatait megőrzik. Az év végi zárási folyamatokból származó bizonylatok, még azok is, amelyek a funkció engedélyezése előtt lettek futtatva, megtekinthetők a **Bizonylattranzakciók** lapon. 

## <a name="general-ledger-the-year-end-close-process-is-failing-because-of-the-following-error-the-year-end-close-cant-be-run-because-one-or-more-ledger-transactions-posted-into-the-fiscal-year-that-you-are-closing-were-settled-to-a-ledger-transaction-in-a-different-fiscal-year-what-does-this-error-mean"></a>Főkönyv: Az év végi zárási folyamat sikertelen a következő hiba miatt: „Az év végi zárás nem futtatható, mert a jelenleg lezárandó pénzügyi évre feladott egy vagy több főkönyvi tranzakció egy másik pénzügyi év főkönyvi tranzakciójával lett kiegyenlítve”. Mit jelent ez a hiba?

Mivel engedélyezve van a **Figyelem a főkönyvi kiegyenlítés és az év végi zárás között** funkció, csak a pénzügyi év lezárt, kiegyenlített főkönyvi tranzakciói lesznek kizárva a nyitó egyenlegből. Ezen viselkedés miatt a követelések és a jóváírás nincsenek egyensúlyban. További információért lásd a [Figyelem a főkönyvi kiegyenlítés és az év végi zárás között](awareness-between-ledger-settlement-year-end-close.md) lehetőséget.

## <a name="general-ledger-reversal-of-the-year-end-close-process-is-failing-because-of-the-following-error-the-year-end-close-for-112022-cant-be-reversed-because-beginning-balance-transaction-have-been-ledger-settled-in-fiscal-year-112023-what-does-this-error-mean"></a>Főkönyv: Az év végi zárási folyamat sztornírozása sikertelen a következő hiba miatt: „A 2022.01.01. év végi zárás nem sztornírozható, mert a kezdő egyenlegtranzakciók főkönyvi kiegyenlítései a 2023.01.01. pénzügyi évben mentek végbe.” Mit jelent ez a hiba?

Mivel engedélyezve van a **Figyelem a főkönyvi kiegyenlítés és az év végi zárás között** funkció, nem engedélyezett az év végi feldolgozás sztornírozása, ha a nyitó tranzakciók ki lettek egyenlítve az új pénzügyi évben. Sztornírozza az új 2023-as pénzügyi évben a főkönyvi kiegyenlítést, mielőtt a 2022. január 1. év végi zárást sztornírozza. Akár újból bezárhatja az 2022. január 1-i évet, de csak az új helyesbítő bejegyzésekhez. Ha az évet csak a kiigazításokhoz szeretné lezárni, akkor tiltsa le a **Meglévő év végi zárási bejegyzések törlése az év újbóli zárásakor** Főkönyv paramétert.

## <a name="general-ledger-why-isnt-the-ledger-settlement-automation-processing-decembers-ledger-settlement-transactions"></a>Főkönyv: A főkönyvi kiegyenlítés automatizálása miért nem végzi el a decemberi főkönyvi kiegyenlítési tranzakciókat?

A **Főkönyvi kiegyenlítések automatizálása** funkció futtatja az automatizálást azokhoz a tranzakciókhoz, amelyek a pénzügyi év első napjától az előfordulás futtatásának aktuális időpontjáig vannak datálva. A december 31-én végződő pénzügyi éveknél lehet, hogy módosítania kell az előfordulás végrehajtási dátumát, hogy biztosan decemberben legyen lefuttatva. Az automatizálás például úgy van beállítva, hogy minden hónap első napján fusson. Ez az automatizálás 2022. december 1-én lesz futtatva, és ütemezés szerint 2023. január 1-jén fog futni. Javasoljuk, hogy módosítsa az előfordulást 2023. január 1-jére, hogy ne 2022. december 31-jén fusson. Ezzel a módosítással gondoskodhat arról, hogy a december 2. és 31. közötti tranzakciókat figyelembe vegyék az automatikus kiegyenlítésben.

## <a name="general-ledger-whats-the-difference-between-the-reverse-year-end-close-action-and-the-delete-existing-year-end-entries-when-reclosing-parameter-for-year-end-close"></a>Főkönyv: Mi a különbség az Év végi zárás sztornírozása művelet és a Meglévő év végi bejegyzések törlése között, amikor az év végi zárási paramétert újból lezárja?

Félreértések fordulhatnak elő az **Év végi zárás sztornírozása** művelet és a Főkönyvben lévő (**Főkönyv \> Főkönyv beállítása \> Főkönyv paraméterei**) **Meglévő év végi bejegyzések törlése az újbóli lezáráskor** paraméter közötti különbségek miatt.

Ha az év végi zárási folyamat futtatása közben szeretné törölni az összes záró és nyitó egyenleggel kapcsolatos bejegyzést, válassza az **Év végi zárás sztornírozása** műveletet. Így olyan lesz, mintha az év végi zárást még nem futtatták volna le. Ebben az esetben a program a bizonylatokat is törli. A program nem indítja el automatikusan újra az év végi zárást. Az év végi zárás futtatásához válassza az **Év végi zárás futtatása** műveletet.

A Főkönyvben lévő **Meglévő év végi bejegyzések törlése az év újbóli lezárásakor** paraméter csak akkor használatos, ha futtatja (nem sztornírozza) az év végi zárást. Ha a paraméter az **Igen** értékre van állítva, a rendszer törli a záró egyenleghez és a nyitó egyenleghez kapcsolódó bejegyzéseket, és újra lefuttatja az év végi zárást. Ezt a lehetőséget akkor használják, ha egy szervezet egyetlen, a záró és a nyitó egyenleg bejegyzéseihez kapcsolódó könyvelési bejegyzésben szeretné feladni az összes tranzakciót, ideértve az előző év zárása óta végzett kiigazításokat. Ha a paraméter **Nem** értékre van állítva, a záró és a nyitó egyenleghez kapcsolódó összes bejegyzés megmarad. A program nem törli őket. Ehelyett létrejön egy új bejegyzés a nyitó és a záró egyenleghez, amely csak a változásokat, tehát az adott pénzügyi év előző év végi zárása óta feladott új tranzakciókat tartalmazza.

> [!NOTE]
> A záró egyenleghez kapcsolódó bejegyzést a rendszer a zárás alatt álló évben hozza létre. Ez csak akkor történik meg, ha a főkönyv **Záró tranzakciók létrehozása átvezetés közben** paramétere az **Igen** értékre van állítva. A nyitó egyenleg bejegyzését a program mindig létrehozza, mert ez a következő év nyitó egyenlege.

## <a name="general-ledger-what-is-the-difference-between-close-all-and-close-single-options-on-the-transfer-profit-and-loss-dimension-section-of-the-year-end-close-process"></a>Főkönyv: Mi a különbség az „Összes lezárása” és az „Egyetlen lezárása” beállítás között az Év végi zárás folyamat Eredménydimenziók átvitele szakaszban?

Az **Összes lezárása** megtartja az eredeti pénzügyi dimenzióértékeket a feladott tranzakcióknál, és segítségükkel hozza létre a nyitó egyenlegeket a visszatartott bevételek számláinál. A fenntartott bevételek különálló nyitó egyenlegei létrejönnek a pénzügyi dimenzióértékek minden egyedi kombinációjához. Az **Egyetlen lezárása** kiválasztása esetén minden, az adott pénzügyi dimenzióval feladott tranzakció összesítve lesz a fenntartott bevételek nyitó egyenlegében az **Egyetlen lezárása** után megjelenő mezőben. 

Tegyük fel például, hogy a pénzügyi év összes tranzakcióját a Fő számla – Részleg számlastruktúrával küldték be. A sablon Részleg pénzügyi dimenziója részénél az **Egyetlen lezárása** beállítás van kiválasztva, és a 100 érték van megadva dimenzióértéknek. Ha a 200, 300 és 400 részlegekhez feladott összes bevétel 100 000 USD, akkor egy nyitó egyenleg jön létre a Fenntartott bevételek – 100 részére. Ha az **Egyetlen lezárása** lehetőséget választja, és a pénzügyi dimenzióértéket üresen hagyja, akkor minden tranzakció úgy adódik fel, hogy az adott dimenzióérték üres lesz.

## <a name="general-ledger-when-i-select-close-single-option-on-the-transfer-profit-and-loss-dimension-section-of-the-year-end-close-process-will-my-detailed-transactional-information-be-lost"></a>Főkönyv: Amikor az Év végi zárási folyamat Eredménydimenziók átvitele szakaszban az „Egyetlen lezárása” lehetőséget választom, elvesznek a részletes tranzakciós információk?

Az **Összes lezárása** és az **Egyetlen lezárása** lehetőséggel megadhatja, hogy az eredményszámlákra feladott tranzakciók pénzügyi dimenziói milyen pénzügyi eredmény fő számlára kerülnek át. Ez nem befolyásolja az eredményszámlák korábbi, részletes feladásait, és részletesek maradnak. A lehetőség befolyásolja a részletességi szintet, amely az új év nyitó egyenlegeként átkerül az elhatárolt pénzügyi eredményszámlákra. 

## <a name="general-ledger-the-year-end-close-process-is-failing-because-the-reporting-currency-for-the-year-does-not-balance-what-does-this-mean"></a>Főkönyv: Az év végi zárási folyamat sikertelen, mert az év jelentési pénznem nem fut ki nullára. Mit jelent ez?

Ez a hiba akkor tapasztalható, miután engedélyezte a **Figyelem a főkönyvi kiegyenlítés és az év végi zárás között** funkciót (a Figyelem funkció). Ha ez a funkció engedélyezve van, a már kiegyenlített főkönyvi tranzakciók a főkönyv év végi zárásának futtatásakor nem fognak szerepelni a következő pénzügyi év nyitó egyenlegében. A kiegyenlített főkönyvi tranzakciók kizárása kihívást jelenthetnek a vevők számára az év végi záráskor, ha a Főkönyvet egy jelentési pénznemmel határozták meg.   
A főkönyvi kiegyenlítés csak a könyvelési pénznemben történik.  A főkönyvi tranzakciók kiegyenlítésekor az ellenőrzés csak arról gondoskodik, hogy a könyvelési pénznem követelési egyenlőek legyenek a könyvelési pénznem követeléseivel. Ezeknek a főkönyvi tranzakcióknak a jelentési pénznemben szereplő összegei nincsenek ellenőrizve, és lehet, hogy nem egyenlőek bennük a követelések és jóváírások.  Ezenkívül a főkönyvi kiegyenlítés automatikusan nem számítja ki és nem adja fel a nyereséget/veszteséget a jelentési pénznemben.  Ezen korlátozások miatt léteznie kell egy nyereség-/veszteségtranzakciónak a jelentési pénznemben a főkönyvi kiegyenlítés végrehajtásakor.  Ha a nyereség/veszteség nem szerepel a főkönyvi kiegyenlítésben, az év végi záráskor egy egyenlegkülönbségre figyelmeztető üzenet fog megjelenni.  További információért lásd a [Figyelem a főkönyvi kiegyenlítési funkció és a jelentési pénznem nincs egyensúlyban között](reporting-currency-yec.md) lehetőséget.

## <a name="general-ledger-what-can-be-changed-to-help-enhance-the-performance-of-year-end-processing"></a>Főkönyv: Milyen módosításokkal lehet segíteni az év végi zárás feldolgozásának teljesítményét?

Számos módosítás segíthet az év végi zárás teljesítményének javításában. Javasoljuk, hogy értékelje ki az itt ajánlott módosításokat, és döntse el, hogy megfelelőek-e az Ön szervezete számára.

### <a name="optimize-year-end-close-service"></a>Optimalizált év végi zárás szolgáltatás

Az **Év végi zárás optimalizálása** szolgáltatás segítséget nyújt a Microsoft Dynamics 365 Finance ügyfelei számára, hogy javítsák az év végi zárást azáltal, hogy az erőteljes év végi feldolgozást egy mikroszolgáltatásba mozgatják. A hatékony év végi zárás során megtakarított idő lehetővé teszi minden Finance csapat számára, hogy időben reagálhassanak a szükséges kiigazításokra, és elkészítsék a pénzügyi jelentéseket. Azáltal, hogy a mikroszolgáltatáson dolgozzák fel az év végi zárást, értékes erőforrásokat szabadítanak fel. A feldolgozás új szintre emelése minimalizálja az SQL Server terhelését, és lehetőséget nyújt az ügyfeleknek, hogy új szintre emeljék az év végi zárásuk feldolgozásukat.

Az **Év végi zárás optimalizálása** szolgáltatás a 10.0.31-es verzióban érhető el, így több ügyfél is használhatja az új szolgáltatást a 2022-es év végi szezonra. Ezenkívül a szolgáltatást a 10.0.30-as és a 10.0.29-es verziókba is bevezették. További információ: [Év végi zárás optimalizálása](optimize-year-end-close.md).

### <a name="dimension-sets"></a>Dimenziókészletek

Az év végi zárás futtatásakor minden dimenziókészlet egyenlegét újraépítik. Ez a viselkedés közvetlen hatással van a teljesítményre. Egyes szervezetek felesleges, a korábbiakban valaha használt vagy a jövőben használni tervezett dimenziókészleteket hoznak létre. Mivel a program ezeket a szükségtelen dimenziókészleteket újraépíti az év végi zárás során, meghosszabbodik a folyamat. Alaposan értékelje ki a dimenziókészleteket, és törölje a szükségteleneket.

A szükségtelen dimenziókészletek a **BudgetDimensionFocusInitializeBalance** kötegelt feladatot is befolyásolják (**Főkönyv \> Számlatükör \> Dimenziók \> Pénzügyi dimenziókészletek**).

[![Pénzügyi dimenziókészletek.](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Év végi zárásra vonatkozó sablon konfigurálása

Az év végi zárásra vonatkozó sablon segítségével a szervezetek kiválaszthatják a pénzügyidimenzió-szintet, amelyet az eredményegyenlegek mérleg szerinti egyenlegbe való átviteléhez szeretnének használni. A beállítások segítségével a szervezetek kezelhetik a részletes pénzügyi dimenziókat (**Az összes lezárása**), amikor az egyenlegeket átviszik a mérleg szerinti eredménybe, vagy ha úgy döntenek, hogy az összegeket egyetlen dimenzióértékben szeretnék összegezni (**Egyetlen lezárása**). Ezt minden pénzügyi dimenziónál meg lehet határozni. A beállításokkal kapcsolatos további információkért lásd az [Év végi zárás](year-end-close.md) című cikket.

A teljesítmény javítása érdekében javasoljuk, hogy értékelje ki a szervezet igényeit, és ha lehetséges, zárjon le a lehető legtöbb dimenziót az **Egyetlen lezárása** év végi lehetőséggel. Ha egyetlen dimenzióértékre (amely üres érték is lehet) végez lezárást, a rendszer kevésbé részletes számításokat végez az eredmény-zárószámla bejegyzéseire vonatkozó egyenleg meghatározásakor.

### <a name="degenerate-dimensions"></a>Ténybe ágyazott dimenziók

A ténybe ágyazott dimenzió csupán kevés vagy semmilyen lehetőséget nem nyújt arra, hogy önmagában, illetve további dimenziókkal együtt újból felhasználhassák. Kétféle típusú ténybe ágyazott dimenziót különböztethetünk meg. Az első típus egy olyan dimenzió, amely egyénileg ténybe ágyazott. Ez a dimenziótípus rendszerint csak egyetlen tranzakcióban, vagy csupán kevés tranzakciókészletben jelenik meg. A második típus egy vagy több olyan dimenzióval együtt válik ténybe ágyazottá, amelyek a lehetséges generálható permutációk alapján megegyező potenciállal rendelkeznek. A ténybe ágyazott dimenziók jelentős mértékben befolyásolhatják az év végi zárási folyamat teljesítményét. A teljesítménnyel kapcsolatos problémák csökkentése érdekében az év végi zárási beállításban határozza meg az összes ténybe ágyazott dimenziót **Egyetlen lezárása** dimenzióként az előző szakaszban ismertetett eljárás segítségével.

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2022"></a>Kötelezettségek: Milyen módosításokat vezettek be 2022-ben az 1099-es év végi jelentés támogatásához?

#### <a name="update-to-all-1099-forms"></a>Frissítés az összes 1099-es űrlapra

A 2022-es adózási év 1099-es űrlapján a következő módosítások történtek:

- 2021-ben az évet az 1099-es űrlapokon rögzítették. 2022-től az évet a jelentésen töltik ki.

#### <a name="1099-misc"></a>1099-MISC

A 2022-es adózási év 1099-MISC űrlapján a következő frissítések történtek:

- 13. mező: Most már jelzi a törvény az adójogszabályoknak a külföldi számlával rendelkező adóalanyok általi betartásáról (FATCA) benyújtási követelményét.
- 14. mező: Most már a többlet végkielégítési kifizetések jelentéséhez használatos.
- 15. mező: Most már a nem minősített halasztott kompenzációs (NQDC) tervek szerinti kifizetés jelentésére használatos.
- 16. mező: Most már az állam által visszatartott adó jelentésére használatos.
- 17. mező: Most már a kifizető állami számának jelentéséhez használatos.
- 18. mező: Most már az állami bevétel jelentésére használatos.

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Kötelezettségek: 1099 – Hogyan módosítom az 1099-es űrlap mezőértékeit, valamint az olyan szállítók értékeit, amely az év során nem követte az 1099-es adatokat?

Az **1099 frissítése** funkció segítségével áttekintheti a korábban kifizetett számlatranzakciókat, hogy megfelelően újból hozzárendelhesse az 1099-es adatokat az **Adó – 1099** fülön megadott beállítások alapján (lásd a **Szállító** oldalon). Az **1099 frissítése** funkció használatához menjen a **Kötelezettségek \> Szállítók \> Minden szállító** lehetőségre, és válasszon ki egy szállítót, majd a Művelet panel **Szállító** lapján válassza az **1099 frissítése** lehetőséget.

## <a name="can-i-run-the-update-1099-functionality-for-all-my-vendors-at-once"></a>Futtathatom az 1099 frissítése funkciót az összes szállítónál egyszerre?

Az **Adó 1099-es adatainak frissítése több szállítóra** oldal használatával frissítheti az 1099-es mezőt egy szállítói rekordban, és frissítheti a tranzakciókat az 1099-es mezőben található adatokkal. Az oldal megnyitásához menjen a **Kötelezettségek \> Időszakos feladat \> Adó – 1099** lehetőségre. Az oldal eléréséhez az **1099-es mező és tranzakciók frissítése több szállítónál** biztonsági jogosultságba kell bejelentkeznie.

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-versus-update-all-in-the-update-1099-utility"></a>Kötelezettségek: 1099 – A meglévő 1099-es összegek újraszámítása és az Összes frissítése lehetőség összehasonlítása az 1099 frissítése segédprogramban

A **Meglévő 1099-es összegek újraszámítása** jelölőnégyzet a teljes kifizetett értékre állítja vissza az 1099-es összeget, amennyiben az **Összes frissítése** jelölőnégyzettel együtt használják.

[![1099-es adótranzakciók: a frissítési rutin futtatása előtt.](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

A **Meglévő 1099-es összegek újraszámítása** jelölőnégyzet csak akkor használható, ha a számlán részleges 1099-es értékek szerepelnek, vagy ha a számlát az 1099-es adóűrlapon módosították. Ha például a számla értéke 1000,00 dollár, de a felhasználó manuálisan beírja a számlán szereplő 500,00 dollár értéket az 1099-es funkciónál.

[![1099-es adótranzakciók: Az Összes frissítése és A meglévő 1099-es összegek újraszámítása lehetőségek megjelölése.](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

Ha ezt a számlát kifizetik, az 500,00 dollár lesz a kifizetett 1099-es összeg. Ha lefuttatja az újraszámítási rutint, 1000,00 dollárra módosul az 1099-es összeg, amely a teljes kifizetett összeg.

[![1099-es adótranzakciók: Az 1099-es rutin futtatása után.](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Kötelezettségek: 1099 – Az 1099-es tranzakciók manuális létrehozása

Előfordulhat, hogy egy szervezetnek manuálisan kell létrehoznia azokat az 1099-es tranzakciókat, amelyek nincsenek számlához társítva. Manuálisan is hozzáadhat 1099-es tranzakciókat, amelyhez a **Kötelezettségek \> Időszakos feladatok \> Adó - 1099 \> Szállítói kiegyenlítések az 1099-es jelentéshez** menüpontot használhatja. Válassza a **Manuális 1099-es tranzakciók** gombot.

A manuálisan létrehozott 1099-es tranzakciók nem frissülnek az **Összes frissítése** folyamattal, sem **A meglévő 1099-es összegek újraszámítása** folyamattal az **1099-es frissítés** segédprogramban.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Kötelezettségek: 1099 – Támogatja a Dynamics 365 Finance az 1096-os űrlapot?

A Dynamics 365 Finance nem nyomtatja ki az 1096-os éves összesítés és az egyesült államokbeli információküldés átvitele űrlapot.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Kötelezettségek: 1099 – Vannak olyan új funkciók, amelyek támogatják az állami szektor számára az 1099-es jelentéseket?

A program az állami szektor számára készült új funkcióval, az **1099-es adatok frissítése fő számla szerint** funkcióval bővült, amelyet a **Funkciókezelés** munkaterületen lehet engedélyezni. Ezzel a funkcióval a fő számla alapján lehet társítani a szállító 1099-es értékeit a könyvelési felosztásban, nem pedig a szállítói rekordon található alapértelmezett számla alapján.

További információkért lásd: [Szállítók beállítása az 1099-es kimutatáshoz](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
