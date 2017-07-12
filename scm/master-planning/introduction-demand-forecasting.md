---
title: "Igény-előrejelzés áttekintése"
description: "Az igény-előrejelzés értékesítési rendelésekből származó független igények előrejelzésére, valamint a vevői rendelések bármely szétválasztási pontjára vonatkozó függő igények előrejelzésére használható. A továbbfejlesztett, igény-előrejelzést redukáló szabályok ideális megoldást kínálnak a tömeges egyéniesítéshez."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72004
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 6b4498ae05b9495918c0a079cc88903820192a59
ms.contentlocale: hu-hu
ms.lasthandoff: 06/13/2017


---

# <a name="demand-forecasting-overview"></a>Igény-előrejelzés áttekintése

[!include[banner](../includes/banner.md)]


Az igény-előrejelzés értékesítési rendelésekből származó független igények előrejelzésére, valamint a vevői rendelések bármely szétválasztási pontjára vonatkozó függő igények előrejelzésére használható. A továbbfejlesztett, igény-előrejelzést redukáló szabályok ideális megoldást kínálnak a tömeges egyéniesítéshez.

A kiinduló előrejelzés generálásához a rendszer elküldi az előzménytranzakciók összesítését az Azure rendszerbeli Microsoft Azure Machine Learning szolgáltatásnak. Mivel ez a szolgáltatás nincs megosztva a felhasználók között, egyszerűen, az iparágra jellemző szükségleteknek megfelelően testreszabható. A Finance and Operations segítségével megjelenítheti és kiigazíthatja az előrejelzést, valamint megtekintheti az előrejelzés pontosságára vonatkozó fő teljesítménymutatókat (KPI-ket).

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

-   **Modularitás** – Az igény-előrejelzés moduláris és egyszerűen konfigurálható. A **Kereskedelem** &gt; **Készlet előrejelzése** &gt; **Igény-előrejelzés** pontban megtalálható konfigurációs kulcs megváltoztatásával a funkció be- és kikapcsolható.
-   **Microsoft-technológiák újrafelhasználása** – A Microsoft 2015 februárjában indította el a Machine Learning platformot. Az immár a Microsoft Cortana Analytics Suite programcsomag részét képező Machine Learning prediktív elemzőkísérletek (például igénybecslési kísérletek) gyors és egyszerű elkészítését teszi lehetővé, R vagy Python programnyelven írt algoritmusok és egy egyszerű, ikonok áthúzásával kezelhető felület használatával.
    -   A Finance and Operations Igény-előrejelzési kísérleteket letöltheti, saját üzleti igényeinek megfelelően testreszabhatja, webszolgáltatásként közzéteheti az Azure rendszeren és felhasználhatja őket igény-előrejelzések létrehozására. A kísérletek egy termeléstervező mint vállalati szintű felhasználó Finance and Operations előfizetésének megvásárlása után tölthetőek le.
    -   A jelenleg elérhető igény-előrejelzési kísérletek bármelyikét letöltheti a [Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/) oldalról. Míg a Finance and Operations Igény-előrejelzés kísérletek a Finance and Operations rendszerrel való integrációja automatikus, a [Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/) gyűjteményből letöltött kísérletek integrálását a vevőknek és partnereknek kell kezelniük. Emiatt a [Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/) oldalról származó kísérletek – a Finance and Operations Igény-előrejelzési kísérleteivel ellentétben – nem használhatóak fel közvetlenül. A Finance and Operations API alkalmazásprogramozási felületének megfelelően módosítani kell a kísérletek kódját.
    -   A Microsoft Azure Machine Learning Studio rendszerében saját kísérleteket hozhat létre, ezeket szolgáltatásként közzéteheti az Azure rendszeren, és használatukkal igény-előrejelzéseket generálhat.
    -   Amennyiben nincs szükség nagy teljesítményre vagy nagy mennyiségű adat feldolgozására, használhatja a Machine Learning ingyenes szintjét. Javasoljuk, hogy mindig erről a szintről induljon, különösen a megvalósítás és a tesztelés fázisában. Ha nagyobb teljesítményre és kiegészítő tárhelyre van szüksége, a Machine Learning standard szintjét használhatja. Ehhez a szinthez Azure előfizetés, valamint további költségek megfizetése szükséges. A Machine Learning használatának költségeiről a <http://aka.ms/machine-learning-price-info> oldalon olvashat részletesen.
-   **Előrejelzés redukálása bármely szétválasztási pontnál** – A Finance and Operations igény-előrejelzése ezen a funkción alapul, amely mind a függő, mind a független igények előrejelzését lehetővé teszi bármely szétválasztási pontnál.

## <a name="basic-flow-in-demand-forecasting"></a>Az igény-előrejelzés alapfolyamata
A következő ábrán az igény-előrejelzés alapfolyamata látható. 

[![igény-előrejelzési bevezetési diagram](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

Az igény-előrejelzés generálás elindul a Finance and Operationsben. A rendszer begyűjti az előzménytranzakciók adatait a Finance and Operations tranzakciós adatbázisából, majd beírja ezeket egy előkészítési táblába. Ez az előkészítő tábla később egy Machine Learning szolgáltatáshoz kerül. Alig néhány testrestabási beállítás elvégzése után az előkészítő tábla számos adatforrással kiegészíthető. Az adatforrások lehetnek Microsoft Excel-fájlok, vesszővel tagolt értékfájlok (CSV), illetve a Microsoft Dynamics AX 2009-ből és a Microsoft Dynamics AX 2012-ből származó adatok. Tehát több különféle rendszerben tárolt előzményadatok alapján is létrehozhatóak igény-előrejelzések. Azonban az alapadatoknak (például a cikkneveknek és a mértékegységeknek) minden adatforrásban azonosnak kell lenniük.

A Finance and Operations Igény-előrejelzés Machine Learning kísérleteinek használatakor azok a kiinduló jelzés kiszámításához megkeresik az öt idősorozat szerinti előrejelzési módszer közül a legmegfelelőbbet. Ezeknek az előrejelzési módszereknek a paraméterei a Finance and Operations rendszerben kezelhetőek. 

Az előrejelzések, az előzményadatok, valamint a megelőző iterációkban az igény-előrejelzésekben eszközölt változtatások ezután elérhetőek a Finance and Operations rendszerében. 

A Finance and Operations segítségével megjelenítheti és módosíthatja a kiinduló előrejelzéseket. Az előrejelzések tervezéshez való használata előtt engedélyezni kell a manuális kiigazításokat.

## <a name="limitations"></a>Korlátozások
A Finance and Operations Igény-előrejelzés egy olyan eszköz, amely a gyártóiparban tevékenykedő vevők számára megkönnyíti az előrejelzési folyamatok létrehozását. Biztosítja az igény-előrejelzési megoldások alapvető funkcióit, és úgy lett tervezve, hogy egyszerűen kibővíthető legyen. Egyes iparágak (például kiskereskedelem, nagykereskedelem, raktározás, szállítás vagy más professzionális szolgáltatás) esetén az igény-előrejelzés nem feltétlenül a legmegfelelőbb választás.

<a name="see-also"></a>Lásd még
--------

[Igény-előrejelzési beállítások](demand-forecasting-setup.md)

[Statisztikai kiinduló előrejelzés generálása](generate-statistical-baseline-forecast.md)

[A kiinduló előrejelzés manuális kiigazítása](manual-adjustments-baseline-forecast.md)

[Beállított előrejelzés engedélyezése](authorize-adjusted-forecast.md)

[Az előrejelzés pontosság megfigyelése](monitor-forecast-accuracy.md)

[Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor](remove-historical-outliers-calculating-demand-forecast.md)




