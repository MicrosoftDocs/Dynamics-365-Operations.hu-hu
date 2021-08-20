---
title: Az ER-formátumok végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárítása érdekében
description: Ez a témakör azt mutatja be, hogyan kell használni az Elektronikus jelentéskészítés (ER) teljesítményfigyelő funkcióját a teljesítménnyel kapcsolatos problémák elhárításához.
author: NickSelin
ms.date: 06/22/2021
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
ms.openlocfilehash: 10eddf2f60db914e6451840d4d7aedb9dce7108874ea3ff45f375b85a55a694f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6724393"
---
# <a name="trace-the-execution-of-er-formats-to-troubleshoot-performance-issues"></a>Az ER-formátumok végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárításához

[!include[banner](../includes/banner.md)]

Az Elektronikus jelentéskészítés (ER) elektronikus dokumentumok létrehozására használatos konfigurációinak tervezési folyamatának részeként meghatározhatja azt a módszert, amellyel a rendszer adatokat kérhet le az alkalmazásból, majd a létrehozott kimeneti fájlba illesztheti őket. A ER teljesítmény-nyomonkövetési funkciója segítségével jelentősen csökkenthető az idő és költség, amely az ER-formátum végrehajtásához kapcsolódó részletes adatok gyűjtésére és az adatok teljesítményi problémák hibajavítására való felhasználására fordítandó. Ez az oktatóanyag bemutatja, hogy hogyan lehet elvégezni a teljesítmény nyomon követését a végrehajtott ER formátumokhoz, valamint hogy hogyan lehet felhasználáni a nyomon követésből származó információkat a teljesítmény javítására.

## <a name="prerequisites"></a>Előfeltételek

A jelen oktatóanyagban szereplő példák elvégzéséhez a következő hozzáférésekkel kell rendelkeznie:

- Hozzáférés a következő szerepkörök egyikéhez:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

- Hozzáférés a Regulatory Configuration Service (RCS) példányához, amelyet ugyanarra a bérlőre telepítettek, mint az alkalmazást, a következő szerepkörök egyikéhez:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

A következő fájlokat is le kell töltenie és helyben tárolnia.

| Fájl                                  | Tartalom                               |
|---------------------------------------|---------------------------------------|
| Teljesítmény-nyomonkövetési modell.verzió.1     | [Minta ER-adatmodell konfigurációja](https://download.microsoft.com/download/0/a/a/0aa84e48-8040-4c46-b542-e3bf15c9b2ad/Performancetracemodelversion.1.xml)    |
| Teljesítmény-nyomonkövetési metaadat.verzió.1  | [Minta ER-metaadat konfigurációja](https://download.microsoft.com/download/a/9/3/a937e8c4-1f8a-43e4-83ee-7d599cf7d983/Performancetracemetadataversion.1.xml)      |
| Teljesítmény-nyomonkövetési leképezés.verzió.1.1 | [Minta ER-adatmodell leképezési konfigurációja](https://download.microsoft.com/download/7/7/3/77379bdc-7b22-4cfc-9b64-a9147599f931/Performancetracemappingversion1.1.xml) |
| Teljesítmény-nyomonkövetési formátum.verzió.1.1  | [Minta ER-formátum konfigurációja](https://download.microsoft.com/download/8/6/8/868ba581-5a06-459e-b173-fb00f038b37f/Performancetraceformatversion1.1.xml)       |

### <a name="configure-er-parameters"></a>ER-paraméterek konfigurálása

Minden egyes, az alkalmazásban létrehozott ER teljesítmény-nyomonkövetést a rendszer a végrehajtási naplórekord mellékleteként tárolja. A Dokumentumkezelés (DM) keretrendszerével kezelhetők ezek a mellékletek. Az ER-paramétereket előre be kell állítania a teljesítmény-nyomkövetéshez használandó DM-dokumentumtípus meghatározásához. Az **Elektronikus jelentéskészítés** munkaterületen kattintson az **Elektronikus jelentések paraméterei** hivatkozására. Ezután az **Elektronikus jelentéskészítés paraméterei** oldalon, a **Mellékletek** lap **Egyéb** mezőjében válassza ki a teljesítmény-nyomkövetéshez használandó DM-dokumentum típusát.

![Elektronikus jelentéskészítés paraméterei lap.](./media/GER-PerfTrace-GER-Parameters-DocumentType.png)

Ahhoz, hogy elérhető legyen az **Egyebek** keresési mezőben, a DM-dokumentumtípust a következő módon kell konfigurálni a **Dokumentumtípusok** oldalon (**Szervezeti adminisztráció \> Dokumentumkezelés \>Dokumentumtípusok**):

- **Osztály:** Fájl csatolása
- **Csoport:** Fájl

![Dokumentumtípusok lapja.](./media/GER-PerfTrace-DM-DocumentType.png)

> [!NOTE]
> A kiválasztott dokumentumtípusnak az aktuális példány minden vállalatában elérhetőnek kell lennie, mivel a DM-mellékletek vállalatspecifikusak.

### <a name="configure-rcs-parameters"></a>RCS-paraméterek konfigurálása

Az ER teljesítmény-nyomkövetéseket a rendszer elemzési célból az RCS szolgáltatásba importálja az ER-formátumtervező és az ER-leképezéstervező használatával. Mivel a rendszer az ER teljesítmény-nyomkövetéseket az adott ER-formátumhoz kapcsolódó végrehajtási naplórekord mellékleteként tárolja, előre be kell állítania az RCS-paramétereket a teljesítmény-nyomkövetések csatolására használandó DM-dokumentumtípus meghatározása érdekében. A vállalat számára rendelkezésre bocsátott RCS-példányban, az **Elektronikus jelentéskészítés** munkaterületen válassza az **Elektronikus jelentéskészítés paraméterei** lehetőséget. Ezután az **Elektronikus jelentéskészítés paraméterei** oldalon, a **Mellékletek** lap **Egyéb** mezőjében válassza ki a teljesítmény-nyomkövetéshez használandó DM-dokumentum típusát.

![Elektronikus jelentéskészítés paraméterei lap az RCS szolgáltatásban.](./media/GER-PerfTrace-RCS-Parameters-DocumentType.png)

Ahhoz, hogy elérhető legyen az **Egyebek** keresési mezőben, a DM-dokumentumtípust a következő módon kell konfigurálni a **Dokumentumtípusok** oldalon (**Szervezeti adminisztráció \> Dokumentumkezelés \>Dokumentumtípusok**):

- **Osztály:** Fájl csatolása
- **Csoport:** Fájl

## <a name="design-an-er-solution"></a>ER-megoldás tervezése

Tegyük fel, hogy egy új ER-megoldást tervez, amellyel szállítói tranzakciókat bemutató új jelentést hozhat létre. Jelenleg a kiválasztott szállítóhoz tartozó tranzakciókat a **Szállítói tranzakciók** oldalon találja (lépjen a **Kötelezettségek \> Szállítók \> Minden szállító** pontra, válasszon a szállítók közül, majd a Műveleti ablaktábla **Szállító lapján**, a **Tranzakciók** csoportban válassza a **Tranzakciók** elemet). Önnek azonban az összes szállítói tranzakció megjelenítésére van szükség, ugyanabban a pillanatban, egyetlen elektronikus dokumentumban, XML formátumban. Ez a megoldás több olyan ER-konfigurációt is magában foglal, amelyek a szükséges adatmodell-, metaadat-, modell-hozzárendelési és formátum-összetevőket tartalmazzák.

1. Jelentkezzen be a vállalata részére biztosított RCS-példányba.
2. Ebben az oktatóanyagban létrehozzuk és módosítjuk a konfigurációkat a **Litware, Inc.** mintavállalatra vonatkozóan. Ezért győződjön meg róla, hogy ezt a konfigurációszolgáltatót hozzáadták az RCS-szolgáltatáshoz, és aktívként kijelölték. További útmutatásért tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.
3. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** csempét.
4. A **Konfigurációk** lapon importálja az előfeltételként az RCS-be letöltött ER-konfigurációkat, a következő sorrendben: adatmodell, metaadat, modell-hozzárendelés, formátum. Minden konfiguráció esetén hajtsa végre az alábbi lépéseket:

    1. A Műveleti ablaktáblában válassza az **Átváltás \> Betöltés XML-fájlból** elemet.
    2. A **Tallózás** gombra kattintva válassza ki a megfelelő, XML-formátumú fájlt a szükséges ER-konfigurációhoz.
    3. Válassza ki az **OK** lehetőséget.

    ![Konfigurációk oldal az RCS-ben.](./media/GER-PerfTrace-RCS-ImportedConfigurations.png)

## <a name="run-the-er-solution-to-trace-execution"></a>Az ER-megoldás futtatása a végrehajtás nyomon követéséhez

Tegyük fel, hogy befejezte az ER-megoldás első verziójának tervezését. Ezt követően tesztelni szeretné példányában, és elemezni a végrehajtás teljesítményét.

### <a name="import-an-er-configuration-from-rcs-into-finance-and-operations"></a><a id='import-configuration'></a>ER konfigurációk importálása RCS-ből a Finance and Operations-alkalmazásba

1. Jelentkezzen be az alkalmazás példányába.
2. Ebben az oktatóanyagban konfigurációkat importálunk az RCS-példányból (ahol az ER-összetevőket tervezzük) az Ön példányába (ahol teszteljük és használjuk majd őket). Ezért győződjön meg arról, hogy az összes szükséges műterméket előkészítette. További útmutatásért tekintse át az [Elektronikus jelentéskészítési (ER) konfigurációk importálása a Regulatory Configuration Service (RCS)](rcs-download-configurations.md) eljárást.
3. A következő lépések végrehajtásával importálhatja a konfigurációkat az RCS szolgáltatásból az alkalmazásba:

    1. Az **Elektronikus jelentéskészítés** munkaterületen, a **Litware, Inc.** konfigurációszolgáltató csempéjén válassza ki a **Tárházak** elemet.
    2. A **Konfigurációs tárházak** lapon válassza ki az **RCS** típusú tárházat, majd válassza a **Megnyitás** lehetőséget.
    3. A **Konfigurációk** gyorslapon válassza ki a **Teljesítmény-nyomkövetés formátuma** konfigurációt.
    4. A **Verziók** gyorslapon válassza ki a kiválasztott konfiguráció **1.1** verzióját, majd az **Importálás** lehetőséget.

    ![Konfigurációk tárháza oldal.](./media/GER-PerfTrace-GER-ImportedConfigurations.png)

Az adatmodell- és modell-hozzárendelési konfigurációk megfelelő verzióit a rendszer automatikusan importálja az importált ER-formátumkonfiguráció előfeltételeként.

### <a name="turn-on-the-er-performance-trace"></a>Az ER teljesítmény-nyomkövetésének bekapcsolása

1. Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. A **Felhasználói paraméterek** párbeszédablakban a **Végrehajtás nyomon követése** szakaszban kövesse az alábbi lépéseket:

    1. A **Végrehajtás nyomkövetésének formátuma** mezőben meghatározhatja a létrejövő teljesítmény-nyomkövetés formátumát, amelyben a végrehajtás részleteit tárolni kell az ER-formátumhoz és leképezési elemekhez:

        - **Nyomkövetési formátum hibakeresése** – akkor válassza ezt az értéket, ha azt tervezi, hogy interaktív módon olyan ER-formátumot futtat, amely rövid végrehajtási idővel rendelkezik. Ezután megkezdődik az ER-formátum végrehajtásával kapcsolatos részletek gyűjtése. Ha az érték ki van választva, akkor a teljesítmény-nyomkövetés adatokat gyűjt arról az időről, amelyet a következő műveletekre fordít:

            - Minden adatforrás futtatása a modell-hozzárendelésben, amelyet az adatok lekéréséhez behív a rendszer
            - Minden egyes formátumelem feldolgozása a létrejövő kimeneti fájlba való adatbevitel érdekében

            Ha a **Nyomkövetési formátum hibakeresése** értékét választja, az ER-művelettervezőben elemezheti a nyomkövetés tartalmát. Itt megtekintheti a nyomkövetésben említett ER-formátumot vagy leképezési elemeket.

        - **Összesített nyomkövetési formátum** – akkor válassza ezt az értéket, ha azt tervezi, hogy interaktív módon olyan ER-formátumot futtat, amely hosszú végrehajtási idővel rendelkezik kötegelt módban. Ezután megkezdődik az ER-formátum végrehajtásával kapcsolatos összesített részletek gyűjtése. Ha az érték ki van választva, akkor a teljesítmény-nyomkövetés adatokat gyűjt arról az időről, amelyet a következő műveletekre fordít:

            - Minden adatforrás futtatása a modell-hozzárendelésben, amelyet az adatok lekéréséhez behív a rendszer
            - Minden adatforrás futtatása abban a formátumleképezésben, amelyet az adatok lekéréséhez meghív a rendszer
            - Minden egyes formátumelem feldolgozása a létrejövő kimeneti fájlba való adatbevitel érdekében

            Az **Összesített nyomkövetési formátum** értéke a Microsoft Dynamics 365 Finance 10.0.20-as és újabb verzióiban érhető el.

            Az ER-formátumtervezőben és az ER-modell leképezéstervezőjében megtekinthető a teljes végrehajtási idő egy adott összetevőhöz. Ezenkívül a nyomkövetés részletes adatokat tartalmaz a végrehajtásról, például a végrehajtások számát, valamint az egyes végrehajtások minimális és maximális idejéről.

            > [!NOTE]
            > Ezt a nyomkövetést a rendszer a nyomon követett összetevők elérési útja alapján gyűjti össze. Emiatt előfordulhat, hogy a statisztika helytelen, ha egyetlen szülőösszetevő több, név nélküli gyermekösszetevőt tartalmaz, vagy ha több gyermekösszetevőnek ugyanaz a neve.

    2. Ha a következő beállításokat **Igen** értékre állítja, akkor specifikus adatokat gyűjthet az ER modell-hozzárendelés és az ER-formátum összetevőinek végrehajtásáról:

        - **Lekérdezési statisztikák gyűjtése** – Ha ez a beállítás be van kapcsolva, a teljesítmény-nyomkövetés a következő adatokat fogja gyűjteni:

            - Az adatforrások által végzett adatbázishívások száma
            - Az ismétlődő hívások száma az adatbázisban
            - Az SQL-utasítások részleteit, amelyekkel az adatbázishívásokat végezték

        - **Gyorsítótárazás hozzáférésének nyomon követése** – Ha ez a beállítás be van kapcsolva, a teljesítmény-nyomkövetés adatokat gyűjt az ER modell-hozzárendelés gyorsítótár-használatáról.
        - **Nyomkövetési adatok hozzáférése** – Ha ez a beállítás be van kapcsolva, a teljesítmény-nyomkövetés a rekordlista típusú végrehajtott adatforrásokhoz tartozó, adatbázisba intézett hívások számával kapcsolatos adatokat gyűjt.
        - **Nyomkövetési lista felsorolása** – Ha ez a beállítás be van kapcsolva, a teljesítmény-nyomkövetés a rekordlista típusú végrehajtott adatforrásokból lekért rekordok számával kapcsolatos adatokat gyűjt.

    > [!NOTE]
    > A **Felhasználói paraméterek** párbeszédpanel paraméterei a felhasználóra és az aktuális vállalatra jellemzőek.

    ![A Felhasználói paraméterek párbeszédablak.](./media/GER-PerfTrace-GER-UserParameters.png)

### <a name="run-the-er-format"></a><a id='run-format'></a>Az ER-formátum futtatása

1. Válassza a **DEMF** vállalatot.
2. Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.
3. A **Konfigurációk** oldalon található konfigurációs fában válassza ki a **Teljesítmény-nyomkövetés formátuma** elemet.
4. A Műveleti ablaktáblán kattintson a **Futtatás** elemre.

Figyelje meg, hogy a létrejövő forrásfájl hat szállító 265 tranzakcióját jeleníti meg.

## <a name="review-the-execution-trace"></a>A végrehajtás nyomkövetésének áttekintése

### <a name="export-the-generated-trace-from-the-application"></a><a id='export-trace'></a>A létrejövő nyomkövetés exportálása az alkalmazásból

A teljesítmény-nyomkövetéseket leválaszthatja az ER forrásformátumából, és szerializálhatja egy külső zip-fájlba.

1. Lépjen a következőre: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk hibakeresési naplói**.
2. Az **Elektronikus jelentéskészítés futtatási naplói** oldalon a bal oldali panelen, a **Konfiguráció neve** mezőben válassza a **Teljesítmény-nyomkövetés formátuma** lehetőséget, amellyel megtalálhatja a **Teljesítmény-nyomkövetés formátuma** végrehajtásával létrehozott naplórekordokat.
3. Válassza a **Mellékletek** gombot (kapocs jel) az oldal jobb felső sarkában, vagy nyomja meg a **Ctrl+Shift+A** billentyűkombinációt.

    ![Mellékletek gomb az Elektronikus jelentéskészítés futtatási naplói oldalon.](./media/GER-PerfTrace-GER-DebugLog.png)

4. Az **Elektronikus jelentéskészítés futtatási naplói – Mellékletek** oldalon a Műveleti ablaktáblán válassza a **Megnyitás** lehetőséget a teljesítmény-nyomkövetés zip-fájlként való lehívásához és helyi tárolásához.

    ![Elektronikus jelentéskészítés futtatási naplók mellékletei.](./media/GER-PerfTrace-GER-DebugLog-AttachedTrace.png)

> [!NOTE]
> A létrehozott nyomkövetés referenciával rendelkezik a kiindulási ER-jelentésre egy egyedi, csak **GUID** formátumban létező jelentésazonosítón keresztül. A formátum verziószámát a rendszer nem veszi figyelembe.

Megfigyelhető, hogy végrehajtott ER-formátumhoz létrehozott teljesítmény-nyomkövetés és az ER-modell-hozzárendelés közti társítás a használt gyökérszintű leírón és a közös adatmodellen alapul. A formátum és a modell-hozzárendelés verziószámát a rendszer nem veszi figyelembe. Az **Alapértelmezett a modell-hozzárendeléshez** jelölő modell-hozzárendeléshez tartozó beállítását szintén figyelmen kívül hagyja.

### <a name="import-the-generated-trace-into-rcs"></a><a id='import-trace'></a>A létrejövő nyomkövetés importálása az RCS szolgáltatásba

1. Az RCS szolgáltatásban az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** csempét.
2. A **Konfigurációk** lapon található konfigurációs fában bontsa ki a **Teljesítmény-nyomkövetési modell** elemet, és válassza a **Teljesítmény-nyomkövetés formátuma** lehetőséget.
3. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
4. A **Formátumtervező** lapon a Műveleti ablaktáblában válassza ki a **Teljesítmény-nyomkövetés** lehetőséget.
5. A **Teljesítmény-nyomkövetési eredmény beállításai** párbeszédpanelen válassza a **Teljesítmény-nyomkövetés importálása** elemet.
6. Válassza a **Tallózás** lehetőséget a korábban exportált zip fájl kiválasztásához.
7. Válassza ki az **OK** lehetőséget.

    ![A teljesítmény-nyomkövetési eredmények beállításai párbeszédpanel az RCS szolgáltatásban.](./media/GER-PerfTrace-RCS-ImportedPerfTrace.png)

### <a name="use-the-performance-trace-for-analysis-in-rcs--format-execution"></a>A teljesítmény-nyomkövetés alkalmazása elemzési célokra az RCS szolgáltatásban – Formátum-végrehajtás

1. Az RCS szolgáltatás **Formátumtervező** lapján válassza a **Kibontás/összecsukás** elemre az összes formátumelem tartalmának kibontásához.

    Megfigyelheti, hogy az aktuális formátum bizonyos elemeinél további információk is megjelennek:

    - Az adatok a létrejövő kimeneti fájlba történő bevitelére fordított tényleges idő a formátumelem használatával
    - Ugyanez az időtartam a teljes kimeneti fájl létrehozására fordított összes idő százalékaként kifejezve

    ![Formátumtervező oldal az RCS szolgáltatásban.](./media/GER-PerfTrace-RCS-TraceInfoInFormat.png)

2. Zárja be a **Formátumtervező** lapot.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><a id='use-trace'></a>A teljesítmény-nyomkövetés alkalmazása elemzési célokra az RCS szolgáltatásban – Modell-hozzárendelés

1. Az RCS szolgáltatásban a **Konfigurációk** oldalon található konfigurációs fában válassza ki a **Teljesítmény-nyomkövetés hozzárendelése** elemet.
2. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
3. Válassza a **Tervező** lehetőséget.
4. A **Modell-hozzárendelési tervező** lapon a Műveleti ablaktáblában válassza ki a **Teljesítmény-nyomkövetés** lehetőséget.
5. Válassza ki a korábban importált nyomkövetést.
6. Válassza ki az **OK** lehetőséget.

Megfigyelheti, hogy az aktuális modell-hozzárendelés bizonyos adatforráselemeihez új információk jelennek meg:

- Az adatforrás által az adatok lekérésére fordított tényleges idő
- Ugyanez az időtartam a teljes modell-hozzárendelés lefuttatására fordított összes idő százalékaként kifejezve

Megfigyelheti, hogy az ER tájékoztatja Önt arról, hogy az aktuális modell-hozzárendelés megkettőzi az adatbázis-kérelmeket a VendTable/\<Kapcsolatok/VendTrans.VendTable\_AccountNum adatforrás futása során. Ez az ismétlődés azért fordul elő, mert a szállítói tranzakciók listájának lekérése minden ismétlődő szállítói rekordnál két alkalommal történik:

- Az egyik lehívás annak érdekében történik, hogy az egyes tranzakciók részleteit bevigyék az adatmodellbe a konfigurált kötések alapján.
- Egy lehívás pedig annak érdekében történik, hogy a szállítónkénti tranzakciók kiszámított mennyiségét bevigyék az adatmodellbe.

![Ismétlődő adatbázis-kérelmekkel kapcsolatos üzenet a Modell-hozzárendelési tervező oldalon az RCS szolgáltatásban.](./media/GER-PerfTrace-RCS-TraceInfoInMapping1.png)

A **\[Q:530\]** érték azt jelzi, hogy a VendTrans táblát a rendszer 530 alkalommal hívta le annak érdekében, hogy egy rekordot visszaadjon az adott táblából a VendTable/\<Kapcsolatok/VendTrans.VendTable\_AccountNum adatforrásba. Az **\[530\]** érték azt jelzik, hogy a VendTable/\<Kapcsolatok/VendTrans.VendTable\_AccountNum adatforrást 530 alkalommal hívta le a rendszer annak érdekében, hogy egy rekordot visszaadjon az adott adatforrásból, és az ebből származó részletes adatokat bevigye az adatmodellbe.

Javasoljuk a gyorsítótárazás használatát a VendTable/\<Relations/VendTrans.VendTable\_AccountNum adatforráshoz a lehívások számának csökkentése érdekében, amelyek a 265 tranzakció adatainak lehívásához szükséges, valamint a modell-hozzzárendelés teljesítményének javítása érdekében.

A LedgerTransTypeList-adatforrásra vonatkozó lehívások számának csökkentéséhez is hasznos lehet. Ezzel az adatforrással lehetséges a **LedgerTransType** felsorolás minden egyes értékének saját címkéjéhez társítása. Az adatforrás használatával megkeresheti a megfelelő címkét, és megadhatja az egyes szállítói tranzakciókhoz tartozó adatmodellben. Az adatforráshoz intézett lehívások jelenlegi száma (9027) elég magas a 265 tranzakcióra vonatkoztatva.

![Modell-hozzárendelési tervező lapja az RCS szolgáltatásban, amely 9027 lehívást jelez az adatforráshoz.](./media/GER-PerfTrace-RCS-TraceInfoInMapping1a.png)

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>A modell-hozzárendelés javítása a végrehajtási nyomkövetésből származó információk alapján

### <a name="modify-the-logic-of-the-model-mapping"></a>A modell-hozzárendelés logikájának módosítása

1. Hajtsa végre a következő lépéseket a gyorsítótárazás használatához az adatbázishoz intézett ismétlődő hívások megakadályozása érdekében:

    1. Az RCS **Modell-hozzárendelési tervező** oldalán az **Adatforrások** panelen válassza ki a **VendTable** elemet.
    2. Válassza a **Gyorsítótárazás** lehetőséget.
    3. Bontsa ki a **VendTable** elemet, bontsa ki a VendTable adatforráshoz tartozó egy a többhöz kapcsolatos listáját (a **\<Kapcsolatok** elemet), és válassza a **VendTrans.VendTable\_AccountNum** elemet.
    4. Válassza a **Gyorsítótárazás** lehetőséget.

    ![Gyorsítótár-beállítás az ismétlődő lehívások megelőzése érdekében.](./media/GER-PerfTrace-RCS-ChangeMapping-Cache.png)

2. Hajtsa végre az alábbi lépéseket, hogy a LedgerTransTypeList-adatforrás a VendTable-adatforrás hatókörébe kerüljön:

    1. Az **Adatforrástípusok** panelen bontsa ki a **Funkciók** elemet, és válassza a **Számított mező** elemet.
    2. Az **Adatforrások** panelen válassza a **VendTable** elemet.
    3. Válassza a **Hozzáadás** lehetőséget.
    4. A **Név** mezőbe írja be a **\$TransType** szót.
    5. Válassza a **Képlet szerkesztése** elemet.
    6. A **Képlet** mezőbe írja be a következőt: **LedgerTransTypeList**.
    7. Válassza a **Mentés** lehetőséget.
    8. Zárja be a **Képletszerkesztő** lapot.
    9. Kattintson az **OK** gombra.

3. Hajtsa végre a következő lépéseket a **\$TransType** mező gyorsítótárazásának végrehajtásához:

    1. Válassza ki a **LedgerTransTypeList** elemet.
    2. Válassza a **Gyorsítótárazás** lehetőséget.
    3. Válassza ki a **a VendTable.\$TransType** elemet.
    4. Válassza a **Gyorsítótárazás** lehetőséget.

    ![A $TransType mező gyorsítótárazásának beállítása.](./media/GER-PerfTrace-RCS-ChangeMapping-Cache2.png)

4. Hajtsa végre az alábbi lépéseket a **\$TransTypeRecord** mező módosításához, hogy az a gyorsítótárazott **\$TransType** mezőt használja:

    1. Az **Adatforrások** panelen bontsa ki a **VendTable** elemet, bontsa ki a **\<Kapcsolatok** elemet, bontsa ki a **VendTrans.VendTable\_AccountNum** elemet, majd válassza a **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord** lehetőséget.
    2. Válassza ki a **Szerkesztés** opciót.
    3. Válassza a **Képlet szerkesztése** elemet.
    4. A **Képlet** mezőben keresse meg a következő kifejezést:

        FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))

    5. A **Képlet** mezőben adja meg a következő kifejezést:

        FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).

    6. Válassza a **Mentés** lehetőséget.
    7. Zárja be a **Képletszerkesztő** lapot.
    8. Válassza ki az **OK** lehetőséget.

5. Válassza a **Mentés** lehetőséget.
6. Zárja be a **Modell-hozzárendelési tervező** lapot.
7. Zárja be a **Modell-hozzárendelések** lapot.

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>Az ER-modell-hozzárendelés módosított verziójának elvégzése

1. Az RCS **Konfigurációk** lapjának **Verziók** gyorslapján válassza ki az **1.2**-es verziót a **Teljesítmény-nyomkövetés** konfigurációhoz.
2. Válassza az **Állapot módosítása** lehetőséget.
3. Válassza a **Kész** lehetőséget.

### <a name="import-the-modified-er-model-mapping-configuration-from-rcs-into-the-application"></a>A módosított ER-modell-hozzárendelési konfiguráció importálása az RCS szolgáltatásból az alkalmazásba

Ismételje meg a jelen témakörben korábban ismertetett, [ER-konfiguráció importálása az RCS szolgáltatásból a Finance and Operations-modulba](#import-configuration) című szakasz lépéseit a **Teljesítmény-nyomkövetés** hozzárendelése konfiguráció 1.2-es verziójának importálásához.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>A módosított ER-megoldás futtatása a végrehajtás nyomon követéséhez

### <a name="run-the-er-format"></a>Az ER-formátum futtatása

Ismételje meg a jelen témakörben korábban ismertetett, [ER-formátum futtatása](#run-format) szakasz lépéseit az új teljesítmény-nyomkövetés létrehozásához.

## <a name="work-with-the-execution-trace"></a>Munka végrehajtás nyomon követésével

### <a name="export-the-generated-trace-from-the-application"></a>A létrejövő nyomkövetés exportálása az alkalmazásból

Ismételje meg a jelen témakörben korábban ismertetett, [A létrejövő nyomkövetés exportálása az alkalmazásból](#export-trace) szakasz lépéseit az új teljesítmény-nyomkövetés helyi mentéséhez.

### <a name="import-the-generated-trace-into-rcs"></a>A létrejövő nyomkövetés importálása az RCS szolgáltatásba

Ismételje meg a jelen témakörben korábban ismertetett, [A létrejövő nyomkövetés importálása az RCS szolgáltatásba](#import-trace) szakasz lépéseit az új teljesítmény-nyomkövetés RCS szolgáltatásba történő importálásához.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a>A teljesítmény-nyomkövetés alkalmazása elemzési célokra az RCS szolgáltatásban – Modell-hozzárendelés

Ismételje meg a jelen témakörben korábban ismertetett, [AA teljesítmény-nyomkövetés alkalmazása elemzési célokra az RCS szolgáltatásban – Modell-hozzárendelés](#use-trace) című szakasz lépéseit a legutóbbi teljesítmény-nyomkövetés elemzéséhez.

Megfigyelheti, hogy az Ön által a modell-hozzárendelésen végzett kiigazításokkal megszüntette az adatbázisba intézett ismétlődő lekérdezéseket. Az adott modellhozzárendeléshez tartozó, adatbázistáblákba és adatforrásokba küldött lehívások száma is csökkent. Ezáltal a teljes ER-megoldás teljesítménye javult.

![A VendTable adatforrás információinak nyomon követése a Modell-hozzárendelési tervező oldalon az RCS szolgáltatásban.](./media/GER-PerfTrace-RCS-TraceInfoInMapping2.png)

A nyomkövetési adatok között szereplő **\[12\]** érték azt jelzi, hogy az adatforrást 12 alkalommal hívták le. A **\[Q:6\]** érték azt jelzi, hogy hat hívást fordított le a rendszer a VendTable táblába irányuló adatbázishívásként. A **\[C:6\]** érték azt jelzik, hogy az adatbázisból lehívott rekordokat gyorsítótárazták, és 6 további hívást a gyorsítótár használatával dolgoztak fel.

Megfigyelheti, hogy a LedgerTransTypeList adatforrásba indított hívások száma 9027-ről 240-re csökkent.

![A LedgerTransTypeList adatforrás információinak nyomon követése a Modell-hozzárendelési tervező oldalon az RCS szolgáltatásban.](./media/GER-PerfTrace-RCS-TraceInfoInMapping2a.png)

## <a name="review-the-execution-trace-in-the-application"></a>A végrehajtási nyomkövetés áttekintése az alkalmazásban

Az RCS szolgáltatás mellett az egyes verziók kínálhatnak ER-keretrendszer tervezői élményére vonatkozó lehetőségeket. Ezek a verziók rendelkeznek a **Tervezői mód engedélyezése** lehetőséggel, amelyet be lehet kapcsolni. Ez a beállítás az **Elektronikus jelentéskészítés paraméterei** oldal **Általános** lapján található, amelyet az **Elektronikus jelentéskészítés** munkaterületről nyithat meg.

![A tervezési mód lehetőség bekapcsolása az Elektronikus jelentéskészítés paraméterei oldalon.](./media/GER-PerfTrace-GER-Parameters-DesignMode.png)

Ha ezen verziók egyikét használja, akkor közvetlenül az alkalmazásban elemezheti a létrehozott teljesítmény-nyomkövetés részleteit. Ezeket nem kell exportálnia az alkalmazásból, és importálnia az RCS szolgáltatásba.

## <a name="review-the-execution-trace-by-using-external-tools"></a>A végrehajtási nyomkövetés áttekintése külső eszközök használatával

### <a name="configure-user-parameters"></a>Felhasználói paraméterek konfigurálása

1. Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. A **Felhasználói paraméterek** párbeszédpanel **Végrehajtás nyomkövetése** szakaszának **Végrehajtási nyomkövetés formátuma** mezőjében válassza a **PerfView XML** elemet.

### <a name="run-the-er-format"></a>Az ER-formátum futtatása

Ismételje meg a jelen témakörben korábban ismertetett, [ER-formátum futtatása](#run-format) szakasz lépéseit az új teljesítmény-nyomkövetés létrehozásához.

Megfigyelheti, hogy az internetböngésző felajánlja a zip-fájl letöltését. Ez a fájl a teljesítmény-nyomkövetést PerfView formátumban tartalmazza. Ezután használhatja a PerfView teljesítményelemzési eszközt az ER-formátum végrehajtás részleteinek elemzésére.

![Teljesítmény-nyomkövetési adatok PerfView formátumban.](./media/GER-PerfTrace2-PerfViewTrace1.PNG)

## <a name="use-external-tools-to-review-an-execution-trace-that-includes-database-queries"></a>Külső eszközök használata az adatbázis-lekérdezéseket tartalmazó végrehajtási nyomon követés áttekintéséhez

Az elektronikus jelentéskészítési keretrendszer fejlesztéseinek köszönhetően a teljesítmény PerfView formátumában létrehozott nyomon követése több részletet biztosít az ER-formátum végrehajtásáról. A Microsoft Dynamics 365 for Finance and Operations 10.0.4-es verziójában (2019. július) ez a nyomon követés az alkalmazás-adatbázishoz végrehajtott SQL-lekérdezések részleteire is kiterjedhet.

### <a name="configure-user-parameters"></a>Felhasználói paraméterek konfigurálása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. A **Felhasználói paraméterek** párbeszédpanel **Végrehajtás nyomon követése** szakaszában állítsa be az alábbi paramétereket:

    - A **Végrehajtási nyomkövetés formátuma** mezőben válassza a **PerfView XML** értéket.
    - A **Lekérdezési statisztikák gyűjtése** beállításnál adja meg az **Igen** értéket.
    - A **Lekérdezés nyomon követése** beállításhoz adja meg az **Igen** lehetőséget.

    ![Végrehajtási nyomkövetési szakasz, Felhasználói paraméterek párbeszédpanel.](./media/GER-PerfTrace2-GER-UserParameters.PNG)

### <a name="run-the-er-format"></a>Az ER-formátum futtatása

Ismételje meg a jelen témakörben korábban ismertetett, [ER-formátum futtatása](#run-format) szakasz lépéseit az új teljesítmény-nyomkövetés létrehozásához.

Megfigyelheti, hogy az internetböngésző felajánlja a zip-fájl letöltését. Ez a fájl a teljesítmény-nyomkövetést PerfView formátumban tartalmazza. Ezután használhatja a PerfView teljesítményelemzési eszközt az ER-formátum végrehajtás részleteinek elemzésére. Ez a nyomon követés már az SQL-adatbázis ER-formátum végrehajtása alatti hozzáférés részleteire is vonatkozik.

![A végrehajtott ER-formátum információinak nyomon követése a PerfView szolgáltatásban.](./media/GER-PerfTrace2-PerfViewTrace2.PNG)

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentések áttekintése](general-electronic-reporting.md)
- [Az ER megoldások teljesítményének javítása a paraméterek SZÁMÍTOTT MEZŐ-adatforrások hozzáadásával](er-calculated-field-ds-performance.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
