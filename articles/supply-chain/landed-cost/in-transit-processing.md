---
title: Úton lévő áruk feldolgozása
description: Ez a témakör azt ismerteti, hogyan kell dolgozni a szállítás közbeni áruk rendelésekkel. Ha egy rendelés vagy hajóút úton lévő áruk feldolgozásának használatára van beállítva, az áruk még azelőtt számlázhatók, hogy a raktárban felhasználásra bevételezték volna őket.
author: Weijiesa
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DeliveryTerms, InventLocation, InventPosting, ITMGoodsInTransitOrder, ITMTableListPage, ITMTable, ITMContainersListPage, ITMContainers, ITMFolioTableListPage, ITMFolioTable, ITMGoodsInTransitOrderEditLines, SysOperationTemplateForm, WHSRFMenuItem, WHSLocDirTable, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 47e5ef2ef99fcf23af73cfdb6ec57b92ad62f18c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854384"
---
# <a name="goods-in-transit-processing"></a>Úton lévő áruk feldolgozása

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan kell dolgozni a szállítás közbeni áruk rendelésekkel. Ezt a rendeléstípust csak a **Partraszállítási költség** modul használja. Ha egy rendelés vagy hajóút úton lévő áruk feldolgozásának használatára van beállítva, az áruk számlázásával nem kell várnia addig, amíg a raktárban felhasználásra bevételezik őket. Ehelyett az áruk számlázása akkor történik meg, amikor elhagyják a szállító raktárát vagy származási kikötőjét, és a pénzügyi költségeket a hajóút megkezdésekor könyvelik. Ez a funkció lehetővé teszi, hogy helyesen tulajdonosa legyen a készletnek, mivel az áruk gyakran a szervezet tulajdonába kerülnek, amikor elhagyják a szállítási kikötőt.

Az úton lévő árukra vonatkozó rendelések használata esetén a pénzügyileg frissített cikkeket egy ideiglenes raktárba vételezik be, amelyet úton lávő áruk raktárának is neveznek. Az áruk ezután mindaddig ebben a raktárban maradnak, amíg a végső célraktárban (tehát a beszerzési sorban meghatározott raktárban) be nem vételezik őket. Ezek manuálisan nem távolíthatók el.

Amíg a cikkek úton vannak, nem érhetők el készletről, és nem tárolhatók ki szállításhoz a készletből. Megtekintheti azonban az úton lévő áruk készletét. Az árukat emellett az alaptervezéshez is felhasználhatja. Ebben az esetben a beszerzési rendelési sorban megerősítszállítási dátumot használja várható dátumként, amikor a készlet rendelkezésre áll a felhasználásra.

Az alábbi szakaszok a készlet és a hajóút úton lévő áruk koncepciójával és funkciójával történő feldolgozásához szükséges beállításokat írják le.

## <a name="terms-of-delivery"></a>Szállítási feltételek

Ha engedélyezi a **Partraszállítási költség** modult, a rendszer kibővíti a szabványos *szállítási feltételek* entitást az úton lévő áruk funkció támogatásához.

Ha az **Úton lévő áruk kezelése** beállítás *Igen* beállítású a vonatkozó szállítási feltételek rekordjában, akkor az áruk az úton lévő áruk raktárába kerülnek. Ez a művelet csak akkor aktiválódik, ha a készletbevételezés feldolgozása nem a számla feldolgozása előtt történik meg. Ha egy rendelés szállítási feltételei az úton lévő áruk használatára vannak beállítva, a felhasználók többé nem tudnak termékbevételezést feladni a beszerzési rendeléshez. Ha megpróbálják, hiba történik. A hibaüzenetben az áll, hogy a folytatáshoz az úton lévő termékek funkciót kell használniuk.

Az úton lévő árukra vonatkozó szállítási feltételekkel kapcsolatos információk kezeléséhez lépjen a **Beszerzés és forrás \> Beállítások \> Elosztás \> Szállítási feltételek** pontra. Az alábbi táblázat leírja azokat a mezőket, amelyeket a **Partraszállítás költség** modul hozzáad a **Szállítási feltételek** oldalhoz, hogy támogassa az úton lévő áruk funkciókat. Mindkét mező az **Általános** gyorslapon oldalon található. Az oldal további mezőivel kapcsolatos további tudnivalókat lásd: [Szállítási feltételek (képernyő)](/dynamicsax-2012//terms-of-delivery-form).

| Mező | Leírás |
|---|---|
| Szállítási kikötő megadása kötelező | Állítsa *Igen* beállításra, ha kötelező a szállítási kikötő, amikor a szállítási feltételek érvényesek. |
| Úton lévő áruk kezelése | Állítsa a beállítást *Igen* értékre úton lévő áruk kezelésének használatához, ha a szállítási feltételek érvényesek. |

## <a name="warehouses-for-goods-in-transit-and-under-delivery"></a>Az úton lévő áruk és a szállítási hiány raktárai

Ha engedélyezi a **Partraszállítási költség** modult, a standard *raktárak* entitása kibővül, hogy lehetővé tegye a beszerzési rendelés számlázását, amíg az áruk az úton lévő áruk raktárában vannak.

A Partraszállítási költség két új raktártípust ad hozzá: az *úton lévő áruk* és a *szállítási hiány*. Mindkét típusú raktár választható alapértelmezett raktárként. Az úton lévő áruk rendeléseinek sikeres feldolgozása megköveteli, hogy mind az úton lévő áruk raktára, mind a szállítási hiány raktár be legyen állítva a **Raktárak** lapon. Ezt követően minden olyan alapértelmezett raktár esetében, amely a Partraszállítás költségével és az úton lévő árukkal használatos, az úton lévő áruk raktárát és a szállítási hiány raktárat ki kell választani az egyes típusokba tartozó elérhető raktárakhoz.

Az *úton lévő áruk* raktártípusa az Ön úton lévő áruk raktárához lesz társítva, és ezt a raktárt fogja használni az áruk feldolgozására az úton lévő áruk rendelésein, mielőtt bevételeznék azokat a végső célraktárban. Általában minden helyhez elegendő egy úton lévő áruk raktára, ha csak a Hely és Raktár az egyetlen készletkezelésre használt készletdimenzió. Ha a Hely készletdimenziót is használja, akkor minden hely és raktár kombinációhoz be kell állítani egy úton lévő áruk raktárat, hogy az alapértelmezett helyet is meg tudja adni.

A raktárak úton lévő áruk beállításaival kapcsolatos munkához lépjen a **Készletkezelés \> Beállítás \> Készlet részletezése \> Raktárak** elemre. Az alábbi táblázat leírja azokat a mezőket, amelyeket a **Partraszállítás költség** modul hozzáad a **Raktárak** oldalhoz, hogy támogassa az úton lévő áruk funkciókat. Mindkét mező az **Általános** gyorslapon oldalon található. Az oldal többi mezőjével kapcsolatos tudnivalók a [Raktárak (képernyő)](/dynamicsax-2012//warehouses-form) című témakörben találhatóak.

| Mező | Leírás |
|---|---|
| Úton lévő áruk raktára | A főraktárhoz kapcsolódó úton lévő áruk raktár azonosítása. |
| Alulszállításhoz tartozó raktár | A főraktárhoz kapcsolódó szállítási hiány raktár azonosítása. |

## <a name="posting-rules-for-landed-cost"></a>Partraszállítási költség feladási szabályai

A partraszállítási költség két új feladási szabályt ad hozzá, amelyek konfigurálhatóak. Ezek a feladási szabályok a közvetlen beszerzési rendelés számlázott összegeinek pénzügyi feladására szolgálnak, hogy azonosítsa az áruk tulajdonosát, amikor elhagyják a származási helyet. Ez a folyamat felváltja a *számlázott de nem bevételezett áruk* koncepcióját, mivel az árukat még a bevételezés előtt kiszámlázzák. <!-- KFM: Add a link to the related scenario when available. -->

A feladási profilokkal kapcsolatos munkához lépjen a **Készletkezelés \> Beállítás \> Feladás \> Feladás** elemre. A **Beszerzési rendelés** lapon a következő új feladási szabályok érhetők el:

- **Partraszállítási költség, úton lévő áruk** – Az úton lévő áruk kezelési szabályainak megadása.
- **Partraszállítási költség, költségdíj elhatárolás** – A költségszámla elhatárolás feladási szabályainak megadása.

## <a name="goods-in-transit-orders"></a>Úton lévő áruk rendelései

Az úton lévő áruk rendeléseit közvetlenül a **Partraszállítási költség** modulban lehet áttekinteni és kezelni. Az úton lévő áruk rendeléseit közvetlenül az **Úton lévő áruk rendelései** oldalról lehet feldolgozni. Egy másik lehetőség az, hogy az úton lévő áruk rendeléseihez társított hajóútra lép, és feldolgozza az egész hajóutat, szállítókonténert vagy levelet. Hajóút számlázásakor és az úton lévő áruk rendeléseinek létrehozásakor a beszerzésirendelés-sorhoz társított készlet és készletdimenziók minden egyes kombinációjához létrejön egy új úton lévő áruk rendelés.

Azúton lévő áruk kezeléséhez a Partraszállítási költség két lépésből álló eljárást használ:

1. A cikk akkor érkezik be, amikor a készletszámla feldolgozásra kerül, és *Úton* állapotot kap.
1. Az úton lévő áruk rendelését a rendszer az **Úton lévő áruk rendelései** oldalon dolgozza fel, majd a beszerzési rendelésen megadott raktárba bevételezi. Ezen a ponton az állapot *Bevételezve* értékre változik.

Az úton lévő áruk rendeléseivel kapcsolatos feladatokhoz lépjen a **Partraszállítási költség \> Időszakos feladatok \> Úton lévő áruk rendelései** részre.

## <a name="receiving-stock-from-the-goods-in-transit-warehouse"></a>Készlet bevételezése az úton lévő áruk raktárból

A rendszer beállításaitól függően többféle módon lehet árut bevételezni az úton lévő áruk rendeléséből.

### <a name="in-transit-receiving"></a>Szállítás közbeni bevételezés

A következő oldalak bármelyikén végezhet szállítás közbeni bevételezést:

- Az **Úton lévő áruk rendelései** oldalon jelölje ki a sort, majd a Művelet panelen válassza a **Bevételezés** lehetőséget.
- Az **Összes hajóút** oldalon válasszon ki vagy nyisson meg egy hajóutat. Ezután a Művelet panel **Kezelés** lapján, az **Úton lévő áruk** csoportban válassza az **Úton lévő áruk bevételezése** lehetőséget.
- Az **Összes szállítókonténer** oldalon válasszon ki vagy nyisson meg egy szállítókonténert. Ezután a Művelet panel **Kezelés** lapján, az **Úton lévő áruk** csoportban válassza az **Úton lévő áruk bevételezése** lehetőséget.
- Az **Összes levél** oldalon válasszon ki vagy nyisson meg egy levelet. Ezután a Művelet panel **Kezelés** lapján, az **Úton lévő áruk** csoportban válassza az **Úton lévő áruk bevételezése** lehetőséget.

> [!NOTE]
> A szállítás közbeni bevételezést általában olyan helyzetekben használják, amikor a helyek és a köteg/sorozatszám-követés nincsenek használatban.

### <a name="arrival-journal"></a>Érkezési napló

Az áruk érkeztetési napló létrehozásával is bevételezhetők. Az érkeztetési naplót közvetlenül a hajóút oldalról lehet létrehozni. A szervezete által alkalmazott bevált gyakorlatok határozzák meg, hogy az érkeztetési napló áruk bevételezésére használható-e.

1. Nyissa meg a hajóutat, a tárolót vagy a levelet.
1. A műveleti ablakban a **Kezelés** lapon a **Funkciók** csoportban válassza az **Érkeztetési napló létrehozása** lehetőséget.
1. Az **Érkeztetési napló létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Mennyiség inicializálása** – A mennyiség szállítás alatt lévő mennyiségből való beállításához állítsa *Igen* értékre. Ha ez a beállítás *Nem* értékű, nem lesz beállítva alapértelmezett mennyiség az úton lévő áruk soraiból.
    - **Létrehozás az úton lévő árukból** – A mennyiségeknek a kijelölt hajóút, konténer vagy levél kijelölt úton lévő áruk sorából történő megadásához állítsa *Igen* értékre a beállítás.
    - **Létrehozás rendeléssorokból** – A beállítás *Igen* értékre állításával beállítható az érkeztetési napló alapértelmezett mennyisége a beszerzésirendelés-sorokból. Az érkeztetési naplóban szereplő alapértelmezett mennyiséget csak akkor lehet ilyen módon beállítani, ha a beszerzési rendelés sorában szereplő mennyiség megegyezik az úton lévő áruk rendelésén szereplő mennyiséggel.

1. Az érkeztetési napló feldolgozása a következőben leírtak szerint: [Cikkbevételezések regisztrálása cikkérkeztetési naplóval](/dynamicsax-2012/appuser-itpro/register-item-receipts-with-an-item-arrival-journal).

> [!NOTE]
> Az érkeztetési napló általában olyan helyzetekben használatos, amikor helyeket és köteg-/sorozatkövetést használnak, de a raktárkezelés nincs használva.
>
> Ha betárolási hely van megadva az érkeztetési naplóban, a rendeléssorok között nem szabad megadni az alapértelmezett bevételezési helyeket.

## <a name="warehouse-management"></a>Raktárkezelés

Ha engedélyezi a **Partraszállítási költség** modult, a **Raktárkezelés** modul több lapja is módosul, így a rendelésfeldolgozás (pontosabban az úton lévő áruk feldolgozása) a **Partraszállítási költség** modulon keresztül hajtható végre. Ez a szakasz a **Raktárkezelés** modulban hozzáadott mezőket és folyamatokat ismerteti.

### <a name="mobile-device-menu-items"></a>Mobileszköz menüpontjai

Az árukat mobileszköz használatával lehet bevételezni, feltéve, hogy a mobileszköz menüje és a **Raktárkezelés** modul be van állítva az áruk bevételezésére az úton lévő áruk rendelésén. Ez a szakasz az úton lévő áruk bevételezéséhez kapcsolódó beállításokat írja le.

A mobileszközök úton lévő áruk feldolgozására való beállításához lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menüpontjai** részre.

A partraszállítási költség hozzáadja a következő munkalétrehozási folyamatokat a mobileszköz menüelemeihez, hogy támogassák az úton lévő áruk feldolgozását:

- Úton lévő áruk cikkének bevételezése
- Úton lévő áruk cikkbevételezése és betárolása

Ezen folyamatok konfigurációs beállításai hasonlítanak a [beszerzési rendelés bevételezési és betárolási munkáinak létrehozási folyamata](/dynamicsax-2012/appuser-itpro/configure-mobile-devices-for-warehouse-work) beállításaihoz. Az *Úton lévő áruk cikkbevételezése és betárolása* folyamat azonban a következő mezőt is hozzáadja.

- **Szállítókonténer kész engedélyezése** – Ha ez a beállítás *Igen* értékű, a betárolási munka befejezésekor a Raktárkezelés mobilalkalmazás egy további, **Szállítókonténer kész** nevű lehetőséget is biztosít. Ha ez a beállítás be van jelölve, a dolgozót felkéri a rendszer annak megerősítésére, hogy a konténer kész. Ezen a ponton minden rövid bevételezés hiány tranzakcióként lesz feldolgozva.

### <a name="location-directives"></a>Helyutasítások

A Partraszállítási költség hozzáad egy új, *Úton lévő áruk* nevű munkarendelés-típust a **Helyutasítások** oldalhoz. Ezt a munkarendelés-típust ugyanúgy kell konfigurálni, mint a [beszerzési rendelés munkarendelés-típusait](/dynamicsax-2012/appuser-itpro/create-a-work-template).

### <a name="work-templates"></a>Munkasablonok

Ez a szakasz olyan funkciókat ír le, amelyekhez a **Partraszállási költség** modul hozzáad a munkasablonokhoz.

#### <a name="goods-in-transit-work-order-type"></a>Úton lévő áruk munkarendelési típus

A Partraszállítási költség hozzáad egy új, *Úton lévő áruk* nevű munkarendelés-típust a **Munkasablonok** oldalhoz. Ezt a munkarendelés-típust ugyanúgy kell konfigurálni, mint a [beszerzési rendelés munkasablonjait](/dynamicsax-2012/appuser-itpro/create-a-work-template).

#### <a name="work-header-breaks"></a>Munkafejléc törések

Az *Úton lévő áruk* típusú munkarendeléssel rendelkező munkarendelési sablonokat be lehet állítani munkafejlécek felosztására. A **Munkasablonok** oldalon hajtsa végre az alábbi lépések valamelyikét:

- A sablon **Általános** lapján állítsa be a munkafejléc maximumait. Ezek a maximumok ugyanúgy működnek, mint a beszerzési rendelések munkasablonjain. (További tájékoztatás a [beszerzési rendelés munkasablonjai](/dynamicsax-2012/appuser-itpro/create-a-work-template) részben található.)
- A **Munkafejléc törése** gombbal meghatározhatja, hogy a rendszer mikor hozzon létre új munkafejléceket a rendezéshez használt mezők alapján. Ha például munkafejlécet szeretne létrehozni minden egyes tárolóazonosítóhoz , válassza a műveleti panelen a **Lekérdezés szerkesztése** lehetőséget, majd adja hozzá a **Tárolóazonosító** mezőt a lekérdezésszerkesző **Rendezés** lapjához. A **Rendezés** lapra hozzáadott mezők *csoportosítási mezőként* választhatók ki. A csoportosítási mezők beállításához válassza a műveleti panel **Munkafejléc törlései** elemet, majd minden egyes, csoportosítási mezőként használni kívánt mezőhöz jelölje be a **Csoportosítás adott mező szerint** oszlopban található jelölőnégyzetet.

A partraszállási költség a [várton felüli tranzakciót](over-under-transactions.md) hoz létre, ha a regisztrált mennyiség meghaladja az eredeti rendelési mennyiséget. Amikor elkészült egy munkafejléc, a rendszer frissíti a fő rendelési mennyiség készlettranzakcióinak állapotát. Először azonban frissíti a vártnál nagyobb tranzakcióhoz kapcsolódó mennyiséget, miután az fő rendelést teljesen megvásárolták.

Ha visszavon egy már regisztrált vártnál nagyobb tranzakció munkafejlécét, akkor a vártnál nagyobb tranzakciót előbb csökkenti a visszavont mennyiséggel. Miután a vártnál nagyobb tranzakciót 0-ra (nulla) csökkentették, a rekord törlődik, és a további mennyiségek regisztrációja törlődik a fő rendelési mennyiséggel szemben.
