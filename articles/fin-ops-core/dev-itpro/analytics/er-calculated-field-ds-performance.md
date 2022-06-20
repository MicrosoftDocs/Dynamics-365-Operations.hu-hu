---
title: Az ER megoldások teljesítményének javítása a paraméterek SZÁMÍTOTT MEZŐ-adatforrások hozzáadásával
description: Ez a cikk bemutatja, hogy hogyan javíthatja az elektronikus jelentéskészítő (ER) megoldások teljesítményét azáltal, hogy paraméterezett SZÁMÍTOTT MEZŐ-adatforrásokat ad hozzá.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8c2c0499ac3d41c9bb6026cc05f971087799c28f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850114"
---
# <a name="improve-the-performance-of-er-solutions-by-adding-parameterized-calculated-field-data-sources"></a>Az ER megoldások teljesítményének javítása a paraméterek SZÁMÍTOTT MEZŐ-adatforrások hozzáadásával

[!include [banner](../includes/banner.md)]

Ez a cikk [bemutatja](trace-execution-er-troubleshoot-perf.md)[, hogy hogyan lehet a futtatott elektronikus jelentési (ER)](general-electronic-reporting.md) formátumokat teljesítménykövetéssel nyomon követni, majd ezeknek a nyomkövetési adatoknak az használatával javíthatja a teljesítményt egy **paraméterezett Számított** mező adatforrás beállításával.

Az ER üzleti dokumentumok létrehozására használatos konfigurációinak tervezési folyamatának részeként meghatározhatja azt a módszert, amellyel a rendszer adatokat kérhet le az alkalmazásból, majd a létrehozott kimenetbe illesztheti őket. A **Számított mező** típusú paraméterezett ER adatforrás tervezésével csökkenthető az adatbázis-hívások száma, és jelentősen csökkenthető az idő és költség, amely az ER formátumvégrehajtás részleteinek gyűjtéséhez kapcsolódik.

## <a name="prerequisites"></a>Előfeltételek

- A példában olvasható példák csak [a következő szerepkörök valamelyikének eléréséhez férhetnek hozzá](../sysadmin/tasks/assign-users-security-roles.md):

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

- A vállalatot **DEMF** értékre kell beállítani.
- Hajtsa végre a [cikk 1](#appendix1) . mellékletének lépéseit a Microsoft ER-minta megoldásnak az ebben a példában szereplő példák befejezéséhez szükséges összetevőinek letöltéséhez.
- A cikk [2](#appendix2) . mellékletében található lépések segítségével konfigurálhatja az ER-keretrendszerhez szükséges minimális ER-paramétereket a Microsoft ER-megoldás teljesítményének javítása érdekében.

## <a name="import-the-sample-er-solution"></a>A minta ER-megoldás importálása

Tegyük fel, hogy egy új ER-megoldást kell terveznie, amellyel szállítói tranzakciókat bemutató új jelentést hozhat létre. Jelenleg a kiválasztott szállítóhoz tartozó tranzakciókat a **Szállítói tranzakciók** oldalon találja (lépjen a **Kötelezettségek** \> **Szállítók** \> **Minden szállító** pontra, válasszon a szállítók közül, majd a Műveleti ablaktábla **Szállító** lapján, a **Tranzakciók** csoportban válassza a **Tranzakciók** elemet). Önnek azonban az összes szállítói tranzakció együttes megjelenítésére van szükség, egyetlen elektronikus dokumentumban, XML formátumban. Ez a megoldás több olyan ER-konfigurációt is magában foglal, amelyek a szükséges adatmodell-, modell-hozzárendelési és formátum-összetevőket tartalmazzák.

Az első lépés az, hogy a minta ER-megoldást importálni kell a szállítói tranzakciók jelentésének előállításához.

1. Jelentkezzen be a Microsoft Dynamics vállalathoz létesített 365 Pénzügy példányba.
2. Ebben a cikkben létrehozhatja és módosíthatja a **Litware, Zrt.** mintavállalat konfigurációit. Győződjön meg róla, hogy ezt a konfigurációszolgáltatót hozzáadták a Finance-példányhoz, és aktívként megjelölték. További információért tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.
3. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** csempét.
4. A **Konfigurációk** lapon importálja az előfeltételként az Finance-ba letöltött ER-konfigurációkat, a következő sorrendben: adatmodell, modell-hozzárendelés, formátum. Minden konfiguráció esetén hajtsa végre az alábbi lépéseket:

    1. A Műveleti ablaktáblában válassza az **Átváltás** \> **Betöltés XML-fájlból** elemet.
    2. A **Tallózás** gombbal válassza ki a megfelelő, XML-formátumú fájlt az ER-konfigurációhoz.
    3. Válassza ki az **OK** lehetőséget.

![A Konfigurációk oldalon importált konfigurációk.](./media/er-calculated-field-ds-performance-imported-configurations.png)

## <a name="review-the-sample-er-solution"></a>A minta ER-megoldás áttekintése

### <a name="review-the-model-mapping"></a>A modell-leképezés áttekintése

1. A **Konfigurációk** oldalon, a konfigurációk bal oldali panelen található fájában bontsa ki a **Teljesítményjavítás modellje** elemet, majd válassza a **Teljesítményfejlesztés leképezése** lehetőséget.
2. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
3. A **Modell leképezése adatforráshoz** oldalon a Műveleti panelen válassza a **Tervező** lehetőséget.

    Ez az ER-leképezés a következők műveletek elvégzésére van tervezve:

    - A VendTrans táblában (**Trans** adatforrás) tárolt szállítói tranzakciók listájának beolvasása.
    - Minden tranzakcióhoz aVendTable táblából beolvassa annak a szállítónak a rekordját, akinek a tranzakciót feladták (**\#Vend** adatforrás).

    > [!NOTE]
    > A **\#Vend** adatforrás be van állítva a megfelelő szállítói rekord beolvasása a meglévő sok az egyhez kapcsolat használatával **\@.\>Relations'.VendTable\_AccountNum**.

    A modell-leképezés ebben a konfigurációban implementálja az alap adatmodellt bármely ER formátumhoz, amely ehhez a modellhez lett készítve és a Finance által futtatva lett. Tehát a **Trans** adatforrás tartalma ER-formátumoknak, például absztrakt **modell** adatforrásoknak van kitéve.

    ![Trans adatforrás a modell-leképezés tervező oldalán.](media/er-calculated-field-ds-performance-mapping-1.png)

4. Zárja be a **Modell-hozzárendelési tervező** lapot.
5. Zárja be a **Modell hozzárendelése adatforráshoz** lapot.

### <a name="review-format"></a>Formátum áttekintése

1. A **Konfigurációk** oldalon, a konfigurációk bal oldali panelen található fájában bontsa ki a **Teljesítményjavítás modellje** elemet, majd válassza a **Teljesítményfejlesztés formátuma** lehetőséget.
2. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
3. A **Formátumtervező** oldalon a **Hozzárendelés** fülön válassz a **Kibontás/összecsukás** elemet.
4. Bontsa ki a **Modell**, **Adatok** és **Tranzakció** elemeket.

    Ez az ER-formátum úgy van kialakítva, hogy a szállítói tranzakciók jelentését XML-formátumban hozza létre.

    ![Az adatforrások és a konfigurált kötések formátumelemeinek formázása a Formátumtervezés oldalon.](media/er-calculated-field-ds-performance-format.png)

5. Zárja be a **Formátumtervező** lapot.

## <a name="run-the-sample-er-solution-to-trace-execution"></a>A minta ER-megoldás futtatása a végrehajtás nyomon követéséhez

Tegyük fel, hogy befejezte az ER-megoldás első verziójának tervezését. Ezt követően tesztelni szeretné a megoldást a Finance and Operations példányában, és elemezni a végrehajtás teljesítményét.

### <a name="turn-on-the-er-performance-trace"></a>Az ER teljesítmény-nyomkövetésének bekapcsolása

1. Válassza a **DEMF** vállalatot.
2. Hajtsa végre a következő lépéseket a [Teljesítmény-követés bekapcsolása](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) alatt teljesítmény-nyomkövetés előállításához az ER-formátum futtatása során.

    ![A Felhasználói paraméterek párbeszédablak.](media/er-calculated-field-ds-performance-format-user-parameters.png)

### <a name="run-the-er-format"></a><a id="run-format"></a>Az ER-formátum futtatása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon található konfigurációs fában válassza ki a **Teljesítmény-javítás formátuma** elemet.
3. A Műveleti ablaktáblán kattintson a **Futtatás** elemre.

## <a name="use-the-performance-trace-to-analyze-model-mapping-performance"></a>A teljesítmény nyomon követése használata a modell-leképezés teljesítményének elemzéséhez

1. A **Konfigurációk** oldalon található konfigurációs fában válassza ki a **Teljesítmény-javítás leképezése** elemet.
2. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
3. A **Modell leképezések** oldalon a Műveleti panelen válassza a **Tervező** lehetőséget.
4. A **Modell-hozzárendelési tervező** lapon a Műveleti ablaktáblában válassza ki a **Teljesítmény-nyomkövetés** lehetőséget.
5. Válassza ki a legutóbb létrehozott nyomkövetést, majd kattintson az **OK** gombra.

Az aktuális modell-hozzárendelés bizonyos adatforráselemeihez új információk jelennek meg:

- Az adatforrás által az adatok lekérésére fordított tényleges idő
- Ugyanez az időtartam a teljes modell-hozzárendelés lefuttatására fordított összes idő százalékaként kifejezve

![Végrehajtási idő részletei a Modell-hozzárendelés tervező lapján.](./media/er-calculated-field-ds-performance-mapping-2.png)

A **Teljesítményadatok** rácsa azt jeleníti meg, hogy a **Trans** adatforrás egy alkalommal hívja meg a VendTrans táblát. A **\[265\]\[Q:265\]** érték a **Trans** adatforrásban azt jelzi, hogy az 265 szállítói tranzakciót beolvasták az alkalmazás táblából, és vissza lettek küldve az adatmodellhez.

A **Teljesítményadatok** rácsa azt is jelzi, hogy az aktuális modell-hozzárendelés ismétlődő adatbázis-igényléseket hoz-e, miközben a **\#Vend** adatforrás fut. Ez a duplikálása a következő okok miatt történik meg:

- A szállítói táblát két alkalommal kell meghívni mind a 265 ismétlődő szállítói tranzakcióhoz, ez összesen 530 hívás:

    - Egy hívás történik a szállítói számla számának megadásához.
    - Egy hívás történik a szállítói nevének megadásához.

- A szállítói táblát mindegyik ismétlődő szállítói tranzakcióhoz meg kell hívni, még akkor is, ha a beolvasott tranzakciók csak öt szállítóhoz lettek feladva. A 530 hívásból 525 ismétlődő. A következő ábra mutatja az ismétlődő hívásokról kapott üzenetet (adatbázis-kérelmek).

![Ismétlődő adatbázis-kérelmekkel kapcsolatos üzenet a Modell-hozzárendelési tervező oldalon.](./media/er-calculated-field-ds-performance-mapping-2a.png)

A teljes modell-leképezés végrehajtási idejéből (kb. nyolc másodperc) több mint 80 százalék (kb. hat másodperc) telt el az értékek lehívásával a VendTable alkalmazástáblából. Ez a százalékos érték túl nagy az öt szállító két attribútumához képest, összehasonlítva a VendTrans-alkalmazás táblából származó adatok mennyiségével.

Ha csökkenteni szeretné az összes tranzakció szállítói adatainak beolvasásához szükséges hívások számát, valamint szeretné segíteni modell-hozzárendelés teljesítményének javítását, használhatja a **\#Vend** adatforrás gyorsítótárazását.

> [!NOTE]
> A **Trans\\\#Vend** adatforrást a program a **Trans** adatforrás aktuális tranzakciójának hatókörében gyorsítótárazza a futásidőben.

A **\#Vend** adatforrás gyorsítótárazásával csökkenthető az ismétlődő hívások száma 525-ről 260-ra, de nem lehet a duplikálást teljes mértékben kiküszöbölni. A duplikálások teljes megszüntetéséhez beállítható a **Számított mezőtípus**, ami egy új, paraméterezett adatforrás.

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>A modell-hozzárendelés javítása a végrehajtási nyomkövetésből származó információk alapján

### <a name="change-the-logic-of-the-model-mapping"></a>A modell-hozzárendelés logikájának megváltoztatása

Hajtsa végre a következő lépéseket a gyorsítótárazás és a **Számított mező** típusú adatforrás használatához , hogy megakadályozza az ismétlődő hívásokat az adatbázis felé.

1. A **Konfigurációk** oldalon található konfigurációs fában válassza ki a **Teljesítmény-javítás leképezése** elemet.
2. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
3. A **Modell leképezések** oldalon a Műveleti panelen válassza a **Tervező** lehetőséget.
4. A **Model-leképezés tervező** lapon hajtsa végre az alábbi lépéseket, ha **Táblázatrekord** típusú adatforrás hozzáadásához a VendTable alkalmazástábla rekordjainak eléréséhez:

    1. Az **Adatforrástípusok** panelen bontsa ki a **Dynamics 365 for Operations** elemet, és válassza a **Táblarekordok** lehetőséget.
    2. Válassza a **Gyökér hozzáadása** elemet.
    3. A párbeszédpanel **Név** mezőjébe írja be a **Vend** kifejezést.
    4. A **Tábla** mezőbe írja be a **VendTable** kifejezést.
    5. Válassza ki az **OK** lehetőséget.

5. A **Számított** mezőtípus adatforrásaihoz a hívásokat csak akkor lehet paraméterezni, ha azok az adatforrások egy tárolóban találhatók. Ennek megfelelően a következő lépések végrehajtásával adjon hozzá egy adatforrást az **Üres tároló** típushoz, hogy a **Kiszámított mező** típus új paraméterekkel rendelkezzen:

    1. Az **Adatforrástípusok** panelen bontsa ki az **Általános** elemet, és válassza a **Tároló űrítése** lehetőséget.
    2. Válassza a **Gyökér hozzáadása** elemet.
    3. A párbeszédpanel **Név** mezőjébe írja be a **Box** kifejezést.
    3. Válassza ki az **OK** lehetőséget.

    ![A Box adatforrás a modell-leképezés tervező oldalán.](./media/er-calculated-field-ds-performance-mapping-3.png)

6. Hajtsa végre a következő lépéseket a **Számított mező** típusú paraméterezett adatforrásának hozzáadásához:

    1. Az **Adatforrás** ablaktáblán válassz a **Box** elemét.
    2. Az **Adatforrástípusok** panelen bontsa ki a **Funkciók** elemet, és válassza a **Számított mező** elemet.
    3. Válassza a **Hozzáadás** lehetőséget.
    4. A párbeszédpanel **Név** mezőjébe írja be a **Vend** kifejezést.
    5. Válassza a **Képlet szerkesztése** elemet.
    6. A **Képlettervező** lapon válassza ki a **Paraméterek** lehetőséget annak meghatározzák hogy az adatforrás hívásakor milyen paramétereket kell megadni.
    7. A **Paraméterek** párbeszédpanelen kattintson az **Új** gombra.
    8. A **Név** mezőbe írja be a következőt: **parmVendAccNumber**.
    9. A **Típus** mezőben válassza ki a **Karakterlánc** lehetőséget.
    10. Válassza ki az **OK** lehetőséget.
    11. A **Képlet** mezőbe írja be: **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.
    12. Válassza a **Mentés** lehetőséget, majd a **Képlettervező** oldalt.
    13. Az új adatforrás hozzáadásához kattintson az **OK** gombra.

7. Hajtsa végre a következő lépéseket a hozzáadott adatforrás a végrehajtás közben gyorsítótárban történő megjelöléséhez:

    1. Válassza az **Adatforrások** ablaktábla **Box\\Vend** elemét.
    2. Válassza a **Gyorsítótárazás** lehetőséget.

    > [!NOTE]
    > A **Box\\Vend** adatforrást a program a **Trans** adatforrás szállítói tranzakciójának hatókörében gyorsítótárazza a futásidőben.

8. A következő lépésekkel frissítheti a beágyazott **Trans\\\#Vend** adatforrást, **Box\\Vend** adatforrást használja:

    1. Bontasa ki az **Adatforrások** ablaktábla **Trans** elemét.
    2. Válassza ki a **Trans\\\#Vend** adatforrást, majd válassza a **Szerkesztés** \> **Képlet szerkesztése** lehetőséget.
    3. A **Képlettervező** lap **Képlet** mezőjébe írja be a mezőbe a következőt: **Box.Vend(\@.AccountNum)**.
    4. Válassza a **Mentés** lehetőséget, majd zárja be a **Képlettervező** oldalt.
    5. A kiválasztott adatforrás változásainak befejezéséhez kattintson az **OK** gombra.

9. Válassza a **Mentés** lehetőséget.

    ![A Vend adatforrás a Modell-leképezés tervező oldalán.](./media/er-calculated-field-ds-performance-mapping-4.png)

10. Zárja be a **Modell-hozzárendelési tervező** lapot.
11. Zárja be a **Modell-hozzárendelések** lapot.

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>Az ER-modell-hozzárendelés módosított verziójának elvégzése

1. A **Konfigurációk** lap **Verziók** gyorslapján válassza ki az **1.2**-es verziót a **Teljesítményjavítás-leképezés** konfigurációhoz.
2. Válassza ki az **Állapot módosítása** \> **Kész** elemet majd válassza az **OK** lehetőséget.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>A módosított ER-megoldás futtatása a végrehajtás nyomon követéséhez

Új teljesítménykövetés létrehozásához [ismételje meg a cikk korábbi, Az ER-formátum](#run-format) futtatása szakaszban található lépéseket.

## <a name="use-the-performance-trace-to-analyze-adjustments-to-the-model-mapping"></a>A teljesítmény nyomon követése használata a modell-leképezés módosításainak elemzéséhez 

1. A **Konfigurációk** oldalon található konfigurációs fában válassza ki a **Teljesítmény-javítás leképezése** elemet.
2. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
3. A **Modell leképezések** oldalon a Műveleti panelen válassza a **Tervező** lehetőséget.
4. A **Modell-hozzárendelési tervező** lapon a Műveleti ablaktáblában válassza ki a **Teljesítmény-nyomkövetés** lehetőséget.
5. Válassza ki a legutóbb létrehozott nyomkövetést, majd kattintson az **OK** gombra.

Megfigyelheti, hogy az Ön által a modell-hozzárendelésen végzett kiigazításokkal megszüntette az adatbázisba intézett ismétlődő lekérdezéseket. Az adott modellhozzárendeléshez tartozó, adatbázistáblákba és adatforrásokba küldött lehívások száma csökkent.

![Híváslánc információk az 1. modell-leképezés tervező oldalán.](./media/er-calculated-field-ds-performance-mapping-5.png)

A teljes végrehajtási idő csökkent a 20-adára csökkent (mintegy 8 másodperc helyett mintegy 400 ezredmásodperc). Ezáltal a teljes ER-megoldás teljesítménye javult.

![Híváslánc információk a 2. modell-leképezés tervező oldalán.](./media/er-calculated-field-ds-performance-mapping-5a.png)

## <a name="appendix-1-download-the-components-of-the-sample-microsoft-er-solution"></a><a name="appendix1"></a>1. függelék: A minta Microsoft ER megoldás komponenseinek letöltése

A következő fájlokat le kell töltenie, és helyben tárolnia.

| Fájl                                        | Tartalom |
|---------------------------------------------|---------|
| Teljesítményjavítás modell.verzió.1     | [Minta ER-adatmodell konfigurációja](https://download.microsoft.com/download/4/6/f/46f0f3fa-782b-414a-8f7b-b6c64a388661/Performance_improvement_model.version.1.xml) |
| Teljesítmény-javítás leképezés.verzió.1.1 | [Minta ER-adatmodell leképezési konfigurációja](https://download.microsoft.com/download/8/9/1/8913a763-afb8-4bf4-aaf1-95ad793ffc5a/Performance_improvement_mapping.version.1.1.xml) |
| Teljesítmény-javítás formátum.verzió.1.1  | [Minta ER-formátum konfigurációja](https://download.microsoft.com/download/9/0/c/90c75963-bc78-4edc-9096-556bbe281f10/Performance_improvement_format.version.1.1.xml) |

## <a name="appendix-2-configure-the-er-framework"></a><a name="appendix2"></a>2. melléklet: Az ER-keretrendszer konfigurálása

Mielőtt elkezdené használni az ER keretrendszert a minta Microsoft ER-megoldás teljesítményének javítása érdekében, konfigurálnia kell az ER-paraméterek minimális készletét.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>ER-paraméterek konfigurálása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza az **Elektronikus jelentéskészítés paraméterei** elemet.
3. Az **Elektronikus jelentéskészítési paraméterek** oldalon, az **Általános** lapon a **Tervezői mód engedélyezése** lehetőséget állítsa **Igen** értékre.
4. A **Mellékletek** lapon állítsa be a következő paramétereket:

    - A **Konfigurációk** mezőben válassza ki a **Fájl** típust az **DEMF** vállalat esetében.
    - A **Feladatarchívum**, **Ideiglenes**, **Alap** és **Egyebek** mezőkben válassza a **Fájl** típust.

Az ER-paraméterekkel kapcsolatos további tudnivalókat lásd: [ER-keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>ER-konfigurációszolgáltató aktiválása

Minden hozzáadott ER-konfigurációt egy ER-konfigurációszolgáltató által birtokoltként kell megjelölni. Erre a célra az **Elektronikus jelentéskészítés** munkaterületen aktiválható ER-konfigurációszolgáltató használatos. Éppen ezért aktiválnia kell egy ER-konfigurációszolgáltatót az **Elektronikus jelentéskészítés** munkaterületen, mielőtt elkezdené az ER-konfigurációk hozzáadását vagy szerkesztését.

> [!NOTE]
> Csak az ER-konfiguráció tulajdonosa szerkesztheti a konfigurációt. Éppen ezért aktiválnia kell a megfelelő ER-konfigurációszolgáltatót az **Elektronikus jelentéskészítés** munkaterületen, mielőtt elkezdené az ER-konfigurációk hozzáadását vagy szerkesztését.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Az ER-konfigurációszolgáltatók listájának áttekintése

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációszolgáltatók** elemet.
3. A **Konfigurációszolgáltatók tábla** oldalon minden szolgáltatói rekordnak egyedi neve és URL-címe van. Tekintse át az oldal tartalmát. Ha a már létezik a **Litware, Inc.** rekordja, hagyja ki a következő eljárást: [Új ER-konfigurációszolgáltató hozzáadása](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>Új ER-konfigurációszolgáltató hozzáadása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációszolgáltatók** elemet.
3. A **Konfigurációszolgáltatók** oldalon válassza az **Új** elemet.
4. A **Név** mezőbe írja be a következőt: **Litware, Inc.**.
5. Az **Internetcím** mezőben adja meg a következőt: `https://www.litware.com`.
6. Válassza a **Mentés** lehetőséget.

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>ER-konfigurációszolgáltató aktiválása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációszolgáltatók** szakaszban válassza ki a **Litware, Inc.** csempét, majd válassza a **Beállítás aktívként** lehetőséget.

További információért az ER-konfigurációszolgáltatókkal kapcsolatban tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentések áttekintése](general-electronic-reporting.md)
- [Az ER-formátumok végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárítása érdekében](trace-execution-er-troubleshoot-perf.md)
- [ER adatforrások paraméterezett hívásainak támogatása a Számított mezőtípusban](er-calculated-field-type.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
