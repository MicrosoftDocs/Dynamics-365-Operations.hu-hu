---
title: "Készpénzáttekintés Power BI-tartalom"
description: "Ez a témakör a Készpénzáttekintés Power BI-tartalmat ismerteti. Leírja, hogy hogyan kell hozzáférni a tartalomcsomagban szereplő jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban."
author: saraschi2
manager: AnnBe
ms.date: 06/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30T00:00:00.000Z
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 367fe61492648ee3ee629a8121e664dfaa0c6c99
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---

# <a name="cash-overview-power-bi-content"></a>Készpénzáttekintés Power BI-tartalom

[!include[banner](../includes/banner.md)]

Ez a témakör a **Készpénzáttekintés** Microsoft Power BI-tartalmat ismerteti. Leírja, hogy hogyan kell hozzáférni a tartalomcsomagban szereplő jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="overview"></a>Áttekintés

A **Készpénzáttekintés** Power BI tartalom azon személyeknek szól, akik a szervezetük készpénzéért felelősek. A **Készpénzáttekintés** Power BI-tartalom áttekintést nyújt a pénzforgalmáról. Emellett előrejelzéseket kínál, melyek segíthetnek, hogy jobb döntéseket hozzon, és ezáltal javíthassa a pénzforgalom állapotát. A készpénzt jogi személy, pénznem és bankszámla szerint elemezheti, hogy jobban megértse a többleteket és hiányokat.

## <a name="accessing-the-power-bi-content"></a>Power BI-tartalom elérése

Ha a Dynamics 365 for Finance and Operations, Enterprise edition 2017. júliusi frissítését használja, akkor a **Készpénzáttekintés** Power BI-tartalom jelentései a **Készpénzáttekintés** és a **Bankszámla kezelése** munkaterületen jelennek meg.

Ha adatokkal együtt szeretné megtekinteni a pénzforgalmi előrejelzések jelentéseit, akkor először futtatnia kell az előrejelzés számítási folyamatát a Készpénz- és bankkezelés terület **Pénzforgalmi előrejelzések kiszámítása** funkciójánál.  Ezt végre kell hajtani az előrejelzésben szereplő mindegyik vállalat esetén.  Ezt követően frissítenie kell a LedgerCovLiquidityMeasurement összesített mértéket az **Entitástár** oldalon.  

Bemutató céllal felvehet pénzforgalom-előrejelzési bemutató adatokat a Demóadatok modul **Adatok generálása** oldaláról.  Ez a szkript adatokat szúr be a pénzforgalmi előrejelzés táblázataiba annak érdekében, hogy gyorsan kitöltse azokat a jelentések számára szükséges adatokkal.  Ez a modul csak akkor érhető el, ha a bemutató adatmodellt telepítették a környezetnél. 

## <a name="reports-that-are-included-in-the-power-bi-content"></a>A Power BI-tartalomhoz tartozó jelentések
A következő táblázat ismerteti a **Készpénzáttekintés** Power BI-tartalom egyes jelentésoldalain található mutatókat.

| Jelentés                                | Tartalom |
|---------------------------------------|----------|
| Készpénzáttekintés – minden vállalat         | <ul><li>Pénzbeáramlások és pénzkiáramlások a rendszer pénznemében</li><li>Előre jelzett pénznemegyenlegek</li><li>Összesített egyenleg a rendszer pénznemében</li><li>Egyenleg jogi személy szerint</li><li>Aznapi tényleges és előrejelzett egyenleg a bankszámla pénznemében</li></ul> |
| Készpénzáttekintés – jelenlegi vállalat       | <ul><li>Pénzbeáramlások és pénzkiáramlások a könyvelési pénznemben</li><li>Előre jelzett pénznemegyenlegek</li><li>Összesített egyenleg a könyvelési pénznemben</li><li>Aznapi tényleges és előrejelzett egyenleg a bankszámla pénznemében</li></ul> |
| Pénzforgalmi előrejelzés – összes vállalat    | <ul><li>Pénzbeáramlások és pénzkiáramlások a rendszer pénznemében</li><li>Napi előrejelzés összegzése</li><li>Előrejelzés részletei</li></ul> |
| Pénzforgalmi előrejelzés – pénznem vállalata | <ul><li>Pénzbeáramlások és pénzkiáramlások a könyvelési pénznemben</li><li>Napi előrejelzés összegzése</li><li>Előrejelzés részletei</li></ul> |
| Pénznem előrejelzése                     | <ul><li>Előre jelzett pénznemegyenlegek</li><li>Napi pénznem összegzése</li><li>Előrejelzés részletei</li></ul> |
| Banki egyenlegek                         | <ul><li>Összesített egyenleg a rendszer pénznemében</li><li>Egyenleg jogi személy szerint</li><li>Aznapi tényleges és előrejelzett egyenleg a bankszámla pénznemében</li><li>Egyenleg bankszámla szerint</li><li>Egyenleg pénznemenként</li></ul> |

## <a name="extending-the-power-bi-content"></a>Power BI-tartalom kibővítése
A Lifecycle Services (LCS) szolgáltatásban elérhető tartalmi csomagokkal nagyszerű elemzési lehetőségeket nyújthat azoknak, akik nem jelentkeztek be a Dynamics 365 szolgáltatásba. Ezek a tartalomcsomagok módosíthatók, hogy más jelentéseket vagy megjelenítéseket is tartalmazhassanak, majd elemzés céljából közzétehetők a Power BI.com-bérlőjénél. 

A **Készpénzáttekintés** Power BI-tartalom a Közös eszközök tárában található az LCS szolgáltatásban. A tartalom letöltésére és szervezeténél való megvalósítására vonatkozó további információért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](/dynamics365/unified-operations/dev-itpro/analytics/power-bi-content-microsoft-partners). Ha meg szeretne tekinteni egy demót, amely bemutatja a Power BI-tartalmak megvalósítását, lásd a [Power BI-tartalom a Microsofttól és az Ön partnereitől a Dynamics Lifecycle Services szolgáltatásban](https://mix.office.com/watch/9puyb1b2xs1w) című részt (Office Mix).

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése

A következő táblázat megjeleníti azokat az entitásokat, amelyeken a **Készpénzáttekintés** Power BI-tartalom alapul.

| Entitás                                                                          | Tartalom |
|---------------------------------------------------------------------------------|----------|
| LedgerCovLiquidityMeasurement\_Vállalat                                          | Vállalatok a jelentések szűréséhez |
| LedgerCovLiquidityMeasurement\_Dátum                                             | Dátumok a jelentések szűréséhez |
| LedgerCovLiquidityMeasurement\_LedgerCovForecastActual                          | Jelenlegi banki egyenleg és az utolsó előre jelzett banki egyenleg |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidity                               | Előrejelzett tranzakció részletes adatai |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceCompany    | Összegzett pénzbevételek, kiadások és egyenlegek az egyes vállalatok könyvelési pénznemében |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceEnterprise | Összegzett pénzbevételek, kiadások és egyenlegek az összes vállalatnál a rendszer pénznemében |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityTransactionCurrency            | Összegzett nettó tranzakciós összeg és devizaegyenleg a tranzakciós pénznem használatával |

Ezeket az entitásokat számított mértékek létrehozására használták az adatmodellben. E kiszámított mértékek aztán a diagramok és a **Készpénzáttekintés** Power BI-tartalomban használt jelentések kiszámításához használatosak. Ha szeretné felvenni a további számításokat a jelentésekbe és irányítópultokba, töltse le és módosítsa a Power BI-fájlt a LCS-ből. Ez a fájl azon alapértelmezett adatmodell, amelyet a tartalom létrehozásához használtak. Miután elvégezte a módosításokat, szervezeti tartalmat és a felvett adatokat tartalmazó irányítópultokat hozhat létre.


