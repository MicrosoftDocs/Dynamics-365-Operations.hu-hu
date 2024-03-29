---
title: Főkönyvi napló típusai
description: Ez a cikk bemutatja, milyen naplótípusokat állíthat be a pénzügyi naplókhoz.
author: kweekley
ms.date: 10/10/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup
audience: Application User
ms.reviewer: kfend
ms.custom: 15631
ms.assetid: 81613b31-bc3c-43a0-8474-e01c9a482c40
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 883c54b84ed31384a28c31c8b814c75d340d020e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901313"
---
# <a name="ledger-journal-types"></a>Főkönyvi napló típusai

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, milyen naplótípusokat állíthat be a pénzügyi naplókhoz. A Naplónevek **lapon** beállíthatja a Dynamics 365 Pénzügyben használható naplókat.

| Naplótípus                      | Alkalmazás célja                       | Adja meg a tranzakciókat ezen az oldalon                                |
|-----------------------------------|-------------------------------|----------------------------------------------------------------|
| Foglalás                        | Felosztási tranzakciók létrehozása felosztási naplóban. Mielőtt létrehozhatna egy felosztási naplót, létre kell hoznia egy felosztási szabályt a **Felosztási napló szabályi** oldalon.      | Felosztási kérés feldolgozása             |
| Jóváhagyás                          | Jóváhagyott szállítói számlák feladása a megfelelő főkönyvi számlákra.  | Számla-jóváhagyási napló                                       |
| Banki csekk sztornírozása               | Feladott csekk sztornója. A naplótípus használatához válassza ki az **Ellenőrzési folyamat alkalmazása a kifizetések sztornírozásakor** lehetőséget a **Készpénz- és bankkezelési paraméterek** oldalon.   | Csekksztornírozások, kifizetés sztornírozása                   |
| Banki letéti jegy érvénytelenítése    | Letéti jegy visszavonása. A naplótípus használatához válassza ki az **Ellenőrzési folyamat a letéti jegyek kifizetésének sztornírozásakor** lehetőséget a **Készpénz- és bankkezelési paraméterek** oldalon.   | Letétijegy-kifizetések visszavonása            |
| Költségvetés                            | Költségvetési előirányzatok feldolgozása. A naplótípus használatához válassza ki a **Költségvetési előirányzat engedélyezése** lehetőséget a **Főkönyvi paraméterek** oldalon. A költségvetési naplóbejegyzések azon főkönyvi számlákon alapuló információkat tartalmazzák, amelyek a **Feladásdefiníciók** oldalon lettek meghatározva.                                                        |                                                                |
| Vevő - váltó elfogadása  | Vevői elfogadási tranzakciók létrehozása váltóknál.             | Váltónapló kiállítása, Váltónapló újbóli kiállítása |
| Vevő - banki utalás          | Szervezete bankjának átküldhető váltóátutalási fájl létrehozása. A naplótípus használatához törölje az **Automatikus kiegyenlítés** lehetőséget a **Kinnlevőségek** **paraméterei** oldalon.            | Átutalás                                                     |
| Vevő - váltó kiállítása    | Vevői váltókiállítási tranzakciók létrehozása. A naplótípus használatához törölje a **Kötelezvénykiállítási napló automatikus létrehozása és feladása számlák feladásakor** lehetőséget a **Fizetési módok – vevők** oldalon.   | Váltónapló kiállítása                                  |
| Vevői kifizetés                  | Vevői kifizetési tranzakciók létrehozása.                             | Fizetési napló             |
| Vevő - váltó óvatolása | Vevői óvatolt váltótranzakciók létrehozása.                    | Váltónapló elutasítása                               |
| Vevő - váltó visszavonása  | Vevői váltó újrakiállítási tranzakciók létrehozása.                     | Váltónapló újbóli kiállítása                                |
| Vevő - váltó kiegyenlítése  | Vevők váltókiegyenlítési tranzakciók létrehozása.                       | Váltó kiegyenlítésének naplója                                |
| Napi                             | Napi tranzakciók létrehozása a főkönyvi naplóban.                          | Általános napló                                                |
| Eltávolítás                       | Eltávolítási tranzakciók létrehozása eltávolítási naplóban. A naplótípus használatához válassza ki a **Pénzügyi eltávolítási folyamatokhoz** és a **Pénzügyi konszolidálási folyamatokhoz** lehetőséget a **Jogi személyek** oldalon. A naplótípus használata előtt létre kell hozni egy főkönyv eltávolítási szabályt a **Főkönyv eltávolítási szabály** oldalon. | Eltávolítás                                                    |
| Tárgyi eszköz költségvetése                | Tárgyieszköz-tételjegyzékbejegyzések létrehozása.                                                                                                                                                                                                                                                                                                                 | Tárgyi eszköz költségvetése                                             |
| Számlajegyzék                  | Szállítói számlák alapadatainak rögzítése.                                                                                                                                                                                                                                                                                                           | Számlajegyzék                                               |
| Bérlista kifizetése              | Kifizetések kiadása bérlistafizetési kimutatás alapján. Ebben a naplóban nem lehet manuálisan tranzakciókat megadni. Előbb fizetési kimutatás kell készíteni, majd beküldeni azokat fizetésre.                                                                                                                                                              |                                                                |
| Időszakos                          | Időszakos tranzakciók létrehozása az időszaki naplóban.                                                                                                                                                                                                                                                                                                      | Időszaki naplók                                              |
| Tárgyi eszközök feladása                 | Tárgyieszköz-tranzakciók feladása.                                                                                                                                                                                                                                                                                                                              | Tárgyi eszközök                                                   |
| Projekt - költségek                | Projektköltség-tranzakciók létrehozása.                                                                                                                                                                                                                                                                                                                        | Expense                                                        |
| Jelentési pénznem kiigazítása     | Helyesbítések létrehozása a főkönyvi számlák egyenlegén a jelentési pénznemben.               | Jelentési pénznem kiigazítási naplói                         |
| Statisztikai tranzakciók            | Statisztikai tranzakciók létrehozása.                                                                                                                                                                                                                                                                                                                            |                                                                |
| Szállító - banki utalás            | Szervezete bankjának átküldhető kötelezvény-átutalási fájl létrehozása.                                                                                                                                                                                                                                                                      | Átutalásnapló                                             |
| Szállítói kifizetés               | Szállítók kifizetési tranzakciók létrehozása.                                                                                                                                                                                                                                                                                                                    | Fizetési napló                                                |
| Szállítói kötelezvény kiállítása       | Szállítói kötelezvény kiállítása fizetési módként. A naplótípus használatához törölje a **Kötelezvénykiállítási napló automatikus létrehozása és feladása számlák feladásakor** lehetőséget a **Fizetési módok – szállítók** oldalon.                                                                                                                                          | Kötelezvénykiállítási napló                                   |
| Szállítói számlagyűjtő feladás nélkül | Ideiglenes érkeztetési számlára még nem feladott szállítói számlatranzakciók létrehozása.                                                                                                                                                                                                                                                             | Szállítói számlagyűjtő a feladási részletek nélkül                  |
| Szállítói számla gyűjtője               | Szállítói számlagyűjtő tranzakciók létrehozása.                                                                                                                                                                                                                                                                                                                    |                                                                |
| Szállítói számla rögzítése          | Naplóban található szállítói számlák feladása.                                                                                                                                                                                                                                                                                                                 | Számlanapló                                                |
| Szállítói kötelezvény újbóli kiállítása     | Olyan kötelezvényt újbóli kiállítása, amelyet a szervezet bankja már korábban elfogadott.                                                                                                                                                                                                                                                                      | Újbóli kötelezvénykiállítás naplója                                 |
| Szállító - kötelezvény kiegyenlítése     | Szállítói kötelezvénykiegyenlítési tranzakciók létrehozása.                                                                                                                                                                                                                                                                                                          | Kötelezvény kiegyenlítésének naplója                                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
