---
title: A biztonsági készlet napló használata a cikkek minimális fedezetének frissítésére
description: Ez a témakör azt ismerteti, hogyan lehet a biztonsági készlet naplóját használni a biztonsági készlet cikkmennyiségének frissítéséhez az előzménytranzakciók alapján kiszámított minimális fedezeti javaslatok alapján.
author: ChristianRytt
ms.date: 10/28/2021
ms.topic: article
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, ReqItemTableSetup, ReqItemTable, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-10-28
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 59e4959898cd961582e1ac1d2285c0c0867ee7af
ms.sourcegitcommit: bc9e75c38e192664cde226ed3a94df5a0b304369
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790975"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage-for-items"></a>A biztonsági készlet napló használata a cikkek minimális fedezetének frissítésére

[!include [banner](../../includes/banner.md)]

A biztonsági készlet a készletben tartott cikk további mennyiségét jelzi, ami csökkenti annak a kockázatot, hogy a cikkből készleten kell kimenni. A biztonsági készlet pufferként használható az értékesítési rendelések bevétele esetén, de a szállító nem tudja teljesíteni a vevő által kért szállítási dátumot.

Ez a témakör azt írja le, hogyan lehet a biztonsági készletnapló segítségével kiszámítani a korábbi tranzakciók alapján a minimális fedezeti javaslatokat, majd frissíteni a cikkfedezetet a javaslatokkal.

## <a name="overview-of-minimum-coverage-usage"></a>A minimális fedezeti kihasználtság áttekintése

A biztonsági készlet minden egyes cikkhez be van **·** állítva a cikkfedezeti lapon. A feltöltés különböző típusait különböző fedezeti kódok ábrázolják. (További tájékoztatás: [Biztonsági készlet teljesítése a](safety-stock-replenishment.md) cikkekhez.) Minden fedezeti kód azonban az egyes cikkekhez a Cikkfedezet lap Minimális mezőjében megadott értéket **·** **·** használja. A Minimum mező használata két fő **megközelítéssel** alkalmazható:

- **Minimális/maximális mennyiség a minimális/maximális célokra – ez a megközelítés a minimális mennyiséget és a** minimális/maximális logikát használja. Akkor érvényes, ha a Fedezetkód mező beállítása Min/Max az adott cikkre **·** vagy *·* fedezeti csoportra. A minimális mennyiség az átlagos napi felhasználásnak és a cikk átfutási idejének **·** szorzatát jelöli.
- **Készlettervi célokra használt minimális mennyiség – ez a megközelítés a minimális mennyiség alapján képviseli a készlettervet az** igény-előrejelzéssel kombinálva. Akkor érvényes, ha a Fedezetkód mező beállítása Időszak vagy Követelmény az adott **·** *·* *·* cikkhez vagy fedezetcsoporthoz. A minimális mennyiség egy olyan készlettervet jelent, amely a kívánt ügyfélszolgálati szintet tükrözi, hogy csökkentse a készlet- és részleges szállítmányokat, valamint a szállítás átfutási **·** időket. A minimális mennyiség az előrejelzés pontosságának bizonyos százalékát tükrözi egy adott cikkre. Nem egy kívánt készletpozíciónak megfelelő.

A **minimális** érték háromféleképpen lehet beállítani:

- Manuálisan a **Cikkfedezet** oldalon
- Az Adatkezelési keretrendszer *(Cikkfedezeti* adatentitások) szerint
- A biztonsági készlet naplók által végzett biztonsági készletszámítás által

## <a name="calculate-minimum-coverage-based-on-historical-usage"></a>A minimális fedezet számítása a korábbi használat alapján

A biztonságikészlet-naplók segítségével lehet kiszámítani a javasolt minimális mennyiséget a cikk múltbeli használata alapján, vagy a minimális/maximális, vagy a készlettervek céljából. A korábbi használat egy adott időszak minden kiadási tranzakcióját jelenti. Ilyen kiadási tranzakciók többek között az értékesítési rendelési tranzakciók és a készlethelyesbítások. A számítások meghatározzák továbbá a javasolt minimális mennyiség hatását a készletértékre, valamint a készletérték változását az aktuális minimális mennyiséghez képest.

Minden biztonságikészlet-naplósor egy cikket és annak fedezeti dimenzióit tartalmazza. Ezek a naplósorok létrejönnek, és megjelennek a Biztonsági **készlet naplósorai** lapon **(Alaptervezés \> – \> Futtatás biztonsági készlet \>** számítása). A biztonságikészlet-naplóknak a javasolt minimális mennyiségek kiszámításához való használatának üzleti folyamatát a témakör későbbi része ismerteti.

A tervező egy biztonságikészlet-napló segítségével számítja ki a kiválasztott cikkek javasolt minimális mennyiségét, a kiválasztott időszakokban korábbi használat alapján. A javasolt minimumok szükség esetén manuálisan felülbírálhatók, és lehetőség van a javasolt minimumok készletértékre gyakorolt lehetséges hatásának áttekintésre. A napló feladása esetén a cikkfedezetben társított minimális mennyiségek automatikusan frissülnek.

### <a name="create-a-new-safety-stock-journal-name"></a>Hozzon létre egy új biztonsági készlet napló nevet

Az ilyen típusú napló létrehozása előtt létre kell hoznia legalább egy biztonságinapló-nevet. Általában több naplónév is használható a biztonsági készlet számításának elválasztában.

1. Menjen az **Alaptervezés beállítása \> biztonsági készlet \> naplónevekkel kapcsolatos** lapra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az új sorban állítsa be a következő mezőket:

    - **Név** – adja meg a napló rövid nevét.
    - **Leírás** – a napló leírásának beírása.
    - **Felhasználói csoport sajátja – ha korlátozni kívánta az aktuális naplónév** célközönségét, válasszon egy felhasználócsoportot.
    - **Sorok törlése feladás után – ennek a jelölőnégyzetnek a bejelölve a feladáskor alapértelmezés szerint törölhetők** a naplósorok. Törölje a vonalat, ha minden feladott sort meg kell tartani.

    A Naplótípus mező írásra olvasható, és a Biztonsági készlet **beállítás van** *beolvasva.*

1. Zárja be a lapot.

### <a name="create-a-safety-stock-journal-and-lines"></a>Biztonsági készlet naplója és sorai

Ez a lépés naplót hoz létre, és automatikusan hozzáad sorokat. Minden sor azonosít egy cikket, fedezeti dimenzióit és a használati előzményekből kiszámított mennyiségeket. A számított mennyiségek tartalmazzák az átlagos cikkátfutási időt, az átlagos havi problémákat és a havi alapeltéréseket.

#### <a name="automatically-generate-journal-lines"></a>Naplósorok automatikus létrehozása

Naplósorokat csak akkor lehet automatikusan generálni, ha az aktuálisan látható naplóhoz nincsenek sorok.

A következő lépések szerint generálhat automatikusan naplósorokat.

1. Ugrás az **Alaptervezés futtatása \> biztonsági készlet \>\> számítása műveletre**
1. A Műveleti ablaktáblán kattintson az **Új** elemre. Létrejön egy új biztonságikészlet-napló.
1. A **Naplófejléc részletei** gyorslapon állítsa be a következő mezőket:

    - **Név** – válassza ki a biztonsági készlet naplónevét, amelybe a sort hozzá kell adni.
    - **Leírás** – az alapértelmezett érték a kiválasztott naplónév leírása. Szükség esetén azonban módosítható az érték.
    - **Sorok törlése feladás után – jelölje be ezt a jelölőnégyzetet, ha törölni szeretné a** naplósorokat a feladásukkor. Törölje a vonalat, ha minden feladott sort meg kell tartani. A beállítás a kiválasztott naplónévből öröklődik.

    A Napló mező írásra olvasható, és annak a naplónak az azonosítószámát jeleníti meg, amelybe sorokat hoz létre, és amelybe **·** sorokat ad hozzá.

1. A **Naplósorok** gyorslapon válassza a Sorok létrehozása lehetőséget **az** eszköztáron.
1. A **Naplósorok létrehozása a javasolt minimumkészlethez párbeszédpanelen állítsa be a** következő mezőket:

    - **Kezdő dátum – válassza ki annak az időszaknak a kezdő dátumát, amelybe a számításban figyelembe kell venni a** problémákat.
    - **Záró dátum – válassza ki annak az időszaknak a záró dátumát, amely időszakban a számításban figyelembe kell venni** a problémákat. Legalább két hónapnak kell lennie a kezdő és a záró dátum között.
    - **Alapeltérés számítása – az alapeltérés** kiszámításához állítsa *Igen* beállításra. A javaslat számítása esetén a Szolgáltatásszint használata beállítás csak Igen beállítással használható (a témakör későbbi témakörében ismertetett *·* **·** módon).

1. A Gyors gyorselemet is beleveendő rekordokban szűrők és megszorítások beállításával meghatározhatja, hogy mely **·** cikkek szerepeljenek a halmazban. (Szűrés például a következő szerint: **Fedezeti csoport** értéke.) A Szűrő kiválasztásával megnyithat egy szokásos lekérdezésszerkesztő párbeszédpanelt, ahol meghatározhatja a kiválasztási feltételeket, a rendezési feltételeket és az **·** illesztéseket. A mezők a Microsoft más típusú lekérdezéseihez is Dynamics 365 Supply Chain Management működnek.
1. A futtatás a háttérben gyorslapon adja meg, hogy kötegelt módban **futtassa-e a feladatot, és/vagy ismétlődő ütemezést** állítson be. A mezők ugyanúgy működnek, mint a Supply Chain Management más, [háttérben futó feladattípusai](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).
1. Válassza ki az **OK** lehetőséget. A sorok a készlettranzakciókkal kapcsolatos dimenziókhoz jön létre.

#### <a name="manually-add-or-remove-journal-lines"></a>Naplósorok manuális hozzáadása vagy eltávolítása

A naplósorokat bármikor manuálisan is hozzá lehet adni és/vagy el lehet távolítani (akár utána, akár a sorok automatikus generálása helyett). Használja a következő gombokat a Naplósorok **·** gyorslap eszköztárában:

- **Új** – új sor hozzáadása. Ezután mindegyik oszlopban adjon meg egy értéket, amely meghatározza, hogy a termékre kiszámítsa és alkalmazza az új minimumokat. Mivel a manuálisan hozzáadott sorokhoz nem állnak rendelkezésre javasolt minimális számítások, a sorokhoz nem jelennek meg új, kiszámított minimális **·** mennyiségértékek. Ezért manuálisan kell megadnia az **Új minimális mennyiség** értékét. Ugyanakkor látható, hogy az Új minimális mennyiség értéke milyen hatással lehet a készletértékre, illetve a készlet potenciális változását a jelenleg **·** megadott minimumhoz képest.
- **Törlés** – a kijelölt sor törlése.
- **Naplósorok** törlése – a napló minden sorának törlése.

### <a name="calculate-a-proposal"></a>Javaslat számítása

Ez a lépés kiszámít egy javasolt minimumot minden naplósorhoz, és a sornak a készletértékre gyakorolt lehetséges hatását. (A javasolt minimum a következőként jelenik meg: **Számított minimális** mennyiségérték.) A számítást a szükséges többször is el lehet végezni. A számítás frissíti az összes naplósorhoz megjelenő számított **·** minimális mennyiség értékét.

A megjelenő számítások mindaddig nem befolyásolják az egyes termékek tényleges minimális mennyiségértékét, amíg a Munkaablakban ki nem **·** választják a Post adatokat. Ebben az időpontban minden egyes termékre az Új minimális mennyiség **·** érték lesz érvényes.

1. Ugrás az **Alaptervezés futtatása \> biztonsági készlet \>\> számítása műveletre**
1. Nyissa meg azt a naplót, amelyhez javaslatot kell számítani. Másik lehetőségként hozzon létre egy új naplót a témakörben korábban ismertetett módon.
1. A **Naplósorok** gyorslapon válassza az eszköztár **Javaslat** számítása lehetőséget. (Nem kell kiválasztania sorokat.)
1. A Minimumkészlet-szint kiszámítása párbeszédpanelen állítsa **be a következő** mezőket:

    - **Átlagos kiadás használata az átfutási idő alatt – ezzel a beállítással a megadott időszak átlagos kiadásán alapuló számított minimális** **mennyiségértékeket** generálhat. Ezután a Szorzótényező mezőben adja meg azt az értéket, amely a kívánt **·** beállításnak megfelelően módosítja az eredményt. Például adjon meg 1,0-t a pontos számított átlaghoz, *·* vagy *1,1-et, ha további* 10 százalékos puffert szeretne hozzáadni.
    - **Szolgáltatásszint használata – akkor válassza ezt a lehetőséget, ha a kívánt szolgáltatási szint alapján ki szeretné számítani** a javasolt minimumot. Ezután a Szolgáltatásszint mezőben válassza ki a kívánt **·** szolgáltatási szintet.
    - **Átfutási idő rátát – adjon meg egy értéket, ezzel kiterjeszti a normál átfutási időt (például az** adminisztrációhoz).
    - **A kiszámított minimális mennyiség használata az új minimális mennyiségként – Állítsa Igen beállításra, ha a számítást követően automatikusan át másolja az értékeket a Számított minimális mennyiség oszlopból az Új minimális mennyiség oszlopba az összes** *·* **·** **·** sorhoz. Ha Nem értékre adja meg ezt a beállítást, a rendszer az összes sor Új minimális mennyiség oszlopba másolja az Aktuális minimális *·* mennyiség **·** **·** értéket. Ezt követően manuálisan kell szerkesztenie az **Új minimális mennyiség értékét a** kívántan.

1. A futtatás a háttérben gyorslapon adja meg, hogy kötegelt módban **futtassa-e a feladatot, és/vagy ismétlődő ütemezést** állítson be. A mezők ugyanúgy működnek, mint a Supply Chain Management más, [háttérben futó feladattípusai](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).
1. Válassza ki az **OK** lehetőséget. A számítás eredménye a Naplósorok gyorslap Számított **minimális mennyiség** **·** oszlopában látható. Jelenleg az értékek csak olyan javasolt értékek, amelyek még nincsenek alkalmazva a termékekre.

### <a name="update-minimum-quantity"></a>Frissítse a minimum mennyiséget

A biztonsági készlet naplójában bármelyik sort kiválaszthatja, és manuálisan felülbírálhatja annak Új minimális **mennyiség mezőjében szereplő** értéket.

1. Ugrás az **Alaptervezés futtatása \> biztonsági készlet \>\> számítása műveletre**
1. A szerkesztett napló megnyitása. Másik lehetőségként hozzon létre egy új naplót a korábban leírt módon.
1. A Naplósorok gyorslapon keresse meg a módosítandó sort, majd módosítsa az **·** Új minimális mennyiség **oszlopban szereplő** értéket. Beállíthatja például az Új minimális mennyiség értékét, hogy az megegyezett a Kiszámított **·** minimális mennyiség **·** értékével. Ha **a számított minimális mennyiség** értéke *0* (nulla), akkor megadhatja a kívánt jövőbeli értéket.

### <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Vigye fel az új minimum mennyiséget és ellenőrizze az eredményt

A következő lépések szerint heti az új minimális mennyiség feladott mennyiségét, és ellenőrizheti az eredményt.

1. Ugrás az **Alaptervezés futtatása \> biztonsági készlet \>\> számítása műveletre**
1. Napló megnyitása, amelybe az új minimális mennyiségek feladása szükséges. Másik lehetőségként hozzon létre egy új naplót a korábban leírt módon.
1. A műveleti ablaktáblán válassza ki a **Feladás** elemet.
1. A Napló feladása párbeszédpanelen állítsa be a Minden feladási hiba átvitele egy **·** új **·** naplómezőbe szükség szerint. Ezt követően az **OK** gombra a napló feladása.
1. Ha módosította egy sor Új minimális mennyiség értékét a Naplósorok gyorslapon, a következő lépésekkel erősítse meg **·** a **·** változtatást:

    1. A szerkesztett sorhoz válassza ki a hivatkozást a **Cikkszám** oszlopban.
    1. A Termékinformációk párbeszédpanelen válassza ki a hivatkozását a Cikkszám mezőben a kapcsolódó kiadott **·** **·** termékrekord megnyitásához.
    1. A Művelet panelen a **Tervezés** lapon, a **Fedezet** csoportban, kattintson a **Cikk fedezete** elemre.
    1. Ne figyelje meg, hogy a feladott biztonságikészlet-naplóval módosított hely és raktár minimális értéke módosult, hogy megfeleljen **·** a szerkesztésnek.

## <a name="additional-resources"></a>További erőforrások

- [Biztonsági készlet teljesítése cikkek számára](safety-stock-replenishment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
