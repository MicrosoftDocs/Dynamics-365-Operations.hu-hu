---
title: Helyutasítások létrehozása
description: Ez a témakör ismerteti, hogy hogyan kell helyutasításokat létrehozni. A helyutasítások olyan a felhasználó által megadott szabályok, melyek segítik a kitárolási és betárolási helyek meghatározását a készletmozgatáshoz.
author: Mirzaab
manager: tfehr
ms.date: 07/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-28
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: bdd99b5faefd7054023b45a91fad070aac055a26
ms.sourcegitcommit: ecad92c9cb7e9e57688e678f79f747673c921df5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2020
ms.locfileid: "3692138"
---
# <a name="create-location-directives"></a>Helyutasítások létrehozása

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti, hogy hogyan kell helyutasításokat létrehozni. A helyutasítások olyan a felhasználó által megadott szabályok, melyek segítik a kitárolási és betárolási helyek meghatározását a készletmozgatáshoz. Például egy értékesítési rendelés tranzakciója esetén a helyutasítás meghatározza, hogy hol kerül az adott cikk felvételre, és hogy a felvett cikk hová kerül.

> [!NOTE]
> Ez a témakör a **Raktárkezelés** modul egyes funkcióira vonatkozik. Ez nem vonatkozik az [Árukészletkezelés kezelése](../inventory/inventory-home-page.md) modul egyes funkcióira.

Helyutasítások segítségével elvégezheti az alábbi feladatokat:

- Bejövő cikkek betárolása.
- Cikkek kitárolása és előkészítése a kimenő tranzakciókhoz.
- Nyersanyagok ki- és betárolása a termeléshez.
- Üres helyek feltöltése.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt helyutasítási műveletet hozhatna létre, követnie kell az alábbi lépéseket, hogy megbizonyosodhasson, hogy az előfeltételek adottak.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Raktárak** pontra.
1. Raktár létrehozása.
1. A **Raktár** gyorslapon állítsa a **Raktárkezelési folyamatok alkalmazása** opciót *Igen*-re.
1. Helyek, helytípusok, helyprofilok és helyformátumok létrehozása. A további tudnivalókért lásd: [Helyek konfigurálása WMS szolgáltatással rendelkező raktárban](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).
1. Helyek, zónák és zónacsoportok létrehozása. A további tudnivalókért lásd: [Raktár beállításai](https://docs.microsoft.com/dynamics365/commerce/channels-setup-warehouse) és [Helyek konfigurálása WMS szolgáltatással rendelkező raktárban](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).

## <a name="setup"></a>Beállítás

### <a name="create-location-directives"></a>Helyutasítások létrehozása

Helyutasítás létrehozásához kövesse az alábbi lépéseket.

1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. A lista ablakban állítsa a **Munkarendelés típusa** mezőt annak a készlettranzakciónak a típusára, amelyhez helyutasítást létrehozott.
1. A Műveleti Panelen válassza az **Új** lehetőséget új helyutasítás létrehozásához.
1. Az új helyutasításhoz állítsa a be mezőket az alábbi táblában megadott mód szerint.

    | Mező | Leírás |
    |---|---|
    | Sorszám | Adjon meg egy egész számot, amely megmutatja a helyutasítás sorban elfoglalt helyét. A sorrend meghatározó, amikor minden helyutasítás a választott munkarendelés-típus esetén kerül feldolgozásra. |
    | Név | Adja meg a helyutasítás nevét. | 
    | Munka típusa | Adja meg a munkatípust, mely elvégzésre kell kerüljön. Az értékek listája a készlettranzakciótól függ, melyet **Munkarendelés típusa** mezőben adott meg. Az alábbi értékek lehetségesek:<ul><li>**Elhelyezés** – a helyutasítás igyekszik megtalálni a legjobb helyet a készlet elhelyezésére, vagy fellelésére, ami a rendszerbe kerül a bevételezés, a termelés és a készlethelyesbítések által. A helyutasítás arra is használható, hogy megadhasson vele egy elhelyezési helyet vagy egy végső öböl ajtó szállítási helyet a kimenő forgalomban.</li><li>**Felvétel** – a helyutasítás igyekszik megtalálni a legjobb helyeket a készlet fizikai lefoglalásához (munka létrehozása). A kitárolás akkor is végrehajtható (azaz a kitárolási munkasor bezárható), ha a munka nem fejeződött be. A felhasználó végrehajthatja a fizikai kitárolást. A rendszerben ez a művelet egy kitárolási lépés. A felhasználó ezután megszakíthatja a folyamatot egy mobileszközről, és befejezheti a munkát (például egy kitárolással) később. Azonban a munkafejléc bezárása akkor történik meg, ha befejeződött a végső betárolás.</li><li>**Leltározás**, **Módosítások**, **Súgó**, **Készletállapot módosítása**, **Azonosítótábla felépítése**, **Nyomtatás**, **Állapot változtatása** és **Csomagolás beágyazott azonosítótáblák** – Ezek az értékek nem használhatók a helyutasítások beállítása során.</li></ul> |
    | Hely | Válassza ki a helyet, ahol a munka elvégzendő. |
    | Raktár | Válassza ki a raktárhelyet, ahol a munka elvégzendő. |
    | Utasításkód | Válasszon egy utasítási kódot, hogy irányíthassa a helyutasításokat, melyek a munkasablon által megadott sorokhoz tartoznak, amit a kód rendelt hozzájuk. Az **Utasításkód** lapján új kódokat hozhat létre, amelyeket a munkasablonok helyutasításokkal való összekötésére használhat. Arra is használhatja ezt az oldalt, hogy kezelje a hivatkozásokat a munkasablonok és helyutasítások között (mint például a raktárajtó vagy a köztes hely). Az utasításkódok munkasablonokkal való összekapcsolásával kapcsolatos további információkat lásd: [Raktári munka ellenőrzése munkasablonok és helyutasítások használatával](control-warehouse-location-directives.md).<p>Ha egy utasításkód meg van adva, amikor szükség van egy munka létrehozására, a rendszer helyutasításokat fog keresni a sorrend helyett az utasításkód alapján. Ilyen módon precízebben kezelheti a helysablonokat, melyek a munkasablonok specifikus lépéseként használatosak, mint például az anyagok előkészítése az egyes lépésekhez.</p> |
    | Intézkedési kód | Válasszon egy intézkedési kódot, hogy átirányíthassa egy cikk betárolását egy adott helyre. (További tájékoztatásért lásd: [Intézkedési kódok beállítása](tasks/set-up-dispositions-codes.md).) Ez a mező csak akkor érhető el, ha a **Munkarendelés típusa** *Beszerzési rendelések*, *Visszárurendelések* vagy *Késztermékek betárolása* funkcióra van állítva. |
    | Több raktározási egység | Állítsa ezt a lehetőséget *Igen*-re, hogy a több raktározási egység (SKU) funkció használatához egy adott helyen. Például ez a lehetőség *Igen* opcióra kell legyen beállítva a raktárajtóhoz.<p>Ha a **Több termékváltozat** lehetőség *Igen* értékre van állítva, a betárolási hely a munka során lesz megadva (a várakozásnak megfelelően). A betárolási hely azonban csak akkor képes több elem betárolását kezelni, ha a munka különböző raktározási egységeket tartalmaz, amelyeket ki- vagy be kell tárolni, akkor nem ha az elvégzendő munka csak egyetlen raktározási egységet tartalmaz, amit be kell tárolni.</p><p>Ha a **Több termékváltozat** lehetőség *Nem*-re van állítva, akkor a betárolási hely csak akkor van megadva, ha az elhelyezésnek csak egyféle termékváltozata van.</p><p>Ha mindkét módszert használni szeretné, akkor két olyan sort kell megadni, amelyeknek ugyanaz a szerkezete és beállítása, de ehhez állítsa a **Több termékváltozat** lehetőséget *Igen*-re az egyik sorhoz és *Nem*-et a másikhoz. Más szóval két egyforma helyutasítás szükséges a késleltetett feldolgozáshoz, ezen kívül Önnek nem szükséges megkülönböztetni az egy vagy több termékváltozatot a munkaazonosítónál. Meg kell adnia egy helyutasítási műveletet a kitároláshoz, ha egynél több tétel szerepel a rendelésében.</p><p>**Megjegyzés:** Ha **Több termékváltozat**-ot ad meg *Igen* lehetőséggel a helyutasítási művelethez az *Elhelyezés* munkatípus esetén, az első helyutasítási sort mindig a rendszer fogja kiválasztani a sorban létrehozott egyéb korlátozásoktól függetlenül.</p> |

1. Tetszőleges: A műveleti panelen válassza a **Lekérdezés szerkesztése** lehetőséget, hogy választhasson helyeket, vagy megadhasson újakat, amelyek alkalmazhatók lesznek, amikor adott helyszín-irányelvet választ.
1. A **Sorok** gyorslapon hozzon létre egy vagy több sort, hogy megadhassa az egyégeket, és elhelyezhesse vagy lefoglalhassa a mennyiséget egy raktárban.
1. Minden egyes új soron állítsa be a mezőket, az alábbi táblában megadott módon.

    | Mező | Leírás |
    |---|---|
    | Sorszám | Adjon meg egy egész számot, amely megmutatja a helyutasítás sorban elfoglalt helyét. A sorrend meghatározó, amikor minden helyutasítás a választott munkatípus esetén kerül feldolgozásra. |
    | Forrásmennyiség | Határozza meg a kezdőmennyiség értékét, amikor a középső-rács sorrendjét kell kiválasztani. Az **Egység** mezőben adja meg a mennyiséghez tartozó mértékegységet. |
    | Záró mennyiség | Adja meg a záró mennyiségtartományt, amikor a középső-rács sorrendjét kell kiválasztani. Az **Egység** mezőben adja meg a mennyiséghez tartozó mértékegységet. |
    | Egység | A cikk mértékegységének kiválasztása.<p>Megadhatja a minimális és maximális mennyiséget, amire az utasítás vonatkozik. Úgy is megadhatja az utasítást, hogy az egy adott készletmennyiségre vonatkozzon. Az **Egység** mező csak a mennyiség értékelésénél használatos.</p><p>Meghatározni, hogy egy hely vagy egy helyutasítássor érvényes, a rendszer értékeli a mennyiségeket az **Egység** értékhez mérten, ami a soron van megadva. Minden alkalommal, amikor egy helyutasítási sor elérhető, a rendszer megpróbálja konvertálni a kereseti egységet, ami a sorban van megadva. Ha a mértékegység-átváltás nem létezik, a rendszer tovább halad a következő sorra.</p> |
    | Mennyiség megkeresése | Ez a mező csak akkor érvényes, ha megpróbál eltárolni, vagy megkeresni egy adott mennyiséget a raktárban. Más szóval a művelet csak a *Betárolás* funkcióra érvényes. Válassza ki a módszert, amivel szeretné kiértékelni, hogy a mennyiség a **Forrásmennyiség** és a **Cél mennyiség** mezők értékei közé esik -e. Ha a helyutasítás bejövő tranzakcióra vonatkozik, válasszon egyet az alábbi lehetőségek közül:<ul><li>**Azonosítótábla mennyisége** – Értékeli, hogy egy mennyiség a mennyiségi céltartományba esik -e, a mennyiséget az azonosítótáblát használva, amit megkapott.</li><li>**Egységekre bontott mennyiség** – Értékeli, hogy egy mennyiség a mennyiségi céltartományba esik -e, amely egység a tranzakcióban került megadásra. Például, ha fogadni tud a raktárba 1000-es mennyiséget, és azokat 10 azonosítótáblára tudja bontani minden 100-as megadott mennyiségből, felhasználhat 1000-es mennyiségű cikket 100-as azonosítótábla mennyisége helyett.</li><li>**Fennmaradó mennyiség** – Annak eldöntéséről, hogy a mennyiségi céltartományon belül van-e egy mennyiség, használja a jelenleg beadott beszerzési rendelési soron még bevételezendő mennyiséget.</li><li>**Várható mennyiség** – Annak eldöntésekor, hogy a mennyiségi a céltartományon belül van-e egy mennyiség, használja a beszerzési rendelésen lévő összesített mennyiséget, eltekintve az eddig befogadott mennyiségre.</li></ul> |

1. Választható: A **Sorok** gyorslapon kijelölheti a további mezőket.

    | Mező | Leírás |
    |---|---|
    | Korlátozás egység szerint | Válassza ki a jelölőnégyzetet, ha korlátozni szeretné a mértékegységet, ami a helyutasítás soraira,a kiválasztási feltételekre érvényes. Amikor a mértékegység meg van adva, azon cikkek, ahol az egység megegyezik legalább egy egységgel, ami megadásra került az egységszekvencia-csoportban, érvényes lesz a választott soron.<p>Például, az egység raklapokra van korlátozva, így az elem összekapcsolásra kerül az egységszekvencia-csoporttal, ami *Raklapok* egységet foglalja magában. Ilyen esetben a cikkek figyelembe vehető, érvényes lehetőséget biztosítanak a helyutasításoknak.</p><p>Ellenben a **Korlátozás egység szerint** jelölőnégyzet nem szabályozza az egységet vagy egységeket a munkasorokon. Az egység korlátozása csak olyan egységekre érvényes, amelyek elérhetővé váltak az egységszekvencia-csoporton keresztül.</p><p>Például, egy egység összekapcsolásra kerül egy egységszekvencia-csoporttal, amely magában foglalja a *raklapok* és a *db* mindkét egységét. Egy mértékegység meghatározásra került, olyan módon, hogy 1 raklap = 100 db, és a helyutasítás **Korlátozás egység szerint** funkciója csak raklapokra vonatkozik. Továbbá egy munkasablon meghatározásra került, ami korlátozza a munkafejléc készítését 50 db-osra. Ebben az esetben az 50 db-os munkasorok létrehozásra kerülnek.</p><p>Hogy megadhassa a mértékegységet a korlátozáshoz, kövesse az alábbi lépéseket</p><ol><li>Válassza a **Sorok** gyorslapon a **Korlátozás egység szerint** elemet. Ez a gomb csak azután válik elérhetővé, miután kiválasztotta a **Korlátozás egység szerint** jelölőnégyzetet, majd rákattintott a **Mentés** parancsra.</li><li>Az **Egység** mezőben válasszon mértékegységet a kitárolási, vagy a betárolási folyamat korlátozáshoz.</li></ol> |
    | Felkerekítés egységre | Válassza ki ezt a beállítást, ha azt szeretné jelezni, hogy a nyersanyag-kitárolást a **Kitárolás egység szerint** mezőben meghatározott anyagkezelési egység egy többszörösére kell felkerekíteni. Ez a mező csak a *Kitárolás* típusba tartozó nyersanyag-kitárolásra és helyutasításokra vonatkozik. |
    | Csomagolási mennyiség keresése | Jelölje be a jelölőnégyzetet, ha a csomagolási egység mennyisége az **Értékesítési rendelés** oldalon meg lett adva. Ha bejelöli ezt a jelölőnégyzetet, csak az olyan helyek kerülnek kiválasztásra, amik rendelkeznek a kiválasztott csomagolási egység mennyiséggel. |
    | Felosztás engedélyezése | Jelölje be ezt a jelölőnégyzetet, hogy szétossza a mennyiséget több hely között. |
    | Azonnali feltöltési sablon | Hozzon létre kapcsolatot egy feltöltési sablonnal, így a feltöltés egyből megkezdődik, hogyha a cikkek még nem forgalmazhatók. Ha ezt a mezőt üresen hagyja, a cikkfeltöltés nem kezdődik meg addig, amíg a helyutasítás összes sora nem került feldolgozásra.<p>Ez a mező csak a kiválasztott munkarendelés-típusokon elérhető, ahol a feltöltés engedélyezett, mint például az *Értékesítési rendelések* és a *Nyersanyag kitárolása*.</p> |

1. A **Helyutasítási műveletek** gyorslapon, válassza az **Új** menüpontot, hogy megfelelő helyet vagy helytartományokat válasszon.
1. A **Sorszám** mező megmutatja azt a sorrendet, amelyben a helyutasítás feldolgozásra kerül, a kijelölt munkatétel típusához. Módosíthatja a sorrendet. Ellenben, elővigyázatosnak kell lennie a sorszámokkal a helyutasítási műveletekkel kapcsolatosan, mert a a helyutasítási műveletek mindig a sorban futnak.
1. A **Név** mezőben, adja meg a helyutasítási művelet nevét. Legyen specifikus, így mindig egyértelmű, hogy mi a művelet.
1. Választható: Kattintson a **Lekérdezés szerkesztése** menüpontra, hogy módosíthassa a raktározási helyeket, vagy más kritériumokat.
1. Választható: megadhatja a következő további mezőket a helyutasításhoz.

    | Mező | Leírás |
    |---|---|
    | Rögzített hely használata | Válassza ki melyik helyre kell vonatkozzon a helyutasítás:<ul><li>**Rögzített- és nem rögzített helyek** – A helyutasítás minden helyet figyelembe vesz.</li><li>**Csak a termék rögzített helyei** – A helyutasítás csak a termék rögzített helyeire vonatkozik.</li><li>**A termékváltozat csak rögzített helyei** – A helyutasítás csak a termékvariáns rögzített helyeire vonatkozik.</li></ul> |
    | Negatív készlet engedélyezése | Jelölje be a jelölőnégyzetet, hogy engedélyezze a negatív készlet funkciót a kiválasztott raktárhelyeken. |
    | Kötegelt engedélyezve | Jelölje be ezt a jelölőnégyzetet, a köteg engedélyezve van a cikkek köteg stratégiák használandó. Ha ez a jelölőnégyzet be van jelölve, és a **Stratégia** mező *Nincs*-re van állítva, a rendszer a következő műveletsorra halad tovább. |
    | Stratégia | Adja meg a stratégiát, amit a helyutasításnak alkalmaznia kell:<ul><li>**Nincs** – A program nem használ stratégiát.</li><li>**Csomagolási mennyiség egyeztetése** – Ez a stratégia ellenőrzi, hogy a kitárolási hely rendelkezik -e a megadott csomagolási mennyiséggel. Ez a stratégia csak akkor érvényes, ha a **Munkatípus** mező *Kitárolás* értékre van állítva.</li><li>**Konszolidálás** – Ez a stratégia konszolidálja a cikkeket egy megadott helyen, ha hasonló cikkek egyaránt elérhetők. Ez a stratégia csak akkor érvényes, ha a **Munkatípus** mező *Eltárolás* értékre van állítva. Egy általános kitároláshoz a rendszer igyekszik konszolidálni az első műveleti sort, és ezután a második műveleti sort, és igyekszik betárolni konszolidáció nélkül. Az áruk konszolidálása hatékonyabbá teszi a későbbi kitárolást.</li><li>**FEFO-köteg lefoglalása** – Ez a stratégia olyankor használatos, ha készlet a köteg lejárati dátuma alapján került elhelyezésre, és véglegesített kötegfoglalásban került forgalmazásra. Az első lejárat, első kiesett (FEFO) kötegfoglalási stratégia akkor is használható, ha a raktár helye a köteg dátum előtti-legjobb funkció segítségével lett megadva a lejárati dátum mellett. Csak köteg-engedélyezett cikkekre használhatja ezt a stratégiát: Ez a stratégia csak akkor érvényes, ha a **Munkatípus** mező *Kitárolás* értékre van állítva. Amikor kiválasztja ezt a stratégiát, felülír bármilyen sorrend szerinti osztályozást a a köteg száma szerint, amikre alkalmazásra került.</li><li>**Felkerekítés a teljes azonosítótáblára** – Ez a stratégia felfelé kerekíti a készletmennyiséget, így az megegyezik az azonosítótábla mennyiségével, és ezt a mennyiséget a kitárolandó cikkekhez is hozzárendeli. Ez a stratégia csak a feltöltés típusára és helyutasításokra vonatkozik, és csak akkor, ha a **Munkatípus** mező *Kitárolás*-ra van állítva.</li><li>**Üres hely, amely nem rendelkezik bejövő munkával** – Ez a stratégia az üres helyek meghatározására használható. Egy hely üresnek tekinthető, ha nincsen fizikai készlete és nincs bejövő munkája. Ez a stratégia csak akkor érvényes, ha a **Munkatípus** mező *Eltárolás* értékre van állítva.</li></ul> |

## <a name="example-of-the-use-of-location-directives"></a>Példa a helyutasítás használatához

Ehhez a példához egy olyan beszerzési rendelési folyamatot veszünk alapul, ahol a helyutasításnak szabad területet kell találnia egy raktáron belül, azoknak a készletcikkeknek, amiket most regisztráltak a bevételezési területen. Először szabad kapacitást kell találnia a raktár területén, az aktuális készlet konszolidálásával. Ha a konszolidáció nem lehetséges, üres helyet kell találnia.

Ebben az esetben két helyutasítási műveletet kell megadni. A sorozat első művelete a **Konszolidálás** stratégiája, a másodiknak az **Üres hely bejövő munka nélkül** stratégiáját használjuk. Hacsak nem ad meg műveletet a túlcsordulás kezelésére, két végkifejlet lehetséges akkor, ha nincs több kapacitása a raktárnak: a munka létrehozható, habár nem lesz hely meghatározva, vagy a munka-létrehozási folyamat sikertelenül zárul. Az eredményt a **Helyutasítási hibák** lap beállításai határozzák meg, ahol eldöntheti, hogy beállítja-e a **Munka leállítása, ha a helyutasítások sikertelenek** lehetőséget minden Munkarendelés-típushoz.

## <a name="next-step"></a>Következő lépés

Miután helyutasításokat hozott létre, összekapcsolhat minden utasításkódot egy munkasablon-kóddal a munkalétrehozáshoz. Bővebb információkért lásd: [Raktári munka ellenőrzése munkasablonok és helyutasítások használatával](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/control-warehouse-location-directives).

## <a name="technical-information-for-system-admins"></a>Technikai információk rendszergazdáknak

Ha nincs hozzáférése azokhoz az oldalakhoz, amik segítségével teljesíthető a feladat, vegye fel a kapcsolatot rendszergazdájával, és adja meg a következő táblában található információkat.

| Kategória | Előfeltételek |
|---|---|
| Konfigurációs kulcsok (Configuration Keys) | Lépjen a **Rendszerfelügyelet \> Beállítás \> Licenckonfiguráció** elemre. Bontsa ki a **Kereskedelem** licenckulcsot, ezután válassza ki a **Raktár- és szállításkezelés** konfigurációs kulcsot. |
