---
title: Egy bizonylat
description: A pénzügyi naplók (főkönyvi napló, tárgyieszköz-napló, szállítói kifizetési napló és így tovább) Egy bizonylat funkciójának használatával bevihető több analitikusnapló-tranzakció egyetlen bizonylat keretein belül.
author: kweekley
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerParameters, AssetProposalDepreciation
audience: Application User
ms.reviewer: kfend
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 8.0.2
ms.openlocfilehash: fa7a519b87bd5933b8b672f9f9b3e230fd7f2eb4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896405"
---
# <a name="one-voucher"></a>Egy bizonylat

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


## <a name="what-is-one-voucher"></a>Mi az az Egy bizonylat?

A pénzügyi naplók (főkönyvi napló, tárgyieszköz-napló, szállítói kifizetési napló és így tovább) meglévő funkcióinak használatával bevihető több analitikusnapló-tranzakció (vevő, szállító, tárgyi eszköz, projekt és bank) egyetlen bizonylat keretein belül. Erre a funkcióra a Microsoft az *Egy bizonylat* megnevezéssel hivatkozik. Egyetlen bizonylatot az alábbi módszerek egyikével hozhat létre:

- Állítsa be a napló nevét (**Főkönyv** \> **Naplóbeállítás** \> **Naplónevek**) úgy, hogy az **Új bizonylat** mező értéke **Csak egy bizonylatszám** legyen. Minden, a naplóhoz hozzáadott sor most ugyanarra a bizonylatra kerül. Ezért a bizonylat többsoros bizonylatként is megadható, mint számla/ellenszámla ugyanazon a soron, vagy kombinációként.

    [![Egy sor.](./media/same-line.png)](./media/same-line.png)

    > [!IMPORTANT]
    > Az Egy bizonylat meghatározása **nem** tartalmazza azokat az eseteket, ahol a naplóneveket a **Csak egy bizonylatszám** beállítással hozták létre, de a felhasználó olyan bizonylatot ad meg, amely csak főkönyvi számla típusúakat tartalmaz. Ebben a cikkben az Egyik bizonylat azt jelenti, hogy egy bizonylat több szállítót, vevőt, bankot, tárgyi eszközt vagy projektet tartalmaz.

- Adjon meg egy többsoros bizonylatot, ha nincs ellenszámla.

    [![Többsoros bizonylat.](./media/Multi-line.png)](./media/Multi-line.png)

- Adjon meg egy bizonylatot, ahol a számla és az ellenszámla is analitikus számlatípust tartalmaz – például **Szállító**/**Szállító**, **Vevő**/**Vevő**, **Szállító**/**Vevő** vagy **Bank**/**Bank**.

    [![Analitikus bizonylat.](./media/subledger.png)](./media/subledger.png)

## <a name="issues-with-one-voucher"></a>Problémák az Egy bizonylat funkcióval

Az Egy bizonylat funkció problémákat okoz a kiegyenlítés, az adószámítás, a tranzakciók sztornírozása, egy analitikus napló egyeztetése a főkönyvvel, a pénzügyi beszámolók és egyebek egyeztetése során. (A kiegyenlítés során felmerülő problémákkal kapcsolatos további információkért tekintse át például az [Egyetlen bizonylat több vevői vagy szállítói rekorddal](../accounts-payable/single-voucher-multiple-customer-vendor-records.md) részt.) A helyes munkavégzés és jelentéskészítés érdekében ezekhez a folyamatokhoz és jelentésekhez szükségesek a tranzakciók részletei. Bár egyes forgatókönyvek még mindig jól működhetnek a szervezete beállításaitól függően, gyakoriak a problémák, ha több tranzakció kerül egy bizonylatra.

Például feladhatja az alábbi többsoros bizonylatot.

[![Példa többsoros bizonylatra.](./media/example.png)](./media/example.png)

Ekkor létrehozza a **Szállítónkénti költségek** jelentést a **Pénzügyi információk** munkaterületen. Ezen a jelentésen a rendszer szállítócsoport, majd szállító szerint csoportosítja a költségszámla-egyenlegeket. A jelentés létrehozásakor a rendszer nem tudja megállapítani, melyik szállítói csoportok/szállítók esetében merült fel a 250,00 költség. Mivel a tranzakció részletei hiányoznak, a rendszer azt feltételezi, hogy a 250,00 összérték a bizonylaton található első szállítónál merült fel. Így a 250,00 költség, amely a 600120 fő számla egyenlegében szerepel, ekkor megjelenik a szállítói csoport vagy szállító alatt. Ugyanakkor nagyon valószínű, hogy a bizonylaton szereplő első szállító nem a megfelelő szállító volt. A jelentés ezért valószínűleg nem megfelelő.

[![Szállítónkénti költségek jelentésben.](./media/expenses.png)](./media/expenses.png)

## <a name="the-future-of-one-voucher"></a>Az Egy bizonylat jövője

Az Egy bizonylat használata esetén előforduló problémák miatt ez a funkció végül elavulttá válik. Mivel azonban vannak ezen a funkción alapuló működési rések, a funkció elavulása nem egyszerre fog megtörténni. Ehelyett a következő ütemezést használja a rendszer:

- **2018 tavaszi kiadás** – Ez a funkció alapértelmezés szerint ki lesz kapcsolva a **Több tranzakció engedélyezése egy bizonylat esetén** paraméteren keresztül a **Főkönyvi paraméterek** oldal **Általános** lapján. Bekapcsolhatja azonban akkor is, ha a szervezetnél olyan helyzet van, amely a cikk későbbi felsorolásában szereplő működési hiányok valamelyikére esik.

    - Ha az üzleti helyzethez nem szükséges Egy bizonylat, akkor javasoljuk, hogy hagyja kikapcsolva a funkciót. Ha annak ellenére használja, hogy létezik másik megoldás, a Microsoft nem fogja kijavítani a "javítást" a cikk későbbi, meghatározott területein.
    - Javasoljuk, hogy ne használja az Egy bizonylatot integrációkhoz, kivéve, ha a funkció a dokumentált működési rések egyikéhez szükséges.

- **Későbbi kiadások** – számos üzleti követelmény csak az Egy bizonylat segítségével teljesíthető. A Microsoftnak gondoskodnia kell arról, hogy a funkció értékcsökkenése után is teljesülni tudjanak a rendszerben az azonosított üzleti követelmények. Ennek megfelelően a működési hiányok kitöltéséhez valószínűleg új funkciókat kell hozzáadni. A Microsoft nem tud konkrét megoldást kínálni, mivel minden működési hiány más, és az üzleti követelmények alapján kell felmérni őket. Bizonyos működési hiányokat valószínűleg olyan funkciók írnak felül, amelyek megfelelnek az egyes üzleti követelményeknek. Előfordulhat azonban, hogy más hiányokat úgy lehet kitölteni, hogy lehetővé teszik a naplóban való bevitelt, mint amikor az Egy bizonylat funkciót használják, de javítani kell a rendszeren, hogy szükség szerint nyomon kövesse a részletesebb adatokat.

Miután minden működési hiányt kitöltött, a Microsoft közli, hogy a funkció elavulttá válik. Az értékcsökkenés azonban a tájékoztatás után legalább egy évig nem lép hatályba. Bár a Microsoft nem tud becslést adni arról, hogy mikorra válik elavulttá az Egy bizonylat funkció, az értékcsökkenés valószínűleg legalább két év múlva következik be. A Microsoft irányelve az, hogy legalább 12 hónapot hagyjon az elavult funkció bejelentése és a tényleges értékcsökkenés között, hogy a vevőknek és független szoftverszállítóknak és független szoftverszállítóknak elegendő idejük legyen arra, hogy a módosításra reagáljanak. Például előfordulhat, hogy egy szervezetnek frissítenie kell az üzleti folyamatait, entitásait és integrációit.

Az Egy bizonylat értékcsökkenése jelentős változás, amelyről széles körben folyik majd tájékoztatás. A kommunikáció részeként a Microsoft frissíti ezt a cikket, felad egy postát a Microsoft Dynamics 365 Pénzügyi évhez, frissíti az "Eltávolított vagy elavult funkciók" cikket, a változtatást a Microsoft megfelelő értekezletén stb.

## <a name="why-use-one-voucher"></a>Miért használjon egy bizonylatot?

Vevőkkel folytatott beszélgetések alapján a Microsoft összeállította az alábbi forgatókönyvek listáját, ahol a vevők az Egy bizonylat funkciót használják, illetve a használatának okait adják meg. Egyes üzleti követelmények csak az egy bizonylat segítségével teljesíthetők. Sok esetben azonban alternatívák is megfelelhetnek ugyanazon üzleti követelményeknek.

### <a name="scenarios-that-require-one-voucher"></a>Egy bizonylatot igénylő esetek

A következő forgatókönyvek csak az Egy bizonylat funkció használatával végezhetők el. Amennyiben a szervezeténél ezen forgatókönyvek bármelyike előfordul, engedélyeznie kell azt, hogy egy bizonylatra több tranzakciót is megadjanak az **Általános főkönyvi paraméterek** oldalon a **Több tranzakció engedélyezése egy bizonylaton** paraméter beállításának módosítása révén. Ezeket a működési réseket más szolgáltatások fogják betölteni a későbbi verziókban.

> [!NOTE]
> [A következő esetek mindegyikében a **Főkönyv paraméterei** lap **Általános** gyorslapján a **Több tranzakció engedélyezése egy bizonylaton belül** mezőt Igen értékre kell tenni.]

### <a name="post-vendor-or-customer-payments-in-summary-form-to-a-bank-account"></a>Szállítói vagy vevői kifizetések feladása a bankszámlára összegző formában

**Forgatókönyv** Egy szervezet egy szállítókból és összegekből álló listát közöl a bankjával, és a bank ezt a listát használja a szervezet nevében a szállítók fizetésére. A bank a kifizetések összesített összegét egyetlen kivétkén könyveli el a bankszámlán.

A szállítói kifizetések összefoglalása csak az Egy bizonylaton keresztül támogatott. Minden szállító külön sorként kerül bevitelre, hogy a Kötelezettségek analitikus naplóban minden részlet szerepeljen. Azonban a kifizetések összesített összege egyetlen sorrá tolódik el a banszámlára. Emiatt a visszavonás a banki analitikus naplóban egyetlen összesített összegként jelenik meg.

**Forgatókönyv** Egy szervezet vevői kifizetéseket helyez letétbe, vagy a bank helyez letétbe vevői kifizetéseket a szervezet nevében, és a letét egy összegként szerepel a bankszámlán.

Vevői kifizetések összefoglalását általában a jóváírás funkció támogatja. Azonban ha „áthidalást” használ a fizetési módnál, ezt az esetet csak az Egy bizonylat funkció támogatja. A vevői kifizetések bevitele a szállítóikifizetés-összefoglalóban ismertetett módhoz hasonlóan történik.

### <a name="mechanism-to-group-transactions-from-a-business-event"></a>Mechanizmus tranzakciók csoportosítására egy üzleti eseményből

**Forgatókönyv** Egy szervezetnél egyetlen üzleti esemény történik, amely több tranzakciót vált ki. Azonban a számviteli osztály a könyvvizsgálati tételeket együtt szeretné látni a jobb auditálhatóság érdekében.

Ha egy szervezetnek egyben kell áttekitenie az egy üzleti eseményhez tartozó könyvelési tételek, használja az Egy bizonylat funkciót. 

### <a name="country-specific-features"></a>Ország-/régiófüggő funkciók

**Forgatókönyv** Az egységes vámokmány (EV) funkció Lengyelország esetében jelenleg egyetlen bizonylat használatát igényli. Amíg a funkcióhoz nem érhető el csoportosítási beállítás, továbbra is az Egy bizonylat funkciót kell használni. Előfordulhat, hogy vannak további, a Egy bizonylat funkciót igénylő országspecifikus funkciók.

### <a name="customer-prepayment-payment-journal-that-has-taxes-on-multiple-lines"></a>Vevői előlegkifizetési napló, amelynél több „soron” találhatók adók

Ebben az esetben az egyetlen bizonylaton szereplő vevők ugyanaz a vevő, mert a tranzakció a vevői rendelés sorait szimulálja. Az előleget egy bizonylaton kell bevinni, mert az adószámítást egy vevői kifizetés „sorain” kell végrehajtani.

### <a name="customer-reimbursement"></a>Vevői visszatérítés

**Forgatókönyv** Egy vevő előre fizet egy rendelésért, és a rendelés sorai különböző adókat tartalmaznak, amelyeket rögzíteni kell az előlegfizetéshez. Az előleg vevői kifizetés egy tranzakció, amely szimulálja a rendelés sorait, hogy a megfelelő adó rögzíthető legyen az összeghez, soronként.

Ha a Visszatérítés időszaki feladat futtatása a Kinnlevőségek modulból történik, ez létrehoz egy tranzakciót, amelynek segítségével az egyenleg a vevőtől a szállítóhoz mozgatható. Ebben az esetben Egy bizonylatot kell használni a vevő visszatérítéséhez.

### <a name="fixed-asset-maintenance-catch-up-depreciation-split-asset-calculate-depreciation-on-disposal"></a>Tárgyi eszközök karbantartása: felzárkózó értékcsökkenés, felosztott eszköz, értékcsökkenés kiszámítása kivezetéskor
A 10.0.21-es és későbbi verziókkal a tárgyi eszközökre vonatkozó tranzakciók a felzárkóztató értékcsökkenés, az eszköz felosztása és az eszköz elidegenítéséhez szükséges értékcsökkenés kiszámítása különböző utalványszámok használatával jön létre.

### <a name="bills-of-exchange-and-promissory-notes"></a>Váltók és kötelezvények
Váltók és kötelezvények esetén szükséges az Egy bizonylat használata, mivel a tranzakciók a vevő vagy szállító egyenlegét egyik Kinnlevőségek/Kötelezettségek főkönyviszámláról egy másikra mozgatja át, a kifizetés állapotától függően.

## <a name="scenarios-that-dont-require-one-voucher"></a>Egy bizonylatot nem igénylő esetek

A következő forgatókönyvek más módszerekkel és megvalósíthatók, és nem szabad az Egy bizonylat funkciót használni.

### <a name="post-customer-payments-in-summary-form-to-the-bank-account"></a>Vevői kifizetések feladása a bankszámlára összegző formában

Egy szervezet betétek vevői kifizetéseket fizet be, vagy a bank helyez el vevői kifizetéseket a szervezet nevében, és a befizetés átalányösszegként szerepel a bankszámlán.

A vevői kifizetések összefoglalását a jóváírás funkció támogatja, ha az „áthidalást” nem használják a fizetési módnál.

### <a name="netting"></a>Nettóérték-számítás

Nettóérték-számításnál a szállító és a vevő egyenlegét egymás ellen számítjuk be, mivel a szállító és a vevő ugyanaz a fél. Ezzel a módszerrel minimálisra csökkenthető a szervezet és a vevő vagy szállító fél közötti pénzcsere.

Nettóérték-számítás végezhető úgy, hogy a növekedést és a csökkenést külön bizonylatokon visszük be, a különbözetet pedig feladjuk egy elszámoló főkönyvi számlára.

### <a name="post-in-summary-to-the-general-ledger"></a>Összegző feladás a főkönyvbe

A szervezetek gyakran szeretnék az adatokat összegzett formában feladni a főkönyvbe, hogy minimalizálják az adatok mennyiségét. Azonban ezek a szervezetek jellemzően továbbra is előírják a tranzakció részleteinek megőrzését. Ha a feladás összegzett formában történik egyetlen bizonylaton keresztül, a tranzakció részletei nem ismertek, és nem lehet karbantartani őket.

- Mivel a tranzakciós részleteket jelenleg nem lehet karbantartani, azt javasoljuk, hogy a szervezet az Egy bizonylat funkciót **ne** használja összegzett formában való feladáshoz.
- Az Egy bizonylat funkció támogatásának megszűnése után a Forrásbizonylat és a Könyvelési keretrendszerek a naplókban valósíthatók meg. Ezek a keretrendszerek ezt követően karbantartják a tranzakció adatait, és támogatják az összefoglaló beküldését a főkönyvbe.


### <a name="settle-multiple-unposted-payments-to-the-same-invoice"></a>Több feladatlan kifizetés kiegyenlítése ugyanazon a számlán

Ez a forgatókönyv általában a szervezetekre jellemző, ahol a felhasználók többféle fizetési módot használhatnak a vásárlások kifizetésére. Ilyen esetben a szervezetnek több feladatlan kifizetést kell rögzítenie és rendeznie a vevői számla alapján.

A Microsoft Dynamics 365 for Operations 1611-es verziójához (2016. november) hozzáadott új funkció lehetővé teszi, hogy több fel nem adott kifizetést egyetlen számlával szemben rendezzen. Több vevői kifizetést már nem kell egyetlen bizonylaton megadni.

### <a name="import-bank-statement-transactions"></a>Banki kivonatban szereplő tranzakciók importálása

A bankok gyakran fizetnek és kapnak kifizetéseket egy szervezet nevében, és azokat a tranzakciókat a Finance-ben a banktól kapott fájlon keresztül rögzíti. A szervezetek gyakran szeretnék összevonni ezeket a tranzakciókat a banki kivonat számával a fájlban. Mivel az egyes tranzakciók részletesen szerepelnek a banki kivonaton, a banki naplóban nem szükséges összegzés.

A tranzakciókat a napló egyéb mezőinek segítségével lehet csoportosítani, például a napló kötegszáma vagy a dokumentumszám alapján.


### <a name="transfer-balances"></a>Egyenlegek átvitele

Egy szervezetnek egy szállító egyenlegének átvitelére lehet szüksége egy másik szállítóhoz vagy hiba miatt, vagy mert egy másik szállító átvette a kötelezettséget. Ilyen típusú átutalások olyan számlatípusok esetében is előfordulnak, mint a **Vevő** és **Bank**.

Egyenlegátvitelek egyik számláról (szállítói, vevői, bankszámla stb.) másik számlára külön bizonylatok révén kivitelezhető, és az ellenszámla elszámolási főkönyvi számlára adható fel.

### <a name="enter-beginning-balances"></a>Nyitóegyenlegek megadása

A szervezetek gyakran egy bizonylatos tranzakcióként adják meg az alszámlák (szállítók, vevők, tárgyi eszközök stb.) nyitóegyenlegét. Az egyes analitikus számlák nyitó egyenlegei külön bizonylatokként adhatók meg, az ellenszámla pedig elszámoló főkönyvi számla lehet.

### <a name="correct-the-accounting-entry-of-a-posted-customer-or-vendor-document"></a>Feladott vevői vagy szállítói dokumentum könyvelési bejegyzésének kijavítása

Egy szervezetnek a Kinnlevőségek vagy Kötelezettségek főkönyvi számla korrekciójára lehet szüksége egy könyvelt számla számlabejegyzéshez, de a számlát nem lehet sztornírozni vagy javítani másik mechanizmus révén.

Ha korrigálni kell a Kinnlevőségek vagy a Kötelezettségek főkönyvi számlát, a kiigazítást közvetlenül a főkönyvi számlán kell elvégezni. A korrekció nem adható fel a vevőn vagy a szállítón keresztül. Ez a módszer azt igényli, hogy a korrekció „állásidő” alatt történjen meg, hogy a főkönyvi számla ideiglenesen engedélyezhesse a manuális bevitelt.

### <a name="the-system-allows-it"></a>„A rendszer lehetővé teszi”

A szervezetek gyakran csak azért használják az Egy bizonylat funkciót,mert a rendszer lehetővé teszi számukra, és nem gondolnak bele a következményekbe.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
