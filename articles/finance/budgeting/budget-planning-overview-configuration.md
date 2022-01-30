---
title: Költségvetés-tervezés áttekintése
description: Ez a témakör bemutatja a költségvetés-tervezést. Olyan információt közöl, mely a költségvetés-tervezés konfigurálásához és a költségvetés-tervezési folyamatok beállításához nyújt segítséget.
author: panolte
ms.date: 01/11/2018
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "17251"
- intro-internal
ms.assetid: a2e06633-a800-4840-a962-88fed8462104
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 391f62f42e482f79420bbe1bbd4cec4930790229
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982065"
---
# <a name="budget-planning-overview"></a>Költségvetés-tervezés áttekintése

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja a költségvetés-tervezést. Olyan információt közöl, mely a költségvetés-tervezés konfigurálásához és a költségvetés-tervezési folyamatok beállításához nyújt segítséget.

## <a name="overview-of-budget-planning"></a>A költségvetés-tervezés áttekintése

Egy szervezet konfigurálhatja a költségvetés-tervezését, és beállíthat olyan költségvetés-tervezési folyamatokat, amelyek célja a szervezet irányelveiknek, eljárás-rendjeiknek és a költségvetési előkészítés követelményeinek való megfelelés. Ha megérti a Microsoft Dynamics 365 Finance rendszerben használt fogalmakat és terminológiát, könnyebben és hatékonyabban valósíthatja meg a szervezet költségvetés-tervezését.

### <a name="key-terms"></a>Kulcsfogalmak

- **Költségvetés-tervezési folyamatok** – A költségvetés-tervezési folyamatok határozzák meg, hogy a költségvetési tervek hogyan frissíthetők, küldhetők tovább, ellenőrizhetők és hagyhatók jóvá a költségvetési szervezet hierarchiájában. A költségvetés-tervezési folyamat a költségvetési ciklushoz és a szervezethez egy jogi személyen keresztül kapcsolódik.
- **Költségvetési tervek** – A költségvetési tervek a költségvetési ciklushoz tartozó költségvetési adatokat tartalmazzák. Több költségvetési tervvel is rendelkezhet, amelyeket különféle célokra használhat. A költségvetési tervek segítségével például a különböző szervezeti egységek költségvetési összegeit lehet létrehozni. Ezek segítségével összehasonlításokat végezhet, és tájékozott döntéseket hozhat.
- **Költségvetési tervváltozatok** – A költségvetési tervváltozatok határozzák meg a költségvetési tervekhez tartozó adatok csoportjait. A költségvetési tervváltozatok meghatározásával a monetáris osztályokat és egyéb egységosztályokat, például a mennyiséget támogatja. Példa a költségvetési tervváltozatokra: a „Részleg előző éve”, illetve a „Részleg igénylései”. Példa a költségvetési terv tervváltozataira: az „Előző évi támogatási hívások”, illetve a „Teljes munkaidőssel egyenértékű (FTE) alkalmazottak száma”.
- **Költségvetés-tervezési szakaszok** – A költségvetés-tervezési szakaszok határozzák meg a költségvetési terv lépéseit a kezdetektől a végleges jóváhagyásig. A költségvetés-tervezési szakaszok költségvetés-tervezési munkafolyamatokba vannak szervezve.
- **Költségvetés-tervezési munkafolyamatok** – A költségvetés-tervezési munkafolyamatok a költségvetés-tervezési szakaszok megadásából állnak. A költségvetés-tervezési munkafolyamatokhoz a költségvetés-készítési munkafolyamatok tartoznak. A költségvetés-tervezési munkafolyamatok olyan automatizált és manuális eljárások, amelyek a költségvetési terveket átviszik a költségvetés-tervezési szakaszokon.

[![Költségvetés-tervezési terminológia.](./media/budgetplanning-terms-1024x504.png)](./media/budgetplanning-terms.png)

### <a name="typical-tasks"></a>Jellemző feladatok

Az Emberi erőforrások modullal a következők végezhetők el:

- Létrehozhat költségvetési terveket, hogy meghatározza a várható bevételt és kiadásokat egy költségvetési ciklushoz.
- Elemezheti és frissítheti a költségvetési terveket különböző tervváltozatok használatával.
- Automatikusan elküldheti ellenőrzésre és jóváhagyásra a költségvetési terveket a munkalapokkal, az indoklásokkal és a mellékletekkel együtt.
- Egyesíthet több költségvetési tervet a szervezet alacsonyabb szintjéről egy magasabb szintű költségvetési tervbe. Létrehozhat egy magasabb szintű egy költségvetési tervet a szervezetben, és eloszthatja a költségvetést az alacsonyabb szinteken.

A Költségvetés-tervezés integrálva van más modulokkal. Ezért az előző költségvetések, a tényleges kiadások, a tárgyi eszközök és az emberi erőforrások adatait is felhasználhatja. Mivel költségvetés-tervezés integráltan jelen van a Microsoft Excel és a Microsoft Word programokban is, így ezen programok segítségét is felhasználhatja a költségvetés-tervezési adatokkal végzett munkához. Például egy költségvetés-kezelő exportálhatja egy részleg költségvetési kérelmét az egyik költségvetési tervváltozatból egy Excel munkalapra. Az adatok ezután elemezhetők, frissíthetők, felvázolhatók a munkalapon, majd újra közzétehetők a költségvetési terv soraiban.

## <a name="configuring-budget-planning"></a>A költségvetés-tervezés konfigurálása.

A Dynamics 365 Finance 10.0.9-es verziójában (2020. április) bemutatott funkcióhoz tartozik egy funkció, amellyel javítható a teljesítmény, amikor a **Közzététel** gomb segítségével frissít meglévő rekordokat az Excelben, majd közzéteszi őket az ügyfélnek. Ez a funkció felgyorsítja a frissítési folyamatot, és csökkenti a frissítés blokkolásának valószínűségét, ha egyszerre több rekordot frissít. A funkció elérhetővé tételéhez nyissa meg a **Funkciókezelés** munkaterületet, és kapcsolja be a **Költségvetéstervezési lekérdezés optimalizálása a teljesítmény érdekében** funkciónál a **Költségvetés** modulban. Javasoljuk, hogy kapcsolja be ezt a funkciót.

A **Költségvetés-tervezési konfiguráció** lap tartalmazza a legtöbb kötelező beállítást a költségvetés-tervezés beállításához. Az alábbiakban olvasható néhány kulcsfontosságú tényezőt ajánlott figyelembe venni a költségvetés-tervezés konfigurálásakor. A konfiguráció befejezése után a költségvetés-tervezési folyamat beállítása következik.

### <a name="budget-planning-schema-optional"></a>Költségvetés-tervezési sablon (nem kötelező)

Nem kötelező, de ajánlott először létrehozni egy sablont, amely tartalmazza a szervezet eljárását a költségvetés kialakítására. A sablon létrehozásához valamennyi módszert használhatja.

A következő ábrán egy általános példát láthat, ahol a szervezet egyes szintjeinek különböző költségvetés-tervezési munkafolyamatai jönnek létre. A szakaszok minden munkafolyamatban előre definiáltak, és minden szakaszhoz egyedi tervváltozatot rendelnek a költségvetési adatok fenntartása céljából. Az adatok egyik szakaszról a másikra történő átvitele különböző eljárásokkal történik. Például az összegek lefoglalhatók, vagy összesíthetők a különböző fiókokra, jóváhagyásokra vagy egyéb ellenőrzésekre. Ezen az ábrán dőlttel jeleztünk egy olyan tervváltozatot, ami nem szerkeszthető ebben a szakaszban, illetve az előzményadatokat vagy a korábbi szakaszokban elfogadott adatokat, amelyeket emiatt nem szabad módosítani.

[![Költségvetés-tervezési általános sablon.](./media/budgetplanninggenericschema-300x145.png)](./media/budgetplanninggenericschema.png) 

A következő ábrán látható példán a vállalati központ megbecsüli a kezdeti költségvetés kiinduló összegeit, és elosztja őket az értékesítési részlegeken. Az Értékesítési részleg ezután megbecsüli és elküldi az előrejelzését a központnak, ahol a költségvetés-kezelő összesíti és módosítja az előrejelzést. Végül a költségvetés-kezelő elküldi a módosított költségvetési összegeket a pénzügyi igazgatónak (CFO), hogy felülvizsgálja, helyesbítse és jóváhagyja azokat.

[![Költségvetés-tervezési sablonminta.](./media/budgetplanningexampleschema-300x145.png)](./media/budgetplanningexampleschema.png)

### <a name="organization-hierarchy-for-budget-planning"></a>Szervezeti hierarchia a költségvetés-tervezésre

A **Szervezeti hierarchia** lapon költségvetés-tervezési hierarchiaként megadhat egy szervezeti hierarchiát minden egyes költségvetés-tervezési folyamatra. A költségvetés-tervezési hierarchiának nem kell megegyeznie a más célokra használt szokásos szervezeti hierarchiával. Mivel ezt a hierarchiát az adatok összesítésére és felosztására használjuk, érdemes egy másik szerkezetet létrehozni hozzá. A mintasablonban az értékesítési részleg a központ szintje alatt van a költségvetési és a pénzügyi részleggel együtt. Ennek a szerkezetnek valószínűleg eltér a struktúrája attól, amely az értékesítési részlegek műveleteinek kezelésére használunk. Egy költségvetés-tervezési folyamathoz csak egy szervezeti hierarchia rendelhető.

További tudnivalókért lásd: [Szervezetek és szervezeti hierarchiák](../../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md).

### <a name="user-security"></a>Felhasználói biztonság

A költségvetés-tervezés két biztonsági modell egyikét követheti a felhasználói engedélyek megadásához. A biztonsági modell kiválasztásához állítsa be a költségvetés-tervezési paramétert a **Költségvetés-tervezési konfiguráció** oldalon.

### <a name="budget-planning-workflows-stages"></a>A költségvetés-tervezési munkafolyamat szakaszai

A költségvetés-tervezési munkafolyamatok a költségvetési munkafolyamatokkal együtt használhatók a költségvetési tervek létrehozására és kezelésére.

A költségvetés-tervezési munkafolyamat egy rendezett szakaszokból álló rendszer, amelyen a költségvetési terv végigmegy. Minden költségvetési munkafolyamathoz tartozik egy költségvetés-tervezési munkafolyamat. A költségvetés-tervezési munkafolyamat az egyik olyan munkafolyamat, amelyet a Dynamics 365 Finance használ. A munkalapokkal, indoklásokkal és a mellékletekkel együtt a költségvetési munkafolyamatot irányítja a szervezeten keresztül ellenőrzésre és jóváhagyásra.

Költségvetés-tervezési munkafolyamatot létrehozhat a **Munkafolyamat szakaszai** menüpontban a **Költségvetés-tervezés konfigurációja** lapon. Itt ki tudja választani a program által használt szakaszt és a költségvetési munkafolyamatot, és további beállításokat is hozzáadhat.

A jó gyakorlat az, ha egy költségvetési hierarchia minden szintjéhez külön költségvetés-tervezési munkafolyamatot hoz létre. Azután olyan költségvetési munkafolyamatot rendel hozzá, melynek elemei megfelelnek a szakaszoknak a költségvetés-tervezési munkafolyamatban. A témakörben szereplő korábbi mintasablonon egy költségvetés-tervezési munkafolyamat hozható létre az értékesítési részleg számára, és egy másik a központ számára. A költségvetési munkafolyamat végigviszi a költségvetési terveket a különböző szakaszokon.

Költségvetési munkafolyamatot a költségvetés-tervezésre a **Költségvetési munkafolyamatok** oldalon hozhat létre. A folyamat hasonlít más munkafolyamatok létrehozásához. A következő ábrán a Központ munkafolyamatának példája látható.

[![Költségvetés-tervezési munkafolyamat költségvetés-tervezéshez.](./media/budgetingworkflowforbudgetplanning-300x300.png)](./media/budgetingworkflowforbudgetplanning.png) 

A munkafolyamat a következő elemeket tartalmazza:

- Felosztás az értékesítési részlegek számára és a beküldéseik összesítése
- Költségvetés-kezelői felülvizsgálat
- CFO jóváhagyása
- Fokozatos átmenetek a költségvetés-tervezési munkafolyamat egyes fázisai között

Költségvetés-tervezési munkafolyamatot az egyes költségvetés-tervezési munkafolyamatokhoz a **Munkafolyamat szakaszai** menüpontban a **Költségvetés-tervezés konfigurációja** lapon jelölhet ki.

### <a name="parameters-scenarios-and-stages"></a>Paraméterek, esetek és szakaszok

A **Költségvetés-tervezési konfiguráció** lapon szereplő alapértelmezett beállítások segítségével készíthet néhány épületblokkot a későbbi konfigurációs lépésekhez:

- **Paraméterek** – A paraméterek határozzák meg azokat a biztonsági szabályokat, amelyeket a kívánt költségvetési tervekre akar alkalmazni, és az alapértelmezett pénzügyi dimenziókat, amelyeket akkor kell használni, amikor a felhasználók a költségvetési terv tervváltozataiban az összegeket részletezik.
- **Esetek** – Az esetek a költségvetési tervekhez kívánt adatok kategóriáit tartalmazzák. A költségvetési tervváltozatok meghatározásával a monetáris osztályokat és egyéb egységosztályokat, például a mennyiséget támogatja. A költségvetési tervben az esetek a költségvetés-tervezési adatok egy-egy verzióját jelentik. Példa a költségvetési tervváltozatokra: a „Előző évi értékesítések”, illetve az „Aláírt szerződések”. Az „Értékesítési hívások száma”, illetve a „Teljes munkaidőssel egyenértékű (FTE) alkalmazottak száma” olyan tervváltozatpéldák, melyek mennyiségeket használnak.
- **Szakaszok** – A szakaszok határozzák meg azokat a lépéseket, amelyeket a költségvetési terv követ a kezdetektől a végleges jóváhagyásig. A költségvetés-tervezési szakaszokra példa a „Központi összesítés”, a „Pénzügyi igazgató ellenőrzése” és a „végleges változat”.

### <a name="allocation-schedules"></a>Felosztási ütemezések

A költségvetés-tervezés során feloszthatja a költségvetési terv sorainak összegeit vagy mennyiségeit az egyik lehetséges esetből egy másikba, vagy akár ugyanabba az esetbe. Például feloszthat összegeket vagy mennyiségeket ugyanahhoz az tervváltozathoz, ha módosításokat szeretne végezni a pénzügyi dimenziókban vagy az adott tervváltozat összegeinek dátumain. A felosztás történhet egy költségvetési terven belül vagy egy költségvetési tervből a másikba.

A felosztási ütemezések automatikusan felosztják a költségvetési terv sorait a munkafolyamat feldolgozása során. A **Felosztási módszer** listán szereplő bármely módszerrel végezhet felosztásokat:

- **Időszaki felosztás** – A költségvetési terv sorait a költségvetési forrás tervváltozatából időszaki felosztókulcs segítségével oszthatja fel a célváltozat pénzügyi időszakai között.

    > [!NOTE]
    > Mielőtt időszakok közötti felosztást végez, azelőtt be kell állítania az időszaki felosztási kulcsokat **Időszak-felosztási kategóriák** oldalon.

- **Dimenziókra való felosztás** – A költségvetési terv sorai a költségvetési forrás tervváltozatából a célváltozat pénzügyi dimenziói között kerülnek felosztásra.

    > [!NOTE]
    > Mielőtt elvégezné a dimenziókra való felosztást, be kell állítania a költségvetés-felosztási feltételeket a **Költségvetés-felosztási feltételek** oldalon.

- **Összesítés** – A költségvetési terv sorai a szülő költségvetési terv költségvetési forrás tervváltozatából a társított költségvetési terv célváltozatában kerülnek összesítésre.
- **Felosztás** – A költségvetési terv sorai a szülő költségvetési terv költségvetési forrás tervváltozatából a társított költségvetési terv célváltozatába kerülnek felosztásra.
- **Főkönyvi felosztási szabályok használata** – A költségvetési terv sorai a forrás költségvetési tervváltozat soraiból a kiválasztott főkönyvi felosztásszabály alapján a cél költségvetési tervváltozatba kerülnek felosztásra.
- **Másolás költségvetési tervből** – A felosztás forrásaként kiválaszthat egy másik költségvetési tervet.

### <a name="stage-allocations"></a>Szakaszok felosztásai.

A szakaszok felosztásait arra használjuk, hogy automatikusan felosszuk a költségvetési terv sorait a munkafolyamat feldolgozása során. Amikor szakaszfelosztásokat használunk, a céltervváltozat költségvetési tervsorait létrehozhatjuk és módosíthatjuk a költségvetési terv készítőjének vagy ellenőrének beavatkozása nélkül.

Szakaszfelosztás beállításakor társítsa a költségvetés-tervezési munkafolyamatot és a szakaszt a felosztási ütemezéssel. A költségvetés-tervezési munkafolyamatot társítani kell egy, a **Költségvetés-tervezési szakasz felosztása** automatizált munkafolyamatot használó költségvetési munkafolyamattal. Ha a munkafolyamat eléri a megadott szakaszt, a felosztás automatikusan megtörténik. Ez az automatizált feladat egy új változat költségvetési terv-sorainak létrehozására használható.

A mintasablonban, amely a témakör korábbi részében szerepelt, egy felosztás végrehajtása szerepel összegek átvitelére a költségvetési tervből és tervváltozatokból a központ „kiindulási” szakaszában egy másik költségvetési tervbe és tervváltozatba az Értékesítési részlegek „Becslési” szakaszában. A következő ábrán a mintasablon idevágó szakasza látható.

[![Felosztási szakasz.](./media/stageallocation-204x300.png)](./media/stageallocation.png) 

Emellett a mintasablonban az „Elküldött” fázisban lévő költségvetési tervekből és tervváltozatokból aggregációt hajtottunk végre az értékesítési részlegek számára egy „Összesítés” szakaszban lévő fölérendelt tervre vonatkozóan a központnak. A következő ábrán a mintasablon idevágó szakasza látható.

[![Összesítés.](./media/aggregation-109x300.png)](./media/aggregation.png)

### <a name="priorities"></a>Prioritások

A költségvetési terv prioritásai segítségével meghatározhat kategóriákat és célkitűzéseket a költségvetési tervekhez, amelyeket beállított. A prioritások bizonyos költségvetési tervek rendezéséhez, osztályozásához és kiértékeléséhez is használhatók. Például létrehozhat egy költségvetés-tervezési prioritást az egészség és biztonság témakörében, majd kiértékelheti azokat a költségvetési terveket, melyek ehhez a prioritáshoz vannak hozzárendelve. A költségvetési tervehez számot is rendelhet, amellyel a sorrendet jelezheti.

### <a name="columns-and-layouts"></a>Oszlopok és elrendezések

A költségvetési számadatok sorokban és oszlopokban jelennek meg a költségvetési tervben. Először definiálni kell az oszlopokat, és ezután létrehozhat egy elrendezést az oszlopok megjelenésének meghatározásához.

Egy oszlop meghatározásához jelölje be a költségvetési tervváltozatot. A tervváltozat sorainak száma a költségvetési tervben látszik. Kiválaszthatja a kívánt időszakot, ami alapján szűrni szeretné az összeget, és a főkönyvi számlán alapuló szűrők is alkalmazhatók.

Az elrendezés meghatározásakor jelöljön ki egy főkönyvi dimenziót a megjeleníteni kívánt költségvetési terv sorainak létrehozásához, majd válassza ki az oszlopokat elrendezési elemként. Több elrendezést is létrehozhat, hogy a költségvetés-tervezési folyamat különböző szakaszaiban a költségvetési terv a kívánt adatokat mutassa.

A költségvetés összege oszlopon kívül a projekt, a javasolt projekt, a tárgyi eszköz és a költségvetési terv javasolt eszköze mezőket is be lehet állítani a költségvetési tervből. Megadhat egy oszlopot a tervezett beosztásoknak is. Ez a lehetőség akkor hasznos, ha elemeznie kell a személyzeti költségvetést.

A példasémához ajánlott az „előző évi értékesítés”, „Szerződések” és „Előrejelzés” tervváltozatokhoz oszlopokat létrehozni. (A következő ábra a séma releváns részét mutatja.) Ezután különböző oszlopokra bonthatja az egyik vagy az összes tervváltozatot a pénzügyi év minden negyedévére, ezáltal az értékesítési részleg vezetője pontosan megadhatja az előrejelzett összegeket az egyes időszakokra vonatkozóan.

[![Az oszlopok hozzáadási séma szakaszainak ábrája.](./media/columns.png)](./media/columns.png)

Megadhatja azt is, hogy szerkeszthető-e minden elrendezési elem (oszlop), és hogy elérhető-e minden munkalapsablonon, amelyet ehhez az elrendezéshez hoztak létre. A mintasablonnál a „Becslés” szakaszhoz használt elrendezésben az „előrejelzés” oszlopai szerkeszthetők, míg az „előző évi értékesítések” és a „szerződések” oszlopok írásvédettek.

> [!NOTE]
> Alapértelmezés szerint ez a 36 oszlopra lesz korlátozva, hacsak nem bővíti a költségvetéstervezést a [Költségvetési terv kiterjesztése](./extending-budget-planning-layout.md) helyen leírt lépésekkel.

### <a name="templates"></a>Sablonok

A **Költségvetés-tervezési konfiguráció** lap **Elrendezések** szakaszán az egyes elrendezésekhez Excel sablonokat tud létrehozni, megjeleníteni vagy feltölteni. Ezek a sablonok azok a munkafüzetek, amelyek az egyes költségvetési tervekhez vannak társítva további elemzések megadása, diagramkészítési és adatbeviteli képességek céljából.

Sablon létrehozásakor az elrendezés zárolva van, ezért nem szerkeszthető. A zárolás segítségével biztosítható, hogy a sablon formátuma megfelel a költségvetési terv elrendezésének, és ugyanazokat az adatokat tartalmazza. Miután létrehozta a sablont, már megtekinthető, illetve szerkeszthető. Például hozzáadhat diagramokat a sablonhoz, vagy testreszabhatja a megjelenését.

> [!NOTE]
> A sablont olyan helyre kell menteni, amelyhez a felhasználó hozzáférhet, így feltölthető az elrendezések közé a szerkesztés befejezése után. Így a sablont azzal a költségvetési tervvel használjuk, amely az elrendezést használja.

### <a name="descriptions"></a>Leírások

Az **Elrendezések** szakaszban hozzárendelhető leírások használatával meg lehet jeleníteni az elrendezésben szereplő pénzügyi dimenzió nevét. Előfordulhat például, hogy egy szervezet meg szeretné jeleníteni a fő számla nevét a költségvetési terv fő számlaszáma mellett. Előfordulhat azonban, hogy ki szeretné hagyni a többi pénzügyi dimenzió nevét, hogy elkerülje a megjelenítés zsúfoltságát.

## <a name="setting-up-budget-planning-processes"></a>Költségvetés-tervezési folyamatok beállítása

Miután befejezte a költségvetés-tervezés konfigurálását, beállíthat költségvetés-tervezési folyamatokat a **Költségvetés-tervezési folyamat** oldalon. A költségvetés-tervezési folyamatok határozzák meg, hogy a költségvetési tervek hogyan frissíthetők, küldhetők tovább, ellenőrizhetők és hagyhatók jóvá a költségvetési szervezet hierarchiájában.

Az egyes költségvetés-tervezési folyamatokhoz válassza ki a használni kívánt költségvetési ciklust és a főkönyvet. Minden költségvetés-tervezési folyamathoz csak egy költségvetési ciklus és egy főkönyv kapcsolódik. Ezután a költségvetés-szervezeti hierarchiát válassza ki a **Költségvetés-tervezési folyamat felügyelete** gyorslapon, és hozzá kell rendelnie a rácsban megjelenő összes szervezeti felelősségközponthoz egy költségvetés-tervezési munkafolyamatot.

Ha hasonló felelősségközpontokhoz szeretne költségvetés-tervezési munkafolyamatot hozzárendelni vagy azt módosítani, kattintson a **Munkafolyamat hozzárendelése** elemre, és válassza ki a cél szervezet típusát és a használandó költségvetés-tervezési munkafolyamatot. A költségvetés-tervezési munkafolyamat-azonosító, amely minden egyes költségvetés-tervezési munkafolyamattal társítva van, automatikusan hozzáadódik a rácshoz.

Amikor a **Költségvetés-tervezési szakaszok szabályai és elrendezései** gyorslapon szakaszokra vonatkozó szabályokat és sablonokat ad meg, minden egyes költségvetés-tervezési szakaszra más szabályt és sablont definiálhat. Például az értékesítési részlegek „Becslés” szakasza lehetővé teheti, hogy a felhasználók módosítani tudják a sorokat a költségvetési tervben, de megtiltja a sorok hozzáadását. Az „Elküldött” szakasz lehetővé teszi, hogy a felhasználók megtekintsék a sorokat, mivel a munka abban a szakaszban befejeződött, és a költségvetési tervek módosításait meg kell akadályozni. A költségvetési tervekhez rendelkezésre álló elrendezések kiválasztásához kattintson a **Alternatív elrendezések** linkre.

A költségvetés-tervezési prioritásokat választhatóan kijelölheti a **Költségvetésiterv-prioritás megszorításai** gyorslapon. Ezután a költségvetési tervekhez prioritásokat választhat ki.

Az utolsó lépés az, hogy aktiválja a költségvetés-tervezési folyamatot a **műveletek** menü segítségével. A költségvetés-tervezési folyamat addig nem használható, amíg nem aktiválták.

A **Műveletek** menü segítségével egy létező folyamat másolásával is létrehozhat új folyamatot. Ez a funkció az olyan szervezeteknek hasznos, amelyek minden költségvetési ciklusban ugyanazokat a folyamatokat követik néhány módosítással vagy módosítások nélkül.

Egy másik hasznos parancs a **Műveletek** menüben a **Költségvetési folyamat állapotának megtekintése** link. Ez a parancs grafikus formában jeleníti meg a költségvetési terveket egy folyamat során a megfelelő adatokkal együtt, mint például a tervek munkafolyamat-állapota, összeg és egység szerinti összesítések, és egy kattintással elérhető navigáció a költségvetési tervekhez.

[![Költségvetés-tervezési folyamat állapota.](./media/budgetplanningprocessstatus-300x171.png)](./media/budgetplanningprocessstatus.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
