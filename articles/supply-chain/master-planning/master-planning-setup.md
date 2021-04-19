---
title: Alaptervezés beállítása
description: Ez a témakör az alaptervezés beállításához használt különböző fontos stratégiákat és paramétereket ismerteti.
author: t-benebo
ms.date: 07/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: fe7ff2ab877182dd3145e39574aa7229c48b6057
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833401"
---
# <a name="set-up-master-planning"></a>Alaptervezés beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör az alaptervezés beállításához használt különböző fontos stratégiákat és paramétereket ismerteti. Áttekintést nyújt az alaptervezés által használt tervek típusairól, és bemutatja, hogy az Ön üzleti igényeitől függően melyik tervstratégiát kell használnia. Azokat a fő paramétereket is ismerteti, amelyek hatással vannak a tervre, és bemutatja, hogyan befolyásolják ezek a paraméterek a javasolt tervezett rendeléseket.

## <a name="types-of-master-plans"></a>Alaptervek típusai

Az alaptervezés kétféle, statikus és dinamikus tervtípussal rendelkezik. Minkét típus más célra készült. A legjobb teljesítmény érdekében ajánlott a megfelelő tervet használni a forgatókönyvéhez.

### <a name="static-plan"></a>Statikus terv

A statikus terv addig nem változik, tekintet nélkül a kínálat és kereslet változásaira, amíg az alaptervezést újra nem futtatja.

A statikus terv a javasolt rendelések jóváhagyására és megerősítésére szolgál. Ez egy olyan működési terv, amelyet a vállalati személyzet különböző tagjai (például a beszerzők vagy a termeléstervezők) használhatnak a döntéseik alapjául, és amely alapján végrehajthatják a napi feladataikat és tevékenységeiket.

A statikus terv az utófeldolgozást is támogatja. Minden alkalommal, amikor az alaptervezést futtatja, a program automatikusan kiszámít egy teljesen új optimalizált tervet, és törli a nem jóváhagyott meglévő rendeléseket.

### <a name="dynamic-plan"></a>Dinamikus terv

A dinamikus terv általában a statikus terv másolataként indul, de az alapadatok módosításakor bármikor frissíthető. Ha például az adatok módosulnak, akkor új értékesítési rendelés jön létre.

A dinamikus terv ad hoc tervezéshez használatos. Ez lehetővé teszi a változó rendeléshálózat és a cikkek rendelkezésre állásának a figyelését anélkül, hogy zavarná a mások munkafolyamataihoz használt statikus tervet. Ez a módszer kifejezetten az ígérhető (CTP). A dinamikus terv az alapértelmezett terv, ha a nettó igényeket a rendelési oldalakból (például értékesítési rendelési, beszerzési rendelési vagy termelési rendelési oldalakból) nyitja meg.

A dinamikus terv a nettó módosítást használja. Ezért gyorsabb futási időt garantál.

## <a name="strategies-for-using-master-plans"></a>Stratégiák az alaptervek alkalmazásához

Az alaptervezésben akár egy, akár két terv is használható. A használt stratégia az Ön üzleti igényeitől függ.

### <a name="one-plan-strategy"></a>Egytervű stratégia

Az egytervű stratégia esetében ugyanazt az alaptervet kell használni a statikus tervhez és a dinamikus tervhez. Ezt a stratégiát a raktárra gyártási eseteknél kell használni, ahol általában nem kell rendelést teljesítő tervet szimulálni.

Az egytervű stratégiát általában kiskereskedelmi és forgalmazói iparágakban használják, vagy olyan ágazatokban, ahol az értékesítésszállítási dátumokat a szolgáltatásiszint-szerződések (SLA) vagy átfutási idők alapján erősítik meg. A terv esetében a szállítási dátum ellenőrzése ígérhető számítás nélkül is használható.

Ha szimulációt kell végeznie, akkor a terv újrafuttatható a szimulációt igénylő cikkek esetében. A szimulációk rendeléséhez tervezett rendelések általában megerősített rendelések.

### <a name="two-plan-strategy"></a>Kéttervű stratégia

A kéttervű stratégiához egy statikus tervet és egy másik dinamikus tervet kell használni. A kéttervű stratégiát általában a konfigurálás rendelésre és a gyártás rendelésre vonatkozó esetekhez használják, ahol értékesítési rendelés szimulációira van szükség, és az értékesítési rendelésekhez pontos szállítási dátumokat kell kiszámítani, de a számítások nem befolyásolhatják a mindennapos műveleteket. Ezeket a szimulációkat mindig a dinamikus tervben kell végrehajtani. A kéttervű stratégia például a gépjárműipari ágazatokban és az eredeti berendezésgyártók (OEM) ágazataiban használhatók.

Kéttervű stratégia esetében a szállítási dátum ellenőrzése ígérhető számítással is használható. Amikor az ígérhető számítás használatban van, a program automatikusan elindítja a futást a dinamikus tervben.

### <a name="setting-up-the-plans"></a>A tervek beállítása

A tervek az **Alaptervek** oldalon hozhatók létre (**Alaptervezés \> Beállítás \> Tervek \> Alaptervek**).

A **Alaptervezés paraméterei** oldal **Jelenlegi statikus alapterv** és **Jelenlegi dinamikus alapterv** mezőinek beállításával megadhatja, hogy mely tervek szerepeljenek a statikus tervben és a dinamikus tervben (**Alaptervezés \> Beállítás \> Alaptervezés paraméterei**). Egytervű stratégia használatához a **Jelenlegi statikus alapterv** és **Jelenlegi dinamikus alapterv** mezőben válassza ki ugyanazt a tervet.

## <a name="types-of-planning-methods"></a>A tervezési módszerek típusai

Az alaptervezés futtatásához három számítási mód használható: az utófeldolgozás és a nettó változás. Minden módszer másik tervet készít futtatásakor.

A tervezési módszert az **Alaptervezés futtatása** párbeszédpanelen határozhatja meg. Ennek a párbeszédablaknak a megnyitásához lépjen az **Alaptervezés \> Alaptervezés \> Futtatás \> Alaptervezés** lehetőségre, vagy válassza az **Alaptervezés** munkaterületen a **Futtatás** parancsot.

### <a name="regeneration"></a>Újbóli létrehozás

Az utófeldolgozás tervezési módszere törli a meglévő tervezett rendeléseket, hacsak nincsenek megerősítve. A módszer új tervezett rendeléseket hoz létre az összes igény alapján. Az utófeldolgozás az egyetlen olyan tervezési módszer, amely elérhető a statikus tervekhez.

- A készletváltozásokat figyelembe veszik. A módosítások között szerepelnek az előrejelzés változásai.
- Ez a módszer figyelembe veszi az **Időszak** fedezeti kódját.
- Ez a módszer támogatja a termékhelyettesítési funkciókat (PI).

### <a name="net-change"></a>Nettó változás

A nettó változás tervezési módszere tervezett rendeléseket hoz létre, hogy lefedje azokat az igényeket, amelyek a legutóbbi alaptervezés-futtatás óta létrejöttek vagy módosultak. A készlet változásai nem számítanak a módszer futtatásakor. A rendszer semmilyen új készletet nem vesz figyelembe, és a korábban létrehozott tervezett rendeléseket nem törli, ha már nincs szükség rájuk. A nettó változás tervezési módszere gyorsabban fut, mint az utófeldolgozási módszer. Csak dinamikus tervekhez érhető el.

- Ugyanakkor a műveleti időpontok és határidők valamennyi igény esetében frissülnek.
- Ez a módszer nem veszi figyelembe az **Időszak** fedezeti kódját.
- Ez a módszer nem teljesíti az előrejelzést, még akkor sem, ha ki van választva a tervben.
- Ez a módszer nem támogatja a termékhelyettesítési funkciókat (PI).

### <a name="net-change-minimized"></a>Nettó változás minimalizálva

A nettó változás minimalizált tervezési módszere tervezett rendeléseket hoz létre, hogy csak azokat az igényeket fedje le, amelyek a legutóbbi ütemezett alaptervezés-futtatás óta létrejöttek vagy módosultak. Ennél a módszernél a nettó változási módszertől eltérően a művelet dátumai és jövőbeli dátumai csak új vagy módosított igényeknél frissülnek. Ez a tervezési mód csak dinamikus tervekhez érhető el.

## <a name="types-of-scheduling-methods"></a>Az ütemezési módszerek típusai

Minden terv esetében az **Alaptervek** lap **Általános** gyorslapján  (**Alaptervezés \> Beállítás \> Tervek \> Alaptervek**) ki kell választani a termelési rendelésekhez használt ütemezési módszert. A termelést műveleti szinten és feladatszinten is ütemezheti.

### <a name="operations-scheduling"></a>Műveletek ütemezése

A műveletek ütemezését arra használhatja, hogy általános időbeli becslést készítsen a termelési folyamatról. A műveletütemezés nem biztosítja az útvonalhoz tartalmazó termelési műveletek feladatokká való lebontását. A műveletütemezéssel kapcsolatos további tudnivalókat lásd: [Műveletütemezés](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/operations-scheduling).

### <a name="job-scheduling"></a>Feladatütemezés

A feladatütemezés részletesebb ütemezési módszer, amely feladatokra bontja az egyes műveleteket. A feladatütemezés információkat tartalmaz a kapacitásról. Általában az üzemben végrehajtott egyes feladatok ütemezésére használják, rendszerint azonnal vagy rövid távú jelleggel. A feladatütemezéssel kapcsolatos további tudnivalókat lásd: [Feladatütemezés](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="time-fences-in-days"></a>Időkorlát napokban

Minden tervnél kiválaszthatja, hogy az alaptervezés alapján a jövőben mennyire előretekintve kell számítani a különböző igényeket és egyéb szempontokat. Ennek az időszaknak *időkorlát* a neve. Az alaptervezésben a legjobb teljesítmény elérése érdekében ajánlott úgy módosítani a különböző időkorlátokat, hogy megfeleljenek az Ön üzleti követelményeinek. Az időkorlátokat minden terv esetében az **Alaptervek** oldal **Időkorlát napokban** gyorslapján találja (**Alaptervezés \> Beállítás \> Tervek \> Alaptervek**).

> [!NOTE]
> Minden időkorlátnál megadhatja, hogy az alaptervezés alapján a jövőben mennyire előretekintve legyenek kiszámítva a különböző igények és egyéb szempontok. Az ezen az oldalon kiválasztott időkorlátok felülbírálják a fedezeti csoportban meghatározott időkorlátot. Ez azt jelenti, hogy az időkorlátot igen értékre kell állítani, és a napok meghatározása felülbírálja a fedezeti csoportban meghatározott időkorlátot. Ha nem értéket állít be, akkor az időkorlátot a fedezeti csoport határozza meg. Végezetül ha nem szeretne egy beállítást használni (például nem szeretné használni a műveletkérő üzeneteket), állítsa **lgen** értékre, majd állítsa az időkorlátot **0** (nulla) napra.

### <a name="coverage"></a>Fedezet

A fedezet időkorlátja az ütemezési időszakot jelenti, vagy azt, hogy távlatban kell belefoglalni az igényt. Más szóval a tervezési időhatárt jelzi.

A **Fedezet** beállítás **Igen** értékre állításával felülbírálhatja az alapütemezés során a cikkhez definiált fedezeti időkorlátot. Ebben az esetben adja meg, hogy hány napra kell az alapütemezés kiszámításának lefednie az igényeket. A fedezeti időkorlátok kiszámítása a jelenlegi dátumtól kezdődik. A jelenlegi dátumnál korábbi követelményeket a program mindenképpen feldolgozza.

> [!NOTE]
> Az alaptervezésben a legjobb teljesítmény elérése érdekében ajánlott úgy módosítani a fedezeti időkorlátokat, hogy megfeleljenek az Ön tervezési időhatárának.

### <a name="freeze"></a>Befagyasztás

A befagyasztási időkorlát azt az időszakot jelzi, amikor egy új alapütemezés futtatásakor a meglévő tervezett rendelések nem változnak. A tervezett rendeléseket befagyasztják, és nem javasolnak újakat.

A **Befagyasztás** beállítás **Igen** értékre állításával felülbírálhatja az alapütemezés során a cikkhez definiált befagyasztási időkorlátot. Ebben az esetben adja meg, hogy hány napig legyen befagyasztva a tervezési művelet. Ne feledje, hogy ezen időszak alatt a program nem hoz létre új tervezett rendeléseket, és a meglévő tervezett rendelések nem változtathatók meg.

### <a name="firming"></a>Megerősítés

A megerősítési időkorlát azt az időhatárt jelzi, amelyben a tervezett rendelések automatikusan termelési és beszerzési rendelésekké alakulnak át. Ezt a folyamatot a *tervezett rendelések automatikus megerősítésének* is nevezik.

A **Megerősítés** beállítás **Igen** értékre állításával felülbírálhatja az alapütemezés során a cikkhez definiált megerősítési időkorlátot. Ebben az esetben adja meg, hogy hány napig legyenek a tervezett beszerzési és termelési rendelések automatikusan megerősítve. A megerősítési időkorlátot a program az alapütemezés dátumától kezdődően számítja ki. A tervezett beszerzési rendelés automatikus megerősítése csak akkor lehetséges, ha a cikk társítva van szállítóval.

### <a name="forecast-plan"></a>Előrejelzési terv

Az előrejelzési terv időkorlátja azt jelzi, hogy a jövőbeli alaptervezés milyen távlatban hozza létre a tervezett rendeléseket az előre jelzett igényekkel rendelkező cikkek esetében.

Az **Előrejelzési terv** beállítás **Igen** értékre állításával felülbírálhatja az alapütemezés során a cikkhez definiált előrejelzésiterv-időkorlátot. Ebben az esetben adja meg, hogy hány napig szerepeljen az előrejelzési terv értékesítési előrejelzése az alaptervezésben.

### <a name="capacity"></a>Kapacitás

A kapacitás időkorlátja azt jelzi, hogy a rendszer a jövőben mennyire előretekintve vegye figyelembe az erőforrások maximális kapacitását a rendelés ütemezése közben. Más szóval a terv a cikkek termelési útvonala alapján ütemezi a termelési rendeléseket, és figyelembe veszi a termelési útvonal erőforrásait és az egyes erőforrások maximális kapacitását.

A **Kapacitás** beállítás **Igen** értékre állításával felülbírálhatja az alapütemezés során a cikkhez definiált kapacitási időkorlátot. Ebben az esetben adja meg, hogy hány napra tervezze meg a program a kapacitást a tervezett termelési rendelésekhez. Az alapütemezés a cikkhez kapcsolódó aktív termékútvonalat használja és a követelmény dátumától visszafelé ütemeződik. Ha a tervezett termelés követelményének dátuma a kapacitás időkorlátján kívülre esik, akkor az átfutási időt a cikk szállítási dátuma határozza meg. A kapacitási időkorlát kiszámítása a jelenlegi dátumtól kezdődik.

### <a name="action-message"></a>Műveletkérő üzenet

A műveletkérő üzenetek olyan változtatásokat javasolnak, amelyek a meglévő ellátási rendelésen hajthatók végre az ellátási terv optimalizálása érdekében. Előfordulhat például, hogy rendelései előrehozását vagy elhalasztását, vagy a rendelési mennyiségek növelését vagy csökkentését ajánlják.

A **Műveletkérő üzenet** beállítás **Igen** értékre állításával felülbírálhatja az alapütemezés során a cikkhez definiált műveletkérő üzenet időkorlátját. Ebben az esetben adja meg a napok számát, ami alatt az alapütemezésnek műveletkérő üzeneteket kell létrehoznia az igényekhez. A műveletkérő üzenet időkorlátjának kiszámítása a jelenlegi dátumtól kezdődik.

A műveletkérő üzenetekkel kapcsolatos további tudnivalókat lásd: [Műveletkérő üzenetek:](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/master-planning/action-messages)műveletkérő üzenetek.

> [!NOTE]
> A műveletkérő üzenetek számítása hosszabb üzemidőt okoz az alaptervezésben. Ha a műveletkérő üzenetek elemzése és alkalmazása nem rendszeresen történik (naponta, hetente és így tovább), fontolja meg a számítás kikapcsolását az Alaptervezés futtatása során. A számítás kikapcsolásához az **Alaptervek** oldalon állítsa a **Műveletkérő üzenet** időkorlátját **0-ra** (nulla) az éppen futtatott alapterv esetében. Győződjön meg arról is, hogy a **műveletkérő üzenet** beállítás minden fedezeti csoport esetében ki van kapcsolva.

### <a name="calculated-delays"></a>Kiszámított késések

Megadhatja, hogy a jövőben mennyire előretekintve észlelje és jelentse a program a tervezett rendelések lehetséges késéseit. Így van lehetősége a lehetséges (késleltetett) szállítási dátumok ütemezésére.

Ha egy tervezett rendelést nem lehet teljesíteni a kért dátumig, akkor a tranzakció esetében a legkorábbi teljesítési dátumára tervezik az átfutási idők és az anyag és a kapacitás rendelkezésre állásának függvényében.

### <a name="approved-requisitions-time-fence"></a>Jóváhagyott igénylések időkorlátja

Az alaptervezés beállítható úgy, hogy tervezett rendeléseket hozzon létre az igénylési igényhez. Állítsa az **Igénylések befoglalása** beállítást **Igen** értékre az **Alaptervek** oldal **Általános** gyorslapján. Ezt követően ha a jóváhagyott igénylés célja feltöltés, az alaptervezés automatikusan létrehoz egy megfelelő tervezett rendelést, amely teljesíti a feltöltést. A feltöltési módszert az Ön szervezetében a cikkekhez beállított ellátási irányelvek határozzák meg. A feltöltési igénylés létrehozása és jóváhagyása után nincs szükség további felhasználói beavatkozásra.

Ha a **Jóváhagyott igénylések időkorlátja** beállítást **Igen** értékre állítja az **Időkorlát napokban** gyorslapon, felülbírálhatja az alapütemezés során a cikkhez definiált igénylési időkorlátot. Ebben az esetben adja meg azoknak a múltbeli napoknak a számát, amelyek során a feltöltési célú jóváhagyott igénylésekből származó igénynek be kell kerülnie az alapértelmezésbe. Például azt is megadhatja, ha a jóváhagyott igénylésekből csak az utolsó 10 napon belül létrehozott, nem teljesített lejárt igényt szeretné figyelembe venni és tervezni.

### <a name="sequencing"></a>Szekvenálás

A sorrendbe állítás lehetővé teszi a tervezett rendelések rendezését a késztermékhez társított sorrendbe állítási attribútumok alapján. Gyakran használatos a termelési rendelések csomagoláshoz való előkészítésére. Felhasználható például egy konkrét sorozatban található dobozok szín és a méret alapján történő csomagolására.

Ha a **Sorrendbe állítást** **Igen** értékre állítja, megadhatja, hogy a jövőben mennyire előretekintve kell sorrendbe állítani a műveleteket vagy feladatokat. Vegye figyelembe, hogy minél hosszabb az időkorlát, annál tovább tart az alaptervezés futtatása.

### <a name="calculated-delays"></a>Kiszámított késések

A késleltetési beállítások segítenek biztosítani, hogy a rendelések teljesíthető dátummal rendelkezzenek. Az alábbi beállítások az **Alaptervek** oldal **Kiszámított késések** gyorslapon érhetők el:

- **Győződjön meg róla, hogy a tervezett rendelések ne az alaptervezés futtatási dátuma előtt legyenek létrehozva** – állítsa ezt a beállítást **Igen** értékre, hogy a rendeléseket ne lehessen múltbeli dátumokra ütemezni.
- **Adja a kiszámított késést a követelmény dátumához** (a **Tervezett beszerzési rendelések** alatt) – állítsa ezt a beállítást **Igen** értékre, hogy hozzáadja a kiszámított késést az igényekhez.
- **Adja a kiszámított késést az igény dátumához** (a **Tervezett termelési rendelések** alatt) – állítsa ezt a lehetőséget **Igen** értékre, hogy hozzáadja a kiszámított késést a követelményekhez.
- **Adja a kiszámított késést az igény dátumához** (a **Tervezett átmozgatás** alatt) – állítsa ezt a lehetőséget **Igen** értékre, hogy hozzáadja a kiszámított késést a követelményekhez.
- **Adja a kiszámított késést az igény dátumához** (a **Tervezett kanban** alatt) – állítsa ezt a lehetőséget **Igen** értékre, hogy hozzáadja a kiszámított késést a követelményekhez.

Amikor a **Számított késés hozzáadása a követelménydátumhoz** lehetőséget **Igen** értékre állítja, hogy a késéseket hozzáadja az igényekhez, a rendszer figyelembe veszi az erőforrások kapacitását, és létrehozza a megvalósítható tervezett rendeléseket. A tervezett rendelési dátumok újraszámítása növeli az alaptervezés futási idejét. Ezért ha nem kell a késéseket használni, akkor **Nem** értékre kell állítania a beállításokat.

## <a name="positive-and-negative-days"></a>Pozitív és negatív napok

A pozitív és a negatív napok hatással vannak az alaptervezés tervezett rendelésekhez és műveletekhez adott javaslatára. A pozitív és negatív napokat a cikk fedezeti csoportjához állítja be a rendszer. Meghatározhatja a különböző fedezeti csoportokat, és beállíthatja paramétereiket a **Fedezeti csoportok** oldalon (**Alaptervezés \> Beállítás \> Fedezet\> Fedezeti csoportok**).

### <a name="positive-days"></a>Pozitív napok

A pozitív napok azt jelzik, hogy az alaptervezés a jövőben mennyire előretekintve vegye figyelembe az aktuális készletet vagy nyugtákat egy jövőbeli igény teljesítéséhez. Ha például a pozitív napok értéke **100**, akkor az aktuális készlet a következő 100 napban történő igény kielégítésére használható. Ha van egy 150 napos rendelés az aktuális dátumtól számítva, akkor az alaptervezés létrehoz egy tervezett rendelést az igény kielégítésére, még akkor is, ha a cikk aktuális készletéből teljesíthető a rendelés. A rövid átfutási idejű, gyorsan mozgatott cikkek esetében előfordulhat, hogy az aktuális készletet nem szeretné egy jóval későbbi rendeléshez használni. Gyors mozgatás esetén az aktuális készlet gyorsan elfogy, és a jövőben több rendelés is leadható a jövőbeli igény időre történő teljesítéséhez, amely a cikk rövid átfutási ideje miatt lehetséges.

A pozitív napok a műveletkérő üzenetekre is hatással vannak. Előfordulhat például, hogy a rendszer egy tervezett beszerzési rendelés növelésére tesz javaslatot, mégpedig úgy, hogy a rendelés a jövőbeli pozitív napok számán belüli igényt tartalmazzon. Ha a pozitív napok értéke **100**, és ha az aktuális dátumtól számított 30 nap múlva van igény egy adott cikkre, akkor a rendszer tervezett rendelést hoz létre az igény kielégítésére. Ha az aktuális dátumtól 90 napon belül van igény ugyanarra a cikkre, akkor a rendszer azt javasolja, hogy a rendelés mennyiségét az aktuális dátumtól számítva 30 napon belül emelje, így a rendelés a 90 napon belüli igényre is kiterjed. Ha azonban az aktuális dátumtól 150 napon belül igény van a cikkre, akkor a rendszer nem javasolja, hogy növelje a már tervezett rendelés mennyiségét. Helyette új tervezett rendelést hoz létre.

Szabály szerint a pozitív napokat a cikkek leghosszabb átfutási ideje és a fedezeti időkorlát között megadott számra állítja be a rendszer. Azt ajánljuk, hogy a rendszeresen beszerezett vagy előállított cikkeket egy fedezeti csoporthoz rendelje hozzá, ahol a pozitív napok megegyeznek a cikk átfutási idejével.

### <a name="negative-days"></a>Negatív napok

A negatív napok azt jelzik, hogy milyen mértékű késés engedélyezett a cikkbevételezéseket illetően. Azoknak a napoknak a számát jelentik, amennyit Ön hajlandó várni új feltöltés rendelése előtt, ha a készlet negatív, vagy nem elegendő. A negatív napok választ adnak a kérdésre: létre kell-e új beszerzési rendelést hozni a cikkhez,  vagy a meglévő beszerzést kell használni, még akkor is, ha tudjuk, hogy a cikk késni fog?

Például Önnek értékesítési rendelése van egy cikkre az aktuális dátumtól számított 15 nap múlva. Ugyanerre a cikkre beszerzési rendelése is van. Ez a beszerzési rendelés az aktuális dátumtól számított 20 napon belül fog megérkezni. Szeretné, hogy a rendszer létrehozzon egy beszerzési rendelést az adott értékesítési rendeléshez, vagy használja a meglévő rendelést, még akkor is, ha Ön nem tudja időben teljesíteni az értékesítési rendelést? Ha a negatív napok száma **5-nél** kisebb értékre van állítva, jelezve, hogy a cikkek legfeljebb öt napot késhetnek, a rendszer új tervezett beszerzési rendelést hoz létre az értékesítési rendelés teljesítésére. Ha a negatív napok száma **5-nél** nagyobb értékre van állítva, akkor a rendszer a cikk meglévő rendelését használja.

A negatív napok az alaptervezés teljesítményére is hatással vannak. Ha a negatív napok magasabb értékre vannak állítva, akkor a rendszer számos műveletkérő üzenetet hoz létre.

Javasoljuk, hogy a negatív napokat a cikk átfutási idejénél kisebb számra állítsa be.

### <a name="dynamic-negative-days"></a>Dinamikus negatív napok

A dinamikus negatív napok figyelembe veszik a cikk átfutási idejét és az Ön által megadott negatív napokat. A rendszer egy új tervezett beszerzési rendelést hoz létre, a következő képlet alapján kiszámított negatív napok időkorlátja alapján:

Átfutási idő + Negatív napok + Aktuális dátum – Igény dátuma

A rendszer csak az ezen időkorláton belül tervezett beszerzési rendeléseket használja, és az időkorláton kívül hoz létre új tervezett rendelést. A dinamikus negatív napok előnye, hogy magában foglalja az adott termék átfutási idejét, lehetővé teszi a meglévő rendelések újrafelhasználását, és kiküszöböli az átfutási idő okozta késések miatt új tervezett rendelések létrehozását. 

További tájékoztatásért lásd: [Negatív napok és dinamikus negatív napok](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/master-planning/more-about-dynamic-negative-days).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]