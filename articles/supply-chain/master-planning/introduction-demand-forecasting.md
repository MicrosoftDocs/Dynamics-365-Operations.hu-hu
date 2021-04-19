---
title: Igény-előrejelzés áttekintése
description: Az igény-előrejelzés értékesítési rendelésekből származó független igények előrejelzésére, valamint a vevői rendelések bármely szétválasztási pontjára vonatkozó függő igények előrejelzésére használható. A továbbfejlesztett, igény-előrejelzést redukáló szabályok ideális megoldást kínálnak a tömeges egyéniesítéshez.
author: roxanadiaconu
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72004
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9e00c980183708c5b9e995fb2a26d45baf13ca14
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829738"
---
# <a name="demand-forecasting-overview"></a>Igény-előrejelzés áttekintése

[!include [banner](../includes/banner.md)]

Az igény-előrejelzés értékesítési rendelésekből származó független igények előrejelzésére, valamint a vevői rendelések bármely szétválasztási pontjára vonatkozó függő igények előrejelzésére használható. A továbbfejlesztett, igény-előrejelzést redukáló szabályok ideális megoldást kínálnak a tömeges egyéniesítéshez.

A kiinduló előrejelzés generálásához a rendszer elküldi az előzménytranzakciók összesítését az Azure rendszerbeli Microsoft Azure gépi tanulás szolgáltatásnak. Mivel ez a szolgáltatás nincs megosztva a felhasználók között, egyszerűen, az iparágra jellemző szükségleteknek megfelelően testreszabható. A Supply Chain Management segítségével megjelenítheti és kiigazíthatja az előrejelzést, valamint megtekintheti az előrejelzés pontosságára vonatkozó fő teljesítménymutatókat (KPI-ket).

> [!NOTE]
> Microsoft Azure A Machine Learning Studio (klasszikus) szükséges az előrejelzés gépi tanulással való generálásához. 2021 januárjától a következő területeken érhető el: Kelet-Japán, USA déli középső régiója, Délkelet-Ázsia, USA nyugati középső régiója és Nyugat-Európa. Az aktuális elérhetőséggel kapcsolatos frissített információkért lásd: [Azure-termékek régiónként.](https://azure.microsoft.com/global-infrastructure/services/?regions=all&products=machine-learning-studio)

## <a name="key-features-of-demand-forecasting"></a>Az igény-előrejelzés fő funkciói

Az igény-előrejelzés legfontosabb funkciói közül néhány:

- Statisztikai kiinduló előrejelzés generálása előzményadatok alapján
- Dinamikus előrejelzési dimenziókészlet használata
- Igénytrendek, megbízhatósági intervallumok és előrejelzés-kiigazítások megjelenítése.
- A kiigazított előrejelzés engedélyezése tervezési folyamatokban való használathoz.
- Kiugró értékek eltávolítása.
- Előrejelzés-pontosságot megadó mérések létrehozása.

## <a name="major-themes-in-demand-forecasting"></a>Az igény-előrejelzés fő témái

Az igény-előrejelzés három fő téma szerint valósul meg:

- **Modularitás** – Az igény-előrejelzés moduláris és egyszerűen konfigurálható. A **Kereskedelem** &gt; **Készlet előrejelzése** &gt; **Igény-előrejelzés** pontban megtalálható konfigurációs kulcs megváltoztatásával a funkció be- és kikapcsolható.
- **Microsoft-technológiák újrafelhasználása** – Az immár a Microsoft Cortana Analytics Suite programcsomag részét képező Machine Learning prediktív elemzőkísérletek (például igénybecslési kísérletek) gyors és egyszerű elkészítését teszi lehetővé, R vagy Python programnyelven írt algoritmusok és egy egyszerű, ikonok áthúzásával kezelhető felület használatával.
  - Az Igény-előrejelzési kísérleteket letöltheti, saját üzleti igényeinek megfelelően testreszabhatja, webszolgáltatásként közzéteheti az Azure rendszeren és felhasználhatja őket igény-előrejelzések létrehozására. A kísérletek egy termeléstervező mint vállalati szintű felhasználó Supply Chain Management előfizetésének megvásárlása után tölthetők le.
  - A jelenleg elérhető igény-előrejelzési kísérletek bármelyikét letöltheti a [Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/) oldalról. Míg az Igény-előrejelzés kísérletek a Supply Chain Management rendszerrel való integrációja automatikus, a [Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/) gyűjteményből letöltött kísérletek integrálását a vevőknek és partnereknek kell kezelniük. Emiatt a [Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/) oldalról származó kísérletek – a Finance and Operations Igény-előrejelzési kísérletekkel ellentétben – nem használhatóak fel közvetlenül. A Finance and Operations alkalmazásprogramozási felületének (API) megfelelően módosítania kell a kísérletek kódját.
  - A Microsoft Azure Machine Learning Studio (klasszikus) rendszerében saját kísérleteket hozhat létre, ezeket szolgáltatásként közzéteheti az Azure rendszeren, és használatukkal igény-előrejelzéseket generálhat.
  - Amennyiben nincs szükség nagy teljesítményre vagy nagy mennyiségű adat feldolgozására, használhatja a Machine Learning ingyenes szintjét. Javasoljuk, hogy mindig erről a szintről induljon, különösen a megvalósítás és a tesztelés fázisában. Ha nagyobb teljesítményre és kiegészítő tárhelyre van szüksége, a Machine Learning standard szintjét használhatja. Ehhez a szinthez Azure előfizetés, valamint további költségek megfizetése szükséges. A Machine Learning használatának költségeiről a [Machine Learnin Studio árképzése](https://aka.ms/machine-learning-price-info) oldalon olvashat részletesen.
- **Előrejelzés redukálása bármely szétválasztási pontnál** – Az igény-előrejelzés ezen a funkción alapul, amely mind a függő, mind a független igények előrejelzését lehetővé teszi bármely szétválasztási pontnál.

## <a name="basic-flow-in-demand-forecasting"></a>Az igény-előrejelzés alapfolyamata

A következő ábrán az igény-előrejelzés alapfolyamata látható.

[![igény-előrejelzési bevezetési diagram](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

Az Igény-előrejelzés létrehozása a Supply Chain Management megoldásban kezdődik. A rendszer begyűjti az előzménytranzakciók adatait a Supply Chain Management tranzakciós adatbázisából, majd beírja ezeket egy előkészítési táblába. Ez az előkészítő tábla később egy Machine Learning szolgáltatáshoz kerül. Alig néhány testrestabási beállítás elvégzése után az előkészítő tábla számos adatforrással kiegészíthető. Az adatforrások lehetnek Microsoft Excel-fájlok, vesszővel tagolt értékfájlok (CSV), illetve adatok a Microsoft Dynamics AX 2009 és Microsoft Dynamics AX 2012 szolgáltatásokból. Tehát több különféle rendszerben tárolt előzményadatok alapján is létrehozhatóak igény-előrejelzések. Azonban az alapadatoknak (például a cikkneveknek és a mértékegységeknek) minden adatforrásban azonosnak kell lenniük.

Az Igény-előrejelzés Machine Learning kísérleteinek használatakor azok a kiinduló jelzés kiszámításához megkeresik az öt idősorozat szerinti előrejelzési módszer közül a legmegfelelőbbet. Ezeknek az előrejelzési módszereknek a paraméterei a Supply Chain Management rendszerben kezelhetőek.

Az előrejelzések, az előzményadatok, valamint a megelőző iterációkban az igény-előrejelzésekben eszközölt változtatások ezután elérhetőek a Supply Chain Management rendszerében.

A Supply Chain Management segítségével megjelenítheti és módosíthatja a kiinduló előrejelzéseket. Az előrejelzések tervezéshez való használata előtt engedélyezni kell a manuális kiigazításokat.

## <a name="limitations"></a>Korlátozások

Az Igény-előrejelzés egy olyan eszköz, amely a gyártóiparban tevékenykedő vevők számára megkönnyíti az előrejelzési folyamatok létrehozását. Biztosítja az igény-előrejelzési megoldások alapvető funkcióit, és úgy lett tervezve, hogy egyszerűen kibővíthető legyen. Egyes iparágak (például kereskedelem, nagykereskedelem, raktározás, szállítás vagy más professzionális szolgáltatás) esetén az igény-előrejelzés nem feltétlenül a legmegfelelőbb választás.

### <a name="demand-forecast-variant-conversion-limitation"></a>Igény-előrejelzés változatának átalakítási korlátozása

A mértékegység (UOM) változatonkénti átalakítása nem teljesen támogatott igény-előrejelzés létrheozása során, ha a készlet mértékegysége eltér az igény-előrejelzés mértékegységétől.

Az előrejelzés létrehozása (**Készlet mértékegység > igény-előrejelzés mértékegysége**) a termék mértékegység-konverzióját használja. Amikor az igény-előrejelzési létrehozásának múltbeli adatait tölti be, akkor a rendszer mindig a termék szintjének mértékegység-konverziót használja, amikor a készlet mértékegységéről az igény-előrejelzés mértékegységére konvertál, még akkor is, ha a változat szintjén definiáltak konverziókat.

Az előrejelzés engedélyezésének első része (**Igény-előrejelzés mértékegysége > készlet mértékegysége**) a termék mértékegység-konverzióját használja. Az előrejelzés engedélyezésének második része (**Készlet mértékegysége > értékesítés mértékegysége**) a változat mértékegység-konverzióját használja. Amikor a létrehozott igény-előrejelzés engedélyezve van, a készlet mértékegységéről az igény-előrejelzés mértékegységére való átváltást a termékszintű mértékegység-konverzió végrehajtásával történik. ugyanakkor a készletegység és az értékesítési mértékegység közti átváltás a változatszinten megadott konverziót veszi figyelembe.

Ne feledje, hogy az igény-előrejelzés mértékegységének nem kell, hogy konkrét jelentése legyen. Meghatározható „Igény-előrejelzési egységként” is. Mindegyik terméknél meghatározhatja, hogy a készlet mértékegység konverziója 1:1 legyen a készlet mértékegységével.

## <a name="additional-resources"></a>További erőforrások

[Igény-előrejelzés beállítása](demand-forecasting-setup.md)

[Statisztikai kiinduló előrejelzés létrehozása](generate-statistical-baseline-forecast.md)

[A kiinduló előrejelzés manuális kiigazítása](manual-adjustments-baseline-forecast.md)

[Módosított előrejelzés engedélyezése](authorize-adjusted-forecast.md)

[Előrejelzés pontosságának követése](monitor-forecast-accuracy.md)

[Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor](remove-historical-outliers-calculating-demand-forecast.md)

[Az igény-előrejelzési funkció kiterjesztése](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]