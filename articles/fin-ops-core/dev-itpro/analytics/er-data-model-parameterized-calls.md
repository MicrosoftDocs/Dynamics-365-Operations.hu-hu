---
title: ER-adatmodellek paraméterezett hívásának támogatása
description: Ez a témakör bemutatja az elektronikus jelentés (ER) adatmodellek paraméterezett hívásait.
author: NickSelin
ms.date: 03/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula, ERDataModelDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-10-01
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 968b0769607e9fdbed57c25b727ed44988a92913
ms.sourcegitcommit: 399d0d3f8e2ebb81b6b9d640365ebe182690bab2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/15/2022
ms.locfileid: "8419513"
---
# <a name="support-parameterized-calls-of-er-data-models"></a>ER-adatmodellek paraméterezett hívásának támogatása

[!include [banner](../includes/banner.md)]

Az üzleti dokumentumok előállításához konfiguráljon egy [elektronikus jelentéskészítő (ER) megoldást](general-electronic-reporting.md), amely a következő ER-összetevőket tartalmazza:

- **[Formátum](er-overview-components.md#format-component)** – ez az összetevő meghatározza az üzleti dokumentumok szerkezetét.
- **Formátumleképezés** – ez az összetevő azt szabályozza, hogyan tölti ki a rendszer futásidőben az üzleti dokumentumokat.
- **[Modellleképezés](er-overview-components.md#model-mapping-component)** – ez az összetevő azt határozza meg, hogy az adatok mit húzzanak át az alkalmazásból egy formátum-hozzárendelésbe.
- **[Adatmodell](er-overview-components.md#data-model-component)** – ez az összetevő információt továbbít az egyes összetevők között.

ER-formátum futtatásakor minden formátumelem fut a gyökérformátum-elemtől kezdve. Ha egy futtatott formátumelem egy adatforrásra vonatkozó kötést tartalmaz, akkor a [rendszer](general-electronic-reporting.md#configuring-data-model-mappings-for-outgoing-documents) az adatforrást a várt adatok kézbesítése érdekében futtatja, és azt használja a formátumelem kitöltéséhez. A modelltípus egyik *adatforrásának* a hívása esetén a program a megfelelő modellleképezést hívja meg, hogy a modellleképezés beállításai alapján kiveszi az adatokat az alkalmazásból.

A modell-hozzárendelési hívások korábban nem paraméterezettek, mert függővé teték őket a futtatott formátum logikája alapján. Csak a következő adatfolyam támogatott.

<table>
<tbody>
<tr align="center">
<td>
<b>Formátum</b><br>
Formátum&nbsp;<br>
&nbsp;
</td>
<td>
<i>Kötés</i><br>
&gt;&nbsp; Kérés&nbsp;&gt;<br>
&lt;&nbsp;érték&nbsp;&lt;
</td>
<td><b>Formázás&nbsp;</b><br>
Adatforrás<br>
&nbsp;
</td>
<td>
<i>Datamodel&nbsp;</i><br>
&gt;&nbsp; Kérés&nbsp;&gt;<br>
&lt;&nbsp;érték&nbsp;&lt;
</td>
<td>
<b>Modell-hozzárendelés&nbsp;</b><br>
Adatforrás&nbsp;<br>
&nbsp;
</td>
<td>
<i>Kötés</i><br>
&gt;&nbsp; Kérés&nbsp;&gt;<br>
&lt;&nbsp;érték&nbsp;&lt;
</td>
<td>
<b>Tábla</b><br>
Rögzítés<br>
Mező
</td>
</tr>
</tbody>
</table>

A 10.0.15-ös és újabb verziókban azonban konfigurálni lehet olyan adatmodell-mezőket, amelyek csak akkor hívhatóak, ha meg vannak állítva a konfigurált paraméterek értéke. Amikor egy ilyen mezőt formátumösszetevőből konfiguráltak és hívtak, a szükséges paramétereket formátumkötésben kell megadni a hívás argumentumaiként. Ilyen esetben az argumentumok értékeit meg lehet adni formátumspecifikus értékek alapján. Ennek megfelelően dinamikus futásidejű **paraméterezés** használható adatmodellhívások esetében a következő adatáramlás támogatása érdekében.

<table>
<tbody>
<tr align="center">
<td>
<b>Formátum</b><br>
Formatelement1&nbsp;&nbsp;<br>
<br>
Formatelement2&nbsp;&nbsp;<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Kötés</i><br>
&gt;&nbsp; 1. kérés&nbsp;&nbsp;&gt;<br>
&lt;&nbsp; érték1&nbsp;&nbsp;&lt;<br>
&gt;&nbsp; 2.&nbsp; kérés&nbsp;&gt;<br>
&lt;&nbsp; érték3&nbsp;&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Formatmapping&nbsp;</b><br>
&nbsp; Adatforrás1&nbsp;<br>
&nbsp;<br>
<b>érték2=Func(érték1)</b><br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Datamodel&nbsp;</i><br>
&gt;&nbsp; mező1&nbsp;&gt;<br>
&lt;&nbsp; érték1&nbsp;&nbsp;&lt;<br>
<b>&gt;&nbsp; field2(érték2)&nbsp;&gt;</b><br>
&lt;&nbsp; érték3&nbsp;&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Modell-hozzárendelés&nbsp;</b><br>
&nbsp; Adatforrás1&nbsp;<br>
<br>
&nbsp; Adatforrás2&nbsp;<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Kötés</i><br>
&gt;&nbsp; 1. kérés&nbsp;&nbsp;&gt;<br>
&lt;&nbsp; érték1&nbsp;&nbsp;&lt;<br>
&gt;&nbsp; 2.&nbsp; kérés&nbsp;&gt;<br>
&lt;&nbsp; érték3&nbsp;&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Table1&nbsp;</b><br>
&nbsp; 1. rekord<br>
1.&nbsp; mező<br>
<b>Table2&nbsp;</b><br>
2.&nbsp; rekord<br>
2.&nbsp; mező
</td>
</tr>
</tbody>
</table>

Az új funkcióval a rekord- vagy rekordlistatípus bármely adatmodellmezőjéhez [*·*](er-formula-supported-data-types-composite.md#record)[*meg lehet hívni a hívást*](er-formula-supported-data-types-composite.md#record-list). Az adatmodell-mezők paraméterei a következő adattípusok esetében támogatottak:

- [Logikai](er-formula-supported-data-types-primitive.md#boolean)
- [Konténer](er-formula-supported-data-types-composite.md#container)
- [Dátum](er-formula-supported-data-types-primitive.md#date)
- [DateTime](er-formula-supported-data-types-primitive.md#datetime)
- [GUID](er-formula-supported-data-types-primitive.md#guid)
- [Int64](er-formula-supported-data-types-primitive.md#int64)
- [Egész](er-formula-supported-data-types-primitive.md#integer)
- [Valós](er-formula-supported-data-types-primitive.md#real)
- [Sztring](er-formula-supported-data-types-primitive.md#string)

Egy olyan adatmodell-mező minden paraméterét be lehet adni, amelyhez az argumentumot meg lehet adni a [*·*](er-formula-supported-data-types-composite.md#record-list) definiált adattípus egyetlen értékeként és az ilyen értékek listájaként.

> [!NOTE]
> Az adatmodell-mező paraméterének alapértelmezett értéke nem támogatott. Ha paramétert ad hozzá egy adatmodell egy mezőjéhez, és az adatmodell verziója már ki van adva és közzé lett adva, [az](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase) összes megfelelő modellleképezést és -formátumot az új verzióra kell lebázisítania, mivel ez az adatmodell-módosítás nem kompatibilis visszafelé.

A paraméteres adatmodell-mezőket konfigurálhatja úgy, hogy a modellfeleltetési hívások formátumspecifikusak legyen. Ezzel a módszersel csökkenthető az egy adatmodell számos formátumára konfigurálható modellleképezések száma. Ezzel a módszersel javíthatja a formátumok végrehajtásának teljesítményét, és csökkentheti az üzleti dokumentumok előállításához szükséges időt. Ha további tájékoztatást szeretne erről a funkcióról, végezze el a példafeladatot ebben a témakörben.

## <a name="example-use-parameterized-calls-of-er-data-models"></a>Példa: paraméterezett ER-adatmodellhívások használata

A következő lépésekkel le lehet állítani, hogy egy rendszergazdai vagy elektronikus jelentéskészítő szerepkörű felhasználó miként tervezhet olyan ER-megoldást, amely adatmodellt, modellleképezést és ER-formátumot tartalmaz, és amely a modellleképezés formátumból történő hívására van beállítva, és amelyben argumentumot adott meg a híváshoz, amelynek értékét futási időben kiszámították a futási formátum képletével. 

Ezeket a lépéseket a **DEMF** vállalatban hajthatja végre. A kód módosítása nem kötelező. 

Ebben a példában hozza létre a szükséges ER-konfigurációkat [a](general-electronic-reporting.md#Configuration) **Litware, Zrt. mintavállalat** számára. Győződjön meg róla **, hogy a Litware, Zrt.** (`http://www.litware.com`) mintavállalat konfigurációs szolgáltatója szerepel az ER keretrendszerben, és hogy Aktívként **van-e megjelölve**. Ha ez a konfigurációs szolgáltató nem szerepel a listán, **vagy** ha nem Aktív jelölésű, kövesse a Konfigurációszolgáltató létrehozása lépést, [és jelölje meg aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="business-scenario"></a>Üzleti eset

Olyan ER-megoldással van probléma, amely a könyvvizsgálati célú elektronikus dokumentumok generálása során futtatható formátumot tartalmaz. Ez a formátum olyan adótranzakciókat tartalmaz, amelyek értékesítési és beszerzési rendelésekhez kapcsolódnak, és amelyekhez a szükséges részletek kapcsolódnak, például a tranzakció dátuma és az adó értéke. Az új pénzügyi év során a bizonylat szerkezete megváltozott. Ezzel egy olyan kiterjesztett dokumentumot kell benyújtania, amely minden olyan fél (vevő és szállító) további részleteit (nevét) tartalmazza, amelynek tranzakciói a létrehozott jelentéseken jelennek meg. Ezért módosítania kell az ER-megoldást, hogy az az új követelménynek megfelelő dokumentumokat generáljon.

### <a name="configure-the-er-framework"></a>ER-keretrendszer konfigurálása

Kövesse az [ER-keretrendszer konfigurálása](er-quick-start2-customize-report.md#ConfigureFramework) rész lépéseit az ER-paraméterek minimális készletének beállításához. Ezt a beállítást be kell fejeznie, mielőtt az ER keretrendszert használva új ER-megoldást tervez.

### <a name="design-a-domain-specific-data-model"></a>Tartományspecifikus adatmodell kialakítása

Létre kell hoznia egy új ER-konfigurációt, amely tartalmazza a szükséges adatmodell-összetevőt. Ezt az adatmodellt fogja a program később adatforrásként használni, amikor a könyvvizsgálati jelentés generálása során er-formátumot tervez.

A következő lépések szerint importálhatja a szükséges adatmodellt a Microsoft által biztosított XML-fájlból.

1. Töltse le [a Mintavizsgálati modell.version.1.xml](https://download.microsoft.com/download/7/1/9/719b0132-fed7-4c73-8afa-90cac29c2fee/Sample-audit-model.version.1.xml) fájlt, és mentse a helyi számítógépre.
2. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
3. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** lehetőséget.
4. Válassza a **Konfigurációk lap** munkaablakában az **XML-fájlból való Adatcsere-betöltés** \> **lehetőséget.**
5. Válassza **a Tallózás** lehetőséget, majd keresse meg és válassza **ki a Mintavizsgálati modell.version.1.xml fájlt**.
6. A konfiguráció importálásához kattintson az **OK** gombra.

    ![Importált ER adatmodell-konfiguráció a Konfigurációk lapon.](./media/er-data-model-parameterized-calls-imported-model.png)

A következő ábra a konfigurált adatmodell szerkeszthető verzióját mutatja be az Adatmodell-tervező **oldalon**.

![Az ER-adatmodell szerkezete az Adatmodell-tervező oldalon.](./media/er-data-model-parameterized-calls-model1.png)

A modell jelenleg úgy van kialakítva, hogy csak a szükséges adatokat tartalmazó adótranzakciókat tegye elérhetővé.

### <a name="design-a-model-mapping-for-the-configured-data-model"></a>Modell-leképezés tervezése a konfigurált adatmodellhez

Az Elektronikus jelentéskészítő fejlesztő szerepkör felhasználójaként létre kell hoznia egy új ER-konfigurációt, amely a mintavizsgálati adatmodell modell-hozzárendelési összetevőjét tartalmazza. Ez az összetevő a Microsoft Dynamics 365 Finance konfigurált adatmodelljét valósítja meg, és az adott alkalmazásra vonatkozik. A modell-hozzárendelési összetevőt úgy kell konfigurálni, hogy megadja azokat az alkalmazásobjektumokat, amelyeket a futásidőben használni kell a konfigurált adatmodell alkalmazásadatokkal való feltöltéséhez. A feladat végrehajtásához meg kell érteni, hogyan valósítja meg az adózási tartomány adatszerkezetét a Pénzügyben.

A következő lépések szerint importálhatja a szükséges modellleképezéseket a Microsoft által biztosított XML-fájlból.

1. Töltse le [a Mintavizsgálati modell mapping.version.1.1.xml](https://download.microsoft.com/download/c/0/3/c03a4673-b1b1-4ef8-96d0-bf96518be6e0/Sample-audit-model-mapping.version.1.1.xml) fájlt, és mentse a helyi számítógépre.
2. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
3. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** lehetőséget.
4. Válassza a **Konfigurációk lap** munkaablakában az **XML-fájlból való Adatcsere-betöltés** \> **lehetőséget.**
5. Válassza **a Tallózás** lehetőséget, majd keresse meg és válassza **ki a Mintavizsgálati modell mapping.version.1.1.xml fájlt**.
6. A konfiguráció importálásához kattintson az **OK** gombra.

    ![Importált ER modellleképezés konfigurációja a Konfigurációk lapon.](./media/er-data-model-parameterized-calls-imported-mapping.png)

A következő ábra a konfigurált modellleképezés szerkeszthető verzióját mutatja be a modellleképezés **tervezőlapján**.

![Az ER modellleképezés szerkezete a modellleképezés tervezőlapján.](./media/er-data-model-parameterized-calls-mapping1.png)

A modellleképezés jelenleg a szükséges adatokat tartalmazó adótranzakciók megjelenítése érdekében van kialakítva. A konfigurált és ER adatforrások `TaxTrans` segítségével beolvasása `TaxTrans``TaxTransFiltered` az alkalmazástáblából.

### <a name="design-a-new-format"></a>Új formátum megtervezése

Elektronikus jelentéskészítési funkció tanácsadója szerepkörű felhasználóként Önnek kell olyan új ER-konfigurációt létrehoznia, amely tartalmaz formátum összetevőt. A formátumösszetevőt úgy kell konfigurálni, hogy a generált jelentéseket az összes szükséges adatot tartalmazó adótranzakciókat tartalmazza.

A következő lépések szerint importálhatja a szükséges formátumot a Microsoft által biztosított XML-fájlból.

1. Töltse le [a Mintavizsgálat formátum.version.1.1.xml](https://download.microsoft.com/download/e/b/7/eb7e126e-2bb3-4bbb-a735-ffd4c48920b1/Sample-audit-format.version.1.1.xml) fájlt, és mentse a helyi számítógépre.
2. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
3. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** lehetőséget.
4. Válassza a **Konfigurációk lap** munkaablakában az **XML-fájlból való Adatcsere-betöltés** \> **lehetőséget.**
5. Válassza **a Tallózás** lehetőséget, majd keresse meg és válassza **ki a Mintavizsgálat formátuma.version.1.1.xml fájlt**.
6. A konfiguráció importálásához kattintson az **OK** gombra.

    ![Importált ER formátumkonfiguráció a Konfigurációk lapon.](./media/er-data-model-parameterized-calls-imported-format.png)

A következő ábra a **Formátumtervező lapon mutatja be a konfigurált formátum szerkeszthető** verzióját.

![Az ER-formátum szerkezete a Formátumtervező lapon.](./media/er-data-model-parameterized-calls-format1.png)

Az ER formátum úgy van beállítva, hogy szöveges fájlként generáljon egy jelentést vesszővel elválasztott értékek (CSV) formátumban.

### <a name="run-the-imported-format"></a>Importált formátum futtatása

1. A Konfigurációk **lapon** válassza **ki** a Mintavizsgálat formátumának konfigurációját, majd a műveletpanelen válassza a **Futtatás lehetőséget**.
2. Az Elektronikus jelentés **paraméterei** párbeszédpanelen a **Beszúrni** kívánt rekordok lapon válassza a Szűrő **lehetőséget**.
3. A PIV **-110000004 és INV-10000001** **adótranzakcióinak kiválasztására vonatkozó feltételek** megadása.
4. Válassza ki az **OK** lehetőséget.
5. Válassza ki az **OK** lehetőséget.
6. A kiválasztott bizonylatok adótranzakcióit tartalmazó létrehozott dokumentum ellenőrzése.

    ![A létrehozott dokumentum előnézete adótranzakciókval.](./media/er-data-model-parameterized-calls-output1.png)

### <a name="adjust-the-imported-er-solution"></a>Az importált ER-megoldás beállítása

Az új követelmény szerint a beküldő dokumentumnak tartalmaznia kell azoknak a vevőknek és szállítóknak a nevét, akiknek a tranzakciói szerepelnek. Ennek megfelelően módosítani kell az importált ER-megoldást, hogy olyan dokumentumot generáljon, amely megfelel ennek az új követelménynek.

Döntse el, hogyan szeretné végrehajtani az importált ER összetevők szükséges módosításait.

A megközelítés megközelítése a következő módosítások végrehajtásához szükséges:

- Az adatmodellben adja hozzá `Transaction.Party.Name` a Karakterlánc típusú új adatmodell-mezőt *·*.
- A modellleképezésben állítsa be az új adatmodell mező kötését úgy, hogy az elérhető táblakapcsolatok segítségével hozzáfér az alkalmazástábla megfelelő rekordjához, `DirPartyTable``Name` és beolvasása a mező értékét onnan.

Bár ez a megközelítés működni fog, teljesítménybeli problémákat okozhat az SQL-adatbázisban, mivel ez a tranzakciós tábla, `TaxTrans` ezért nagy mennyiségű rekordot tartalmazhat. Ebben az esetben a `DirPartyTable``TaxTrans` hívott hívások számának meg kell egynie a táblában található azon rekordok számának, amelyek teljesítménybeli problémákat okozhatnak.

A következő módosításokat is végrehajthatja:

- Az adatmodellben adja hozzá az új gyökért `Party` és az új mezőt`Party.Name`.
- A modellleképezésben vegyen fel egy új adatforrást, `DirPartyTable` amely a táblakapcsolatok minden rekordját illeszti az alkalmazástábla vonatkozó rekordjainak eléréséhez, `TaxTrans` a táblától kezdve.

Bár ez a megközelítés működik, memóriafelhasználási problémákat okozhat. Még ha egy [új JOIN adatforrást is egyetlen SQL-kérésként](er-join-data-sources.md) futtat az alkalmazás-adatbázisba az adatbázis teljesítményével kapcsolatos problémák megakadályozása érdekében, az eredményt be kell bekérni az alkalmazáskiszolgáló memóriájába. Mivel a rekordok száma és az abban a rekordban található mezők száma nagyon nagy lesz, ezért a megközelítés nagyon nehéz memóriafelhasználást okozhat. Előfordulhat, hogy futásidejű memória közbeni kivételt is futtatni kell.

A módosításokat akkor hajthatja végre, amikor egy futó formátum összegyűjti a memóriában a vevők és szállítók egyedi azonosító kódjait a generált jelentésben megjelenő adótranzakciókhoz. Mivel csak egyedi kódokat kell megtartanunk, a végső kódkészlet nem lesz elég nagy ahhoz, hogy befolyásolja a memóriafelhasználást. Ezt követően a kódok egy *másik, a Modell típusú adatforrás hívásának argumentumaként fognak a modell megfeleltetésnek átesni*. A hívás alapján a modellleképezés egy új ER-adatforrást fog futtatni, amely egyetlen SQL-kérést tesz az alkalmazás-adatbázisba, `DirPartyTable` amely a táblából csak azoknak a feleknek a rekordjait tartalmazza, akiknek a kódjai a megadott kódkészletben jelennek meg.

### <a name="adjust-the-imported-data-model"></a>Az importált adatmodell beállítása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A Konfigurációk **lap** bal oldali konfigurációs fájában válassza **a Mintavizsgálati modell lehetőséget**.
3. A Verziók gyorsjelentésben válassza ki **a 2-es** verziót, amely Vázlat **állapotú**.**[...](general-electronic-reporting.md#component-versioning)**
4. Válassza ki a **Konfigurációs összetevők** gyorslapot.
5. Válassza a **Tervező** lehetőséget az adatmodell szerkesztésre való megnyitásához.
6. Az Adatmodell **lapon** győződjön meg arról, `Root` hogy be van jelölve a mező, majd válassza az Új **lehetőséget**.
7. A legördülő párbeszédpanelen hajtsa végre a következő lépéseket:

    1. Az Új **csomópont mezőcsoportban** válassza ki **az aktív csomópont gyermek beállítását**.
    2. A Név **mezőben** adja meg a Fél **nevét**.
    3. A **Cikktípus** mezőben válassza ki a **Rekordlista** lehetőséget.
    4. Az **új mező** hozzáadásának befejezéséhez válassza a Hozzáadás lehetőséget.

8. Győződjön meg róla, hogy `Root.Party` a mező ki van választva, **majd** a Csomópont lapon válassza a Paraméterek **gombra**.
9. A Paraméterek **párbeszédpanelen** hajtsa végre a következő lépéseket:

    1. A Paraméterek **lapon** válassza az Új **lehetőséget**.
    2. A Név **mezőben** adja meg a **PartyRefRecId mezőt**.
    3. A Típus **mezőben** válassza az **Int64 lehetőséget**.
    4. Jelölje be **a Lista** jelölőnégyzetet.
    5. A **paraméterek beírásának befejezéséhez kattintson az OK** gombra.

    > [!NOTE]
    > Az adatmodell mező `Root.Party`**értékét most egy mezőként állította be, amely a PartyRefRecId** paraméter értékének megadásakor hívható meg. Ennek az értéknek jelen kell lennie az `Value`*Int64 adattípus mezőjét tartalmazó* rekordok listáján.

    ![Paraméterek párbeszédpanel.](./media/er-data-model-parameterized-calls-model2a.png)

10. Győződjön meg róla, hogy `Root.Party` a mező ki van választva, majd válassza az Új **lehetőséget**.
11. A legördülő párbeszédpanelen hajtsa végre a következő lépéseket:

    1. Az Új **csomópont mezőcsoportban** válassza ki **az aktív csomópont gyermek beállítását**.
    2. A Név **mezőben** adja meg a **Nevet**.
    3. A **Cikktípus** mezőben válassza ki a **Karakterlánc** lehetőséget.
    4. Az **új mező** hozzáadásának befejezéséhez válassza a Hozzáadás lehetőséget.

12. Válassza a **Mentés** lehetőséget, és zárja be az **Adatmodell lapját**.

    ![A módosított ER-adatmodell szerkezete az Adatmodell-tervező oldalon.](./media/er-data-model-parameterized-calls-model2b.png)

13. A Verziók **gyorsjelentés** **2. verziójához** válassza a Kész **állapot módosítása** \> **lehetőséget**. Majd kattintson az **OK** lehetőségre.

    > [!NOTE]
    > Az adatmodell **változásait** **a rendszer a Mintavizsgálati modell adatmodell-összetevő második verziójában tárolja, amely az ER-konfiguráció mintavizsgálati verziójában** található.

![Módosított ER adatmodell-konfiguráció a Konfigurációk lapon.](./media/er-data-model-parameterized-calls-updated-model.png)

### <a name="adjust-the-imported-model-mapping"></a>Az importált modell megfeleltetésének beállítása

1. A Konfigurációk **lap** bal oldali konfigurációs fájában bontsa **ki a Mintavizsgálati modell ágat**.
2. **Válassza ki a Mintavizsgálati** modell megfeleltetését, **majd** a **Verziók** gyorsjelentésben válassza ki az első (1.2-es) verzión (**1.2-es** verzió) alapuló második megfeleltetési verziót, amely Vázlat állapotú.
3. Válassza az **Új alap** lehetőséget.
4. A Célverzió **mezőben** hagyja meg a **Mintavizsgálati** modell **2**. verzióját.
5. Válassza az **OK** gombra a modellleképezést a legutóbbi adatmodell-módosításoknak megfelelően.

    A szerkeszthető **modell hozzárendelésének verziószáma 1.2-ről** **2.2-re** változott, ezzel jelezve, hogy a második modellverzió jelenleg alapként van használatban.

6. Válassza a **Tervező** lehetőséget.
7. A Modell és **adatforrás megfeleltetése lapon** válassza ki az **aktuális** modellleképezés Tervező beállítását.
8. A következő lépések szerint adhat hozzá új adatforrást az alkalmazástáblához `DirPartyTable` való hozzáféréshez:

    1. Az Adatforrás típusa ablakban válassza ki a **Táblarekordokat** **Dynamics 365 for Operations.\>**
    2. Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.
    3. A Név **mezőben** adja meg a **PartyTable mezőt**.
    4. A Tábla **mezőben** adja meg a **DirPartyTable táblát**.
    5. Az **új adatforrás hozzáadásának befejezéséhez kattintson az OK** gombra.

9. Az alábbi lépések szerint adhat hozzá új adatforrást a `DirPartyTable` rekordok kéréséhez a megadott rekordazonosítólista alapján:

    1. Az Adatforrás **típusa ablakban** válassza az Üres **általános \> tárolót**.
    2. Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.
    3. A Név **mezőbe** írja be az **Adatokat**.
    4. Az **új adatforrás hozzáadásának befejezéséhez kattintson az OK** gombra.
    5. Az Adatforrások **ablakban** válassza ki **az adatforrást**.
    6. Az Adatforrás **típusa ablakban** válassza ki a Számított funkciók **\> mezőt**.
    7. Az Adatforrások **ablakban** válassza a Hozzáadás **lehetőséget**.
    8. A Név **mezőbe** írja be a **DirParty mezőt**.
    9. Válassza a **Képlet szerkesztése** elemet.
    10. A Képlettervező **lapon** válassza a Paraméterek **lehetőséget**.
    11. A Paraméterek **párbeszédpanelen** hajtsa végre a következő lépéseket:

        1. A Paraméterek **lapon** válassza az Új **lehetőséget**.
        2. A Név **mezőbe** írja be a **DirPartyId mezőt**.
        3. A Típus **mezőben** válassza az **Int64 lehetőséget**.
        4. Jelölje be **a Lista** jelölőnégyzetet.
        5. Válassza ki az **OK** lehetőséget.

        > [!NOTE]
        > A számított mezőt úgy állította be, `Value`*hogy futásidőben elfogadja egyetlen paraméter argumentumát, amely rekordlistaként van beállítva, és egyetlen Int64 típusú mezővel rendelkezik*.

    12. A **Képlet** mezőben adja meg a következő kifejezést:

        `FILTER(PartyTable, VALUEINLARGE(PartyTable.RecId, DirPartyId, DirPartyId.Value))`

        > [!NOTE]
        > A számított mezőt úgy állította `DirParty``DirPartyTable``DirPartyId``DirParty` be, hogy csak azokat a rekordokat foglalja le, amelyekben a rekordazonosító kódok szerepelnek az argumentumként megadott listában a mező hívása esetén.

        ![A félneveknek a képlettervező lapon található alkalmazástáblából való beolvasására használt képlet.](./media/er-data-model-parameterized-calls-formula1.png)

    13. Válassza a **Mentés** lehetőséget, majd a **Képlettervező** oldalt.
    14. Válassza **a Mentés** lehetőséget, majd az **új adatforrás hozzáadásának befejezéséhez kattintson az OK** gombra.

10. Az alábbi lépések szerint lehet az új adatforrást az új adatmodell-mezőhöz kötni, hogy az adatmodellben a felek nevei is láthatóak leselkedve láthatóak le:

    1. Az Adatmodell **ablakban** jelölje ki az adatmodell `Root.Party` mezőt.
    2. Az **Adatmodell** panelen válassza a **Szerkesztés** elemet.
    3. Írja be **a** kifejezést a Képletszerkesztő **lap Képlet** mezőjébe `Data.DirParty(PartyRefRecId)`.
    4. Válassza a **Mentés** lehetőséget, majd a **Képlettervező** oldalt.

        > [!NOTE]
        > A kötést úgy állította be, hogy hívja `Data.DirParty``Root.Party` a konfigurált adatforrást, és adja meg a rekordazonosító kódok listáját, amelyek az adatmodell mező hívásakor megadott formátumban lesznek megadva.

    5. Az Adatmodell **ablakban** jelölje ki az adatmodell `Root.Party.Name` mezőt.
    6. Az **Adatmodell** panelen válassza a **Szerkesztés** elemet.
    7. Bontsa ki **a Képlettervező** lap **Adatforrás ablakában** az **Adat \> DirParty** bontását, és válassza **a Név lehetőséget**.
    8. **Adatforrás hozzáadása** lehetőség választása.
    9. Válassza a **Mentés** lehetőséget, majd a **Képlettervező** oldalt.

    ![A módosított ER modellleképezés szerkezete a modellleképezés tervezőlapján.](./media/er-data-model-parameterized-calls-mapping2.png)

11. Válassza a **Mentés** lehetőséget, és zárja be **a Modellleképezés tervezőlapját**.
12. Zárja be a **Modell hozzárendelése adatforráshoz** lapot.
13. A Verziók **gyorsjelentések** **2.2-es** **verziójához válassza a Kész állapot módosítása \> lehetőséget**. Majd kattintson az **OK** lehetőségre.

### <a name="adjust-the-imported-format"></a>Az importált formátum beállítása

1. A Konfigurációk **lapon** válassza ki a Mintavizsgálat **formátumot**.
2. A Verziók **gyorsjelentésben** válassza ki **a Vázlat állapotú 1.2-es** **verziót**.
3. Válassza az **Új alap** lehetőséget.
4. A Célverzió **mezőben** hagyja meg a **Mintavizsgálati** modell **2**. verzióját.
5. Kattintson az **OK** gombra a formátum újrabázishoz és a formátumnak a legutóbbi adatmodell-változásokhoz való igazítása érdekében.
6. Válassza a **Tervező** lehetőséget.
7. Válassza a **Kibontás** /összecsukás lehetőséget a formátumszerkezet bal oldali lapján a Formátumtervező **lapon**.
8. A következő lépések szerint új formátumelemet adhat meg azon felek rekordazonosítási kódjainak összegyűjtéséhez, amelyeknek a tranzakciói jelennek meg a jelentéseken.

    1. A formátumszerkezeti fában válassza ki a **Report.Row.Trans szekvenciaelemet**.
    2. Válassza a **Hozzáadás** lehetőséget.
    3. A Hozzáadás **párbeszédpanelen** válassza az **Adatforrás \> elemet**.
    4. Adja meg az **Azonosítót a Összetevő** tulajdonságai párbeszédpanel Név **mezőjében** **.**
    5. Az Adattípus **mezőben** válassza az **Int64 lehetőséget**.
    6. Válassza ki az **OK** lehetőséget.

    > [!NOTE]
    > Az **adatforráscikkek \>** csak a futó formátum hatókörében használhatók belső számítások és adatátalakítási műveletek elvégzésére. Ennek megfelelően a formátumelem hozzáadásával nem módosítja a létrehozott dokumentum tartalmát.

9. A következő lépések szerint adhat hozzá új formátumelemeket a létrehozott jelentésekben a félnevek hozzáadásához:

    1. Válassza ki **a Report.Row** sequence elemet.
    2. Válassza a **Hozzáadás** lehetőséget.
    3. A Hozzáadás **párbeszédpanelen** válassza a Szövegsorozat **\> lehetőséget**.
    4. Adja meg **a Fél nevét** az Összetevő tulajdonságai párbeszédpanel Név **mezőjében** **.**
    5. Válassza ki az **OK** lehetőséget.
    6. Válassza ki **a Report.Row.Party szekvenciaelemet**.
    7. Válassza a **Hozzáadás** lehetőséget.
    8. A Hozzáadás **párbeszédpanelen** válassza a Szöveg karakterlánc **\> lehetőséget**.
    9. Adja meg **a Nevet az Összetevő** tulajdonságai párbeszédpanel Név **mezőjében** **.**
    10. Válassza ki az **OK** lehetőséget.

10. A következő lépések szerint új adatforrást adhat hozzá azon felek rekordazonosítási kódjainak összegyűjtéséhez, amelyeknek a tranzakciói jelennek meg a generált jelentéseken:

    1. Válassza a **Gyökér** hozzáadása lehetőséget a Megfeleltetés **lapon**.
    2. Az Adatforrás **hozzáadása párbeszédpanelen** válassza a Függvények **adatgyűjteménye \> lehetőséget**.
    3. Az "Adatgyűjtés **" adatforrás** **tulajdonságai** párbeszédpanel Név mezőjébe írja be a **PartyIds adatokat.**
    4. A Cikktípus **mezőben** válassza az **Int64 lehetőséget**.
    5. Válassza ki az **OK** lehetőséget.

11. A következő lépések szerint új kötést adhat meg azon felek rekordazonosítási kódjainak összegyűjtéséhez, amelyeknek a tranzakciói jelennek meg a generált jelentéseken:

    1. A formátumszerkezeti fában válassza ki az **Report.Row.Trans.Id** elemét.
    2. Válassza a **Képlet szerkesztése** elemet.
    3. A Képletszerkesztő **lapon** írja be a kifejezést `PartyIds.Collect(model.Transaction.Party.RecId)`.
    4. Válassza a **Mentés** lehetőséget, majd a **Képlettervező** oldalt.

12. A következő lépések szerint adhat hozzá új kötéseket a létrehozott jelentésekben szereplő félnevekhez:

    1. A formátumszerkezeti fában válassza ki a **Report.Party szekvenciaelemet**.
    2. Válassza a **Képlet szerkesztése** elemet.
    3. A Képletszerkesztő **lapon** írja be a kifejezést `model.Party(PartyIds.Result)`.
    4. Válassza a **Mentés** lehetőséget, majd a **Képlettervező** oldalt.
    5. A formátumszerkezetben válassza ki a **Report**.Party.Name elemét.
    6. A Megfeleltetés **lapon** jelölje ki az adatmodell `model.Party.Name` mezőjét.
    7. Válassza a **Bind** elemet.

    ![A módosított ER-formátum szerkezete a Formátumtervező lapon.](./media/er-data-model-parameterized-calls-format2.png)

13. Válassza a **Mentés** lehetőséget, és zárja be **a Formátumtervező** lapot.
14. Zárja be a **Modell hozzárendelése adatforráshoz** lapot.
15. A Verziók gyorsjelentések **2.2-es** **verziójához válassza a Kész állapot módosítása** **lehetőséget**.\>**·** Majd kattintson az **OK** lehetőségre.

### <a name="run-the-adjusted-format"></a>A módosított formátum futtatása

1. A Konfigurációk **lapon** válassza **ki a Mintavizsgálat formátumát**, majd a műveletpanelen válassza a Futtatás **lehetőséget**.
2. Az Elektronikus jelentés **paraméterei** párbeszédpanelen a **Beszúrni** kívánt rekordok lapon válassza a Szűrő **lehetőséget**.
3. Adja meg a PIV-110000004 **és INV#**-10000001 **adótranzakcióinak** kiválasztására vonatkozó feltételeket.
4. Válassza ki az **OK** lehetőséget.
5. Válassza ki az **OK** lehetőséget.
6. Tekintse át a létrehozott dokumentumot, amely tartalmazza a kiválasztott bizonylatok adótranzakcióit, valamint a megfelelő vevő és szállító nevét.

    ![A létrehozott dokumentum előnézete az adótranzakciók és a felek nevével.](./media/er-data-model-parameterized-calls-output2.png)

7. Menjen a Kötelezettségek **szállítóihoz** \> **·** \> **, és tekintse** **át a kijelölt PIV-110000004** bizonylat adatait, beleértve a szállító nevét is.

    ![A beszerzési bizonylatok részleteinek ellenőrzése az Összes szállító és számlanapló oldalon.](./media/er-data-model-parameterized-calls-review1.gif)

8. Menjen a **Kinnlevőségek** \> **vevőihez** \> **·** – Minden vevő, **és tekintse át a kiválasztott INV-10000001** bizonylat adatait, beleértve a vevő nevét is.

    ![Az értékesítési bizonylatok részleteinek áttekintése az összes vevő és a Feladott áfaoldalakon.](./media/er-data-model-parameterized-calls-review2.gif)

Az ER-megoldás végrehajtásával kapcsolatos további részletekért használja az ER beépített [teljesítmény-nyomkövetési](trace-execution-er-troubleshoot-perf.md) elemzőt.

## <a name="additional-resources"></a>További erőforrások

- [ER adatforrások paraméterezett hívásainak támogatása a Számított mezőtípusban](er-calculated-field-type.md)
- [Az ER-formátumok végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárítása érdekében](trace-execution-er-troubleshoot-perf.md)
- [Adatgyűjtési adatforrások használata elektronikus jelentési formátumokban](er-data-collection-data-sources.md)
- [ValueInLarge ER függvény](er-functions-logical-valueinlarge.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
