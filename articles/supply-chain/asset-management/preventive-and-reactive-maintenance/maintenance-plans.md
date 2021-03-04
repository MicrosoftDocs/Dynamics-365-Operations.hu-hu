---
title: Karbantartási tervek
description: Ez a témakör az Eszközkezelés karbantartási terveit ismerteti.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 28c00b5a2485ffcc01a316d2a39e7259fb563d1d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429553"
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

Először létre kell hoznia a megelőző karbantartási feladatokhoz szükséges karbantartási terveket, és ki kell választania azokat a az eszköztípusokat, eszközöket, munkavégzési helyszíntípusokat és munkavégzési helyszíneket, amelyek az egyes karbantartási tervekhez kapcsolódnak. Ezt követően, ha szükséges, a karbantartási terveket hozzáadhat egy eszközhöz vagy egy munkavégzési helyszínhez is, amely Ezt az **Eszköz** > eszköz kijelölése > **Eszközkarbantartási tervek** gyorslapon, vagy a **Minden munkavégzési helyszín** > munkavégzési helyszín kiválasztása > **Karbantartási tervek** gyorslapon végezheti el.

Ha egy karbantartási tervet ad hozzá a eszköztípusokhoz vagy a munkavégzési helyszín típusokhoz, akkor ez azt jelenti, hogy amikor új eszközöket vagy munkavégzési helyszíneket hoz létre az ilyen eszköztípusokkal vagy munkavégzési helyszíntípusokkal, a program automatikusan hozzáadja az eszközt vagy a munkavégzési helyszínt a karbantartási tervhez. A karbantartási tervhez tartozó kezdődátum az aktuális dátum lesz, amelyet esetleg módosítani kell.

## <a name="set-up-maintenance-plans"></a>Karbantartási tervek beállítása

Ez a szakasz bemutatja, hogyan lehet beállítani a karbantartási terv sorait, és példákat kínál arra, hogy hogyan használhatók.

1. Kattintson az **Eszközkezelés** > **Beállítások** > **Megelőző karbantartás** > **Karbantartási tervek** elemre.

2. Új sorozat létrehozásához kattintson az **Új** gombra.

3. Szúrjon be egy azonosítót a **Karbantartási szekvencia** mezőbe és írjon be egy nevet a **Név** mezőbe.

4. A **Terv dátuma** mezőbe írja be azt a kezdő dátumot, amelytől kezdve a karbantartási tervben a tervezés végezhető. Ne feledje, hogy az időalapú karbantartási tervsorok rendelkezhetnek más tervezett dátumokkal.

5. A karbantartási terv aktiválásához válassza az „Igen” beállítást az **Aktív** választógombra kattintva.

>[!NOTE]
>Karbantartási terv inaktiválása esetén nem jönnek létre ütemezett közzétételek a karbantartási ütemezésben, amikor egy ütemezett karbantartásiterv feladatot futtat.

6. A **Tűréshatár napban előtte** és a **Tűréshatár napban utána** mezők olyan karbantartási tervsorokhoz kapcsolódnak, amelyekben az **Átfedő karbantartási feladatok kihagyása** jelölőnégyzet be van jelölve (lásd a 17. lépést). A „Tűréshatár” mezők kibővítik az intervallumot napokban, amikor több karbantartási terv átfedésben van, a legrészletesebb/legnagyobb feladat lesz karbantartási ütemezés sorként létrehozva karbantartási terve ütemezésekor, míg a gyakoribb, átfedő feladatok ki vannak hagyva a karbantartási terv ütemezése során. Adja meg a napok számát a **Tűréshatár napban előtte** mezőben, például „2”.

7. Ha megadott értéket adott meg a **Tűréshatár napban előtte** mezőben akkor adja meg a napok számát a **Tűréshatár napban utána** mezőbe is, például „2”.

>[!NOTE]
>Az ebben és az előző lépésben ismertetett példa azt jelenti, hogy ha több karbantartási tervsor átfedésben van , és egy vagy több sorhoz be van állítva az **Átfedő karbantartási feladatok kihagyása** lehetősége, akkor a karbantartási ütemezés sorainak kihagyott időszaka meghosszabbodik. összesen öt napra (a karbantartási ütemezés sorában szereplő várható kezdési dátum, *és* két nappal a dátum lőtt *és* két nappal a dátum után).

8. A **Részletek** gyorslap **Részletek** csoportjának mezői a karbantartási tervben beállított karbantartási terv sorainak számát, valamint a karbantartási tervhez kapcsolódó eszközök és munkavégzési helyszínek számát mutatják.

9. A **Sorok** gyorslapon kattintson az **Idő sor hozzáadása** vagy **Eszközszámláló sor hozzáadása** lehetőségre egy új karbantartásiterv-sor létrehozásához.

10. Adja meg a sor leírását a **Munkarendelés leírása** mezőbe. A program átviszi a leírást a kapcsolódó munkarendelésekre.

11. A **Karbantartási feladat típusa** mezőben válassza ki a feladattípust, amelyhez karbantartási terv sora kapcsolódik.

12. A **Karbantartási feladattípus változója** és a **Szakma** mezőben válassza ki a karbantartási feladattípushoz tartozó változatot és szakmát.

13. A **Befejezés ennyi nap múlva** és **Befejezés ennyi óra múlva** mezőkbe a várható záró dátumot napokban vagy órákban lehet beszúrni. A várható záró dátumot a karbantartási ütemezés sorainak létrehozásakor, a várható kezdődátumhoz viszonyítva szúrja be a rendszer. Beszúrhatja például a „7-es” számot a **Befejezés ennyi nap múlva** mezőben, ha a kapcsolódó feladatot a várható kezdő dátumtól egy héten belül kell végrehajtani.

14. Az **intervallum típusa** mezőben válassza ki, hogy milyen típusú intervallumot kíván használni a karbantartási terv sorában, például: „Ismétlődő…” vagy „egyszeri…”. Lásd az [Intervallumtípusok áttekintése](## Interval types overview) táblázatot alább az intervallum-típusok és a sorok típusának leírásáért.

15. Az **Időszak** mező csak időalapú sortípusokra vonatkozik. Válassza ki időszak gyakoriságához kapcsolódó időszak típusát.

16. Az **Időszak gyakorisága** mezőbe írja be, hogy hány alkalommal kell a sort használni a megelőző karbantartási feladatok megtervezéséhez. Példa: Ha létrehozott egy „számláló” típusú sort, és a számláló egy termelési mennyiség, és a „20000” szám szerepel ebben a mezőben, akkor a rendszer az új karbantartási szekvencia-sorokat hoz létre a megelőző karbantartás ütemezése során minden olyan alkalommal, amikor várhatóan további 20 000 cikk előállítása történik.

17. Az **Átfedő karbantartási feladatok kihagyása** jelölőnégyzet időalapú és számlálóalapú sortípusokra is vonatkozik. Jelölje be a jelölőnégyzetet, ha törölni szeretné az ugyanarra a dátumra létrehozott karbantartási ütemezések bejegyzéseit. Erre akkor van szükség, ha például egy 1 hónapos ellenőrzési sort, egy 6 hónapos ellenőrzési sort és egy 1 éves ellenőrzési sort hozott létre. Az 1 éves vizsgálatnál csak azt szeretné, ha csak annak a vizsgálatnak az elvégzése történne, nem pedig a másik két ellenőrzésé, amely az időkeretben esedékes lenne. A példa helyes beállításához be kell állítani az 1 éves ellenőrzési sort első sorként, a 6 hónapos sort második sorként, és az 1 hónapos sort harmadik sorként és be kell jelölnie **Átfedő karbantartási feladatok kihagyása** jelölőnégyzetet az 1 hónapos és 6 hónapos sorokhoz. Így biztosítható, hogy az 1 éves határelérésekor a program kihagyja az egy hónapos és hat hónapos ellenőrzést, és a karbantartási ütemezési sort csak az 1 éves ellenőrzési sorhoz hozza létre.

>[!NOTE]
>Az ebben a lépésben leírt példa azt mutatja, hogy a legátfogóbb feladatot, amely a legnagyobb számú feladatot tartalmazza, és amely nem olyan gyakran történik meg, mindig első sorként kell beszúrni. A gyakoribb feladatok ezután külön sorokként jelennek meg a gyakoriság sorrendjében, a leggyakrabban elvégzett feladattal a lista alján.

18. Az **Számláló** mező csak számlálóalapú sortípusokra vonatkozik. Válassza ki a sorhoz használt számláló típusát. Ha egy kapcsolódó eszköz esetében nem aktív a számláló típus, akkor a karbantartási terv sora ki lesz hagyva.

19. Az **Eszköz számláló időkerete napokban** mező csak a számláló típusú sorokra vonatkozik. Adjon meg egy számot, amely meghatározza, hogy a rendszer mennyi napra visszamenőleg ellenőrizze a számláló-regisztrációkat, amikor a karbantartási terv ütemezése elkészül. Ez azt jelenti, hogy a mennyi időre visszamenőlegesen használja a rendszer az adatokat (meglévő számláló-regisztrációk) annak a trendnek a kiszámításához, ami meghatározza, hogy karbantartásiütemezés-sor legyen létrehozva.

>*Példa:* Ha a számláló-regisztrációkat havonta egyszer szeretné elkészíteni, akkor ebbe a mezőbe beillesztheti a „365” számot, mert a karbantartási terv ütemezése mindig az elmúlt 12 hónapon fog alapulni, így a karbantartási ütemezés sorait az előző év trendje alapján kell létrehozni. Ha viszont ebbe a mezőbe a „10” számot illeszti be, akkor a számlálók regisztrációi gyakrabban történnek, például napi rendszerességgel. Ez azt jelenti, hogy a karbantartási terv ütemezésekor a program az utolsó 10 nap számláló-regisztrációit használja a karbantartásiütemezési sorok ütemezésének alapjául.

20. Az **Terv dátuma** mező csak időalapú sortípusokra vonatkozik. Ha a karbantartási terv sora a teljes karbantartási tervétől eltérő tervezési dátumot tartalmaz, válasszon ki egy dátumot **Terv dátuma** mezőben a sorban.

21. A **Szolgáltatási szint** mezőben kiválaszthatja a munkarendelés szolgáltatási szintjét, mint a karbantartási terv sorának további elválasztóját, amely szolgáltatási szintként használható a munkarendeléseken.

22. Jelölje be az **Automatikus létrehozás** jelölőnégyzetet, ha azt szeretné, hogy a karbantartási tervek ütemezésekor a program automatikusan létrehozza a kiválasztott karbantartási terv sora szerinti munkarendelést.

23. Ha bejelölte az **Automatikus létrehozás** jelölőnégyzetet, akkor az automatikusan létrehozott munkarendeléshez a **Munkarendelés típusa** mezőben kiválaszthatja a Munkarendelés típusát. Ha bejelölte az **Automatikus létrehozás** jelölőnégyzetet, és ebben a mezőben nem választ munkarendelés-típust, akkor az **Eszközkezelés** > **Beállítás** > **Eszköz kezelési paraméterek** > **Munkarendelések** hivatkozás > **Megelőző munkarendelés típusa** mező lesz használva.

24. Az **Időszak kezdete** és **Időszak** vége mezőkkel ismétlődő, időalapú karbantartási tervsort hozhat létre egy 12 hónapos időszakon belül. *Példa:* A zöldterületek fenntartására használt berendezésekhez minden tavasszal egy előre megadott időszakon belül szervizre van szükség. Az időszak kezdő dátumát szúrja be az **Időszak kezdete** mezőbe.

25. Az időszak befejező dátumát szúrja be az **Időszak vége** mezőbe.

26. A **Létrejövő időszak** mezőbe az aktuálisan megismételni kívánt időszak jelenik meg. Amikor az aktuális időszak eltelt, és új évet kezd, az ebben a mezőben megjelenő időszakot frissíti a program, hogy az megfeleljen a következő időszaknak az ismétlési sorozatban.

27. Az **Eszközök** gyorslapon válassza ki azokat az eszközöket amelyek az adott karbantartási tervhez kapcsolódnak:

28. Az **Eszköztípusok** gyorslapon válassza ki azokat az eszköztípusokat amelyek az adott karbantartási tervhez kapcsolódnak:

29. Az **Munkavégzési helyszínek** gyorslapon válassza ki azokat az munkavégzési helyszíneket, amelyek az adott karbantartási tervhez kapcsolódnak: Ha szükséges, a megfelelő eszköz típusának, gyártójának és modelljének kiválasztásával pontosabban is megadhatja a beállításokat.

30. Az **Munkavégzési helyszíntípusok** gyorslapon válassza ki azokat az munkavégzési helyszíntípusokat, amelyek az adott karbantartási tervhez kapcsolódnak:

>[!NOTE]
>Ha a munkarendelések létrehozása manuálisan, egyszállítói garanciával fedezett eszközhöz történik, egy párbeszédpanel jelenik meg, amely a felhívja a felhasználó figyelmét a jótállásra. A munkarendelés létrehozása ezt követően visszavonható. Az automatikusan létrehozott munkarendelések a jótállási kapcsolat keresése ki van hagyva.

## <a name="interval-types-overview"></a>Intervallumtípusok áttekintése

| Intervallum típusa és leírása                                                                                                                                                                                                                                                                                                                                                                                                       | Sor típusa: Idő                                                                                                                                                                                                                                                                                                                                                           | Sor típusa: számláló                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Intervallum típusa: Megismételve a terv dátumától** A számolás a használt tervdátumtól kezdődik. A karbantartási tervek ütemezésekor létrejön egy karbantartási ütemezési sor az intervallum elérésekor.                                                                                                                                                                                                                | A **Terv dátuma** a karbantartási sorban lesz használva. Ha nincs kiválasztva a terv dátuma a sorban, akkor a karbantartási terv **Tervdátumát** használja a rendszer. Példa: ha a 3-as szám szerepel az **Időszaki gyakorisága** mezőben, és az „Év" beállítás van kiválasztva az **Időszak** mezőben, akkor az új karbantartási ütemezési sor egyszer jön létre 3 évente.                             | A **Terv dátuma** a karbantartási sorhoz használva van. Ha a számlálót lecserélték, a program a legutóbbi cseredátumot használja a terv dátumaként.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Intervallum típusa: Ismétlődő a kezdődátumtól** A számlálás az eszköz kapcsolatának kezdődátumától kezdődik. A dátum az **Összes eszköz** részletek nézet > **Eszközkarbantartási tervek** gyorslap > **Kezdődátum** mezőjéből vagy az **Összes munkavégzési helyszín** részletek nézet> **Karbantartási tervek** gyorslap > **Kezdődátum** mezőjéből lesz kiválasztva. A karbantartási tervek ütemezésekor létrejön egy karbantartási ütemezési sor az intervallum elérésekor. | Az eszköz vagy munkavégzési helyszín karbantartási sorának kezdődátuma lesz használva. Ha ez a mező üres, a karbantartási tervhez tartozó **Tervdátum** használatos.                                                                                                                                                                                                 | Az eszköz vagy munkavégzési helyszín karbantartási sorának kezdődátuma lesz használva. Ha ez a mező üres, a karbantartási tervhez tartozó **Tervdátum** használatos.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Intervallum típusa: Ismételve az utolsó munkarendelésből** A számlálás a legutóbbi elvégzett munkarendelés tényleges záró dátumától és idejétől, és a konkrét karbantartási feladattípus, karbantartási feladattípus változat- és a szakmakombinációtól kezdődik. Ez a dátum és **az idő a Tényleges befejezés** mezőben átható a **Minden munkarendelés** részletei nézetben.                                                                                                                                 | Az eszközön elvégzett Munkarendelés tényleges záró dátuma és időpontja, és a konkrét karbantartási feladattípus/karbantartás feladattípus változata/szakma kombinációja. Ha nem található befejezett munkarendelés, akkor a program a fentebb ismertetett „Ismétlődő a kezdődátumtól” intervallumtípusnál használt dátumot használja.                                                                                             | Az eszközön elvégzett Munkarendelés tényleges záró dátuma és időpontja, *és* a karbantartási feladattípus/karbantartás feladattípus változata/szakma kombinációja. Lesz használva. Ha a munkarendelésben a kezdő és befejező dátumot üresen hagyták, akkor a program a fentebb ismertetett „Ismétlődő a kezdődátumtól” intervallumtípusnál használt dátumot használja.                                                                                                                                                                                                                                                                                                                                                                           |
| **Intervallum típusa: Egyszer a terv dátumától** Lásd az „Ismétlődő a tervdátumtól" intervallum leírását fent. Ez egyetlen különbség az, hogy ez az intervallum csak egyszer lesz használva.                                                                                                                                                                                                                                                   | Lásd az „Ismétlődő a terv dátumától" típusú intervallum leírását fent. Ez az intervallum általában egy egyszeri karbantartási vagy szervizfeladathoz használatos.                                                                                                                                                                                                                             | Lásd az „Ismétlődő a terv dátumától" típusú intervallum leírását fent. Ez az intervallum általában egy egyszeri karbantartási vagy szervizfeladathoz használatos. **1. Megjegyzés** : Ez az intervallumtípus csak akkor érvényes, ha a számlálót minden karbantartási vagy szolgáltatási feladat végrehajtása alkalmával kicserélik. Ha valamilyen oknál fogva a számlálót a tervezett időszak vége előtt cserélte le a program, akkor a számláló cseréjének idejétől a feladatra vonatkozóan új idő lesz kiszámítva. **2. megjegyzés** : Ha a számlálót a karbantartás vagy a szolgáltatás feladatának végrehajtásakor cserélik ki, akkor ez az intervallum a fenti „Ismétlődő a terv dátumától" szerint működik.                                             |
| **Intervallum típusa: Egyszer a kezdődátumtól** Lásd az „Ismétlődő a kezdődátumtól" intervallum leírását fent. Ez egyetlen különbség az, hogy ez az intervallum csak egyszer lesz használva.                                                                                                                                                                                                                                                 | Lásd az „Ismétlődő a kezdődátumától" típusú intervallum leírását fent. Ez az intervallum általában egy egyszeri karbantartási vagy szervizfeladathoz használatos.                                                                                                                                                                                                                            | Lásd az „Ismétlődő a kezdődátumától" típusú intervallum leírását fent. Ez az intervallum általában egy egyszeri karbantartási vagy szervizfeladathoz használatos. A fenti **1. megjegyzés**: erre az intervallumtípusra is vonatkozik. **3. megjegyzés** : Ha a számlálót a karbantartás vagy a szolgáltatás feladatának végrehajtásakor cserélik ki, akkor ez az intervallum a fenti „Ismétlődő a kezdődátumtól” szerint működik.                                                                                                                                                                                                                                                                                                |
| **Intervallum típusa: Miután elérte fent** Ezt az intervallumtípust csak a számlálókra vonatkozik, és a karbantartási terv sorában megadott felső határérték jelzésére szolgál. A karbantartási ütemezés bejegyzései tartalmazzák a számláló regisztrációjának várható kezdő dátumát és időpontját, amely azt jelenti, hogy ezek a bejegyzések a kezdő dátummal megegyező vagy annál korábbi értékkel fognak létrejönni.                                                | N.a.                                                                                                                                                                                                                                                                                                                                                                       | A számláló intervalluma egy felső határt jelez. Ha ezt a korlátot túllépik a számlálóregisztráció létrehozásakor, megelőző karbantartás ütemezésekor jön létre egy karbantartási ütemezési sor.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Intervallum típusa: Miután elérte lent** Ezt az intervallumtípust csak a számlálókra vonatkozik, és a karbantartási terv sorában megadott alsó határérték jelzésére szolgál. A karbantartási ütemezés bejegyzései tartalmazzák a számláló regisztrációjának várható kezdő dátumát és időpontját, amely azt jelenti, hogy ezek a bejegyzések a kezdő dátummal megegyező vagy annál korábbi értékkel fognak létrejönni.                                                 | N.a.                                                                                                                                                                                                                                                                                                                                                                       | A számláló intervalluma egy alsó határt jelez. Ha ezt a korlátot elérik a számlálóregisztráció létrehozásakor, megelőző karbantartás ütemezésekor jön létre egy karbantartási ütemezési sor.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Intervallum típusa: Kezdő dátumtól kapcsolva** Ez az intervallumtípus csak egyszer hoz létre egy karbantartási ütemezési sort. Egy karbantartási terv több karbantartásiterv-sort is tartalmazhat az ilyen típusú intervallummal és ezek a sorok csatolva vannak. Általában olyan karbantartási tervet fog létrehozni, amely csak ilyen intervallumtípust tartalmazó sorokat tartalmaz. A karbantartási ütemezés sorai úgy lesznek létrehozva, hogy azonosítva lesz az karbantartási tervsor, amelynek a legkorábbi a kezdő dátuma és időpontja.                                                                                                                                                                                                                                                                                                                                                                                           | Lásd az „Egyszer a kezdődátumától" típusú intervallum leírását fent. Példa:Agy karbantartási tervben két sort hoz létre egy szervizfeladathoz egy autó esetében: egy idő-alapú sort egy 1 éves időszakkal, és egy számláló alapú sort pedig 25 000 km-es határértékkel. A program létrehoz egy karbantartási ütemezési sort az elsőként elért korláthoz. Ehhez a sortípushoz egy 1 éves időszakkal hoz létre sort.                                                                                                                                                                                   | Lásd az „Egyszer a kezdődátumától" típusú intervallum leírását fent. Példa:Agy karbantartási tervben két sort hoz létre egy szervizfeladathoz egy autó esetében: egy idő-alapú sort egy 1 éves időszakkal, és egy számláló alapú sort pedig 25 000 km-es határértékkel. A program létrehoz egy karbantartási ütemezési sort az elsőként elért korláthoz. Ehhez a sortípushoz egy 25 000 km-es határértéket hoz létre. Példa két számláló sor létrehozására: Beállíthatja egy karbantartási tervet két összekapcsolt számlálóalapuló sorral amelyeknél az első sor 10 000-es legyártott mennyiséget tartalmaz, és a második sor egy gépre vagy munkaközpontra vonatkozik, amelyhez 3000 üzemóra után szükséges szerviz.                                                                                                                                                           |
| **Intervallum típusa: Az utolsó munkarendelésből kapcsolva** Ez az intervallumtípus új karbantartási ütemezési sort hoz létre minden befejezett munkarendelés után. Egy karbantartási terv több sort is tartalmazhat az ilyen típusú intervallummal és ezek a sorok csatolva vannak. Általában olyan karbantartási tervet fog létrehozni, amely csak ilyen intervallumtípust tartalmazó karbantartásiterv-sorokat tartalmaz. A karbantartási ütemezés sorai úgy lesznek létrehozva, hogy azonosítva lesz az karbantartási tervsor, amelynek a legkorábbi a kezdő dátuma és időpontja.                                                                                                                                                                                                                                                                        | Ez az intervallum-típus alapvetően a fenti „Kezdő dátumtól kapcsolva” változattal megegyezően működik. Az egyetlen különbség az a dátum, amelyen az intervallum alapul. A használt dátum az eszközön elvégzett utolsó munkarendelés tényleges záró dátuma és időpontja, *és* a karbantartási feladattípus/karbantartás feladattípus változata/szakma kombinációja.                                                                                                                                                                                                                                                           | Ez az intervallum-típus alapvetően a fenti „Kezdő dátumtól kapcsolva” változattal megegyezően működik. Az egyetlen különbség az a dátum, amelyen az intervallum alapul. A használt dátum az eszközön elvégzett utolsó munkarendelés tényleges záró dátuma és időpontja, *és* a karbantartási feladattípus/karbantartás feladattípus változata/szakma kombinációja.                                                                                                                   |


>[!NOTE]
>Amikor a karbantartási ütemezés sorait időalapú karbantartási tervsorokhoz hozza létre, a várható időpont mindig a nap kezdetén van. A számláló-alapú karbantartási terv soraiban a várható idő a nap folyamán bármikor lehet.

Az alábbiakban példákat talál az időalapú és a számláló alapú karbantartási terv sorainak beállítására:

**1. példa – Időalapú karbantartási tervsor:** Egy kenési feladatot egy hetente egyszer bekövetkező rögzített intervallumként is beállítható. Erre a célra válassza az „Ismétlődés a terv dátumától" beállítást az **Intervallum típusa** mezőben. Egy példa a következő ábrán látható.

![1. ábra](media/02-preventive-maintenance.png)

**2. példa – Időalapú karbantartási tervsor:** Egy ellenőrzési feladat beállítható úgy, hogy hetente egyszer legyen elvégezve. Erre a célra válassza az „Ismételve az utolsó munkarendelésből” beállítást az **Intervallum típusa** mezőben. Egy példa a következő ábrán látható.

![2. ábra](media/03-preventive-maintenance.png)

**3. példa – Számláló-alapú karbantartási tervsor** : A következő óraszámláló grafikus illusztrációja, amelynek esetében 250 óra eltelte után egy új karbantartási ütemezési sor jön létre. Ennek a számláló-alapú sornak az intervallumtípusa „Ismétlődő a kezdő dátumtól”. A kezdő dátum a kapcsolódó eszköz kezdő dátuma az **Összes eszköz** részletek nézet > **Eszközkarbantartási tervek** gyorslap > **Kezdődátum** mezőjéből vagy az **Munkavégzési helyszín** részletek nézet> **Karbantartási tervek** gyorslap > **Kezdődátum** mezőjében. Ez egy példa a *megelőző* karbantartási tervre, hiszen a karbantartási ütemezési sor automatikusan létrejön a küszöb (+ 250) elérésekor.

![3. ábra](media/04-preventive-maintenance.png)


**4. példa – Számláló alapú karbantartási tervsora:** A következő grafika a számláló értékének csökkenésének illusztrációja, a fékbetétkopás méréséhez. A karbantartási ütemezéssor akkor jön létre, amikor 20 mm alatti számláló-bejegyzés jön létre a fékbetét esetében. Ennek a számláló alapú sornak az intervallumtípusa „Miután elérte lent” vagy „Egyszer a legutóbbi kezdődátumtól”. Ez egy példa a *beavatkozó* karbantartási tervre, hiszen a karbantartási ütemezési sor nem jön létre, amíg 20 mm alatti mérés nincs regisztrálva.

![4. ábra](media/05-preventive-maintenance.png)


**5. példa – Számlálóalapú karbantartási tervsor:** Egy -18 Celsiusfokos küszöbértéket tartalmazó grafikus illusztráció. A karbantartási ütemezési sor akkor jön létre, amikor a -18 ° Celsius-fok fölötti számlálóregisztrálás történik. Ennek a számláló-alapú sornak az intervallumtípusa „Miután elérte fent”. Ez egy példa a *beavatkozó* karbantartási tervre, hiszen a karbantartási ütemezési sor nem jön létre, amíg -18 Celsius fok feletti mérés nincs regisztrálva.

![5. ábra](media/06-preventive-maintenance.png)

- Új eszköz létrehozásakor, ha az eszköz egy karbantartási tervhez kapcsolódó eszköztípust használ, a karbantartási tervet a program automatikusan beilleszti az **Összes objektum** > **Eszközkarbantartási tervek** gyorslapra. Ezenkívül a **Tárgyi eszközök alapértelmezései** helyen a **Karbantartási tervek** gyorslapon automatikusan beilleszti a kapcsolódó karbantartási terveket.  
- Ha a **Karbantartási tervekben** eszköztípusokat vagy munkavégzési helyszíneket ad hozzá vagy távolít el, akkor ez a módosítás csak a módosítást követően létrejövő új eszközökre fog vonatkozni.  
- Ha eszközöket vagy munkavégzési helyszíneket ad hozzá a **Karbantartási tervekhez**, akkor a módosítást automatikusan frissítve lesz az **Összes eszköz** > **Összes karbantartási terv** gyorslapon az **Összes munkavégzési helyszín** > **Karbantartási tervek** gyorslapon.  

A következő illusztráción egy „Truck Service” karbantartási terv látható a **Karbantartási tervek** oldalon.

![6. ábra](media/07-preventive-maintenance.png)


## <a name="add-a-maintenance-plan-to-an-asset"></a>Karbantartási terv hozzáadása egy eszközhöz

1. Kattintson az **Eszközök kezelése** > **Közös** > **Eszközök** > **Minden eszköz** vagy **Aktív eszközök** lehetőségre.

2. Válassza ki azt az eszközt, amelyhez be szeretné állítani a karbantartási tervet, éskattintson a **Szerkesztés** lehetőségre.

3. Az **Eszközkarbantartási tervek** gyorslapon válassza a **Sor Hozzáadása** lehetőséget, ha karbantartási terveket szeretne hozzáadni az eszközhöz.

4. A **Karbantartási terv** mezőben válassza ki a kapcsolódó karbantartási tervet.

5. A **Kezdődátum** mezőben válassza ki a dátumot, amelytől kezdve a megelőző karbantartási feladatok tervezése elkezdődhet. 

6. Kattintson a **Mentés** gombra. Az **Aktív** mező frissítése automatikusan történik.

A következő illusztráción karbantartási tervek láthatók egy eszközön beállítva, a **Minden eszköz** oldalon.

![7. ábra](media/08-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]