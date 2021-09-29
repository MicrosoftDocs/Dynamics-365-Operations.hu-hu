---
title: A konfigurált ER-összetevő ellenőrzése a futásidejű problémák megelőzése érdekében
description: Ez a témakör azt mutatja be, hogyan lehet ellenőrizni a konfigurált Elektronikus jelentéskészítési (ER) összetevőket az esteleges futásidejű problémák megelőzésére.
author: NickSelin
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a855619ebd1c41dc3ca583912f758ed8a8f9ceef
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/15/2021
ms.locfileid: "7488114"
---
# <a name="inspect-the-configured-er-component-to-prevent-runtime-issues"></a>A konfigurált ER-összetevő ellenőrzése a futásidejű problémák megelőzése érdekében

[!include[banner](../includes/banner.md)]

Minden konfigurált [Elektronikus jelentéskészítési (ER)](general-electronic-reporting.md) [formátum](general-electronic-reporting.md#FormatComponentOutbound) és [modell-leképezési](general-electronic-reporting.md#data-model-and-model-mapping-components) összetevő [ellenőrizhető](er-fillable-excel.md#validate-an-er-format) a tervezés során. Ennek az ellenőrzésnek a során a rendszer konzisztencia-ellenőrzést futtat a futásidejű problémák megelőzése érdekében, mint például a végrehajtási hibák és a teljesítmény romlása. Minden megtalált probléma esetében az ellenőrzés elérési utat biztosít a problémás elemhez. Bizonyos problémák esetében automatikus javítás is rendelkezésre áll.

Alapértelmezés szerint a program automatikusan alkalmazza az ellenőrzést a következő esetekben egy ER-konfiguráció esetében, amely tartalmazza a korábban említett ER-komponenseket.

- [Importálja](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally) egy ER-konfiguráció új [verzióját](general-electronic-reporting.md#component-versioning) az Ön Microsoft Dynamics 365 Finance példányába.
- Módosítja az [állapotát](general-electronic-reporting.md#component-versioning) a szerkeszthető ER-konfigurációnak **Vázlat** állapotról **Befejezett** állapotra.
- Egy szerkeszthető konfigurációt egy új alapverzió alkalmazásával [újraalapoz](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase).

Ezt az ellenőrzést szándékosan is futtathatja. Válassza ki a következő három lehetőség egyikét, és kövesse a megadott lépéseket:

- 1. lehetőség:

    1. Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.
    2. A bal oldali konfiguráció fastruktúrájában válassza ki azt a kívánt ER-konfigurációt, amely az ER-formátumot vagy az ER modell-hozzárendelési összetevőt tartalmazza.
    3. A **Verziók** gyorslapon válassza ki a kívánt ER-konfiguráció szükséges verzióját.
    4. A Művelet panelen válassza ki az **Érvényesítés** lehetőséget.

- 2. lehetőség egy ER-formátumhoz:

    1. Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.
    2. A bal oldali konfiguráció fastruktúrájában válassza ki azt a kívánt ER-konfigurációt, amely az ER-formátumösszetevőt tartalmazza.
    3. A **Verziók** gyorslapon válassza ki a kívánt ER-konfiguráció szükséges verzióját.
    4. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
    5. A **Formátumtervező** lapon a Műveleti ablaktáblában válassza ki a **Ellenőrzés** lehetőséget.

- 3. opció: egy ER modell-leképezéshez:

    1. Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.
    2. A bal oldali konfiguráció fastruktúrájában válassza ki azt a kívánt ER-konfigurációt, amely az ER modell-hozzárendelési összetevőt tartalmazza.
    3. A **Verziók** gyorslapon válassza ki a kívánt ER-konfiguráció szükséges verzióját.
    4. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
    5. A **Modell leképezése adatforráshoz** oldalon a Műveleti panelen válassza a **Tervező** lehetőséget.
    6. A **Modell-leképezés tervező** oldalon a Műveleti panelen válassza az **Ellenőrzés** lehetőséget.

Ha a konfiguráció importálásakor szeretné kihagyni az ellenőrzést, hajtsa végre az alábbi lépéseket.

1. Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. A **Konfiguráció érvényesítése a importálás után** lehetőséget állítsa **Nem** értékre.

Ha a verzió állapotának módosításakor vagy újralapozáskor szeretné kihagyni az ellenőrzést, hajtsa végre az alábbi lépéseket.

1. Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. A **Konfiguráció állapotváltozással és új alappal kapcsolatos érvényesítésének kihagyása** beállítást állítsa **Igen** értékre.

Az ER a következő kategóriákat használja a konzisztencia-ellenőrzési vizsgálatok csoportosításához:

- **Végrehajthatóság** – A futásidőben esetlegesen előforduló kritikus problémák felismerését észlelő ellenőrzések. Ezek a problémák többnyire **Hiba** szintűek. 
- **Teljesítmény** – Azon problémák felderítése, amelyek a konfigurált ER-összetevők nem hatékony végrehajtását eredményezhetik. Ezek a problémák többnyire **Figyelmeztetés** szintűek.
- **Adatintegritás** – Az adatvesztést vagy futásidejű problémákat kereső ellenőrzések. Ezek a problémák többnyire **Figyelmeztetés** szintűek.

## <a name="list-of-inspections"></a>Viszgálatok listája

Az alábbi táblázat tartalmazza az ER által kínált vizsgálatokat. Ha további tájékoztatást szeretne erről a vizsgálatokról, használja az első oszlopban található hivatkozásokat, a témakör a megfelelő szakaszainak eléréséhez. Ezek a szakaszok leírják, hogy milyen típusú összetevőkhöz kínál az ER ellenőrzést, illetve hogyan lehet újrakonfigurálni az ER-összetevőket a problémák megelőzéséhez.

<table>
<thead>
<tr>
<th>Név</th>
<th>Kategória</th>
<th>Szint</th>
<th>Üzenet</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href='#i1'>Típuskonverzió</a></td>
<td>Végrehajthatóság</td>
<td>Hiba</td>
<td>
<p>A típus &lt;típus&gt; kifejezés nem konvertálható típus &lt;típus&gt; mezővé.</p>
<p><b>Futásidejű hiba:</b> Kivétel típushoz</p>
</td>
</tr>
<tr>
<td><a href='#i2'>Típus kompatibilitása</a></td>
<td>Végrehajthatóság</td>
<td>Hiba</td>
<td>
<p>A konfigurált kifejezés nem használható az aktuális formátum elemének egy adatforráshoz való kötéséhez, mivel ez a kifejezés olyan adattípus &lt;típust&gt; ad vissza, amely túllépi az aktuális típusú formátum által támogatott &lt;típusok&gt; körét.</p>
<p><b>Futásidejű hiba:</b> Kivétel típusa</p>
</td>
</tr>
<tr>
<td><a href='#i3'>Hiányzó konfigurációs elem</a></td>
<td>Végrehajthatóság</td>
<td>Hiba</td>
<td>
<p>Az elérési út nem található &lt;elérési út&gt;.</p>
<p><b>Futásidejű hiba:</b> E konfigurációs &lt;elérési út&gt; eleme nem található</p>
</td>
</tr>
<tr>
<td><a href='#i4'>Kifejezés végrehajthatósága a SZŰRŐ funkcióval</a></td>
<td>Végrehajthatóság</td>
<td>Hiba</td>
<td>
<p>A FILTER funkció listakifejezése nem lekérdezhető.</p>
<p><b>Futásidejű hiba:</b> A szűrés nem támogatott. A konfiguráció ellenőrzésével további részleteket kaphat erről.</p>
</td>
</tr>
<tr>
<td rowspan='2'><a href='#i5'>Egy GROUPBY adatforrás végrehajthatósága</a></td>
<td>Végrehajthatóság</td>
<td>Hiba</td>
<td>Az &lt;elérési út&gt; elérési út nem támogatja a lekérdezéseket.</td>
</tr>
<tr>
<td>Végrehajthatóság</td>
<td>Hiba</td>
<td>
<p>A csoportosítási funkció nem hajtható végre lekérdezéssel.</p>
<p><b>Futásidejű hiba:</b> A csoportosítási funkció nem hajtható végre lekérdezéssel.</p>
</td>
</tr>
<tr>
<td><a href='#i6'>Egy JOIN adatforrás végrehajthatósága</a></td>
<td>Végrehajthatóság</td>
<td>Hiba</td>
<td>
<p>Nem csatlakozhat olyan lista &lt;elérési úthoz&gt;, amely a lekérdezésben nem szűrő.</p>
<p><b>Futásidejű hiba:</b> A Függvény egyesített adatforrása, amely egy számított mező egy szűrőkifejezése kell legyen helytelenül lett meghívva.</p>
</td>
</tr>
<tr>
<td><a href='#i7'>A SZŰRŐ és a HOL függvény előnyben részesíthetősége</a></td>
<td>Teljesítmény</td>
<td>Figyelmeztetés</td>
<td>A kifejezés SZŰRŐ függvényének használata kívánatosabb a HOL függvénynél a teljesítmény szempontjából. Válassza ki a Javítás lehetőséget az automatikus lecserélés érdekében.</td>
</tr>
<tr>
<td><a href='#i8'>Az ALLITEMSQUERY és ALLITEMS fügvények előnyben részesítése</a></td>
<td>Teljesítmény</td>
<td>Figyelmeztetés</td>
<td>A kifejezés ALLITEMSQUERY függvényének használata kívánatosabb az ALLITEMS függvénynél a teljesítmény szempontjából. Válassza ki a Javítás lehetőséget az automatikus lecserélés érdekében.</td>
</tr>
<tr>
<td><a href='#i9'>Üres listaesetek megfontolása</a></td>
<td>Végrehajthatóság</td>
<td>Figyelmeztetés</td>
<td>
<p>A lista &lt;elérési útja&gt; nem tartalmaz ellenőrzést üres lista esetére, futás közben hibát okozhat. Ellenőrzés megadása az üres lista esetéhez.</p>
<p><b>Futásidejű hiba:</b> A lista üres a(z) &lt;elérési úton&gt;</p>
<p><b><a href='#i9a'>Lehetséges hiba</a>:</b> A sort már egyszer feltöltötték, miközben egy adatforrás, amelyből feltöltötték több rekordot tartalmaz</p>
</td>
</tr>
<tr>
<td><a href='#i10'>Kifejezés végrehajthatósága a SZŰRŐ funkcióval (gyorsítótárazás)</a></td>
<td>Végrehajthatóság</td>
<td>Hiba</td>
<td>
<p>A SZŰRŐ funkció nem alkalmazható az adatforrás kiválasztott típusára. A táblarekord típusú egy adatforrás csak akkor használható, ha a nem gyorsítótárazták, és nincs kézzel hozzáadva beágyazott adatforrások.</p>
<p><b>Futásidejű hiba:</b> A szűrés nem támogatott. A konfiguráció ellenőrzésével további részleteket kaphat erről.</p>
</td>
</tr>
<tr>
<td><a href='#i11'>Hiányzó kötés</a></td>
<td>Végrehajthatóság</td>
<td>Figyelmeztetés</td>
<td>
<p>A (z) &lt;elérési út&gt; elérési útja nincs hozzákötve egyetlen adatforráshoz sem modell-leképezéssel.</p>
<p><b>Futásidejű hiba:</b> Az &lt;elérési út&gt; elérési út nincs kötve</p>
</td>
</tr>
<tr>
<td><a href='#i12'>Nem csatolt sablon</a></td>
<td>Adatintegritás</td>
<td>Figyelmeztetés</td>
<td>A fájl &lt;neve&gt; nincs fájlösszetevőkhöz van csatolva, és a konfigurációs verzió állapotának módosítása után eltávolítja a program.</td>
</tr>
<tr>
<td><a href='#i13'>Nem szinkronizált formátum</a></td>
<td>Adatintegritás</td>
<td>Figyelmeztetés</td>
<td>A megadott név &lt;összetevő neve&gt; nem létezik az &lt;munkalap neve&gt; Excel munkalapon</td>
</tr>
<tr>
<td><a href='#i14'>Nem szinkronizált formátum</a></td>
<td>Adatok sértetlensége</td>
<td>Figyelmeztetés</td>
<td>
<p>A &lt;Megjelölt Word-tartalomvezérlő&gt; címkéje nem létezik a Word-sablonfájlban</p>
<p><b>Futásidejű hiba:</b> A &lt;Megjelölt Word-tartalomvezérlő&gt; címkéje nem létezik a Word-sablonfájlban.</p>
</td>
</tr>
<tr>
<td><a href='#i15'>Nincs alapértelmezett leképezés</a></td>
<td>Adatok sértetlensége</td>
<td>Hiba</td>
<td>
<p>A &lt;modellnév (gyökérleíró)&gt; adatmodellnél egynél több modell-leképezés létezik a konfigurációkban &lt;konfigurációs nevek vesszővel elválasztva&gt;. Állítsa be az egyik konfigurációt alapértelmezettként</p>
<p><b>Futásidejű hiba:</b> A &lt;modellnév (gyökérleíró)&gt; adatmodellnél egynél több modell-leképezés létezik a konfigurációkban &lt;konfigurációs nevek vesszővel elválasztva&gt;. Állítsa be az egyik konfigurációt alapértelmezettként.</p>
</td>
</tr>
<tr>
<td><a href='#i16'>A fejléc- vagy láblécösszetevők következetlen beállítása</a></td>
<td>Adatok sértetlensége</td>
<td>Hiba</td>
<td>
<p>A fejlécek/láblécek (&lt;összetevő típusa: Fejléc vagy Lábléc&gt;) következetlenek.</p>
<p><b>Futásidő:</b> Az utolsó konfigurált összetevő futásidőben használatos, ha végrehajtják a konfigurált ER-formátum vázlatverzióját.</p>
</td>
</tr>
<tr>
<td><a href='#i17'>Az Oldal összetevő inkonzisztens beállítása</a></td>
<td>Adatok sértetlensége</td>
<td>Hiba</td>
<td>Több mint két tartomány-összetevő van replikáció nélkül. Távolítsa el a szükségtelen összetevőket.</td>
</tr>
</tbody>
</table>

## <a name="type-conversion"></a><a id="i1"></a>Típuskonverzió

Az ER ellenőrzi, hogy az adattípusú mező adattípusa kompatibilis-e annak a kifejezésnek az adattípusával, amely konfigurálva van a mező kötéséhez. Ha az adattípusok nem kompatíbilisek, akkor egy ellenőrzési hiba fordul elő az ER modell-leképezés tervezőben. Az az üzenet, amelyet kap tájékoztatja, hogy az ER nem tudja az A típusú kifejezést B típusú mezővé átalakítani.

A következő lépések a problémák előfordulásának módját mutatják be.

1. Kezdje el az ER adatmodellt és az ER modell-leképezés összetevőit egyszerre kell konfigurálni.
2. Az adatmodell-fában adjon hozzá egy **X** nevű mezőt , és válassza az **Egész szám** értéket adattípusként.

    ![X mező és egész szám adattípus az Adatmodell lap adatmód fájához van hozzáadva.](./media/er-components-inspections-01.png)

3. A modell-leképezés tervezőben az **Adatforrások** ablaktáblában adjon hozzá egy **Számított mező** típusú adatforrást.
4. Nevezze el az új **Y** adatforrás-típust , és konfigurálja úgy, hogy a `INTVALUE(100)` kifejezést tartalmazza.
5. **X** kötése **Y**-hoz.
6. Az adatmodell-tervezőben módosítsa az **X** mező adattípusát **Egész szám** értékről **Int64** értékre.
7. Válassza az **Ellenőrzés** lehetőséget , ha ellenőrizni szeretné a szerkeszthető modell-leképezési összetevőt a **Modell-leképezés tervező** oldalon.

    ![A szerkeszthető modell-leképezési összetevő ellenőrzése a Modell-leképezés tervező oldalon.](./media/er-components-inspections-01.gif)

8. Válassza az **Ellenőrzés** lehetőséfet, hogy megvizsgálja a kiválasztott ER konfiguráció modell-leképezési összetevőjét a **Konfigurációk** oldalon.

    ![A modell-leképezési összetevő ellenőrzése a Konfigurációk oldalon.](./media/er-components-inspections-01a.png)

9. A következő ellenőrzési hiba jelentkezik. Az üzenet azt jelzi, hogy az **Egész szám** típusú érték, amelyet az **Y** adatforrás `INTVALUE(100)` kifejezése visszaad nem tárolható az **X** adatmodell **Int64** típusú mezőjében.

A következő ábra bemutatja azt a futásidejű hibát, amely akkor jelentkezik, ha figyelmen kívül hagyja a figyelmeztetést, és a **Futtatás** parancsot választva futtatja a modell-leképezés használatára beállított formátumot.

![Futásidejű hibák a Formátumtervező oldalon.](./media/er-components-inspections-01b.png)

### <a name="automatic-resolution"></a>Automatikus megoldás

A hiba automatikus javítása nem lehetséges.

### <a name="manual-resolution"></a>Manuális megoldás

#### <a name="option-1"></a>1. beállítás

Az adatmodell struktúrájának frissítése az adatmodell mező adattípusának megváltoztatásával, hogy az megfeleljen az adott mezőhöz megadott kifejezés adattípusának. Az előző példában az **X** mező adattípusát **Egész szám** értékre kell módosítani.

#### <a name="option-2"></a>2. beállítás

Módosítsa a modell-leképezést úgy, hogy megváltoztatja az adatmodell mezőhöz kötött adatforrás kifejezését. Az előző példánál az **Y** adatforrás kifejezését `INT64VALUE(100)` értékre kell változtatni.

## <a name="type-compatibility"></a><a id="i2"></a>Típus kompatibilitása

Az ER ellenőrzi, hogy a formátumelem adattípusa kompatibilis-e annak a kifejezésnek az adattípusával, amely konfigurálva van a formátumelem kötéséhez. Ha az adattípusok nem kompatíbilisek, akkor egy ellenőrzési hiba fordul elő az ER művelettervezőben. A kapott üzenet tájékoztatja, hogy a konfigurált kifejezés nem használható az aktuális formátum elemének egy adatforráshoz való kötéséhez, mivel ez a kifejezés olyan adattípus típust ad vissza, amely túllépi az aktuális B típusú formátum által támogatott típusok körét.

A következő lépések a problémák előfordulásának módját mutatják be.

1. Kezdje el az ER adatmodellt és az ER formátum összetevőit egyszerre kell konfigurálni.
2. Az adatmodell-fában adjon hozzá egy **X** nevű mezőt , és válassza az **Egész szám** értéket adattípusként.
3. A szerkezeti fa formátum elemével adja meg a **Numerikus** típus formátumát.
4. Az új formátumelemnek adja az **Y** nevet. A **Numerikus típus** mezőben válassza az **Egész szám** értéket adattípusként.
5. **X** kötése **Y**-hoz.
6. A Format struktúra fában módosítsa az **Y** formátumúelem adattípusát **Egész szám** értékről **Int64** értékre.
7. Válassza az **Ellenőrzés** lehetőséget , ha ellenőrizni szeretné a szerkeszthető formátumösszetevőt a **Formátumtervező** oldalon.

    ![A típus kompatibilitásának ellenőrzése a Formátumtervező oldalon.](./media/er-components-inspections-02.gif)

8. A következő ellenőrzési hiba jelentkezik. Az üzenet azt jelzi, hogy a konfigurált kifejezés csak **Int64** értékeket képes fogadni. Ennek megfelelően az **X** **Egész szám** típusú adatmodell-mező értéke nem adható meg az **Y** formátumelemben.

### <a name="automatic-resolution"></a>Automatikus megoldás

A hiba automatikus javítása nem lehetséges.

### <a name="manual-resolution"></a>Manuális megoldás

#### <a name="option-1"></a>1. beállítás

A formátumstruktúra frissítése a **Numerikus** formátumelem adattípusának megváltoztatásával, hogy az megfeleljen az adott mezőhöz megadott kifejezés adattípusának. Az előző példában az **X** formátumelem **Numerikus típus** értékét **Egész szám** értékre kell módosítani.

#### <a name="option-2"></a>2. beállítás

Módosítsa az **X** formátumelem formátum-hozzárendelését úgy, hogy a kifejezést a `model.X` helyett `INT64VALUE(model.X)` értékre módosítja.

## <a name="missing-configuration-element"></a><a id="i3"></a>Hiányzó konfigurációs elem

Az ER ellenőrzi, hogy a kötési kifejezések csak olyan adatforrásokat tartalmaznak-e, amelyek a szerkeszthető ER összetevőben vannak konfigurálva. Minden olyan kötés esetében, amely olyan adatforrást tartalmaz amely nem szerepel a szerkeszthető ER összetevőben, ellenőrzési hiba fordul elő az ER művelettervezőben vagy az ER modell-leképezés tervezőben.

A következő lépések a problémák előfordulásának módját mutatják be.

1. Kezdje el az ER adatmodellt és az ER modell-leképezés összetevőit egyszerre kell konfigurálni.
2. Az adatmodell-fában adjon hozzá egy **X** nevű mezőt , és válassza az **Egész szám** értéket adattípusként.

    ![Adatmodell-fa X mezővel és Egész szám adattípus az Adatmodell oldalon.](./media/er-components-inspections-01.png)

3. A modell-leképezés tervezőben az **Adatforrások** ablaktáblában adjon hozzá egy **Számított mező** típusú adatforrást.
4. Nevezze el az új **Y** adatforrás-típust , és konfigurálja úgy, hogy a `INTVALUE(100)` kifejezést tartalmazza.
5. **X** kötése **Y**-hoz.
6. A modell-leképezés tervezőben **Adatforrások** ablaktáblában törölje az **Y** adatforrást.
7. Válassza az **Ellenőrzés** lehetőséget , ha ellenőrizni szeretné a szerkeszthető modell-leképezési összetevőt a **Modell-leképezés tervező** oldalon.

    ![A szerkeszthető modell-leképezési összetevő vizsgálata a Modell-leképezés tervező oldalon.](./media/er-components-inspections-03.gif)

8. A következő ellenőrzési hiba jelentkezik. Az üzenet azt jelzi, hogy az **X** adatmodellmező kötése tartalmazza az **Y** adatforrásra hivatkozó útvonalat, de ez az adatforrás nem található.

### <a name="automatic-resolution"></a>Automatikus megoldás

Ha a hiányzó adatforrás-kötés eltávolításával automatikusan ki szeretné javítani ezt a hibát, válassza a **Kötés megszüntetése** lehetőséget.

### <a name="manual-resolution"></a>Manuális megoldás

#### <a name="option-1"></a>1. beállítás

Szüntesse meg az **X** adatmodell mező kötését, hogy ne hivatkozzon a nem létező **Y** adatforrásra.

#### <a name="option-2"></a>2. beállítás

A modell-leképezés tervezőben az **Adatforrások** ablaktáblában adja ismét hozzá az **Y** adatforrást.

## <a name="executability-of-an-expression-with-filter-function"></a><a id="i4"></a>Kifejezés végrehajthatósága a SZŰRŐ funkcióval

A beépített [SZŰRŐ](er-functions-list-filter.md) ER-függvény használatával lehet elérni az alkalmazási táblákat, nézeteket és az adatentitásokat úgy, hogy egyetlen SQL-hívást indít a szükséges adatok lekéréséhez rekordlistaként. A függvény argumetumaként a **Rekordlista** típusú adatforrás van használva, és meghatározza a hívás alkalmazási forrását. Az ER ellenőrzi, hogy a `FILTER` függvényben megadott adatforráshoz közvetlen SQL-lekérdezés létrehozható-e. Ha nem sikerül megvalósítani a közvetlen lekérdezést, akkor ellenőrzési hiba fordul elő az ER modell-leképezés tervezőben. Az üzenet arról tájékoztatja, hogy a függvényt tartalmazó ER kifejezés, amely a `FILTER` függvényt tartalmazza nem futtatható futásidőben.

A következő lépések a problémák előfordulásának módját mutatják be.

1. Kezdje el konfigurálni az ER modell-leképezési összetevőt.
2. Adjon hozzá egy **Dynamics 365 for Operations \\ Táblarekordok** típusú adatforrást.
3. Adja a következő nevet az új adatforrásnak: **Szállító**. A **Tábla** mezőben válassza ki a **VendTable** elemet és adja meg, hogy ez az adatforrás igényelni fogja a VendTable táblát.
4. Adjon hozzá egy **Számított mező** típusú adatforrást.
5. Nevezze el az új **FilteredVendor** adatforrást , és konfigurálja úgy, hogy a `FILTER(Vendor, Vendor.AccountNum="US-101")` kifejezést tartalmazza.
6. Válassza az **Ellenőrzés** lehetőséget , ha ellenőrizni szeretné a **Modell-leképezés tervező** lapjának szerkeszthető modell-leképezési összetevőjét , és ellenőrizze, hogy a **Szállító** adatforrás `FILTER(Vendor, Vendor.AccountNum="US-101")` kifejezését le lehet-e kérdezni.
7. Módosítsa a **Szállító** adatforrást úgy, hogy hozzáad egy **Számított mező** típusú beágyazott mezőt, hogy megkapja a rövidített szállítói számlaszámot.
8. Nevezze el az új beágyazott mezőt **$AccNumber** néven adatforrást , és konfigurálja úgy, hogy a `TRIM(Vendor.AccountNum)` kifejezést tartalmazza.
9. Válassza az **Ellenőrzés** lehetőséget , ha ellenőrizni szeretné a **Modell-leképezés tervező** lapjának szerkeszthető modell-leképezési összetevőjét , és ellenőrizze, hogy a **Szállító** adatforrás `FILTER(Vendor, Vendor.AccountNum="US-101")` kifejezését le lehet-e kérdezni.

    ![A kifejezés ellenőrzése a modell-leképezés tervező lapján kérdezhető le.](./media/er-components-inspections-04.gif)

10. Figyelje meg, hogy érvényesítési hiba lép fel, mert a **Szállító** adatforrás a **Számított mező** típusú beágyazott mezőt tartalmaz, amely nem teszi lehetővé a **FilteredVendor** adatforrás kifejezésének a közvetlen SQL utasításra történő lefordítását.

A következő ábra bemutatja azt a futásidejű hibát, amely akkor jelentkezik, ha figyelmen kívül hagyja a figyelmeztetést, és a **Futtatás** parancsot választva futtatja a modell-leképezés használatára beállított formátumot.

![Futásidejű hibák, amelyek a szerkeszthető formátumnak a Formátumtervező lapon történő futtatásakor fordulnak elő.](./media/er-components-inspections-04a.png)

### <a name="automatic-resolution"></a>Automatikus megoldás

A hiba automatikus javítása nem lehetséges.

### <a name="manual-resolution"></a>Manuális megoldás

#### <a name="option-1"></a>1. beállítás

Ahelyett, hogy a **Számított mező** típusú beágyazott mezőt hozzáadná a **Szállító** adatforráshoz, adja hozzá az **$AccNumber** beágyazott mezőt a **FilteredVendor** adatforráshoz, és konfigurálja úgy, hogy az tartalmazza a `TRIM(FilteredVendor.AccountNum)` kifejezést. Ily módon a `FILTER(Vendor, Vendor.AccountNum="US-101")` kifejezés SQL szinten futtatható, és utána kiszámíthatja a beágyazott **$AccNumber** beágyazott mezőt.

#### <a name="option-2"></a>2. beállítás

Módosítsa a **FilteredVendor** adatforrás kifejezését `FILTER(Vendor, Vendor.AccountNum="US-101")` helyett `WHERE(Vendor, Vendor.AccountNum="US-101")` értékre. Nem javasoljuk, hogy módosítsa a kifejezést egy olyan tábla esetében, amely nagy mennyiségű adatot tartalmaz (tranzakciós tábla), mert az összes rekordot be kell olvasni, és a szükséges rekordok kiválasztása a memóriában történik. Ezért ez a megközelítés gyenge teljesítményt okozhat. A további tudnivalókat lásd: [WHERE ER függvény](er-functions-list-where.md).

## <a name="executability-of-a-groupby-data-source"></a><a id="i5"></a>Egy GROUPBY adatforrás végrehajthatósága

A **GROUPBY** adatforrás rekordcsoportokra osztja a lekérdezés eredményét, általában abból a célból, hogy minden csoporton egy vagy több aggregációt végezzük. Minden **GROUPBY** adatforrás konfigurálható úgy, hogy az adatbázis szintjén vagy a memóriában fusson. Ha a **GROUPBY** adatforrás úgy van konfigurálva, hogy az adatbázis szintjén fusson, az ER ellenőrzi, hogy létrehozható-e közvetlen SQL-lekérdezés az adatforrásban hivatkozott adatforráshoz. Ha nem sikerül megvalósítani a közvetlen lekérdezést, akkor ellenőrzési hiba fordul elő az ER modell-leképezés tervezőben. A kapott üzenet szerint a konfigurált **GROUPBY** adatforrás futásidőben nem futtatható.

A következő lépések a problémák előfordulásának módját mutatják be.

1. Kezdje el konfigurálni az ER modell-leképezési összetevőt.
2. Adjon hozzá egy **Dynamics 365 for Operations \\ Táblarekordok** típusú adatforrást.
3. Nevezze el az új adatforrást **Trans** néven. A **Tábla** mezőben válassza a **VendTrans** lehetőséget annak megadásához, hogy ez az adatforrás kéri majd a VendTrans táblát.
4. Adjon hozzá egy **Csoportosítás alapja** típusú adatforrást.
5. Nevezze el az új adatforrást **GroupedTrans** néven, és konfigurálja a következő módon:

    - Válassza ki a **Trans** adatforrást a csoportosítandó rekordok forrásaként.
    - A **Végrehajtási hely** mezőben válassza a **Lekérdezés** lehetőséget, ha meg szeretné adni, hogy az adatforrást adatbázis szintjén kívánja futtatni.

    ![Az adatforrás konfigurálása a „Csoportosítás alapja” szerkesztése paraméterek lapon.](./media/er-components-inspections-05a.gif)

6. Válassza az **Ellenőrzés** lehetőséget , ha ellenőrizni szeretné a **Modell-leképezés tervező** lapjának szerkeszthető modell-leképezési összetevőjét , és ellenőrizze, hogy a konfigurált **GroupedTrans** adatforrás le lehet-e kérdezni.
7. Módosítsa a **Trans** adatforrást úgy, hogy hozzáad egy **Számított mező** típusú beágyazott mezőt, hogy megkapja a rövidített szállítói számlaszámot.
8. Nevezze el az új adatforrást **$AccNumber** néven, és konfigurálja úgy, hogy a `TRIM(Trans.AccountNum)` kifejezést tartalmazza.

    ![Az adatforrás konfigurálása a modell-leképezés tervező oldalán.](./media/er-components-inspections-05a.png)

9. Válassza az **Ellenőrzés** lehetőséget , ha ellenőrizni szeretné a **Modell-leképezés tervező** lapjának szerkeszthető modell-leképezési összetevőjét , és ellenőrizze, hogy a konfigurált **GroupedTrans** adatforrás le lehet-e kérdezni.

    ![Az ER modell-leképezés összetevő hitelesítése és annak ellenőrzése, hogy a GroupedTrans adatforrás lekérdezhető-e a Modell-leképezés tervező oldalán.](./media/er-components-inspections-05b.png)

10. Figyelje meg, hogy érvényesítési hiba lép fel, mert a **Trans** adatforrás a **Számított mező** típusú beágyazott mezőt tartalmaz, amely nem teszi lehetővé a **GroupedTrans** adatforrás meghívásának a közvetlen SQL utasításra történő lefordítását.

A következő ábra bemutatja azt a futásidejű hibát, amely akkor jelentkezik, ha figyelmen kívül hagyja a figyelmeztetést, és a **Futtatás** parancsot választva futtatja a modell-leképezés használatára beállított formátumot.

![Futásidejű hibák, amelyek akkor fordulnak elő, ha a Formátumtervező oldalán a figyelmeztetést figyelmen kívül hagyják.](./media/er-components-inspections-05c.png)

### <a name="automatic-resolution"></a>Automatikus megoldás

A hiba automatikus javítása nem lehetséges.

### <a name="manual-resolution"></a>Manuális megoldás

#### <a name="option-1"></a>1. beállítás

Ahelyett, hogy a **Számított mező** típusú beágyazott mezőt hozzáadná a **Trans** adatforráshoz, adja hozzá az **$AccNumber** beágyazott mezőt a **GroupedTrans.lines** elemhez a **GroupedTrans** adatforrásban, és konfigurálja úgy, hogy az tartalmazza a `TRIM(GroupedTrans.lines.AccountNum)` kifejezést. Ily módon a **GroupedTrans** adatforrás SQL szinten futtatható, és utána kiszámíthatja a beágyazott **$AccNumber** beágyazott mezőt.

#### <a name="option-2"></a>2. beállítás

Módosítsa a **GroupedTrans** adatforrás **Végrehajtási hely** mezőjének értékét **Lekérdezés** helyett **A memóriában** értékre. Nem javasoljuk, hogy módosítsa az értéket egy olyan tábla esetében, amely nagy mennyiségű adatot tartalmaz (tranzakciós tábla), mert az összes rekordot be kell olvasni, és a csoportosítás és aggregáció a memóriában történik. Ezért ez a megközelítés gyenge teljesítményt okozhat.

## <a name="executability-of-a-join-data-source"></a><a id="i6"></a>Egy JOIN adatforrás végrehajthatósága

A [JOIN](er-join-data-sources.md) adatforrás két vagy több adatbázistábla rekordjait egyesíti a kapcsolódó mezők alapján. Minden **JOIN** adatforrás konfigurálható úgy, hogy az adatbázis szintjén vagy a memóriában fusson. Ha egy **JOIN** adatforrás úgy van konfigurálva, hogy az adatbázis szintjén fusson, az ER ellenőrzi, hogy létrehozható-e közvetlen SQL-lekérdezés az adatforrásban hivatkozott adatforrásokhoz. Ha nem sikerül megvalósítani az SQL-lekérdezést legalább egy hivatkozott adatforrással, akkor ellenőrzési hiba fordul elő az ER modell-leképezés tervezőben. A kapott üzenet szerint a konfigurált **JOIN** adatforrás futásidőben nem futtatható.

A következő lépések a problémák előfordulásának módját mutatják be.

1. Kezdje el konfigurálni az ER modell-leképezési összetevőt.
2. Adjon hozzá egy **Dynamics 365 for Operations \\ Táblarekordok** típusú adatforrást.
3. Adja a következő nevet az új adatforrásnak: **Szállító**. A **Tábla** mezőben válassza ki a **VendTable** elemet és adja meg, hogy ez az adatforrás igényelni fogja a VendTable táblát.
4. Adjon hozzá egy **Dynamics 365 for Operations \\ Táblarekordok** típusú adatforrást.
5. Nevezze el az új adatforrást **Trans** néven. A **Tábla** mezőben válassza a **VendTrans** lehetőséget annak megadásához, hogy ez az adatforrás kéri majd a VendTrans táblát.
6. Adjon hozzá egy **Számított mező** típusú adatforrást a **Szállító** adatforrás beágyazott mezőjeként.
7. Nevezze el az új adatforrást **FilteredTrans** néven, és konfigurálja úgy, hogy a `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)` kifejezést tartalmazza.
8. Adjon hozzá egy **Egyesítés** típusú adatforrást.
9. Nevezze el az új adatforrást **JoinedList** néven, és konfigurálja a következő módon:

    1. Adja hozzá a **Szállító** adatforrást az első egyesítendő rekordként.
    2. Adja hozzá a **Vendor.FilteredTrans** adatforrást a második egyesítendő rekordként. A típusként válassza a **BELSŐ** lehetőséget.
    3. A **Végrehajtás** mezőben válassza a **Lekérdezés** lehetőséget, ha meg szeretné adni, hogy az adatforrást adatbázis szintjén kívánja futtatni.

    ![Az adatforrás konfigurálása az Egyesítéstervező oldalán.](./media/er-components-inspections-06a.gif)

10. Válassza az **Ellenőrzés** lehetőséget , ha ellenőrizni szeretné a **Modell-leképezés tervező** lapjának szerkeszthető modell-leképezési összetevőjét , és ellenőrizze, hogy a konfigurált **JoinedList** adatforrás le lehet-e kérdezni.
11. Módosítsa a **Vendor.FilteredTrans** adatforrás kifejezését `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)` helyett `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)` értékre.
12. Válassza az **Ellenőrzés** lehetőséget , ha ellenőrizni szeretné a **Modell-leképezés tervező** lapjának szerkeszthető modell-leképezési összetevőjét , és ellenőrizze, hogy a konfigurált **JoinedList** adatforrás le lehet-e kérdezni.

    ![A szerkeszthető modell-leképezési összetevő validálása és annak ellenőrzése, hogy a JoinedList adatforrás lekérdezhető-e a Modell-leképezés tervező oldaláról.](./media/er-components-inspections-06b.png)

13. Figyelje meg, hogy érvényesítési hiba lép fel, mert a **Vendor.FilteredTrans** adatforrás kifejezése nem fordítható le a közvetlen SQL-hívásra. Emellett a közvetlen SQL-hívás nem teszi lehetővé a **JoinedList** adatforrás közvetlen SQL utasításra való fordítását.

    ![Futásidejű hibák a JoinedList adatforrás sikertelen érvényesítése okán a Modell-leképezés tervező oldalon.](./media/er-components-inspections-06c.png)

A következő ábra bemutatja azt a futásidejű hibát, amely akkor jelentkezik, ha figyelmen kívül hagyja a figyelmeztetést, és a **Futtatás** parancsot választva futtatja a modell-leképezés használatára beállított formátumot.

![A szerkeszthető formátum futtatása a Formátumtervező lapon.](./media/er-components-inspections-06e.png)

### <a name="automatic-resolution"></a>Automatikus megoldás

A hiba automatikus javítása nem lehetséges.

### <a name="manual-resolution"></a>Manuális megoldás

#### <a name="option-1"></a>1. beállítás

Módosítsa vissza a **Vendor.FilteredTrans** adatforrás kifejezését `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)` helyett `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)` értékre, ahogy azt a figyelmeztetés tanácsolta.

![Az adatforrás frissített kifejezése a modell-leképezés tervező oldalán.](./media/er-components-inspections-06d.png)

#### <a name="option-2"></a>2. beállítás

Módosítsa a **JoinedList** adatforrás **Végrehajtás** mezőjének értékét **Lekérdezés** helyett **A memóriában** értékre. Nem javasoljuk, hogy módosítsa az értéket egy olyan tábla esetében, amely nagy mennyiségű adatot tartalmaz (tranzakciós tábla), mert az összes rekordot be kell olvasni, és az egyesítés a memóriában történik. Ezért ez a megközelítés gyenge teljesítményt okozhat. Egy érvényesítési figyelmeztetés jelenik meg, amely tájékoztatja Önt erről a kockázatról.

## <a name="preferability-of-filter-vs-where-function"></a><a id="i7"></a>A SZŰRŐ és a HOL függvény előnyben részesíthetősége

A beépített [SZŰRŐ](er-functions-list-filter.md) ER-függvény használatával lehet elérni az alkalmazási táblákat, nézeteket és az adatentitásokat úgy, hogy egyetlen SQL-hívást indít a szükséges adatok lekéréséhez rekordlistaként. A [WHERE](er-functions-list-where.md) függvény az adott forrásból származó összes rekordot lekéri, és rögzíti a memóriában történő kiválasztást. Mindkét függvény argumetumaként a **Rekordlista** típusú adatforrás van használva, és meghatározza a rekordok lekérésének forrását. Az ER ellenőrzi, hogy a **WHERE** függvényben megadott adatforráshoz közvetlen SQL-lekérdezés létrehozható-e. Ha sikerül megvalósítani a közvetlen hívást, akkor ellenőrzési figyelmeztetés fordul elő az ER modell-leképezés tervezőben. A kapott üzenet azt javasolja, hogy a hatásfok növelése érdekében a **WHERE** függvény helyett a **FILTER** függvényt használja.

A következő lépések a problémák előfordulásának módját mutatják be.

1. Kezdje el konfigurálni az ER modell-leképezési összetevőt.
2. Adjon hozzá egy **Dynamics 365 for Operations \\ Táblarekordok** típusú adatforrást.
3. Nevezze el az új adatforrást **Trans** néven. A **Tábla** mezőben válassza a **VendTrans** lehetőséget annak megadásához, hogy ez az adatforrás kéri majd a VendTrans táblát.
4. Adjon hozzá egy **Számított mező** típusú adatforrást a **Szállító** adatforrás beágyazott mezőjeként.
5. Nevezze el az új adatforrást **FilteredTrans** néven, és konfigurálja úgy, hogy a `WHERE(Trans, Trans.AccountNum="US-101")` kifejezést tartalmazza.
6. Adjon hozzá egy **Dynamics 365 for Operations \\ Táblarekordok** típusú adatforrást.
7. Adja a következő nevet az új adatforrásnak: **Szállító**. A **Tábla** mezőben válassza ki a **VendTable** elemet és adja meg, hogy ez az adatforrás igényelni fogja a VendTable táblát.
8. Adjon hozzá egy **Számított mező** típusú adatforrást.
9. Nevezze el az új **FilteredVendor** adatforrást , és konfigurálja úgy, hogy a `WHERE(Vendor, Vendor.AccountNum="US-101")` kifejezést tartalmazza.
10. Válassza az **Ellenőrzés** lehetőséget , ha ellenőrizni szeretné a szerkeszthető modell-leképezési összetevőt a **Modell-leképezés tervező** oldalon.

    ![A szerkeszthető modell-leképezési összetevőt a Modell-leképezés tervező oldalon vizsgálja meg.](./media/er-components-inspections-07a.png)

11. Figyelje meg, hogy az érvényesítési figyelmeztetések azt javasolják, hogy a **SZŰRŐ** függvényt használja a **HOL** függvény helyett a **FilteredVendor** és a **FilteredTrans** adatforrásokhoz.

    ![Javaslat a FILTER függvény használatára a WHERE függvény helyett a Modell-leképezés tervező oldalán.](./media/er-components-inspections-07b.png)

### <a name="automatic-resolution"></a>Automatikus megoldás

Válassza a **Javítás** lehetőséget, ha automatikusan le szeretné cserélni a **HOL** függvényt a **SZŰRŐ** függvénnyel az összes olyan adatforráshoz tartozó kifejezésben, amelyek megjelennek a **Figyelmeztetések** lap rácsán ehhez a vizsgálattípushoz.

Másik lehetőségként kijelölheti a sort egyetlen figyelmeztetéshez a rácsban, majd válassza a **Kijelölt javítása** lehetőséget. Ebben az esetben a kifejezés csak a kijelölt figyelmeztetésben említett adatforrásban módosul automatikusan.

![A Javítás lehetőség kiválasztása, hogy a WHERE függvényt automatikusan a FILTER függvényre cserélje a Modell-leképezés tervező oldalán.](./media/er-components-inspections-07c.png)

### <a name="manual-resolution"></a>Manuális megoldás

Az érvényesítési rácsban említett összes adatforrás kifejezéseit manuálisan is módosíthatja, ha a **HOL** függvényt a **SZŰRÉS** függvénnyel helyettesíti.

## <a name="preferability-of-allitemsquery-vs-allitems-function"></a><a id="i8"></a>Az ALLITEMSQUERY és ALLITEMS fügvények előnyben részesítése

A beépített [ALLITEMS](er-functions-list-allitems.md) és [ALLITEMSQUERY](er-functions-list-allitemsquery.md) ER-függvények egy összeolvasztott **Rekordlista**-értéket adnak vissza, amely a megadott elérési úttal megegyező összes elemet reprezentáló rekordok listájából áll. Az ER ellenőrzi, hogy az **ALLITEMS** függvényben megadott adatforráshoz közvetlen SQL-lekérdezés létrehozható-e. Ha sikerül megvalósítani a közvetlen hívást, akkor ellenőrzési figyelmeztetés fordul elő az ER modell-leképezés tervezőben. A kapott üzenet azt javasolja, hogy a hatásfok növelése érdekében a **ALLITEMS** függvény helyett a **ALLITEMSQUERY** függvényt használja.

A következő lépések a problémák előfordulásának módját mutatják be.

1. Kezdje el konfigurálni az ER modell-leképezési összetevőt.
2. Adjon hozzá egy **Dynamics 365 for Operations \\ Táblarekordok** típusú adatforrást.
3. Adja a következő nevet az új adatforrásnak: **Szállító**. A **Tábla** mezőben válassza ki a **VendTable** elemet és adja meg, hogy ez az adatforrás igényelni fogja a VendTable táblát.
4. **Számított mező** típusú adatforrás hozzáadása több szállító rekordjainak lekéréséhez.
5. Nevezze el az új **FilteredVendor** adatforrást , és konfigurálja úgy, hogy a `FILTER(Vendor, OR(Vendor.AccountNum="US-101",Vendor.AccountNum="US-102"))` kifejezést tartalmazza.
6. A **Számított mező** típusú adatforrás hozzáadása az összes leszűrt szállító tranzakcióinak lekéréséhez.
7. Nevezze el az új adatforrást **FilteredVendorTrans** néven , és konfigurálja úgy, hogy a `ALLITEMS(FilteredVendor.'<Relations'.'VendTrans.VendTable_AccountNum')` kifejezést tartalmazza.
8. Válassza az **Ellenőrzés** lehetőséget , ha ellenőrizni szeretné a szerkeszthető modell-leképezési összetevőt a **Modell-leképezés tervező** oldalon.

    ![A szerkeszthető modell-leképezési összetevő vizsgálata a Modell-leképezés tervező oldalon.](./media/er-components-inspections-08a.png)

9. A következő ellenőrzési figyelmeztetés jelentkezik. Az üzenet azt javasolja, hogy a **FilteredVendorTrans** adatforráshoz az **ALLITEMS** függvény helyett az **ALLITEMSQUERY** függvényt használja.

    ![Javaslat az ALLITEMSQUERY függvény használatára az ALLITEMS függvény helyett a Modell-leképezés tervező oldalán.](./media/er-components-inspections-08b.png)

### <a name="automatic-resolution"></a>Automatikus megoldás

Válassza a **Javítás** lehetőséget, ha automatikusan le szeretné cserélni a **ALLITEMS** függvényt a **ALLITEMSQUERY** függvénnyel az összes olyan adatforráshoz tartozó kifejezésben, amelyek megjelennek a **Figyelmeztetések** lap rácsán ehhez a vizsgálattípushoz.

Másik lehetőségként kijelölheti a sort egyetlen figyelmeztetéshez a rácsban, majd válassza a **Kijelölt javítása** lehetőséget. Ebben az esetben a kifejezés csak a kijelölt figyelmeztetésben említett adatforrásban módosul automatikusan.

![A Kijelöltek javítása lehetőség kiválasztása a Modell-leképezés tervező oldalon.](./media/er-components-inspections-08c.png)

### <a name="manual-resolution"></a>Manuális megoldás

Az érvényesítési rácsban említett összes adatforrás kifejezéseit manuálisan is módosíthatja, ha a **ALLITEMS** függvényt a **ALLITEMSQUERY** függvénnyel helyettesíti.

## <a name="consideration-of-empty-list-cases"></a><a id="i9"></a>Üres listaesetek megfontolása

Az ER formátum vagy a modellleképezési összetevő konfigurálásával lekérheti **Rekordlista** típusú adatforrás mezőértékét. Az ER ellenőrzi, hogy a terv figyelembe veszi-e azt az esetet, amikor egy meghívott adatforrás nem tartalmaz rekordokat (azaz üres), hogy megakadályozza a futásidejű hibákat, amikor egy értéket nem létező rekord mezőjéből lehívnak.

A következő lépések a problémák előfordulásának módját mutatják be.

1. Kezdje el az ER adatmodellt, az ER modell-leképezés és az ER formátum összetevőit egyszerre kell konfigurálni.
2. Az adatmodellfán adjon hozzá egy **Root3** nevű gyökérelemet.
3. Módosítsa a **Root3** elemet egy **Rekordlista** típusú beágyazott elem hozzáadásával.
4. Nevezze el az új beágyazott cikket **Szállító** néven.
5. Módosítsa a **Szállító** elemet az alábbi módon:

    - Adjon hozzá egy **Karakterlánc** típusú beágyazott mezőt, és nevezze el **Név** néven.
    - Adjon hozzá egy **Karakterlánc** típusú beágyazott mezőt, és nevezze el **AccountNumber** néven.

    ![Beágyazott mezők hozzáadása az Adatmodell lapon.](./media/er-components-inspections-09a.png)

6. A modell-leképezés tervezőben az **Adatforrások** ablaktáblában adjon hozzá egy **Dynamics 365 for Operations \\ Táblarekordok** típusú adatforrást.
7. Adja a következő nevet az új adatforrásnak: **Szállító**. A **Tábla** mezőben válassza ki a **VendTable** elemet és adja meg, hogy ez az adatforrás igényelni fogja a VendTable táblát.
8. Adjon hozzá egy **Általános \\ Felhasználó beviteli paraméter** típusú adatforrást, ha a futásidejű párbeszédpanelen szállítói számlát szeretne keresni.
9. Adja a következő nevet az új adatforrásnak: **RequestedAccountNum**. A **Címke** mezőben adja meg a **Szállítói számlaszám** értéket. A **Műveletek adattípus neve** mezőben hagyja meg az alapértelmezett értéket: **Leírás**.
10. **Számított mező** típusú adatforrás hozzáadása egy olyan szállító leszűréséhez, amely iránt érdeklődnek.
11. Nevezze el az új **FilteredVendor** adatforrást , és konfigurálja úgy, hogy a `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)` kifejezést tartalmazza.
12. Az adatmodell elemeit a következő módon kötheti a konfigurált adatforrásokhoz:

    - A **FilteredVendor** kötése a **Szállító** elemhez.
    - A **FilteredVendor.AccountNum** kötése a **Vendor.AccountNumber** elemhez.
    - A **FilteredVendor.'name()'** kötése a **Vendor.Name** elemhez.

    ![Az adatmodell-elemek kötése a modell-leképezés tervező oldalán.](./media/er-components-inspections-09b.png)

13. A formátumszerkezet-fában adja hozzá a következő elemeket, hogy a szállító adatait tartalmazó XML-formátumú kimenő dokumentumot hozzon létre:

    1. Adja hozzá az **Utasítás** gyökér XML-elemet.
    2. Az **Utasítás** XML elemhez adja hozzá a beágyazott **Fél** XML-elemet.
    3. A **Fél** XML elemhez adja hozzá a következő beágyazott XML-attribútumokat:

        - Név
        - AccountNum

14. A formátumelemeket kapcsolja a megadott adatforrásokhoz a következő módon:

    - Kapcsolja az **Utasítás\\Fél\\Név** formátumelemet a **model.Vendor.Name** adatforrás-mezőhöz.
    - Kapcsolja az **Utasítás\\Fél\\AccountNum** formátumelemet a **model.Vendor.AccountNumber** adatforrás-mezőhöz.

15. Válassza az **Ellenőrzés** lehetőséget , ha ellenőrizni szeretné a szerkeszthető formátumösszetevőt a **Formátumtervező** oldalon.

    ![Adatforrásokhoz kapcsolt formátumelemek validálása a Formátumtervező oldalon.](./media/er-components-inspections-09c.png)

16. A következő ellenőrzési hiba jelentkezik. Az üzenet tájékoztatja, hogy hiba jelentkezhet a konfigurált **Utasítás\\Fél\\Név** és **Utasítás\\Fél\\AccountNum** formátum-összetevőkhöz futásidőben, ha a `model.Vendor` lista üres.

    ![Ellenőrzési hiba a konfigurált formátumösszetevők lehetséges hibájáról.](./media/er-components-inspections-09d.png)

A következő ábra bemutatja azt a futásidejű hibát, amely akkor jelentkezik, ha figyelmen kívül hagyja a figyelmeztetést, és a **Futtatás** paranccsal futtatja a formátumot és egy nem létező szállító számlaszámát választaja ki. Mivel a kért szállító nem létezik, a `model.Vendor` lista üres lesz (azaz nem tartalmaz rekordokat).

![Futásidejű hibák, amelyek a formátumleképezés futtatásakor lépnek fel.](./media/er-components-inspections-09e.png)

### <a name="automatic-resolution"></a>Automatikus megoldás

A **Figyelmeztetések** lap rácsának kijelölt sorához válassza a **Kapcsolás megszüntetése** lehetőséget. Az **Elérési út** oszlopra mutató kötés automatikusan törlődik a formátumelemek közül.

### <a name="manual-resolution"></a>Manuális megoldás

#### <a name="option-1"></a>1. beállítás

Kapcsolhatja az **Utasítás\\Fél\\Név** formátumelemet a `model.Vendor` adatforrás elemhez. Futásidőben ez a kötés először meghívja a `model.Vendor` adatforrást. Amikor a `model.Vendor` üres rekordlistát ad vissza, a beágyazott formátumelemek nem futnak. Ezért nem jelennek meg érvényesítési figyelmeztetések ehhez a formátumkonfigurációhoz.

![A formátumelem kötése az adatforrás-elemhez a Formátumtervező oldalon.](./media/er-components-inspections-09e.gif)

#### <a name="option-2"></a>2. beállítás

Módosítsa az **Utasítás\\Fél\\Név** formátumelemet `model.Vendor.Name` helyett `FIRSTORNULL(model.Vendor).Name` értékre. A frissített kötés feltételesen konvertálja a `model.Vendor` adatforrás első rekordját a **Rekordlista** típus típusból egy új **Rekord** típusú adatforráshoz. Ez az új adatforrás ugyanazt a mezőhalmazt tartalmazza.

- Ha legalább egy rekord elérhető a `model.Vendor` adatforrásban, a rekord mezői a `model.Vendor` adatforrás első rekordja mezőinek értékeivel lesznek kitöltve. Ebben az esetben a frissített kötés a szállító nevét adja vissza.
- Ellenkező esetben a létrehozott rekord minden mezője ki van töltve a mező adattípusának alapértelmezett értékével. Ebben az esetben az üres karakterláncot ad vissza a **Karakterlánc** adattípus alapértelmezett értékeként.

Ezért nem fordulnak elő érvényesítési figyelmeztetések a **Utasítás\\Fél\\Név** formátumelemhez, ha az a `FIRSTORNULL(model.Vendor).Name` kifejezéshez van kötve.

![A módosított kötés feloldja az érvényesítési figyelmeztetéseket a Formátumtervező lapon.](./media/er-components-inspections-09f.gif)

#### <a name="option-3"></a>3. beállítás

Ha kifejezetten szeretné meghatározni az adatokat egy generált dokumentumban, amikor a **Rekordlista** típusú `model.Vendor` adatforrás nem ad vissza rekordokat (a **Nem elérhető** szöveg ebben a példában) módosítsa az **Utasítás\\Fél\\Név** formátumelemét `model.Vendor.Name` értékről `IF(NOT(ISEMPTY(model.Vendor)), model.Vendor.Name, "Not available")` értékre. Használhatja a `IF(COUNT(model.Vendor)=0, model.Vendor.Name, "Not available")` kifejezést is.

### <a name="additional-consideration"></a><a id="i9a"></a>További megfontolandó kérdések

Az ellenőrzés egy másik lehetséges problémára is figyelmezteti. Alapértelmezés szerint, amikor kapcsolja az **Utasítás\\Fél\\Név** és **Utasítás\\Fél\\AccountNum** formátumelemeket a megfelelő mezőkhöz a **Rekordlista** típusú `model.Vendor` adatforrásban, ezek a kötések futtatva lesznek, és felveszik a `model.Vendor` adatforrás első rekordja megfelelő mezőinek értékeit, ha az a lista nem üres.

Mert az **Utasítás\\Fél** formátumelemet nem kötötte a `model.Vendor` adatforráshoz. Szállítói adatforrás, a **Utasítás\\Fél** elem nem lesz iterálva a `model.Vendor` adatforrás minden rekordjához a formátum végrehajtása során. Ehelyett a létrehozott dokumentum csak a rekordlista első rekordjából származó adatokkal lesz kitöltve, ha az több rekordot tartalmaz. Ezért lehet, hogy probléma van, ha a formátum célja, hogy töltse ki a létrehozott dokumentumot a `model.Vendor` adatforrás összes szállítójával kapcsolatos információkkal. A probléma megoldásához kösse az **Utasítás\\Fél** elemet a `model.Vendor` adatforráshoz.

## <a name="executability-of-an-expression-with-filter-function-caching"></a><a id="i10"></a>Kifejezés végrehajthatósága a SZŰRŐ funkcióval (gyorsítótárazás)

Több beépített ER-függvénnyel, többek között a [SZŰRŐ](er-functions-list-filter.md) és az [ALLITEMSQUERY](er-functions-list-allitemsquery.md) függvények használatával el lehet érni alkalmazási táblákat, nézeteket és az adatentitásokat úgy, hogy egyetlen SQL-hívást indít a szükséges adatok lekéréséhez rekordlistaként. Az egyes függvények argumentumaként a **Rekordlista** típusú adatforrás van használva, és meghatározza a hívás alkalmazási forrását. Az ER ellenőrzi, hogy a függvények egyikében megadott adatforráshoz közvetlen SQL-lekérdezés létrehozható-e. Ha nem sikerül megvalósítani aza közvetlen lekérdezést, mert az adatforrás [gyorsítótárazottként](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace) van megjelölve, akkor ellenőrzési hiba fordul elő az ER modell-leképezés tervezőben. Az üzenet arról tájékoztatja, hogy a függvényt tartalmazó ER kifejezés, amely a függvények egyikét tartalmazza nem futtatható futásidőben.

A következő lépések a problémák előfordulásának módját mutatják be.

1. Kezdje el konfigurálni az ER modell-leképezési összetevőt.
2. Adjon hozzá egy **Dynamics 365 for Operations \\ Táblarekordok** típusú adatforrást.
3. Adja a következő nevet az új adatforrásnak: **Szállító**. A **Tábla** mezőben válassza ki a **VendTable** elemet és adja meg, hogy ez az adatforrás igényelni fogja a VendTable táblát.
4. Adjon hozzá egy **Általános \\ Felhasználó beviteli paraméter** típusú adatforrást, ha a futásidejű párbeszédpanelen szállítói számlát szeretne keresni.
5. Adja a következő nevet az új adatforrásnak: **RequestedAccountNum**. A **Címke** mezőben adja meg a **Szállítói számlaszám** értéket. A **Műveletek adattípus neve** mezőben hagyja meg az alapértelmezett értéket: **Leírás**.
6. **Számított mező** típusú adatforrás hozzáadása egy olyan szállító leszűréséhez, amely iránt érdeklődnek.
7. Nevezze el az új **FilteredVendor** adatforrást , és konfigurálja úgy, hogy a `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)` kifejezést tartalmazza.
8. A konfigurált **Szállító** adatforrás megjelölése gyorsítótárazottként.

    ![A modell-leképezési összetevő konfigurálása a Modell-leképezés tervező oldalon.](./media/er-components-inspections-10a.gif)

9. Válassza az **Ellenőrzés** lehetőséget , ha ellenőrizni szeretné a szerkeszthető modell-leképezési összetevőt a **Modell-leképezés tervező** oldalon.

    ![A gyorsítótárazott Szállítói adatforrásra alkalmazott FILTER függvény validálása a Modell-leképezés tervező oldalon.](./media/er-components-inspections-10a.png)

10. A következő ellenőrzési hiba jelentkezik. Az üzenet kimondja, hogy a **SZŰRŐ** függvény nem alkalmazható a gyorsítótárazott **Szállító** adatforrásra.

A következő ábra bemutatja azt a futásidejű hibát, amely akkor jelentkezik, ha figyelmen kívül hagyja a figyelmeztetést, és a **Futtatás** parancsot választva futtatja a formátumot.

![Futásidejű hiba, amely formátumleképezésnek Formátumtervező lapon történő futtatásakor fordul elő.](./media/er-components-inspections-10b.png)

### <a name="automatic-resolution&quot;></a>Automatikus megoldás

A hiba automatikus javítása nem lehetséges.

### <a name=&quot;manual-resolution&quot;></a>Manuális megoldás

#### <a name=&quot;option-1&quot;></a>1. beállítás

Távolítsa el a **Gyorsítótár** jelölőt a **Szállító** adatforrásból. A **FilteredVendor** adatforrás ezután végrehajthatóvá válik, de a VendTable táblában említett **Szállító** adatforrás minden alkalommal elérhető lesz, amikor a **FilteredVendor** adatforrást meghívják.

#### <a name=&quot;option-2&quot;></a>2. beállítás

Módosítsa a **FilteredVendor** adatforrás kifejezését `FILTER(Vendor, Vendor.AccountNum=&quot;US-101")` helyett `WHERE(Vendor, Vendor.AccountNum="US-101")` értékre. Ebben az esetben a VendTable táblában említett **Szállító** adatforrás csak a **Szállító** adatforrás első hívása során érhető el. A rekordok kiválasztása azonban a memóriában történik. Ezért ez a megközelítés gyenge teljesítményt okozhat.

## <a name="missing-binding"></a><a id="i11"></a>Hiányzó kötés

ER formátumösszetevő konfigurálásakor az alap ER-adatmodell az ER-formátum alapértelmezett adatforrásaként szolgál. A konfigurált ER formátum futtatásakor az alapmodell [alapértelmezett modell-leképezése](er-country-dependent-model-mapping.md) az adatmodell alkalmazásadatokkal való kitöltésére szolgál. Az ER formátumtervező figyelmeztetést jelenít meg, ha egy formátumelemet olyan adatmodell-elemhez köt, amely nincs kötve a modellleképezés egyetlen adatforrásához sem, amely jelenleg a szerkeszthető formátum alapértelmezett modell-leképezéseként ki van kiválasztva. Az ilyen típusú kötés nem futtatható futásidőben, mert a futtatható formátum nem tudja kitölteni a kötött elemet alkalmazásadatokkal. Ezért futásidőben hiba történik.

A következő lépések a problémák előfordulásának módját mutatják be.

1. Kezdje el az ER adatmodellt, az ER modell-leképezés és az ER formátum összetevőit egyszerre kell konfigurálni.
2. Az adatmodellfán adjon hozzá egy **Root3** nevű gyökérelemet.
3. Módosítsa a **Root3** elemet egy új **Rekordlista** típusú beágyazott elem hozzáadásával.
4. Nevezze el az új beágyazott cikket **Szállító** néven.
5. Módosítsa a **Szállító** elemet az alábbi módon:

    - Adjon hozzá egy **Karakterlánc** típusú beágyazott mezőt, és nevezze el **Név** néven.
    - Adjon hozzá egy **Karakterlánc** típusú beágyazott mezőt, és nevezze el **AccountNumber** néven.

    ![Beágyazott mezők hozzáadása a Szállítói elemhez az Adatmodell lapon.](./media/er-components-inspections-11a.png)

6. A modell-leképezés tervezőben az **Adatforrások** ablaktáblában adjon hozzá egy **Dynamics 365 for Operations \\ Táblarekordok** típusú adatforrást.
7. Adja a következő nevet az új adatforrásnak: **Szállító**. A **Tábla** mezőben válassza ki a **VendTable** elemet és adja meg, hogy ez az adatforrás igényelni fogja a VendTable táblát.
8. Adjon hozzá egy **Általános \\ Felhasználó beviteli paraméter** típusú adatforrást, ha a futásidejű párbeszédpanelen szállítói számlát szeretné lekérdezni.
9. Adja a következő nevet az új adatforrásnak: **RequestedAccountNum**. A **Címke** mezőben adja meg a **Szállítói számlaszám** értéket. A **Műveletek adattípus neve** mezőben hagyja meg az alapértelmezett értéket: **Leírás**.
10. **Számított mező** típusú adatforrás hozzáadása egy olyan szállító leszűréséhez, amely iránt érdeklődnek.
11. Nevezze el az új **FilteredVendor** adatforrást , és konfigurálja úgy, hogy a `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)` kifejezést tartalmazza.
12. Az adatmodell elemeit a következő módon kötheti a konfigurált adatforrásokhoz:

    - A **FilteredVendor** kötése a **Szállító** elemhez.
    - A **FilteredVendor.AccountNum** kötése a **Vendor.AccountNumber** elemhez.

    > [!NOTE]
    > A **Vendor.Name** adatmodell mezője nem kötött marad.

    ![A konfigurált adatforrásokhoz kötött adatmodell-elemek és a Modell-leképezés tervezője oldalon nem kötöttként megmaradó adatmodell-elem.](./media/er-components-inspections-11b.png)

13. A formátumszerkezet-fában adja hozzá a következő elemeket, hogy a lekérdezett szállítók adatait tartalmazó XML-formátumú kimenő dokumentumot hozzon létre:

    1. Adja hozzá az **Utasítás** gyökér XML-elemet.
    2. Az **Utasítás** XML elemhez adja hozzá a beágyazott **Fél** XML-elemet.
    3. A **Fél** XML elemhez adja hozzá a következő beágyazott XML-attribútumokat:

        - Név
        - AccountNum

14. A formátumelemeket kapcsolja a megadott adatforrásokhoz a következő módon:

    - Kapcsolja az **Utasítás\\Fél** formátumelemet a `model.Vendor` adatforrás elemhez.
    - Kapcsolja az **Utasítás\\Fél\\Név** formátumelemet a **model.Vendor.Name** adatforrás-mezőhöz.
    - Kapcsolja az **Utasítás\\Fél\\AccountNum** formátumelemet a **model.Vendor.AccountNumber** adatforrás-mezőhöz.

15. Válassza az **Ellenőrzés** lehetőséget , ha ellenőrizni szeretné a szerkeszthető formátumösszetevőt a **Formátumtervező** oldalon.

    ![Az ER formátumösszetevő validálása a Formátumtervező oldalon.](./media/er-components-inspections-11c.png)

16. A következő ellenőrzési figyelmeztetés jelentkezik. Az üzenet tájékoztatja, hogy a **model.Vendor.Name** adatforrás mező nincs kötve a modell-leképezés egyetlen olyan adatforrásához sem, amelyet a formátum a konfiguráció szerint használ. Ezért előfordulhat, hogy az **Utasítás\\Fél\\Név** formátum elem nincs kitöltve futásidőben, és futásidejű kivétel fordulhat elő.

    ![Az ER formátumösszetevő ellenőrzése a Formátumtervező lapon.](./media/er-components-inspections-11d.png)

A következő ábra bemutatja azt a futásidejű hibát, amely akkor jelentkezik, ha figyelmen kívül hagyja a figyelmeztetést, és a **Futtatás** parancsot választva futtatja a formátumot.

![A szerkeszthető formátum futtatása a Formátumtervező lapon.](./media/er-components-inspections-11e.png)

### <a name="automatic-resolution"></a>Automatikus megoldás

A hiba automatikus javítása nem lehetséges.

### <a name="manual-resolution"></a>Manuális megoldás

#### <a name="option-1"></a>1. beállítás

Módosítsa a konfigurált modell-leképezést a **model.Vendor.Name** adatforrás-mező kötésének hozzáadásával.

#### <a name="option-2"></a>2. beállítás

Módosítsa a konfigurált formátumot a **Kimutatás\\Fél\\Név** formátumelem kötésének eltávolításával.

## <a name="not-linked-template"></a><a id="i12"></a>Nem csatolt sablon

Ha [manuálisan](er-fillable-excel.md#manual-entry) állít be egy ER formátumösszetevőt úgy, hogy az sablont használjon egy kimenő dokumentum létrehozásához, manuálisan kell hozzáadnia az **Excel\\Fájl** elemet a szerkeszthető összetevő mellékleteként, és ki kell jelölnie a mellékletet a hozzáadott **Excel\\Fájl** elemben. Ily módon azt jelzi, hogy a hozzáadott elem futásidőben kitölti a kiválasztott sablont. Ha **Vázlat** [állapotú](general-electronic-reporting.md#component-versioning) formátum-összetevő verziót állít be, a szerkeszthető összetevőhöz több sablont is hozzáadhat, majd az **Excel\\Fájl** elemben kijelölheti az egyes sablonokat az ER formátum futtatásához. Ily módon láthatja, hogy a különböző sablonok, hogyan vannak kitöltve futásidőben. Ha olyan sablonokkal rendelkezik, amelyek nincsenek kijelölve egyetlen **Excel\\Fájl** elemben sem, az ER formátumtervező figyelmezteti, hogy ezek a sablonok törlődnek a szerkeszthető ER formátum összetevőverziójából, amikor az állapota **Vázlatról** **Befejezett** értékre változik.

A következő lépések a problémák előfordulásának módját mutatják be.

1. Kezdje el konfigurálni az ER formátumösszetevőt.
2. A formátumstruktúra fában adja hozzá az **Excel\\Fájl** elemet.
3. Az imént hozzáadott **Excel\\Fájl** elemhez vegyen fel mellékletként egy **A.xlsx** Excel-munkafüzetfájlt. Az [ER-paraméterekben](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) konfigurált dokumentumtípussal adja meg az ER formátumsablonok tárolását.
4. Az **Excel\\Fájl** elemhez vegyen fel mellékletként egy másik **B.xlsx** Excel-munkafüzetfájlt. Ugyanazt a dokumentumtípust használja, mint az A munkafüzetfájlhoz.
5. Az **Excel\\Fájl** elemben jelölje ki az A munkafüzetfájlt.
6. Válassza az **Ellenőrzés** lehetőséget , ha ellenőrizni szeretné a szerkeszthető formátumösszetevőt a **Formátumtervező** oldalon.

    ![A munkafüzetfájl szerkeszthető formátumösszetevőjének érvényesítése a Formátumtervező lapon.](./media/er-components-inspections-12a.gif)

7. A következő ellenőrzési figyelmeztetés jelentkezik. Az üzenet tájékoztatja, hogy a B.xlsx munkafüzetfájl nem kapcsolódik egyetlen összetevőhöz sem, és a konfigurációs verzió állapotának módosítása után törlődik.

### <a name="automatic-resolution"></a>Automatikus megoldás

A hiba automatikus javítása nem lehetséges.

### <a name="manual-resolution"></a>Manuális megoldás

Módosítsa a konfigurált formátumot úgy, hogy eltávolítja az összes olyan sablont, amely nem kapcsolódik egyetlen **Excel\\Fájl** elemhez sem.

## <a name="not-synced-format"></a><a id="i13"></a>Nem szinkronizált formátum

Ha [konfigurál](er-fillable-excel.md) egy ER formátumösszetevőt úgy, hogy az Excel-sablont használjon egy kimenő dokumentum létrehozásához, manuálisan hozzáadhatja az **Excel\\Fájl** elemet a szerkeszthető összetevő mellékleteként, és ki kell jelölnie a mellékletet a hozzáadott **Excel\\Fájl** elemben. Ily módon azt jelzi, hogy a hozzáadott elem futásidőben kitölti a kiválasztott sablont. Mivel a hozzáadott Excel-sablon külső tervezésű, a szerkeszthető ER formátum tartalmazhat olyan Excel-neveket, amelyek hiányoznak a hozzáadott sablonból. Az ER formátumtervező figyelmezteti Önt az ER formátumelemek tulajdonságai közötti ellentmondásokra, amelyek olyan nevekre hivatkoznak, amelyek nem szerepelnek a hozzáadott Excel-sablonban.

A következő lépések a problémák előfordulásának módját mutatják be.

1. Kezdje el konfigurálni az ER formátumösszetevőt.
2. A formátumstruktúra fában adja hozzá a **Jelentés** **Excel\\Fájl** elemet.
3. Az imént hozzáadott **Excel\\Fájl** elemhez vegyen fel mellékletként egy **A.xlsx** Excel-munkafüzetfájlt. Az [ER-paraméterekben](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) konfigurált dokumentumtípussal adja meg az ER formátumsablonok tárolását.

    > [!IMPORTANT]
    > Győződjön meg arról, hogy a hozzáadott Excel-munkafüzet nem tartalmazza a **ReportTitle** nevet.

4. Adja hozzá a **Cím** **Excel\\Cella** elemet a **Jelentés** elem beágyazott elemeként. Az **Excel-tartomány** mezőbe írja be: **ReportTitle**.
5. Válassza az **Ellenőrzés** lehetőséget , ha ellenőrizni szeretné a szerkeszthető formátumösszetevőt a **Formátumtervező** oldalon.

    ![A beágyazott elemek és mezők validálása a Formátumtervező oldalon.](./media/er-components-inspections-13a.png)

6. A következő ellenőrzési figyelmeztetés jelentkezik. Az üzenet tájékoztatja, hogy a **ReportTitle** nem létezik a használt Excel-sablon **Munka1** lapján.

    ![Érvényesítési figyelmeztetés, hogy a ReportTitle név nem létezik az Excel-sablon Munka1 lapján.](./media/er-components-inspections-13b.png)

### <a name="automatic-resolution"></a>Automatikus megoldás

A hiba automatikus javítása nem lehetséges.

### <a name="manual-resolution"></a>Manuális megoldás

#### <a name="option-1"></a>1. beállítás

Módosítsa a konfigurált formátumot a sablonból hiányzó Excel-nevekre hivatkozó összes elem eltávolításával.

#### <a name="option-2"></a>2. beállítás

Excel-sablon importálásával [frissítse](er-fillable-excel.md#template-import) a szerkeszthető ER-formátumot. A szerkeszthetővé tett ER-formátum struktúráját a program [szinkronizálja](modify-electronic-reporting-format-reapply-excel-template.md) az importált Excel-sablon tartalmával.

### <a name="additional-consideration"></a>További megfontolandó kérdések

Ha meg szeretné tudni, hogyan szinkronizálható a formátumstruktúra egy ER-sablonnal az [Üzleti dokumentumkezelés](er-business-document-management.md) sablonszerkesztőjében, olvassa el az [Üzleti dokumentumsablon szerkezetének frissítése](er-bdm-update-structure.md) című témakört.

## <a name="not-synced-with-a-word-template-format"></a><a id="i14"></a>Nincs szinkronizálva Word-sablonformátummal

Ha [konfigurál](er-fillable-excel.md) egy ER formátumösszetevőt úgy, hogy a Word-sablont használjon egy kimenő dokumentum létrehozásához, manuálisan hozzáadhatja az **Excel\\Fájl** elemet a szerkeszthető összetevő mellékleteként, és ki kell jelölnie a mellékletet a hozzáadott **Excel\\Fájl** elemben.

> [!NOTE]
> Ha a Word-dokumentum csatolva van, akkor az ER-formátumtervező **Word\\Fájl** formában mutatja be a szerkeszthető elemet.

Ily módon azt jelzi, hogy a hozzáadott elem futásidőben kitölti a kiválasztott sablont. Mivel a hozzáadott Word-sablon külső tervezésű, a szerkeszthető ER formátum tartalmazhat olyan Word-tartalomvezérlőkre mutató hivatkozásokat, amelyek hiányoznak a hozzáadott sablonból. Az ER formátumtervező figyelmezteti Önt az ER formátumelemek tulajdonságai közötti ellentmondásokra, amelyek olyan tartalomvezérlőkre hivatkoznak, amelyek nem szerepelnek a hozzáadott Word-sablonban.

A problémát a következő példa mutatja be: [A szerkeszthető formátum konfigurálása az összegző szakasz elrejtésére](er-design-configuration-word-suppress-controls.md#configure-to-suppress-control).

### <a name="automatic-resolution"></a>Automatikus megoldás

A hiba automatikus javítása nem lehetséges.

### <a name="manual-resolution"></a>Manuális megoldás

#### <a name="option-1"></a>1. beállítás

A konfigurált formátum módosításához törölje a **Törölve** képletet az ellenőrzési figyelmeztetésben említett formátumelemből.

#### <a name="option-2"></a>2. beállítás

Módosítsa a használt Word-sablont úgy, hogy [hozzáadja](er-design-configuration-word-suppress-controls.md#tag-control) a szükséges címkét a releváns Word-tartalomvezérlőhöz.

## <a name="no-default-mapping"></a><a id="i15"></a>Nincs alapértelmezett leképezés

Ha a [Hiányzó kötés](#i11) vizsgálat megtörtént, a rendszer kiértékeli a megvizsgált formátumkötéseket a releváns modell-leképezési összetevő kötései alapján. Mivel [több](./tasks/er-manage-model-mapping-configurations-july-2017.md) ER modell-leképezési konfigurációt is importálhat a Finance példányba, és mindegyik konfiguráció tartalmazhatja a megfelelő modell-leképezési összetevőt, egy konfigurációt kell kiválasztani alapértelmezett konfigurációként. Ellenkező esetben a megvizsgált ER-formátum futtatása, szerkesztése vagy ellenőrzése során kivétel történik, és a következő üzenet jelenik meg: Egynél több modell-leképezés létezik a \<model name (root descriptor)\> adatmodellben a konfigurációkban \<configuration names separated by comma\>. Állítsa be az egyik konfigurációt alapértelmezettként.

A probléma előfordulásának okát és kijavítási módját lásd: [Egyetlen modellgyökérhez tartozó több származtatott leképezés kezelése](er-multiple-model-mappings.md).

## <a name="inconsistent-setting-of-header-or-footer-components"></a><a id="i16"></a>A fejléc- vagy láblécösszetevők következetlen beállítása

Amikor ER formátumösszetevőt [konfigurál](er-fillable-excel.md) egy Excel-sablon használatára kimenő dokumentum létrehozásához, hozzáadhatja az **Excel\\Fejléc** összetevőt, és kitöltheti az Excel-munkafüzet munkalapjának fejléceit. Az **Excel\\Lábléc** összetevőt hozzáadhatja a munkalap alján található láblécek kitöltésére is. Minden **Excel\\Fejléc** vagy **Excel\\Lábléc** típusú összetevő hozzáadásához be kell állítania a **Fejléc/lábléc megjelenés** tulajdonságot, hogy meghatározza az összetevő futtatásához kapcsolódó oldalakat. Mivel egyetlen **Munkalap** összetevőhöz több **Excel\\Fejléc** vagy **Excel\\Lábléc** típusú összetevőt konfigurálhat, és különböző fejléceket és lábléceket hozhat létre az Excel-munkalap különböző típusú lapjaihoz, egyetlen **Excel\\Fejléc** vagy **Excel\\Lábléc** típusú összetevőt kell beállítania a **Fejléc/lábléc megjelenése** tulajdonság meghatározott értékéhez. Ha egynél több **Excel\\Fejléc** vagy **Excel\\Lábléc** összetevő van beállítva a **Fejléc/lábléc megjelenése** tulajdonság meghatározott értékéhez, ellenőrzési hiba történik, és a következő hibaüzenet jelenik meg: A fejlécek/láblécek (&lt;összetevő típusa: Fejléc vagy Lábléc&gt;) következetlenek.

### <a name="automatic-resolution"></a>Automatikus megoldás

A hiba automatikus javítása nem lehetséges.

### <a name="manual-resolution"></a>Manuális megoldás

#### <a name="option-1"></a>1. beállítás

Módosítsa a konfigurált formátumot az egyik következetlen **Excel\\Fejléc** vagy **Excel\\Lábléc** összetevő törlésével.

#### <a name="option-2"></a>2. beállítás

Módosítsa a **Fejléc/lábléc megjelenése** tulajdonság értékét az **Excel\\Fejléc** vagy **Excel\\Lábléc** következetlen összetevőinek egyikében.

## <a name="inconsistent-setting-of-page-component"></a><a id="i17"></a>Az Oldal összetevő inkonzisztens beállítása

Amikor egy ER-formátumösszetevőt úgy [konfigurál](er-fillable-excel.md), hogy egy Excel-sablont használjon kimenő dokumentum előállításához, hozzáadhatja az **Excel\\Oldal** összetevőt, hogy a generált dokumentumot ER-képletek segítségével tördelje oldalakra. Minden egyes hozzáadott **Excel\\Oldal** összetevőhöz hozzáadhat beágyazott [Tartomány](er-fillable-excel.md#range-component) összetevőt, és továbbra is megfelel a következő [struktúrának](er-fillable-excel.md#page-component-structure):

- Az első beágyazott **Tartomány** összetevő úgy konfigurálható, hogy a **Replikáció iránya** tulajdonság beállítása **Nincs replikáció**. Ezzel a tartománnyal lehet oldalfejléceket generálni a létrehozott dokumentumokban.
- További beágyazott **Tartomány** összetevőt is hozzáadhat, ahol a **Replikáció iránya** tulajdonság beállítása **Függőleges**. Ezek a tartományok a létrehozott dokumentumok kitöltéséhez használhatók.
- Az utolsó beágyazott **Tartomány** összetevő úgy konfigurálható, hogy a **Replikáció iránya** tulajdonság beállítása **Nincs replikáció**. Ezzel a tartománnyal lehet oldalléceket generálni a létrehozott dokumentumokban, és hozzáadni a szükséges oldaltöréseket.

Ha a tervezés során nem követi ezt a szerkezetet egy ER-fomtáumhoz az ER-formátumtervezőben, ellenőrzési hiba történik, és a következő hibaüzenet jelenik meg: "Több mint két tartomány-összetevő van replikáció nélkül. Távolítsa el a szükségtelen összetevőket."

### <a name="automatic-resolution"></a>Automatikus megoldás

A hiba automatikus javítása nem lehetséges.

### <a name="manual-resolution"></a>Manuális megoldás

#### <a name="option-1"></a>1. beállítás

Módosítsa a konfigurált formátumot az **Excel\\Tartomány** inkonzisztens összetevőinél a **Replikációs irány** tulajdonságának módosításával.

## <a name="additional-resources"></a>További erőforrások

[ALLITEMS ER-függvény](er-functions-list-allitems.md)

[ALLITEMSQUERY ER-függvény](er-functions-list-allitemsquery.md)

[INT64VALUE ER-függvény](er-functions-conversion-int64value.md)

[INTVALUE ER-függvény](er-functions-conversion-intvalue.md)

[FILTER ER-funkció](er-functions-list-filter.md)

[WHERE ER-függvény](er-functions-list-where.md)

[Több alkalmazási táblából származó adatok beolvasásához használja a JOIN adatforrásokat az ER-modell-leképezésekben](er-join-data-sources.md)

[Az ER-formátumok végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárítása érdekében](trace-execution-er-troubleshoot-perf.md)

[Üzletidokumentum-kezelés – áttekintés](er-business-document-management.md)

[Word tartalmi vezérlőelemek elrejtése a létrehozott jelentésekben](er-design-configuration-word-suppress-controls.md)

[Több származtatott leképezés kezelése egy modellgyökérnél](er-multiple-model-mappings.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
