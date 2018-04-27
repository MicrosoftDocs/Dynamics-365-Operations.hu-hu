---
title: "Jelentési fa definíciója a pénzügyi jelentésekben"
description: "Ez a cikk a jelentési fa definíciójáról tartalmaz információt. A jelentési fa definíciója a jelentés azon összetevője vagy építőeleme, amely segít meghatározni szervezetének szerkezetét és hierarchiáját."
author: twheeloc
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 57592
ms.assetid: 747faa47-9a23-4277-bc11-8d0a1267c3a4
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 78dd1b5e0a19690ffefdb03de495061ef51f2e16
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="reporting-tree-definitions-in-financial-reports"></a>Jelentési fa definíciója a pénzügyi jelentésekben

[!INCLUDE [banner](../includes/banner.md)]

Ez a cikk a jelentési fa definíciójáról tartalmaz információt. A jelentési fa definíciója a jelentés azon összetevője vagy építőeleme, amely segít meghatározni szervezetének szerkezetét és hierarchiáját.

A Pénzügyi jelentéskészítő támogatja a rugalmas jelentést, így egyszerűen módosíthatja, ha a vállalat szerkezete megváltozik. A jelentések különböző összetevőkből vagy építőelemekből állnak. Az egyik ilyen építőelem a jelentési fa definíciója. Jelentési fa meghatározása segít a szervezeti szerkezet és hierarchia meghatározásában. Ez egy dimenziókon átnyúló hierarchia a pénzügyi adatok dimenzionális kapcsolatai alapján. Jelentési egység és összefoglaló szinten biztosít információt a fa minden eleméről. A Jelentési fa definíciók kombinálhatók oszlopdefiníciókkal és a jelentésdefiníciókkal alapvető egységek csoportjának létrehozásához, amely több vállalat által használható. Egy jelentési egységet egy szervezeti diagram minden mezője használ. Egy jelentési egység lehet például egy részleg a pénzügyi adatokon belül, de léteznek olyan magas szintű összesítő egységek is, amelyek más jelentési egységek adatait kombinálják. Egy jelentési fát tartalmazó jelentésdefinícióhoz egy jelentés készül minden jelentési egységhez és az összegző szinthez. Ezek a jelentések mind sor- és oszlopdefiníciókat használnak, amelyek meg vannak határozva a jelentésdefinícióban, kivéve, ha a jelentésdefiníció megadja, hogy a jelentési fát kell használni a sordefinícióból. A sor- és oszlopdefiníciók fontos elemei a pénzügyi jelentések tervezésének és funkciójának. A jelentési fák növelik a komponensek erejét, és támogatják a rugalmas jelentést, ahogyan változik a vállalat struktúrája. A pénzügyi kimutatások, melyek nem a jelentési fán alapszanak, a Pénzügyi jelentés szolgáltatásai közül csak néhányat használnak. Több jelentési fa definíciót használhat egyszerre ugyanazokkal a sor- és oszlopdefiníciókkal, így különböző módokon tekintheti meg a szervezet adatait.

## <a name="reporting-tree-best-practices"></a>Jelentési fa legjobb gyakorlatai
Mielőtt létrehoz egy jelentési fát, vegye figyelembe a következő gyakorlati tanácsokat:

-   Először határozza meg, mely jelentési dimenziókat követeli meg a jogi személy vagy a vállalat.
-   Fontolja meg, hogyan állította fel a szerkezetét, és ezután rajzolja meg a vállalat szervezeti diagramját. A szervezeti diagram szemléletesebbé teszi a felépítést, így könnyebben el tudja képzelni, hogyan csoportosíthatja a jelentési egységeket egy vagy több jelentésfába.
-   Kezdje a legalacsonyabb rendelkezésre álló részletességi szinttel, például a részlegek és a projektek, amelyeket a pénzügyi adatok határoznak meg. Tetszőleges számú mezők hozzáadása a részletességi szinthez, a magasabb szintű osztályok és régiók megjelenítéséhez. Minden mező egy lehetséges jelentési egységet képvisel bármely jelentési fán belül.
-   A fa összeállítására való legjobb módszerét is ki kell alakítania. Egy automatikus építőfolyamat segítségével hozhat létre jelentési fát, vagy Ön is létrehozhatja azt. Fontos, hogy mindkét módszert megértse, mielőtt belevág a fák tervezésébe.
-   A jelentési egységeket, melyek a pénzügyi adatok rendszerében vannak megadva, arra használhatja, hogy jelentési egységeket adjon hozzá a jelentési fa definíciójához.

## <a name="create-multiple-reporting-trees"></a> Több jelentési fa létrehozása
Korlátlan számú jelentési fát hozhat létre, hogy szervezete adatait különböző módokon tekinthesse meg. Az egyes jelentési fák a részlegek és összegző egységek tetszőleges kombinációját tartalmazhatják. A jelentés definíciója csak egy jelentési fára mutató hivatkozást tartalmazhat. A jelentési egységek szerkezetének átrendezésével, különböző jelentési fákat hozhat létre. Ezután használhatja ugyan azt a sor- és oszlopdefiníciót a különböző jelentési fákhoz. Ezzel a módszerrel gyorsan hozhat létre különböző pénzügyi jelentés-elrendezéseket. Ha több különböző jelentési fát hoz létre, havonta kinyomtathatja a pénzügyi kimutatásokat, és többféleképpen elemezheti és mutathatja be vállalata műveleteit. További információkért, lásd a példákat a jelentési egységek struktúráira a témakör végén.

## <a name="create-a-reporting-tree-definition"></a> Jelentési fa definíciójának létrehozása
A jelentési fa meghatározása az alábbi táblázatban leírt oszlopokat tartalmazza.


| Jelentési fa oszlop |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           Leírás                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        Cég        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          A jelentési egység vállalati neve. Az <strong>@ANY</strong> érték, amely rendszerint csak az összesítő szintjéhez van hozzárendelve, lehetővé teszi, hogy a jelentési fát az összes vállalatra vonatkozóan használni lehessen. Minden gyermek ághoz hozzá van rendelve egy vállalat.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|       Egység neve       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   A kód, amely azonosítja ezt a jelentési egységet a grafikus jelentési fán. Bizonyosodjon meg róla, hogy egy konzisztens kódolási rendszert hoz létre, amit a felhasználók könnyen megérthetnek.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|   Egység leírása    |                                                                                                                                                                                                                                                                                                                                                                                                                                                        A jelentési egység címe megjelenik jelentés fejlécében vagy a láblécben, az <strong>UnitDesc</strong> kódként való megadásakor a jelentésdefiníció <strong>Fejlécek és láblécek</strong> lapján. A cím megjelenik a jelentés sorleírásában, ha beírja az <strong>UnitDesc</strong> kódot a sordefiníció <strong>Leírás</strong> cellájába.                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|      Dimenziók       |                                                                                                                                                                                                                                                                                                                                                                      Egy jelentési egység, amely az adatokat közvetlenül pénzügyi adatokból vonja ki. A fiók és a kapcsolódó szegmensek logikai pozícióját és hosszát határozza meg. Ebben az oszlopban minden jelentési egység sornak rendelkeznie kell egy dimenzióval. Helyezhet dimenziót az összesítő egység sorába (például azokhoz a költségekhez, amelyek közvetlenül kapcsolódnak az egységhez) Ha beír egy dimenziót egy összesítő egység sorába, azokat a fiókokat, amelyeket fölérendelt egységek használnak, nem szabad használni alárendelt egységekben. Ellenkező esetben az összegek megduplázódhatnak.                                                                                                                                                                                                                                                                                                                                                                      |
|    Sordefiníciók    |                                                                                                                                                                                                                                                                                                                                                                                        A jelentési egység sordefiníciójának neve. Ez a sordefiníció használatos a jelentésfa minden egyes egységéhez. Jelentés létrehozásakor ez a sordefiníció használatos minden egyes jelentési egységhez. A sordefiníció több pénzügyi dimenzióra mutató hivatkozást is tartalmazhat. Ha a jelentésfában meg van adva sordefiníció, jelölje be a <strong>Sordefiníció használata a jelentésfából</strong> négyzetet a jelentésdefiníció <strong>Jelentés</strong> lapján.                                                                                                                                                                                                                                                                                                                                                                                        |
|       Sorösszekapcsolás        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            A jelentési egységhez használandó sorösszekapcsolás. A sorösszekapcsolások abból a célból vannak megadva a sordefinícióhoz, hogy azonosítsák az összekapcsolási cél pénzügyi dimenziókat.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|     Külső összekapcsolás     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   A jelentési egységhez használandó külső összekapcsolás. A sorhivatkozások a sordefinícióhoz vannak megadva, a hivatkozott jelentés azonosítása céljából.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|     Külső file     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              A pénzügyi jelentés munkalapjának elérési címe az adatok lekéréséhez.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|     Oldalbeállítások      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Ez az oszlop szabályozza, hogy a jelentési egység részletei le legyenek-e tiltva a jelentés megtekintésénél vagy nyomtatásánál.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|       Összesítő %        | A jelentési egység százalékszáma, melyet hozzá kell rendelni a fölérendelt egységéhez. A százalék, amelyet ebben az oszlopban ad meg, a sordefiníció összes sorára érvényes, mielőtt a sor értéke hozzá lesz adva a fölérendelt jelentéshez. Például ha egy alárendelt egységet két részleg között egyenlően kell elosztani, az összegeket minden sorban meg kellene szorozni 50 %-kal, mielőtt hozzáadjuk részlegjelentéshez. Egy jelentési egység nem rendelkezhet két fölérendelt egységgel. Egy jelentési egységnek nem lehet két fölérendelt egysége. Ahhoz, hogy az összegeket a jelentési egységektől a fölérendelt egységekhez rendelje, hozzon létre egy másik jelentési egységet ugyanazzal a dimenzióval, hogy a további 50 százalékot továbbvihesse. Teljes százalékokat adjon meg, tizedesvessző nélkül. Például a <strong>25</strong> 25 %-os foglalást jelent a fölérendeltnek. Ha tizedesvesszőt használ (<strong>,25</strong>), akkor 0,25 százalék lesz foglalva a fölérendeltnek. Az 1 százaléknál kisebb százalékértékek használatához használja az <strong>Összesítő &lt;1 % engedélyezése</strong> opciót a jelentésdefinícióban. Ez a beállítás a <strong>További lehetőségek</strong> lapon, a <strong>Jelentésbeállítások</strong> párbeszédpanelen található. Ez a párbeszédpanel az <strong>Egyebek</strong> gombra kattintva a jelentésdefiníció <strong>Beállítások</strong> lapján érhető el. |
|     Egységbiztonság     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   Korlátozások, melyekkel a felhasználók és csoportok elérhetik a jelentési egység adatait.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|    További szöveg    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               Az a szöveg, amely a jelentésben szerepel.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |

Jelentési fa definíciójának létrehozásához kövesse az alábbi lépéseket:

1.  Nyissa meg a Jelentéstervezőt.
2.  Kattintson a **Fájl** &gt; **Új** &gt; **Jelentési fa definíciója** lehetőségekre.
3.  Kattintson a **Szerkesztés** &gt; **Jelentési egységek beszúrása dimenziókból** lehetőségekre.
4.  A **Jelentési egységek beszúrása dimenziókból** párbeszédpanelen jelölje be a jelölőnégyzetet minden dimenzióhoz, amelyeket bele akar venni a jelentési fába. A **Jelentési egységek beszúrása dimenziókból** párbeszédpanel a következő részeket tartalmazza.

    | Szakasz                          | Leírás                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
    |----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Dimenzió-szegmentálás jelentése | Használja a **Szegmensek felosztása** és a **Szegmensek egyesítése** gombokat, hogy megváltoztassa a szegmensek számát és hosszát. **Megjegyzés:** Csak a felosztott szegmenseket egyesítheti. Több dimenzió kombinálására helyettesítő karakterek is használhatók a dimenzióértékekben.                                                                                                                                                                                                          |
    | Belefoglalás/Karakterpozíció       | Ez a rész felsorolja a dimenziókat, amelyek meg vannak határozva a pénzügyi adatokban és megmutatja minden dimenzióhoz a karakterek számát a leghosszabb definiált értékben. Jelölje be a dimenzió jelölőnégyzetét, ha bele akarja foglalni a jelentési fahierarchiába.                                                                                                                                                                                           |
    | Szegmenshierarchia és tartományok     | Ez a rész bemutatja a dimenzió hierarchiákat. A dimenziókat áthelyezheti a listában a jelentési sorrend módosításához. Adjon meg egy értéktartományt minden dimenzióhoz a **Forrásként használt dimenzió** és a **Célként használt dimenzió** mezőkben. Ha nem ad meg egy tartományt, minden dimenzió érték be lesz illesztve a jelentési fába. **Megjegyzés:** Ha egynél több dimenziót használ, csak a feladott dimenzió kombinációk fognak megjelenni eredményként. |

    Képernyőképért, ami egy példát mutat a **Jelentési egységek beszúrása a dimenziókból** párbeszédpanelre, lásd a „Példa a Jelentési egységek beszúrása dimenziókból párbeszédpanelre" szakaszt.
5.  További szegmensek létrehozásához (például egy szegmens két rövidebb szegmensre osztásához), kattintson a megfelelő helyre egy **Karakterpozíció** mezőben, majd kattintson a **Szegmensek felosztása** lehetőségre.
6.  Két szegmens egy szegmenssé egyesítéséhez kattintson bele valamelyik szegmens jelölőnégyzetébe, majd kattintson a **Szegmensek kombinálása** elemre.
7.  A hierarchia határozza meg, hogy a dimenziók hogyan jelentenek egymás felé, minden dimenzió tartományát. A dimenziók hierarchiájának módosításához a **Szegmenshierarchia és -tartományok** területen válassza ki az áthelyezendő dimenziót, és kattintson a **Mozgatás fel** vagy a **Mozgatás le** lehetőségre.
8.  Új jelentési fánál dimenzióértékek tartományának meghatározásához a **Szegmenshierarchia és -tartományok** területen kövesse az alábbi lépéseket:
    1.  A dimenzió **Forrásként használt dimenzió** mezőjében írja be az első értéket a tartományban.
    2.  A **Célként használt dimenzió** mezőjében írja be az utolsó értéket a tartományban.

9.  Minden egyes dimenzióhoz a **Szegmenshierarchia és tartományok** területen ismételje meg a 7. és 8. lépést.
10. Miután befejezte annak a meghatározását, hogy hogyan kerüljenek a jelentési egységek az új jelentési fába, kattintson az **OK** lehetőségre.
11. Kattintson a **Fájl** &gt; **Mentés** parancsra a jelentési fa elmentéséhez. Adjon meg egyedi nevet és leírást a jelentési fának, és kattintson az **OK** lehetőségre.

### <a name="open-an-existing-reporting-tree-definition"></a>Egy meglévő jelentési fa definíciójának megnyitása

1.  A Jelentéstervezőben kattintson a **Jelentési fa definíciói** lehetőségre a navigációs ablakban.
2.  Kattintson duplán egy névre a jelentési fák listájában annak megnyitásához.
3.  A jelentési fához társított bármely építőelem megtekintéséhez kattintson a jobb gombbal a jelentési fa-definícióra, és válassza ki a **Társítások** lehetőséget.

### <a name="roll-up-data-in-a-reporting-tree"></a>A jelentési fa adatainak összesítése

A jelentési fa segítségével összesítheti az alárendelt jelentési egységek összegeit a fölérendelt jelentési egység szintjén. Ennek az aggregálásnak a neve az adatok összesítése. Az alábbi szabályok segítségével lehet összesíteni az összegeket a fölérendelt jelentési egységekben a jelentési fán belül:

-   A jelentési fán belül az alárendelt egységeknek dimenziókat kell tartalmazniuk, kivéve ha egy egyszintű fáról van szó. A fölérendelt egységek általában nem tartalmaznak dimenziókat a jelentési fában. **Megjegyzés:** Ha a dimenziókat az alá- és fölérendelt egységekben is megadjuk, ez dupla adatokat eredményezhet a jelentésben.
-   A jelentési egységek, amelyek a jelentési fában dimenziókat tartalmaznak, megfelelnek azoknak a dimenzióknak, melyek a sor- és oszlopdefiníciókban használatosak. A dimenziók kombinációja határozza meg az adott egységbe visszatérő összegeket. Például a 2. példában a 6. és 7. sorok csak a 00 és 01 részlegek értékeit küldik vissza.
-   A jelentési fában dimenziókat nem tartalmazó fölérendelt jelentési egységek mennyiségeit az alárendelt egység jelentéséből kell meghatározni, és ezt a mennyiséget kell összesíteni a fölérendelt egységbe. Például ha a fölérendelt egység (lásd a Contoso USA 2. példában az adatok összesítését) két alárendelt egységgel rendelkezik (022 és 023), és nem tartalmaz dimenziókat, egy jelentés keletkezik minden alárendelt egységhez és a fölérendelt egységhez. A fölérendelt egység teljes összege a két alárendelt mennyiség összege.

### <a name="manage-reporting-units"></a>Jelentési egységek kezelése

Minden jelentési fa definíció egyedien van megjelenítve. A grafikus nézet a fölé-alárendelt hierarchia megjelenítésére és a munkalap nézetre alkalmas, amely tartalmazza a konkrét adatokat minden jelentési egységre vonatkozóan. A grafikus nézet és a munkalap össze vannak kapcsolva. Ha egy nézetben kiválaszt egy jelentési egységet, azt a másik nézetben is kiválasztja. Létrehozhat dimenziókon átnyúló hierarchiákat a pénzügyi adatok dimenzionális kapcsolatai alapján. Jelentési fa definíciójának létrehozásakor többször is használhatók ugyanazok a sordefiníciók, függetlenül attól, hogy a részleg bevételi kimutatását hozza-e létre vagy egy konszolidált bevételi jelentést. A sordefinícióban megadott dimenziók kombinálhatók a jelentési fa meghatározásában lévő dimenziókkal, hogy számos nézetben tekinthesse meg vállalata működését.

### <a name="reporting-unit-structure"></a> Jelentési egységek struktúrája

A következő típusú jelentési egységek használhatók a pénzügyi jelentéskészítőben:

-   A részletegység az adatokat közvetlenül a pénzügyi adatokból nyeri, egy Excel-munkalapból, vagy egy másik pénzügyi jelentéskészítő munkalapról.
-   Az összesítő egység összegzi az alacsonyabb szintű egységek adatait.

A fölérendelt jelentési egység egy összesítő egység, amely egy részletegység adatait összesíti. Az összefoglaló egység lehet részletegység és összesítő egység. Ezért az összesítő egység kinyerhet információt egy alacsonyabb egységből, a pénzügyi adatokból vagy egy Excel-munkalapból. A fölérendelt egység lehet egy magasabb szintű fölérendelt egység alárendelt egysége. Az alárendelt jelentési egység lehet részletegység, amely az információt közvetlenül a pénzügyi adatokból vagy egy Excel-munkalapból nyeri. Az alárendelt egység lehet köztes összesítő egység. Más szóval lehet egy alacsonyabb szintű egység fölérendelt egysége, valamint lehet egy magasabb szintű egység alárendelt egység. A leggyakoribb eset a jelentési egységek esetében, hogy a **Dimenziók** oszlopban üres cellával rendelkező fölérendelt egységük van, és vannak alárendelt egységeik, melyek bizonyos vagy helyettesítő dimenziókombinációkra mutató hivatkozásokkal rendelkeznek.

### <a name="organize-reporting-units"></a> Jelentési egységek rendezése

Egy jelentési fa definíciójának szervezeti felépítését átrendezheti a jelentési egységek grafikus nézetben történő áthelyezésével. A jelentési fában magasabb szintre is helyezhet a jelentési egységeket, és alacsonyabb szintre is teheti őket.

1.  A módosításhoz a Jelentéstervezőben nyissa meg a jelentési fa definícióját.
2.  Válasszon ki egy jelentési egységet a jelentési fa definíciójának grafikus nézetében.
3.  Húzza az egységet új helyre. Másik lehetőségként húzza át az egységet egy új pozícióba, vagy kattintson a jobb gombbal, és válassza a **Jelentési egység előléptetése** vagy a **Jelentési egység visszafokozása** lehetőséget.
4.  A változtatások mentéséhez kattintson a **Fájl** &gt; **Mentés** gombra.

### <a name="add-text-about-a-reporting-unit"></a> A jelentési egységgel kapcsolatos szöveg hozzáadása

A további szöveg olyan statikus karakterlánc, amely legfeljebb 255 karakterből állhat, és amely olyan információt ad hozzá jelentési fa definíciójához. Például a további szöveg lehet a vállalat rövid leírása. Legfeljebb tíz további szöveget adhat hozzá minden jelentési egységhez egy jelentési fa definícióján belül. A további szöveg megjelenik a jelentési egység jelentésében, amelyhez a szöveg hozzá van rendelve. Szövegeket a sordefiníció **Leírás** oszlopából és a jelentésdefinícióban a **Fejlécek és Láblécek** lapról adhat hozzá.

1.  A módosításhoz a Jelentéstervezőben nyissa meg a jelentési fa definícióját.
2.  Kattintson duplán a **További szöveg** cellára a jelentési egység sorához.
3.  A **További szöveg** párbeszédpanel első üres sorában írja be a szöveget. Az első szöveget tartalmazó sor UnitText1 néven van megadva, függetlenül a **További szöveg** párbeszédpanelben elfoglalt helyétől.
4.  Ha a jelentési egységhez további szövegeket kíván hozzáadni, írja be a szöveget egy üres sorba.
5.  Kattintson az **OK** gombra.

### <a name="remove-additional-text-from-a-reporting-unit"></a>További szöveg eltávolítása a jelentési egységből

1.  A Report Designer alkalmazásban nyissa meg a módosítani kívánt jelentésfa-definíciót.
2.  Kattintson duplán a **További szöveg** cellára a jelentési egység sorában.
3.  A **További szöveg** párbeszédpanelen válassza ki az eltávolítani kívánt szöveget, és kattintson a **Törlés** lehetőségre. Másik lehetőségként a diagramban kattintson a jobb gombbal, majd válassza a **Kivágás** menüpontot.
4.  Kattintson az **OK** gombra.

### <a name="restrict-access-to-a-reporting-unit"></a>Hozzáférés korlátozása egy jelentési egységhez

Egyes felhasználók és csoportok számára megakadályozhatja a hozzáférést egy jelentési egységhez. Meg is adhat korlátozásokat, így azok alkalmazva lesznek a jelentési egység alárendelt jelentési egységeire.

1.  A módosításhoz a Jelentéstervezőben nyissa meg a jelentési fa definícióját.
2.  Kattintson duplán az **Egység biztonsága** cellára annak a jelentési egységnek a sorában, amelynek az elérhetőségét korlátozni szeretné.
3.  Az **Egységbiztonság** párbeszédpanelen kattintson a **Felhasználók és csoportok** részre.
4.  Válassza ki a felhasználókat vagy csoportokat, amelyek rendelkezhetnek hozzáféréssel a korlátozott jelentési egységhez, majd kattintson az **OK** gombra.
5.  A hozzáférés korlátozásához az alárendelt jelentési egységeknél jelölje be a **Védelem hozzáadása az alárendelt jelentési egységekhez** jelölőnégyzetet.
6.  Kattintson az **OK** gombra.

### <a name="remove-access-to-a-reporting-unit"></a>Hozzáférés eltávolítása egy jelentési egységhez

1.  A módosításhoz a Jelentéstervezőben nyissa meg a jelentési fa definícióját.
2.  Kattintson duplán az **Egységbiztonság** cellára a jelentési egység sorában a hozzáférés eltávolításához.
3.  Az **Egységbiztonság** párbeszédpanelen válasszon ki egy nevet, majd kattintson az **Eltávolítás** gombra.
4.  Kattintson az **OK** gombra.

### <a name="link-to-reports"></a>Hivatkozás a jelentésekhez

Miután létrehozott egy **jelentés** oszlopot a sordefinícióban, és megadta a jelentést, melynek szerepelnie kell a jelentésben, frissítenie kell a jelentési fát a csatolt oszloppal és a jelentés adataival. Egy jelentés bármely egységbe lehet importálni a jelentési fában.

### <a name="identify-the-report-in-a-reporting-tree"></a>A jelentés azonosítása a jelentési fában.

1.  A módosításhoz a Jelentéstervezőben nyissa meg a jelentési fa definícióját.
2.  A **Sordefiníciók** oszlopban a kijelölt sor információi alapján jelenítenek meg információkat, mivel ugyanazt a sordefiníciót kell használni a jelentési fa összes egységében. Kattintson duplán a **Sordefiníciók** cellára, és válassza ki azt a sordefiníciót, amely a jelentéssel kapcsolatban tartalmaz tájékoztatást.
3.  A jelentési egység **Munkalap hivatkozás** cellájában válassza ki a hivatkozás nevét, amely megfelel a jelentésnek.
4.  A jelentési egység **Munkafüzet vagy jelentés elérési útja** cellájában írja be a jelentés nevét vagy tallózással keresse meg a jelentést.
5.  Egy munkalap meghatározásához a jelentésben írja be a munkalap nevét a **Munkalapnév** cellába.
6.  Ismételje meg a 3–5. lépéseket minden jelentési egységnél, melyeknek adatokat kell kapniuk a jelentésből. A jelentésben szereplő hibás adatok megakadályozásához győződjön meg arról, hogy a megfelelő jelentésnevek szerepelnek a jelentési fa a megfelelő egységében.

## <a name="examples"></a>Példák
### <a name="reporting-unit-structure--example-1"></a>Jelentési egységek struktúrája – 1. példa

A következő jelentési fában a jelentési egység struktúrája a következő:

-   A Contoso Japan jelentési egység a Contoso Japan Értékesítés fölérendelt egysége, valamint a Contoso Japan Konzultáció alárendelt egysége.
-   A Contoso Japan Értékesítési osztály egysége a Contoso Japan alárendelt egysége, és egyben a Kiskereskedelmi Értékesítés és a Nagykereskedelmi Értékesítés fölérendelt egysége.
-   A legalacsonyabb szintű részletjelentési egységek (Kiskereskedelmi Értékesítés, Nagykereskedelmi Értékesítés, Ügyfélszolgáltatások és Műveletek) a pénzügyi adatok a részlegeit képviselik. Ezek a jelentési egységek a diagram árnyékolt területén találhatók.
-   A magasabb szintű összesítő egységek összesítik a részletegységek adatait.

[![ContosoEntertainmentSummaryReportStructure](./media/contosoentertainmentsummaryreportstructure.png)](./media/contosoentertainmentsummaryreportstructure.png)

### <a name="reporting-unit-structure--example-2"></a>Jelentési egységek struktúrája – 2. példa

A következő ábra bemutat egy jelentési fát, amely megjelenít egy szervezeti struktúrát, vállalati funkciók szerint van felosztva. [![summaryofallunitscontoso](./media/summaryofallunitscontoso.png)](./media/summaryofallunitscontoso.png)

### <a name="example-of-the-insert-reporting-units-from-dimensions-dialog-box"></a>Példa a Jelentési egységek beszúrása dimenziókból párbeszédpanelre

A következő ábra példa a **Jelentési egységek beszúrása dimenziókból** párbeszédpanelre. Ebben a példában az eredmény az üzleti egység, a költséghelyek és a részlegek kombinációja lesz. [![InsertReportingUnits](./media/insertreportingunits.png)](./media/insertreportingunits.png) A létrejövő jelentési fa definíció először üzleti egység szerint, majd költséghely, illetve részleg szerint lesz listázva. Az ötödik jelentési egység dimenziója az **Üzleti Egység = \[001\], Költséghely =\[\], Részleg = \[022\]**, valamint ez azonosítja a jelentési egységet a számlákhoz, amelyek a 001-es üzleti egységre és a 022-es részlegre vonatkoznak. [![ReportingTree](./media/reportingtree-1024x646.png)](./media/reportingtree.png)

### <a name="examples-of-data-roll-up"></a>Példák összesítési adatokra

Az alábbi példák lehetséges információkat mutatnak, melyeket a jelentési fa definíciójában lehet használni az adatok összesítésének példájával.

#### <a name="example-1"></a>1. példa

[![MutliCompanyRollUp](./media/mutlicompanyrollup.png)](./media/mutlicompanyrollup.png)

#### <a name="example-2"></a>2. példa

[![CrossCompanyDepartmentRollUp](./media/crosscompanydepartmentrollup.png)](./media/crosscompanydepartmentrollup.png)

# <a name="see-also"></a>Lásd még

[Pénzügyi jelentéskészítés](financial-reporting-intro.md)




