---
title: Ajánlott eljárások a feladási profilokhoz
description: Ez a témakör a feladási profilok konfigurálásához ajánlott eljárásokat ismerteti.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, MainAccount, SysDatabaseLogSetup, CustGroup, VendGroup, InventItemGroup
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb0e321f447b78b88c065e52bb7fad1c445e47b6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849902"
---
# <a name="recommended-practices-for-posting-profiles"></a>Ajánlott eljárások a feladási profilokhoz

A feladási profiloknak a rendszeren belül való konfigurálása során számos ajánlott módszer áll rendelkezésre. Ez a témakör a különböző helyzetekről és a megfelelő ajánlott eljárásokról ad le.

## <a name="setting-the-do-not-allow-manual-entry-flag"></a>A Manuális bevitel engedélyezése jelző beállítása

A Fő **számlák** lapon be kell lennie jelölve a Manuális bevitel engedélyezése jelölőnégyzetnek minden olyan fő számlánál, **amely** feladási profilhoz használatos. Ez a beállítás megakadályozza, hogy a felhasználók manuálisan adják fel a naplóbejegyzéseket a fő számlára. Ennek megfelelően gondoskodik arról, hogy az a szám még mindig egyenlegben maradjon a főkönyvvel, és megkönnyíti az egyeztetési folyamatot.

Ha a rendszer által szabályozott és automatikusan feladott számlához helyesbítések szükségesek, a következő megközelítések közül lehet alkalmazni:

- Hozzon létre egy másodlagos fő számlát, ahol a helyesbítések feladhatóak. Ezután a pénzügyi jelentések összegző számlájának vagy sorának használatával csoportosítja és összegzi a számlákat.
- A megfelelő arelék eredeti tranzakcióinak sztornírozása, az esetleges szükséges helyesbítések, majd a tranzakció ugyanazon az arelikán keresztüli újraposta.

## <a name="changing-posting-profiles-after-transactions-exist"></a>Feladási profilok módosítása tranzakciók után

Ha a tranzakciók léteznek után módosítja a feladási profilt, az egyeztetés sikertelen lesz, és az a szám és a főkönyv egyenlege kieshet az egyenlegből. Általában azt ajánljuk, hogy ne **módosítsa** a feladási profilt, ha már léteznek tranzakciók.

Ha változtatások szükségesek, a következő irányelvek segítségével biztosíthatja a rendszer integritását:

- Az időszaki zárás során végrehajtott módosítások
- Akkor tegye a változtatásokat, ha nem történik másik tranzakció a rendszerben.
- A főkönyv ellenőrzése és egyeztetése az arelippel a módosítások előtt és után.
- A feladott tranzakciók nem frissülnek, ha módosítja a feladási profilt. Gondosan mérlegelje, hogy szükséges-e módosítási bejegyzés a változtatáshoz.
- Ha módosítja a készletfeladási profilokat, vegye figyelembe, hogy a módosítások milyen hatással lesznek az aktuális készletre és a főkönyvi egyenlegre. Bizonyos változtatásoknál előfordulhat, hogy a készletet nullára kell hozni, le kell zárni a készletet, majd a módosítást követően vissza kell hozni a készletet.
- A módosításokat mindig tesztelje nem termelési környezetben, mielőtt élesben módosítja azokat.

## <a name="using-database-logging-to-audit-changes-to-posting-profiles"></a>Az adatbázis-naplózás használata a feladási profilok változásainak könyvvizsgálatához

Fontolja meg az adatbázis naplózásának beállítását minden egyes feladási profilhoz és paramétertáblához, amely a feladást szabályozja. Ezután ha egy paramétert vagy profilt megváltoztatnak, akkor teljes ellenőrzési rekordja lesz arról, hogy mi volt az érték, ki módosította, mikor módosította, és mi volt az előző érték. Ez az információ az egyeztetési folyamat során kritikus lehet, és előfordulhat, hogy a könyvvizsgálónak szüksége van a támogató dokumentációra.

A további tudnivalókat lásd az adatbázis naplózásának [konfigurálása](../../fin-ops-core/dev-itpro/sysadmin/configure-manage-database-log.md).

A következő táblázat a feladási profilokkal és a kapcsolódó feladási paraméterekkel kapcsolatos gyakori táblanevekre hivatkozik.

| Oldalnév | Navigációs útvonal | Tábla neve |
|-----------|-----------------|------------|
| Kötelezettségek paraméterei | Kötelezettségek beállítása &gt; – &gt; Kötelezettségek paraméterei | VendParm |
| Szállítói feladási profil | Kötelezettségek beállítási &gt; szállítói &gt; feladási profilja | VendPosting |
| Költségkód | Kötelezettségek – Költségek &gt; beállítása – &gt; Költségek kódja vagy Kinnlevőségek – &gt; Költségek beállítási költségkódja &gt; | MarkupTable |
| Fizetési módok | Kötelezettségek – &gt; Fizetésbeállítás fizetési &gt; módjai | VendPaymMode |
| Készpénzfizetési engedmények | Kötelezettségek – &gt; Fizetés beállítása Készpénzfizetési &gt; engedmények vagy Kinnlevőségek &gt; – Fizetés beállítása Készpénzfizetési &gt; engedmények | CashDisc |
| Kifizetési díj (szállító) | Kötelezettségek – &gt; Fizetés beállítása kifizetési &gt; díj | VendPaymFee |
| Kinnlevőségek paraméterei | Kinnlevőségek beállítása &gt; - &gt; Kinnlevőségek paraméterei | CustParm |
| Vevői feladási profilok | Kinnlevőségek beállítási &gt; vevői &gt; feladási profilja | CustPosting |
| Fizetési módok | Kinnlevőségek &gt; – Kifizetések beállítási &gt; módjai | CustPaymMode |
| Kifizetési díj (vevő) | Kinnlevőségek &gt; – Kifizetések beállítása – &gt; Fizetési módok | CustPaymFee |
| Eszközlízing paraméterei | Tárgyi eszköz értékcsökkenésének &gt; beállításához &gt; kapcsolódó paraméterek | AssetLeasePostingAccounts<br>AssetLeaseJournalParameters<br>AssetLeaseExecutoryCostPostingAccounts |
| Bankszámlák | Készpénz- és bankkezelés &gt; – Bankszámlák &gt; | BankAccountsTable |
| Banki tranzakciótípusok | Készpénz- és bankkezelés &gt; – Banki &gt; tranzakciók típusainak beállítása | BankTransType |
| Eltávolítási szabályok | Konszolidációk beállítási &gt; eltávolítási &gt; szabálya | LedgerEliminationRule<br>LedgerEliminationRuleLines |
| Költségkategóriák | Költséggazdálkodás – &gt; Általános &gt; költségkategóriák &gt; beállítása | ProjCategories |
| Tárgyi eszköz paraméterei | Tárgyi eszközök beállítása &gt; - &gt; Tárgyi eszközök paraméterei | AssetParameters |
| Tárgyieszköz-feladási profilok | Tárgyi eszközök beállítása &gt; - feladási &gt; profilok | AssetLedgerAccounts<br>AssetDisposalParameters |
| Devizaátértékelési számlák | Főkönyv szerinti &gt; pénznemek devizaátértékelési &gt; számlái | CurrencyLedgerGainLossAccount |
| Számlák automatikus tranzakciókhoz | Főkönyvi feladás &gt; beállítási számlái &gt; automatikus tranzakciókhoz | LedgerSystemAccounts |
| Vállalatközi könyvelés | Főkönyvi feladás &gt; beállítása vállalatközi &gt; számlák | LedgerIntercompany |
| Tranzakció-feladásdefiníciók | Főkönyvi feladás &gt; beállítása - &gt; tranzakció-feladásdefiníciók | JournalizingDefinitionTrans |
| Feladásdefiníciók | Főkönyvi feladás &gt; beállításának &gt; feladásdefiníciói | JournalizingDefintion |
| Feladás (készlet) | Készletkezelés – &gt; Beállítás – &gt; Feladás feladása &gt; | InventPosting |
| Költségtípus kódjai | Partrahozott költség &gt; költségszámításának beállítása - &gt; Költségtípuskódok | ITMCostTypeTable |
| Erőforrások | Gyártásvezérlés - &gt; Erőforrások beállítása &gt;&gt; | WrkCtrTable |
| Erőforráscsoportok | Gyártásvezérlés – &gt; Beállítási &gt; erőforrások erőforráscsoportok &gt; | WrkCtrResourceGroup |
| Termelési csoportok | Gyártásvezérlés – &gt; Beállítás &gt; – Termelés &gt; – Csoport | ProdGroup |
| Költségkategóriák | Gyártásvezérlés beállítási &gt;&gt; útvonalai &gt; – Költségkategóriák | ProjCategory |
| Projektcsoportok | Projektvezetés és könyvelés &gt; – Beállítás – &gt; Feladási projektcsoportok &gt; | ProjGroup |
| Főkönyvi feladás beállítása (projektek) | Projektvezetés és könyvelés &gt; – Beállítás – Feladási &gt;&gt; főkönyvi feladás beállítása | ProjPosting |
| Alapértelmezett ellenszámlák költségekhez | Projektvezetés és könyvelés &gt; – Beállítás – Alapértelmezett &gt;&gt; ellenszámlák a költségekhez | ProjDefaultOffsetSetup |
| Visszatérítés-kezelés feladási profilok | Visszatérítéskezelés - &gt; visszatérítéskezelés feladási beállításai visszatérítéskezelési &gt; feladási profilok | TAMRebatePosting |
| Főkönyvi feladási csoport (adó) | Adóbeállítás &gt; - &gt; főkönyvi &gt; áfa feladási csoportja | TaxAccountGroup |

## <a name="changing-groups-after-transactions-exist"></a>Csoportok módosítása tranzakciók megása után

Az alapadatok csoportjainak módosításakor körültekintően kell eljárni. Ha csoportokat használ a feladási profilok meghatározására, az alaprekordok csoportjainak bármely módosítása hátrányosan befolyásolja a főkönyv és az akkre vonatkozó egyeztetési képességet. Beállíthatja például a készletfeladási profilt az értékesítési rendelés bevételére, hogy minden cikkcsoporthoz egy másik bevételi számlát használ a rendszer. Ha a tranzakciók léteznek után módosítja a cikkhez rendelt cikkcsoportot, az új tranzakciók bevétele a frissített számlára lesz feladva. A módosítás előtt feladott bevételek azonban megmaradnak az eredeti számlán.

## <a name="testing-posting-profiles"></a>Feladási profilok tesztelése

Mielőtt élőben, illetve a feladási profilok vagy a kapcsolódó paraméterek módosítása vagy módosítása után minden esetet tesztelni kell. Legalább az egyes feladási típusokat tesztelni kell, hogy a feladás megfelelően működik-e. A javasolt azonban az egyes feladási profiltranzakciók és -kombinációk tesztelése.

Van például két vevői feladási profil, amelyek mindegyikében három, a vevőcsoportokra jellemző rekord van. Ebben az esetben minden tranzakciótípust tesztelni kell.

**Feladási profilok:**

- **GEN** – az általános feladási profil, amelybe egy csoport tartozik az alkalmazottak, egy a vevők, és egy a vállalatköziek számára. Mindegyik csoport egy másik Kinnlevőségek kereskedelmi számlára mutat.
- **PRE** – az előleg feladási profilja, amely egy rekordot mutat minden olyan előleghez, amely a vevői előre fizetett számlákra mutat.

### <a name="testing-scenarios"></a>Tesztelési esetek

- Szabadszöveges számla **a** **GEN** feladási profilt használó vevőhöz az Alkalmazott csoportban
- Szabadszöveges számla az Alkalmazott csoportban **szereplő** **, előzetes feladási profilt** használó vevőhöz
- A GEN feladási **profilt** **használó vevő értékesítési** rendelési számlája az Alkalmazott csoportban
- Értékesítési rendelési számla egy olyan vevőhöz az Alkalmazott **csoportban**, amely a **feladás előtti profilt** használja
- A GEN feladási profilt **használó**, az Alkalmazott csoportban dolgozó vevő vevői **kifizetési** naplója
- A pre feladási profilt **használó**, az Alkalmazott csoportban dolgozó vevő vevői kifizetési **naplója**

Az előző példában ismételje meg a tesztelési esetet mindegyik vevőcsoportnál, majd ismételje meg a tesztelési esetek mindegyik csoportját minden további tranzakciótípusra (például projektszámlákra és szolgáltatáskezelésre).

## <a name="reconciling-the-ledger-to-the-subledger"></a>Főkönyv egyeztetése az arelékvel

A főkönyvet minden időszakban egyeztetni kell az a számkulált evővel. Számos modul olyan, a mezőn túli jelentéseket tartalmaz, amelyek az egyeztetésben segítenek. A helyi követelményektől függően azonban előfordulhat, hogy egyéni jelentéseket kell kialakítása vagy a meglévő jelentések kiterjesztése a jelentési követelményeknek megfelelően.

Javasoljuk, hogy az élő használat előtt zárást zárjon le, és egyezteti az egyes részalapokat a főkönyvvel. Javasoljuk továbbá, hogy a kezdeti ugrás előtt kiegyensúlyozottan eltolja az összes nyitott egyenleget és nyitott tranzakciót. Ennek a folyamatnak a részeként teljes egyeztetést kell futtatnia annak érdekében, hogy az egyenlegek és a nyitott tranzakciók egyenlege áttérjon az örökölt rendszerekkel, és hogy az új tranzakciók létrehozása előtt minden részalap egyenlege kiegyenlül a főkönyvvel.
