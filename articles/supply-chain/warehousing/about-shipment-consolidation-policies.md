---
title: Szállítmánykonszolidációs irányelvek
description: Ez a témakör áttekintést nyújt azokról a funkciókról, amelyekkel rugalmasan konfigurálhatók a szállítmánykonszolidációs irányelvek.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSShipConsolidationError, WHSShipConsolidationSetShipment, WHSShipConsolidationPolicySelect, WHSShipPlanningListPage, TMSCarrierGroup, WHSShipConsolidationTemplate, WHSShipConsolidationTemplateApply, WHSShipConsolidationTemplateCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: f895b13b2e11d4cb341f80b3cfeb40ed998ccfc4
ms.sourcegitcommit: d9bffbeae2ba14f06294dd275383077d4d65c4fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/01/2020
ms.locfileid: "4654220"
---
# <a name="shipment-consolidation-policies"></a>Szállítmánykonszolidációs irányelvek

A szállítmánykonszolidációs irányelveket használó szállítmánykonszolidációs folyamat lehetővé teszi az automatizált szállítmánykonszolidálást a raktárba történő automatikus és manuális kiadáskor. A funkció bevezetése előtt rendelkezésre álló automatikus konszolidáció véglegesen kódolt mezőket tartalmazott, és a raktárhoz beállított **Szállítmány konszolidálása a raktárnak való kiadáskor** mezőn alapult.

A szállítmánykonszolidációs irányelvek a következő funkciókhoz használatosak:

- Az automatikus kiadás raktárba kötegelt feladata
- Értékesítési rendelés vagy átmozgatási rendelés esetében a **raktárba történő kiadás**
- A dedikált **kiadás a raktárba** oldal
- A **Kiadás a raktárba** parancs a **Rakománytervező munkaterület** oldalon
- Szállítmányok manuális konszolidálása a **Szállítmányok konszolidálása** és **Szállítmánykonszolidációs munkaterület** oldalakon

A szállítmánykonszolidációs irányelvek bevezetése előtt a konszolidációs funkció a raktár szintjén beállításként már létezett. Az egyetlen raktárból származó összes rendelést az összes vevőhöz úgy kezeltek, mintha ugyanazzal a konszolidációs követelménnyel rendelkeztek volna. A szállítmánykonszolidációs irányelvek támogatják azokat a eseteket, amelyekben a különböző szervezetek a szállítmányok konszolidálásához eltérő követelményekkel rendelkeznek.

A lekérdezések a vonatkozó szállítmánykonszolidációs irányelv meghatározására szolgálnak, és a mezők szerkeszthető csoportja határozza meg, hogy a rakománysorok milyen módon legyenek csoportosítva a szállítmány szintjén. (Ez a minta hasonlít a hullámsablonok által követett mintához.) Ezenkívül a program hozzáadta a **Konszolidáció meglévő szállítmányokkal** beállítást az egyes irányelvekhez. Ha ez a beállítás be van kapcsolva, a *Kiadás a raktárba* eljárás megkeresi a konszolidációhoz a szállítmányokat az ugyanazon a konszolidációs irányelv alapján létrehozott meglévő szállítmányok közti kereséssel. Ebben az esetben a rendszer egy létező szállítmányt vagy rakományt fog kijelölni, nem pedig újat létrehozni. A rendszer azonban csak *Nyitott* állapotú meglévő szállítmányokkal fog konszolidálni; a *Kiadott* vagy magasabb állapotú hullámkiadáshoz tartozó szállítmányokat nem tekinti a konszolidáció céljának.

Amikor a szállítmánykonszolidációs irányelvek elérhetővé válnak, a **Szállítmány konszolidálása a raktárnak való kiadáskor** beállítás, amely korábban a **Raktárak** beállítási oldalon volt elérhető, rejtve lesz. Az új szállítmánykonszolidációs funkcióra való áttérés támogatása érdekében a **Szállítmánykonszolidációs irányelvek** oldal egyik funkciója létrehoz egy olyan alapértelmezett irányelvet, amelyben automatikusan szerepel a meglévő raktárakhoz tartozó régi beállítás. Miután létrejött az alapértelmezett irányelv, a **Szállítmány konszolidálása a raktárnak való kiadáskor** beállítást a **Raktárak** beállítási oldalon már nem veszi figyelembe a rendszer.

A **Kiadás a raktárba** oldalon manuálisan felülbírálhatja a megfelelő konszolidációs irányelveket ugyanúgy, ahogy felülbírálhatja a teljesítési irányelveket.

A **Kiadás \> Kiadás a raktárba** parancs segítségével a **Rakománytervezés munkaterület** oldalon létrehozhat olyan, értékesítési rendelési és átmozgatási rendelési sorokon alapuló kimenő rakományokat, mielőtt elvégzi a raktárnak való kiadást. Ezek a rakományok ugyanazt a konszolidációs logikát követik, amelyet a szállítmányok konszolidációjával kapcsolatos irányelvekkel együtt vezettek be.

A **szállítmánykonszolidációs munkaterület** lapon konszolidálhatja azokat a meglévő szállítmányokat, amelyek még nem lettek jóváhagyva, de már ki lettek adva a raktárba. Ez a funkció olyan eseteket támogat, amikor a saját szállítmánykonszolidálással rendelkező automatizált kiadási folyamatot naponta többször futtatja a program, de az esetleges további konszolidációkat a rendszer a visszaigazolási folyamat során a szállítmányozóknak történő szállítás végrehajtása előtt manuálisan azonosítja. Ez a funkció lehetővé teszi az értékesítési rendelési vagy átmozgatási rendelési sorokból létrehozott kimenő szállítmányok konszolidálását a szállítmányoknak a raktárba történő kiadását követően, de még a megerősítés előtt.

A **Szállítmánykonszolidációs munkaterület** oldal úgy működik, mint a rakomány-létrehozási munkaterület, ahol egyszerre több szállítmányt is ki lehet értékelni, és a nem konszolidált rendelést egy meghatározott szállítmányhoz rendelheti. A szállítmánykonszolidációs sablonokat többször is fel lehet használni a javasolt konszolidációk megadásához és a megerősítéshez. Néhány szabályt a rendszer úgy alkalmaz, hogy megakadályozza az illetéktelen konszolidációt, és figyelmeztesse a lehetséges hibákra.

## <a name="overview-of-new-functionality"></a>Új funkciók áttekintése

Ez a szakasz azokat az oldalakat, parancsokat és funkciókat mutatja be, amelyek a *Szállítmánykonszolidációs irányelvek* funkció bekapcsolása és használata során módosultak vagy bővültek.

### <a name="shipment-consolidation-policies-page"></a>Szállítmánykonszolidációs irányelvek oldal

Az irányelvek megkülönböztetése munkarendelés-típus alapján történik. Az **értékesítési rendelések** típus az _Értékesítési rendelési_ szállítmányokat jelzi, az **Átmozgatási rendelések** típus az _Átmozgatási probléma_ szállítmányokat.

Minden szállítmány konszolidációs irányelvének van egy lekérdezése, amely meghatározza, hogy mikor alkalmazzák, és egy sorszáma, amely meghatározza a végrehajtási sorrendet. A konszolidációt a program a kiválasztott mezők egyedi kombinációi esetében alkalmazza. A meglévő (nyitott) szállítmányokkal történő konszolidációhoz egy megadott kiegészítő paramétert használ a rendszer. A rendszer kiértékeli és alkalmazza az irányelveket, valahányszor új szállítmányt hoz létre (a hullám feldolgozása előtt).

Ha egy irányelvből hiányzik egy kötelező mező, vagy a tiltott mezőket tartalmaz, akkor az irányelv érvénytelen jelölést kap a **Kiválasztott** szakaszban. A kötelező és tiltott mezők listája véglegesen kódolt, és ki lehet bővíteni.

Az alábbi listában láthatók a kötelező mezők. Mivel a szállítmányok ezen mezők alapján mindig felosztásra kerülnek, több olyan szállítmány nem csoportosítható, amelyek ezeknél a mezőknél eltérő értékkel rendelkeznek.

- Értékesítési rendelések:

    - **Számlaszám:** _WHSShipmentTable.AccountNum_
    - **Szállítási címzett:** _WHSShipmentTable.DeliveryName_
    - **Postai cím (RecId):** _WHSShipmentTable.DeliveryPostalAddress_
    - **Raktár:** _WHSShipmentTable.InventLocationId_

- Átmozgatási rendeléseknél:

    - **Feladó raktár:** _InventTransferTable.InventLocationIdFrom_
    - **Fogadó raktár:** _InventTransferTable.InventLocationIdTo_

A következő mezők egyik dokumentumtípus esetében sem érhetők el. Ezek a mezők nem láthatók a felhasználói felületen (UI), és nem használhatók konszolidálásra.

- **Szállítmány azonosítója:** _WHSShipmentTable.ShipmentId_
- **Állapot:** _WHSShipmentTable.ShipmentStatus_
- **Szállítmánykonszolidációs irányelv:** _WHSShipmentTable.ShipConsolidationPolicyName_
- **Munkatranzakció típusa:** _WHSShipmentTable.WorkTransType_
- **Hullám azonosítója:** _WHSShipmentTable.WaveId_
- **Rakomány azonosítója:** _WHSShipmentTable.LoadId_
- **Szállítmány azonosítója:** _WHSLoadLine.ShipmentId_
- **Rakomány azonosítója:** _WHSLoadLine.LoadId_

Alapértelmezés szerint az irányelvek létrehozásakor a kötelező mezők csoportja a konszolidációs mezőként használatos. A lista azonban módosítható a bal és a jobb nyílgombok segítségével. (A folyamat hasonlít a hullámsablonokban használt metódusok kiválasztásának folyamatához.)

Minden újonnan létrehozott szállítmánynál megjelennek a felhasználók által ezekhez a mezőkhöz kiválasztott értékek, illetve a rendszer ezeket az ilyen szállítmányokkal történő konszolidáció során felveszi őket a meglévő szállítmányokhoz. Ha két szállítmány ugyanazzal az értékkel rendelkezik egy olyan mezőben, amelyet az adott szállítmányok konszolidációjához kiválasztottak, a szállítmányok konszolidációja megtörténik. Ugyanez az elv vonatkozik a kiválasztott összes további konszolidációs mezőre. Ha az értékek eltérnek, akkor a program elveti a második szállítmányt, és később kijelöli az új szállítmányhoz. Az automatizált konszolidációs folyamat tartalmazza a szállítmány konszolidációs mezőiben szereplő összes egyedi kombináció létrehozását, majd a szállítmány hozzárendelését a megfelelő kombinációhoz.

A nem kiválasztott mezőket a konszolidációs folyamat során figyelmen kívül hagyja a rendszer. Ha két szállítmány egy nem kiválasztott mezőben eltérő értéket tartalmaz, akkor a mező üresen marad (azaz üresre van állítva). Ha egy nem kiválasztott mező esetében mindkét szállítmánynak ugyanaz a értéke, akkor a mező kitöltésre kerül.

A konszolidációs mezők listája (vagyis azok a mezők, amelyek tartalmát törli a rendszer, ha más értékkel rendelkeznek) véglegesen kódolt. A lista minden olyan mezőt tartalmaz, amely egy értékesítési rendelési vagy átmozgatási rendelési sorból inicializáltak egy új szállítmány létrehozásakor. Más szóval, ha egy mező nincs inicializálva egy értékesítési rendelési vagy átmozgatási rendelési sorból, akkor figyelmen kívül hagyja a rendszer, amikor új adatot ad hozzá egy meglévő szállítmányhoz.

### <a name="release-to-warehouse-page"></a>Kiadás a raktárba oldal

- Az alsó rácsban egy új mező jeleníti meg az alkalmazott konszolidációs irányelvet.
- Egy új gomb segítségével manuálisan kiválaszthatja és/vagy felülbírálhatja a konszolidációs irányelvet.

### <a name="release-to-warehouse-command-on-the-load-planning-workbench-page"></a>A Kiadás a raktárba parancs a Rakománytervező munkaterület oldalon

- A logikát úgy igazították, hogy az alkalmazott konszolidációs irányelveket használja.
- A szállítmányok most már csak egyetlen rakományon belül kerülnek konszolidálásra.

### <a name="consolidate-shipments-page"></a>Szállítmányok konszolidálása oldal

- A hasonló szállítmányok (azaz a konszolidációra jelöltek) keresése úgy módosult, hogy a szállítmánykonszolidációs irányelvben kiválasztott mezőket használja.
- A különböző szállítmányoknál különböző értéket tartalmazó mezők üresre vannak állítva. (Korábban a kiválasztott "alap" szállítmány értékeit használta a rendszer.)

### <a name="shipment-consolidation-workbench-page"></a>Szállítmánykonszolidációs munkaterület oldal

- Az új funkciók a manuális konszolidáció folyamatát egy nagyobb léptékben replikálják.
- Ezt a lapot a **raktárkezelési modul** **kiadás a raktárból** menüjéből is megnyithatja.
- Az algoritmus elemzi azokat a meglévő szállítmányokat, amelyek még nincsenek kiszállítva. Ezt követően a konszolidációs irányelvekben kiválasztott mezők alapján javasolja a konszolidációt.

## <a name="comparison-of-functionality"></a>Funkciók összehasonlítása

A következő táblázat összegzi a szállítmánykonszolidálás működését, ha nem használja a szállítmánykonszolidációs irányelveket, és amikor ezeket használja.

| Szállítmánykonszolidációs irányelvek nélkül | Szállítmánykonszolidációs irányelvekkel |
|---|----|
| Nem alkalmazható | A konszolidálásra kiválasztott értékesítési vagy átmozgatási szállítmányoknak ugyanazzal a konszolidációs irányelvvel kell rendelkezniük, mint a létrehozandó szállítmánynak, vagy nyitott szállítmányhoz kell rendelni őket (ha a **Konszolidáció meglévő szállítmányokkal** beállítás be van kapcsolva). |
| A *Kiadás raktárba* eljárás nem keres a meglévő szállítmányok között a konszolidációra szánt szállítmány megtalálásához. A konszolidációra szánt szállítmányok megkereséséhez a rendszer csak a *Kiadás a raktárba* eljárás aktuális példánya alapján létrehozott szállítmányokat használja. | Ha a jelenleg használt konszolidációs irányelvhez be van kapcsolva a **Konszolidáció meglévő szállítmányokkal** beállítás, akkor a *Kiadás a raktárba* eljárás az olyan meglévő szállítmányok között keres szállítmányt a konszolidációhoz, amelyeket ugyanazon konszolidációs irányelv alapján hoztak létre. Ezért ha két irányelv van, akkor a 2. irányelv alapján létrehozott szállítmányok sosem lesznek konszolidálva egy, az 1. irányelv alapján létrehozott szállítmánnyal. |
| Nem alkalmazható | Ha a konszolidációs irányelv mezőinek egyik listája üres, vagy nem található irányelv, akkor minden egyes értékesítési rendelési vagy átmozgatási rendelési sorhoz új szállítmány jön létre. |
| A következő konszolidációs mező határozza meg egy *átmozgatási sorhoz* tartozó szállítmányok konszolidálásához használt értékek egyedi kombinációját. (Az összes többi mezőt figyelmen kívül hagyja a program.)<ul><li>Megrendelés száma (OrderNum)</li></ul> | A következő konszolidációs mezők határozzák meg egy *átmozgatási sorhoz* tartozó szállítmányok konszolidálásához használt értékek egyedi kombinációját. (Az összes többi mezőt figyelmen kívül hagyja a program.)<ul><li>Megrendelés száma (OrderNum)</li><li>Szállítás címzettje (DeliveryName)</li><li>Postai cím (DeliveryPostalAddress)</li><li>ISO ország kódja (CountryRegionISOCode)</li><li>Cím (Address)</li><li>Telephely (InventSiteId)</li><li>Raktár (InventLocationId)</li><li>Szállítmányozó (CarrierCode)</li><li>Szállítmányozói szolgáltatás (CarrierServiceCode)</li><li>Szállítási mód (ModeCode)</li><li>Szállítmányozói csoport (CarrierGroupCode)</li><li>Szállítási feltételek (DlvTermId)</li></ul>Csak ezek a mezők az új szállítmány létrehozásakor rendelkezésre álló és inicializált mezők. |
| A következő konszolidációs mezők határozzák meg egy *értékesítési sorhoz* tartozó szállítmányok konszolidálásához használt értékek egyedi kombinációját. (Az összes többi mezőt figyelmen kívül hagyja a program.)<ul><li>Megrendelés száma (OrderNum)</li><li>Vevő hivatkozása (CustomerRef)</li><li>Vevői igénylés (CustomerReq)</li><li>Szállítási feltételek (DlvTermId)</li></ul> | A következő konszolidációs mezők határozzák meg egy *értékesítési sorhoz* tartozó szállítmányok konszolidálásához használt értékek egyedi kombinációját. (Az összes többi mezőt figyelmen kívül hagyja a program.)<ul><li>Megrendelés száma (OrderNum)</li><li>Számlaszám (AccountNum)</li><li>Szállítás címzettje (DeliveryName)</li><li>Postai cím (DeliveryPostalAddress)</li><li>ISO ország kódja (CountryRegionISOCode)</li><li>Cím (Address)</li><li>Telephely (InventSiteId)</li><li>Raktár (InventLocationId)</li><li>Szállítmányozó (CarrierCode)</li><li>Szállítmányozói szolgáltatás (CarrierServiceCode)</li><li>Szállítási mód (ModeCode)</li><li>Szállítmányozói csoport (CarrierGroupCode)</li><li>Ügynök azonosítója (BrokerCode)</li><li>Irány (LoadDirection)</li><li>Szállítási feltételek (DlvTermId)</li><li>Vevő hivatkozása (CustomerRef)</li><li>Vevői igénylés (CustomerReq)</li></ul>Csak ezek a mezők az új szállítmány létrehozásakor rendelkezésre álló és inicializált mezők. |
| Nem alkalmazható | Egy *értékesítési sorhoz* a következő konszolidációs mezők kötelezőek, és nem távolíthatók el:<ul><li>Számlaszám (AccountNum)</li><li>Szállítás címzettje (DeliveryName)</li><li>Postai cím (DeliveryPostalAddress)</li><li>Raktár (InventLocationId)</li></ul>Alapértelmezés szerint ezeket a mezőket rendeli hozzá a rendszer az új irányelvek létrehozásakor. Ezek nem távolíthatók el. |
| A *Rakományok kiadása a raktárba* eljárás a **Rakománytervezés munkaterület** oldalon saját kódjaival hoz létre szállítmányokat és hullámokat. | A szállítmánykonszolidációs irányelvek alkalmazásával határozzák meg, hogy mely mezőket kell kiértékelni a konszolidációhoz. A szállítmányok csak egyetlen rakományon belül kerülnek konszolidálásra. |
| Manuálisan kiválaszthatja a **Szállítmányok konszolidálása** elemet az **Összes szállítmány** oldalon, majd kiválaszthat egy „alap” szállítmányt. A szűrő javaslatot tesz olyan meglévő szállítmányokra, amelyeknél több kulcsmezőnél egyező érték szerepel. | Manuálisan kiválaszthatja a **Szállítmányok konszolidálása** elemet az **Összes szállítmány** oldalon, majd kiválaszthat egy „alap” szállítmányt. A rendszer más meglévő szállítmányokat javasol a megfelelő szállítmánykonszolidációs irányelvhez konfigurált számos kulcsmező értékének egyeztetésével. |
| A **Szállítmányok konszolidációja** parancsot az **Összes szállítmány** oldalon csak egyetlen szállítmányhoz használhatja. | A **szállítmánykonszolidációs munkaterület** oldal segít megtalálni azokat a szállítmányokat, amelyek még nem szállított állapotban vannak. Ezeknek a szállítmányoknak az elemzése a szállítmánykonszolidációs irányelvekben megadott több kulcsfontosságú mező alapján történik. Azok a szállítmányok lesznek konszolidációra javasoltak, amelyeknél az ilyen mezők értékei megegyeznek.<p>A konszolidációt manuálisan is karbantarthatja, ha eltávolítja a javasolt konszolidálásból a szállítmányokat, és/vagy szállítmányokat ad hozzá. Különböző típusú hibák fordulhatnak elő, de ezek közül néhányat felül lehet bírálni.</p> |
| **Tervezési megjegyzés:** Az *Értékesítési rendelések automatikus kiadása a raktárba* eljárás csoportokra osztja fel az értékesítési sorokat. Minden csoportnak saját egyedi **ReleaseToWarehouseId** értéke van, és a rendszer a *Kiadás a raktárba* eljárás alapján dolgozza fel. Ez az eljárás a munkaszüneti beállításoktól függetlenül új munkát hoz létre. | **Tervezési megjegyzés:** Az *Értékesítési rendelések automatikus kiadása a raktárba* eljárás ugyanazt a **ReleaseToWarehouseId** értéket rendeli az összes feldolgozás alatt álló értékesítési sorhoz. Minden értékesítési sor feldolgozását a *kiadás a raktárba* eljárás ezzel egyidejűleg végzi. A korábbi működés biztosítása érdekében a munkaszünet konfigurálásának a szállítmányazonosító alapján kell történnie. |

## <a name="additional-resources"></a>További erőforrások

- [Szállítmánykonszolidációs irányelvek konfigurálása](configure-shipment-consolidation-policies.md)
