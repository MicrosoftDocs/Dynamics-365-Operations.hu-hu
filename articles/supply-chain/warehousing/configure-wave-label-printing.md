---
title: A hullámcímkék nyomtatásának beállítása és használata
description: Ez a témakör bemutatja a hullámcímkék nyomtatását, és elmagyarázza, hogy kell beállítani.
author: GarmMSFT
manager: PJacobse
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSDocumentRouting, WHSWaveTableListPage, WHSPostMethod, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelType, WHSWaveLabelTemplateGroup, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: PJacobse
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: a08f10c1f5c3ff5b9023f37614c4e113b3a6b30d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211766"
---
# <a name="set-up-and-use-wave-label-printing"></a>A hullámcímkék nyomtatásának beállítása és használata

[!include [banner](../includes/banner.md)]

A hullámcímke nyomtatás alternatív megközelítést tesz lehetővé a címkék nyomtatásához egy új hullám lépés módszer bevezetésével, amellyel a címkék közvetlenül a hullámsablonból is létrehozhatók és kinyomtathatók a hullámvégrehajtás során. Így a címkék már akkor elérhetők lesznek, mielőtt a dolgozók a munkarendelést futtatják egy mobileszközön. A dolgozók ezt követően kitároláskor csatolhatják a szükséges címkéket, ahelyett, hogy a kitárolás után tennék.

A hullámcímkék kinyomtatása Zebra programnyelvet (ZPL meghatározó mező) használ a címkék létrehozásához. A címkék elrendezése három szakaszra (fejléc, szövegtörzs és lábléc) van osztva, amelyek lehetővé teszik az ismétlődő struktúrával rendelkező címkék használatát. A hullámcímkesablon mondja meg a rendszernek, melyik címkeelrendezést használja. A felhasználók megadhatják, hogy melyik nyomtató legyen használatban. Szükség szerint egyszerre több nyomtatón is nyomtathatnak címkéket. A **hullámcímkék előzményei** lap a jelen beállítással létrehozott összes címke rekordját jeleníti meg.

A címkék a munkafejlécek alapján is kinyomtathatók és leválogathatók, ezért szünetcímkék a munkfejlécek alapján is nyomtathatók, valamint nyomtathatók a konténerek tartalmát jelző címkék, esetcímkék és más hasonló címkék is.

> [!NOTE]
> Ez a funkció nem helyettesíti a dokumentumátirányításon alapuló meglévő címkenyomtatási funkciókat.

A hullámcímke-nyomtatás a következő fejlesztéseket kínálja:

- A címkék nyomtatása egyetlen munkasoron a kartondobozok számának megfelelően, a tárolóra bontás használata nélkül. (A "kartondoboz" egy egység, amely az egységszekvencia-csoport sorain van megjelölve.)
- Több különböző címkefájl (például kartondoboz és raklapcímke) nyomtatása.
- A címkék felsorolásának szerepeltetése (például 1/124, 2/124, ... 124/124), és megadja a felsorolás tartományát (például a munkasort, a rakománysort vagy a szállítmányt).
- Fuvarlevél-azonosítók létrehozása és nyomtatása a címkékre a fuvarlevél létrehozása előtt.
- Egyedi szállítási tároló sorozatkód (SSCC) létrehozása mindegyik kartondobozhoz, és elhelyezése minden címkén.
- GS1-kompatibilis számsorozatok létrehozása a fuvarlevél-azonosítók és a SSCC-k számára.
- A címkék újranyomtatása mind a mobil eszközökből, mind a funkciógazdag kliensből.
- A címkék érvénytelenítése (például rövid kitárolási helyzetekben), majd újranyomtatása.
- Hullámcímke-előzmények törlése.
- A dokumentumátirányítási elrendezések javításai megoszlanak a dokumentumátirányítási elrendezések és a hullámcímkék elrendezései között. (További tájékoztatás: [Azonosítótáblák dokumentumátirányítási elrendezése](../warehousing/document-routing-layout-for-license-plates.md).)

Ezek a javítások hatékonyabbá teszik a kartondobozok raklaposítás előtti címkézését. Különösen előnyös azoknak a vállalatoknak, amelyek nagy méretű kiskereskedőkhöz szállítanak, akik automatikusan megerősítik a rendelés bevételezését az egyes kartondobozok külön beolvasásával.

> [!NOTE]
> Az ebben a témakörben leírt konfigurációs forgatókönyveket akár külön, akár együttesen is végre lehet hajtani az üzleti igényektől függően. A különböző hullámcímke-sablonokat tervezhet, amelyek sorozatban működnek (3. forgatókönyvben látható módon). Például az 1. forgatókönyvvel kartondobozcímkéket nyomtathat, a 2. forgatókönyvvel raklapcímkéket nyomtathat (ha a raklapok méretben és összetételben változnak).

## <a name="turn-on-the-wave-label-printing-feature"></a>A Hullámcímke-nyomtatás funkció bekapcsolása

A *Hullámcímke-nyomtatás* funkciót használata előtt be kell kapcsolni a rendszerben. A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Hullámcímke-nyomtatás*

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a>1. eset: Hullámcímke-nyomtatás, amelyben egyetlen hullámcímke jön létre

Ez a példa azt mutatja be, hogyan nyomtathat levélcímkéket egy nagyméretű kiskereskedő számára, amely automatikusan visszaigazolja a rendelések bevételezését a kartondobozok külön beolvasásával.

Ez a forgatókönyv a végpontok közötti folyamatot jeleníti meg.

### <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

A jelen forgatókönyv követéséhez a demó adatokat kell telepíteni, és az **USMF** demó jogi személyt kell használnia.

### <a name="make-sure-that-the-wave-label-method-is-available"></a>Ellenőrizze, hogy a hullámcímke módszer elérhető-e

Előfordulhat, hogy újra kell generálnia a hullámfeldolgozási módszereket, hogy a hullámcímke-nyomtatási módszer elérhető legyen.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre.
1. Győződjön meg róla, hogy a **waveLabelPrinting** szerepel a listán. Ha nincs, akkor a műveleti ablaktáblán válassza ki a **Metódusok újragenerálása** lehetőséget a hozzáadáshoz.

### <a name="configure-a-wave-template"></a>Hullámsablon konfigurálása

A hullámsablonokkal összekötheti a hullámmetódusok megadott példányait a hozzá tartozó hullámcímkesablonnal.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.
1. Válasszon sablont, például a **62 Szállítási alapértelmezés** sablont.
1. A **metódusok** gyorslapon helyezze át a **hullámcímke-nyomtatás** módszert a **kiválasztott metódusok** oszlopba.
1. A **kiválasztott metódusok** oszlopban válassza ki a **hullámcímke nyomtatás** módját, és állítsa be a **Hullámlépéskód** mező értékét *PrintLabel* értékre. További tájékoztatás: [Hullámlépéskódok](wave-step-codes.md).

### <a name="create-a-wave-label-layout"></a>Hullámcímke elrendezésének létrehozása

A címke elrendezése határozza meg, hogy milyen adatok jelennek meg a címkén, és milyen módon kell elrendezni. Itt megadhatja a nyomtatónak küldött ZPL kódot.

1. Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímke-elrendezések** pontra.
1. Hozzon létre egy második rekordot, amelynek beállításai a következők:

    - **Címkeelrendezés azonosítója:** *Kartondoboz*
    - **Leírás:** *Kartondoboz (SSCC)*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A műveleti panelen válassza a **hullámcímkék sorbeállításai** elemet.

    Megjelenik a **Hullámcímke sorbeállításai** lap. Itt beállítható a címke dinamikus része.

1. Adjon hozzá egy sort, amelynek beállításai a következők:

    - **Sorazonosító:** *WaveLabel*
    - **Sor táblaneve:** *WHSWaveLabel*
    - **Sor kezdő pozíciója:** *0*

        Ez a mező azt a függőleges pozíciót határozza meg, ahol a sor a címkén kezdődik.

    - **Sormagasság** *0*

        Ez a mező határozza meg az egyes sorok magasságát (pontban) a ZPL szabvány szerint. A sormagasság pozitív a vízszintes címkéknél, és negatív a függőleges címkéknél. Mivel ebben a példában csak egy sor van, az értéket *0* (nulla) értékre lehet megadni.

    - **Sorok száma oldalanként** *1*

        Ez a mező határozza meg, hogy hány sort lehet nyomtatni az egyes címkékre.

        > [!NOTE]
        > Ez a beállítás külön ZPL címkét fog okozni a hullámcímkék táblában szereplő mindegyik rekordhoz.

1. Zárja be a lapot.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.

    - **Táblázat:** *Munkasorok*
    - **Származtatott tábla:** *Munkasorok*
    - **Mező:** *Munkatípus*
    - **Feltételek:** *Kitárolás*

    Ez a lekérdezés gondoskodik arról, hogy csak a kitárolás típusú munkasorok legyenek kinyomtatva a címkére, és ne legyenek betárolás típusú munkasorok.

1. Ha azt szeretné, hogy a fuvarlevél-azonosító kinyomtatása megtörténjen, az **illesztések** lapon válassza ki a **munkasorok** táblát, majd a **szállítmányok** tábláját illessze hozzá.
1. Zárja be a lekérdezéstervező párbeszédpanelt.
1. A **nyomtató szövegének elrendezése** gyorslap három szakaszból áll, ahol megadhatja a nyomtató kódját: **fejléc szakasz** , **szövegtörzs** és **lábléc szakasz**. A **Fejléc szakasz** szakaszban a **Címkefejléc** mezőben adja meg a kívánt fejléc kódját. Ha például Zebra nyomtatókat használ, a következő kódot használhatja.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. A **Szövegtörzs szakasz** szakaszban a **Címke szövegtörzse** mezőben adja meg a kívánt szövegtörzs ZPL kódját. Íme, egy példa.

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. A **Szövegtörzs szakasz** szakaszban a **Címke lábléce** mezőben adja meg a kívánt lábléc ZPL kódját. Íme, egy példa.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Ez a beállítás kinyomtatja az egyes címkék egy példányát. Ha több példányra van szükség (például egy példány a raklap mindkét oldalára), akkor állítsa be a lábléc **\^PQn** szakaszának **n** értékét a példányok szükséges számára. Ha például az egyes címkékből négy másolatot szeretne nyomtatni, adja meg: **\^PQ4**.

A címke készen áll a használatra.

### <a name="create-a-wave-label-type"></a>Hullámcímke típusának létrehozása

A hullámcímkék típusaival a hullámcímkesablonok egy egységhez kapcsolhatók egy egységszekvencia-csoport soraiban.

1. Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímketípusok** pontra.
1. Adjon hozzá egy hullámcímketípust, amelynek beállításai a következők:

    - **Címke típusa:** *kartondoboz*
    - **Leírás:** *Kartondoboz*

### <a name="set-up-unit-sequence-groups"></a>Egységszekvencia-csoportok beállítása

Ezután állítsa be a hullámcímke típusának egységszekvencia-csoportját.

1. Lépjen a **Raktárkezelés \> Beállítás \> Raktár \> Egységszekvencia-csoportok** részre.
1. Válassza az **Ea Box PL** csoportot.
1. A **Doboz** sorban állítsa a **Hullámcímketípus** mezőt *Kartondoboz* értékre.

### <a name="create-a-wave-label-template"></a>Hullámcímkesablon létrehozása

Ezután hozza létre a hullámcímke sablonját a hullámcímkék típusához.

1. Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímkesablonok** pontra.
1. Adjon hozzá egy hullámcímkesablont, és állítsa be a következő értékeket a fejlécben:

    - **Címkesablon neve:** *Kartondobozcímkék*
    - **Leírás:** *Kartondobozcímkék*
    - **Hullámlépés kódja:** *PrintLabel*
    - **Raktár:** *62*

1. Az **általános** gyorslapon adja meg a **hullámcímke típusa** mezőt *kartondoboz* értékre.
1. A **Hullámcímkesablon adatai** gyorslapján vegyen fel egy új sort, amely a következő beállításokkal rendelkezik:

    - **Címkeelrendezés azonosítója:** *Kartondoboz*
    - **Nyomtató neve:** válassza ki a megfelelő ZPL nyomtatót.
    - **Lekérdezés futtatása:** *Igen* (ez a beállítás nem kötelező, de ajánlott az optimális teljesítmény érdekében.)

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Nem kötelező: Ha ügyfélre vonatkozó címkét állít be, akkor egy lekérdezést kell létrehoznia, hogy megkeresse a vevő számláját. A **Hullámcímkesablon adatai** gyorslapján válassza a **lekérdezés szerkesztése** elemet. Ezután a lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.

    - **Tábla:** *Szállítmányok*
    - **Származtatott tábla:** *Szállítmányok*
    - **Mező:** *Számlaszám*
    - **Feltételek:** Adja meg a megfelelő vevői számlaszámot.

    Ha befejezte a munkát, az **OK** gombra kattintva zárja be a lekérdezéstervező párbeszédpanelt.

1. A műveleti ablaktáblán válassza ki a **Lekérdezés szerkesztése** lehetőséget a lekérdezésszerkesztő párbeszédpanel megnyitásához a teljes címkesablonhoz.
1. A lekérdezésszerkesztő párbeszédpanelen, a **Rendezés** lapon adjon hozzá egy sort a következő beállításokkal.

    - **Táblázat:** *Munkasorok*
    - **Származtatott tábla:** *Munkasorok*
    - **Mező:** *Hivatkozási terhelési sor azonosítója (rekord azonosítója)*
    - **Keresés iránya:** *Növekvő*

1. Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.
1. Egy üzenet jelenik meg, amely a csoportosítás-visszaállítási művelet jóváhagyását kéri. A folytatáshoz kattintson az **Igen** gombra.
1. A műveleti ablaktáblán válassza ki a **Hullámcímkesablon-csoport** lehetőséget.
1. A **Hullámcímkesablon-csoport** párbeszédablakban válassza ki azt a sort, amelynek **Hivatkozási mező neve** mezője *Hivatkozási rakománysor-azonosító* értékre van állítva, majd jelölje be a sorhoz tartozó **Címke-összeállítási azonosító** jelölőnégyzetet.

    > [!NOTE]
    > Ez a beállítás egy címkesorozatot hoz létre („X 1. kartondoboz”) rakománysoronként az egész hullámban, a munkacsoportosítási beállítástól függetlenül. Ezt a címksorozatot a címke elrendezésére lehet nyomtatni.

### <a name="configure-number-sequence-extensions"></a>Számsorozat-bővítések konfigurálása

A számsorozat-bővítések meghatározott számsorozatok GS1 megfelelőségét vezérlik. Ez a konfiguráció nem kötelező az aktuális forgatókönyv esetében. További tájékoztatás és konfigurációs utasítások: [a számsorozat-kiterjesztések konfigurálása](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Értékesítési rendelés létrehozása és kiadása a raktárba

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelés \> Összes értékesítési rendelés** pontra.
1. Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-001*
    - **Raktár:** *62*

1. Adjon hozzá két értékesítési sort a következő beállításokkal:

    - 1. értékesítésirendelés-sor:

        - **Cikkszám:** *A0001*
        - **Mennyiség:** *9024*
        - **Egység:** *ea* (9024 ea = 376 Box = 47 PL)

    - 2. értékesítésirendelés-sor:

        - **Cikkszám:** *A0002*
        - **Mennyiség:** *9016*
        - **Egység:** *ea* (9016 ea = 322 Box = 46 PL)

    > [!NOTE]
    > Az itt megadott cikkek és mennyiségek csak példák. A korábban megadott egységszekvencia-csoportot kell használnia, meg kell határozni a egységátváltást *ea* elemről *Box* elemről *PL* elemre, és rendelkezniük kell készlettel a *62.* raktárban. További tájékoztatás: [Mértékegység- és készletezési irányelvek](unit-measure-stocking-policies.md).

1. Jelölje ki az 1. értékesítésirendelés-sort. Ezután az **Értékesítési rendelés sora** szakasz **Készlet** menüjében válassza a **Foglalások** lehetőséget.
1. A **Foglalás** lap műveleti ablaktáblán válassza ki az **Adag foglalása** elemet, mjad zárja be az oldalt.
1. Ismételje meg a 4. és 5. lépést a 2. értékesítésirendelési-sorhoz.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.

    A következő események zajlanak le:

    - A rendszer feldolgozza a létrehozott szállítmányt a címkenyomtatási lépést tartalmazó sablon használatával. A címke elrendezése a címke formátumának meghatározására szolgál, az eredmény pedig a címkesablonban kiválasztott nyomtatón kinyomtatott címke lesz.
    - A hullámcímkék létrehozása és nyomtatása megtörténik. A címkék számának meg kell egyeznie a kartondobozok számával (ebben a példában 376 dobozcímke az 1. sorhoz és 322 dobozcímke a 2. sorhoz).
    - Létrejön egy új fuvarlevél-azonosító a szállítmányok számára. Ha beállította a számsorozat-kiterjesztéseket, akkor a hullámcímke-azonosítók az **SSCC-18** számformátumot követik. 

A következő lapokon megtekintheti és újranyomtathatja a hullámcímkéket. A Művelet ablaktábla **Szállítmányok** lapjának **Kapcsolódó információk** csoportjában válassza a **Hullámcímkék** elemet.

- Minden szállítmány \> Szállítmány adatai
- Minden rakomány \> Rakomány adatai
- Minden hullám
- Hullámcímkék
- Hullámcímke előzményei

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a>2. eset: Hullámcímke-nyomtatás a tárolóra bontáshoz (hullámcímkerekordok nélkül)

Ez a forgatókönyv lehetővé teszi a hullámcímkék kinyomtatását, amikor a tárolóra bontás használatával automatikusan felosztja a cikkeket a kartondobozokba, ezért nem szükséges a hullámcímkerekord. Ebben az esetben a tároló azonosítója helyőrzőként működik a SSCC-hez.

Itt találhatók a jelen forgatókönyv és az 1. eset közötti legfontosabb különbségek:

- **Hullámcímkesablonok:** Nem kell kiválasztani a hullámcímkék típusát a hullámcímkesablonon, és a címke-összeállítás csoportosítására nem lesz szükség. Ellenkező esetben a hullámcímke sablonját kell konfigurálni, és a hullámsablonra mutató hivatkozást ugyanúgy kell konfigurálni, mint az 1. forgatókönyvben leírt módon. Ha meg szeretné akadályozni a hullámcímkék létrehozását, hagyja üresen a hullámcímke típusát.
- **Hullámcímke-elrendezések**: a hullámcímkék elrendezési sorait a hullámcímkerekordok helyett a munkasorokhoz konfigurálja. Konfigurálnia kell a sor beállításait a címkeelrendezéshez a **WHSWorkLine** tábla használatával a **WHSWaveLabel** tábla helyett. A **sorok oldalanként** beállítás határozza meg, hogy hány sor lesz a szövegtörzsben. 

Ez a konfiguráció olyan üzleti esetekhez is használható, amikor több különböző cikket csomagolnak be egy címkézett dobozba vagy egy raklapra, és ezt a csomagolási folyamatot munkalétrehozással (például szállítmány szerint csoportosított munka) lehet definiálni.

Ez a forgatókönyv a végpontok közötti folyamatot jeleníti meg.

### <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

A jelen forgatókönyv követéséhez a demó adatokat kell telepíteni, és az **USMF** demó jogi személyt kell használnia.

### <a name="make-sure-that-the-wave-label-method-is-available"></a>Ellenőrizze, hogy a hullámcímke módszer elérhető-e

Előfordulhat, hogy újra kell generálnia a hullámfeldolgozási módszereket, hogy a hullámcímke-nyomtatási módszer elérhető legyen.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre.
1. Győződjön meg róla, hogy a **waveLabelPrinting** szerepel a listán. Ha nincs, akkor a műveleti ablaktáblán válassza ki a **Metódusok újragenerálása** lehetőséget a hozzáadáshoz.

### <a name="set-up-a-wave-template"></a>Állítsa be a hullámsablon lehetőséget

A hullámsablonokkal összekötheti a hullámmetódusok megadott példányait a hozzá tartozó hullámcímkesablonnal.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.
1. Válasszon sablont, például a **63 Tárolóra bontás** sablont.
1. A **metódusok** gyorslapon helyezze át a **hullámcímke-nyomtatás** módszert a **kiválasztott metódusok** oszlopba.
1. A **kiválasztott metódusok** oszlopban válassza ki a **hullámcímke nyomtatás** módját, és állítsa be a **Hullámlépéskód** mező értékét *PrintLabel* értékre. További tájékoztatás: [Hullámlépéskódok](wave-step-codes.md).

### <a name="create-a-wave-label-layout"></a>Hullámcímke elrendezésének létrehozása

1. Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímke-elrendezések** pontra.
1. Hozzon létre egy második rekordot, amelynek beállításai a következők:

    - **Címkeelrendezés azonosítója:** *Kartondoboz*
    - **Leírás:** *Kartondoboz (SSCC)*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A műveleti panelen válassza a **hullámcímkék sorbeállításai** elemet.

    Megjelenik a **Hullámcímke sorbeállításai** lap. Itt beállítható a címke dinamikus része.

1. Adjon hozzá egy sort, amelynek beállításai a következők:

    - **Sorazonosító:** *WorkLine*
    - **Sor táblaneve:** *WHSWorkLine*
    - **Sor kezdő pozíciója:** *500*

        Ez a mező azt a függőleges pozíciót határozza meg, ahol a sor a címkén kezdődik.

    - **Sormagasság** *-50*

        Ez a mező határozza meg az egyes sorok magasságát. A sormagasság pozitív a vízszintes címkéknél, és negatív a függőleges címkéknél.

    - **Sorok száma oldalanként** *5*

        Ez a mező határozza meg, hogy hány sort lehet nyomtatni az egyes címkékre.

        > [!NOTE]
        > Ez a beállítás számos ZPL címkét fog nyomtatni munkánként, ahol mindegyik lap legfeljebb öt munkasorral rendelkezhet. Ha például egy 12 soros tárolóhoz nyomtat egy címkét, akkor három címkét nyomtat. Ha minden egyes kitárolási sorhoz külön címkét szeretne nyomtatni, akkor ezt az értéket *1*-re kell állítania.

1. Zárja be a lapot.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.

    - **Táblázat:** *Munkasorok*
    - **Származtatott tábla:** *Munkasorok*
    - **Mező:** *Munkatípus*
    - **Feltételek:** *Kitárolás*

1. Ha azt szeretné, hogy a fuvarlevél-azonosító kinyomtatása megtörténjen, az **illesztések** lapon válassza ki a **munkasorok** táblát, majd a **szállítmányok** tábláját illessze hozzá.
1. Zárja be a lekérdezéstervező párbeszédpanelt.
1. A **nyomtató szövegének elrendezése** gyorslap három szakaszból áll, ahol megadhatja a nyomtató kódját: **fejléc szakasz** , **szövegtörzs** és **lábléc szakasz**. A **Fejléc szakasz** szakaszban a **Címkefejléc** mezőben adja meg a kívánt fejléc kódját. Ha például Zebra nyomtatókat használ, a következő kódot használhatja.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. A **Szövegtörzs szakasz** szakaszban a **Címke szövegtörzse** mezőben adja meg a kívánt szövegtörzs ZPL kódját. Íme, egy példa.

    ```plaintext
    <Row name="WorkLine">
    <Heading>
    //Optional heading for section of rows
    </Heading>
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWorkLine.ItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWorkLine.QtyWork$ ^FS
    </Row>
    ```

1. A **Szövegtörzs szakasz** szakaszban a **Címke lábléce** mezőben adja meg a kívánt lábléc ZPL kódját. Íme, egy példa.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Ez a beállítás kinyomtatja az egyes címkék egy példányát. Ha több példányra van szükség (például egy példány a raklap mindkét oldalára), akkor állítsa be a lábléc **\^PQn** szakaszának **n** értékét a példányok szükséges számára. Ha például az egyes címkékből négy másolatot szeretne nyomtatni, adja meg: **\^PQ4**.

A címke készen áll a használatra.

### <a name="create-a-wave-label-template"></a>Hullámcímkesablon létrehozása

1. Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímkesablonok** pontra.
1. Adjon hozzá egy hullámcímkesablont, és állítsa be a következő értékeket a fejlécben:

    - **Címkesablon neve:** *Tárolócímkék*
    - **Leírás:** *Tárolócímkék*
    - **Hullámlépés kódja:** *PrintLabel*
    - **Raktár:** *63*

1. A **Hullámcímkesablon adatai** gyorslapján vegyen fel egy sort, amely a következő beállításokkal rendelkezik:

    - **Címkeelrendezés azonosítója:** *Tároló*
    - **Nyomtató neve:** válassza ki a megfelelő ZPL nyomtatót.
    - **Lekérdezés futtatása:** *Igen* (ez a beállítás nem kötelező, de ajánlott az optimális teljesítmény érdekében.)

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Nem kötelező: Ha ügyfélre vonatkozó címkét állít be, akkor egy lekérdezést kell létrehoznia, hogy megkeresse a vevő számláját. A **Hullámcímkesablon adatai** gyorslapján válassza a **lekérdezés szerkesztése** elemet. Ezután a lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.

    - **Tábla:** *Szállítmányok*
    - **Származtatott tábla:** *Szállítmányok*
    - **Mező:** *Számlaszám*
    - **Feltételek:** Adja meg a megfelelő vevői számlaszámot.

    Ha befejezte a munkát, az **OK** gombra kattintva zárja be a lekérdezéstervező párbeszédpanelt.

### <a name="configure-number-sequence-extensions"></a>Számsorozat-bővítések konfigurálása

A számsorozat-bővítések meghatározott számsorozatok GS1 megfelelőségét vezérlik. Ez a konfiguráció nem kötelező az aktuális forgatókönyv esetében. További tájékoztatás és konfigurációs utasítások: [a számsorozat-kiterjesztések konfigurálása](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Értékesítési rendelés létrehozása és kiadása a raktárba

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelés \> Összes értékesítési rendelés** pontra.
1. Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-001*
    - **Raktár:** *63*

1. Adjon hozzá 5 értékesítésirendelési-sort:

    - 1. értékesítésirendelés-sor:

        - **Cikkszám:** *A0001*
        - **Mennyiség:** *10*

    - 2. értékesítésirendelés-sor:

        - **Cikkszám:** *A0002*
        - **Mennyiség:** *20*

    - 3. értékesítésirendelés-sor:

        - **Cikkszám:** *L0006*
        - **Mennyiség:** *20*

    - 4. értékesítésirendelés-sor:

        - **Cikkszám:** *L0100*
        - **Mennyiség:** *40*

    - 5. értékesítésirendelés-sor:

        - **Cikkszám:** *L0101*
        - **Mennyiség:** *50*

    > [!NOTE]
    > Az itt megadott cikkek és mennyiségek csak példák. A megadott raktárban készlettel kell rendelkezniük.

1. Jelölje ki az 1. értékesítésirendelés-sort. Ezután az **Értékesítési rendelés sora** szakasz **Készlet** menüjében válassza a **Foglalások** lehetőséget.
1. A **Foglalás** lap műveleti ablaktáblán válassza ki az **Adag foglalása** elemet, mjad zárja be az oldalt.
1. Ismételje meg a 4. és 5. lépést minden egyes értékesítésirendelési-sorhoz.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.

    A következő események zajlanak le:

    - A rendszer feldolgozza a létrehozott szállítmányt a címkenyomtatási lépést tartalmazó sablon használatával. A címke elrendezése a címke formátumának meghatározására szolgál, a végeredmény pedig a címkesablonban kiválasztott nyomtatón kinyomtatott címke lesz, amely 5 sorral rendelkezik.
    - Létrejön egy új fuvarlevél-azonosító a szállítmányok számára. Ha beállította a számsorozat-kiterjesztéseket, akkor a hullámcímke-azonosítók az **SSCC-18** számformátumot követik. 

A hullámcímkék újranyomtathatók a **Raktárkezelés \> lekérdezések és a jelentések \> hullámcímkék előzményei** pontban.

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a>3. forgatókönyv: Többszintű címkék hullámcímke-nyomtatása

Ez a példa azt mutatja be, hogyan kell használni a hullámcímkék nyomtatási funkcióit, amikor a raktározási folyamatokban a szállítási címkék több szintje szükséges. Például külön címkéket kell nyomtatni a kartondobozok és raklapok számára, és előfordulhat, hogy egy teljes szállítmányhoz ki kell nyomtatni egy szünetcímkét. A szünetcímkék külön típusú címkék, amelyek a tekercsek és a tárolók közti elválasztóként használhatók, például a szállítmány azonosítója és a vonalkód között, így a címkék nyomtatás után egyszerűen rendezhetők.

A jelen forgatókönyv konfiguráció és az 1. eset konfigurációja közti legfontosabb különbség, a szünetcímkék engedélyezésén kívül, hogy több hullámcímketípust kell társítani a hullámcímkesablonokhoz és az egységszekvencia-csoportsorokhoz. Ennek a konfigurációnak a végrehajtásához a következő elemeket kell beállítania erre az esetre:

- **A hullámfeldolgozási módok:** "ismételhető" módszerként jelöli meg a hullámcímkét, és adja hozzá két (vagy több) alkalommal a hullámsablonhoz, és adjon meg különböző hullámlépéskódokat.
- **Hullámcímkesablonok:** Beállítja a hullámcímkesablonokat, és csatolja őket a hullámsablonhoz. Minden hullámcímke sablonjának saját hullámcímketípusának kell lennie.
- **Hullámcímke-elrendezések:** Több hullámcímke-elrendezést fog létrehozni. A címkék mindegyik "rétegét" külön címkeelrendezéssel kell ellátni, és a program egy szünetcímke elrendezést is tartalmaz.

Ez a forgatókönyv a végpontok közötti folyamatot jeleníti meg.

### <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

A jelen forgatókönyv követéséhez a demó adatokat kell telepíteni, és az **USMF** demó jogi személyt kell használnia.

### <a name="set-up-a-wave-process-method"></a>Hullámfeldolgozási mód beállítása

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre.
1. Győződjön meg róla, hogy a **waveLabelPrinting** szerepel a listán. Ha nincs, akkor a műveleti ablaktáblán válassza ki a **Metódusok újragenerálása** lehetőséget a hozzáadáshoz.
1. A **waveLabelPrinting** módszernél jelölje be a **metódus ismétlődővé tétele** jelölőnégyzetet.

### <a name="set-up-a-wave-template"></a>Állítsa be a hullámsablon lehetőséget

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.
2. Válasszon sablont, például a **62 Szállítási alapértelmezés** sablont.
3. A **metódusok** gyorslapon helyezze át a **hullámcímke-nyomtatás** módszert a **kiválasztott metódusok** oszlopba.
4. A **kiválasztott metódusok** oszlopában állítsa be a **hullámlépés kódja** értékét (például *kartondoboz*) a **Hullámcímke-nyomtatás** módhoz. További tájékoztatás: [Hullámlépéskódok](wave-step-codes.md).
5. Ismét helyezze át a **Hullámcímke-nyomtatás** módszert a **kiválasztott metódusok** oszlopba.
6. A **kiválasztott metódusok** oszlopában állítson be eltérő **hullámlépés kódja** értékét (például *raklap*) a második **Hullámcímke-nyomtatás** módhoz. További tájékoztatás: [Hullámlépéskódok](wave-step-codes.md).

### <a name="create-three-wave-label-layouts"></a>Három hullámcímke-elrendezés létrehozása

1. Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímke-elrendezések** pontra.
1. Hozzon létre egy második rekordot, amelynek beállításai a következők:

    - **Címkeelrendezés azonosítója:** *Kartondoboz*
    - **Leírás:** *Kartondoboz (SSCC)*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A műveleti panelen válassza a **hullámcímkék sorbeállításai** elemet.

    Megjelenik a **Hullámcímke sorbeállításai** lap. Itt beállítható a címke dinamikus része.

1. Adjon hozzá egy sort, amelynek beállításai a következők:

    - **Sorazonosító:** *WaveLabel*
    - **Sor táblaneve:** *WHSWaveLabel*
    - **Sor kezdő pozíciója:** *0*

        Ez a mező azt a függőleges pozíciót határozza meg, ahol a sor a címkén kezdődik.

    - **Sormagasság** *0*

        Ez a mező határozza meg az egyes sorok magasságát (pontban) a ZPL szabvány szerint. A sormagasság pozitív a vízszintes címkéknél, és negatív a függőleges címkéknél. Mivel ebben a példában csak egy sor van, az értéket *0* (nulla) értékre lehet megadni.

    - **Sorok száma oldalanként** *1*

        Ez a mező határozza meg, hogy hány sort lehet nyomtatni az egyes címkékre.

        > [!NOTE]
        > Ez a beállítás külön ZPL címkét fog okozni a hullámcímkék táblában szereplő mindegyik rekordhoz.

1. Zárja be a lapot.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.

    - **Táblázat:** *Munkasorok*
    - **Származtatott tábla:** *Munkasorok*
    - **Mező:** *Munkatípus*
    - **Feltételek:** *Kitárolás*

    Ez a lekérdezés gondoskodik arról, hogy csak a kitárolás típusú munkasorok legyenek kinyomtatva a címkére, és ne legyenek betárolás típusú munkasorok.

1. Ha azt szeretné, hogy a fuvarlevél-azonosító kinyomtatása megtörténjen, az **illesztések** lapon válassza ki a **munkasorok** táblát, majd a **szállítmányok** tábláját illessze hozzá. 
1. Zárja be a lekérdezéstervező párbeszédpanelt.
1. A **nyomtató szövegének elrendezése** gyorslap három szakaszból áll, ahol megadhatja a nyomtató kódját: **fejléc szakasz** , **szövegtörzs** és **lábléc szakasz**. A **Fejléc szakasz** szakaszban a **Címkefejléc** mezőben adja meg a kívánt fejléc kódját. Ha például Zebra nyomtatókat használ, a következő kódot használhatja.


    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. A **Szövegtörzs szakasz** szakaszban a **Címke szövegtörzse** mezőben adja meg a kívánt szövegtörzs ZPL kódját. Íme, egy példa.

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. A **Szövegtörzs szakasz** szakaszban a **Címke lábléce** mezőben adja meg a kívánt lábléc ZPL kódját. Íme, egy példa.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Ez a beállítás kinyomtatja az egyes címkék egy példányát. Ha több példányra van szükség (például egy példány a raklap mindkét oldalára), akkor állítsa be a lábléc **\^PQn** szakaszának **n** értékét a példányok szükséges számára. Ha például az egyes címkékből négy másolatot szeretne nyomtatni, adja meg: **\^PQ4**.

1. Az első címke készen áll a használatra.
1. Hozzon létre egy második elrendezésrekordot, amelynek beállításai a következők:

    - **Címkeelrendezés azonosítója:** *Raklap*
    - **Leírás:** *raklap*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A műveleti panelen válassza a **hullámcímkék sorbeállításai** elemet.

    Megjelenik a **Hullámcímke sorbeállításai** lap. Itt beállítható a címke dinamikus része.

1. Adjon hozzá egy sort, amelynek beállításai a következők:

    - **Sorazonosító:** *WaveLabel*
    - **Sor táblaneve:** *WHSWaveLabel*
    - **Sor kezdő pozíciója:** *0*

        Ez a mező azt a függőleges pozíciót határozza meg, ahol a sor a címkén kezdődik.

    - **Sormagasság** *0*

        Ez a mező határozza meg az egyes sorok magasságát (pontban) a ZPL szabvány szerint. A sormagasság pozitív a vízszintes címkéknél, és negatív a függőleges címkéknél. Mivel ebben a példában csak egy sor van, az értéket *0* (nulla) értékre lehet megadni.

    - **Sorok száma oldalanként** *1*

        Ez a mező határozza meg, hogy hány sort lehet nyomtatni az egyes címkékre.

        > [!NOTE]
        > Ez a beállítás külön ZPL címkét fog okozni a hullámcímkék táblában szereplő mindegyik rekordhoz.

1. Zárja be a lapot.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.

    - **Táblázat:** *Munkasorok*
    - **Származtatott tábla:** *Munkasorok*
    - **Mező:** *Munkatípus*
    - **Feltételek:** *Kitárolás*

    Ez a lekérdezés gondoskodik arról, hogy csak a kitárolás típusú munkasorok legyenek kinyomtatva a címkére, és ne legyenek betárolás típusú munkasorok.

1. Ha azt szeretné, hogy a fuvarlevél-azonosító kinyomtatása megtörténjen, az **illesztések** lapon válassza ki a **munkasorok** táblát, majd a **szállítmányok** tábláját illessze hozzá.
1. Zárja be a lekérdezéstervező párbeszédpanelt.
1. A **nyomtató szövegének elrendezése** gyorslap három szakaszból áll, ahol megadhatja a nyomtató kódját: **fejléc szakasz** , **szövegtörzs** és **lábléc szakasz**. A **Fejléc szakasz** szakaszban a **Címkefejléc** mezőben adja meg a kívánt fejléc kódját. Ha például Zebra nyomtatókat használ, a következő kódot használhatja.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. A **Szövegtörzs szakasz** szakaszban a **Címke szövegtörzse** mezőben adja meg a kívánt szövegtörzs ZPL kódját. Íme, egy példa.

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. A **Szövegtörzs szakasz** szakaszban a **Címke lábléce** mezőben adja meg a kívánt lábléc ZPL kódját. Íme, egy példa.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Ez a beállítás kinyomtatja az egyes címkék egy példányát. Ha több példányra van szükség (például egy példány a raklap mindkét oldalára), akkor állítsa be a lábléc **\^PQn** szakaszának **n** értékét a példányok szükséges számára. Ha például az egyes címkékből négy másolatot szeretne nyomtatni, adja meg: **\^PQ4**.

1. A második címke készen áll a használatra.
1. Hozzon létre egy harmadik elrendezésrekordot, amelynek beállításai a következők:

    - **Címkeelrendezés azonosítója:** *Szünet*
    - **Leírás:** *Szünetcímke*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A **nyomtató szövegének elrendezése** gyorslap három szakaszból áll, ahol megadhatja a nyomtató kódját: **fejléc szakasz** , **szövegtörzs** és **lábléc szakasz**. A **Fejléc szakasz** szakaszban a **Címkefejléc** mezőben adja meg a kívánt fejléc ZPL-kódját. Íme, egy példa.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. Ez alkalommal nem kell megadni szövegtörzset. Ezért csak írja be a szükséges szöveget az **Lábléc szakasz** szakaszba. Íme, egy példa.

    ```plaintext
    ^XZ
    ```

    A harmadik címke készen áll a használatra.

    > [!NOTE]
    > Ez a harmadik címke egy szünetcímke, amely elválasztóként fog szerepelni a címketekercsek között.

### <a name="create-two-wave-label-types"></a>Két hullámcímke típus létrehozása

1. Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímketípusok** pontra.
1. Hozzon létre egy második rekordot, amelynek beállításai a következők:

    - **Címke típusa:** *kartondoboz*
    - **Leírás:** *Kartondoboz*

1. Hozzon létre egy második rekordot, amelynek beállításai a következők:

    - **Címke típusa:** *raklap*
    - **Leírás:** *raklap*

### <a name="set-up-unit-sequence-groups"></a>Egységszekvencia-csoportok beállítása

1. Lépjen a **Raktárkezelés \> Beállítás \> Raktár \> Egységszekvencia-csoportok** részre.
1. Válassza ki vagy hozzon létre egy **Ea Box PL** csoportot.
1. A **Doboz** sorban állítsa a **Hullámcímketípus** mezőt *Kartondoboz* értékre.
1. A **PL** sorban állítsa a **Hullámcímketípus** mezőt *Raklap* értékre.

### <a name="create-wave-label-templates"></a>Hullámcímkesablonok létrehozása

1. Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímkesablonok** pontra.
1. Hozzon létre egy címkesablont, amelynek beállításai a következők:

    - **Címkesablon neve:** *Kartondobozcímkék*
    - **Leírás:** *Kartondobozcímkék*
    - **Hullámlépés kódja:** *Kartondoboz*
    - **Raktár:** *62*

1. Az **Általános** gyorslapon a **Hullámcímketípus** mezőben válasszon egy értéket, pl. az *Kartondoboz* lehetőséget.
1. A **Hullámcímkesablon adatai** gyorslapján vegyen fel egy sort, amely a következő beállításokkal rendelkezik:

    - **Címkeelrendezés azonosítója:** *Kartondoboz*
    - **Nyomtató neve:** válassza ki a megfelelő ZPL nyomtatót.
    - **Lekérdezés futtatása:** *Igen* (ez a beállítás nem kötelező, de ajánlott az optimális teljesítmény érdekében.)

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Nem kötelező: Ha ügyfélre vonatkozó címkét állít be, akkor egy lekérdezést kell létrehoznia, hogy megkeresse a vevő számláját. A **Hullámcímkesablon adatai** gyorslapján válassza a **lekérdezés szerkesztése** elemet. Ezután a lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.

    - **Tábla:** *Szállítmányok*
    - **Származtatott tábla:** *Szállítmányok*
    - **Mező:** *Számlaszám*
    - **Feltételek:** Adja meg a megfelelő vevői számlaszámot.

    Ha befejezte a munkát, az **OK** gombra kattintva zárja be a lekérdezéstervező párbeszédpanelt.

1. A műveleti ablaktáblán válassza ki a **Lekérdezés szerkesztése** lehetőséget a lekérdezésszerkesztő párbeszédpanel megnyitásához a teljes címkesablonhoz.
1. A lekérdezésszerkesztő párbeszédpanelen, a **Rendezés** lapon adjon hozzá egy sort a következő beállításokkal.

    - **Táblázat:** *Munkasorok*
    - **Származtatott tábla:** *Munkasorok*
    - **Mező:** *Hivatkozási terhelési sor azonosítója (rekord azonosítója)*
    - **Keresés iránya:** *Növekvő*

1. Adjon hozzá egy második sort, amelynek beállításai a következők:

    - **Táblázat:** *Munkasorok*
    - **Származtatott tábla:** *Munkasorok*
    - **Mező:** *Szállítmány azonosítója*
    - **Keresés iránya:** *Növekvő*

1. Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.
1. Egy üzenet jelenik meg, amely a csoportosítás-visszaállítási művelet jóváhagyását kéri. A folytatáshoz kattintson az **Igen** gombra.
1. A műveleti ablaktáblán válassza ki a **Hullámcímkesablon-csoport** lehetőséget.
1. A **Hullámcímkesablon-csoport** párbeszédpanel azon sorához, ahol a **hivatkozási mező neve** mező a *szállítmányazonosító* értékre van állítva, adja meg a következő értékeket:

    - **Szünet címkéjének nyomtatása:** jelölje be ezt a jelölőnégyzetet.
    - **Címke elrendezésének azonosítója:** Jelöljön ki egy szünetcímkét. (Például válassza ki az ebben a helyzetben korábban létrehozott *Szünet* címkeelrendezést.)
    - **Nyomtató neve:** Válassza ki a szünet címkéjének nyomtatóját. (A címkék felosztásának céljából általában ugyanaz a nyomtató van kiválasztva, mint a **hullámcímkesablon részletek** gyorslapon. Más forgatókönyvek azonban lehetségesek.)

1. Abban a sorban, ahol a **hivatkozási mező neve** mező a *hivatkozási rakománysor azonosítójára* van állítva , jelölje be a **címke-összeállítás azonosítója** jelölőnégyzetet.

    > [!NOTE]
    > Ez a beállítás egy címkesorozatot hoz létre („X 1. kartondoboz”) rakománysoronként az egész hullámban, a munkacsoportosítási beállítástól függetlenül. Ezt a címksorozatot a címke elrendezésére lehet nyomtatni. Ezenkívül a különböző szállítmányok címkéit a kiválasztott szünetcímke elválasztja.

1. Az **OK** gombra kattintva zárja be a **Hullámcímkesablon csoportja** párbeszédpanelt.
1. Hozzon létre egy második címkesablont, amelynek beállításai a következők:

    - **Címkesablon neve:** *Raklapcímkék*
    - **Leírás:** *raklapcímkék*
    - **Hullámlépés kódja:** *Raklap*
    - **Raktár:** *62*

1. Az **Általános** gyorslapon a **Hullámcímketípus** mezőben válasszon egy értéket, pl. az *Raklap* lehetőséget.
1. A **Hullámcímkesablon adatai** gyorslapján vegyen fel egy sort, amely a következő beállításokkal rendelkezik:

    - **Címkeelrendezés azonosítója:** *Raklap*
    - **Nyomtató neve:** válassza ki a megfelelő ZPL nyomtatót.
    - **Lekérdezés futtatása:** *Igen* (ez a beállítás nem kötelező, de ajánlott az optimális teljesítmény érdekében.)

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Nem kötelező: Ha ügyfélre vonatkozó címkét állít be, akkor egy lekérdezést kell létrehoznia, hogy megkeresse a vevő számláját. A **Hullámcímkesablon adatai** gyorslapján válassza a **lekérdezés szerkesztése** elemet. Ezután a lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.

    - **Tábla:** *Szállítmányok*
    - **Származtatott tábla:** *Szállítmányok*
    - **Mező:** *Számlaszám*
    - **Feltételek:** Adja meg a megfelelő vevői számlaszámot.

    Ha befejezte a munkát, az **OK** gombra kattintva zárja be a lekérdezéstervező párbeszédpanelt. 

1. A műveleti ablaktáblán válassza ki a **Lekérdezés szerkesztése** lehetőséget a lekérdezésszerkesztő párbeszédpanel megnyitásához a teljes címkesablonhoz.
1. A lekérdezésszerkesztő párbeszédpanelen, a **Rendezés** lapon adjon hozzá egy sort a következő beállításokkal.

    - **Táblázat:** *Munkasorok*
    - **Származtatott tábla:** *Munkasorok*
    - **Mező:** *Hivatkozási terhelési sor azonosítója (rekord azonosítója)*
    - **Keresés iránya:** *Növekvő*

1. Adjon hozzá egy második sort, amelynek beállításai a következők:

    - **Táblázat:** *Munkasorok*
    - **Származtatott tábla:** *Munkasorok*
    - **Mező:** *Szállítmány azonosítója*
    - **Keresés iránya:** *Növekvő*

1. Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.
1. Egy üzenet jelenik meg, amely a csoportosítás-visszaállítási művelet jóváhagyását kéri. A folytatáshoz kattintson az **Igen** gombra.
1. A műveleti ablaktáblán válassza ki a **Hullámcímkesablon-csoport** lehetőséget.
1. A **Hullámcímkesablon-csoport** párbeszédpanel azon sorához, ahol a **hivatkozási mező neve** mező a *szállítmányazonosító* értékre van állítva, adja meg a következő értékeket:

    - **Szünet címkéjének nyomtatása:** jelölje be ezt a jelölőnégyzetet.
    - **Címke elrendezésének azonosítója:** Jelöljön ki egy szünetcímkét. (Például válassza ki az ebben a helyzetben korábban létrehozott *Szünet* címkeelrendezést.)
    - **Nyomtató neve:** Válassza ki a szünet címkéjének nyomtatóját. (A címkék felosztásának céljából általában ugyanaz a nyomtató van kiválasztva, mint a **hullámcímkesablon részletek** gyorslapon. Más forgatókönyvek azonban lehetségesek.)

1. Abban a sorban, ahol a **hivatkozási mező neve** mező a *hivatkozási rakománysor azonosítójára* van állítva , jelölje be a **címke-összeállítás azonosítója** jelölőnégyzetet.

    > [!NOTE]
    > Ez a beállítás egy címkesorozatot hoz létre („X 1. kartondoboz”) rakománysoronként az egész hullámban, a munkacsoportosítási beállítástól függetlenül. Ezt a címksorozatot a címke elrendezésére lehet nyomtatni. Ezenkívül a különböző szállítmányok címkéit a kiválasztott szünetcímke elválasztja.

### <a name="configure-number-sequence-extensions"></a>Számsorozat-bővítések konfigurálása

A számsorozat-bővítések meghatározott számsorozatok GS1 megfelelőségét vezérlik. Ez a konfiguráció nem kötelező az aktuális forgatókönyv esetében. További tájékoztatás és konfigurációs utasítások: [a számsorozat-kiterjesztések konfigurálása](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Értékesítési rendelés létrehozása és kiadása a raktárba

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelés \> Összes értékesítési rendelés** pontra.
1. Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-001*
    - **Raktár:** *62*

1. Adjon hozzá 2 értékesítésirendelési-sort:

    - 1. értékesítésirendelés-sor:

        - **Cikkszám:** *A0001*
        - **Mennyiség:** *9024*
        - **Egység:** *ea* (9024 ea = 376 Box = 47 PL)

    - 2. értékesítésirendelés-sor:

        - **Cikkszám:** *A0002*
        - **Mennyiség:** *9016*
        - **Egység:** *ea* (9016 ea = 322 Box = 46 PL)

    > [!NOTE]
    > Az itt megadott cikkek és mennyiségek csak példák. A korábban megadott egységszekvencia-csoportot kell használnia, meg kell határozni a egységátváltást *ea* elemről *Box* elemről *PL* elemre, és rendelkezniük kell készlettel a *62.* raktárban. További tájékoztatás: [Mértékegység- és készletezési irányelvek](unit-measure-stocking-policies.md).

1. Jelölje ki az 1. értékesítésirendelés-sort. Ezután az **Értékesítési rendelés sora** szakasz **Készlet** menüjében válassza a **Foglalások** lehetőséget.
1. A **Foglalás** lap műveleti ablaktáblán válassza ki az **Adag foglalása** elemet, mjad zárja be az oldalt.
1. Ismételje meg a 4. és 5. lépést a 2. értékesítésirendelési-sorhoz.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.

    A következő események zajlanak le: 

    - A rendszer feldolgozza a létrehozott szállítmányt a címkenyomtatási lépést tartalmazó sablon használatával. A címke elrendezése a címke formátumának meghatározására szolgál, az eredmény pedig a címkesablonban kiválasztott nyomtatón kinyomtatott címke lesz.
    - A hullámcímkék létrehozása és nyomtatása megtörténik. A címkék számának meg kell egyeznie a kartondobozok számával (ebben a példában 376 dobozcímke az 1. sorhoz, 322 dobozcímke a 2. sorhoz, 47 raklapcímke a 2. sorhoz és két szünetcímke, amely a szállítmány azonosítójával rendelkezik).
    - Létrejön egy új fuvarlevél-azonosító a szállítmányok számára. Ha beállította a számsorozat-kiterjesztéseket, akkor a hullámcímke-azonosítók az **SSCC-18** számformátumot követik. 

A következő lapokon megtekintheti és újranyomtathatja a hullámcímkéket:

- Minden szállítmány \> Szállítmány adatai
- Minden rakomány \> Rakomány adatai
- Minden hullám
- Hullámcímkék
- Hullámcímke előzményei

A legtöbb ilyen lap esetében a megfelelő függvényt megtalálhatja, ha ki választja a műveleti ablaktábla **Szállítmányok** lapján a **Kapcsolódó információk** csoport **Hullámcímkék** elemét.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]