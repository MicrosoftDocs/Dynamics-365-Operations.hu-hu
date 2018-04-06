---
title: "A költségvetés-tervezés áttekintése"
description: "Ez a cikk bemutatja a költségvetés-tervezést, illetve információkkal szolgál a költségvetés-tervezés beállítási és a költségvetés-tervezési folyamatok létrehozási lehetőségeiről."
author: twheeloc
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 17251
ms.assetid: a2e06633-a800-4840-a962-88fed8462104
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: e874d7353e0d9561ca55f313bfb5209299298169
ms.contentlocale: hu-hu
ms.lasthandoff: 03/26/2018

---

# <a name="budget-planning-overview"></a>A költségvetés-tervezés áttekintése

[!include[banner](../includes/banner.md)]


Ez a cikk bemutatja a költségvetés-tervezést, illetve információkkal szolgál a költségvetés-tervezés beállítási és a költségvetés-tervezési folyamatok létrehozási lehetőségeiről.

<a name="overview-of-budget-planning"></a>A költségvetés-tervezés áttekintése
---------------------------

A költségvetés-tervezés az a folyamat, amely során előkészíti a szervezet által a jövőben alkalmazandó költségvetést. Egy szervezet konfigurálhatja a költségvetés-tervezését, és beállíthat olyan költségvetés-tervezési folyamatokat, amelyek célja a szervezet irányelveiknek, eljárás-rendjeiknek és a költségvetési előkészítés követelményeinek való megfelelés. 

Ha megérti a Microsoft Dynamics 365 for Finance and Operations rendszerben használt fogalmakat és terminológiát, könnyebben valósíthatja meg a szervezet költségvetés-tervezését.

### <a name="key-terms"></a>Kulcsfogalmak

-   **Költségvetés-tervezési folyamatok** – A költségvetés-tervezési folyamatok határozzák meg, hogy a költségvetési tervek hogyan frissíthetők, küldhetők tovább, ellenőrizhetők és hagyhatók jóvá a költségvetési szervezet hierarchiájában. A költségvetés-tervezési folyamat a költségvetési ciklushoz és a szervezethez egy jogi személyiségen keresztül kapcsolódik.
-   **Költségvetési tervek** – A költségvetési tervek a költségvetési ciklushoz tartozó költségvetési adatokat tartalmazzák. Több költségvetési tervvel is rendelkezhet, amelyeket különféle célokra használhat. Például a költségvetési tervek használhatók különböző szervezeti egységek költségvetési összegeinek létrehozására, vagy segíthetnek abban, hogy összehasonlításokat készíthessen és megalapozott döntéseket hozzon.
-   **Költségvetési tervváltozatok** – A költségvetési tervváltozatok határozzák meg a költségvetési tervekhez tartozó adatok csoportjait. A költségvetési tervváltozatok meghatározásával a monetáris és egyéb egységosztályokat, például a mennyiséget támogatja. Példa a költségvetési tervváltozatokra: a Részleg előző éve, illetve a Részleg igénylései. A költségvetési tervváltozatok olyan esetpéldák, melyek az előző évi hívások és a teljes munkaidőssel egyenértékű (FTE) alkalmazottak mennyiségeit használják.
-   **Költségvetés-tervezési szakaszok** – A költségvetés-tervezési szakaszok határozzák meg a költségvetési terv lépéseit a kezdetektől a végleges jóváhagyásig. A költségvetés-tervezési szakaszok költségvetés-tervezési munkafolyamatokba vannak szervezve.
-   **Költségvetés-tervezési munkafolyamatok** – A költségvetés-tervezési munkafolyamatok a költségvetés-tervezési szakaszok megadásából állnak. A költségvetési munkafolyamatokhoz a költségvetés-tervezési munkafolyamatok tartoznak. A költségvetés-tervezési munkafolyamatok olyan automatizált és manuális eljárások, amelyek a költségvetési terveket átviszik a költségvetés-tervezési szakaszokon.

[![Költségvetés-tervezési terminológia](./media/budgetplanning-terms-1024x504.png)](./media/budgetplanning-terms.png)

### <a name="common-tasks"></a>Általános feladatok

Az Emberi erőforrások modullal a következők végezhetők el:

-   Létrehozhat költségvetési terveket, hogy meghatározza a várható bevételeket és kiadásokat egy költségvetési ciklushoz.
-   Elemezheti és frissítheti a költségvetési terveket különböző tervváltozatok használatával.
-   Automatikusan elküldheti ellenőrzésre és jóváhagyásra a költségvetési terveket a munkalapokkal, az indoklásokkal és a mellékletekkel együtt.
-   Egyesíthet több költségvetési tervet a szervezet alacsonyabb szintjéről egy magasabb szintű költségvetési tervbe. A szervezet egy magasabb szintű egy költségvetési terv kialakítása, továbbá az alacsonyabb szintű a szervezet a költségvetési felosztáshoz.

A költségvetés-tervezés integrálva van más Microsoft Dynamics 365 for Finance and Operations modulokba is. Ezért az előző költségvetések, a tényleges kiadások, a tárgyi eszközök és az emberi erőforrások adatait is felhasználhatja. A költségvetés-tervezés integrálva van a Microsoft Excel és a Microsoft Word programokban is, így ezen eszközök segítségét is felhasználhatja a költségvetés-tervezési adatokkal végzett munkához. Például egy költségvetés-kezelő exportálhatja egy részleg költségvetési kérelmét az egyik költségvetési tervváltozatból egy Excel munkalapra. Az adatok elemezhetők, frissíthetők, felvázolhatók a munkalapon, majd újra közzétehetők a költségvetési terv soraiban.

## <a name="configuring-budget-planning"></a>A költségvetés-tervezés konfigurálása.
A **Költségvetés-tervezési konfiguráció** lap tartalmazza a legtöbb beállítást a költségvetés-tervezés beállításához. Az alábbiakban olvasható néhány kulcsfontosságú tényezőt ajánlott figyelembe venni a költségvetés-tervezés konfigurálásakor. A konfiguráció befejezése után a költségvetés-tervezési folyamat beállítása következik.

### <a name="create-a-budget-planning-schema"></a>Költségvetés-tervezési sablon létrehozása

Nem kötelező, de ajánlott először létrehozni egy sablont, amely tartalmazza a szervezet eljárását a költségvetés kialakítására. A sablon létrehozásához valamennyi módszert használhatja. A következő ábrán egy általános példát láthat, ahol a szervezet egyes szintjeinek különböző költségvetés-tervezési munkafolyamatai jönnek létre. A szakaszok minden munkafolyamatban előre definiáltak, és minden szakaszhoz egyedi esetet rendelnek a költségvetési adatok fenntartása céljából. Az adatok egyik szakaszról a másikra történő átvitele különböző eljárásokkal történik. Például az összegek lefoglalhatók, vagy összesíthetők a különböző fiókokra, jóváhagyásokra vagy egyéb ellenőrzésekre. Ezen az ábrán dőlttel jeleztünk egy olyan esetet, ami nem szerkeszthető ebben a szakaszban, illetve az előzményadatokat vagy a korábbi szakaszokban elfogadott adatokat, amelyeket emiatt nem szabad módosítani. 

[![Költségvetés-tervezési általános sablon](./media/budgetplanninggenericschema-300x145.png)](./media/budgetplanninggenericschema.png) 

A következő ábrán a vállalati központ megbecsüli a kezdeti költségvetés kiinduló összegeit, és elosztja őket az értékesítési részlegeken. Az értékesítési részleg ezután megbecsüli és elküldi az előrejelzését a központnak, ahol a költségvetés-kezelő összesíti és módosítja az előrejelzést. Végül a költségvetés-kezelő elküldi a módosított költségvetési összegeket a pénzügyi igazgatónak, hogy felülvizsgálja, helyesbítse és jóváhagyja azokat. 

[![Költségvetés-tervezési sablonminta](./media/budgetplanningexampleschema-300x145.png)](./media/budgetplanningexampleschema.png)

###  <a name="organization-hierarchy-for-budget-planning"></a>Szervezeti hierarchia a költségvetés-tervezésre

A **Szervezeti hierarchia** lapon költségvetés-tervezési hierarchiaként megadhat egy szervezeti hierarchiát minden egyes költségvetés-tervezési folyamatra. A költségvetés-tervezési hierarchiának nem kell megegyeznie a más célokra használt szokásos szervezeti hierarchiával. Mivel ezt a hierarchiát az adatok összesítésére és felosztására használjuk, érdemes egy másik szerkezetet létrehozni hozzá. A mintasablonban az értékesítési részleg a központ szintje alatt van a költségvetési és a pénzügyi részleggel együtt. Ennek a szerkezetnek valószínűleg eltér a struktúrája attól, amely az értékesítési részlegek műveleteinek kezelésére használunk. Egy költségvetés-tervezési folyamathoz csak egy szervezeti hierarchia rendelhető. 

További tudnivalókért lásd: [Szervezetek és szervezeti hierarchiák](../../fin-and-ops/organization-administration/organizations-organizational-hierarchies.md).

### <a name="user-security"></a>Felhasználói biztonság

A költségvetés-tervezés két biztonsági modell egyikét követheti a felhasználói engedélyek megadásához. A biztonsági modell kiválasztásához állítsa be a költségvetés-tervezési paramétert a **Költségvetés-tervezési konfiguráció** oldalon.

### <a name="budget-planning-workflows-stages"></a>A költségvetés-tervezési munkafolyamat szakaszai

A költségvetés-tervezési munkafolyamatok a költségvetési munkafolyamatokkal együtt használhatók a költségvetési tervek létrehozására és kezelésére.

A költségvetés-tervezési munkafolyamat egy rendezett szakaszokból álló rendszer, amelyen a költségvetési terv végigmegy. Minden költségvetési munkafolyamathoz tartozik egy költségvetés-tervezési munkafolyamat. A költségvetés-tervezési munkafolyamat az egyik olyan munkafolyamat, amelyet a Finance and Operations használ. A költségvetési terveket a munkalapokkal, indoklásokkal és a mellékletekkel együtt a költségvetési munkafolyamat irányítja a szervezeten keresztül ellenőrzésre és jóváhagyásra. 

Költségvetés-tervezési munkafolyamatot létrehozhat a **Munkafolyamat szakaszai** menüpontban a **Költségvetés-tervezés konfigurációja** lapon. Itt ki tudja választani a program által használt szakaszt és a költségvetési munkafolyamatot, és további beállításokat is hozzáadhat. 

A jó gyakorlat az, ha egy költségvetési hierarchia minden szintjéhez külön költségvetés-tervezési munkafolyamatot hoz létre. Azután olyan költségvetési munkafolyamatot rendel hozzá, melynek elemei megfelelnek a szakaszoknak a költségvetés-tervezési munkafolyamatban. A cikkben szereplő korábbi mintasablonon egy költségvetés-tervezési munkafolyamat szerepelt az értékesítési részleg számára, és egy másik a központ számára. A költségvetési munkafolyamat végigviszi a költségvetési terveket a különböző szakaszokon. 

Költségvetési munkafolyamatot a költségvetés-tervezésre a **Költségvetési munkafolyamatok** oldalon hozhat létre. A folyamat hasonlít más munkafolyamatok létrehozása a Finance and Operations rendszerben. A következő ábrán a Központ munkafolyamatának példája látható. 

[![Költségvetés-tervezési munkafolyamat költségvetés-tervezéshez](./media/budgetingworkflowforbudgetplanning-300x300.png)](./media/budgetingworkflowforbudgetplanning.png) 

A munkafolyamat tartalmazza az értékesítési részleg beadványait, a költségvetés-kezelő helyesbítéseit, a pénzügyi igazgató hozzájárulását, és a szakaszok közötti átmeneteket. 

Költségvetés-tervezési munkafolyamatot az egyes költségvetés-tervezési munkafolyamatokhoz a **Munkafolyamat szakaszai** menüpontban a **Költségvetés-tervezés konfigurációja** lapon jelölhet ki.

### <a name="parameters-scenarios-and-stages"></a>Paraméterek, esetek és szakaszok

A **Költségvetés-tervezési konfiguráció** lapon szereplő alapértelmezett beállítások segítségével készíthet néhány épületblokkot a későbbi konfigurációs lépésekhez:

-   **Paraméterek** – A paraméterek határozzák meg azokat a biztonsági szabályokat, amelyeket a kívánt költségvetési tervekre akar alkalmazni, és az alapértelmezett pénzügyi dimenziókat, amelyeket akkor kell használni, amikor a felhasználók a költségvetési terv eseti összegeit részletezik.
-   **Esetek** – Az esetek a költségvetési tervekhez kívánt adatok kategóriáit tartalmazzák. A költségvetési tervváltozatok meghatározásával a monetáris és egyéb egységosztályokat, például a mennyiséget támogatja. A költségvetési tervben az esetek a költségvetés-tervezési adatok egy-egy verzióját jelentik. Példa a költségvetési tervváltozatokra: a Részleg előző éve, illetve az Aláírt szerződések. Az eladási mennyiségek, illetve a teljes munkaidőssel egyenértékű (FTE) alkalmazottak száma olyan esetpéldák, melyek mennyiségeket használnak.
-   **Szakaszok** – A szakaszok határozzák meg azokat a lépéseket, amelyeket a költségvetési terv követ a kezdetektől a végleges jóváhagyásig. A költségvetés-tervezési szakaszokra példa a központi összesítés, a pénzügyi igazgató ellenőrzése és a végleges változat.

### <a name="allocation-schedules"></a>Felosztási ütemezések

A költségvetés-tervezés során feloszthatja a költségvetési terv sorainak összegeit vagy mennyiségeit az egyik lehetséges esetből egy másikba, vagy akár ugyanabba az esetbe. Például feloszthatja ugyanazt az esetet, ha alkalmazni akarja a változtatásokat a pénzügyi dimenziókra vagy az összegek időpontjaira egy másik esetben. A felosztás történhet egy költségvetési terven belül vagy egy költségvetési tervből a másikba. 

A felosztási ütemezések automatikusan felosztják a költségvetési terv sorait a munkafolyamat feldolgozása során. A **Felosztási módszer** listán szereplő bármely módszerrel végezhet felosztásokat:

-   **Időszaki felosztás** – A költségvetési terv sorait a költségvetési forrás tervváltozatából időszaki felosztókulcs segítségével oszthatja fel a célváltozat pénzügyi időszakai között. **Megjegyzés**: Mielőtt időszakok közötti felosztást végez, azelőtt be kell állítania az időszaki felosztási kulcsokat az ****Időszak-felosztási kategóriák**** oldalon.
-   **Dimenziókra való felosztás** – A költségvetési terv sorai a költségvetési forrás tervváltozatából a célváltozat pénzügyi dimenziói között kerülnek felosztásra. **Megjegyzés**: Mielőtt elvégezné a dimenziókra való felosztást, be kell állítania a költségvetés-felosztási feltételeket a ****Költségvetés-felosztási feltételek**** oldalon.
-   **Összesítés** – A költségvetési terv sorai a szülő költségvetési terv költségvetési forrás tervváltozatából a társított költségvetési terv célváltozatában kerülnek összesítésre.
-   **Felosztás** – A költségvetési terv sorai a szülő költségvetési terv költségvetési forrás tervváltozatából a társított költségvetési terv célváltozatába kerülnek felosztásra.
-   **Főkönyvi felosztási szabályok használata** – A költségvetési terv sorai a forrás költségvetési tervváltozat soraiból a kiválasztott főkönyvi felosztásszabály alapján a cél költségvetési tervváltozatba kerülnek felosztásra.
-   **Másolás költségvetési tervből** – A felosztás forrásaként kiválaszthat egy másik költségvetési tervet.

### <a name="stage-allocations"></a>Szakaszok felosztásai.

A szakaszok felosztásait arra használjuk, hogy automatikusan felosszuk a költségvetési terv sorait a munkafolyamat feldolgozása során. Amikor szakaszfelosztásokat használunk, a célváltozat költségvetési terv sorait létrehozhatjuk és módosíthatjuk a költségvetési terv készítőjének vagy ellenőrének beavatkozása nélkül.

Szakaszfelosztás beállításakor társítsa a költségvetés-tervezési munkafolyamatot és a szakaszt a felosztási ütemezéssel. A költségvetés-tervezési munkafolyamatot társítani kell egy, a ****Költségvetés-tervezési szakasz felosztása**** automatizált munkafolyamatot használó költségvetési munkafolyamattal. Ha a munkafolyamat eléri a megadott szakaszt, a felosztás automatikusan megtörténik. Ez az automatizált feladat egy új változat költségvetési terv-sorainak létrehozására használható. 

A mintasablonban, amely a cikk korábbi részében szerepelt, egy felosztás végrehajtása szerepel összegek átvitelére a költségvetési tervből és tervváltozatokból a központ kiindulási szakaszában egy másik költségvetési tervbe és tervváltozatba az Értékesítési részleg Becslési szakaszában. A következő ábrán a mintasablon idevágó szakasza látható.

[![Felosztási szakasz](./media/stageallocation-204x300.png)](./media/stageallocation.png) 

Emellett a mintasablonban a költségvetési tervekből és tervváltozatokból aggregációt hajtottunk végre az értékesítési részlegen az Előterjesztési szakaszban egy szülő tervre a központ összesítő szakaszában. A következő ábrán a mintasablon idevágó szakasza látható.

[![Összesítés](./media/aggregation-109x300.png)](./media/aggregation.png)

### <a name="priorities"></a>Prioritások

A költségvetési terv prioritásai segítségével meghatározhat kategóriákat és célkitűzéseket a költségvetési tervekhez, amelyeket beállított. A prioritások bizonyos költségvetési tervek rendezéséhez, osztályozásához és kiértékeléséhez is használhatók. Például létrehozhat egy költségvetés-tervezési prioritást az egészség és biztonság témakörében, majd kiértékelheti azokat a költségvetési terveket, melyek ehhez a prioritáshoz vannak hozzárendelve. A költségvetési tervekhez az összes költségvetési tervhez viszonyított sorszámot is rendelhet.

### <a name="columns-and-layouts"></a>Oszlopok és elrendezések

A költségvetési számadatok sorokban és oszlopokban jelennek meg a költségvetési tervben. Először definiálni kell az oszlopokat, és ezután létrehozhat egy elrendezést az oszlopok megjelenésének meghatározásához. 

Egy oszlop meghatározásához jelölje be a költségvetési tervváltozatot. A tervváltozat sorainak száma a költségvetési tervben látszik. Kiválaszthatja a kívánt időszakot, ami alapján szűrni szeretné az összeget, és a főkönyvi számlán alapuló szűrők is alkalmazhatók. 

Az elrendezés meghatározásakor jelöljön ki egy főkönyvi dimenziót a megjeleníteni kívánt költségvetési terv sorainak létrehozásához, majd válassza ki az oszlopokat elrendezési elemként. Több elrendezést is létrehozhat, hogy a költségvetés-tervezési folyamat különböző szakaszaiban a költségvetési terv a kívánt értékét mutassa. 

A költségvetés összege oszlopon kívül a projekt, a javasolt projekt, a tárgyi eszköz és a költségvetési terv javasolt eszköze mezőket is be lehet állítani a költségvetési tervből. Megadhat egy oszlopot a tervezett beosztásoknak is. Ez a lehetőség nagyon hasznos, ha elemeznie kell a személyzeti költségvetést. 

A mintasablon szerint előfordulhat, hogy oszlopokat szeretne létrehozni az értékesítési, a szerződési és az előrejelzési tervváltozatokhoz (a következő ábra a sablon megfelelő szakaszát ábrázolja). Ezután különböző oszlopokra bonthatja az egyik vagy az összes tervváltozatot a pénzügyi év minden negyedévére, ezáltal az értékesítési részleg vezetője pontosan megadhatja az előrejelzett összegeket az egyes időszakokra vonatkozóan.

[![Oszlopok](./media/columns.png)](./media/columns.png) 

Kijelölheti azt is, hogy szerkeszthető-e minden elrendezési elem (oszlop), és hogy elérhető-e minden munkalapsablonon, amelyet ehhez az elrendezéshez hoztak létre. A mintasablon szerint a becslési szakaszhoz használt elrendezésben az előrejelzés oszlopai szerkeszthetők, míg a PY értékesítések és a szerződések oszlopok írásvédettek.

### <a name="templates"></a>Sablonok

A **Költségvetés-tervezési konfiguráció** lap **Elrendezések** szakaszán Excel sablonokat tud létrehozni, megjeleníteni vagy feltölteni. Ezek a sablonok azok a munkafüzetek, amelyek az egyes költségvetési tervekhez vannak társítva további elemzések megadása, diagramkészítési és adatbeviteli képességek céljából. 

Létrehozhat, megjeleníthet vagy feltölthet sablont az egyes elrendezésekhez. Sablon létrehozásakor az elrendezés zárolva van, ezért nem szerkeszthető. A zárolás segítségével garantálható, hogy a sablon formátuma megfelel a költségvetési terv elrendezésének, és ugyanazokat az adatokat tartalmazza. Miután létrehozta a sablont, már megtekinthető, illetve szerkeszthető. Például hozzáadhat diagramokat a sablonhoz, vagy testreszabhatja a megjelenését.

> [!NOTE] 
> A sablont olyan helyre kell menteni, amelyhez a felhasználó hozzáférhet, így feltölthető az elrendezések közé a szerkesztés befejezése után. Így a sablont azzal a költségvetési tervvel használjuk, amely az elrendezést használja.

### <a name="descriptions"></a>Leírások

Az **Elrendezések** szakaszban hozzárendelhető leírások használatával meg lehet jeleníteni az elrendezésben szereplő pénzügyi dimenzió nevét. Például egy szervezet lehet, hogy meg akarja jeleníteni a fő számla nevét a fő számla száma mellett a költségvetési tervben, viszont lehet, hogy más pénzügyi dimenziók nevét el szeretné rejteni a megjelenés rendezetlenségének elkerülése érdekében.

## <a name="setting-up-budget-planning-processes"></a>Költségvetés-tervezési folyamatok beállítása

Miután befejezte a költségvetés-tervezés konfigurálását, beállíthat költségvetés-tervezési folyamatokat a **Költségvetés-tervezési folyamat** oldalon. A költségvetés-tervezési folyamatok határozzák meg, hogy a költségvetési tervek hogyan frissíthetők, küldhetők tovább, ellenőrizhetők és hagyhatók jóvá a költségvetési szervezet hierarchiájában. 

Az egyes költségvetés-tervezési folyamatokhoz válassza ki a használni kívánt költségvetési ciklust és a főkönyvet. Minden költségvetés-tervezési folyamathoz csak egy költségvetési ciklus és egy főkönyv kapcsolódik. A költségvetés-szervezeti hierarchia **Költségvetés-tervezési folyamat felügyelete** gyorslapon történő kiválasztása után hozzá kell rendelnie a rácsban megjelenő összes szervezeti felelősségközponthoz egy költségvetés-tervezési munkafolyamatot. 

Ha hasonló felelősségközpontokhoz szeretne költségvetés-tervezési munkafolyamatot hozzárendelni vagy azt módosítani, kattintson a **Munkafolyamat hozzárendelése** elemre, és válassza ki a cél szervezet típusát és a használandó költségvetés-tervezési munkafolyamatot. A költségvetés-tervezési munkafolyamat-azonosító, amely minden egyes költségvetés-tervezési munkafolyamattal társítva van, automatikusan hozzáadódik a rácshoz. 

Amikor a **Költségvetés-tervezési szakaszok szabályai és elrendezései** gyorslapon szakaszokra vonatkozó szabályokat és sablonokat ad meg, minden egyes költségvetés-tervezési szakaszra más szabályt és sablont definiálhat. Például az értékesítési részleg becslési szakasza lehetővé teheti, hogy a felhasználók módosítani tudják a sorokat a költségvetési tervben, de megtiltja a sorok hozzáadását. Az előterjesztett szakasz lehetővé teszi, hogy a felhasználók megtekintsék a sorokat, mivel a munka abban a szakaszban befejeződött, és a költségvetési tervek módosításait meg kell akadályozni. A költségvetési tervekhez rendelkezésre álló elrendezések kiválasztásához kattintson a **Alternatív elrendezések** linkre. 

A költségvetés-tervezési prioritásokat választhatóan kijelölheti a **Költségvetésiterv-prioritás megszorításai** gyorslapon. Ezután a költségvetési tervekhez prioritásokat választhat ki. 

Az utolsó lépés a költségvetés-tervezési folyamat aktiválása a **Műveletek** menü segítségével A költségvetés-tervezési folyamatot nem lehet használni addig, amíg nem lett aktiválva. 

A **Műveletek** menüben egy létező folyamat másolásával is létrehozhat új folyamatot. Ez a funkció az olyan szervezeteknek hasznos, amelyek minden költségvetési ciklusban ugyanazokat a folyamatokat követik néhány módosítással vagy módosítások nélkül. 

Egy másik hasznos parancs a **Műveletek** menüben a **Költségvetési folyamat állapotának megtekintése** link. Ez a parancs grafikus formában jeleníti meg a költségvetési terveket egy folyamat során a megfelelő adatokkal együtt, mint például a tervek munkafolyamat-állapota, összeg és egység szerinti összesítések, és egy kattintással elérhető navigáció a költségvetési tervekhez.

[![Költségvetés-tervezési folyamat állapota](./media/budgetplanningprocessstatus-300x171.png)](./media/budgetplanningprocessstatus.png)




