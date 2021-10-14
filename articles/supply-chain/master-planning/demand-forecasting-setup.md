---
title: Igény-előrejelzési beállítások
description: Ez a témakör az igény-előrejelzés használata előtt elvégzendő telepítési feladatokat mutatja be.
author: ChristianRytt
ms.date: 08/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f71d7a1ef2e8b6a113124d3fb17f1681d62aed9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575752"
---
# <a name="demand-forecasting-setup"></a>Igény-előrejelzési beállítások

[!include [banner](../includes/banner.md)]

Ez a témakör az igény-előrejelzés használata előtt elvégzendő telepítési feladatokat mutatja be.  

A beállítási folyamat részeként a következő adatokat és paramétereket kell beállítani.

## <a name="item-allocation-keys"></a>Cikkfelosztási kulcsok

Egy cikkről, valamint annak különböző dimenzióiról csak akkor készül igény-előrejelzés, ha az része egy cikkfelosztási kulcsnak. Ez a szabály a nagy mennyiségű cikkek csoportosítására szolgál, így az igény-előrejelzések gyorsabban létrehozhatóak. A cikkfelosztási kulcs százalékértékét a rendszer nem veszi figyelembe az előrejelzések létrehozásakor. Az előrejelzések csak a korábbi adatok alapján lesznek létrehozva.

Egy cikk és annak különböző dimenziói csak egy cikkfelosztási kulcs alá tartozhatnak, ha a cikkfelosztási kulcs az előrejelzés létrehozása során használatos.

Raktározási egység (SKU) cikkfelosztási kulcshoz való hozzáadásához kattintson az **Alaptervezés \> Beállítás \> Igény-előrejelzés \> Cikkfelosztási kulcsok** menüpontra. Egy felosztási kulcsot egy cikkhez a **Cikkek társítása** oldal használatával tud hozzárendelni.

## <a name="intercompany-planning-groups"></a>Vállalatközi tervezőcsoportok

Az igény-előrejelzés több vállalatra kiterjedő előrejelzést hoz létre. A Dynamics 365 Supply Chain Management rendszerben együtt tervező vállalatok egy vállalatközi tervezési csoportba vannak csoportosítva. Ahhoz, hogy vállalatonként meg tudja határozni, melyik cikkfelosztási kulcsot vegye figyelembe a rendszer igény-előrejelzés esetén, rendeljen hozzá egy cikkfelosztási kulcsot a vállalatközi tervezési csoport tagjához. Ehhez nyissa meg az **Alaptervezés \> Beállítás \> Vállalatközi tervezőcsoportok** menüpontot.

Alapértelmezés szerint, ha nincsenek cikkfelosztási kulcsok hozzárendelve a vállalatközi tervezési csoport tagjaihoz, az igény-előrejelzés az összes cikk összes cikkfelosztási kulcsához készül, az összes vállalaton belül. További szűrési feltételek a vállalatokhoz és cikkfelosztási kulcsokhoz elérhetőek a **Statisztikai kiinduló előrejelzés létrehozása** oldalon.

Ellenőrizze az előrejelzett cikkek számát. A felesleges cikkek pluszköltséggel járhatnak a Microsoft Azure Machine Learning használata során.

## <a name="demand-forecasting-parameters"></a>Igény-előrejelzési paraméterek

Az igény-előrejelzés paramétereinek beállításához lépjen az **Alaptervezés \> Beállítás \> \> Igény-előrejelzés \> Igény-előrejelzési paraméterek** oldalra. Mivel az igény-előrejelzés működése vállalatközi, ezért a telepítse globális. Ez azt jelenti, hogy a beállítása minden vállalatra érvényes.

Az igény-előrejelzés az előrejelzés során mennyiségeket használ. Emiatt azt, hogy a mennyiség milyen egységben legyen megadva, specifikálni kell az **Igény-előrejelzés egysége** mezőben. A mértékegység egyedisége biztosítja, hogy az összesítés és százalékeloszlás értelmezhető legyen. További információkért az összesítésről és százalékeloszlásról az alábbi oldalon olvasható: [Manuális módosítások a kiinduló előrejelzésben](manual-adjustments-baseline-forecast.md). Bizonyosodjon meg róla, hogy minden, az igény-előrejelzésben használt SKU mértékegységhez tartozik egy átváltási szabály, a használt mértékegység és az általános előrejelzési mértékegység között. Az előrejelzés létrehozása közben azok a cikkek, melyeknek nincs mértékegysége naplózásra kerülnek, így később könnyedén korrigálható a beállítás.

Az igény-előrejelzéssel függő és független előrejelzés is készíthető. Ha például csak az **Eladási rendelés** van bejelölve, és az összes cikk, ami az igény-előrejelzéshez szükséges el van adva, a rendszer független igényt számít. Azonban fontos alösszetevőket lehet a cikkfelosztási kulcshoz adni. Ezek szerepelnek az igény-előrejelzésben. Ebben az esetben ha a **Termelési sor** be van jelölve, függő előrejelzés kerül kiszámításra.

Kétféleképpen hozható létre kiinduló előrejelzés. Használhat előrejelzési modellt az előzményadatok mellett, vagy másolja át az előzményadatokat az előrejelzésbe. Az **Előrejelzés-generálási stratégia** mezőben választhat a két módszer közül. Előrejelzési modellek használatához jelölje be az **Azure Machine Learning** mezőt.

Az **Előrejelzési dimenziók** menüpont kiválasztásával, amely az **Igény-előrejelzési paraméterek** lap bal oldalán található, kijelölheti az igény-előrejelzés létrehozásakor használandó előrejelzés dimenziókat. Az előrejelzési dimenzió az előrejelzés részletességi szintjét jelzi. Vállalat, a hely és a cikkfelosztási kulcs szükséges előrejelzési dimenziók, de létrehozhat előrejelzést a raktár, készletállapot, vevőcsoport, vevőkód, ország/régió, állam, és a cikk, illetve minden cikk szerint is.

Az igény-előrejelzéshez bármikor hozzáadhat új előrejelzési dimenziókat. A listából, igény szerint, el lehet távolítani előrejelzési dimenziókat. Azonban a manuális módosítások elvesznek, ha hozzáad vagy eltávolít egy előrejelzési dimenziót.

Nem minden cikk viselkedik ugyanúgy igény-előrejelzés szempontjából. Lehet hasonló cikkeket egy cikkfelosztási kulcs alá rendelni, valamint olyan jellemzőket, mint a tranzakció típusa vagy az előrejelzés fajtája, cikkfelosztási kulcsonként is megadhatóak. Válassza ki a **Cikkfelosztási kulcsok** menüpontot az **Igény-előrejelzési paraméterek** lap bal oldalán.

Az előrejelzés létrehozásához a Supply Chain Management egy gépi tanulási webszolgáltatást használ. A szolgáltatáshoz való kapcsolódáshoz meg kell adnia a következő adatokat, ha bejelentkezik a Microsoft Azure Machine Learning Studio (klasszikus) termékbe:

- Az API programozási felület (Telephony Alkalmazásprogramozási Felület) beállítása
- URL webszolgáltatási végpont
- Azure tárfiók neve
- Azure tárfiók kulcsa

> [!NOTE]
> Az Azure tárolási számlanév és kulcs csak egyéni tárolási fiók használata esetén szükséges. Ha a helyszíni verziót használja, rendelkeznie kell egy egyéni tárolási fiókkal az Azure-on, hogy a gépi tanulási szolgáltatás elérhesse az előzményadatokat.

Igény-előrejelzések létrehozásánál használhat saját szolgáltatást a Machine Learning Studio vagy a Supply Chain Management igény-előrejelzési kísérletek segítségével. A Finance and Operations igény-előrejelzési kísérletek webes szolgáltatásként való telepítéséhez a Supply Chain Management alkalmazáson belül talál útmutatást. Az **Igény-előrejelzési paraméterek** lapon nyissa meg az **Azure Machine Learning** fület.

## <a name="settings-for-the-demand-forecasting-machine-learning-service"></a>A igény-előrejelzés gépitanulás-szolgáltatás beállításai

Az igény-előrejelzési szolgáltatás beállítható paramétereinek megtekintéséhez lépjen az **Alaptervezés \> Beállítás \> Igény-előrejelzés \> Előrejelzési algoritmus paraméterei** menüpontra. Az **Előrejelzési algoritmus alapértelmezett paraméterei** lapon láthatóak a paraméterek alapértelmezett értékei. Ezeket a paramétereket az **Alaptervezés \> Beállítás \> Igény-előrejelzés \> Igény-előrejelzési paraméterek** menüpontban lehet felülírni, ahol a következőket teheti:

- Az **Általános** lapon globálisan felülírhatja a paramétereket.
- A **Cikkfelosztási kulcsok lapon** felülírhatja a cikkfelosztási kulcsonkénti paramétereket. Ha a cikkfelosztási kulcsokhoz tartozó paraméterek változnak, azok csak az adott cikkfelosztási kulcshoz tartozó cikkeket érintik.

### <a name="forecast-algorithm-parameters"></a>Az előrejelzési algoritmus paraméterei

Az **Igény-előrejelzési paraméterek** lap **Cikkfelosztási kulcs** lapján az **Előrejelzési algoritmus paraméterei** gyorslapon rendelhet előrejelzési algoritmusparamétereket a bal oldali rácsban jelenleg kijelölt cikkfelosztási kulcshoz. Az eszköztár **Hozzáadás** és **Eltávolítás** gombjaival lehet létrehozni a szükséges paramétergyűjteményt. A lista minden paramétere számára válasszon a **Név** mezőben a következő értékek közül, majd adjon meg egy megfelelő értéket az **Érték** mezőben:

- **Megbízhatósági szint százaléka** – A megbízhatósági intervallum olyan értékek tartományából áll, amelyek az igény-előrejelzés jó becslését adják. A 95 %-os megbízhatósági szint azt jelenti, hogy 5 % a kockázata annak, hogy az igény-előrejelzés eredménye a megbízhatósági intervallum tartományán kívül esik.
- **Szezonalitás kényszerítése** – Megadja, hogy a modellt egy bizonyos típusú szezonalitási típusra szeretné-e kényszeríteni. Csak az ARIMA és ETS lehetőségekre vonatkozik. Lehetőségek: AUTÓ (alapértelmezett), NINCS, ADDITÍV, SZORZÓ.
- **Előrejelzési modell** – Beállítások: ARIMA, ETS, STL, ETS+ARIMA, ETS+STL, MIND. A legjobb illeszkedésű modellez válassza a **MIND** lehetőséget.
- **Maximális előre jelzett érték** – Az előrejelzésekhez használandó maximális értéket adja meg. Formátum: + 1E[n] vagy numerikus állandó.
- **Minimális előre jelzett érték** – Az előrejelzésekhez használandó minimális értéket adja meg. Formátum: -1E[n] vagy numerikus állandó.
- **Hiányzó érték-helyettesítés** – Meghatározza a múltbeli adatok hiányosságainak kitöltésének módját. Beállítások: numerikus érték, ÁTLAG, ELŐZŐ, INTERPOLÁLT LINEÁRIS, INTERPOLÁCIÓS POLINOM.
- **Hiányzó érték-helyettesítésihatóköre** – Megadja, hogy az érték-helyettesítés csak az egyéni granularítású attribútumok dátumtartományára vagy a teljes adathalmazra vonatkozik-e. A korábbi adatokból hiányzó adatok kitöltésekor a rendszer által használt dátumtartomány megállapítására a következő lehetőségek állnak rendelkezésre:

  - GLOBÁLIS – A rendszer a részletességi attribútumok teljes dátumtartományát használja.
  - HISTORY_DATE_RANGE – A rendszer a **Statisztikai kiinduló előrejelzés létrehozása** párbeszédpanel **Előzményhorizont** mezőcsoportjának a **Kezdő dátum** és **Záró dátum** mezője által meghatározott dátumtartományt használja.
  - GRANULARITY_ATTRIBUTE – A rendszer a jelenleg feldolgozott részletességi attribútum dátumtartományát használja.

  > [!NOTE]
  > A részletességi attribútum az előrejelzési dimenziók olyan kombinációja, amelyen az előrejelzést elvégzik. Az előrejelzési dimenziókat az **Igény-előrejelzési paraméterek** oldalon definiálhatja.

- **Szezonalitás tipp** – A szezonális adatokhoz az előrejelzési pontosság javítása érdekében adjon meg egy tippet az előrejelzési modellhez. Formátum: egész szám, amely az időszakok számát, jelenti, amikor egy minta ismétlése szükséges. Például a "6" értéket írja be a 6 havonta önmagukat ismétlő adatokhoz.
- **Tesztkészlet mérete százalékban** – Az előrejelzés pontosságának számításához tesztkészletként használni kívánt előzményadatok százaléka.

## <a name="additional-resources"></a>További erőforrások

- [Igény-előrejelzés áttekintése](introduction-demand-forecasting.md)
- [Statisztikai kiinduló előrejelzés létrehozása](generate-statistical-baseline-forecast.md)
- [A kiinduló előrejelzés manuális kiigazítása](manual-adjustments-baseline-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
