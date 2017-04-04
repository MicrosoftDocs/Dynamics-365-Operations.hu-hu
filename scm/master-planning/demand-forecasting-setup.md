---
title: "Igény-előrejelzési beállítások"
description: "Ez a témakör az igény-előrejelzés használata előtt elvégzendő telepítési feladatokat mutatja be."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: f629329f4f50bd7c8edcfd70641bace01a1c53aa
ms.lasthandoff: 03/31/2017


---

# <a name="demand-forecasting-setup"></a>Igény-előrejelzési beállítások

Ez a témakör az igény-előrejelzés használata előtt elvégzendő telepítési feladatokat mutatja be.  

A beállítási folyamat részeként a következő adatokat és paramétereket kell beállítani.

## <a name="item-allocation-key"></a>Cikkfelosztási kulcs
Egy cikkről, valamint annak különböző dimenzióiról csak akkor készül igény-előrejelzés, ha az része egy cikkfelosztási kulcsnak. Ez a szabály, hogy az igény-előrejelzések gyorsabban hozható létre elem, csoport nagyszámú érvényesül. A cikk felosztási kulcs százalék igény-előrejelzések létrehozásakor figyelmen kívül hagyja. Az előrejelzések csak a korábbi adatok alapján lesznek létrehozva. 

Egy cikk és annak különböző dimenziói csak egy cikkfelosztási kulcs alá tartozhatnak, ha a cikkfelosztási kulcs az előrejelzés létrehozása során használatos. 

Cikkfoglalási kulcs egy leltári egység (SKU) hozzáadni, keresse fel **fő tervezési**&gt;**a telepítő**&gt;**igény-előrejelzés**&gt;**cikk felosztási kulcsok**. Egy felosztási kulcsot egy cikkhez a **Cikkek társítása** oldal használatával tud hozzárendelni.

## <a name="intercompany-planning-groups"></a>Vállalatközi tervezőcsoportok
Az igény-előrejelzés több vállalatra kiterjedő előrejelzést hoz létre. A Microsoft Dynamics 365 műveletekhez vállalatok közösen tervezett egy vállalatközi tervezőcsoport vannak csoportosítva. Adja meg, mely cikkfelosztási kulcsok figyelembe kell venni az igény előrejelzésére, vállalatonként cikkfoglalási kulcs társítása a vállalatközi tervezési csoport tagjának nyissa meg a **fő tervezési**&gt;**a telepítő**&gt;**vállalatközi tervezési csoportok**. 

Alapértelmezés szerint ha nem cikkfelosztási kulcsok rendelt vállalatközi tervezési csoport tagjai igény-előrejelzés számítása minden cikkhez rendelt összes cikkfelosztási kulcsok az összes Dynamics 365 műveletek vállalatok számára. További szűrési feltételek a vállalatokhoz és cikkfelosztási kulcsokhoz elérhetőek a **Statisztikai kiinduló előrejelzés létrehozása** oldalon. 

Ellenőrizze az előrejelzett cikkek számát. A felesleges cikkek pluszköltséggel járhatnak a Microsoft Azure Machine Learning használata során.

## <a name="demand-forecasting-parameters"></a>Igény-előrejelzési paraméterek
Igény-előrejelzés paraméterek beállításához nyissa meg **fő tervezési**&gt;**telepítő**&gt;**a kereslet előrejelzése paraméterek**. Mivel az igény-előrejelzés működése vállalatközi, ezért a telepítse globális. Ez azt jelenti, hogy a beállítása minden vállalatra érvényes. 

Az igény-előrejelzés az előrejelzés során mennyiségeket használ. Emiatt azt, hogy a mennyiség milyen egységben legyen megadva, specifikálni kell az **Igény-előrejelzés egysége** mezőben. A mértékegység egyedisége biztosítja, hogy az összesítés és százalékeloszlás értelmezhető legyen. További információkért az összesítésről és százalékeloszlásról az alábbi oldalon olvasható: [Manuális módosítások a kiinduló előrejelzésben](manual-adjustments-baseline-forecast.md). Bizonyosodjon meg róla, hogy minden, az igény-előrejelzésben használt SKU mértékegységhez tartozik egy átváltási szabály, a használt mértékegység és az általános előrejelzési mértékegység között. Az előrejelzés létrehozása közben azok a cikkek, melyeknek nincs mértékegysége naplózásra kerülnek, így később könnyedén korrigálható a beállítás. 

Az igény-előrejelzéssel függő és független előrejelzés is készíthető. Ha például csak az **Eladási rendelés** van bejelölve, és az összes cikk, ami az igény-előrejelzéshez szükséges el van adva, a rendszer független igényt számít. Azonban fontos alösszetevőket lehet a cikkfelosztási kulcshoz adni. Ezek szerepelnek az igény-előrejelzésben. Ebben az esetben ha a **Termelési sor** be van jelölve, függő előrejelzés kerül kiszámításra. 

Dynamics 365 műveletek előrejelzése az alapterv létrehozásának két módja van. Használhat előrejelzési modellt az előzményadatok mellett, vagy másolja át az előzményadatokat az előrejelzésbe. Az **Előrejelzés-generálási stratégia** mezőben választhat a két módszer közül. Előrejelzési modellek használatához jelölje be az **Azure Machine Learning** mezőt. 

Az **Előrejelzési dimenziók** menüpontra kattintva, ami az **Igény-előrejelzési paraméterek** lap bal oldalán található, kijelölheti az igény-előrejelzés létrehozásakor használandó előrejelzés dimenziókat. Az előrejelzési dimenzió az előrejelzés részletességi szintjét jelzi. Vállalat, a hely és a cikkfelosztási kulcs kötelező előrejelzési dimenziók, de létrehozhat előrejelzést a raktár, készletállapot, vevőcsoport, vevőkód, ország/terület, állam, és a cikk illetve minden cikk szerint is. 

Az igény-előrejelzéshez bármikor hozzáadhat új előrejelzési dimenziókat. A listából, igény szerint, el lehet távolítani előrejelzési dimenziókat. Azonban a manuális módosítások elvesznek, ha hozzáad vagy eltávolít egy előrejelzési dimenziót. 

Nem minden cikk viselkedik ugyan úgy, igény-előrejelzés szempontjából. Lehet hasonló cikkeket egy cikkfelosztási kulcs alá rendelni, valamint olyan jellemzőket, mint a tranzakció típusa vagy az előrejelzés fajtája, cikkfelosztási kulcsonként is megadhatóak. Kattintson a **Cikkfelosztási kulcsok** menüre az **Igény-előrejelzési paraméterek** lap bal oldalán. 

Az előrejelzés létrehozása, Dynamics 365 műveletek gép tanulás webszolgáltatást használ. A szolgáltatáshoz való kapcsolódáshoz meg kell adnia Dynamics 365 műveletek a következő információkat, ha bejelentkezik Microsoft Azure gép tanulás Studio:

-   Az API programozási felület (Telephony Alkalmazásprogramozási Felület) beállítása
-   URL webszolgáltatási végpont
-   Azure tárfiók neve
-   Azure tárfiók kulcsa

**Megjegyzés:** az Azure tárolási számlanév és kulcs csak az egyéni tárolási fiók használata esetén szükséges. Ha a helyszíni verziójában telepíti, rendelkeznie kell egy egyéni tároló fiók Azure, így a gép tanulás szolgáltatást is elérheti a történelmi adatok. 

Igény-előrejelzéseket létrehozására saját szolgáltatási műveletek igény előrejelzésére kísérletek gép tanulás Studio vagy a Dynamics 365 használatával telepítheti. A Dynamics 365 műveletek igény kísérletek előrejelzés web szolgáltatás telepítésére vonatkozó útmutatás is elérhető Dynamics 365 műveletekhez. Az **Igény-előrejelzési paraméterek** lapon kattintson az **Azure Machine Learning** fülre.

## <a name="settings-for-the-dynamics-365-for-operations-demand-forecasting-machine-learning-service"></a>A Dynamics 365 műveletek beállításainak igény-előrejelzési gép tanulás szolgáltatás
A műveletek igény-előrejelzési szolgáltatást a Dynamics 365 konfigurálható paraméterek megtekintéséhez keresse fel **Alaptervezés**&gt;**telepítő**&gt;**igény-előrejelzés**&gt;**előrejelzés algoritmus paraméterei**. A **algoritmus paraméterei előrejelzés** lap megjeleníti az alapértelmezett értékeket a paraméterek. Felülírhatja ezeket a paramétereket a a **a kereslet előrejelzése paraméterek** oldalon. Használja az **Általános** lapot, hogy a paramétereket globálisan felülírja, vagy használja a **Cikkfelosztási kulcsok** lapot, hogy cikkfelosztási kulcsonként módosítsa a paramétereket. Ha a cikkfelosztási kulcsokhoz tartozó paraméterek változnak, azok csak az adott cikkfelosztási kulcshoz tartozó cikkeket érintik.

<a name="see-also"></a>Lásd még
--------

[Introduction to demand forecasting](introduction-demand-forecasting.md)

[Generating a statistical baseline forecast](generate-statistical-baseline-forecast.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)


