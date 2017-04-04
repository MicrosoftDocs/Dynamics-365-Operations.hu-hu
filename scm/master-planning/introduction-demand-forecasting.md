---
title: "A kereslet előrejelzése – áttekintés"
description: "Az igény-előrejelzés értékesítési rendelésekből származó független igények előrejelzésére, valamint a vevői rendelések bármely szétválasztási pontjára vonatkozó függő igények előrejelzésére használható. A fokozott kereslet előrejelzés csökkentése szabályok az ideális megoldást nyújt a tömeges testreszabás."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72004
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 9152616b81e7873426f296376b5e57c94439379d
ms.lasthandoff: 03/31/2017


---

# <a name="demand-forecasting-overview"></a>A kereslet előrejelzése – áttekintés

Az igény-előrejelzés értékesítési rendelésekből származó független igények előrejelzésére, valamint a vevői rendelések bármely szétválasztási pontjára vonatkozó függő igények előrejelzésére használható. A fokozott kereslet előrejelzés csökkentése szabályok az ideális megoldást nyújt a tömeges testreszabás.

A kiinduló előrejelzés generálásához a rendszer elküldi az előzménytranzakciók összesítését az Azure rendszerbeli Microsoft Azure Machine Learning szolgáltatásnak. Mivel ez a szolgáltatás nincs megosztva a felhasználók között, egyszerűen, az iparágra jellemző szükségleteknek megfelelően testreszabható. Dynamics 365 műveletek segítségével ábrázolhatja az előrejelzés, előrejelzés beállítása és megtekintése kapcsolatos előrejelzési pontosságának fő teljesítménymutatók (KPI).

## <a name="key-features-of-demand-forecasting"></a>Az igény-előrejelzés fő funkciói
Az igény-előrejelzés legfontosabb funkciói közül néhány:

-   Statisztikai kiinduló előrejelzés generálása előzményadatok alapján
-   Dinamikus előrejelzési dimenziókészlet használata
-   Igénytrendek, megbízhatósági intervallumok és előrejelzés-kiigazítások megjelenítése.
-   A kiigazított előrejelzés engedélyezése tervezési folyamatokban való használathoz.
-   Kiugró értékek eltávolítása.
-   Előrejelzés-pontosságot megadó mérések létrehozása.

## <a name="major-themes-in-demand-forecasting"></a>Az igény-előrejelzés fő témái
Az igény-előrejelzés három fő téma szerint valósul meg:

-   **Modularitás** – Az igény-előrejelzés moduláris és egyszerűen konfigurálható. A funkció be- és kikapcsolása, a konfigurációs kulcs módosításával kapcsolhatja **kereskedelmi**&gt;**Készlet előrejelzése**&gt;**igény-előrejelzés**.
-   **Ismételt felhasználása a Microsoft Jegyzettömb** – a Microsoft kiadta a gép tanulási platform február 2015. Gépi tanulás, amely ma a Microsoft Cortana Analytics csomag része, gyorsan és egyszerűen készíthet prediktív elemzés kísérletek kereslet becslése kísérleteket, például R algoritmusok vagy Python programozási nyelv és az egyszerű drag-and-drop felületet teszi lehetővé.
    -   Töltse le a Dynamics 365 műveletek igény előrejelzésére kísérletek, módosítja azokat az üzleti követelményeknek, tegye közzé őket Azure a webes szolgáltatás, és segítségével igény-előrejelzések készítése. A kísérletekre letölthető, ha a Dynamics 365 a vállalati szintű felhasználói műveleteket a gyártástervező előfizetést vásárolt.
    -   A jelenleg elérhető igény-előrejelzési kísérletek bármelyikét letöltheti a [Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/) oldalról. Mivel műveletek igény előrejelzésére kísérletek a Dynamics 365 Dynamics 365 műveletek automatikusan integrálták, ügyfelek és partnerek kezelni kell az integrációs kísérletek, akkor töltse le a [Cortana Analytics galéria](https://gallery.cortanaanalytics.com/). Ezért a kísérletek a [Cortana Analytics galéria](https://gallery.cortanaanalytics.com/) nem használja a Dynamics 365 műveletek kereslet előrejelzése kísérletek éppolyan. A kísérletek a kódot módosítani kell, úgy, hogy a Dynamics 365 műveletek alkalmazásprogramozási felület (API) használjanak.
    -   A Microsoft Azure Machine Learning Studio rendszerében saját kísérleteket hozhat létre, ezeket szolgáltatásként közzéteheti az Azure rendszeren, és használatukkal igény-előrejelzéseket generálhat.
    -   Amennyiben nincs szükség nagy teljesítményre vagy nagy mennyiségű adat feldolgozására, használhatja a Machine Learning ingyenes szintjét. Javasoljuk, hogy mindig erről a szintről induljon, különösen a megvalósítás és a tesztelés fázisában. Ha nagyobb teljesítményre és kiegészítő tárhelyre van szüksége, a Machine Learning standard szintjét használhatja. Ehhez a szinthez Azure előfizetés, valamint további költségek megfizetése szükséges. A Machine Learning használatának költségeiről a <http://aka.ms/machine-learning-price-info> oldalon olvashat részletesen.
-   **Előrejelzés csökkentése szétválasztó bármikor** – az előrejelzés 365 Dynamics for műveletek build ezt a funkciót, amely lehetővé teszi mind a függő és független igények szétválasztó bármikor előrejelzés a kereslet.

## <a name="basic-flow-in-demand-forecasting"></a>Az igény-előrejelzés alapfolyamata
A következő ábrán az igény-előrejelzés alapfolyamata látható. 

[![Előrejelzési diagram igény szerint a Bevezetés](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

Igény-előrejelzési Dynamics 365 műveletek létrehozása induljon el. A Dynamics 365 műveletek tranzakciós adatbázis történeti tranzakciós adatait gyűjt, és feltölti átmeneti tábla. Ezen átmeneti tábla később táplálják egy gép tanulás szolgáltatást. Minimális testreszabási végrehajtásával csatlakoztathatja különböző adatforrások átmeneti táblájába. Az adatforrások lehetnek a Microsoft Excel fájlokat, vesszővel tagolt értéklista (CSV) fájlokat és adatokat a Microsoft Dynamics AX 2009, és a Microsoft Dynamics AX 2012. Ezért érdemes több rendszer között oszlik előzményadatok igény-előrejelzések hozhat létre. Azonban az alapadatoknak (például a cikkneveknek és a mértékegységeknek) minden adatforrásban azonosnak kell lenniük.

A Dynamics 365 műveletek igény gép tanulási kísérletekben előrejelzés használata esetén akkor keresni a legjobb öt alkalommal sorozat előrejelzési módszerek közül kiszámítására az előrejelzés alapterv. A paraméterek előrejelzési módszerek műveletek Dynamics 365 kezeli. 

Az előrejelzések, történelmi adatok és a korábbi iterációban igény-előrejelzések végrehajtott módosításokat a Dynamics 365 műveletek majd érhetők el. 

Dynamics 365 műveletek segítségével ábrázolhatja és az eredeti előrejelzések módosítása. Az előrejelzések tervezéshez való használata előtt engedélyezni kell a manuális kiigazításokat.

## <a name="limitations"></a>Korlátozások
Olyan eszköz, amely segíti a felhasználókat a feldolgozóipar hozzon létre előrejelzési folyamatok Dynamics 365 műveletek előrejelzése igény. Alapvető működést a kereslet előrejelzése megoldást kínál, és azt tervezték, hogy könnyen bővíthető. Igény-előrejelzés, lehet, hogy nem lehet a legjobb alkalmas ügyfelek például a kereskedelmi, ipari nagykereskedelemben, raktározás, szállítás vagy más szakmai szolgáltatásokat.

<a name="see-also"></a>Lásd még
--------

[Demand forecasting setup](demand-forecasting-setup.md)

[Generating a statistical baseline forecast](generate-statistical-baseline-forecast.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)

[Monitoring forecast accuracy](monitor-forecast-accuracy.md)

[Remove outliers from historical transaction data when calculating a demand forecast](remove-historical-outliers-calculating-demand-forecast.md)


