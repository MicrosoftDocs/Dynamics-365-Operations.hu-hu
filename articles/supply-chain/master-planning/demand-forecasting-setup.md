---
title: "Igény-előrejelzési beállítások"
description: "Ez a témakör az igény-előrejelzés használata előtt elvégzendő telepítési feladatokat mutatja be."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 974edd06460df4afe594b0a033a042b8c2763f7f
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="demand-forecasting-setup"></a>Igény-előrejelzési beállítások

[!INCLUDE [banner](../includes/banner.md)]

Ez a témakör az igény-előrejelzés használata előtt elvégzendő telepítési feladatokat mutatja be.  

A beállítási folyamat részeként a következő adatokat és paramétereket kell beállítani.

## <a name="item-allocation-key"></a>Cikkfelosztási kulcs
Egy cikkről, valamint annak különböző dimenzióiról csak akkor készül igény-előrejelzés, ha az része egy cikkfelosztási kulcsnak. Ez a szabály a nagy mennyiségű cikkek csoportosítására szolgál, így az igény-előrejelzések gyorsabban létrehozhatóak. A cikkfelosztási kulcs százalékértékét a rendszer nem veszi figyelembe az előrejelzések létrehozásakor. Az előrejelzések csak a korábbi adatok alapján lesznek létrehozva. 

Egy cikk és annak különböző dimenziói csak egy cikkfelosztási kulcs alá tartozhatnak, ha a cikkfelosztási kulcs az előrejelzés létrehozása során használatos. 

Raktározási egység (SKU) cikkfelosztási kulcshoz való hozzáadásához kattintson az **Alaptervezés** &gt; **Beállítás** &gt; **Igény-előrejelzés** &gt; **Cikkfelosztási kulcsok** menüpontra. Egy felosztási kulcsot egy cikkhez a **Cikkek társítása** oldal használatával tud hozzárendelni.

## <a name="intercompany-planning-groups"></a>Vállalatközi tervezőcsoportok
Az igény-előrejelzés több vállalatra kiterjedő előrejelzést hoz létre. A Microsoft Dynamics 365 for Finance and Operations rendszerben együtt tervezett vállalatok egy vállalatközi tervezési csoportba vannak csoportosítva. Ahhoz, hogy vállalatonként meg tudja határozni, melyik cikkfelosztási kulcsot vegye figyelembe a rendszer igény-előrejelzés esetén, rendeljen hozzá egy cikkfelosztási kulcsot a vállalatközi tervezési csoport tagjához. Ehhez nyissa meg az **Alaptervezés** &gt; **Beállítás** &gt; **Vállalatközi tervezőcsoportok** menüpontot. 

Alapértelmezés szerint, ha nincsenek cikkfelosztási kulcsok hozzárendelve a vállalatközi tervezési csoport tagjaihoz, az igény-előrejelzés az összes cikk összes cikkfelosztási kulcsához készül, az összes Dynamics 365 for Finance and Operationst használó vállalaton belül. További szűrési feltételek a vállalatokhoz és cikkfelosztási kulcsokhoz elérhetőek a **Statisztikai kiinduló előrejelzés létrehozása** oldalon. 

Ellenőrizze az előrejelzett cikkek számát. A felesleges cikkek pluszköltséggel járhatnak a Microsoft Azure Machine Learning használata során.

## <a name="demand-forecasting-parameters"></a>Igény-előrejelzési paraméterek
Az igény-előrejelzés paramétereinek beállításához lépjen az **Alaptervezés** &gt; **Beállítás** &gt; **Igény-előrejelzési paraméterek** oldalra. Mivel az igény-előrejelzés működése vállalatközi, ezért a telepítse globális. Ez azt jelenti, hogy a beállítása minden vállalatra érvényes. 

Az igény-előrejelzés az előrejelzés során mennyiségeket használ. Emiatt azt, hogy a mennyiség milyen egységben legyen megadva, specifikálni kell az **Igény-előrejelzés egysége** mezőben. A mértékegység egyedisége biztosítja, hogy az összesítés és százalékeloszlás értelmezhető legyen. További információkért az összesítésről és százalékeloszlásról az alábbi oldalon olvasható: [Manuális módosítások a kiinduló előrejelzésben](manual-adjustments-baseline-forecast.md). Bizonyosodjon meg róla, hogy minden, az igény-előrejelzésben használt SKU mértékegységhez tartozik egy átváltási szabály, a használt mértékegység és az általános előrejelzési mértékegység között. Az előrejelzés létrehozása közben azok a cikkek, melyeknek nincs mértékegysége naplózásra kerülnek, így később könnyedén korrigálható a beállítás. 

Az igény-előrejelzéssel függő és független előrejelzés is készíthető. Ha például csak az **Eladási rendelés** van bejelölve, és az összes cikk, ami az igény-előrejelzéshez szükséges el van adva, a rendszer független igényt számít. Azonban fontos alösszetevőket lehet a cikkfelosztási kulcshoz adni. Ezek szerepelnek az igény-előrejelzésben. Ebben az esetben ha a **Termelési sor** be van jelölve, függő előrejelzés kerül kiszámításra. 

Kétféleképpen hozható létre kiinduló előrejelzés Dynamics 365 for Finance and Operationsben. Használhat előrejelzési modellt az előzményadatok mellett, vagy másolja át az előzményadatokat az előrejelzésbe. Az **Előrejelzés-generálási stratégia** mezőben választhat a két módszer közül. Előrejelzési modellek használatához jelölje be az **Azure Machine Learning** mezőt. 

Az **Előrejelzési dimenziók** menüpontra kattintva, ami az **Igény-előrejelzési paraméterek** lap bal oldalán található, kijelölheti az igény-előrejelzés létrehozásakor használandó előrejelzés dimenziókat. Az előrejelzési dimenzió az előrejelzés részletességi szintjét jelzi. Vállalat, a hely és a cikkfelosztási kulcs kötelező előrejelzési dimenziók, de létrehozhat előrejelzést a raktár, készletállapot, vevőcsoport, vevőkód, ország/terület, állam, és a cikk illetve minden cikk szerint is. 

Az igény-előrejelzéshez bármikor hozzáadhat új előrejelzési dimenziókat. A listából, igény szerint, el lehet távolítani előrejelzési dimenziókat. Azonban a manuális módosítások elvesznek, ha hozzáad vagy eltávolít egy előrejelzési dimenziót. 

Nem minden cikk viselkedik ugyan úgy, igény-előrejelzés szempontjából. Lehet hasonló cikkeket egy cikkfelosztási kulcs alá rendelni, valamint olyan jellemzőket, mint a tranzakció típusa vagy az előrejelzés fajtája, cikkfelosztási kulcsonként is megadhatóak. Kattintson a **Cikkfelosztási kulcsok** menüre az **Igény-előrejelzési paraméterek** lap bal oldalán. 

Az előrejelzés létrehozásához a Dynamics 365 for Finance and Operations egy gépi tanulási webszolgáltatást használ. A szolgáltatáshoz való kapcsolódáshoz meg kell adnia a Dynamics 365 for Finance and Operations rendszerben a következő adatokat, ha bejelentkezik a Microsoft Azure Machine Learning Studióba:

-   Az API programozási felület (Telephony Alkalmazásprogramozási Felület) beállítása
-   URL webszolgáltatási végpont
-   Azure tárfiók neve
-   Azure tárfiók kulcsa

**Megjegyzés:** az Azure tárolási számlanév és kulcs csak az egyéni tárolási fiók használata esetén szükséges. Ha a helyszíni verziót használja, rendelkeznie kell egy egyéni tárolási fiókkal az Azure-on, hogy a gépi tanulási szolgáltatás elérhesse az előzményadatokat. 

Igény-előrejelzések létrehozásánál használhat saját szolgáltatást a Machine Learning Studio vagy a Dynamics 365 for Finance and Operations igény-előrejelzési kísérletek segítségével. A Dynamics 365 for Finance and Operations igény-előrejelzési kísérletek webes szolgáltatásként való telepítéséhez a Dynamics 365 for Finance and Operationsön belül talál útmutatást. Az **Igény-előrejelzési paraméterek** lapon kattintson az **Azure Machine Learning** fülre.

## <a name="settings-for-the-finance-and-operations-demand-forecasting-machine-learning-service"></a>A Dynamics 365 for Finance and Operations igény-előrejelzési gépi tanulási szolgáltatásának beállításai
A Dynamics 365 for Finance and Operations igény-előrejelzési szolgáltatása beállítható paramétereinek megtekintéséhez lépjen az **Alaptervezés** &gt; **Beállítás** &gt; **Igény-előrejelzés** &gt; **Előrejelzési algoritmus paraméterei** menüpontra. Az **Előrejelzési algoritmus paraméterei** lapon láthatóak a paraméterek alapértelmezett értékei. Ezeket a paramétereket a felülírhatja az **Igény-előrejelzési paraméterek** oldalon. Használja az **Általános** lapot, hogy a paramétereket globálisan felülírja, vagy használja a **Cikkfelosztási kulcsok** lapot, hogy cikkfelosztási kulcsonként módosítsa a paramétereket. Ha a cikkfelosztási kulcsokhoz tartozó paraméterek változnak, azok csak az adott cikkfelosztási kulcshoz tartozó cikkeket érintik.

<a name="see-also"></a>Lásd még
--------

[Igény-előrejelzés – bevezetés](introduction-demand-forecasting.md)

[Statisztikai kiinduló előrejelzés generálása](generate-statistical-baseline-forecast.md)

[A kiinduló előrejelzés manuális kiigazítása](manual-adjustments-baseline-forecast.md)




