---
title: Promóciós engedmények kezelése
description: Ez a témakör leírja a promóciós engedmények kezelését a Dynamics 365 Supply Chain Management megoldásban.
author: Henrikan
ms.date: 08/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MCRBrokerClaims, MCRBrokerWriteOffReasonPrompt, MCRRoyaltyVendTable, MCRRoyaltyVendTrans, PdsCustRebateGroup, PdsRebateAgreement, TAMCopyTradePromotions, TAMDeduction, TAMDeductionCreate, TAMDeductionDenyReason, TAMDeductionParmDeny, TAMDeductionParmMassUpdate, TAMDeductionParmMatch, TAMDeductionParmSplit, TAMDeductionParmWriteOff, TAMDeductionType, TAMDeductionWriteOffReason, TAMFundManagement, TAMFundUsage, TAMListPage, TAMMarketingObjective, TAMMerchEventType, TAMOneTimePromotion, TAMPromoCompareGraph, TAMPromoStatistic, TAMPromotionAnalysisSummary, TAMPromotionParameters, TAMPromotionPeriod, TAMTemplateListPage, TAMTradePromotionAnalysis, TAMTradePromotions, TAMWhatIfPromotionAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2018-01-31
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: c9e523ef88a472e8f6372f871360803649c9cded
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672850"
---
# <a name="trade-allowance-management"></a>Promóciós engedmények kezelése

[!include [banner](../includes/banner.md)]

A kereskedelmi kedvezmények kezelése megkönnyíti a vállalatok számára az értékesítési promóciós programok kezelését, amelyek „teljesítményalapú fizetés” jellegű anyagi jutalmakat kínálnak a fogyasztók számára annak érdekében, hogy a mennyiségi és viselkedési célokat elérje. A funkció lehetőségeit olyan vállalatok számára tervezték, amelyek átfogó promóció-a-profit-érdekében folyamatokra összpontosítanak, a promóciós alap költségvetés-tervezéséről és felosztásától kezdve, a kedvezményszerződések létrehozásán, valamint a jogcím kialakításán és feldolgozásán, a fizetések feldolgozásán keresztül egészen a promóció hatékonysági elemzésének elkészítéséig.


Ez a cikk széleskörű áttekintést biztosít a Kereskedelmi kedvezmények kezelése funkcióba, és segít megismerni egy értékesítési promóciós program kezelésének tipikus feladatsorozatát. Várhatóan ezt a funkciót sokféle típusú, üzemeltetési és döntéshozatali felelősségi körrel rendelkező felhasználó használja majd céljaik elérése érdekében:

- Diszkrecionális pénzalapok allokálása a kiválasztott számlákhoz, valamint kereskedelmi kedvezményszerződések beállítása promóciókhoz, a továbbszámlázások és egyszeri, egyösszegű kifizetések alapján (egy megállapodott szolgáltatásért)
- A tárgyalt promóciós szerződések futtatása folyamatos értékesítésen és továbbszámlázási követelések generálásán keresztül
- A generált követelések kiszámítása, jóváhagyása és feldolgozása, majd továbbításuk a Kinnlevőségekhez (A/R) mint fizetéskiegyenlítés levonásai
- A vevő teljes összegnél kevesebb kifizetésének és a neki járó levonásnak az egyeztetése
- A promóciós alap használatának nyomon követése, és a program nyereségességi és hatékonysági értékelése

## <a name="audience-and-purpose"></a>Célközönség és cél

E dokumentum információit vállalatok üzleti döntéshozóknak szántuk, például beszerzési vezetőknek, pénzügyi igazgatóknak (CFO) és főkönyvelőknek, akik a következő felelősségi körökkel rendelkeznek:

- Magas szintű költségvetés és pénzalapfelosztás
- Értékesítési promóciók tervezése és elemzése
- Olyan személyzet irányítása, amely továbbszámlázási igényeket dolgoz fel, árusítási események alapján kifizetéseket futtat, valamint kiegyenlít hiányos fizetéseket és levonásokat

Az ilyen beosztásokban dolgozó személyek különféle módszereket keresnek céljaik elérésére:

- Marketing és promóciós pénzalapok jobb felhasználása.
- A különböző típusú promóciós programok és kedvezmények rugalmas alakítása.
- A promóció teljesítményének figyeléséhez és az igények feldolgozásához kapcsolódó adminisztratív terhek és hibák csökkentése.
- A jövőbeli követeléseknek való elhatárolás révén javítani a pénzforgalmi előrejelzéseket.
- Számszerű alappal való rendelkezés az ügyfelekkel folytatott folyamatos és jövőbeli tárgyalásokhoz promóciós témában.

## <a name="promotional-fund-and-trade-allowance-agreement"></a>Promóciós pénzalap és Kereskedelmi kedvezményszerződés

Egy kereskedelmi kedvezményszerződés olyan ösztönzési program, ahol teljesítményalapú fizetés jellegű anyag jutalmakat kínálnak az ügyfeleknek annak érdekében, hogy meghatározott mennyiségi célértékeket és/vagy viselkedési célokat érjenek el. A promóciós pénzalapok költségvetés szempontjából tervezett kiadások. Ezzel a módszerrel a promóciós kampányokat rögzíteni lehet.

### <a name="promotional-fund"></a>Promóciós pénzalap

A kereskedelmi kedvezményszerződésekre allokált pénzalapokat a **Pénzalapok** oldalon rögzítik. A **Pénzalapok** oldal megnyitásához válassza a **Értékesítés és marketing** \> **Kereskedelmi kedvezmények** \> **Pénzalapok** \> **Pénzalapok** lehetőséget.

![Pénzalapok lap.](./media/trade-allowance-management-funds-page.png "Pénzalapok lap")

A **Pénzalapok** oldalon megtekintheti a promóciós pénzalapok részleteit.

Az **Általános** gyorslapon a pénzalap érvényességi időszaka látható, valamint a költségvetésben tervezett összege. Ahhoz, hogy a pénzalapot egy promóciós szerződéshez lehessen rendelni, az **Állapot** mező értékének **Jóváhagyott** értékűnek kell lennie.

A **Vevők** gyorslapon a vevő hierarchiája látható. A pénzalap által megcélzott vevők kiválasztásához húzza őket a **Pénzalap vevői** rész alá. Ez a gyorslap a pénzalap teljes összegének megoszlását is mutatja.

A **Cikkek** gyorslap a promócióban részt vevő cikkeket mutatja.

### <a name="trade-allowance-agreement"></a>Kereskedelmi kedvezményszerződések

Miután a pénzalap meghatározása megtörtént, a promóciótervezés következő lépése a promóciós szerződések regisztrálása (amelyeket más néven kereskedelmi kedvezményszerződésnek nevezünk), a pénzalapok felosztása és az egyes árusítási események teljesítménycéljainak meghatározása.

A kereskedelmi kedvezményszerződések a **Kereskedelmi kedvezményszerződések** oldalon kerülnek rögzítésre. A **Kereskedelmi kedvezményszerződések** oldalt az **Értékesítés és marketing** \> **Kereskedelmi kedvezmények** \> **Kereskedelmi kedvezményszerződések** útvonalon tudja megnyitni.

![Promóciósengedmény-megállapodások oldal.](./media/trade-allowance-management-agreements-page.png "Promóciósengedmény-megállapodások oldal")

#### <a name="header"></a>Fejléc

Válassza a **Fejléc** lehetőségre, ha a Fejléc nézetre szeretne váltani.

Az **Általános** gyorslapon a **Rendelés eddig** és a **Rendelés ettől** mezők határozzák meg a szerződés érvényességi időtartamát. A szerződés **Belsőleg jóváhagyva** jóváhagyási állapota azt jelzi, hogy a szerződés még nem érvényes, és még nem lehet értékesítési rendelés feldolgozásakor alkalmazni.

Az **Általános** gyorslap **Elemzés** része olyan fontos mezőket tartalmaz, amelyek a promóció értékelésekor használt mennyiségeket és költségeket határozzák meg:

- Az **Alapegységek** mező határozza meg a kiválasztott vevőknek eladandó termékek mennyiségét, mielőtt a promóció alkalmazásra kerül.
- A **Számított szállítási mennyiség** értéket a **Növekedési százalék** értékének megfelelően számolja ki a rendszer, amely a promóció tervezett célnövekménye.
- A **Kereskedelmi kedvezmény költsége** a kereskedelmi kedvezményszerződésben foglalt különböző események mennyiségének megfelelően kerül kiszámításra.

A **Vevők** gyorslapon a baloldalon található listában választhatja ki és tekintheti meg a vevői csoportokat, amelyek előre meghatározott hierarchiában jelennek meg. Kiválaszthatja a teljes hierarchiát vagy bizonyos számlákat a kedvezményszerződés célpontjaiként.

A **Cikkek** gyorslapon, valamint a **Pénzalapok** oldal **Cikkek** gyorslapján a termékek hozzáadásra kerülnek a termékekhez, amelyek értékesítését a megállípodott kedvezménnyel társítja.

A **Pénzalapok** gyorslapon megtekintheti a szerződéshez társított promóciós pénzalapokat. Ugyanitt megtekintheti a szerződés eseményekre vonatkozó költségfelosztását. Egy 100%-os eseményköltség-felosztás azt jelenti, hogy a promóciót kizárólag egy pénzalapból finanszíroznak majd. Egyéb esetben a promóciós szerződés több különböző pénzalapra is támaszkodhat, amelyeket egyenlő vagy különböző százalékban osztanak fel.

#### <a name="lines"></a>Sorok

Ezután válassza ki **Sorok** lehetőséget a Sorok nézetre való váltáshoz.

Az **Árusítási események** lap megmutatja az adott szerződés által fedezett események típusát. Három típus létezik: továbbszámlázás, egyösszegű vagy számlán kívüli.

Az árusítási esemény kiválasztása után válassza az **Összegek** lapot az esemény részleteinek megtekintéséhez.

![Promóciós engedményekre vonatkozó megállapodási sorok.](./media/trade-allowance-management-agreements-lines.png "Promóciós engedményekre vonatkozó megállapodási sorok")

A **Kereskedelmi kedvezmény** sorok szakaszban megadhatja a mennyiségi vagy összegtartományt, amelyet a vevőnek el kell érnie definíció alapján a jutalmak megszerzéséhez.

**Továbbszámlázás** típusú árusítási esemény esetén az **Összegek** lap felső része határozza meg azokat a szabályokat, amelyek alapján a továbbszámlázás alkalmazható, generálható és fizethető. Például a szabályok a következő feltételeket határozhatják meg a továbbszámlázási követelésre vonatkozóan:

- Az értékesítési rendelés létrehozásának dátumán alapul (a **Számítási dátum típus** értéke **Létrehozott**).
- Az értékesítési rendelés sorának engedmények előtti összege alapján kerül kiszámításra, nem a nettó összeg alapján, amely az engedményeket tartalmazza (a **Forrás** értéke **Bruttó**).
- Az eladott termékek mennyiségén alapul, nem az összegükön (a **Visszatérítés sortörés típus** értéke **Mennyiség**).
- Egyhavi időszakonként kerül kiszámításra (az **Értékesítés összesítés alapja** értéke a **Hónap**). 
- Levonásként kerül kiegyenlítésre, nem pedig A/P használatával (a **Kifizetés típusa** értéke **Vevői levonások**).

Abban az esetben, ha egy árusítási esemény **Egyösszegű** típusú, az **Összegek** lap azt a mennyiséget mutatja, amelyet a vevőnek levonás formájában fognak kifizetni, amikor a vevő elér egy bizonyos teljesítményt. Egy **Nyitott** jóváhagyási állapot azt jelzi, hogy az egyösszegű kifizetést még nem teljesítették.

Ahhoz, hogy a szerződés feltételeinek megfelelő értékesítési rendelésekre alkalmazni lehessen a szerződést, a szerződés állapotának **Megerősített** értékűnek kell lennie. 

## <a name="perform-sales-under-the-planned-merchandising-event-and-generate-bill-back-claims"></a>Értékesítés teljesítése a tervezett árusítási esemény alatt és továbbszámlázási követelések létrehozása

Amikor olyan értékesítési rendeléseket hoz létre, amelyek a szerződés előírásait teljesítő sorokat tartalmaznak, a kapcsolódó információkat az **Értékesítési rendelés** oldalon tekintheti meg az **Értékesítési rendelés sora** \> **Megtekintés** \> **Ár részletei** lehetőség kiválasztása után.

Az **Ár részletei** oldalon, a **Visszatérítések** gyorslapon az értékesítési adminisztrátor megtekintheti az érvényes kereskedelmi kedvezményszerződésből származó továbbszámlázást (a visszatérítés programazonosítója is látható), és a teljes összeg alkalmazásra kerül a sorban. Ez az összeg a **Visszatérítés összege** mezőben is megjelenik, az **Ár részletei** oldal **Becsült haszonkulcs** részében.

Az értékesítési számla feladásakor a megfelelő továbbszámlázási követelés kerül létrehozásra minden egyes számlasorra vonatkozóan.

> [!NOTE]
> Annak érdekében, hogy láthassa az **Ár részletei** oldalt, a **Kinnlevőségek paraméterei** oldalon, az **Árak** lapon jelölje be az **Ár részleteinek engedélyezése** jelölőnégyzetet. d

## <a name="process-claims-and-pass-them-as-deductions-to-ar"></a>Követelések feldolgozása és továbbítása levonásként az A/R-hez

A továbbszámlázás kezelés folyamatának következő lépése a követelések ellenőrzése, kiszámítása és jóváhagyása, majd levonásokká alakítása.

A továbbszámlázási munkaterületen a promóciós szerződés tulajdonosa rendszeresen áttekinti és feldolgozza a létrehozott követeléseket. Ezen a helyen alakítja át az A/R adminisztrátor a jóváhagyott követeléseket levonásokká vagy szokásos fizetésekké, a követekés kifizetési módjától függően.

A **Továbbszámlázási munkaterület** lapon megtekintheti a követelés sorait. Ha a követelések **Újraszámítandó** állapotban vannak, minden kumulatív hatás esetén újra kell számítani őket.

### <a name="recalculate-claims"></a>Követelések újraszámítása

A követelések újraszámításához válassza az **Összesítés** lehetőséget a Műveletpanelen. Majd a **Visszatérítések összesítése** párbeszédpanelen válassza ki a vevőt.

Az újraszámítás következményeként a program új követeléseket hoz létre az összegekhez, hogy az eredeti követeléseket az egységenkénti minősítő összeghez igazítsa. Vevő, cikk, pénznem, mértékegység, készletdimenziók, pénzügyi dimenziók és értékesítési csoportok minden egyes egyedi kombinációjához létrejön egy kiigazítási követelés. Ezek a kiigazítási követelések ugyanazzal a referenciával rendelkeznek az értékesítési rendelésre és számlaszámra, mint azok a követelések, amelyet kiigazítanak (azokra a követelésekre vonazkoóan, amelyeket eredetileg az értékesítési bizonylatból hoztak létre). Az eredeti követeléssel ellentétben a kiigazítási követelés esetében nem szerepelnek értékek azokban a mezőkben, amelyek az eredeti értékesítési rendelés sorának összegeit és mennyiségét írják le.

Az újraszámítás befejeződése után a követelések állapota **Kiszámított** állapotra változik. A követelések jóváhagyásához válassza a **Jóváhagyás** lehetőséget a Műveletpanelen.

### <a name="process-claims-and-pass-them-to-ar"></a>Követelések feldolgozása és továbbítása az A/R-hez

A követelések most készen állnak az A/R feldolgozásra. A feldolgozáshoz válassza a **Feldolgozás** lehetőséget a Műveletpanelen. 

A követelések feldolgozása után az állapot **Jelölés** állapotúra változik, és azt jelzi, hogy a napló feladása (a feladott napló a Visszatérítés elhatárolási napló, ahogy az A/R paraméterekben meghatározásra került) a következő események megtörténtét okozta: 

- A követelések levonásként átvitelre kerültek az ideiglenes vevői egyenlegbe.
- A visszatérítés elhatárolási számlán jóváírás történt, hogy a vevő jövőbeli kötelezettségét jelezze.
- A visszatérítés költségszámlán terhelés történt, hogy az értékesítéssel kapcsolatban felmerült költségeket jelezze.

A folyamat befejezéséhez a Kinnlevőségek adminisztrátornak kezelnie kell az elhatárolási levonásokat, mégpedig úgy, hogy jóváírásként (kötelezettségként) átviszi őket a vevő egyenlegére. 

A feladat megkezdéséhez válassza a **Beszedés** \> **Tranzakciók kiegyenlítése** lehetőséget a **Vevő** oldalhoz tartozó Műveletpanelen. Majd a **Tranzakciók kiegyenlítése** oldalon válassza a **Funkciók** \> **Továbbszámlázási program** lehetőséget. Ez a visszatérítési oldal az összes továbbszámlázási követelést megjelenít, amelyeket korábban már feldolgoztak.

Ha jóváírást szeretne létrehozni, jelölje be a **Jelölés** jelölőnégyzetet minden sorra vonatkozóan, majd válassza a **Funkciók** \> **Jóváírás létrehozása**.

A jóváírás létrehozása után a napló feladásra került. (A feladott napló az AR felhasználási napló, az A/R paramétereknek megfelelően). Ennek eredményeképp a valós kötelezettségek (jóváírás) összege átkerült a vevői egyenlegbe. Pénzügyi tekintetben ez a helyzet azt jelzi, hogy a következő események történtek:

- A vevői Kinnlevőségek számlán jóváírás történt.
- A visszatérítés elhatárolási számlán terhelés történt.

Az **Egyösszegű** típusú árusítási esemény jóváhagyásához válassza ki az eseményt a **Kereskedelmi kedvezményszerződések** oldalon, majd az **Összegek** oldalon válassza a **Jóváhagyás** lehetőséget.

## <a name="settle-the-deduction-that-is-due-and-the-customer-short-pay-by-using-the-deduction-workbench"></a>Az esedékes levonás és a vevői hiányos fizetés kiegyenlítése a Levonás munkaterület használatával

Gyakran olyan esetekben, ahol továbbszámlázás várható, a vevők úgy döntenek, bizonyos számlákat hiányosan fizetnek ki. A jövőbeli fizetési egyeztetési problémák megelőzése érdekében az A/R adminisztrátor levonásként rögzíti ezeket a hiányos kifizetéseket, amikor a tényleges vevői kifizetéseket rögzíti. Majd a levonás munkaterületen később ezek a vevői levonások egyszerűen kiegyenlíthetőek a vállalat részéről esedékes követelések összegével.

A vevői hiányos fizetés Fizetési naplóban való rögzítéséhez válassza a **Kinnlevőségek** \> **Kifizetések** \> **Fizetési napló** lehetőséget, és hozzon létre egy új fizetési naplót. A Műveletpanelen válassza ezután a **Levonások** elemet. A **Levonás** lapon létrehozhatja és nyomon követheti a hiányosan fizetett összeget.

A behajtási vezető felelős a nyitott jóváírás-tranzakció és a hiányos fizetési tranzakció egymással szembeni kiegyenlítéséért a Levonások munkaterületen.

A levonások kezeléséhez válassza az **Értékesítés és marketing** \> **Kereskedelmi kedvezmények** \> **Levonások** \> **Levonások munkaterület** lehetőséget. Az oldal felső részében találhatóak a vevő hiányos fizetéseit megjelenítő sorok. Az oldal alsó része jeleníti meg a vevő nyitott jóváírás-tranzakcióit. 

A levonás nyitott tranzakcióval szembeni kiegyenlítéséhez jelölje meg a levonás sort, majd a Nyitott tranzakciók lapon jelölje be a sort. A Műveletpanelen kattintson a Karbantartás > Egyeztetés elemre.

Az eredeti követelések állapota **Befejezett** állapotra változik.

## <a name="analyze-the-effectiveness-of-the-promotion-and-fund-consumption"></a>A promóció és a pénzalap-felhasználás hatékonyságának elemzése

A Kereskedelmi kedvezmények kezelése menüpontban számos jelentési és elemzési nézet érhető el a program kulcsstatisztikáinak és pénzalap-felhasználásának áttekintéséhez.

A **Kereskedelmi kedvezmény tevékenység** oldalon, az **Áttekintés** lapon megtalálja a kereskedelmi kedvezményszerződés főbb részleteit. A többi lap részletesebb információkat tartalmaz a társított dokumentumokról, fizetésekről, és más, a programhoz kapcsolódó eseményekről.

Az **Összefoglaló** lap a promóció során eladott termékek teljes mennyiségét mutatja, a kiszámlázott értékesítési összeget, valamint a kifizetett továbbszámlázást és egyösszegű kifizetéseket.

A **Továbbszámlázási jóváírások** lap a vevőnek jóváírt egyéni továbbszámlázások részleteit tartalmazza.

A promóció különböző teljesítmény-mérőszámainak részletesebb analitikai áttekintése érdekében használja az Elemzés nézetet. Az Elemzés nézetet az **Értékesítés és marketing** \> **Kereskedelmi kedvezmények** \> **Kereskedelmi kedvezményszerződések** lehetőségre kattintva érheti el. A Műveletpanelen kattintson az **Elemzés** elemre.  

A promóció különböző teljesítmény-mérőszámainak részletesebb analitikai áttekintése érdekében használja az Elemzés nézetet. Az Elemzés nézetet az **Értékesítés és marketing** \> **Kereskedelmi kedvezmények** \> **Kereskedelmi kedvezményszerződések** lehetőségre kattintva érheti el. A Műveletpanelen kattintson az **Elemzés** elemre. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]