---
title: Kettős pénznem
description: Ez a témakör a kettős pénznemről szól, ahol a könyvelési pénznem használt második könyvelési pénznemként a Microsoft Dynamics 365 Finance esetében.
author: kweekley
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, Ledger, AssetTransReportingCurrencyAmountsWizard,BankAccountTransReportingCurrencyAmountsWizard, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-10
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: b20c45952d2c0c28a1b785fd92bf47cfb25251fa3a3308d14130ad0f1c78305d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762067"
---
# <a name="dual-currency"></a>Kettős pénznem

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics 365 for Finance and Operations 8.1 verziójában (2018. október) megjelent funkció lehetővé teszi, hogy a jelentési pénznem célja módosítható legyen, és második könyvelési pénznemként legyen használva. Ezt a funkciót *kettős pénznemnek* nevezik. A kettős pénznem módosításai konfigurációs kulccsal vagy paraméterrel nem kapcsolhatók ki. Mivel a jelentési pénznem szolgál második könyvelési pénznemként, a jelentési pénznemben kiszámítási módja a feladási logikában megváltozott.

Ezenkívül több modul javítva lett a jelentési pénznem nyomon követése, jelentése és használata érdekében a különböző folyamatokban. Az érintett modulok a következők:

- Főkönyv 
- Pénzügyi jelentéskészítés 
- Kötelezettségek
- Kinnlevőségek 
- Készpénz- és bankkezelés 
- Tárgyi eszközök 
- Konszolidációk

Egy frissítést követően el kell végezni bizonyos lépéseket a Készpénz- és bankkezelés esetében. Ezért ügyeljen arra, hogy a témakör vonatkozó részeit figyelmesen olvassa el.

## <a name="posting-process"></a>Feladási folyamat

A feladási logika valamennyi tranzakcióra módosítva lett, amely főkönyvi könyvelési bejegyzést generál. Itt látható a jelentési pénznem korábbi számítási módja:

Tranzakció pénznemének összege \> Összeg könyvelési pénznemben \> Összeg a jelentési pénznemben

Például bejegyzésre kerül egy tranzakció a kanadai dollár (CAD) pénznemben. A CAD összeg le van fordítva a könyvelési pénznemre, amely az USA dollár (USD). Az USD összeg le van fordítva a jelentési pénznemre, amely az euró (EUR). Ezért az átváltási árfolyamnak léteznie kell a CAD és az USD, illetve az USD és az EUR között.

Az új számítás a következő:

Tranzakció pénznemének összege \> Könyvelési pénznem összege

Tranzakció pénznemének összege \> Jelentési pénznem összege

A változás miatt az átváltási árfolyamnak most már léteznie kell a CAD és az USD, illetve az CAD és az EUR között.

## <a name="reports-and-inquiries"></a>Jelentések és lekérdezések

Különféle jelentések és lekérdezések most már megjelenítik a jelentési pénznem összegét és a könyvelési pénznem összegét is. Nem minden jelentés és lekérdezés frissítése történt meg. Például nem módosultak azok a jelentések, amelyeket csak a tranzakció pénznemében mutatják az összegeket.

A módosítások a két minta egyikét követik:

- Ha a jelentésben vagy a lekérdezésben volt elég hely az könyvelési pénznem és a jelentési pénznemben összegeinek egyidejű megjelenítéséhez, a jelentési pénznem összege hozzá lett adva.
- Ha a jelentésben vagy a lekérdezésben nem elég hely mindkét pénznemben összegeinek, egy beállítást adtunk hozzá, hogy a felhasználók kiválaszthassák, melyik pénznem jelenjen meg.

Különféle jelentések és lekérdezések esetében hozzá lett adva egy logika a jelentési pénznem összegének elrejtésére, ha a jelentési pénzneme megegyezik a könyvelési pénznemmel, vagy ha a jelentési pénznemet a jogi személy esetében nem definiálták a főkönyvben.

## <a name="financial-journals"></a>Pénzügyi naplók

A pénzügyi naplók, például a főkönyvi napló és a szállítói számla naplója frissítve lett, hogy további információt tartalmazzanak a jelentési pénznemben. A bizonylat és a napló összegei most már a jelentési pénznemben láthatók. Ezen kívül a jelentési pénznem árfolyamáról most már információk jelennek meg a naplósorok **Általános** lapján. Ennek megfelelően felül lehet írni a jelentési pénznem árfolyamát a tranzakciók beírásakor.

## <a name="vendor-invoices-sales-orders-and-sales-agreements"></a>Szállítói számlák, értékesítési rendelések és értékesítési szerződések
A szállítói számlák, értékesítési rendelések és értékesítési szerződések frissítve lettek, így már tartalmazzák a jelentési pénznem rögzített árfolyamát. Ha a tranzakció pénzneme eltér, akkor meg lehet határozni a könyvelési pénznemhez és a jelentési pénznemhez is egy rögzített árfolyamot. Ha a könyvelési pénznem és a jelentési pénznem megegyezik, akkor a rögzített árfolyamot szinkronizálni fogja a rendszer úgy, hogy a könyvelési pénznem rögzített árfolyamát használja a jelentési pénznem rögzített árfolyamaként. Ehhez a konfigurációhoz a jelentési pénznem rögzített árfolyama nem módosítható. Ha a könyvelési pénznem és a jelentési pénznem eltér, akkor meg lehet határozni a könyvelési pénznemhez és a jelentési pénznemhez is egy rögzített árfolyamot a tranzakció bevitele során. Ha a jelentési pénznem nincs megadva a főkönyvben, akkor a **Jelentési pénznem rögzített árfolyama** mező nincs engedélyezve, és a rendszer nem számítja ki a jelentési pénznem összegét.

## <a name="module-changes"></a>Modulváltozások

A következő moduloknak használják a jelentési pénznemet második könyvelési pénznemként:

- [Főkönyv](#general-ledger)
- [Pénzügyi jelentéskészítés](#financial-reporting)
- [Kötelezettségek](#accounts-payable-and-accounts-receivable)
- [Kinnlevőségek](#accounts-payable-and-accounts-receivable)
- [Készpénz- és bankkezelés](#cash-and-bank-management)
- [Tárgyi eszközök](#fixed-assets)
- [Konszolidációk](#consolidations)

### <a name="general-ledger"></a>Főkönyv

Ha a jelentési pénznem meg volt adva a főkönyvben, a főkönyvbe már nyomon követte a jelentési pénznem összegeit minden könyvelési tételnél. Ezeket az összegeket azonban most már le is fordítja a rendszer a tranzakció pénznemének összegből.

A következő további módosítások történtek a **Főkönyv** modulon:

- Egy külön árfolyamtípust a lehet megadni a főkönyvben a jelentési pénznemhez. Ha egy szervezet nem szeretné használni a külön árfolyamtípust, üresen hagyhatja a jelentési pénznem árfolyamtípusának mezőjét. Azt is megteheti, hogy kiválasztja ugyanazt az árfolyamtípust, amely a könyvelési pénznemhez használt. Ha üresen hagyja a mezőt, a rendszer a könyvelési pénznem árfolyamtípusát használja.
- Egy új napló, a Jelentési pénznem kiigazítási naplója, lehetővé teszi a kiigazítások feladását a főkönyvi számlákra csak a jelentési pénznemben. Ez a napló lehetővé teszi csak a főkönyvi számlákra történő feladást. Nem támogatja a vállalatközi megoldást, és a pénznemnek a napló feladása szerinti jogi személy jelentési pénznemének kell lennie. A napló feladásakor a tranzakció pénzneme és a könyvelési pénznem összegei 0 (nulla), és a jelentési pénznem összegének feladása a tranzakcióhoz megadott összeggel történik. Mivel a jelentési pénznem használatának módja a **Kötelezettségek**, **Kinnlevőségek** és **Tárgyi eszközök** modulokban megváltozott, ez a napló használható a korrekciókhoz a frissítéseket követően. Példák arra, hogy hogyan használható ez a napló, a modulok szakaszokban olvashatók.
- Az időszak-felosztási folyamat frissítve lett, így az összegeket a tranzakció, a könyvelés és a jelentés pénznemében osztja fel. Korábban az összegeket a tranzakció és a könyvelési pénznemben osztották fel, és ezután fordították a könyvelési pénznem összegét a jelentési pénznemre. Ezt a viselkedést azzal járhatott, hogy továbbra is a jelentési pénznemben maradt az egyenleg a főkönyvi számlán. Most, amikor az összegek számítása és használata a könyvelési bejegyzésben történik, nincs fordítás.
- A devizaátértékelési folyamatban már átértékelte a jelentési pénznemben az összegeket. Azonban a jelentési pénznem összegének számítása a tranzakció pénzneméből történik, a témakör korábbi részében az itt leírtak szerint: [Feladási folyamat](#posting-process).
- Számos jelentés és lekérdezés a főkönyvben már rendelkezett a jelentési pénznemmel, de néhány nem. Az egyik példa a **Főkönyvi kivonat** listaoldal. Ezen listaoldal most oszlopokat tartalmaz a könyvelési pénznemhez és a jelentési pénznemhez. Vegye figyelembe, hogy ha a könyvelési pénznem és a jelentési pénznem megegyezik, vagy ha nincs jelentési pénznem meghatározva a főkönyvben, a jelentési pénznem oszlopai rejtettek.

### <a name="financial-reporting"></a>Pénzügyi jelentéskészítés

A **Pénzügyi beszámolók** modul továbbfejlesztése lehetővé teszik jelentési pénzösszegek feltüntetését a pénzügyi kimutatásokon kétféleképpen. Az oszlopdefinícióban közvetlenül jelentheti a főkönyvbe feladott jelentési pénznem összegeket (új funkció). Azt is megteheti, hogy folytatja az összegek lefordítását a könyvelési pénznemből a jelentési pénznembe (meglévő funkciót).

Ez a módosítás a **Pénznem megjelenítése** beállításon keresztül érhető el a oszlopdefiníciónál. Ha bejelöli a **Jelentési pénznem a főkönyvből**, az oszlopban szereplő összegek nem lesznek lefordítva. Ehelyett közvetlenül a főkönyvből lesznek jelentve. Ha azt szeretné, hogy az oszlop mutassa a lefordított összegeket, jelölje be az **XXXX fordítás** lehetőséget, ahol az *XXXX* jelentési pénznem, amelyet az oszlopnak meg kell jelennie. Ebben az esetben a könyvelési pénznem összegét a rendszer lefordítja a kiválasztott pénznemre a meglévő fordítás funkció segítségével.

### <a name="accounts-payable-and-accounts-receivable"></a>Kötelezettségek és kinnlevőségek

A **Kötelezettségek** és **Kinnlevőségek** modulok már nyomon követték a jelentési pénznem összegeket. Azonban az összegek nem jelentek meg, vagy nem voltak használva különböző folyamatokhoz. Az alábbi módosítások történtek:

- A jelentési pénznem összegek most már megjelennek a tranzakciókon a vevőknek és szállítóknak is. A jelentési pénznem összegek az egyes tranzakciók nyitó egyenlegeinél is láthatók.
- A korosítási folyamat frissítve lett, hogy a szervezet megtekinthesse a korosítási időszakokat a könyvelési pénznemben és a jelentési pénznemben.
- Különféle lekérdezések és jelentések frissítve lettek, így mutatják a jelentési pénznem összegeket. Néhány példa: **Vevő és főkönyv egyeztetése** és **Szállító és főkönyv egyeztetése** jelentések.
- A devizaátértékelési folyamatban már átértékelte a jelentési pénznemben az összegeket. Azonban a jelentési pénznem összegének számítása a tranzakció pénzneméből történik, az itt leírtak szerint: [Feladási folyamat](#posting-process).
- **Frissítési megfontolások:** A frissítés előtt a jelentési pénznem összegek kiszámítása a bizonylatokhoz (számlák, kifizetések, és így tovább) a könyvelési pénznemen keresztül történik. Például egy szervezet frissítése előtt feladnak egy számlát, és a számla nincs kifizetve. A frissítés során a számla könyvelési bejegyzése nem változik. Azonban a frissítés után a két pénznem módosítások érvénybe lépnek. Emiatt, amikor megtörténik a számla kifizetése, a kifizetés jelentési pénznem összeg most már a tranzakció pénznemének összegében van kiszámítva. A kifizetés és a számla kiegyenlítésekor, kis eltérés lehet a realizált nyereség/veszteség összegének számításában, mert jelentési pénznem összegének most már eltérő a kiszámítása. Ha a számított különbség jelentősnek minősül, az új jelentési pénznem kiigazítási napló segítségével kiigazítható a realizált nyereség/veszteség egyenlege és kötelezettségek/kinnlevőségek főkönyvi számlák a jelentési pénznemben.

### <a name="cash-and-bank-management"></a>Készpénz- és bankkezelés

Korábban a **Készpénz- és bankkezelés** modul nem követte nyomon a jelentési pénznemben levő összegeket a bankszámlákra feladott tranzakciókban. Egy frissítést követően a jelentési pénznem összegeket a rendszer automatikusan nyomon követi az új feladott tranzakciókra nézve. Azonban a jelentési pénznem összegeket hozzá kell adni a korábban feladott tranzakciókhoz az analitikus naplóban.

- **Frissítési megfontolások:** Mivel a bankszámla-tranzakciók korábban nem követték nyomon az analitikus naplóban a jelentési pénznem összegeket, egy varázsló hozzá lett adva, hogy a bankszámla-tranzakciókhoz jelentési pénznem összegeket is hozzáadhasson. Ez a varázsló **nem** végez újrafeladást a főkönyvbe. Ehelyett a jelentési pénznem összegeket a főkönyvből veszi, és frissíti őket az analitikus táblákban.

    - A varázsló elindításához: **Készpénz- és bankkezelés** \> **Beállítás** \> **Jelentési pénznem összegek hozzáadása bankszámla-tranzakciókhoz**.
    - A varázsló az aktuális vállalat összes bankszámlájához tartozó olyan tranzakciókat megjeleníti, amelyeknél a jelentési pénznemben megadott összeg 0 (nulla). Csak a frissítés előtt feladott tranzakciók szerepelnek.
    - A varázsló az egyes bankszámlához tartozó tranzakcióknál megkeresi a megfelelő könyvelési tételeket a főkönyvben, és beírja az alapértelmezett összeget a jelentés pénznemében. Annak ellenére, hogy az összegek szerkeszthetők, javasoljuk, hogy **ne** szerkessze őket. Ellenkező esetben lehet, hogy nem tudja elvégezni a bankszámla-egyenlegek egyeztetését a főkönyvbe. Csak akkor kell módosítani az összeget, ha a jelentési pénznem összege nem található a főkönyvben. A varázsló ebben az esetben megjeleníti a 0 (nulla) összeget a jelentési pénznemre.
    - Ha bejelöli az **Érvénytelenítés** lehetőséget a varázslóban, a bankszámla-tranzakciókat és a jelentési pénznem összeg módosításait menti a rendszer a varázsló következő futtatásáig. Azonban a bankszámla-tranzakciókon nem lesznek frissítve a jelentési pénznem összegei. A frissítés csak akkor történik meg, ha bejelöli a **Befejezést** a varázslóban. A varázslót többször is lehet futtatni. Ezért a helytelen jelentési pénznem összegek kijavíthatók, ha hibát fedez fel.

- A készpénz- és bankkezelés modulban nem módosultak folyamatok, de különböző jelentések és lekérdezések frissültek, így mutatják a jelentési pénznem összegeket. A pénzforgalmi előrejelzés jelentések kivétel. A jelentési pénznem összegeinek megjelenítésére nem módosultak.

### <a name="fixed-assets"></a>Tárgyi eszközök

Korábban a **Tárgyi eszköz** modul nem követte nyomon a jelentési pénznemben levő összegeket a tárgyieszköz-könyvbe feladott tranzakciókban. Egy frissítést követően a jelentési pénznem összegeket a rendszer automatikusan nyomon követi az új feladott tranzakciókra nézve. Azonban a jelentési pénznem összegeket hozzá kell adni a korábban feladott tranzakciókhoz az analitikus naplóban.

Ezenkívül jelentős módosítást végeztünk az értékcsökkenés folyamaton. Ezekhez a változtatásokhoz a frissítés után felhasználói beavatkozás szükséges. Fontos, hogy elolvasta és megértse az alábbi változtatások akkor is, ha még nem használt tárgyi eszközöket.

- Módosult az, ahogy az értékcsökkenés folyamat meghatározza a jelentési pénznem összegét. A következő helyzet annak az összehasonlítására szolgál, hogy az értékcsökkenés hogyan határozta meg korábban a jelentési pénznem összegét, és hogy határozza meg a jelentési pénznem összegét most.



    **Értékcsökkenési eset**

    Az eszköz beszerzése és feladása a következő összegekkel történik. Vegye figyelembe, hogy a jelentési pénznem összege fel lesz adva a főkönyvbe, de nem tárolódik a tárgyi eszköz analitikus táblákban.

    | Tranzakció típusa | Tranzakció összege | Árfolyam | Könyvelési pénznem összege | Árfolyam | Jelentési pénznem összeg |
    |------------------|--------------------|---------------|----------------------------|---------------|---------------------------|
    | Beszerzés      | 1 000 000 DKK      | 2,0           | 500 000 USD                | 2,5           | 200 000 EUR               |

    **Korábbi értékcsökkenés a jelentési pénznemben**

    Az év végén az értékcsökkenési javaslat lefut, és kiszámítja a következő összegeket.

    | Tranzakció típusa | Tranzakció összege | Árfolyam | Könyvelési pénznem összege | Árfolyam | Jelentési pénznem összeg |
    |------------------|--------------------|---------------|----------------------------|---------------|---------------------------|
    | Értékcsökkenés     | 50 000 USD         | 1,0           | 50 000 USD                 | 2,6           | 19 230,77 EUR             |

    Az értékcsökkenési javaslat a futtatásakor kiszámítja a könyvelési pénznem összegét az értékcsökkenési módszer használatával. Ezt az összeget a jelentési pénznemre váltja az aktuális USD és EUR közötti átváltási árfolyamon. Ez a fordítás problémákat eredményez, mivel az eszköz nem lesz teljes mértékben értékcsökkentve a jelentési pénznemben azonnali árfolyam használata esetén.

    **Új értékcsökkenés a jelentési pénznemben**

    Az értékcsökkenés folyamat módosítva lett, hogy a jelentési pénznem összegét is az értékcsökkenési módszer használatával számítsa ki. Az alábbi történik meg a tárgyi eszköz értékcsökkenési futtatásakor.

    | Tranzakció típusa | Tranzakció összege | Árfolyam | Könyvelési pénznem összege | Árfolyam                                                       | Jelentési pénznem összeg |
    |------------------|--------------------|---------------|----------------------------|---------------------------------------------------------------------|---------------------------|
    | Értékcsökkenés     | 50 000 USD         | 1,0           | 50 000 USD                 | 2,5<blockquote>[!NOTE] Annak ellenére, hogy ez az árfolyam jelenik meg, nem használt a jelentési pénznembe való fordításhoz.</blockquote> | 20,000 EUR                |

    Az értékcsökkenési javaslat a futtatásakor kiszámítja a könyvelési pénznem összeget és a jelentési pénznem összeget is az értékcsökkenési módszer szerint. Az összegeket a rendszer ezután a könyvelési bejegyzésben a főkönyvben használja. Nem történik a jelentési pénznem összegének meghatározására fordítás.

- **Frissítési megfontolások:** Mivel a tárgyi eszköz-tranzakciók korábban nem követték nyomon az analitikus naplóban a jelentési pénznem összegeket, egy varázsló hozzá lett adva, hogy a tárgyieszköz-tranzakciókhoz jelentési pénznem összegeket is hozzáadhasson. Ez a varázsló **nem** végez újrafeladást a főkönyvbe. Mivel módosult az, ahogy az értékcsökkenési javaslat kiszámítja a jelentési pénznem összegeit, a varázslót **kötelező** futtatni és végigvinni minden vállalatnál, mielőtt a szervezet értékcsökkenési tranzakciókat adhatna meg.

    - A varázsló elindításához, jelölje be: **Tárgyi eszközök** \> **Beállítás** \> **Jelentési pénznem összegeinek hozzáadása tárgyieszköz-könyvekhez**.
    - A varázsló az aktuális vállalat összes tárgyieszköz-könyvéhez tartozó olyan tranzakciókat megjeleníti, amelyeknél a jelentési pénznemben megadott összeg 0 (nulla). Csak a frissítés előtt feladott tranzakciók szerepelnek.
    - A varázsló **nem** kéri le a jelentési pénznem összegeket a főkönyvből. Amint azt az előző helyzet láttuk, a jelentési pénznemben a főkönyvbe eredetileg feladott összegek helytelenül használták az azonnali árfolyamot. Ezeknek az összegek nem kellene megjelenniük a tárgyi eszköz analitikus naplóban, mert a következő értékcsökkenés-számítás a hibás összegeket fogja használni. Ehelyett a varázsló megkeresi az első beszerzés dátumának árfolyamát. Ezután ezt az árfolyamot használja a jelentési pénznem összegének javaslására, amelyet fel kell adni az analitikus naplóba. Ezt mutathatja például a varázsló az előző esetnél.

        | Tárgyi eszköz | Könyv      | Tranzakció típusa | Tranzakció dátuma | Pénznem | Összeg a tranzakció pénznemében. | Összeg  | Árfolyam | Jelentési pénznem összeg |
        |-------------|-----------|------------------|------------------|----------|--------------------------------|---------|-----------|---------------------------|
        | BUIL-00001  | 200\_SLLT | Beszerzés      | 2016/3/6         | DKK      | 1 000 000                      | 500,000 | 2.5       | 250,000                   |
        | BUIL-00001  | 200\_SLLT | Értékcsökkenés     | 2016/3/6         | USD      | 50,000                         | 50,000  | 2.5       |  25,000                   |
        | BUIL-00001  | 200\_SLLT | Értékcsökkenés     | 2016/3/6         | USD      | 50,000                         | 50,000  | 2.5       |  25,000                   |
        | BUIL-00001  | 200\_SLLT | Értékcsökkenés     | 2016/3/6         | USD      | 50,000                         | 50,000  | 2.5       |  25,000                   |

    - Számos vevő követte nyomon munkafüzetekben az eszköz-tranzakciók részletei. Ezeket az adatok magukban foglalják az átváltási árfolyamokat és az összegeket. Ha ezek az adatok egy munkafüzetben vannak, hozzon létre egy egyéni árfolyamtípust, és frissítse az átváltási árfolyamokkal a munkafüzetből. A rendszerárfolyam típusát fel lehet használni a beszerzési dátumon alapértelmezett árfolyam megadására, és a jelentési pénznemben számított összeg kiszámításához. Ha nincs kiválasztva árfolyamtípus, a varázsló a főkönyvben definiált árfolyamtípust használja.
    - A könyvelési pénznem és a jelentési pénznem összege módosítható. Ha az árfolyam megváltozik, a program az új árfolyam használatával újraszámítja a jelentési pénznem összegét.
    - Ha bejelöli az **Érvénytelenítés** lehetőséget a varázslóban, a tárgyieszközkönyv-tranzakciókat és az átváltási árfolyam jelentési pénznem összeg módosításait menti a rendszer a varázsló következő futtatásáig. Azonban a tárgyieszközkönyv-tranzakciókon nem lesznek frissítve a jelentési pénznem összegei. A frissítés csak akkor történik meg, ha bejelöli a **Befejezést** a varázslóban. A varázslót többször is lehet futtatni. Ezért a helytelen jelentési pénznem összegek kijavíthatók, ha hibát fedez fel.
    - A jelentési pénznem összeg teljes frissítése esetén az analitikus naplóban, **kötelező** beállítani a **Frissítette az összes jelentési pénznem összeget a tárgyieszköz-könyv tranzakcióin?** lehetőséget az **Igen** opcióra, majd ki kell választania a **Befejezés** elemet. Értékcsökkenési számítás nem hajtható végre, amíg a **Frissítette az összes jelentési pénznem összeget a tárgyieszköz-könyv tranzakcióin?** lehetőség beállítása nem **Igen**. Az **Igen** beállítása után a varázsló nem érhető el.
    - A tárgyieszköz-tranzakcióknak az analitikus naplóban a jelentési pénznem összegekkel való frissítése után ezek az összegek nem fognak egyezni az eredetileg a főkönyvbe feladott összegekkel. Azonban a jelentési pénznem kiigazítási napló használatával az értékcsökkenés főkönyvi számlák egyenlegei frissíthetők a főkönyvben, hogy megegyezzenek az eredetileg feladott összegekkel.
    - Az új **Eszköztranzakció jelentési pénznem összegei** entitás, amely hozzá lett adva az **Adatkezelés** munkaterülethez, lehetővé teszi az adatok exportálását a varázslóból. Az adatokat ezután a tárgyi eszköz analitikus értékcsökkenési tranzakciók egyenlege meghatározására használhatja. Az egyenleget ezután fel lehet használni a főkönyvi jelentési pénznem korrekció összegének meghatározására.

- **Frissítési megfontolások:** Új beállítási mezők lettek hozzáadva a tárgyi eszközökhöz, és az értékcsökkenés kiszámításánál használatosak. Előfordulhat, hogy a mezőket a következő értékcsökkenési számítás előtt frissíteni kell.

    - A tárgyieszköz-könyvben (**Tárgyi eszközök** \> **Könyvek**), az **Általános** gyorslapon van egy új **Beszerzési ár a jelentési pénznemben** mező.
    - A tárgyieszköz-könyvben (**Tárgyi eszközök** \> **Könyvek**), az **Értékcsökkenés** gyorslapon van egy új **Várható selejt értéke a jelentési pénznemben** mező.
    - A tárgyieszköz-paramétereknél (**Tárgyi eszközök** \> **Beállítás** \> **Tárgyieszközök-paraméterek**), az **Általános** gyorslapon van egy új **Minimális értékcsökkenési összeg a jelentési pénznemben** mező.
    - A könyveknél (**Tárgyi eszközök** \> **Beállítás** \> **Könyvek**), az **Általános** gyorslapon van két új mező: **Kerekített értékcsökkenés a jelentési pénznemben** és **Nettó könyv szerinti érték megtartása jelentési pénznemben**.

- Mivel az értékcsökkenési javaslat az összegeket a könyvelési pénznemben és a jelentési pénznemben is kiszámítja, a tárgyieszköz-napló frissítése megtörtént, hogy értékcsökkenési összeget a jelentési pénznemben mutassa. Értékcsökkenési tranzakciók esetén a tranzakció pénzneme mindig a könyvelési pénznem. Ebből következően ezek az összegek továbbra is megjelennek a **Tartozik** és **Követel** oszlopokban. Két új oszlop, **Tartozás jelentési pénznemben** és **Jóváírás jelentési pénznemben**, hozzá lettek adva a rácshoz.

    - Az új mezők csak akkor érhetők el, ha a tranzakció típusa a négyféle értékcsökkenési típus egyike: **Értékcsökkenés**, **Értékcsökkenési helyesbítés**, **Rendkívüli értékcsökkenés** vagy **Különleges értékcsökkenési keret**.
    - Ha egy értékcsökkenési tranzakciótípus szerepel a tárgyieszköz-naplóban, az új oszlopokban a jelentési pénznem összege jelenik meg. Ezeket az összegeket módosíthatja.
    - Ha a főkönyvben a könyvelési pénznem és a jelentési pénznem megegyezik, az összegek folyamatosan szinkronban lesznek. Ha módosítja a **Követel** összeget, a **Jóváírás jelentési pénznemben** összege automatikusan módosul, úgy, hogy megfeleljen neki.
    - Ha bármilyen más tranzakciótípus szerepel a tárgyieszköz-naplóban, ha a **Tartozás jelentési pénznemben** és a **Követelés jelentési pénznemben** összegek soha nem jelennek meg, feladás előtt és után sem. A könyvelési pénznem és a jelentési pénznem összegei továbbra is elérhetők a bizonylaton, amely a főkönyvbe végzi a feladást.
    
### <a name="consolidations"></a>Konszolidációk
    
A Dynamics 365 Finance 10.0.5 verziójában (2019. október) bevezetett funkciók lehetővé teszik a szolgáltatások funkcióinak kezelését a konszolidáció és a kettős pénznem továbbfejlesztett rugalmassága érdekében. A funkció engedélyezéséhez nyissa meg a **Funkciókezelés** munkaterületet, és jelölje be a **Kettős pénznem funkció engedélyezése a Főkönyv konszolidálásához** jelölőnégyzetet.

A Főkönyv konszolidálásához egy új beállítás lett hozzáadva, amely a forrásoldali vállalatoktól származó könyvelési vagy jelentési pénznemek összegeit összesíti. Ha a könyvelési vagy a jelentési pénznem megegyezik a konszolidációs vállalat könyvelési vagy jelentési pénznemével, akkor az összegeket a program az átváltás helyett közvetlenül másolja.

-  Ezután kiválaszthatja, hogy a forrás vállalattól a könyvelési pénznemet vagy a jelentési pénznemet használja-e a konszolidációs vállalatban a tranzakciós pénznemnek.

- A forrásvállalat könyvelési vagy jelentési pénzneme közvetlenül lesz másolva a konszolidációs vállalat könyvelési vagy jelentési pénznemösszegeire, ha valamelyik pénznem megegyezik. A konszolidációs vállalatban a könyvelési és jelentési pénznem összegeit az árfolyam alapján számítja ki a program, ha a pénznemek egyike sem egyezik meg.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]