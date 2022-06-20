---
title: Helyutasítások kezelése
description: Ez a témakör a helyi irányelvekről szóló útmutatót ismerteti. A helyutasítások olyan a felhasználó által megadott szabályok, melyek segítik a kitárolási és betárolási helyek meghatározását a készletmozgatáshoz.
author: Mirzaab
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSLocDirHint, WHSLocDirTableUOM, WHSLocDirFailure
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 7705ea132521353cd6af7245df90aafaf23af885
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903695"
---
# <a name="work-with-location-directives"></a>Helyutasítások kezelése

[!include [banner](../includes/banner.md)]

A helyutasítások olyan szabályok, amik segítik a kitárolási és betárolási helyek meghatározását, készletmozgatás esetében. Például egy értékesítési rendelés tranzakciójába a helyutasítás azt határozza meg, ahol a cikkek kitárolása történik, valamint ahol a cikkeket betárolják. A helyutasítások fejlécből és a kapcsolódó sorokból állnak. Ezek meghatározott *munkarendelés-típusokhoz* jönnek létre.

> [!NOTE]
> Ez a cikk a Raktárkezelés modul **szolgáltatásaira vonatkozik**. Ez nem vonatkozik az [Árukészletkezelés kezelése](../inventory/inventory-home-page.md) modul egyes funkcióira.

Helyutasítások segítségével elvégezheti az alábbi feladatokat:

- Bejövő cikkek betárolása.
- Cikkek kitárolása és előkészítése a kimenő tranzakciókhoz.
- Nyersanyagok ki- és betárolása a termeléshez.
- Üres helyek feltöltése.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt helyutasítási műveletet hozhatna létre, követnie kell az alábbi lépéseket, hogy megbizonyosodhasson, hogy az előfeltételek adottak.

1. Győződjön meg arról, hogy a szükséges licenckulcs be van kapcsolva. Nyissa meg a **Rendszerfelügyelet \> Beállítás \> Licenc konfigurációja** részt, bontsa ki a **Kereskedelmi** licenckulcsot, majd válassza a **Raktár- és szállításkezelés** konfigurációs kulcsot. Vegye figyelembe, hogy ehhez a lépéshez rendszergazdai hozzáférés szükséges.
1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Raktárak** pontra.
1. Raktár létrehozása.
1. A **Raktár** gyorslapon állítsa a **Raktárkezelési folyamatok alkalmazása** opciót *Igen*-re.
1. Helyek, helytípusok, helyprofilok és helyformátumok létrehozása. A további tudnivalókért lásd: [Helyek konfigurálása WMS szolgáltatással rendelkező raktárban](./tasks/configure-locations-wms-enabled-warehouse.md).
1. Helyek, zónák és zónacsoportok létrehozása. A további tudnivalókért lásd: [Raktár beállításai](../../commerce/channels-setup-warehouse.md) és [Helyek konfigurálása WMS szolgáltatással rendelkező raktárban](./tasks/configure-locations-wms-enabled-warehouse.md).

## <a name="work-order-types-for-location-directives"></a>A helyutasítások munkarendelés-típusai

A helyutasításokhoz beállítható mezők közül sok minden munkarendelés-típusban közös. Más mezők azonban adott munkarendelés-típusokra jellemzőek.

![A helyutasítások munkarendelés-típusai.](media/Location_Directives_Work_Order_Types.png "A helyutasítások munkarendelés-típusai")

> [!NOTE]
> Két munkarendelés-típust, a *Visszavont munkát* és a *Ciklikus leltározást* csak a rendszer használja. A helyutasítások nem hozhatók létre ezekhez a munkarendelés-típusokhoz.

A következő alszakaszokban található táblák a helyutasítás beállításakor elérhető közös és feldolgozó rendeléstípus-specifikus mezőket sorolják fel.

### <a name="fields-that-are-common-to-all-work-order-types"></a>Minden munkarendelés-típusra közös mezők

Az alábbi táblázat az összes munkarendelés-típusra közös mezőket sorolja fel.

| Gyorslap | Mező |
|---|---|
| Helyutasítások | Munka típusa |
| Helyutasítások | Hely |
| Helyutasítások | Raktár |
| Helyutasítások | Utasításkód |
| Helyutasítások | Több raktározási egység |
| Sorok | Sorszám |
| Sorok | Forrásmennyiség |
| Sorok | Záró mennyiség |
| Sorok | Egység |
| Sorok | Mennyiség megkeresése |
| Sorok | Korlátozás egység szerint |
| Sorok | Felkerekítés egységre |
| Sorok | Csomagolási mennyiség keresése |
| Sorok | Felosztás engedélyezése |
| Helyutasítási műveletek | Sorszám |
| Helyutasítási műveletek | Név |
| Helyutasítási műveletek | Rögzített hely használata |
| Helyutasítási műveletek | Negatív készlet engedélyezése |
| Helyutasítási műveletek | Kötegelt engedélyezve |
| Helyutasítási műveletek | Stratégia |

### <a name="fields-that-are-specific-to-work-order-types"></a><a name="fields-specific-types"></a>Munkarendelés-típusokra jellemző mezők

Az alábbi táblázat az egyes munkarendelés-típusokra jellemző mezőket sorolja fel.

| Gyorslap | Mező | Munkarendelés típusa |
|---|---|---|
| Helyutasítások | Keresés alapja | Beszerzési rendelések |
| Helyutasítások | Érvényes intézkedéskód | Beszerzési rendelések |
| Helyutasítások | Intézkedési kód | Beszerzési rendelések |
| Helyutasítások | Érvényes intézkedéskód | Késztermékek betárolása |
| Helyutasítások | Intézkedési kód | Késztermékek betárolása |
| Helyutasítások | Érvényes intézkedéskód | Visszárurendelések |
| Helyutasítások | Intézkedési kód | Visszárurendelések |
| Helyutasítások | Érvényes intézkedéskód | Kanban betárolás |
| Helyutasítások | Érvényes intézkedéskód | Kanban kitárolás |
| Sorok | Azonnali feltöltési sablon | Értékesítési rendelés |
| Sorok | Azonnali feltöltési sablon | Nyersanyag kitárolása |
| Sorok | Azonnali feltöltési sablon | Átmozgatási probléma |
| Sorok | Azonnali feltöltési sablon | Kanban kitárolás |

## <a name="open-the-location-directives-page"></a>A Helyutasítások oldal megnyitása

A **Helyutasítások** oldal megnyitásához vagy szerkesztéséhez nyissa meg a **Raktárkezelés \> Beállítás \> Helyutasítások** elemet.

Itt a Művelet panel parancsaival megtekintheti, létrehozhatja és szerkesztheti a helyutasításokat. A cikk további részeiben található tájékoztatás az oldalon elérhető mezők használatával kapcsolatban.

## <a name="action-pane"></a>Műveleti panel

A **Helyutasítások** oldal Művelet ablaktáblája olyan gombokat tartalmaz, amelyek utasítások (**Szerkesztés**, **Új** és **Törlés**) létrehozására, szerkesztésére és törlésére használhatók. A következő gombokat is tartalmazza, amelyek segítségével módosíthatja a helyutasítás feldolgozásának sorrendjét, és konfigurálhat egy lekérdezést, amely meghatározza a helyutasítás alkalmazásának kritériumait:

- **Mozgatás felfelé** – A kijelölt helyutasítás feljebb mozgatása a sorrendben. Áthelyezheti például a 4-es sorszámról a 3-as sorszámra.
- **Mozgatás lefelé** – A kijelölt helyutasítás lejjebb mozgatása a sorrendben. Áthelyezheti például a 4-es sorszámról a 5-as sorszámra.
- **Lekérdezés szerkesztése** – Nyisson meg egy párbeszédpanelt, ahol meghatározhatja azokat a feltételeket, amelyek alatt a kiválasztott helyutasítást fel kell dolgozni. Előfordulhat például, hogy csak egy adott raktárra szeretné alkalmazni.

## <a name="location-directives-header"></a>Helyutasítások fejléce

A helyutasítás fejléce a következő mezőket tartalmazza a helyutasítás sorszámához és leíró nevéhez:

- **Sorszám** – Ez a mező azt a sorrendet jelzi, amelyben a rendszer megpróbálja alkalmazni az egyes helyirányelveket a kiválasztott munkarendelés-típusra. Először az alacsony számokat alkalmazza a program. A sorrendet a Művelet panel **Mozgatás felfelé** és **Mozgatás lefelé** gombjaival módosíthatja.
- **Név** – Írja be a helyutasítás leíró nevét. Ennek a névnek segítenie kell az irányelv általános céljának azonosítását. Írja be például az *Értékesítési rendelés kitárolása a 24-es raktárban*.

## <a name="location-directives-fasttab"></a>Helyutasítások gyorslapja

A **Helyutasítások** gyorslap mezői a listaablak **Munkarendelés típusa** mezőjében kiválasztott munkarendelés-típusra vonatkoznak.

- **Munkatípus** – Adja meg a munkatípust, mely elvégzésre kell kerüljön. A rendelkezésre álló értékek a készlettranzakciótól függnek, melyet **Munkarendelés típusa** mezőben adott meg. Válasszon a következő értékek közül:

    - **Elhelyezés** – a helyutasítás igyekszik megtalálni a legjobb helyet a készlet elhelyezésére, vagy fellelésére, ami a rendszerbe kerül a bevételezés, a termelés és a készlethelyesbítések által. Fel lehet használni arra is, hogy definiáljon egy helyet egy köztes szinten vagy a végső öböl ajtó szállítási helyére.
    - **Felvétel** – a helyutasítás igyekszik megtalálni a legjobb helyeket a készlet fizikai lefoglalásához (munka létrehozása). A kitárolás akkor is végrehajtható (azaz a kitárolási munkasor bezárható), ha a munka nem fejeződött be. A felhasználó végrehajthatja a fizikai kitárolást. A rendszerben ez a művelet egy kitárolási lépés. A felhasználó ezután megszakíthatja a folyamatot egy mobileszközről, és később befejezheti a munkát. Azonban a munkafejléc bezárása akkor történik meg, ha befejeződött a végső betárolás.

    > [!IMPORTANT]
    > A **Munkatípus** mezőben lévő többi érték nem releváns a helyutasítások szempontjából. Csak azért jelennek meg, mert a mező nincs szűrve a kijelölt munkarendelés-típusnak megfelelően.

- **Hely** – Ez a mező kötelező, mert a helymeghatározási irányelvnek szüksége van a hely és a raktár megállapítására, amelyre érvényes.
- **Raktár** – Ez a mező kötelező, mert a helyutasításnak szüksége van a hely és a raktár megállapítására, amelyre érvényes.
- **Utasításkód** – A munkasablon, illetve a feltöltési sablon társítása irányelv kódjának kiválasztása. Az **Utasításkód** lapján új kódokat hozhat létre, amelyeket a munkasablonok vagy feltöltési sablonok helyutasításokkal való összekötésére használhat. Az utasításkódokat arra is használhatja, hogy létrehozzon hivatkozásokat a munkasablonok és helyutasítások között (mint például a raktárajtó vagy a köztes hely).

    > [!TIP]
    > Ha egy utasításkód meg van adva, amikor szükség van egy munka létrehozására, a rendszer nem fog helyutasításokat fog keresni a sorszám alapján. Ehelyett utasításkód szerint fog keresni. Ilyen módon pontosabban kezelheti a helyutasításokat, melyek a munkasablonok adott lépéseként használatosak, mint például az anyagok előkészítése az egyes lépésekhez.

- **Több SKU** – Állítsa ezt a lehetőséget *Igen* értékre, a több termékváltozat (SKU) funkció használatához egy adott helyen. Például több termékváltozatot kell engedélyezni a raktárajtó helyhez. Ha több termékváltozatot engedélyez, a betárolási hely a várt módon meg lesz adva a munkában. A betárolási hely azonban csak egy többcikkes betárolást képes kezelni (ha a munka különböző termékváltozatokat tartalmaz, amelyeket ki és be kell tárolni). Nem lesz képes kezelni egy termékváltozatos betárolást. Ha ezt a beállítást *Nem* értékre állítja, a betárolási hely csak akkor lesz megadva, ha a betárolás csak termékváltozattal rendelkezik.

    > [!IMPORTANT]
    > Ahhoz, hogy többcikkes és egy termékváltozatú betárolások is végrehajthatók legyenek, két azonos szerkezetű és beállítású sort kell megadnia, de a **Több termékváltozat** beállítást *Igen* értékre kell állítania az egyik sorban, és *Nem* értékre a másiknál. Ezért a betárolási műveletekhez két azonos helyutasítás szükséges, még akkor is, ha nem kell különbséget tennie az egy vagy több termékváltozat között egy munkaazonosítón. Gyakran előfordul, hogy ha nem állítja be mindkét helyutasítást, a váratlan üzleti folyamatok helyszínei az alkalmazott helyutasításból származnak. Hasonló beállítást kell használnia a **Munkatípus** *kitárolással* rendelkező utasítások esetében, ha több termékváltozatot tartalmazó rendeléseket kell feldolgoznia.

    Használja a **Több termékváltozat** beállítást olyan munkasorokhoz, amelyek több cikkszámot kezelnek. (A cikkszám üres lesz a munka részleteiben, és **Több** értékkel jelenik meg a Raktárkezelés mobilalkalmazás feldolgozási lapjain.)

    Egy tipikus példaforgatókönyvben egy munkasablon úgy van beállítva, hogy egynél több kitárolási/betárolási párja legyen. Ebben az esetben érdemes lehet megkeresni egy adott átmeneti helyet, amelyet a **Munka típusú** *Kitárolás* sorokhoz kíván használni.

    > [!NOTE]
    > Ha a **Több termékváltozat** beállítás értéke *Igen*, akkor a Művelet panelen nem választhatja a **Lekérdezés szerkesztése** beállítást, mert a lekérdezés nem értékelhető ki cikkszinten, ha több cikk van. A kívánt helyutasítás kiválasztásának biztosítása érdekében az **Utasításkód** mező segítségével irányítsa a helyutasítás kiválasztását, amely azon betárolási sorokhoz kapcsolódik, ahol az utasításkód a munkasablonban van hozzárendelve.

    Hacsak nem dolgozik mindig egycikkes vagy vegyes cikkes műveletekkel, fontos, hogy két helyutasítást adjon meg a *Betárolás* munkatípushoz: az egyikben a **Több termékváltozat** beállítás *Igen*, a másiknál pedig *Nem* értékű.

- **Alkalmazható intézkedési kód** – Adja meg, hogy a helymeghatározási elv intézkedéskódjának meg kell-e egyeznie a cikkek fogadásakor alkalmazott intézkedéskóddal, vagy a helyutasítás bármilyen intézkedéskód alapján kiválasztható. Ha a *Pontos egyezés* lehetőséget választja, és az **Intézkedéskód** mező üresen marad, akkor csak az üres intézkedéskódokat veszi figyelembe a rendszer ennél a helyutasításnál.

    > [!NOTE]
    > Ez a mező csak olyan kiválasztott munkarendelés-típusoknál érhető el, ahol a feltöltés megengedett. A teljes listát lásd [a](#fields-specific-types) cikk korábbi, a munkarendeléstípusokra jellemző mezőkben.

- **Keresés szempontja** – Adja meg, hogy az elraktározott mennyiség legyen-e a teljes mennyiség az azonosítótáblán, vagy cikkenként szerepeljen. Ebben a mezőben biztosíthatja, hogy az azonosítótábla teljes tartalma egy helyre kerüljön, és hogy a rendszer ne javasolja a tartalom felosztását több helyre az **ASN** (azonosítótábla fogadása), a **Vegyes azonosítótábla** fogadása és a **Fürt** fogadási folyamatokra. (A **Fürt** fogadási folyamatához be kell kapcsolni a [Fürt eltárolási funkciója](putaway-clusters.md) funkciót.) A helyutasítási lekérdezés, a sorok és a helyutasítási műveletek viselkedése a kiválasztott értéktől függően változhat. A **Sorok** gyorslap csak akkor használatos, ha a **Keresés szempontja** *Cikk* értékre van állítva.

    > [!NOTE]
    > Ez a mező csak olyan kiválasztott munkarendelés-típusoknál érhető el, ahol a feltöltés megengedett. A teljes listát a [Munkarendelés-típusokra jellemző mezők](#fields-specific-types) című szakaszban találhatja.

- **Intézkedési kód** – Ez a mező olyan helyutasításokhoz használatos, amelyek munkarendelés-típusa *Beszerzési rendelések*, *Késztermékek betárolása* vagy *Visszárurendelések*, és munkatípusa *Betárolás*. Segítségével irányítsa a folyamatot egy adott helyutasítás használatára, a dolgozó által a Raktárkezelés mobilalkalmazásban kiválasztott intézkedési kódtól függőben. A visszaküldött árukat például a készletbe való visszaküldés előtt átirányíthatja egy ellenőrzési helyre. Az intézkedési kód készletállapothoz kapcsolható. Ily módon a készlet állapotának módosítására használható a bevételezési folyamat részeként. Például van egy *QA* intézkedési kódja, amely a készlet állapotát *QA* értékre állítja. Ezután egy külön helyutasítással áthelyezheti a készletet egy karanténhelyre.

    > [!NOTE]
    > Ez a mező csak olyan kiválasztott munkarendelés-típusoknál érhető el, ahol a feltöltés megengedett. A teljes listát a [Munkarendelés-típusokra jellemző mezők](#fields-specific-types) című szakaszban találhatja.

## <a name="lines-fasttab"></a>Sorok gyorslap

A **Sorok** gyorslapon hozhatja létre a **Helyutasítás műveletei** gyorslapon megadott kapcsolódó műveletek alkalmazásának feltételeit. Minden sor esetében megadhatja a minimális és maximális mennyiséget, amire a művelet vonatkozik. Úgy is megadhatja a műveletet, hogy az egy adott készletmennyiségre vonatkozzon.

- **Sorszám** – Megadja azt a sorrendet, amelyben az egyes helyutasítássorok feldolgozásra kerülnek, a kijelölt munkatípushoz. A sorrendet szükség szerint az eszköztár **Mozgatás felfelé** és **Mozgatás lefelé** gombjaival módosíthatja.
- **Kezdő mennyiség** – Megadja a mennyiségtartománynak a kezdetét, amelyre a sor vonatkozik. Az **Egység** mezőben adja meg a mennyiséghez tartozó mértékegységet.
- **Záró mennyiség** – Megadja a mennyiségtartománynak a végét, amelyre a sor vonatkozik. Az **Egység** mezőben adja meg a mennyiséghez tartozó mértékegységet.
- **Egység** – A cikk mértékegységének kiválasztása. Megadhat egy minimális és egy maximális mennyiséget, amire az utasítás vonatkozik, valamint megadhatja, hogy az utasítás csak egy adott készletegységre vonatkozzon. Az **Egység** mező *csak* a mennyiség értékelésénél használatos. Annak meghatározásához, hogy egy helyutasítássor érvényes-e egyáltalán, a rendszer az egység mennyiségét használja, ami a soron van megadva. Minden alkalommal, amikor egy helyutasítási sort elér, a rendszer megpróbálja konvertálni a kereseti egységet, ami a sorban van megadva. Ha a mértékegység-átváltás nem létezik, a rendszer tovább halad a következő sorra.
- **Mennyiség megkeresése** – Ez a mező csak a cikkek raktárban történő elraktározására vagy megkeresésére tett kísérletek során használatos. (Ezért csak akkor érvényes, ha a **Munkatípus** mező *Eltárolás* értékre van állítva). Válasszon az alábbi értékek közül, ha meg szeretné adni, hogy a mennyiség a **Kezdő mennyiség** és a **Záró mennyiség** között van-e:

    - **Azonosítótábla mennyisége** – a kapott azonosítótáblán lévő mennyiség használata.
    - **Egységes mennyiség** – a tranzakció során felhasznált mennyiség használata. Például 1000 egységnyi mennyiséget kap egy raktárban, és 10 azonosítótáblára bontja, amelyek mindegyike 100-as mennyiséggel rendelkezik. Ebben az esetben a 100-as azonosítótábla-mennyiség helyett 1000 cikkes mennyiséget használhat.
    - **Hátralévő mennyiség** – a feldolgozás alatt álló beszerzésirendelés-sorban még beérkezendő mennyiség használata.
    - **Várható mennyiség** – a beszerzésirendelés-sor teljes mennyiségének használata, függetlenül attól, hogy mi érkezett már be.

- **Korlátozás egység szerint** – Ez a jelölőnégyzet lehetővé teszi, hogy a helyutasítási sort egy mértékegységre vagy több mértékegységre határozza meg. Válassza ki, ha korlátozni szeretné a mértékegységet, ami a helyutasítás soraira,a kiválasztási feltételekre érvényes. Ez a funkció csak olyan helyutasításoknál működik, ahol a **Munkatípus** mező *Kitárolás* értékre van beállítva.

    Ha például mennyiségeket foglal le, a raklapokat csak egy adott helyről szeretné lefoglalni. Ebben az esetben a sorok a raklapokra korlátozzák a szekvenciát oly módon, hogy a raklapnál kisebb mennyiség ne legyen kiválasztva a helyutasításhoz.

    Ne feledje, hogy a **Korlátozás egység szerint** jelölőnégyzet nem szabályozza az egységet vagy egységeket a munkasorokon. Az egység korlátozása csak olyan egységekre érvényes, amelyek elérhetővé váltak az egységszekvencia-csoporton keresztül. Például, egy egység összekapcsolásra kerül egy egységszekvencia-csoporttal, amely magában foglalja a *raklapok* egységet és a *db* egységet. Egy mértékegység meghatározásra került, olyan módon, hogy 1 raklap = 100 db, és a helyutasítás **Korlátozás egység szerint** funkciója csak raklapokra vonatkozik. Továbbá egy munkasablon meghatározásra került, ami korlátozza a munkafejléc készítését 50 db-osra. Ebben az esetben az 50 db-os munkasorok létrehozásra kerülnek. Hogy megadhassa a mértékegységet a korlátozáshoz, kövesse az alábbi lépéseket:

    1. A **Sorok** gyorslapon válassza a **Korlátozás egység szerint** lehetőséget. (Ez a gomb csak azután válik elérhetővé, miután kiválasztotta a **Korlátozás egység szerint** jelölőnégyzetet, majd rákattintott a **Mentés** parancsra.)
    1. A **Korlátozás egység szerint** lap **Egység** mezőjében válassza ki azt a mértékegységet, amely szerint korlátozni szeretné a kitárolási és betárolási folyamatokat.

- **Felkerekítés egységre** – Ez a mező a **Korlátozás egység szerint** jelölőnégyzettel együtt működik. Például: Ha a **Korlátozás egység szerint** és **Felkerekítés egységre** van kiválasztva a helyutasítássorban, akkor a nyersanyag kitárolására vonatkozó utasításból generált munkát fel kell kerekítenie egy anyagkezelési egység többszörösére (ennek megadása a **Korlátozás egység szerint** beállításban történik).

    > [!NOTE]
    > Ez a **Felkerekítés egységre** beállítás csak a *Nyersanyag kitárolása* munkarendelés-típusánál működik, és csak olyan helyutasításoknál, ahol a **Munkatípus** mező értéke *Kitárolás*.

- **Csomagolási mennyiség keresése** – Ha egy értékesítési rendelésen, átmozgatási rendelésen vagy gyártási rendelésen megad csomagolási mennyiséget, ez a jelölőnégyzet lehetővé teszi a rendszer korlátozását, hogy csak azokat a helyeket válassza ki, amelyek legalább az adott csomagolási mennyiséggel rendelkeznek.

    > [!NOTE]
    > Ez a funkció csak a *Kitárolás* típusú helyutasításoknál működik.

- **Felosztás engedélyezése** – Ez adja meg, hogy egy helyutasítás feloszthatja-e a beérkező vagy lefolgalt mennyiséget több raktár között, vagy a teljes mennyiségnek egy helyen kell lennie, illetve azt egyetlen helyen kell lefoglalni a munka létrehozásához.
- **Azonnali feltöltési sablon** – Ezzel a mezővel hozhat létre kapcsolatot egy feltöltési sablonnal, így a feltöltés egyből megkezdődik, hogyha a cikkek még nem forgalmazhatók. Ha ezt a mezőt üresen hagyja, a cikkfeltöltés nem kezdődik meg addig, amíg a helyutasítás összes sora nem került feldolgozásra.

    > [!NOTE]
    > Ez a mező csak olyan kiválasztott munkarendelés-típusoknál érhető el, ahol a feltöltés megengedett. A teljes listát a [Munkarendelés-típusokra jellemző mezők](#fields-specific-types) című szakaszban találhatja.

## <a name="location-directive-actions-fasttab"></a>Helyutasítási műveletek gyorslapja

Több helyutasítási műveletet is megadhat minden sornak. Még egyszer, a sorozatszám meghatározza a műveletek értékelésének sorrendjét. Ezen a szinten megadhat egy lekérdezést, hogy megadja, hogyan legyen megtalálva a legjobb hely a raktárban. Emellett használható előre definiált **Stratégia** érték az optimális hely megtalálásához.

- **Sorszám** – Ez a mező megmutatja azt a sorrendet, amelyben a műveletek feldolgozásra kerülnek, a kijelölt munkatétel típusához. A sorrendet az eszköztár **Mozgatás felfelé** és **Mozgatás lefelé** gombjaival módosíthatja.
- **Név** – Adja meg a helyutasítási művelet nevét. Legyen konkrét, hogy a végrehajtott művelet egyértelmű legyen a névből.
- **Rögzített hely használata** – Adja meg, hogy a helyutasításnak mely helyeket kell figyelembe vennie. Válasszon a következő értékek közül:

    - **Rögzített- és nem rögzített helyek** – A helyutasítás minden helyet figyelembe vesz.
    - **Csak a termék rögzített helyei** – A helyutasítás csak a termék rögzített helyeire vonatkozik.
    - **A termékváltozat csak rögzített helyei** – A helyutasítás csak a termékvariáns rögzített helyeire vonatkozik.

- **Negatív készlet engedélyezése** – A jelölőnégyzet bejelölésével engedélyezi a negatív készlet megadását a kiválasztott raktárhelyhez a helyutasításokban.
- **Köteg engedélyezve** – Jelölje be ezt a jelölőnégyzetet, a köteg engedélyezve van a cikkek köteg stratégiák használandó. Fontos, hogy bejelölje ezt a jelölőnégyzetet azoknál a folyamatoknál, amelyek helyutasításokkal keresik a kötegszámmal nyomon követett cikkeket. Ily módon a kötegszámmal nyomon követett cikkeket tartalmazó helyek keresése is szerepel. Ha ez a jelölőnégyzet be van jelölve, és a **Stratégia** mező *Nincs*-re van állítva, a rendszer a következő műveletsorra halad tovább.
- **Stratégia** – A különböző helyutasítássorokhoz tartozó tevékenységek egyszerűbb és gyorsabb meghatározásához kiválaszthatja a következő előre meghatározott stratégiák egyikét:

    - **Nincs** – A program nem használ stratégiát.
    - **Csomagolási mennyiség egyeztetése** – Ez a stratégia ellenőrzi, hogy a kitárolási hely rendelkezik -e a megadott csomagolási mennyiséggel. Ez a stratégia csak akkor érvényes, ha a **Munkatípus** mező *Kitárolás* értékre van állítva.
    - **Konszolidálás** – Ez a stratégia konszolidálja a cikkeket egy megadott helyen, ha hasonló cikkek egyaránt elérhetők. Ez a stratégia csak akkor érvényes, ha a **Munkatípus** mező *Eltárolás* értékre van állítva. Egy általános kitároláshoz a rendszer igyekszik konszolidálni az első műveleti sort, és ezután a második műveleti sort, és igyekszik betárolni konszolidáció nélkül. Az áruk konszolidálása hatékonyabbá teszi a későbbi kitárolást.
    - **FEFO-köteg lefoglalása** – Ez a stratégia az első lejárat, első kimenő (FEFO) kötegfoglalásokat használja. Akkor használja, amikor a készlet keresése egy köteg lejárati dátuma alapján történik, és kötegfoglalásra van lefoglalva. Csak köteg-engedélyezett cikkekre használhatja ezt a stratégiát: Csak akkor érvényes, ha a **Munkatípus** mező *Kitárolás* értékre van állítva.
    - **Felkerekítés a teljes azonosítótáblára és FEFO-kötegre** – Ez a stratégia egyesíti a *FEFO-köteg lefoglalása* és a *Felkerekítés a teljes azonosítótáblára* stratégiák elemeit. Csak olyan köteg-engedélyezett cikkekre és helyutasításokra érvényes, amelyek munkatípusa *Kitárolás*. A sornak köteg-engedélyezettnek kell lennie a *FEFO-köteg foglalása* stratégia használatához, és a *Felkerekítés a teljes azonosítótáblára* stratégia csak a feltöltéshez használható. Ha ez a stratégia egy helyraktározási korláttal van konfigurálva, akkor a kijelölt betárolási munka helyének túlterhelését és a készletezési korlátok figyelmen kívül hagyását okozhatja.
    - **Felkerekítés a teljes azonosítótáblára** – Ez a stratégia felfelé kerekíti a készletmennyiséget, így az megegyezik az azonosítótábla mennyiségével, és ezt a mennyiséget a kitárolandó cikkekhez is hozzárendeli. Ezt a stratégiát csak a *Kitárolás* típus feltöltési helyutasításához használhatja. Ha ez a stratégia egy helyraktározási korláttal van konfigurálva, akkor a kijelölt betárolási munka helyének túlterhelését és a készletezési korlátok figyelmen kívül hagyását okozhatja.
    - **Azonosítótábla-vezérelt** – Használja ezt a stratégiát, amikor a raktár számára kiadja a rendelést a kitárolási és betárolási munka létrehozásához. Ezt a megközelítést több azonosítótáblára is alkalmazhatja. Ez a stratégia megpróbálja lefoglalni az átmozgatási rendelés soraihoz társított azonosítótáblát tartalmazó helyeket, és megpróbál kitárolási munkát létrehozni. Ha azonban ezeket a műveleteket nem lehet végrehajtani, de továbbra is létre szeretne hozni kitárolási munkát, akkor vissza kell lépnie egy másik helyutasítási műveletstratégiára. Az üzleti folyamat követelményeitől függően érdemes lehet a raktár egy másik területén is keresni.
    - **Üres hely, amely nem rendelkezik bejövő munkával** – Ez a stratégia az üres helyek meghatározására használható. Egy hely üresnek tekinthető, ha nincsen fizikai készlete és nincs bejövő munkája. Ezt a stratégiát csak a *Betárolás* munkatípusú helyutasításokhoz használhatja.
    - **FIFO-helykorosítás** – Az először be, először ki (FIFO) stratégiával mind a kötegelt nyomon követett cikkek, mind a nem kötegelt követett cikkek szállíthatók a készlet raktárba érkezésének dátuma alapján. Ez a funkció különösen a nem kötegelt nyomon követett készletekben hasznos, ahol nem található lejárati dátum a rendezéshez. A FIFO-stratégia megtalálja azt a helyet, amely a legrégebbi korosítási dátumot tartalmazza, és a kitárolást a korosítási dátum alapján osztja el.
    - **LIFO-helykorosítás** – Az utoljára be, utoljára ki (LIFO) stratégiával mind a kötegelt nyomon követett cikkek, mind a nem kötegelt követett cikkek szállíthatók a készlet raktárba érkezésének dátuma alapján. Ez a funkció különösen a nem kötegelt nyomon követett készletekben hasznos, ahol nem található lejárati dátum a rendezéshez. A LIFO-stratégia megtalálja azt a helyet, amely a legújabb korosítási dátumot tartalmazza, és a kitárolást a korosítási dátum alapján osztja el.

## <a name="example-using-location-directives"></a>Példa: Helyutasítások használata

Ehhez a példához egy olyan beszerzési rendelési folyamatot veszünk alapul, ahol a helyutasításnak szabad területet kell találnia egy raktáron belül, azoknak a készletcikkeknek, amiket most regisztráltak a bevételezési területen. Először szabad kapacitást kell találnia a raktár területén, az aktuális készlet konszolidálásával. Ha a konszolidáció nem lehetséges, üres helyet kell találnia.

Ebben az esetben két helyutasítási műveletet kell megadni. A sorozat első művelete a *Konszolidálás* stratégiája, a másodiknak az *Üres hely bejövő munka nélkül* stratégiáját használjuk. Hacsak nem ad meg műveletet a túlcsordulás kezelésére, két végkifejlet lehetséges akkor, ha nincs több kapacitása a raktárnak: a munka létrehozható, habár nem lesz hely meghatározva, vagy a munka-létrehozási folyamat sikertelenül zárul. Az eredményt a **Helyutasítási hibák** lap beállításai határozzák meg, ahol eldöntheti, hogy beállítja-e a **Munka leállítása, ha a helyutasítások sikertelenek** lehetőséget minden Munkarendelés-típushoz.

## <a name="next-step"></a>Következő lépés

Miután helyutasításokat hozott létre, összekapcsolhat minden utasításkódot egy munkasablon-kóddal a munkalétrehozáshoz. Bővebb információkért lásd: [Raktári munka ellenőrzése munkasablonok és helyutasítások használatával](./control-warehouse-location-directives.md).

## <a name="additional-resources"></a>További erőforrások

- Videó: [Raktárkezelési konfiguráció teljes részletességgel](https://community.dynamics.com/365/b/techtalks/posts/warehouse-management-configuration-deep-dive-october-14-2020)
- Súgócikk: [A raktári munka vezérlése munkasablonok és helyi irányelvek segítségével](control-warehouse-location-directives.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]