---
title: Igény-előrejelzési beállítások
description: Ez a témakör az igény-előrejelzés használata előtt elvégzendő telepítési feladatokat mutatja be.
author: t-benebo
ms.date: 11/23/2021
ms.topic: article
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3b52b970a8040dcba5a1fc59d297dc9ce1a3c53
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/23/2022
ms.locfileid: "8470009"
---
# <a name="demand-forecasting-setup"></a>Igény-előrejelzési beállítások

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet beállítani az igény-előrejelzést.  

## <a name="item-allocation-keys"></a>Cikkfelosztási kulcsok

A cikkfelosztási kulcsok cikkcsoportokat hoznak létre. Egy cikkről, valamint annak különböző dimenzióiról csak akkor készül igény-előrejelzés, ha az része egy cikkfelosztási kulcsnak. Ennek a szabálynak a segítségével nagy számú cikkcsoportot csoportosíthat, így gyorsabban létre lehet hozva az igény-előrejelzéseket. Az előrejelzések csak a korábbi adatok alapján lesznek létrehozva.

Egy cikk és annak különböző dimenziói csak egy cikkfelosztási kulcs alá tartozhatnak, ha a cikkfelosztási kulcs az előrejelzés létrehozása során használatos.

A következő lépések szerint hozhatja létre a cikkfelosztási kulcsokat, és raktározási egységet adhat hozzá a kulcsokhoz.

1. Lépjen az **Alaptervezés \> Beállítása \> Igény-előrejelzés \> Cikkhozzárendelési-kulcsok** részre.
1. Válasszon egy cikkfelosztási kulcsot a listaablakban, **vagy** az Új elemet a munkaablakban, ha újat is létre kell hoznia. Az új vagy kiválasztott kulcs fejlécében állítsa be a következő mezőket:

    - **Cikkfelosztási** kulcs – adja meg a kulcs egyedi nevét.
    - **Név** – adja meg a kulcs jól leíró nevét.

1. A következő lépések valamelyikét követve adhat hozzá cikkeket a kijelölt cikkfelosztási kulcshoz, illetve eltávolíthat cikkeket:

    - A Cikkfelosztás **gyorspultban** az **·** **eszköztár** Új és Törlés gombjaival lehet szükség szerint cikkeket hozzáadni vagy eltávolítani. Minden sorhoz válassza ki a cikkszámot, majd szükség szerint rendeljen dimenzióértékeket a többi oszlophoz. Válassza **a Dimenziók** megjelenítése lehetőséget az eszköztáron a rácsban megjelenített dimenzióoszlopok halmazának a módosításahoz. (Az érték a következőben: **Igény-előrejelzések** generálása esetén a program figyelmen kívül hagyja a Százalék oszlopot.)
    - Ha nagy számú elemet szeretne hozzáadni a kulcshoz, **a** munkaablakBan válassza a Cikkek hozzárendelése lehetőséget egy olyan lap megnyitásához, ahol a kiválasztott kulcshoz több elemet is meg lehet találni, illetve hozzá lehet rendelni őket.

> [!IMPORTANT]
> Ügyeljen arra, hogy az egyes cikkfelosztási kulcsokban csak a fontos cikkek szerepeljenek. A felesleges cikkek pluszköltséggel járhatnak a Microsoft Azure Machine Learning használata során.

## <a name="intercompany-planning-groups"></a>Vállalatközi tervezőcsoportok

Az igény-előrejelzés több vállalatot is képes generálni. A Dynamics 365 Supply Chain Management vállalatok, amelyek együtt vannak tervezve, ugyanannak a vállalatközi tervezőcsoportnak abe vannak csoportosítva. Annak megadásához, hogy vállalatonként mely cikkfelosztási kulcsokat kell figyelembe venni az igény-előrejelzésben, társítsa a cikkfelosztási kulcsot a vállalatközi tervezési csoport taghoz.

> [!IMPORTANT]
> A tervezési optimalizálás jelenleg nem támogatja a vállalatközi tervezőcsoportokat. Ha a Tervezési optimalizálást használó vállalatközi tervezéshez alaptervezési kötegelt feladatokat kell beállítania, amelyek minden érintett vállalat alaptervét tartalmazzák.

A vállalatközi tervezőcsoportok beállítását a következő lépések szerint hajtsa végre.

1. Ugrás az Alaptervezés **beállítása vállalatközi \> tervezési csoportokhoz \>**.
1. Válasszon egy tervezési csoportot a listaablakban, **vagy** az Új gombra kattintva hozzon létre egy újat a munkaablakban. Az új vagy kiválasztott csoport fejlécében állítsa be a következő mezőket:

    - **Név** – adja meg a tervezési csoport egyedi nevét.
    - **Leírás** – adja meg a tervezési csoport rövid leírását.

1. A vállalatközi **tervezési** csoport tagjainak gyorstábláján, az eszköztár gombjaival adjon hozzá egy sort minden olyan vállalathoz (jogi személyhez), amely a csoportnak része kell legyen. Az egyes sorokhoz állítsa be a következő mezőket:

    - **Jogi személy** – a kijelölt csoportban tag vállalat (jogi személy) nevének kiválasztása.
    - **Ütemezési sorrend** – a vállalat egyéb vállalatokhoz viszonyított sorrendjének hozzárendelése. Az alacsony értékek feldolgozása először. Ez a rendelés akkor lehet fontos, ha egy vállalat iránti igény más vállalatokat is befolyásol. Ilyen esetben az igényt biztosító vállalatot kell utoljára feldolgozni.
    - **Alapterv** – az aktuális vállalatra vonatkozó alapterv kiválasztása.
    - **Automatikus másolás statikus tervbe** – jelölje be ezt a jelölőnégyzetet a terv eredményének statikus tervbe való másoláshoz.
    - **Automatikus másolás dinamikus tervbe** – jelölje be ezt a jelölőnégyzetet a terv eredményének a dinamikus tervbe való másoláshoz.

1. Alapértelmezés szerint, ha nincsenek cikkfelosztási kulcsok hozzárendelve a vállalatközi tervezési csoport tagjaihoz, az igény-előrejelzés az összes cikk összes cikkfelosztási kulcsához készül, az összes vállalaton belül. A vállalatokra és cikkfelosztási kulcsokra vonatkozó további szűrési beállítások a Statisztikai **kiinduló** előrejelzés létrehozása párbeszédpanelen érhetők el (**Alaptervezés \> előrejelzése \> igény-előrejelzés \> statisztikai kiinduló előrejelzés generálása**). Ha a kiválasztott vállalatközi tervezőcsoportban cikkfelosztási kulcsokat szeretne hozzárendelni egy vállalathoz, jelölje ki a vállalatot, **·** **majd** az eszköztár Cikkfelosztási kulcsait jelölje ki a Vállalatközi tervezési csoport tagjai gyorstáblában.

> [!IMPORTANT]
> Ügyeljen arra, hogy csak a megfelelő cikkfelosztási kulcsokat tartalmazza az egyes vállalatközi tervezési csoportokban. A szükségtelen cikkek megnövelik a költségeket az Azure-számítógép-tanulás használata miatt.

## <a name="set-up-demand-forecasting-parameters"></a><a name="parameters"></a> Igény-előrejelzési paraméterek beállítása

Az igény-előrejelzési **paraméterek** lapon több olyan beállítás is beállítható, amelyek az igény-előrejelzés működését szabályozják a rendszerben.

### <a name="open-the-demand-forecasting-parameters-page"></a>Az Igény-előrejelzési paraméterek lap megnyitása

Az igény-előrejelzési paraméterek beállításához **kattintson az Alaptervezés \> beállítása \> igény-előrejelzési \> igény-előrejelzési paramétereire**. Mivel az igény-előrejelzés működése vállalatközi, ezért a telepítse globális. Más szóval az összes jogi személyre (vállalatra) vonatkozik.

### <a name="general-settings"></a>Általános beállítások

Az Igény-előrejelzési **paraméterek** **lap** Általános lapján adhatja meg az igény-előrejelzés általános beállításait.

#### <a name="demand-forecast-unit"></a>Igény-előrejelzés egysége

Az igény-előrejelzés az előrejelzés során mennyiségeket használ. Emiatt azt, hogy a mennyiség milyen egységben legyen megadva, specifikálni kell az **Igény-előrejelzés egysége** mezőben. Ez a mező azt az egységet határozza meg, amely az egyes termékek szokásos készletegységétől függetlenül az összes igény-előrejelzésben használatos lesz. A konzisztens előrejelzési egység használatával biztos lehet abban, hogy az összesítésnek és a százalékos elosztásnak van értelme. További információkért az összesítésről és százalékeloszlásról az alábbi oldalon olvasható: [Manuális módosítások a kiinduló előrejelzésben](manual-adjustments-baseline-forecast.md).

Az igény-előrejelzésben foglalt átalakítási egységekhez használt minden egyes mértékegységnél ellenőrizze, hogy van-e átváltási szabály a kiválasztott mértékegységhez és az általános előrejelzési mértékegységhez. Előrejelzés generálása során naplózza a program azon cikkek listáját, amelyek nem tartalmaznak mértékegység-átváltási beállításokat. Ezért könnyen kijavíthatja a beállításokat. További tájékoztatás a mértékegységekkel és az átváltásukról: [Mértékegységek kezelése](../pim/tasks/manage-unit-measure.md).

#### <a name="transaction-types"></a>Tranzakciótípusok

A Tranzakciótípusok gyorsjelentés **mezőivel** kiválaszthatja azokat a tranzakciótípusokat, amelyek a statisztikai kiinduló előrejelzés generálása során használatosak.

Az igény-előrejelzés mind a függő igények, mind a független igények előrejelzésre használható. Ha **például** *csak* az Értékesítési rendelés beállítás van megadva Igen beállításra, és az igény-előrejelzéshez figyelembe venni kívánt valamennyi cikk eladott cikk, akkor a rendszer független igényt számít. Azonban fontos alösszetevőket lehet a cikkfelosztási kulcshoz adni. Ezek szerepelnek az igény-előrejelzésben. Ebben az esetben, ha **a** Termelési sor beállítása *Igen*, a rendszer kiszámít egy függő előrejelzést.

A cikkfelosztási kulcsok lap **használatával felülbírálhatja egy vagy több cikkfelosztási kulcs tranzakciótípusait** . Ez a lap hasonló mezőket biztosít.

#### <a name="choose-how-to-create-the-baseline-forecast"></a>A kiinduló előrejelzés létrehozási mikéntének kiválasztása

Az **Előrejelzés-generálás stratégia** mezőben kiválaszthatja a kiinduló előrejelzés létrehozásához használt módszert. Három módszer áll rendelkezésre:

- *Korábbi igény átmásolása* – előrejelzések létrehozása az előzményadatok másolása alapján.
- *Azure-számítógép oktatási szolgáltatás* – az Azure gépi oktatási szolgáltatást használó előrejelzési modell használata. Az Azure-számítógép oktatási szolgáltatás az Azure rendszer aktuális gépi oktatási megoldása. Ezért javasoljuk, hogy előrejelzési modell használata esetén használja.
- *Azure-gépi tanulás* – Az Azure Machine Learning Studio (teljes) használatát használó előrejelzési modell használata. Az Azure Machine Learning Studio (előfizetés) elavult, hamarosan el lesz távolítva az Azure szolgáltatásból. Ezért javasoljuk, *hogy az Igény-előrejelzés első alkalommal való beállítása esetén válassza az Azure* gépi oktatási szolgáltatást. Ha jelenleg az Azure Machine Learning Studio (a következőt) használja, akkor a lehető leghamarabb át kell váltania az Azure gépi oktatási szolgáltatásra.

A Cikkfelosztási **kulcsok lapon felülbírálhatja egy vagy több cikkfelosztási kulcs előrejelzés-generálási** módszerét. Ez a lap hasonló mezőket biztosít.

#### <a name="override-default-forecast-algorithm-parameters-globally"></a>Az előrejelzési algoritmus alapértelmezett paramétereinek globális felülbírálása

Az előrejelzés alapértelmezett algoritmusparaméterei és értékei az Igény-előrejelzési **paraméterek** lapon vannak hozzárendelve (**Alaptervezés – \> Igény-előrejelzési \>\> igény-előrejelzési paraméterek**). Globálisan azonban **felülbírálhatja** **·** **őket az Igény-előrejelzési paraméterek lap Általános lapján, az Előrejelzés algoritmusparaméterek gyorslapján.** (Adott felosztási kulcsokra vonatkozó beállításokat a <a0/<a0/<a2/<a2/ **<a Cikkfelosztási kulcsok** lap az Igény-előrejelzési **paraméterek lapon** .)

Az eszköztár **Hozzáadás** és **eltávolítás** gombjaival lehet létrehozni a paraméter-felülbírálások kötelező gyűjteményét. A listában mindegyik paraméterhez válasszon ki egy értéket a **Név** mezőben, **majd adjon meg egy megfelelő értéket az Érték mezőben**. Az itt nem látható **paraméterek az igény-előrejelzési paraméterek lapon megadott beállításokból veik át az értékeiket**. A normál paraméterkészlet [használatával és a paraméterek értékeinek kiválasztásával kapcsolatos további tudnivalókat lásd az Igény-előrejelzési modellek alapértelmezett paraméterei és értékei című](#model-parameters) részében.

### <a name="set-forecast-dimensions"></a>Előrejelzési dimenziók beállítása

Az előrejelzési dimenzió az előrejelzés részletességi szintjét jelzi. A vállalat, a telephely és a cikkfelosztási kulcs kötelező előrejelzési dimenzió. Előrejelzéseket a raktár, a készletállapot, a vevőcsoport, a vevői számla, az ország/régió, az állam és/vagy cikk szintjén, valamint a cikkdimenziók minden szintjén elő lehet hozni. Az Igény-előrejelzési **paraméterek** **lapon** található Előrejelzési dimenziók lapon kiválaszthatja az igény-előrejelzés generálása során használt előrejelzési dimenziókat.

Az igény-előrejelzéshez használt dimenziók listájához bármikor hozzáadhat előrejelzési dimenziókat. A listából, igény szerint, el lehet távolítani előrejelzési dimenziókat. Azonban a manuális módosítások elvesznek, ha hozzáad vagy eltávolít egy előrejelzési dimenziót.

### <a name="set-up-overrides-for-specific-item-allocation-keys"></a>Adott cikkfelosztási kulcsok felülbírálásának beállítása

Nem minden cikk dolgozik ugyanúgy az igény-előrejelzési szempontból. Ennek megfelelően felosztási kulcsspecifikus felülbírálásokat lehet létrehozni az **Általános** lapon megadott legtöbb beállításhoz. Kivétel az igény-előrejelzés egysége. A következő lépések szerint állíthatja be egy adott cikkfelosztási kulcs felülbírálását.

1. Az Igény-előrejelzési **·** **paraméterek** lapon, a Cikkfelosztási kulcsok lapon az eszköztár gombjaival adhat hozzá cikkfelosztási kulcsokat a bal oldali rácshoz, illetve igény szerint távolíthatja el azokat. Ezután válassza ki azt a felosztási kulcsot, amely számára be szeretné állítani a felülbírálásokat.
1. A Tranzakciótípusok **gyorsbillentyűn** engedélyezze a kijelölt felosztási kulcshoz tartozó termékek statisztikai kiinduló előrejelzésének generálása során használni kívánt tranzakciótípusokat. A beállítások úgy működnek, **mint** az Általános lapon, de csak a kiválasztott cikkfelosztási kulcsra vonatkoznak. Az összes beállítás (igen *·* *és* Nem érték is) **·** **felülbírálja az Általános lapon található összes tranzakciótípus-beállítást.**
1. Az Előrejelzés algoritmusparaméterek **gyorsbillentyűinél** válassza ki az előrejelzés-generálási stratégiát és az előrejelzési algoritmus paramétereinek felülbírálatát a kiválasztott felosztási kulcshoz tartozó termékeknél. Ezek a beállítások pont úgy **működnek**, mint az Általános lapon, de csak a kiválasztott cikkfelosztási kulcsra vonatkoznak. Az eszköztár **Hozzáadás** és **eltávolítás** gombjaival megadhatja a paraméter-felülbírálások kötelező gyűjteményét. A listában mindegyik paraméterhez válasszon ki egy értéket a **Név** mezőben, **majd adjon meg egy megfelelő értéket az Érték mezőben**. A normál paraméterkészlet [használatával és a paraméterek értékeinek kiválasztásával kapcsolatos további tudnivalókat lásd az Igény-előrejelzési modellek alapértelmezett paraméterei és értékei című](#model-parameters) részében.

### <a name="set-up-the-connection-to-the-azure-machine-learning-service"></a>Az Azure-számítógép-oktatási szolgáltatáshoz való kapcsolat beállítása

**Az Azure számítógép-oktatási szolgáltatás** lapon beállíthatja a kapcsolatot az Azure gépi oktatószolgáltatással. Ez a megoldás a kiinduló előrejelzés létrehozásának egyik lehetséges beállítása. Ezeknek a beállításoknak a lapnak csak akkor van hatása, **ha az Előrejelzés-generálási stratégia** mező az *Azure gépi oktatási szolgáltatásra van beállítva*.

Az Azure-gépi oktatási szolgáltatás beállításának és az itt megadott beállításoknak a használatával való kapcsolódásról az Azure-számítógép-oktató [szolgáltatás beállítása című szakasz nyújt további tájékoztatást](#setup-amls).

### <a name="set-up-the-connection-to-azure-machine-learning-studio-classic"></a>Az Azure Machine Learning Studio alkalmazással létesítő kapcsolat beállítása (az)

> [!IMPORTANT]
> Az Azure Machine Learning Studio (8) elavult. A továbbiakban nem hozhat létre új munkaterületet az Azure szolgáltatásban. Ezt a funkciót az Azure számítógép-oktatási szolgáltatás váltotta fel, amely hasonló funkciókat és más funkciókat is biztosít. Ha még nem használja az Azure-számítógép-tanulást, el kell kezdenie az Azure gépi oktatási szolgáltatás használatát. Ha már van egy olyan munkaterülete, amely az Azure Machine Learning Studio alkalmazáshoz lett létrehozva (az előfizetéshez), akkor továbbra is használhatja, amíg a funkciót teljesen el nem távolítja az Azure szolgáltatásból. Javasoljuk azonban, hogy a lehető leghamarabb frissítse az Azure számítógép-oktatási szolgáltatást. Annak ellenére, hogy az alkalmazás továbbra is figyelmezteti, hogy az Azure Machine Learning Studio (5) elavult, ez nem befolyásolja az előrejelzés eredményét. Az új Azure-számítógép-oktatási [szolgáltatásról és beállításukról az Azure-gépi oktatási szolgáltatás beállítása című szakasz nyújt további](#setup-amls) tájékoztatást.
>
> Az ellátásilánc-kezelés segítségével szabadon válthat az új és régi gépi oktatási megoldások között, amíg a régi Azure Machine Learning Studio (az eszköz) munkaterülete elérhető marad.

Ha már van egy elérhető Azure Machine Learning Studio (az5) munkaterülete, előrejelzést generálhat, ha az ellátásilánc-kezeléshez kapcsolódik. Ezt a kapcsolatot az **Igény-előrejelzési paraméterek lap Azure Gépi** **tanulás lapján lehet** létrehozni. (A lapon található beállítások csak akkor lépnek hatályba, ha **a Az előrejelzés-generálás stratégiamezője** az Azure-gépi *tanulásra van beállítva*.) Adja meg a következő adatokat az Azure Machine Learning Studio (5) munkaterületéhez:

- Az API programozási felület (Telephony Alkalmazásprogramozási Felület) beállítása
- URL webszolgáltatási végpont
- Azure tárfiók neve
- Azure tárfiók kulcsa

> [!NOTE]
> Az Azure tárolási számlanév és kulcs csak egyéni tárolási fiók használata esetén szükséges. Ha a létesítmény verzióját telepíti, akkor egyéni tárolási fiókkal kell rendelkezik az Azure szolgáltatásban, hogy a gépi tanulás hozzáférjen az előzményadatokhoz.

## <a name="default-parameters-and-values-for-demand-forecasting-models"></a><a name="model-parameters"></a> Az igény-előrejelzési modellek alapértelmezett paraméterei és értékei

Ha a gépi oktatás segítségével generálja az előrejelzés-tervezési modelleket, *akkor a gépi oktatási lehetőségeket az előrejelzési algoritmus paramétereire vonatkozó értékek beállításával szabályozhatja*. Ezeket az értékeket az Ellátásilánc-kezelés rendszerből az Azure-gépi tanulásba küldi a rendszer. Az előrejelzési **algoritmus paraméterei** lapon lehet szabályozni, hogy milyen típusú értékeket és milyen értékeket kell adni.

Az igény-előrejelzési **\> modellekhez használt alapértelmezett paraméterek és értékek beállításához használja az Alaptervezés beállítása \>\> igény-előrejelzési algoritmusának paramétereit**. A rendszer szabványos paraméterkészletet biztosít. Mindegyik paraméter a következő mezőket tartalmazza:

- **Név** – a paraméter neve, ahogyan azt az Azure használja. Ezt a nevet általában csak akkor érdemes módosítani, ha már testreszabta az Azure-gépi tanulással való kísérleteket.
- **Leírás** – a paraméter gyakori neve. Ezzel a névvel lehet azonosítani a paramétert a rendszer más helyeiben (**például az igény-előrejelzési paraméterek oldalon**).
- **Érték** – a paraméter alapértelmezett értéke. A beírni szükséges érték a szerkesztett paramétertől függ. 
- **Magyarázat** – a paraméter rövid leírása és használata. Ez a leírás általában az Érték mező érvényes értékeivel kapcsolatban tartalmaz **kódot**.

Alapértelmezés szerint a következő paraméterek biztosítanak. (Ha soha nem kell visszaállni erre a szokásos listára, válassza a **Visszaállítás** a műveletpanelen.)

- **Megbízhatósági szint százaléka** – A megbízhatósági intervallum olyan értékek tartományából áll, amelyek az igény-előrejelzés jó becslését adják. A 95 %-os megbízhatósági szint azt jelenti, hogy 5 % a kockázata annak, hogy az igény-előrejelzés eredménye a megbízhatósági intervallum tartományán kívül esik.
- **Force szezonálisság** – megadja, hogy a modellt egy bizonyos típusú szezonálisra kell-e kényszeríteni. Ez a paraméter csak az ARIMA és az ETS paraméterre vonatkozik. Lehetőségek: *AUTOMATIKUS (alapértelmezett)*, NINCS *,* ADDIKTÍVA *·*, *SZORZÓ*.
- **Előrejelzési modell** – a használni használt előrejelzési modellt adja meg. Lehetőségek: *ARIMA*, *ETS*, *STL*, *ETS+ARIMA*, *ETS+STL*, *MIND*. A leginkább illeszkedő modell kiválasztásához használja az *ÖSSZES lehetőséget*.
- **Maximális előre jelzett érték** – Az előrejelzésekhez használandó maximális értéket adja meg. Formátum: + 1E[n] vagy numerikus állandó.
- **Minimális előre jelzett érték** – Az előrejelzésekhez használandó minimális értéket adja meg. Formátum: -1E[n] vagy numerikus állandó.
- **Hiányzó érték-helyettesítés** – Meghatározza a múltbeli adatok hiányosságainak kitöltésének módját. Lehetőségek: *(numerikus érték)*, *MEAN*, *ELŐZŐ*, *LINEÁRIS ÉS LINEÁRIS* *LINEÁRIS ÉS LINEÁRIS POLINOMIÁLIS*.
- **Hiányzó érték-helyettesítésihatóköre** – Megadja, hogy az érték-helyettesítés csak az egyéni granularítású attribútumok dátumtartományára vagy a teljes adathalmazra vonatkozik-e. A korábbi adatokból hiányzó adatok kitöltésekor a rendszer által használt dátumtartomány megállapítására a következő lehetőségek állnak rendelkezésre:

    - *GLOBÁLIS* – a rendszer a részletességi attribútumok teljes dátumtartományát használja.
    - *HISTORY_DATE_RANGE* – a rendszer egy olyan konkrét dátumtartományt használ, amelyet **a** **·** **·** **Statisztikai** kiinduló előrejelzés létrehozása párbeszédpanel Előzményhorizont szakaszának Kiindulási dátum és Befejezés dátum mezője határoz meg.
    - *GRANULARITY_ATTRIBUTE* – a rendszer a jelenleg feldolgozott részletességi attribútum dátumtartományát használja.

    > [!NOTE]
    > A részletességi attribútum az előrejelzési dimenziók olyan kombinációja, amelyen az előrejelzést elvégzik. Az előrejelzési dimenziókat az **Igény-előrejelzési paraméterek** oldalon definiálhatja.

- **Szezonalitás tipp** – A szezonális adatokhoz az előrejelzési pontosság javítása érdekében adjon meg egy tippet az előrejelzési modellhez. Formátum: az igényminta által ismétlődő időszakszámnak megfelelő egész szám. Adjon meg *például 6-ot* az olyan adatokhoz, amelyek minden hat hónapban ismétlődnek.
- **Tesztkészlet mérete százalékban** – Az előrejelzés pontosságának számításához tesztkészletként használni kívánt előzményadatok százaléka.

Ezeknek a paramétereknek az **\>\>\> értékét az Alaptervezés beállítása igény-előrejelzési paramétereinél lehet felülbírálni.** Az Igény-előrejelzési **paraméterek** lapon a következőképpen lehet felülbírálni a paramétereket:

- Az Általános **lapon** globálisan felülbírálhatja a paramétereket.
- A Cikkfelosztási **kulcsok** lapon felülbírálhatja az egyes cikkfelosztási kulcsok paramétereit. Egy adott cikkfelosztási kulcshoz felülbírált paraméterek csak az adott cikkfelosztási kulcshoz társított cikkek előrejelzésére vonatkoznak.

> [!NOTE]
> Az Előrejelzés algoritmusparaméterek **lapon** használhatja a műveletpanelen található gombok paramétereit a listához, vagy eltávolíthatja a paramétereket a listáról. Általában azonban csak akkor érdemes ezt a megközelítést alkalmazni, ha testreszabták az Azure-gépi tanulásban történt kísérleteket.

## <a name="set-up-the-azure-machine-learning-service"></a><a name="setup-amls"></a> Az Azure-számítógép-oktatási szolgáltatás beállítása

Az ellátásilánc-kezelés az igény-előrejelzéseket az Azure gépi oktatási szolgáltatás használatával számítja ki, amelyet saját Azure-előfizetésére kell beállítania és futtatnia. Ez a szakasz azt írja le, hogyan lehet beállítani az Azure-t és az Ellátásilánc-kezelési környezetet az Azure szolgáltatásban, majd csatlakoztatni azt az ellátásilánc-kezelési környezethez.

### <a name="enable-the-azure-machine-learning-service-in-feature-management"></a>Az Azure-számítógép oktatási szolgáltatás engedélyezése a funkciókezelésben

Az Azure-gépi oktatási szolgáltatás igény-előrejelzésre való használata előtt be kell kapcsolnia az Ellátásilánc-kezelés egy funkcióját, hogy engedélyezze az integrációt. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Alaptervezés modul*
- **Funkció neve:** *Azure gépi oktatási szolgáltatás igény-előrejelzéshez*

### <a name="set-up-machine-learning-in-azure"></a><a name="ml-workspace"></a> Gépi tanulás beállítása az Azure szolgáltatásban

Ahhoz, hogy az Azure a gépi tanulást használja az előrejelzések feldolgozásához, ehhez be kell állítania egy Azure-alapú gépi oktatási munkaterületet. Két lehetőség áll rendelkezésre:

- A munkaterületnek a Microsoft [által biztosított parancsfájl futtatásával való beállításához hajtsa végre az 1. beállításnál megadott utasításokat: Parancsfájl futtatása a](#ml-workspace-script) gépi tanulás munkaterületének automatikus beállításához, [majd előreugrás az Azure-gépi tanulás szolgáltatás](#demand-forecast-parameters) kapcsolati paramétereinek beállításához az Ellátásilánc-kezelés szakaszban.
- A munkaterület [manuális beállításához kövesse a 2. lehetőségnél megadott utasításokat:](#ml-workspace-manual) állítsa be manuálisan a gépi tanulás munkaterületének szakaszát, [majd ugorjon előre az Azure-számítógép-oktató](#demand-forecast-parameters) szolgáltatás kapcsolati paramétereinek beállítása az Ellátásilánc-kezelés szakaszban. Ez a beállítás több időt vesz igénybe, de több ellenőrzést ad.

#### <a name="option-1-run-a-script-to-automatically-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-script"></a> 1. beállítás: Parancsfájl futtatása a gépi oktató munkaterület automatikus beállításhoz

Ez a szakasz bemutatja, hogyan lehet beállítani a gépi oktatási munkaterületet a Microsoft által biztosított automatikus parancsfájl használatával. Ha azt szeretné, hogy [manuálisan állítsa be az összes erőforrást, kövesse a 2. lehetőségben található utasításokat: Állítsa be kézzel a gépi tanulás munkaterületének szakaszát](#ml-workspace-manual). Nem kell mindkét lehetőséget végrehajtania.

1. Nyissa meg a Sablonokat igény-előrejelzéshez [Dynamics 365 Supply Chain Management az Azure-számítógép oktatási](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) tárházában (repo), és töltse le a következő fájlokat:

    - quick_setup.ps1
    - sampleInput.csv
    - rc/parameters.py
    - src/api_trigger.rc
    - src/run.py
    - src/REntryScript/forecast.r

1. Nyisson meg egy PowerShell-ablakot, **és futtassa az quick_setup.ps1** parancsfájlt, amely az előző lépésben letöltött. Kövesse a képernyőn megjelenő utasításokat. A parancsfájl be fogja állítani a szükséges munkaterületet, tárolót, alapértelmezett adattárat és erőforrásokat. Ennek ellenére létre kell hoznia a szükséges csővezetékeket az eljárás további lépéseit követve. (A csővezetékek segítségével el lehet kezdeni az ellátásilánc-kezelésből származó előrejelzési parancsfájlokat.)
1. Az Azure Machine Learning Studio **szolgáltatásban töltse fel az 1**. lépésben letöltött sampleInput.csv *fájlt a demplan-azureml nevű tárolóba*. (A quick_setup.ps1 parancsprogram hozta létre ezt a tárolót.) Ez a fájl szükséges a csővezeték közzétételéhez és a teszt-előrejelzés generálásához. Az utasításokat lásd: Blokk [blob feltöltése](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob).
1. Az Azure Machine Learning Studio szolgáltatásban válassza ki **a Előfizetések** lehetőséget a fájlban.
1. A következő hely a **Fájlok** struktúrában: **Felhasználók/\[aktuális felhasználó\]/rc**.
1. Töltse fel az 1. lépésben letöltött fennmaradó négy fájlt az előző lépésben talált helyre.
1. Válassza ki **api_trigger most feltöltött api_trigger.fájlját**, majd futtassa. Létrehoz egy csővezetéket, amely az API-n keresztül indítható el.
1. A munkaterület már be van állítva. Ugorjon előre az [Azure-számítógép-oktatási szolgáltatás kapcsolati paramétereinek beállításához az Ellátásilánc-kezelés szakaszban](#demand-forecast-parameters).

#### <a name="option-2-manually-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-manual"></a> 2. beállítás: A gépi oktató munkaterület manuális beállítása

Ez a szakasz bemutatja, hogyan lehet manuálisan beállítani a gépi oktatási munkaterületet. Csak akkor kell végrehajtania az ebben a szakaszban leírt eljárásokat, ha úgy döntött, hogy nem futtatja az automatizált beállítási parancsfájlt az [1. lehetőségnél leírtak szerint: Parancsfájl futtatása a](#ml-workspace-script) gépi tanulás munkaterületének beállításához.

##### <a name="step-1-create-a-new-workspace"></a><a name="create-workspace"></a> 1. lépés: Új munkaterület létrehozása

A következő eljárás szerint hozzon létre egy új gépi oktatási munkaterületet.

1. Jelentkezzen be az Azure-portálra.
1. A Gépi **oktatási szolgáltatás** megnyitása
1. Válassza a **Létrehozás** lehetőséget az eszköztáron a Létrehozás varázsló **megnyitásához**.
1. Töltse ki a varázslót a képernyőn látható útmutatások segítségével. Munka közben tartsa szem előtt a következő pontokat:

    - Használja az alapértelmezett beállításokat, hacsak a listában más pontok nem javasolnak eltérő beállításokat.
    - Győződjön meg róla, hogy azt a földrajzi régiót választja ki, amely megfelel annak a régiónak, ahová az ellátásilánc-kezelés egy példányát telepítik. Ellenkező esetben az adatok egy része a régióhatárok határán haladhat végig. A további tudnivalókat lásd a témakör [későbbi](#privacy) adatvédelmi nyilatkozatában.
    - Használjon külön erőforrásokat, például erőforráscsoportokat, tárolási fiókokat, tárolóregisztrálókat, Azure-kulcsokat és hálózati erőforrásokat.
    - A varázsló **Azure-számítógép oktatási szolgáltatás kapcsolati paramétereinek** lapján meg kell adnia egy tárolási fiók nevét. Igény-előrejelzésre kijelölt fiók használata. Az igény-előrejelzés bemeneti és kimeneti adatait a rendszer ebben a tárolási fiókban tárolja.

További tájékoztatás: Munkaterület [létrehozása](/azure/machine-learning/quickstart-create-resources#create-the-workspace).

##### <a name="step-2-configure-storage"></a><a name="config-storage"></a> 2. lépés: A tárolás konfigurálása

A következő eljárás szerint állíthatja be a tárolást.

1. Nyissa meg a Sablonokat igény-előrejelzéshez [Dynamics 365 Supply Chain Management az Azure-gépi](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) oktatófájllal, **és töltse le a sampleInput.csv fájlt**.
1. Nyissa meg az [1. lépésben létrehozott tárolási fiókot: hozzon létre egy új munkaterületet](#create-workspace).
1. A Demplan-azureml [nevű tároló létrehozásához hajtsa végre a](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)*Tároló létrehozása útmutatását*.
1. Töltse fel **az 1. lépésben letöltött sampleInput.csv** fájlt a most létrehozott tárolóba. Ez a fájl szükséges a csővezeték közzétételéhez és a teszt-előrejelzés generálásához. Az utasításokat lásd: Blokk [blob feltöltése](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob).

##### <a name="step-3-configure-a-default-datastore"></a>3. lépés: Alapértelmezett adattár konfigurálása

A következő eljárás szerint állíthatja be az alapértelmezett adattárat.

1. Az Azure Machine Learning Studio szolgáltatásban válassza **ki az adattárokat** a környezetben.
1. Hozzon létre egy új, az Azure Blob *tárolótípusnak* megfelelő adattárat, amely a *2. lépésben létrehozott demplan-azureml* Blob [tárolóra mutat: A tárolási szakasz](#config-storage) konfigurálása. (Ha az új adattár hitelesítési típusa *Számlakulcs*, adjon meg egy számlakulcsot a létrehozott tárolási fiókhoz. Az útmutatás a Tárolási fiókok hozzáférési [kulcsának kezelése útmutatóban található](/azure/storage/common/storage-account-keys-manage?tabs=azure-portal).)
1. Az új adattár létrehozása az alapértelmezett **adattár megnyitásával és a Beállítás alapértelmezett adattárként beállításával**.

##### <a name="step-4-configure-compute-resources"></a><a name="config-compute-resources"></a> 4. lépés: Számítási erőforrások konfigurálása

A következő eljárás szerint állíthat be egy számítási erőforrást az Azure Machine Learning Studio szolgáltatásban az előrejelzés-generáló parancsfájlok futtatásához.

1. Nyissa meg az [1. lépésben létrehozott gépi oktatási munkaterület részletező lapját: Hozzon létre egy új munkaterületet](#create-workspace). Keresse meg **a Studio web URL-címét**, és válassza ki a megnyitni kívánt hivatkozást.
1. Válassza a **Számítás** lehetőséget a navigációs ablakban.
1. A Számításpéldányok **lapon** az Új **gombra** választva megnyit egy varázslót, amely segít új számítási példány létrehozásában. Kövesse a képernyőn megjelenő utasításokat. A számítási példány fogja használni az igény-előrejelzési folyamat létrehozásához (a t csővezeték közzététele után törölhető.) Az alapértelmezett beállítások használata.
1. A Fürtök **számítása** lapon az Új **gombra választva megnyit egy varázslót,** amely segít új számítási fürt létrehozásában. Kövesse a képernyőn megjelenő utasításokat. A számítási fürt az igény-előrejelzések előállítására lesz használva. A beállítások befolyásolják a teljesítményt és a futtatás maximális párhuzamosítási szintjét. A következő mezők beállítása, de az összes többi mező alapértelmezett beállításainak használata:

    - **Név** – adja meg az *e2ecpuclustert*.
    - **Virtuális gép mérete** – a beállítást annak megfelelően kell módosítani, hogy milyen adatmennyiségre számít az igény-előrejelzés bemeneteként. A csomópontok számának nem szabad 11-et túllépni, mert egy csomópont szükséges az igény-előrejelzés előállításának az aktiválásához, és az előrejelzés generálása esetén használható csomópontok maximális száma 10. (A csomópontok számát a <a0/parameters.py fájljában is be fogja állítani. [5. lépés: Csővezetékek szakasz](#create-pipelines) létrehozása.) Minden csomóponton több olyan dolgozói folyamat is lesz, amelyek párhuzamosan futtatnak előrejelzési parancsfájlokat. A feladatban található *dolgozói* *folyamatok száma a csomópontok csomópontok számának megfelelő × lesz*. *Ha például a számítási fürt StandardD4\_* (nyolc mag) típusú, és legfeljebb 11 csomópont, `nodes_count`*és ha az parameters.py fájlban 10-re* van állítva, akkor a párhuzamosság tényleges szintje 80.

##### <a name="step-5-create-pipelines"></a><a name="create-pipelines"></a> 5. lépés: Csővezetékek létrehozása

A csővezetékek segítségével el lehet kezdeni az ellátásilánc-kezelésből származó előrejelzési parancsfájlokat. A következő eljárás szerint hozza létre a szükséges csővezetékeket.

1. Nyissa meg a Sablonokat igény-előrejelzéshez [Dynamics 365 Supply Chain Management az Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) repo segítségével, és töltse le a következő fájlokat:

    - rc/parameters.py
    - src/api_trigger.rc
    - src/run.py
    - src/REntryScript/forecast.r

1. Az Azure Machine Learning Studio szolgáltatásban válassza ki **a Előfizetések** lehetőséget a fájlban.
1. A következő hely a **Fájlok** struktúrában: **Felhasználók/\[aktuális felhasználó\]/rc**.
1. Töltse fel az 1. lépésben letöltött négy fájlt arra a helyre, amely az előző lépésben megtalálható.
1. Az Azure szolgáltatásban nyissa meg és **tekintse parameters.py** az éppen feltöltött fájlban. Győződjön meg róla `nodes_count`, hogy az érték 1-ével [kisebb, mint a 4. lépésben a számítási fürthöz konfigurált érték: A Számított erőforrások szakasz](#config-compute-resources) konfigurálása. Ha az `nodes_count` érték nagyobb vagy egyenlő a számítási fürtben található csomópontok számán, akkor a csővezeték-futás el is indítható. Ettől azonban le fog állni, amíg a szükséges erőforrásokra várakozik. A csomópontok számról [a 4. lépés: Számítási erőforrások konfigurálása szakasz tartalmaz](#config-compute-resources) további tudnivalókat.
1. Válassza ki **api_trigger most feltöltött api_trigger.fájlját**, majd futtassa. Létrehoz egy csővezetéket, amely az API-n keresztül indítható el.

### <a name="set-up-a-new-active-directory-application"></a><a name="aad-app"></a> Új Active Directory-alkalmazás beállítása

Egy Active Directory-alkalmazásnak hitelesítve kell lennie az igény-előrejelzésre kijelölt erőforrásokkal a szolgáltatásnév alapján. Emiatt az alkalmazásnak az előrejelzés generálához szükséges legalacsonyabb szintű jogosultsággal kell rendelkezik.

1. Jelentkezzen be az Azure-portálra.
1. Új pályázat regisztrálása a bérlő () számára Azure Active Directory Azure AD. Az útmutatásért lásd [a portálon az Azure AD erőforrásokhoz hozzáférő alkalmazás és szolgáltatásnév létrehozásához](/azure/active-directory/develop/howto-create-service-principal-portal).
1. A varázsló befejezése után kövesse a képernyőn látható utasításokat. Az alapértelmezett beállítások használata.
1. Adjon új Active Directory-alkalmazáselérést [a következő erőforrásokhoz, amelyek az Azure rendszer gépi oktatásának beállítása szakaszban létre vannak](#ml-workspace) hozva. Az útmutatás az Azure-szerepkörök [hozzárendelése az Azure-portálon található](/azure/role-based-access-control/role-assignments-portal?tabs=current). Ez a lépés lehetővé teszi, hogy a rendszer importálja és exportálja az előrejelzési adatokat, és elindítsa az ellátásilánc-kezelésből a gépi oktatási folyamatot.

    - Kitöltő szerepkör a gépi oktatási munkaterületen
    - Támogató szerepkör a kijelölt tárolási fiókhoz
    - Tárolási blobadatokhoz való hozzájárulási szerepkör a kijelölt tárolási fiókhoz

1. A létrehozott **alkalmazás Tanúsítványok & szakaszának** létrehozásához hozzon létre egy titkos alkalmazást. Az útmutatásért lásd [az Ügyfél titkos hozzáadása gombra vonatkozó tudnivalókat](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).
1. Jegyezze fel az alkalmazásazonosítót és annak titkos azonosítóját. Az alkalmazás részleteire később szüksége lesz az igény-előrejelzési **paraméterek** lapnak az Ellátásilánc-kezelés eszközben való beállításakor.

### <a name="set-up-azure-machine-learning-service-connection-parameters-in-supply-chain-management"></a><a name="demand-forecast-parameters"></a> Az Azure-számítógép-oktatási szolgáltatás kapcsolati paramétereinek beállítása az ellátásilánc-kezelésben

A következő eljárás szerint kapcsolhatja az ellátásilánc-kezelési környezetet az Azure szolgáltatásban éppen beállított gépi oktatási szolgáltatáshoz.

1. Jelentkezzen be a Supply Chain Management alkalmazásba.
1. Ugrás az Alaptervezés **beállítása \> igény-előrejelzési \> igény-előrejelzési \> paramétereihez**.
1. Az Általános **lapon** győződjön meg arról, **hogy** az Előrejelzés-generálási stratégia mező az *Azure gépi oktatási szolgáltatásra van beállítva*.
1. A Cikkfelosztási **kulcsok** lapon győződjön meg arról, hogy az Előrejelzés-generálási stratégia mezőben az Azure gépi **tanulás szolgáltatás minden olyan foglalási kulcsnál be van állítva,** *amely* az Azure gépi oktatási szolgáltatást igény-előrejelzésre használja.
1. **Az Azure-számítógép oktatási szolgáltatás** lapján állítsa be a következő mezőket:

    - **Bérlő azonosítója** – adja meg az Azure-bérlő azonosítóját. Az ellátásilánc-kezelés ezt az azonosítót fogja használni az Azure-számítógép-oktató szolgáltatással való hitelesítésre. A bérlőazonosító az **Azure-portál Áttekintés** Azure AD lapján található.
    - **Szolgáltatásnév alkalmazásazonosítója** – adja meg [annak az alkalmazásnak az azonosítóját, amit az Active Directory alkalmazás szakaszban](#aad-app) létrehozott. Ez az érték az Azure számítógép-oktató szolgáltatásnak való API-kérések engedélyeztetését teszi lehetővé.
    - **Szolgáltatásnév titkos szolgáltatását** – adja [meg az Active Directory alkalmazás szakaszban létrehozott alkalmazás szolgáltatási rendszernév-alkalmazásának titkos](#aad-app) könyvtárát. Ezzel az értékkel szerezheti meg annak a biztonsági meghatalmazottnak a hozzáférési jogkivonatát, amely az Azure-tárterülettel és az Azure-számítógép nyelvi munkaterületével szemben engedélyezett műveletek végrehajtásához jött létre.
    - **Tárolási fiók neve** – adja meg azt az Azure-tárolási fióknevet, amely a beállítási varázsló Azure-munkaterületen való futtatásakor meg van adva. (További tájékoztatás: [Gépi tanulás beállítása az Azure szakaszban](#ml-workspace) .)
    - **Térér végpontjának címe** – adja meg az Azure-számítógép oktatási szolgáltatása térmében található REST végpont URL-címét. Ez a csővezeték az Utolsó [lépés, amikor gépi tanulást hoz létre az Azure szolgáltatásban](#ml-workspace). A csővezeték URL-címének bejéhez jelentkezzen be az Azure-portálra, **és** válassza ki a navigációs csővezeték-t. A T csővezeték **lapon** válassza **ki a TriggerDemandForecastGeneration nevű csővezeték-végpontot**. Ezután másolja át a megjelenő REST-végpontot.

    ![Az Igény-előrejelzési paraméterek lap Azure-számítógép-oktatási szolgáltatás lapján található paraméterek](media/azure-ml-service-parameters.png "Az Igény-előrejelzési paraméterek lap Azure-számítógép-oktatási szolgáltatás lapján található paraméterek")

## <a name="privacy-notice"></a><a name="privacy"></a>Adatvédelmi nyilatkozat

*Ha az Azure gépi* oktatási szolgáltatást előrejelzés-generáló stratégiaként választja, az ellátásilánc-kezelés automatikusan elküldi a vevő adatait a korábbi igényeknek( például összesített mennyiségeknek, termékneveknek és termékdimenzióiknak, a szállítási és bevételi helyeknek, a vevőazonosítóknak, valamint az előrejelzési paramétereknek) a földrajzi régióba, ahol a gépi oktatási munkaterület és a kapcsolódó tárolási fiók található, a jövőbeli igények előrejelzésére. Az Azure-számítógép oktatási szolgáltatása valószínűleg más földrajzi területen van, mint az ellátásilánc-kezelés telepítésének földrajzi régiója. Egyes felhasználók az igény-előrejelzési **paraméterek oldalon az előrejelzés-generálás stratégia kiválasztásával szabályozhatja, hogy ez a funkció engedélyezve** van-e.

## <a name="additional-resources"></a>További erőforrások

- [Igény-előrejelzés áttekintése](introduction-demand-forecasting.md)
- [Statisztikai kiinduló előrejelzés létrehozása](generate-statistical-baseline-forecast.md)
- [A kiinduló előrejelzés manuális kiigazítása](manual-adjustments-baseline-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
