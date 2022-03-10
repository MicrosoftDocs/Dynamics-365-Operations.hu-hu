---
title: A PDF-sablonokat kitöltő ER-konfigurációk megtervezése
description: Ez a témakör a PDF-sablon kitöltéséhez szükséges elektronikus jelentéskészítési (ER) formátum megtervezésével kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: a568ddd93bfbc7d536e951a13470b3dedb796e1b
ms.sourcegitcommit: 753714ac0dabc4b7ce91509757cd19f7be4a4793
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/01/2022
ms.locfileid: "8367856"
---
# <a name="design-er-configurations-to-fill-in-pdf-templates"></a>A PDF-sablonokat kitöltő ER-konfigurációk megtervezése

[!include[banner](../includes/banner.md)]

Az ebben a témakörben szereplő eljárások példák arra, hogy egy **Rendszergazda** vagy **Elektronikus jelentések fejlesztője** szerepkörrel rendelkező felhasználó hogyan tudja konfigurálni az Elektronikus jelentéskészítési (ER) formátumot, amely PDF-formátumban jelentéseket hoz létre jelentéssablonként használt, kitölthető PDF-dokumentumok segítségével. Ezeket a lépéseket bármely Dynamics 365 Finance vagy Regulatory Configuration Service (RCS)-vállalatban végrehajthatja.

## <a name="prerequisites"></a>Előfeltételek

A művelet elkezdése előtt rendelkeznie kell az alábbi hozzáférések egyikével, a témakörben említett eljárások végrehajtásához használt szolgáltatástól függően:

- Hozzáférés a Finance alkalmazáshoz a következő szerepkörök egyikével:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

- Hozzáférés a RCS alkalmazáshoz a következő szerepkörök egyikével:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

Ezenkívül el kell végeznie a [Konfigurációszolgáltatók létrehozása és megjelölésük aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.

Végül töltse le az alábbi fájlokat.

| Tartalom leírása                       | Fájlnév                                     |
|-------------------------------------------|-----------------------------------------------|
| A jelentés első oldalának sablonja | [IntrastatReportTemplate1.pdf](https://download.microsoft.com/download/0/8/3/0832c82b-4448-4562-afbf-01e0efc8d999/IntrastatReportTemplate1.pdf)                  |
| A jelentés további oldalainak sablonja    | [IntrastatReportTemplate2.pdf](https://download.microsoft.com/download/c/7/a/c7a8a806-2192-4034-9052-e8b84b527d5e/IntrastatReportTemplate2.pdf)                  |
| Minta ER-formátum – PDF                          | [Intrastat-jelentés (PDF).version.1.1.xml](https://download.microsoft.com/download/a/8/7/a87aea3e-3f60-404c-8899-c471d20e7ea9/IntrastatreportPDFversion1.1.xml)        |
| Minta ER-formátum – Excel                          | [Intrastat (importálás Excel szolgáltatásból).version.1.1.xml](https://download.microsoft.com/download/a/2/c/a2c0c145-d989-4e55-9d47-9647c02e4ee4/IntrastatimportfromExcelversion1.1.xml) |
| Mintaadathalmaz                            | [Intrastat mintaadatok.xlsx](https://download.microsoft.com/download/9/f/1/9f1c5b96-3800-475f-8cf6-1ddd42873758/Intrastatsampledata.xlsx)                    |

## <a name="design-the-format-configuration"></a>A formátumú konfigurációjának kialakítása

### <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Hozzáférés a Microsoft által biztosított konfigurációk listájához

1. Ugorjon a **Szervezeti adminisztráció \> Munkaterületek \> Elektronikus jelentés** pontra.
2. Győződjön meg arról, hogy a **Litware, Inc.** szolgáltató rendelkezésre áll, és aktívként van megjelölve.
3. A **Microsoft** szolgáltató mozaikján válassza ki **Tárházak** lehetőséget.

    > [!NOTE]
    > Ha már létezik az **LCS**-típus tárháza, ugorja át az eljárás további lépéseit.

4. Válassza a **Hozzáadás** lehetőséget.
5. A legördülő párbeszédpanel **Konfigurációs tárház típusa** mezőcsoportjában válassza az **LCS** beállítást.
6. Válassza a **Tárház létrehozása** lehetőséget.
7. Válassza ki az **OK** lehetőséget.

### <a name="get-the-model-configurations-provided-by-microsoft"></a>A Microsoft által biztosított modellkonfigurációk beszerzése

1. A **Konfigurációs tárházak** bal oldalán válassza a **Szűrők megjelenítése** gombot (a tölcsér szimbólumot).
2. A **Typus** mezőben adjon meg egy szűrőt az **LCS** értékére, majd használja a **következővel kezdődik** operátort.
3. Válassza az **Alkalmazás** lehetőséget.
4. Válassza ki a **Megnyitás** lehetőséget.
5. A fastruktúrában válassza ki az **Instrastat modell** elemet.
6. Válassza ki a **Verziók** gyorslap **1.** verzióját.

    > [!NOTE]
    > Ha a **Verziók** gyorslap **Importálás** gombja nem érhető el, ugorja át ennek az eljárásnak a hátralevő lépéseit.

7. Válassza az **Importálás** lehetőséget.
8. Válassza az **Igen** lehetőséget, amellyel megerősíti az **Intrastat modell** modellkonfigurációjának kiválasztott verziójára vonatkozó importálást.

### <a name="create-a-new-format-configuration"></a>Új formátumkonfiguráció létrehozása

1. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** csempét.
2. A fastruktúrában válassza ki az **Instrastat modell** elemet.
3. Válassza a **Konfiguráció létrehozása** lehetőséget.

    > [!NOTE]
    > Ha a **Konfiguráció létrehozása** gomb nem elérhető, akkor tervezési módra kell váltania az **Elektronikus jelentéskészítési paraméterek** oldalon, amelyet az **Elektronikus jelentéskészítés** munkaterületről nyithat meg.

4. A legördülő párbeszédpanel **Új** mezőcsoportjában válassza az **Intrastat-adatmodellen alapuló formátum** beállítást.
5. A **Név** mezőbe írja be: **Intrastat-jelentés (PDF)**.
6. A **Leírás** mezőbe írja be: **Intrastat-jelentés PDF-formátumban**.

    > [!NOTE]
    > Az aktív konfigurációs szolgáltató automatikusan megjelenik. Ez a szolgáltató tartja majd karban ezt a konfigurációt. Ugyan más szolgáltatók is használhatják ezt a konfigurációt, nem tudják majd karbantartani.

7. Nem kötelező: A **Formátumtípus** mezőben kiválaszthatja az elektronikus dokumentum megadott formátumát. Ha a **PDF** lehetőséget választja, a tervezés során az ER Művelettervező csak azokat a formátumelemeket ajánlja fel, amelyek csak a PDF-formátumban létrehozott dokumentumokra érvényesek (**PDF\Fájl**, **PDF\PDF-egyesítés** stb.). Ha ezt a mezőt üresen hagyja, akkor az elektronikus dokumentum formátumát akkor határozzák meg a tervezés során az ER Művelettervezőben, amikor az első formátumelemet hozzáadják. Ha például első formátumelemként az **Excel\Fájl** elemet adja hozzá, az ER Művelettervező csak olyan formátumelemeket fog felajánlani, amelyek az Excel-formátumban létrehozott dokumentumokra érvényesek (**Excel\Cella**, **Excel\Tartomány** stb.). formátum.
8. Válassza a **Konfiguráció létrehozása** lehetőséget.

Létrejött egy új ER formátumkonfiguráció. Ennek a konfigurációnak a Piszkozat verziójában tárolhatja az elektronikus dokumentumok PDF-formátumban történő előállítására kialakított, ER formátum-összetevőt.

### <a name="design-the-format-of-an-electronic-document"></a>Elektronikus dokumentumok formátumának tervezése

A következő lépésként a létrehozott ER formátumkonfigurációban megtervezheti az ER formátumot, amely az **Intrastat kontroll** jelentéset PDF-formátumban hozza létre. A jelentés első oldalának tartalmaznia kell a jelentés összefoglalását, valamint a jelentésben szereplő külkereskedelmi tranzakciók részleteit. A többi oldal csak azokat a külföldi kereskedelmi tranzakciók részleteit jeleníti meg, amelyek a jelentésben szerepelnek. Mivel a létrejövő jelentés oldalainak különböző elrendezéseket kell tartalmazniuk, a program két különböző PDF-formátumú sablont fog használni az ER formátumban.

Egy PDF-megjelenítő programban nyissa meg a letöltött PDF-sablonokat. Figyelje meg, hogy minden sablon több olyan mezőt tartalmaz, amelyeket ki kell tölteni. Minden sablonban a külkereskedelmi tranzakciók részletes adatai 42 sorként jelennek meg, amelyek mindegyikének kilenc mezője van. A sor száma az egyes mezők nevének végén jelenik meg (például **Dátum 1**...**Dátum 42** és **Árucikk 1**...**Árucikk 42**).

A következő ábra a jelentés első oldalának PDF-sablonját jeleníti meg.

![1. sablon](media/rcs-ger-filloutpdf-template1.png)

A következő ábra a jelentés további oldalainak PDF-sablonját jeleníti meg.

![2. sablon](media/rcs-ger-filloutpdf-template2.png)

1. A **Konfigurációk** oldalon válassza a **Tervező** elemet.
2. Válassza a **Gyökér hozzáadása** elemet.
3. A fastruktúra legördülő párbeszédpaneljében válassza a **PDF \> PDF-egyesítés** elemet.

    Amikor kiválasztja a **PDF-egyesítés** elemet a formátum gyökérelemeként, minden futáskor létrejövő PDF-dokumentumot egyetlen végleges PDF-dokumentumba egyesít a program. Ha csak egy PDF-sablon szükséges az összes szükséges dokumentum előállításához a tervezett ER formátummal, kiválaszthatja a **PDF-fájl** lehetőséget gyökérelemként.

4. A **Név** mezőbe írja be a **Kimenet** szót.
5. A **Nyelvi preferenciák** mezőben válassza a **Felhasználói preferencia** lehetőséget. A jelentést a rendszer az ezt futtató felhasználó előnyben részesített nyelvén hozza létre.
6. A **Kulturális preferenciák** mezőben válassza a **Felhasználói preferencia** lehetőséget. A jelentésben szereplő értékeket és dátumokat a rendszer a jelentést futtató felhasználó előnyben részesített területi beállítása alapján formázza.
7. Válassza ki az **OK** lehetőséget.
8. Az **Importálás** lap műveleti ablaktáblájában kattintson az **Importálás PDF-fájlból** pontra.

    Amikor egy kitölthető PDF-dokumentumot sablonként importál ehhez az ER formátumhoz, az összes kötelező ER formátumelem (**PDF-fájl**, **Mezőcsoport** és **Mező** elemek) automatikusan a tervezett formátumban jönnek létre, az importált PDF-dokumentum struktőrája alapján.

9. Válassza a **Tallózás** elemet. Keresse meg és válassza ki az előfeltételként korábban letöltött **IntrastatReportTemplate1. pdf** fájlt.
10. Válassza ki az **OK** lehetőséget.

    A kiválasztott fájl betöltődik, és a **Sablon** mező az **Importálás PDF-fájlból** párbeszédpanelen ki van töltve.

11. Állítsa a **Csoportmezők** beállítást **Igen** értékre. Ha a kiválasztott PDF-dokumentumon minden mezőcsoport szerepel, akkor a rendszer ezekkel a létrejövő ER formátum elemeit csoportosítja. Erre a célra egy **Mezőcsoport** formátumelem jön létre.

    Ha ez a beállítás **Nem** értékre van állítva, akkor a rendszer a szükséges ER formátumelemeket olyan egyszerű elemlistaként fogja létrehozni, amelyet a létrejövő **PDF-fájl** formátumelem alá ágyaz be.

12. Válassza ki az **OK** lehetőséget.

    ![Importálás PDF-fájlból párbeszédpanel.](media/rcs-ger-filloutpdf-importtemplate.png)

13. A fastruktúrában bontsa ki a **Kimenet** csomópontot.

    Figyelje meg, hogy a **PDF-fájl** összetevő automatikusan létrejön a futási időben létrejövő jelentés első oldalának létrehozásának kezelésére.

14. A fastruktúrában bontsa ki a **Kimenet \> PDF-fájl** csomópontot.

    Figyelje meg, hogy a formátumelemek strukturált listája automatikusan létrejön ebben a képernyőn, a korábban importált kitölthető PDF-dokumentum szerkezete alapján.

15. A fastruktúrában válassza a **Kimenet \> PDF-fájl** csomópontot.
16. A **Név** mezőbe írja be az **1. oldal** szót.

    Ez a formátumelem az **Intrastat kontroll** jelentés első oldalának előállítására szolgál. Ez a lap a jelentés összefoglalóját és a külkereskedelmi tranzakciók részletes adatait jeleníti meg.

    Ha üresen hagyja a **Nyelvi beállítások** mezőt, akkor fölérendelt **PDF-egyesítés** elem **Nyelvi beállítások** beállítása határozza meg a nyelvet, amelyen a jelentést ezzel a formátumelemmel létrehozzák majd. A fölérendelt elem beállítását egy másik érték választásával írhatja felül.

    Ha üresen hagyja a **Kulturális beállítások** mezőt, akkor fölérendelt **PDF-egyesítés** elem **Kulturális beállítások** beállítása határozza meg a területi beállítást, amelyen a jelentést ezzel a formátumelemmel létrehozzák majd. A területi beállítás határozza meg a jelentés oldalain látható értékek és dátumok formátumát. A fölérendelt elem beállítását egy másik érték választásával írhatja felül.

17. A műveleti ablaktáblán válassza ki az **Importálás** lapot. Figyelje meg, hogy a **Frissítés PDF-fájlból** gomb aktívvá vált a kiválasztott formátumelem, a **PDF-fájl** számára.

    Ezt a gombot használhatja a frissített PDF-sablonnak a szerkesztett formátumba történő importálásához. A frissített PDF-sablon importálásakor a program ennek megfelelően módosítja a formátumelemek listáját:

    - A frissített PDF-sablonban szereplő minden új mező esetében a szerkesztett ER formátumban új formátumelemek jönnek létre.
    - Ha a frissített PDF-sablon már nem tartalmaz olyan mezőket, amelyek megfelelnek a szerkesztett ER formátumú formátumelemeknek, akkor ezek a formátumelemek törlődnek az ER formátumból.

18. Válassza a **Formátum** lap **Mellékletek** elemét.

    Figyelje meg, hogy az importált PDF-dokumentum a szerkesztett ER formátumhoz van csatolva.

    ![PDF-melléklet előnézete.](media/rcs-ger-filloutpdf-attachedtemplate.png)

19. A második PDF-sablon importálásával folytassa a formátum megtervezését, és adja hozzá a szükséges kötéseket az adatforrásokhoz, és így tovább.
20. Válassza a **Mentés** lehetőséget.
21. Zárja be a lapot.
22. Válassza a **Törlés** lehetőséget.
23. Válassza ki az **Igen** lehetőséget.

Ha szeretné tudni, hogyan lehet új **PDF-egyesítés**, **PDF-fájl**, **Mezőcsoport** és **Mező** formátumelemekkel PDF-formátumú dokumentumokat létrehozni, importálja és elemezze a minta ER formátumot.

### <a name="import-the-format-configuration"></a>A formátumkonfiguráció importálása

Ezután importálja a korábban letöltött minta ER formátumot, amellyel PDF-formátumban hozhatja létre az **Intrastat kontroll** jelentést. A jelentés első oldalának tartalmaznia kell a jelentés összefoglalását, valamint a jelentésben szereplő külkereskedelmi tranzakciók részleteit. A többi oldal csak azokat a külföldi kereskedelmi tranzakciók részleteit jeleníti meg, amelyek a jelentésben szerepelnek.

1. A **Konfigurációk** lapon válassza az **Átváltás \> Betöltés XML-fájlból** elemet.
2. Válassza a **Tallózás** elemet. Keresse meg és válassza ki az előfeltételként korábban letöltött **Intrastat jelentés (PDF).version.1.1.xml** fájlt.
3. Válassza ki az **OK** lehetőséget.

## <a name="analyze-the-format-configuration"></a>A formátumkonfiguráció elemzése

### <a name="format-layout"></a>Formátumelrendezés

1. A **Konfigurációk** lapon a fastruktúrában válassza az **Intrastat modell \> Intrastat-jelentés (PDF)** lehetőséget.
2. Válassza a **Tervező** lehetőséget.
3. Válassza a **Részletek megjelenítése** lehetőséget.
4. A fastruktúrában bontsa ki a **Kimenet: PDF-egyesítés** csomópontot.

    Figyelje meg, hogy ez az ER formátum két **PDF-fájl** elemet tartalmaz, amelyek mindegyike különböző PDF-sablont használt. Az egyik sablon a jelentés első oldalának PDF-formátumban történő létrehozásához használatos, a másik sablon pedig a többi oldal létrehozásához.

5. A fastruktúrában bontsa ki a **Kimenet: PDF-egyesítés \> 1. oldal: PDF-fájl (IntrastatReportTemplate1)** elemet.
6. A fastruktúrában bontsa ki a **Kimenet: PDF-egyesítés \> N. oldal: PDF-fájl (IntrastatReportTemplate2)** elemet.

    Figyelje meg, hogy mivel a két PDF-sablon tartalma különbözik, a két **PDF-fájl** elemhez tartozó beágyazott formátumelemek szerkezete is eltér.

### <a name="format-mapping"></a>Formátum-hozzárendelés

1. A **Formátumtervező** lapon válassza a **Hozzárendelés** fület.
2. A fában bontsa ki a **Lapozás \> Oldalak** elemet.

    ![Képlettervező lap, ahol a modell-fastruktúra ki van bontva.](media/rcs-ger-filloutpdf-reviewformat.png)

    Vegye figyelembe a következőket:

    - A **PDF-fájl** típus **Kimenet \> 1.oldal** formátumeleme nincs hozzákötve egy adatforráshoz sem, és a formátumelem **Engedélyezve** kifejezése üres. Éppen ezért futtatáskor a **IntrastatReportTemplate1** PDF-sablon csak egy alkalommal lesz kitöltve, amikor egy egyéni PDF-dokumentum létrejön.
    - A **PDF-fájl** típus **Kimenet \> N.oldal** formátumeleme a **Rekordlista** típus **Paging.PageN** adatforrásához van kötve, az adott formátumelem **Engedélyezve** kifejezése pedig üres. Éppen ezért futtatáskor a **IntrastatReportTemplate2** PDF-sablon a hozzákötött rekordlista minden rekordja esetén ki lesz kitöltve, amikor egy egyéni PDF-dokumentum létrejön.
    - Mivel az **1. oldal: PDF-fájl** és az **N. oldal: PDF-fájl** formátumelemek a **Kimenet: PDF-egyesítés** formátumelem alárendeltjei, az összes kitöltött PDF-dokumentumot a rendszer egyetlen végső PDF-dokumentumba fog egyesíteni.
    - A **Paging.Page1** és **Paging.PageN** adatforrások konfigurációk alapján a **Paging.Pages** adatforrás rekordjainak szűrőjeként szerepelnek. Ez az adatforrás úgy van konfigurálva, hogy a külkereskedelmi tranzakciók teljes állományát kötegekre osztja fel. Minden egyes köteg legfeljebb 42 rekordot tartalmaz. A következő ER-kifejezés a tranzakciók kötegekre történő felosztása céljából használható:

        SPLITLIST (Totals.CommodityRecord,42)

    - A **Paging.Pages** adatforrásban szerepel a **Paging.Pages.Enumerated** elem, amely a kötegben szereplő minden egyes rekord részleteit visszaadja. Ezek az adatok tartalmazzák a rekord sorszámát a jelenlegi kötegben ( a **Paging.Pages.Enumerated.Number** mezőt). A **Paging.Pages.Enumerated.Number** mezőt a rendszer a **PDF mező** formátumelemek **Név** kifejezésében használja mezőnevek dinamikus létrehozásához, amely a kötegben szereplő tranzakció számán alapul. A létrejövő mező neve ezután a használt PDF-sablon megfelelő PDF-mezőjének kitöltésére szolgál.
    - A **PDF csoport** típus **Kimenet \> N.oldal \> 2. részlet** formátumeleme a **Paging.PageN.Enumerated** adatforráshoz van közve (vagy **\@.Enumerated** ha a **Relatív útvonal** nézet mód van használatban), amely a **Rekordlista** típushoz tartozik. Éppen ezért a futáridő során az adott PDF-csoport beágyazott elemeit a rendszer a hozzákötött rekordlistából származó minden egyes rekordhoz kitölti. Ily módon az egyéni PDF-sorok virtuálisan akkor jönnek létre, amikor a **Paging.PageN.Enumerated** lista 42 rekordjából minden N-edik elemhez kitöltésre kerülnek a következő PDF-mezők: Dátum N, Útvonal N, Árucikk N stb. Ezért ebben az értelemben az adott **Mezőcsoport** formátumelem viselkedése hasonlít az **XML \> Sorozat** és a **Szöveg \> Sorozat** formátumelemére.

3. A fastruktúrában bontsa ki a **Kimenet \> N. oldal \> Adatok 2** csomópontot.
4. A fastruktúrában válassza a **Kimenet \> N. oldal \> Adatok 2 \> PageFooter** elemet.

    Figyelje meg, hogy az adott formátumelem **Név** attribútuma **PageFooter** néven van meghatározva. Azt is figyelje meg, hogy a formátumelem **Név** kifejezése üres.

5. A fastruktúrában válassza a **Kimenet \> N. oldal \> Adatok 2 \> Javítás 1** elemet.

    Figyelje meg, hogy az adott formátumelem **Név** attribútuma **Javítás 1** néven van meghatározva. Azt is észreveheti, hogy a formátumelem **Név** kifejezése a következőként van meghatározva: **Paging.FldName("Javítás",\@.Number)**

![Formátumtervező, ahol a hozzárendelés kiválasztható.](media/rcs-ger-filloutpdf-reviewformat2.png)

Ne feledje, hogy a **Mező** formátumelemet annak a kitölthető PDF-dokumentumnak egyik egyéni mezője kitöltésére használják, amelyet a fölérendelt **PDF-fájl** fáromátumelem sablonjában meghatároztak. A **PDF-fájl** formátumelemének vagy beágyazott elemeinek kötése, ha beágyazott elemekkel rendelkezik, meghatározza a megfelelő PDF-mezőkben megadott értéket. A **Mező** formátumelem különböző tulajdonságai segítségével megadhatja, hogy egy egyéni formátumelem melyik PDF-mező kitöltésére használatos:

- A **Formátum** lapon a formátumelem **Név** attribútuma
- A **Hozzárendelés** lapon a formátumelem **Név** kifejezése

Mivel egyik tulajdonság megadása sem kötelező a **Mező** formátumelemhez, a következő szabályok vonatkoznak a cél PDF-mező meghatározására:

- Ha a **Név** attribútum üres, és a **Név** kifejezés egy üres karakterláncot ad vissza futáskor, akkor egy kivétel jelenik meg a futási időben, hogy tájékoztassa a felhasználót arról, hogy a PDF-mező nem található a PDF-dokumentum kitöltéséhez használt PDF-sablonban.
- Ha a **Név** attribútum meghatározott, és a **Név** kifejezés üres, akkor a program a formátumelem **Név** attribútumának megfelelő névvel rendlekezik.
- Ha a **Név** attribútum meghatározott, és a **Név** kifejezés konfigurált, akkor a program a formátumelem **Név** kifejezése által visszaadott érték nevével megegyező PDF-mezőt tölti ki.

> [!NOTE]
> A PDF-jelölőnégyzetet a kiválasztás szerint az alábbi módokon töltheti ki:
>
> - Amikor a megfelelő **Mező** formátumelem egy **Logikai** adattípusú adatforrásmezőhöz van kötve, amely **Igaz** értékkel rendelkezik
> - Amikor megfelelő **Mező** formátumelemben szerepel egy beágyazott **Karakterlánc** formátum elen, amely össze van kötve egy olyan adatforrásmezővel, amelynek szöveges értéke **1**, **Igaz** vagy **Igen**.

## <a name="run-the-format-configuration"></a>A formátumkonfigurációjának futtatása

### <a name="import-the-format-configuration"></a>A formátumkonfiguráció importálása

Következő lépésként betölti az **Intrastat (importálás Excel-fájlból)** minta ER formátumot. Ez a formátum olyan, felhasználó által kiválasztott Microsoft Excel munkafüzet elemzésére szolgál, amely szimulálja a külföldi kereskedelmi tranzakciókat.

1. A **Konfigurációk** lapon válassza az **Átváltás \> Betöltés XML-fájlból** elemet.
2. Válassza a **Tallózás** elemet. Keresse meg és válassza ki az előfeltételként korábban letöltött **Intrastat (importálás Excel-fájlból).version.1.1.xml** fájlt.
3. Válassza ki az **OK** lehetőséget.
4. A fastruktúrában válassza ki az **Intrastat-modell \> Intrastat (importálás Excelből)** lehetőséget.
5. Válassza ki a **Szerkesztés** opciót.
6. Állítsa az **Alapértelmezett a modell-hozzárendeléshez** beállítást **Igen** értékre.

    > [!NOTE]
    > Ha korábban az **Alapértelmezett a modell-hozzárendeléshez** beállítást **Igen** értékre állította az **Intrastat modell** konfigurációhoz vagy más konfigurációhoz, amely az **Intrastat modell** konfiguráció alá van beágyazva, állítsa ezt a beállítást **Nem** értékre.

    Amikor az **Alapértelmezett a modell-hozzárendeléshez** beállítás **Igen** értékre van állítva, a rendszer az importált **Intrastat (importálás Excel-fájlból)** ER formátumot rendeli hozzá alapértelmezett adatforrásként az **Intrastat-jelentés (PDF)** formátumkonfigurációhoz. Ezután amikor az **Intrastat-jelentés (PDF)** formátumkonfiguráció fut, akkor az **Intrastat (importálás Excel-fájlból)** ER formátum által elemzett Excel.munkafüzet tartalma szimulálja a jelenteni szükséges külkereskedelmi tranzakciókat. A következő ábrán egy Excel-munkafüzet példája látható.

    ![Mintaadatokat tartalmazó Excel-munkafüzet.](media/rcs-ger-filloutpdf-excelworkbook.png)

### <a name="run-the-format-configuration"></a>A formátumkonfigurációjának futtatása

1. A **Konfigurációk** lapon a fastruktúrában válassza az **Intrastat modell \> Intrastat-jelentés (PDF)** lehetőséget.
2. Válassza a **Futtatás** parancsot.
3. Válassza a **Tallózás** elemet. Keresse meg és válassza ki az előfeltételként korábban letöltött **Intrastat mintaadatok.xlsx** fájlt.
4. Válassza ki az **OK** lehetőséget.
5. A **Jelentés iránya** mezőben válassza **Mindkettő** lehetőséget, ha az importált Excel-munkafüzetből szeretné kitölteni az összes tranzakciót a létrejövő PDF-jelentésben.
6. Válassza ki az **OK** lehetőséget.
7. Tekintse át a létrejött PDF-dokumentumot.

A következő ábra egy példát mutat be a létrejövő jelentés első oldaláról.

![A létrejövő jelentés első oldala.](media/rcs-ger-filloutpdf-generatedreport.png)

A következő ábra egy példát mutat be a létrejövő jelentés egy másik oldaláról.

![A létrejövő jelentés egy másik oldala.](media/rcs-ger-filloutpdf-generatedreport2.png)

## <a name="limitations"></a>Korlátozások

A kitölthető mezők nevének egyedinek kell lennie abban a PDF-képernyőn, amelyről jelentést készít. PDF-űrlap importálható ER formátumában minden ilyen mezőben létrejön egy egyedi formátumelem a megfelelő néven. Ha a PDF-űrlap több azonos nevű mezőt tartalmaz, egyetlen formátumelem jön létre az olyan mezőkhöz, amelyek nem teszik lehetővé, hogy futásidőben egyenként ki legyen töltve.

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="when-i-run-the-er-format-to-generate-a-report-in-pdf-format-why-do-i-get-the-following-errors--cannot-handle-iref-streams-the-current-implementation-of-pdfsharp-cannot-handle-this-pdf-feature-introduced-with-acrobat-6-and-a-pdf-name-must-start-with-a-slash-"></a>Amikor PDF-formátumú jelentés létrehozásához futtatom az ER formátumot, akkor mi az oka a következő hibáknak: **Iref-adatfolyamok nem kezelhetők. A PDF Mutatrp jelenlegi implementációja nem tudja kezelni ezt a Pdf-funkciót, amely a Pdf 6 programmal együtt van bevezetve.** A **PDF-névnek perjellel (/) kell kezdődnie.**

Az ER keretrendszer a PDFRp-kódtár 1.5-ös verziója alapján generálja ezeket a PDF-jelentéseket. A PDF 1.5 (Adobe Reader 6.0) egyes szolgáltatásai még nincsenek megvalósítva ebben a tárban. Ezért a PDFAshrp még **nem tud megnyitni néhány OLYAN fájlt, amely PDF 1.5-ös** vagy újabb PDF-fájlként van megjelölve, és a kapott hibákat okozhatja. A probléma megoldásához használja a következő megoldások egyikét:

-   Saját PDF-sablon használata esetén: Adobe A sablon korábbi verzióra való besorolása és új sablon használata az ER formátumban.
-   Olyan ER-formátumsablon használata esetén, amelyet egy másik konfigurációszolgáltató megosztott Önnel egy ER-megoldás részeként: forduljon az ER-megoldás tulajdonosához, és adja meg a probléma leírását.
-   Ha olyan ISV-megoldást használ, amely a PDFRp-függvénytár egy korábbi verzióját tartalmazza, forduljon a megoldás tulajdonosához, és javasoljon egy frissítést az újabb PDF Verzióra.

## <a name="additional-resources"></a>További erőforrások

- [ER – Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése (2016. november)](tasks/er-design-reports-openxml-2016-11.md)
- [ER konfigurációk tervezése jelentések Word-formátumú előállításához](tasks/er-design-configuration-word-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
