---
title: Szállítói számlák áttekintése
description: Ez a cikk a szállítói számlákkal kapcsolatos általános információkat tartalmazza.
author: abruer
ms.date: 02/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 565e45a1c396b9144b4a6437056a0040b2fbde1d
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228751"
---
# <a name="vendor-invoices-overview"></a>Szállítói számlák áttekintése

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Ez a cikk a szállítói számlákkal kapcsolatos általános információkat tartalmazza. A szállítói számlák termékekért és szolgáltatásokért cserébe igényelt kifizetés kérelmei. A szállítói számlák vonatkozhatnak már folyamatban lévő szolgáltatásokra, vagy bizonyos termékek és szolgáltatások esetén beszerzési rendeléseken is alapulhatnak.

## <a name="vendor-invoices"></a>Szállítói számlák

A beszerzési rendelés szállítói számlája olyan számla, amit a szállítóval egyeztetett beszerzési rendelés alapján termékek vagy szolgáltatások kézbesítésekor jön létre. A szállítói számla fejlécet, valamint a cikkekre vagy szolgáltatásokra vonatkozó egy vagy több sort tartalmaz. A szállítói számlával a ciklus beszerzési rendelésből termékbevételezésre és szállítói számlára léphet tovább.

Annak ellenére, hogy néhány szállítói számla beszerzési rendeléshez kapcsolódik a szállítói számlák tartalmazhatnak olyan sorokat is, amelyek nem tartoznak beszerzési rendeléssorokhoz. Olyan szállítói számlákat is létrehozhat, amelyek nincsenek hozzárendelve egyetlen beszerzési rendeléshez sem. Ezek a szállítói számlák a folyamatban lévő szolgáltatásokat, például egy közüzemi számlát jelenthetnek. Folyamatban lévő szolgáltatás hozzáadása esetén nem kell beszerzési rendelésre hivatkozni.

Számos módja van a szállítói számla bevitelének:

- A szállítói számlajegyzék használatával gyorsan adhat meg számlákat amelyek nem rendelkeznek hivatkozással egy beszerzési rendeléshez, így elhatárolhatja a kiadást. Szállítói számla jóváhagyási napló használatával kiválaszthat számlákat és feladhatja azokat a szállítói egyenlegbe a könyvelt összeg sztornírozásához.
- A szállítói számlanapló használatával gyorsan megadhat egy lépésben számlákat amelyek nem hivatkoznak a beszerzési rendelésre.
- A szállítói gyűjtőszámlával a szállítói számlajegyzékkel gyorsan megadhat számlákat a költség elhatárolásához. Megnyithatja a kapcsolódó beszerzési rendeléseket később a számla kiadási számlára történő feladásához.
- A **Nyitott szállítói számlák** és a **Függőben lévő szállítói számlák** lapok lehetővé teszik a szállítói számlák létrehozását a visszaigazolt beszerzési rendelésekből.

Az alábbi vitafórumon további információkat tudhat meg a **Nyitott szállítói számlák** vagy a **Függőben lévő szállítói számlák** oldalak használatáról, ha szállítói számlát szeretne létrehozni egy beszerzési rendelésből.

## <a name="understanding-invoice-line-quantities"></a>Számlasor mennyiségek ismertetése

Ha szállítói számlát egy kapcsolódó beszerzési rendelésből nyit meg, akkor a rendszerben számlasorok jönnek létre a beszerzési rendelésből. Alapértelmezés szerint a rendszer a mennyiségeket termékbevételezésből veszi át. Azonban a következő alapértelmezett viselkedések bármelyikét használhatja:

- **Most bevételezett mennyiség** – Használja részleges szállítmányokhoz ezt a lehetőséget. A Mennyiség mezőben **szereplő** **alapértelmezett** érték a beszerzési rendelés Bevétele mezőben megadott mennyiségre lesz állítva.
- **Rendelt mennyiség** – Használja teljes szállítmányokhoz ezt a lehetőséget. A Mennyiség mezőben **szereplő** **alapértelmezett** érték a beszerzési rendelés Megrendelve mezőjében megadott mennyiségre lesz állítva.
- **Regisztrált mennyiség** – Használja ezt a lehetőséget, ha a cikkhez regisztráció szükséges a megadott a **Cikkmodell csoportok** oldalon. A **Mennyiség** mezőben szereplő alapértelmezett érték a regisztrált fizikai módosítási mennyiség.
- **Termékbevételezési mennyiség** – Akkor válassza, ha a rendelés már átesett termékbevételezésen. A Mennyiség mezőben szereplő alapértelmezett **érték** az elérhető termékbevételezések összmennyisége.
- **Regisztrált mennyiség és szolgáltatások** – Akkor használja, ha az érkeztetési naplóban raktározott cikkek vagy a nem raktározott cikkek regisztrált mennyiségek. Ez a beállítás a szolgáltatásokat is tartalmazza, függetlenül attól, hogy regisztrálva vannak-e.

Ha a jogi személy számlaegyeztetést használ, akkor megtekintheti a mennyiségegyeztetés eredményeit a **Termékbevételezés mennyiségi egyeztetése** oszlopban. Használhatja az **Egyezetés részletei** gombot is a műveleti ablaktábla **Ellenőrzés** fülén a mennyiségegyeztetés eredményeinek megtekintéséhez.

## <a name="adding-a-line-that-wasnt-on-the-purchase-order"></a>Új sor hozzáadása amely nem volt megnyitva a beszerzési rendelésen

Hozzáadhat sorokat, amelyek nem voltak a szállítói számla beszerzési rendelésében. Ki kell választania egy cikkszámot vagy beszerzési kategóriát. Ezután hozzáadhatja mennyiségeket, árakat és összegeket a sorhoz. A sor csak az egyeztetési irányelvek számlaösszegeiben fog szerepelni.

## <a name="submitting-a-vendor-invoice-for-review"></a>Szállítói számla küldése ellenőrzésre

A szervezet használhat meghatározott munkafolyamatokat a szállítói számlák ellenőrzési eljárásához. A munkafolyamat előírhatja a számlafejléc, a számlasor vagy mindkettő ellenőrzését. A munkafolyamat vezérlőelemei a fejlécre vagy a sorra vonatkoznak, attól függően, hogy hol van a fókusz, amikor a vezérlőelemet választja. A Küldés gomb **helyett** a Küldés **gomb elküldi a** szállítói számlát az felülvizsgálati folyamaton keresztül.

### <a name="preventing-invoice-from-being-submitted-to-workflow"></a>A számla beküldésének megakadályozása a munkafolyamatba 

A következőkben többféle módot ismerhet meg, amelyekkel megakadályozhatja, hogy egy számla beküldésre kerüljön a munkafolyamatba.

- **A számla végösszege és a regisztrált végösszeg nem egyenlő.** A számlát eladó felhasználó figyelmeztetést kap, ha az összegek nem egyeznek meg. Ez a figyelmeztetés lehetőséget ad a felhasználónak az egyenlegek korrigálére, mielőtt újrakenné a számlát a munkafolyamat-rendszerbe. Ez **a** **funkció akkor használható, ha** **a Munkafolyamatba való beküldés tiltása, ha a számla végösszege és a regisztrált számlaösszeg nem egyenlő a Funkciókezelési** **lapon** és a Munkafolyamat beállításban szereplő paraméterrel, ha a Számlaösszeg és a Regisztrált végösszeg beállítás nincs megadva a Kötelezettségek paraméterei lapon. 
- **A számla nem hozzárendelt költségeket tartalmaz.** A számlát benyújtó felhasználó figyelmeztetést kap, ha a számlán nem felosztott költségek vannak. Ezzel a módszerrel a felhasználó még a munkafolyamat rendszerbe való újrabevallása előtt korrigálhatja a számlát. Ez a **funkció akkor használható, ha a Kötelezettségek paraméterei lapon be van kapcsolva a Nem lefoglalt költségek a munkafolyamatba való beküldés stb. paramétere, ha a Funkciók kezelése lapon és a** **·** **·** **Munkafolyamat** funkcióban vannak fel nem osztott költségek paraméterek.
- **A számla sorszáma megegyezik egy másik feladott számla sorszámával.** A számlát benyújtó felhasználó figyelmeztetést kap, ha olyan számlát talált, amely ismétlődő számmal rendelkezik. A felhasználó kijavíthatja az ismétlődő számot, mielőtt újrakenheti a számlát a munkafolyamat-rendszernek. A figyelmeztetés akkor jelenik meg, ha **a** Kötelezettségek között a Számlaszám ellenőrzése paraméter értéke "Ismétlődés elutasítása **"**. Ez a funkció akkor érhető el **Munkafolyamatba küldés tiltása, ha a számlaszám már létezik egy feladott számlán, és az Ön rendszere nincs beállítva ismétlődő számlaszámok fogadására** paraméter a **Funkciókezelés** oldalon be van kapcsolva.
- **A számla olyan sort tartalmaz, ahol a számlázott mennyiség kisebb, mint az egyező termékbevételezési mennyiség.** A számlát elküldő vagy a feladni próbáló felhasználó egy üzenetet kap, hogy a mennyiségek nem egyenlőek. Ez az üzenet lehetőséget ad a felhasználónak arra, hogy helyeselje az értékeket, mielőtt újra elküldené a számlát a munkafolyamat-rendszernek. Ez **a** **·** **·** **funkció** akkor használható, ha a Kötelezettségek paraméterei oldalon be van kapcsolva a Szállítói számlák munkafolyamatba történő benyújtásának és feladásának blokkolása paraméter, valamint a Kötelezettségek paraméterei lapon a Feladás és beküldés a munkafolyamatba paraméter.

## <a name="matching-vendor-invoices-to-product-receipts"></a>Szállítói számlák egyeztetése a termékbevételezésekkel

Megadhatja és mentheti a szállítói számlák adatait, és a számlasorokat egyeztetheti a termékbevételezési sorokkal. Részleges mennyiségeket is egyeztethet a soroknál.

Szállítói számlát létrehozhat a termékbevételezési sorokban az adott dátum napjáig bevételezett cikkek alapján akkor is, ha még nem érkezett meg egy meghatározott beszerzési rendelés összes cikke. Például ezt olyankor teheti meg, amikor egy szállító havonta egy számlát küld, amely a szállító által az adott hónapban kézbesített összes szállítást fedezi. Mindegyik termékbevételezés a beszerzési rendelésen szereplő cikkek egy-egy részleges vagy teljes szállításának felel meg.

Amikor egy számla munkafolyamatban van, a jóváhagyó frissítheti a számlamennyiségeket, hogy azok megegyezzenek az **Egyeztetendő termékbevételezések mennyisége** mezőben szereplő értékkel. Ezt úgy teheti meg, hogy a **Funkciókezelés** munkaterületen a **Termékbevételezési mennyiségeknek megfelelő számlamennyiségek frissítése a munkafolyamatban** lehetőséget választja ki, és kiválasztja az **Engedélyezés** lehetőséget. Ha a munkafolyamat egyik jóváhagyója eltávolította a számlasor összes termékbevételezésének összes egyezését, a számlasor törlődik. Ha ez a funkció nincs engedélyezve, a rendszer nem frissíti a számlamennyiségeket a munkafolyamat számláira vonatkozóan.

A számla feladásakor a **Számlahátralék** mennyisége minden cikkre vonatkozóan frissül a kiválasztott termékbevételezéseken fogadott mennyiségekkel. Ha a beszerzési rendelésen található összes cikknél 0 (nulla) a **Számlahátralék** és a **Fennmaradó szállítása** értéke, a beszerzési rendelés **Számlázott** állapotú lesz. Ha a számlához tartozó **Számlahátralék** mennyisége nem 0, akkor a beszerzési rendelés állapota változatlan marad, és további számlákat lehet hozzá rögzíteni.

Ez a lehetőség azt feltételezi, hogy legalább egy termékbevételezést feladtak a beszerzési rendeléshez. A szállítói számla ezeken a termékbevételezéseken alapul, és azok mennyiségeit tükrözi. A számla pénzügyi adatai a számla feladásakor megadott információkon alapulnak.

További informáiók: [A szállítói számlák rögzítése és összevetése a bevételezett mennyiséggel](../accounts-payable/tasks/record-vendor-invoice-match-against-received-quantity.md)

## <a name="configure-an-automated-task-for-vendor-invoice-workflow-to-post-the-vendor-invoice-using-a-batch-job"></a>Automatizált feladat konfigurálása a szállítói számla munkafolyamathoz a szállítói számla kötegelt feladattal történő feladásához

A szállítói számla munkafolyamatához hozzáadhat egy automatizált feladási feladatot, hogy a számlák feldolgozása egy kötegben történjen. A számlák kötegek feladásával a munkafolyamat folytatódhat anélkül, hogy várnia kellene a feladás befejezésére, ami javítja a munkafolyamatnak elküldött összes feladat általános teljesítményét.

Ha kötegelten szeretné feladni a szállítói számlát , akkor a **Funkciókezelés** oldalon kapcsolja be a **Szállítói számlák kötegelt feladása** paramétert. A szállítói számlák munkafolyamatait a **Kötelezettségek > Beállítások > Kötelezettségek munkafolyamatai** helyen konfigurálhatja.

A munkafolyamat-szerkesztőben látható **Szállítói számlák feladása kötegben** feladat attól függetlenül, hogy a **Szállítói számla kötegelt feladása** funkcióparaméter engedélyezve van-e. Ha nincs engedélyezve a funkcióparaméter, akkor egy olyan számla, amely tartalmazza a **Szállítóói számla feladása kötegelt feladattal** opciót nem lesz feldolgozva munkafolyamatban, amíg a paraméter engedélyezve nem lesz. A **Szállítói számla kötegelt feladattal történő feladása** nem használható ugyanabban a munkafolyamatban, mint a **szállítói számlák feladása** automatizált feladat. Ezenkívül a **Szállítói számla feladása kötegelt feladattal** a munkafolyamat-konfiguráció utolsó eleme kell legyen.

Megadhatja, hogy hány számla kerüljön egy kötegbe, valamint a köteg újraütemezése előtt kivárandó órák száma, a **Kötelezettségek > Beállítások > Kötelezettségek paraméterei > Számla > Számla munkafolyamata** helyen. 

## <a name="working-with-multiple-invoices"></a>Több számla használata

Dolgozhat egyszerre több számlával, és fel is adhatja azokat egyszerre. Ha több számlát kell létrehoznia, akkor használja a **Függőben lévő szállítói számlák** oldalt. Ha több szállítói számlát kell feladásra és nyomtatásra használnia, használja a Számla-jóváhagyási **naplót**. Ha számla-jóváhagyási **naplót** használ, a beszerzési rendeléshez legalább egy termékbevételezést fel kell lennie adva, a beszerzési rendelés számláját pedig egy számlajegyzékbe. A számla pénzügyi adatai a számlajegyzékbe feladott számláról származnak.

## <a name="recovering-vendor-invoices-that-are-being-used"></a>Használatban lévő szállítói számlák visszaállítása

Amikor egy szállítói számla használatban van, akkor egy másik felhasználó által nem szerkeszthető. Azonban a számla állapota időnként azt jelezheti, hogy a számla használatban van, annak ellenére, hogy az nincs aktívan szerkesztve. Ha például az alkalmazás nem válaszolt, miközben a számlán módosították, vagy a felhasználó lehet, hogy véletlenül hagyta megnyitva a számlát az alkalmazásban.

Használhatja a **Szállítói számlák helyreállítása** lapot a szállítói számlák visszaállításához vagy feloldásához, amelyeket több, mint négy órája vannak használatban, hogy azok szerkeszthetők legyenek. Megnyithatja ezt a lapot az **Ismétlődő feladat** navigációs elemről vagy a **Szállítói számla bevitele** munkaterület egy csempéjéről. A számla visszaállítást követően az szerkeszthető lesz a **Szállítói számla** oldalon.

A **Szállítói számlák helyreállítása** laphoz csak akkor férhet hozzá, ha a **Használatban lévő szállítói számlák helyreállítása** biztonsági kötelezettség és jogosultság Önhöz van rendelve. Ezenkívül a **Szállítói számla visszaállítása** paramétert a **Kötelezettségek paraméterei** lapon be kell kapcsolni.

## <a name="resetting-the-workflow-status-for-vendor-invoices-from-unrecoverable-to-draft"></a>Szállítói számlák munkafolyamat-állapotának visszaállítása Helyreállíthatatlan állapotból Tervezet állapotba

A helyreállíthatatlan hiba miatt leállított munkafolyamat-példány **Helyreállíthatatlan** munkafolyamat-állapotot kap. Ha egy szállítóiszámla-munkafolyamat állapota **Helyreállíthatatlan**, a **Visszahívás** kiválasztásával visszaállíthatja **Tervezet** állapotba. Ezután szerkesztheti a szállítói számlát. Ez a funkció akkor érhető el, ha a **Funkciókezelés** oldal **Munkafolyamat állapot visszaállítása a szállítóiszámla Helyreállíthatatlan állapotból Tervezet állapotba** paramétere be van kapcsolva.

A **Munkafolyamat-előzmények** oldal segítségével visszaállíthatja a munkafolyamat állapotát **Tervezet** értékre. Ezt az oldalt a **Szállítói számla**  vagy a **Közös > Lekérdezések > Munkafolyamatok** lehetőséghez navigálva nyithatja meg. A munkafolyamat állapotának **Tervezet** értékre való visszaállításához válassza ki a **Visszahívás** lehetőséget. A munkafolyamat-állapotot úgy is visszaállíthatja tervezetnek, ha a **Szállítói számla** vagy a **Függőben lévő szállítói számlák** oldalon kiválasztja a **Visszahívás** műveletet. Miután a munkafolyamat állapotát visszaállította **Tervezet** állapotba, szerkeszthetővé válik a **Szállítói számlák** lapon.

## <a name="viewing-the-invoice-total-on-the-pending-vendor-invoices-page"></a>A számla végösszegének megtekintése a függőben lévő szállítói számlák lapon

A függőben lévő szállítói számlák lapon megtekintheti a számla összegét a **Függőben lévő szállítói számlák** oldalon a **Kötelezettségek paraméterei** oldalon lévő **Számla végösszegének megjelenítése a függő szállítói számlák listájában** paraméter engedélyezésével. 

## <a name="vendor-open-transactions-report"></a>Nyitott szállítói tranzakciók – jelentés

A **Nyitott szállítói tranzakciók** jelentés részletes adatokat nyújt az egyes szállítókhoz tartozó, a megadott dátumon nyitott tranzakciókról. Ezt a jelentést gyakran használják auditálási eljárás során a szállító könyvi tranzakciók és a főkönyvi számlatranzakciók közötti egyenlegek ellenőrzésére.

A jelentés minden tranzakcióhoz a következő adatokat tartalmazza:

- Számla száma
- Tranzakció dátuma
- Bizonylatszám
- A tranzakció összege a tranzakció pénznemében és a könyvelési pénznemben
- Jóváírás egyenlege a tranzakció pénznemében és a könyvelési pénznemben
- Terhelés egyenlege a tranzakció pénznemében és a könyvelési pénznemben
- Részösszeg a könyvelési pénznemben
- Fizetési határidő

### <a name="filter-the-data-on-the-report"></a>A jelentésen látható adatok szűrése

A **Szállító nyitott tranzakciói** jelentés létrehozásakor a következő alapértelmezett paraméterek állnak rendelkezésre. Ezekkel szűrheti a jelentésben lévő adatokat.

- **Jövőbeli kiegyenlítés kizárása** – jelölje be ezt a jelölőnégyzetet, ha ki szeretné zárni a tranzakciókat, amelyek azután a dátum után vannak kiegyenlítve, amely meg van adva a **Nyitott tranzakciók ekkor** mezőben.
- **Nyitott tranzakciók ekkor** – Adjon meg egy dátumot, hogy tartalmazza az adott napon nyitott tranzakciókat. Ha nem ad meg dátumot, akkor ez a mező a maximális dátumra lesz állítva. (A legkésőbbi dátum az a legkésőbbi dátum, amit a rendszer elfogad december 31-én, 2154.) Alapértelmezés szerint a jelentés következő futtatásakor ez a mező az utolsóként megadott dátum lesz.

A **Szerepeltetni kívánt rekord** mezővel tovább korlátozhatja a jelentésben szereplő tranzakcióadatokat.

## <a name="additional-resources"></a>További erőforrások

- [Szállítói számla irányelveinek beállítása](../accounts-receivable/tasks/set-up-vendor-invoice-policies.md)
- [Fő számlaadatok a Kintlevőségek rendszerben, szállítói számla használatával](tasks/key-invoice-data-ap-system-vendor-invoice.md)
- [Fő számlaadatok a kötelezettségekbe jóváhagyási napló használatával](tasks/key-invoice-data-into-ap-system-approval-journal.md)
- [A legfontosabb számlaadatok a kötelezettségkezelési rendszerbe számlagyűjtő használatával](tasks/key-invoice-data-into-ap-system-invoice-pool.md)
- [Szállítói számla rögzítése a számlanaplóban](tasks/record-vendor-invoice-invoice-journal.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
