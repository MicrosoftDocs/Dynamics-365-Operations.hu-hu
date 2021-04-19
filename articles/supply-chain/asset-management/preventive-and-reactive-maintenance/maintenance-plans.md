---
title: Karbantartási tervek
description: Ez a témakör az Eszközkezelés karbantartási terveit ismerteti.
author: johanhoffmann
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectType, EntAssetCounterType, EntAssetWorkOrderLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 143b9337dc9ca530383575e0f9bb16e4313ce96b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839607"
---
# <a name="maintenance-plans"></a>Karbantartási tervek

[!include [banner](../../includes/banner.md)]

A karbantartási terv határozza meg, hogy mikor kell végrehajtani egy eszközön egy előre tervezett megelőző karbantartási feladatot. A karbantartási tervek az eszközökhöz, eszköztípusokhoz a munkavégzési helyszínekhez vagy munkavégzési helyszín típusaihoz kapcsolhatók, de először létre kell hozni a vállalatnál használandó karbantartási terveket.

A karbantartási tervnek több karbantartási tervsora is lehet. A karbantartási feladattípust és intervallumot a karbantartási tervsorban határozhatja meg. A karbantartási terv sorainak két típusa van:

- Idő
- Számláló

Az „Idő” típusú karbantartási tervsorok a rögzített időintervallum alapján ismétlődő tervezett karbantartásokhoz használatosak. A „Számláló” típusú karbantartási tervsorok az eszközök számláló regisztrációi alapján tervezett karbantartáshoz vagy beavatkozó karbantartáshoz használatosak. A karbantartási terv több sort tartalmazhat mindkét típusú karbantartási tervből.

>[!NOTE]
>Ha egy eszköz esetében nem regisztráltak számlálókértékeket egy számlálótípushoz, akkor a karbantartási terv sorai ki vannak hagyva.

Először létre kell hoznia a megelőző karbantartási feladatokhoz szükséges karbantartási terveket, és ki kell választania azokat a az eszköztípusokat, eszközöket, munkavégzési helyszíntípusokat és munkavégzési helyszíneket, amelyek az egyes karbantartási tervekhez kapcsolódnak. Ezt követően, ha szükséges, a karbantartási terveket hozzáadhat egy eszközhöz vagy egy munkavégzési helyszínhez is, amely az **Összes eszköz** \> eszköz kijelölése \> **Eszközkarbantartási tervek** gyorslapon vagy a **Minden munkavégzési helyszín** \> munkavégzési helyszín kiválasztása \> **Karbantartási tervek** gyorslapon végezheti el.

Ha egy karbantartási tervet ad hozzá a eszköztípusokhoz vagy a munkavégzési helyszín típusokhoz, akkor ez azt jelenti, hogy amikor új eszközöket vagy munkavégzési helyszíneket hoz létre az ilyen eszköztípusokkal vagy munkavégzési helyszíntípusokkal, a program automatikusan hozzáadja az eszközt vagy a munkavégzési helyszínt a karbantartási tervhez. A karbantartási tervhez tartozó kezdődátum az aktuális dátum lesz, amelyet esetleg módosítani kell.

## <a name="set-up-maintenance-plans"></a>Karbantartási tervek beállítása

Ez a szakasz bemutatja, hogyan lehet beállítani a karbantartási terv sorait, és példákat kínál arra, hogy hogyan használhatók.

1. Lépjen az **Eszközkezelés \> Beállítások \> Megelőző karbantartás \> Karbantartási tervek** elemre.

1. Válassza ki az **Új** lehetőséget egy új sorozat létrehozásához.

1. Szúrjon be egy azonosítót a **Karbantartási szekvencia** mezőbe és írjon be egy nevet a **Név** mezőbe.

1. A **Terv dátuma** mezőbe írja be azt a kezdő dátumot, amelytől kezdve a karbantartási tervben a tervezés végezhető. Ne feledje, hogy az időalapú karbantartási tervsorok rendelkezhetnek más tervezett dátumokkal.

1. A karbantartási terv aktiválásához válassza az „Igen” beállítást az **Aktív** választógombra kattintva.

    >[!NOTE]
    >Karbantartási terv inaktiválása esetén nem jönnek létre ütemezett közzétételek a karbantartási ütemezésben, amikor egy ütemezett karbantartásiterv-feladatot futtat.

1. A **Tűréshatár napban előtte** és a **Tűréshatár napban utána** mezők olyan karbantartási tervsorokhoz kapcsolódnak, amelyekben az **Átfedő karbantartási feladatok kihagyása** jelölőnégyzet be van jelölve (lásd a 17. lépést). A „Tűréshatár” mezők kibővítik az intervallumot napokban, amikor több karbantartási terv átfedésben van, a legrészletesebb/legnagyobb feladat lesz karbantartási ütemezés sorként létrehozva karbantartási terve ütemezésekor, míg a gyakoribb, átfedő feladatok ki vannak hagyva a karbantartási terv ütemezése során. Adja meg a napok számát a **Tűréshatár napban előtte** mezőben, például „2”.

1. Ha megadott értéket adott meg a **Tűréshatár napban előtte** mezőben akkor adja meg a napok számát a **Tűréshatár napban utána** mezőbe is, például „2”.

    >[!NOTE]
    >Az ebben és az előző lépésben ismertetett példa azt jelenti, hogy ha több karbantartási tervsor átfedésben van , és egy vagy több sorhoz be van állítva az **Átfedő karbantartási feladatok kihagyása** lehetősége, akkor a karbantartási ütemezés sorainak kihagyott időszaka meghosszabbodik. összesen öt napra (a karbantartási ütemezés sorában szereplő várható kezdési dátum, *és* két nappal a dátum lőtt *és* két nappal a dátum után).

1. A **Részletek** gyorslap **Részletek** csoportjának mezői a karbantartási tervben beállított karbantartási terv sorainak számát, valamint a karbantartási tervhez kapcsolódó eszközök és munkavégzési helyszínek számát mutatják.

1. A **Sorok** gyorslapon válassza az **Idő sor hozzáadása** vagy **Eszközszámláló sor hozzáadása** lehetőséget egy új karbantartásiterv-sor létrehozásához.

1. Adja meg a sor leírását a **Munkarendelés leírása** mezőbe. A program átviszi a leírást a kapcsolódó munkarendelésekre.

1. A **Karbantartási feladat típusa** mezőben válassza ki a feladattípust, amelyhez karbantartási terv sora kapcsolódik.

1. A **Karbantartási feladattípus változója** és a **Szakma** mezőben válassza ki a karbantartási feladattípushoz tartozó változatot és szakmát.

1. A **Befejezés ennyi nap múlva** és **Befejezés ennyi óra múlva** mezőkbe a várható záró dátumot napokban vagy órákban lehet beszúrni. A várható záró dátumot a karbantartási ütemezés sorainak létrehozásakor, a várható kezdődátumhoz viszonyítva szúrja be a rendszer. Beszúrhatja például a „7-es” számot a **Befejezés ennyi nap múlva** mezőben, ha a kapcsolódó feladatot a várható kezdő dátumtól egy héten belül kell végrehajtani.

1. Az **intervallum típusa** mezőben válassza ki, hogy milyen típusú intervallumot kíván használni a karbantartási terv sorában, például: „Ismétlődő…” vagy „egyszeri…”. Lásd az [Intervallumtípusok áttekintése](#interval-types) táblázatot alább az intervallum-típusok és a sorok típusának leírásáért.

1. Az **Időszak** mező csak időalapú sortípusokra vonatkozik. Válassza ki időszak gyakoriságához kapcsolódó időszak típusát.

1. Az **Időszak gyakorisága** mezőbe írja be, hogy hány alkalommal kell a sort használni a megelőző karbantartási feladatok megtervezéséhez. Példa: Ha létrehozott egy „számláló” típusú sort, és a számláló egy termelési mennyiség, és a „20000” szám szerepel ebben a mezőben, akkor a rendszer az új karbantartási szekvencia-sorokat hoz létre a megelőző karbantartás ütemezése során minden olyan alkalommal, amikor várhatóan további 20 000 cikk előállítása történik.

1. Az **Átfedő karbantartási feladatok kihagyása** jelölőnégyzet időalapú és számlálóalapú sortípusokra is vonatkozik. Jelölje be a jelölőnégyzetet, ha törölni szeretné az ugyanarra a dátumra létrehozott karbantartási ütemezések bejegyzéseit. Erre akkor van szükség, ha például egy 1 hónapos ellenőrzési sort, egy 6 hónapos ellenőrzési sort és egy 1 éves ellenőrzési sort hozott létre. Az 1 éves vizsgálatnál csak azt szeretné, ha csak annak a vizsgálatnak az elvégzése történne, nem pedig a másik két ellenőrzésé, amely az időkeretben esedékes lenne. A példa helyes beállításához be kell állítani az 1 éves ellenőrzési sort első sorként, a 6 hónapos sort második sorként, és az 1 hónapos sort harmadik sorként és be kell jelölnie **Átfedő karbantartási feladatok kihagyása** jelölőnégyzetet az 1 hónapos és 6 hónapos sorokhoz. Így biztosítható, hogy az 1 éves határelérésekor a program kihagyja az egy hónapos és hat hónapos ellenőrzést, és a karbantartási ütemezési sort csak az 1 éves ellenőrzési sorhoz hozza létre.

    >[!NOTE]
    >Az ebben a lépésben leírt példa azt mutatja, hogy a legátfogóbb feladatot, amely a legnagyobb számú feladatot tartalmazza, és amely nem olyan gyakran történik meg, mindig első sorként kell beszúrni. A gyakoribb feladatok ezután külön sorokként jelennek meg a gyakoriság sorrendjében, a leggyakrabban elvégzett feladattal a lista alján.

1. Az **Számláló** mező csak számlálóalapú sortípusokra vonatkozik. Válassza ki a sorhoz használt számláló típusát. Ha egy kapcsolódó eszköz esetében nem aktív a számláló típus, akkor a karbantartási terv sora ki lesz hagyva.

1. Az **Eszköz számláló időkerete napokban** mező csak a számláló típusú sorokra vonatkozik. Adjon meg egy számot, amely meghatározza, hogy a rendszer mennyi napra visszamenőleg ellenőrizze a számláló-regisztrációkat, amikor a karbantartási terv ütemezése elkészül. Ez azt jelenti, hogy a mennyi időre visszamenőlegesen használja a rendszer az adatokat (meglévő számláló-regisztrációk) annak a trendnek a kiszámításához, ami meghatározza, hogy karbantartásiütemezés-sor legyen létrehozva.

    >*Példa:* Ha a számláló-regisztrációkat havonta egyszer szeretné elkészíteni, akkor ebbe a mezőbe beillesztheti a „365” számot, mert a karbantartási terv ütemezése mindig az elmúlt 12 hónapon fog alapulni, így a karbantartási ütemezés sorait az előző év trendje alapján kell létrehozni. Ha viszont ebbe a mezőbe a „10” számot illeszti be, akkor a számlálók regisztrációi gyakrabban történnek, például napi rendszerességgel. Ez azt jelenti, hogy a karbantartási terv ütemezésekor a program az utolsó 10 nap számláló-regisztrációit használja a karbantartásiütemezési sorok ütemezésének alapjául.

1. Az **Terv dátuma** mező csak időalapú sortípusokra vonatkozik. Ha a karbantartási terv sora a teljes karbantartási tervétől eltérő tervezési dátumot tartalmaz, válasszon ki egy dátumot **Terv dátuma** mezőben a sorban.

1. A **Szolgáltatási szint** mezőben kiválaszthatja a munkarendelés szolgáltatási szintjét, mint a karbantartási terv sorának további elválasztóját, amely szolgáltatási szintként használható a munkarendeléseken.

1. Jelölje be az **Automatikus létrehozás** jelölőnégyzetet, ha azt szeretné, hogy a karbantartási tervek ütemezésekor a program automatikusan létrehozza a kiválasztott karbantartási terv sora szerinti munkarendelést.

1. Ha bejelölte az **Automatikus létrehozás** jelölőnégyzetet, akkor az automatikusan létrehozott munkarendeléshez a **Munkarendelés típusa** mezőben kiválaszthatja a Munkarendelés típusát. Ha bejelölte az **Automatikus létrehozás** jelölőnégyzetet, és ebben a mezőben nem választ munkarendelés-típust, akkor az **Eszközkezelés \> Beállítás \> Eszköz kezelési paraméterek \> Munkarendelések** hivatkozás \> **Megelőző munkarendelés típusa** mező lesz használva.

1. Az **Időszak kezdete** és **Időszak** vége mezőkkel ismétlődő, időalapú karbantartási tervsort hozhat létre egy 12 hónapos időszakon belül. *Példa:* A zöldterületek fenntartására használt berendezésekhez minden tavasszal egy előre megadott időszakon belül szervizre van szükség. Az időszak kezdő dátumát szúrja be az **Időszak kezdete** mezőbe.

1. Az időszak befejező dátumát szúrja be az **Időszak vége** mezőbe.

1. A **Létrejövő időszak** mezőbe az aktuálisan megismételni kívánt időszak jelenik meg. Amikor az aktuális időszak eltelt, és új évet kezd, az ebben a mezőben megjelenő időszakot frissíti a program, hogy az megfeleljen a következő időszaknak az ismétlési sorozatban.

1. Az **Eszközök** gyorslapon válassza ki azokat az eszközöket amelyek az adott karbantartási tervhez kapcsolódnak:

1. Az **Eszköztípusok** gyorslapon válassza ki azokat az eszköztípusokat amelyek az adott karbantartási tervhez kapcsolódnak:

1. Az **Munkavégzési helyszínek** gyorslapon válassza ki azokat az munkavégzési helyszíneket, amelyek az adott karbantartási tervhez kapcsolódnak: Ha szükséges, a megfelelő eszköz típusának, gyártójának és modelljének kiválasztásával pontosabban is megadhatja a beállításokat.

1. Az **Munkavégzési helyszíntípusok** gyorslapon válassza ki azokat az munkavégzési helyszíntípusokat, amelyek az adott karbantartási tervhez kapcsolódnak:

>[!NOTE]
>Ha a munkarendelések létrehozása manuálisan, egyszállítói garanciával fedezett eszközhöz történik, egy párbeszédpanel jelenik meg, amely a felhívja a felhasználó figyelmét a jótállásra. A munkarendelés létrehozása ezt követően visszavonható. Az automatikusan létrehozott munkarendelések a jótállási kapcsolat keresése ki van hagyva.

<a id="interval-types"></a>

## <a name="interval-types-overview"></a>Intervallumtípusok áttekintése

| Intervallum típusa és leírása | Sor típusa: Idő | Sor típusa: számláló |
|---|---|---|
| **Intervallum típusa: Megismételve a terv dátumától** A számolás a használt tervdátumtól kezdődik. A karbantartási tervek ütemezésekor létrejön egy karbantartási ütemezési sor az intervallum elérésekor. | A **Terv dátuma** a karbantartási sorban lesz használva. Ha nincs kiválasztva a terv dátuma a sorban, akkor a karbantartási terv **Tervdátumát** használja a rendszer. Példa: ha a 3-as szám szerepel az **Időszaki gyakorisága** mezőben, és az „Év" beállítás van kiválasztva az **Időszak** mezőben, akkor az új karbantartási ütemezési sor egyszer jön létre 3 évente. | A **Terv dátuma** a karbantartási sorhoz használva van. Ha a számlálót lecserélték, a program a legutóbbi cseredátumot használja a terv dátumaként. |
| **Intervallum típusa: Ismétlődő a kezdődátumtól** A számlálás az eszköz kapcsolatának kezdődátumától kezdődik. A dátum az **Összes eszköz** részletek nézet \> **Eszközkarbantartási tervek** gyorslap \> **Kezdődátum** mezőjéből vagy az **Összes munkavégzési helyszín** részletek nézet \> **Karbantartási tervek** gyorslap \> **Kezdő dátum** mezőjéből lesz kiválasztva. A karbantartási tervek ütemezésekor létrejön egy karbantartási ütemezési sor az intervallum elérésekor. | Az eszköz vagy munkavégzési helyszín karbantartási sorának kezdődátuma lesz használva. Ha ez a mező üres, a karbantartási tervhez tartozó **Tervdátum** használatos. | Az eszköz vagy munkavégzési helyszín karbantartási sorának kezdődátuma lesz használva. Ha ez a mező üres, a karbantartási tervhez tartozó **Tervdátum** használatos. |
| **Intervallum típusa: Ismételve az utolsó munkarendelésből** A számlálás a legutóbbi elvégzett munkarendelés tényleges záró dátumától és idejétől, és a konkrét karbantartási feladattípus, karbantartási feladattípus változat- és a szakmakombinációtól kezdődik. Ez a dátum és **az idő a Tényleges befejezés** mezőben átható a **Minden munkarendelés** részletei nézetben. | Az eszközön elvégzett Munkarendelés tényleges záró dátuma és időpontja, és a konkrét karbantartási feladattípus/karbantartás feladattípus változata/szakma kombinációja. Ha nem található befejezett munkarendelés, akkor a program a fentebb ismertetett „Ismétlődő a kezdődátumtól” intervallumtípusnál használt dátumot használja. | Az eszközön elvégzett Munkarendelés tényleges záró dátuma és időpontja, *és* a karbantartási feladattípus/karbantartás feladattípus változata/szakma kombinációja. Lesz használva. Ha a munkarendelésben a kezdő és befejező dátumot üresen hagyták, akkor a program a fentebb ismertetett „Ismétlődő a kezdődátumtól” intervallumtípusnál használt dátumot használja. |
| **Intervallum típusa: Egyszer a terv dátumától** Lásd az „Ismétlődő a tervdátumtól" intervallum leírását fent. Ez egyetlen különbség az, hogy ez az intervallum csak egyszer lesz használva. | Lásd az „Ismétlődő a terv dátumától" típusú intervallum leírását fent. Ez az intervallum általában egy egyszeri karbantartási vagy szervizfeladathoz használatos. | Lásd az „Ismétlődő a terv dátumától" típusú intervallum leírását fent. Ez az intervallum általában egy egyszeri karbantartási vagy szervizfeladathoz használatos. **1. Megjegyzés** : Ez az intervallumtípus csak akkor érvényes, ha a számlálót minden karbantartási vagy szolgáltatási feladat végrehajtása alkalmával kicserélik. Ha valamilyen oknál fogva a számlálót a tervezett időszak vége előtt cserélte le a program, akkor a számláló cseréjének idejétől a feladatra vonatkozóan új idő lesz kiszámítva. **2. megjegyzés** : Ha a számlálót a karbantartás vagy a szolgáltatás feladatának végrehajtásakor cserélik ki, akkor ez az intervallum a fenti „Ismétlődő a terv dátumától" szerint működik. |
| **Intervallum típusa: Egyszer a kezdődátumtól** Lásd az „Ismétlődő a kezdődátumtól" intervallum leírását fent. Ez egyetlen különbség az, hogy ez az intervallum csak egyszer lesz használva. | Lásd az „Ismétlődő a kezdődátumától" típusú intervallum leírását fent. Ez az intervallum általában egy egyszeri karbantartási vagy szervizfeladathoz használatos. | Lásd az „Ismétlődő a kezdődátumától" típusú intervallum leírását fent. Ez az intervallum általában egy egyszeri karbantartási vagy szervizfeladathoz használatos. A fenti **1. megjegyzés**: erre az intervallumtípusra is vonatkozik. **3. megjegyzés** : Ha a számlálót a karbantartás vagy a szolgáltatás feladatának végrehajtásakor cserélik ki, akkor ez az intervallum a fenti „Ismétlődő a kezdődátumtól” szerint működik. |
| **Intervallum típusa: Miután elérte fent** Ezt az intervallumtípust csak a számlálókra vonatkozik, és a karbantartási terv sorában megadott felső határérték jelzésére szolgál. A karbantartási ütemezés bejegyzései tartalmazzák a számláló regisztrációjának várható kezdő dátumát és időpontját, amely azt jelenti, hogy ezek a bejegyzések a kezdő dátummal megegyező vagy annál korábbi értékkel fognak létrejönni. | Nem alkalmazható | A számláló intervalluma egy felső határt jelez. Ha ezt a korlátot túllépik a számlálóregisztráció létrehozásakor, megelőző karbantartás ütemezésekor jön létre egy karbantartási ütemezési sor. |
| **Intervallum típusa: Miután elérte lent** Ezt az intervallumtípust csak a számlálókra vonatkozik, és a karbantartási terv sorában megadott alsó határérték jelzésére szolgál. A karbantartási ütemezés bejegyzései tartalmazzák a számláló regisztrációjának várható kezdő dátumát és időpontját, amely azt jelenti, hogy ezek a bejegyzések a kezdő dátummal megegyező vagy annál korábbi értékkel fognak létrejönni. | Nem alkalmazható | A számláló intervalluma egy alsó határt jelez. Ha ezt a korlátot elérik a számlálóregisztráció létrehozásakor, megelőző karbantartás ütemezésekor jön létre egy karbantartási ütemezési sor. |
| **Intervallum típusa: Kezdő dátumtól kapcsolva** Ez az intervallumtípus csak egyszer hoz létre egy karbantartási ütemezési sort. Egy karbantartási terv több karbantartásiterv-sort is tartalmazhat az ilyen típusú intervallummal és ezek a sorok csatolva vannak. Általában olyan karbantartási tervet fog létrehozni, amely csak ilyen intervallumtípust tartalmazó sorokat tartalmaz. A karbantartási ütemezés sorai úgy lesznek létrehozva, hogy azonosítva lesz az karbantartási tervsor, amelynek a legkorábbi a kezdő dátuma és időpontja. | Lásd az „Egyszer a kezdődátumától" típusú intervallum leírását fent. Példa:Agy karbantartási tervben két sort hoz létre egy szervizfeladathoz egy autó esetében: egy idő-alapú sort egy 1 éves időszakkal, és egy számláló alapú sort pedig 25 000 km-es határértékkel. A program létrehoz egy karbantartási ütemezési sort az elsőként elért korláthoz. Ehhez a sortípushoz egy 1 éves időszakkal hoz létre sort. | Lásd az „Egyszer a kezdődátumától" típusú intervallum leírását fent. Példa:Agy karbantartási tervben két sort hoz létre egy szervizfeladathoz egy autó esetében: egy idő-alapú sort egy 1 éves időszakkal, és egy számláló alapú sort pedig 25 000 km-es határértékkel. A program létrehoz egy karbantartási ütemezési sort az elsőként elért korláthoz. Ehhez a sortípushoz egy 25 000 km-es határértéket hoz létre. Példa két számláló sor létrehozására: Beállíthatja egy karbantartási tervet két összekapcsolt számlálóalapuló sorral amelyeknél az első sor 10 000-es legyártott mennyiséget tartalmaz, és a második sor egy gépre vagy munkaközpontra vonatkozik, amelyhez 3000 üzemóra után szükséges szerviz. |
| **Intervallum típusa: Az utolsó munkarendelésből kapcsolva** Ez az intervallumtípus új karbantartási ütemezési sort hoz létre minden befejezett munkarendelés után. Egy karbantartási terv több sort is tartalmazhat az ilyen típusú intervallummal és ezek a sorok csatolva vannak. Általában olyan karbantartási tervet fog létrehozni, amely csak ilyen intervallumtípust tartalmazó karbantartásiterv-sorokat tartalmaz. A karbantartási ütemezés sorai úgy lesznek létrehozva, hogy azonosítva lesz az karbantartási tervsor, amelynek a legkorábbi a kezdő dátuma és időpontja. | Ez az intervallum-típus alapvetően a fenti „Kezdő dátumtól kapcsolva” változattal megegyezően működik. Az egyetlen különbség az a dátum, amelyen az intervallum alapul. A használt dátum az eszközön elvégzett utolsó munkarendelés tényleges záró dátuma és időpontja, *és* a karbantartási feladattípus/karbantartás feladattípus változata/szakma kombinációja. | Ez az intervallum-típus alapvetően a fenti „Kezdő dátumtól kapcsolva” változattal megegyezően működik. Az egyetlen különbség az a dátum, amelyen az intervallum alapul. A használt dátum az eszközön elvégzett utolsó munkarendelés tényleges záró dátuma és időpontja, *és* a karbantartási feladattípus/karbantartás feladattípus változata/szakma kombinációja. |
| **Intervallumtípus: Az összesített értéken (csak számláló) ismétlődve** A karbantartási terv futtatásakor mindig létrejön egy ütemezett karbantartási sor, amikor az eszközszámláló összesített értéke eléri az időszak gyakoriságát, vagy akár a többszörösét is. (Az időszak gyakoriságát a karbantartási sorban definiálja a rendszer.)<p>A funkció engedélyezésével és használatával kapcsolatos további tudnivalókat lásd a témakör későbbi, [Számlálón alapuló karbantartási fejlesztések](#counter-based-maintenance) című részében. | Nem alkalmazható | **Példa:** az AK-101 eszközhöz be van állítva egy óraszámláló. Az eszközhöz egy eszköztervsor is be van állítva. A sor intervallumtípusa *Az összesített értéken (csak számláló)* ismétlődik, és az időszak gyakorisága *1000*. A karbantartási terv futtatásakor a rendszer generál egy ütemezett karbantartási sort, ha a számláló összesített értéke meghaladja az 1000 órát. Ezután amikor a számláló összesített értéke meghaladja a 2000 órát, létrejön egy másik ütemezett karbantartási sor, és így tovább minden további 1000 órához. |
| **Intervallumtípus: Egyszer az összesített értéken (csak számláló)** A karbantartási terv futtatásakor létrejön egy ütemezett karbantartási sor, amikor az eszközszámláló összesített értéke eléri az időszak gyakoriságát, amelyet a karbantartási terv sorában határoztak meg.<p>A funkció engedélyezésével és használatával kapcsolatos további tudnivalókat lásd a témakör [Számlálón alapuló karbantartási fejlesztések](#counter-based-maintenance) című részében. | Nem alkalmazható | **Példa:** az AK-101 eszközhöz be van állítva egy óraszámláló. Az eszközhöz egy eszköztervsor is be van állítva. A sor intervallumtípusa *Egyszer az összesített értéken (csak számláló)*, és az időszak gyakorisága *1000*. A karbantartási terv futtatásakor a rendszer generál egy ütemezett karbantartási sort, ha a számláló összesített értéke meghaladja az 1000 órát. |

>[!NOTE]
>Amikor a karbantartási ütemezés sorait időalapú karbantartási tervsorokhoz hozza létre, a várható időpont mindig a nap kezdetén van. A számláló-alapú karbantartási terv soraiban a várható idő a nap folyamán bármikor lehet.

Az alábbiakban példákat talál az időalapú és a számláló alapú karbantartási terv sorainak beállítására:

**1. példa – Időalapú karbantartási tervsor:** Egy kenési feladatot egy hetente egyszer bekövetkező rögzített intervallumként is beállítható. Erre a célra válassza az „Ismétlődés a terv dátumától" beállítást az **Intervallum típusa** mezőben. Egy példa a következő ábrán látható.

![Egy rögzített intervallumként beállított szervizfeladat, amely hetente egyszer történik](media/02-preventive-maintenance.png "Egy rögzített intervallumként beállított szervizfeladat, amely hetente egyszer történik.")

**2. példa – Időalapú karbantartási tervsor:** Egy ellenőrzési feladat beállítható úgy, hogy hetente egyszer legyen elvégezve. Erre a célra válassza az „Ismételve az utolsó munkarendelésből” beállítást az **Intervallum típusa** mezőben. Egy példa a következő ábrán látható.

![Hetente egyszer legfeljebb egyszer elvégzendő, beállított ellenőrzési feladat](media/03-preventive-maintenance.png "Hetente egyszer legfeljebb egyszer elvégzendő, beállított ellenőrzési feladat")

**3. példa – Számláló-alapú karbantartási tervsor** : A következő óraszámláló grafikus illusztrációja, amelynek esetében 250 óra eltelte után egy új karbantartási ütemezési sor jön létre. Ennek a számláló-alapú sornak az intervallumtípusa „Ismétlődő a kezdő dátumtól”. A kezdő dátum a kapcsolódó eszköz kezdő dátuma az **Összes eszköz** részletek nézet \> **Eszközkarbantartási tervek** gyorslap \> **Kezdődátum** mezőjéből vagy a **Munkavégzési helyszín** részletek nézet \> **Karbantartási tervek** gyorslap \> **Kezdődátum** mezőjében. Ez egy példa a *megelőző* karbantartási tervre, hiszen a karbantartási ütemezési sor automatikusan létrejön a küszöb (+ 250) elérésekor.

![Óraszámláló, amely rendszeres időközönként karbantartási ütemezési sorokat hoz létre](media/04-preventive-maintenance.png "Óraszámláló, amely rendszeres időközönként karbantartási ütemezési sorokat hoz létre")

**4. példa – Számláló alapú karbantartási tervsora:** A következő grafika a számláló értékének csökkenésének illusztrációja, a fékbetétkopás méréséhez. A karbantartási ütemezéssor akkor jön létre, amikor 20 mm alatti számláló-bejegyzés jön létre a fékbetét esetében. Ennek a számláló alapú sornak az intervallumtípusa „Miután elérte lent” vagy „Egyszer a legutóbbi kezdődátumtól”. Ez egy példa a *beavatkozó* karbantartási tervre, hiszen a karbantartási ütemezési sor nem jön létre, amíg 20 mm alatti mérés nincs regisztrálva.

![A számláló értékének csökkenése, a fékbetét elhasználódásának mérése](media/05-preventive-maintenance.png "A számláló értékének csökkenése, a fékbetét elhasználódásának mérése")

**5. példa – Számlálóalapú karbantartási tervsor:** Egy -18 Celsiusfokos küszöbértéket tartalmazó grafikus illusztráció. A karbantartási ütemezési sor akkor jön létre, amikor a -18 ° Celsius-fok fölötti számlálóregisztrálás történik. Ennek a számláló-alapú sornak az intervallumtípusa „Miután elérte fent”. Ez egy példa a *beavatkozó* karbantartási tervre, hiszen a karbantartási ütemezési sor nem jön létre, amíg -18 Celsius fok feletti mérés nincs regisztrálva.

![-18 °C-os küszöbértékű számláló](media/06-preventive-maintenance.png "-18 °C-os küszöbértékű számláló")

- Új eszköz létrehozásakor, ha az eszköz egy karbantartási tervhez kapcsolódó eszköztípust használ, a karbantartási tervet a program automatikusan beilleszti az **Összes objektum \> Eszközkarbantartási tervek** gyorslapra. Ezenkívül a **Tárgyi eszközök alapértelmezései** helyen a **Karbantartási tervek** gyorslapon automatikusan beilleszti a kapcsolódó karbantartási terveket.
- Ha a **Karbantartási tervekben** eszköztípusokat vagy munkavégzési helyszíneket ad hozzá vagy távolít el, akkor ez a módosítás csak a módosítást követően létrejövő új eszközökre fog vonatkozni.
- Ha eszközöket vagy munkavégzési helyszíneket ad hozzá a **Karbantartási tervekhez**, akkor a módosítást automatikusan frissítve lesz az **Összes eszköz \> Összes karbantartási terv** gyorslapon az **Összes munkavégzési helyszín \> Karbantartási tervek** gyorslapon.

A következő illusztráción egy „Truck Service” karbantartási terv látható a **Karbantartási tervek** oldalon.

![Példa teherautó szerviz karbantartási tervére](media/07-preventive-maintenance.png "Példa teherautó szerviz karbantartási tervére")

## <a name="add-a-maintenance-plan-to-an-asset"></a>Karbantartási terv hozzáadása egy eszközhöz

1. Válassza ki az **Eszközkezelés \> Általános \> Eszközök \> Összes eszköz** vagy **Aktív eszközök** lehetőséget.

1. Válassza ki azt az eszközt, amelyhez be szeretné állítani a karbantartási tervet, és kattintson a **Szerkesztés** lehetőségre.

1. Az **Eszközkarbantartási tervek** gyorslapon válassza a **Sor Hozzáadása** lehetőséget, ha karbantartási terveket szeretne hozzáadni az eszközhöz.

1. A **Karbantartási terv** mezőben válassza ki a kapcsolódó karbantartási tervet.

1. A **Kezdődátum** mezőben válassza ki a dátumot, amelytől kezdve a megelőző karbantartási feladatok tervezése elkezdődhet. 

1. Válassza a **Mentés** lehetőséget. Az **Aktív** mező frissítése automatikusan történik.

A következő illusztráción karbantartási tervek láthatók egy eszközön beállítva, a **Minden eszköz** oldalon.

![Példa az eszközön beállított karbantartási tervekre](media/08-preventive-maintenance.png "Példa az eszközön beállított karbantartási tervekre")

<a id="counter-based-maintenance"></a>

## <a name="counter-based-maintenance-enhancements"></a>Számlálón alapuló karbantartási fejlesztések

A *Számlálón alapuló karbantartási fejlesztések* szolgáltatás a következő funkciókat tartalmazza:

- Lehetőség van arra, hogy eszköz létrehozásakor automatikusan beszúrjon egy *0* (nulla) értékű számlálót. Ez a lehetőség akkor lehet hasznos, ha számlálókon alapuló prediktív karbantartást használ. Ha nem használja a *Számlálón alapuló karbantartási fejlesztések* funkciót, manuálisan kell beszúrni a *0* (nulla) értékű számlálókat.
- A számláló konfigurálása úgy, hogy automatikusan alaphelyzetbe áll a munkarendelés befejezésekor. Ez a funkció akkor hasznos, ha a legutóbbi befejezett munkarendelés óta összesített érték alapján szeretne karbantartást ütemezni.
- A karbantartásiterv-intervallum egy új típusa, amelynek neve: *Az összesített értéken (csak számláló) ismétlődik*. Ez a típus karbantartást indít minden alkalommal, amikor egy összesített számláló eléri egy adott érték többszörösét. A karbantartás például 10 000 óránként indul el. A további tudnivalókat lásd: [Intervallumtípusok áttekintése](#interval-types) rész a témakör korábbi részében.
- A karbantartásiterv-intervallum egy másik új típusa, amelynek neve: *Egyszer az összesített értéken (csak számláló)*. Ez a típus karbantartást indít, amikor egy összesített számláló eléri egy adott érték többszörösét, például 8000 órát. A további tudnivalókat lásd: [Intervallumtípusok áttekintése](#interval-types) rész.

### <a name="turn-on-the-counter-based-maintenance-enhancements-feature"></a>A Számlálón alapuló karbantartási funkció bekapcsolása

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Tárgyieszköz-kezelés*
- **Funkció neve:** *Számlálón alapuló karbantartási fejlesztések*

### <a name="create-and-initialize-counters-when-an-asset-is-created"></a>Számlálók létrehozása és inicializálása eszköz létrehozásakor

Minden alkalommal, amikor létrehoz egy eszközt, automatikusan létre lehet hozni *0* (nulla) értékre inicializált, kapcsolódó eszközszámlálókat, feltéve, hogy be van állítva a rendszer, és az eszköz megfelelően van létrehozva.

1. Nyissa meg az **Eszközkezelés \> Beállítás \> Eszköztípusok** lehetőséget.
1. Győződjön meg arról, hogy a tervezett új eszköznek megfelelő eszköztípussal rendelkezzen. Igény szerint hozzon létre egy eszköztípust. Győződjön meg arról, hogy minden releváns számláló ki legyen választva a **Számlálók** gyorslapon.
1. Nyissa meg az **Eszközkezelés \> Beállítás \> Eszköztípusok \> Számlálók** lehetőséget.
1. Minden egyes releváns számlálónál ellenőrizze, hogy a **Teljes összesítés** mező beállítása *Összeg* legyen.
1. Hozza létre az eszközt az **Összes eszköz** lapon.
1. Állítsa az **Eszköztípus mezőt** a 2. lépésben azonosított vagy létrehozott eszköztípusra.
1. Szükség szerint fejezze be az új eszköz beállítását.
1. Nyissa meg az **Eszközkezelés \> Lekérdezések \> Eszközök \> Számlálók** lehetőséget. Keresse meg az új eszközhöz beállított inicializált számlálókat.

> [!NOTE]
> Az inicializált eszközszámlálók létrehozásakor az a feltételezés, hogy az eszközt még soha nem használták a rendszerhez való hozzáadása előtt. Amikor a karbantartási ütemezést az első alkalommal futtatják, a számítás a dátumot és a *0* nulla számlálóértéket használja kiindulási alapként a jövőbeli karbantartás kiszámításához. Ha az eszköz nem volt új, amikor hozzáadta a rendszerhez, manuálisan módosíthatja a számláló értékét úgy, hogy megegyezzen a tényleges számlálóértékkel. A számláló értékének módosításához nyissa meg a kívánt eszközt az **Összes eszköz** lapon, majd a Műveletpanel **Eszköz** lapján, a **Megelőző** csoportban válassza a **Számlálók** lehetőséget. A kijelölt eszköz **Eszközszámlálók** lapján szükség szerint módosítsa a kezdeti számlálórekord **Érték** oszlopában található értéket.

### <a name="automatically-reset-a-counter-value"></a>Számláló értékének automatikus alaphelyzetbe állítása

Beállíthatja, hogy a rendszer automatikusan alaphelyzetbe állítsa a számlálót, amikor a megfelelő munkarendelés eléri a kiválasztott állapotértéket.

1. Lépjen az **Eszközkezelés \> Beállítások \> Megelőző karbantartás \> Karbantartási tervek** elemre.
1. A lista ablaktáblán válasszon ki egy karbantartási tervet. A számláló alaphelyzetbe állítása minden olyan eszközre érvényes lesz, amelyik ezt a tervet használja.
1. A **Sorok** szakaszban keressen meg egy olyan eszközszámláló sort, amelyre vonatkozóan vissza szeretné állítani a számlálót, és jelölje be a **Számláló alaphelyzetbe állítása** jelölőnégyzetet a sorhoz. (Az eszköz számlálósorai értéket tartalmaznak a **Számláló** oszlopban. Az oszlopban megadott számláló az a számláló, amely alaphelyzetbe kerül a releváns eszközzel kapcsolatban.)
1. Válassza ki az **Eszközkezelés \> Beállítás \> Munkarendelések \> Életciklus-állapotok** elemet.
1. A lista ablaktáblán válassza ki azt a munkarendelés-életciklusállapotot, amelynél alaphelyzetbe kell állítani a megfelelő számlálót.
1. Az **Általános** gyorslapon állítsa a **Számláló alaphelyzetbe állítása** beállítást *Igen* értékre.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]