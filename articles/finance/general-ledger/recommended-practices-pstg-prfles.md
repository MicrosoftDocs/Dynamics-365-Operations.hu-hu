---
title: Ajánlott eljárások a feladási profilokhoz
description: Ez a témakör a feladási profilok konfigurálásához ajánlott módszereket ismerteti.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, MainAccount, SysDatabaseLogSetup, CustGroup, VendGroup, InventItemGroup
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 097d1c6d1fbe64dadc69cdb275a0aef38922036d
ms.sourcegitcommit: 5bfd6511d710deb539b4030eb0e9c48d25513595
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/19/2022
ms.locfileid: "8014102"
---
# <a name="recommended-practices-for-posting-profiles"></a>Ajánlott eljárások a feladási profilokhoz

A feladási profiloknak a rendszeren belül való konfigurálása során számos ajánlott módszer áll rendelkezésre. Ez a témakör a különböző eseteket és a megfelelő ajánlott eljárásokat írja le.

## <a name="setting-the-do-not-allow-manual-entry-flag"></a>A Manuális bevitel engedélyezése jelző beállítása

A Fő számlák lapon be kell lennie jelölve a Manuális bevitel engedélyezése jelölőnégyzetnek minden olyan fő számlánál, amely **feladási** **profilhoz** használatos. Ez a beállítás megakadályozza, hogy a felhasználók manuálisan adják fel a naplóbejegyzéseket a fő számlára. Ennek megfelelően gondoskodik arról, hogy az a szám még mindig egyenlegben maradjon a főkönyvvel, és megkönnyíti az egyeztetési folyamatot.

Ha a rendszer által szabályozott és automatikusan feladott számlához helyesbítések szükségesek, a következő megközelítések közül lehet alkalmazni:

- Hozzon létre egy másodlagos fő számlát, ahol a helyesbítések feladhatóak. Ezután a pénzügyi jelentések összegző számlájának vagy sorának használatával csoportosítja és összegzi a számlákat.
- A megfelelő arelék eredeti tranzakcióinak sztornírozása, az esetleges szükséges helyesbítések, majd a tranzakció ugyanazon az arelikán keresztüli újraposta.

## <a name="changing-posting-profiles-after-transactions-exist"></a>Feladási profilok módosítása tranzakciók után

Ha a tranzakciók léteznek után módosítja a feladási profilt, az egyeztetés sikertelen lesz, és az a szám és a főkönyv egyenlege kieshet az egyenlegből. Általában azt ajánljuk, hogy ne módosítsa a feladási **profilt**, ha már léteznek tranzakciók.

Ha változtatások szükségesek, a következő irányelvek segítségével biztosíthatja a rendszer integritását:

- Az időszaki zárás során végrehajtott módosítások
- Akkor tegye a változtatásokat, ha nem történik másik tranzakció a rendszerben.
- A főkönyv ellenőrzése és egyeztetése az arelippel a módosítások előtt és után.
- A feladott tranzakciók nem frissülnek, ha módosítja a feladási profilt. Gondosan mérlegelje, hogy szükséges-e módosítási bejegyzés a változtatáshoz.
- Ha módosítja a készletfeladási profilokat, vegye figyelembe, hogy a módosítások milyen hatással lesznek az aktuális készletre és a főkönyvi egyenlegre. Bizonyos változtatásoknál előfordulhat, hogy a készletet nullára kell hozni, le kell zárni a készletet, majd a módosítást követően vissza kell hozni a készletet.
- A módosításokat mindig tesztelje nem termelési környezetben, mielőtt élesben módosítja azokat.

## <a name="using-database-logging-to-audit-changes-to-posting-profiles"></a>Az adatbázis-naplózás használata a feladási profilok változásainak könyvvizsgálatához

Fontolja meg az adatbázis naplózásának beállítását minden egyes feladási profilhoz és paramétertáblához, amely a feladást szabályozja. Ezután ha egy paramétert vagy profilt megváltoztatnak, akkor teljes ellenőrzési rekordja lesz arról, hogy mi volt az érték, ki módosította, mikor módosította, és mi volt az előző érték. Ez az információ az egyeztetési folyamat során kritikus lehet, és előfordulhat, hogy a könyvvizsgálónak szüksége van a támogató dokumentációra.

A további tudnivalókat lásd az adatbázis [naplózásának konfigurálása](../../fin-ops-core/dev-itpro/sysadmin/configure-manage-database-log.md).

A következő táblázat a feladási profilokkal és a kapcsolódó feladási paraméterekkel kapcsolatos gyakori táblanevekre hivatkozik.

| Lapnév | Navigációs útvonal | Tábla neve |
|-----------|-----------------|------------|
| Kötelezettségek paraméterei | Kötelezettségek beállítása &gt; – &gt; Kötelezettségek paraméterei | VendParm |
| Szállítói feladási profil | Kötelezettségek &gt; beállítási &gt; szállítói feladási profilja | VendPosting |
| Költségkód | Kötelezettségek – &gt; Költségek beállítása – Költségek kódja vagy &gt; Kinnlevőségek &gt; – Költségek &gt; beállítási költségkódja | MarkupTable |
| Fizetési módok | Kötelezettségek – &gt; Fizetésbeállítás &gt; fizetési módjai | VendPaymMode |
| Készpénzfizetési engedmények | Kötelezettségek – &gt; Fizetés beállítása &gt; Készpénzfizetési engedmények vagy Kinnlevőségek &gt; – Fizetés beállítása &gt; Készpénzfizetési engedmények | CashDisc |
| Kifizetési díj (szállító) | Kötelezettségek – &gt; Fizetés beállítása &gt; kifizetési díj | VendPaymFee |
| Kinnlevőségek paraméterei | Kinnlevőségek &gt; beállítása &gt; - Kinnlevőségek paraméterei | CustParm |
| Vevői feladási profilok | Kinnlevőségek &gt; beállítási &gt; vevői feladási profilja | CustPosting |
| Fizetési módok | &gt; Kinnlevőségek – Kifizetések &gt; beállítási módjai | CustPaymMode |
| Kifizetési díj (vevő) | &gt; Kinnlevőségek – Kifizetések beállítása &gt; – Fizetési módok | CustPaymFee |
| Eszközlízing paraméterei | Tárgyi eszköz &gt; értékcsökkenésének &gt; beállításához kapcsolódó paraméterek | AssetLeasePostingAccounts<br>AssetLeaseJournalParameters<br>AssetLeaseExecutoryCostPostingAccounts |
| Bankszámlák | Készpénz- és bankkezelés &gt; – &gt; Bankszámlák | BankAccountsTable |
| Banki tranzakciótípusok | Készpénz- és bankkezelés &gt; – Banki &gt; tranzakciók típusainak beállítása | BankTransType |
| Eltávolítási szabályok | Konszolidációk &gt; beállítási &gt; eltávolítási szabálya | LedgerEliminationRule<br>LedgerEliminationRuleLines |
| Költségkategóriák | Költséggazdálkodás – &gt; Általános &gt;&gt; költségkategóriák beállítása | ProjCategories |
| Tárgyi eszköz paraméterei | Tárgyi eszközök beállítása &gt;&gt; - Tárgyi eszközök paraméterei | AssetParameters |
| Tárgyieszköz-feladási profilok | Tárgyi eszközök beállítása &gt;&gt; - feladási profilok | AssetLedgerAccounts<br>AssetDisposalParameters |
| Devizaátértékelési számlák | Főkönyv &gt; szerinti pénznemek &gt; devizaátértékelési számlái | CurrencyLedgerGainLossAccount |
| Számlák automatikus tranzakciókhoz | Főkönyvi &gt; feladás beállítási &gt; számlái automatikus tranzakciókhoz | LedgerSystemAccounts |
| Vállalatközi könyvelés | Főkönyvi &gt; feladás beállítása &gt; vállalatközi számlák | LedgerIntercompany |
| Tranzakció-feladásdefiníciók | Főkönyvi &gt; feladás beállítása &gt; - tranzakció-feladásdefiníciók | JournalizingDefinitionTrans |
| Feladásdefiníciók | Főkönyvi &gt; feladás &gt; beállításának feladásdefiníciói | JournalizingDefintion |
| Feladás (készlet) | Készletkezelés – &gt; Beállítás – &gt; Feladás &gt; feladása | InventPosting |
| Költségtípus kódjai | Partrahozott költség &gt; költségszámításának beállítása &gt; - Költségtípuskódok | ITMCostTypeTable |
| Erőforrások | Gyártásvezérlés &gt; - Erőforrások beállítása &gt;&gt; | WrkCtrTable |
| Erőforráscsoportok | Gyártásvezérlés &gt; – &gt; Beállítási erőforrások &gt; erőforráscsoportok | WrkCtrResourceGroup |
| Termelési csoportok | Gyártásvezérlés &gt; – Beállítás – Termelés – &gt;&gt; Csoport | ProdGroup |
| Költségkategóriák | Gyártásvezérlés &gt; beállítási &gt;&gt; útvonalai – Költségkategóriák | ProjCategory |
| Projektcsoportok | Projektvezetés és könyvelés &gt; – Beállítás &gt; – &gt; Feladási projektcsoportok | ProjGroup |
| Főkönyvi feladás beállítása (projektek) | Projektvezetés és könyvelés &gt; – Beállítás &gt; – &gt; Feladási főkönyvi feladás beállítása | ProjPosting |
| Alapértelmezett ellenszámlák költségekhez | Projektvezetés és könyvelés &gt; – Beállítás – Alapértelmezett &gt;&gt; ellenszámlák a költségekhez | ProjDefaultOffsetSetup |
| Visszatérítéskezelés feladási profiljai | Visszatérítéskezelés &gt; - visszatérítéskezelés feladási beállításai &gt; visszatérítéskezelési feladási profilok | TAMRebatePosting |
| Főkönyvi feladási csoport (adó) | Adóbeállítás &gt; - &gt;&gt; főkönyvi áfa feladási csoportja | TaxAccountGroup |

## <a name="changing-groups-after-transactions-exist"></a>Csoportok módosítása tranzakciók megása után

Az alapadatok csoportjainak módosításakor körültekintően kell eljárni. Ha csoportokat használ a feladási profilok meghatározására, az alaprekordok csoportjainak bármely módosítása hátrányosan befolyásolja a főkönyv és az akkre vonatkozó egyeztetési képességet. Beállíthatja például a készletfeladási profilt az értékesítési rendelés bevételére, hogy minden cikkcsoporthoz egy másik bevételi számlát használ a rendszer. Ha a tranzakciók léteznek után módosítja a cikkhez rendelt cikkcsoportot, az új tranzakciók bevétele a frissített számlára lesz feladva. A módosítás előtt feladott bevételek azonban megmaradnak az eredeti számlán.

## <a name="testing-posting-profiles"></a>Feladási profilok tesztelése

Mielőtt élőben, illetve a feladási profilok vagy a kapcsolódó paraméterek módosítása vagy módosítása után minden esetet tesztelni kell. Legalább az egyes feladási típusokat tesztelni kell, hogy a feladás megfelelően működik-e. A javasolt azonban az egyes feladási profiltranzakciók és -kombinációk tesztelése.

Van például két vevői feladási profil, amelyek mindegyikében három, a vevőcsoportokra jellemző rekord van. Ebben az esetben minden tranzakciótípust tesztelni kell.

**Feladási profilok:**

- **GEN – az általános feladási profil, amelybe egy csoport tartozik az alkalmazottak, egy a vevők, és egy a** vállalatköziek számára. Mindegyik csoport egy másik Kinnlevőségek kereskedelmi számlára mutat.
- **PRE – az előleg feladási profilja, amely egy rekordot mutat minden olyan előleghez, amely a vevői előre fizetett** számlákra mutat.

### <a name="testing-scenarios"></a>Tesztelési esetek

- Szabadszöveges számla a GEN feladási profilt használó vevőhöz az **Alkalmazott** **csoportban**
- Szabadszöveges számla az Alkalmazott csoportban szereplő, előzetes **·** **feladási profilt** használó vevőhöz
- A GEN feladási profilt használó vevő **értékesítési** **rendelési számlája az Alkalmazott** csoportban
- Értékesítési rendelési számla egy olyan vevőhöz az Alkalmazott **csoportban**, amely a **feladás előtti** profilt használja
- A GEN feladási profilt használó, az Alkalmazott csoportban dolgozó vevő **vevői** kifizetési **naplója**
- A pre feladási profilt használó, az Alkalmazott csoportban dolgozó **vevő** **vevői kifizetési** naplója

Az előző példában ismételje meg a tesztelési esetet mindegyik vevőcsoportnál, majd ismételje meg a tesztelési esetek mindegyik csoportját minden további tranzakciótípusra (például projektszámlákra és szolgáltatáskezelésre).

## <a name="reconciling-the-ledger-to-the-subledger"></a>Főkönyv egyeztetése az arelékvel

A főkönyvet minden időszakban egyeztetni kell az a számkulált evővel. Számos modul olyan, a mezőn túli jelentéseket tartalmaz, amelyek az egyeztetésben segítenek. A helyi követelményektől függően azonban előfordulhat, hogy egyéni jelentéseket kell kialakítása vagy a meglévő jelentések kiterjesztése a jelentési követelményeknek megfelelően.

Javasoljuk, hogy az élő használat előtt zárást zárjon le, és egyezteti az egyes részalapokat a főkönyvvel. Javasoljuk továbbá, hogy a kezdeti ugrás előtt kiegyensúlyozottan eltolja az összes nyitott egyenleget és nyitott tranzakciót. Ennek a folyamatnak a részeként teljes egyeztetést kell futtatnia annak érdekében, hogy az egyenlegek és a nyitott tranzakciók egyenlege áttérjon az örökölt rendszerekkel, és hogy az új tranzakciók létrehozása előtt minden részalap egyenlege kiegyenlül a főkönyvvel.
