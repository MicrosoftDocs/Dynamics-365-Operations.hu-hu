---
title: Beszerzési és ráfordítási elemzés Power BI tartalom
description: Ez a témakör a Beszerzési kiadások elemzése Power BI tartalom modul tartalmát ismerteti. Leírja, hogy hogyan kell hozzáférni a tartalomban szereplő jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.
author: FrankDahl
manager: AnnBe
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3f556cf2e506c57e465c2a86485d2cdd4cf8b65e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680614"
---
# <a name="purchase-spend-analysis-power-bi-content"></a>Beszerzési és ráfordítási elemzés Power BI tartalom

[!include [banner](../includes/banner.md)]

Ez a témakör a **Beszerzési kiadások elemzése** Microsoft Power BI tartalom modul tartalmát ismerteti. Leírja, hogy hogyan kell hozzáférni a Power BI-jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához korábban használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="overview"></a>Áttekintés

A **Beszerzési kiadások elemzése** Power BI-tartalom a beszerzési vezetők és olyan vezetők segítségével készült, akik a beszerzési kiadások költségvetéésének nyomon követésért felelősek. A vezetők az alábbi módokon elemezhetik a beszerzési költségeket:

- Az év megadott napjáig tartó beszerzések (szállítói csoport és az egyes szállítók , beszerzési kategória és egyes termékek, valamint a szállító helye szerint)
- Egy éves időszak beszerzési változásai (szállítói csoport és a beszerzési kategória szerint)

A tartalom beszerzési tranzakciós adatokat használ, és egyrészt összesített adatokat nyújt a vállalati szintű beszerzési számokról, másrészt a kiadások szállító és termék szerinti lebontását kínálja. A jelentések kiemelik a beszerzési kiadások időbeli változásait. Ezért a jelentések riasztásra használhatók a menedzserek számára a kiadások pozitív és negatív trendjeiről az egyes szállítókra és termékekre nézve. Ezenkívül diagramok jelenítik meg a beszerzési kiadásokat a különböző beszerzési kategóriákra és szállítói csoportokra nézve. Ezért a kategória- és regionális vezetők a diagramok segítségével a kiadások viselkedési változásait azonosíthatják.

## <a name="accessing-the-power-bi-content"></a>A Power BI tartalom elérése
A **Beszerzési és ráfordítási elemzés** Power BI tartalom a **Beszerzési és ráfordítási elemzés** oldalon látható (**Beszerzés és forrás** \> **Lekérdezések és jelentések** \> **Beszerzési teljesítményelemzés** \> **Beszerzési és ráfordítási elemzés**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mérőszámok, amelyek a Power BI tartalomban szerepelnek
A **Beszerzési kiadások elemzése** Power BI tartalomcsomag tartalmaz egy jelentést, amely metrikák készletéből áll. Ezek a metrikák mozaikok, táblázatok és diagramok formájában jelennek meg. 

Az alábbi szakaszok tartalmazzák a megjelenítések áttekintését.

### <a name="purchase-by-vendor-report-page"></a>Beszerzés a szállítói jelentés lapján
**Diagramok**
- 10 legmagasabb szállító beszerzés szerint (halmozott sávdiagram)
- Teljes beszerzések szállítói csoport / ország / név szerint (kördiagram)
- Beszerzések szállítói csoport / ország / név szerint (oszlopdiagram)
- Átlagos beszerzések szállítói csoport / ország / név szerint (oszlopdiagram)

**Mozaik**
- Összes beszerzés
- Egy éves időszak beszerzési növekedése
- Összes szállító száma
- Aktív szállítók száma

**Példa**
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a>Beszerzés a termékjelentés lapján

**Diagramok**
- Beszerzés beszerzési kategória / termék neve szerint (oszlopdiagram)
- Összes beszerzés beszerzési kategória / termék neve szerint (kördiagram)
- 10 legmagasabb termék beszerzés szerint (halmozott sávdiagram)

**Mozaik**
- Termékek összes száma</li>
- Összes aktív termék, teljes termékszám százaléka
- A beszerzések 80%-át lefedő termékek száma

**Példa**


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a>Beszerzés a az időszakjelentés lapján
Ez az oldal az erre az évre és az előző évre eső beszerzéseket, és növekedés beszerzési kategória szerint adatokat mutatja.

**Diagramok** 
- Beszerzés hónap / nap szerint (oszlopdiagram)
- Összesített beszerzés, egy éves időszak eltérése (vízesésdiagram)
- Teljes beszerzés, egy éves időszak növekedése (oszlopdiagram)
- Beszerzési kimutatás (mátrix)

**Mozaik**
- Egy éves időszak beszerzési növekedése
- Egy éves időszak beszerzési növekedése %

**Példa**
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a>Beszerzés a szállítói helyjelentés lapján

**Diagramok**
- Beszerzés település szerint
- Egy éves időszak beszerzési növekedési százaléka
- Beszerzési ország szerint

**Példa**
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a>Beszerzési kiadások elemzése idő szerint lapján

**Diagramok** 
- Beszerzési folyó év, hónap / nap szerint (vonaldiagram)
- Beszerzés, jelenlegi és az előző év (vonal- és oszlopdiagram)

**Példa**
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a>Beszerzési kiadások elemzése beszállító szerint lapján

**Diagramok** 
- A legjobb szállítói beszerzési %-a a beszerzésekből (tölcsér)
- Top 10 szállító megnövekedett kiadásokkal egy éves időszakban
- Top 10 szállító csökkent kiadásokkal egy éves időszakban

**Példa** 
<img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a>Adatmodell és entitások
A **Beszerzési kiadások elemzése** Power BI tartalom jelentési oldalainak feltöltésére a következő adatok szolgálnak. Ezeket az adatokat az Entitástárban lebonyolított összesített mérések jelenítik meg. Az entitástár az analitikai célokra optimalizált Microsoft SQL Server adatbázisa. További tudnivalókért lásd: [Power BI integrációja az entitástárral](power-bi-integration-entity-store.md).

A tartalomcsomag összesítő mértékek a következőkben rendelkezésre álló összesítő mértékek részhalmazát alkotják: Purchase Cube in Microsoft Dynamics AX 2012 és Microsoft Dynamics AX 2012 R3. A kocka összesítő mértékeinek előkészítéséhez az entitástárban, a mértékeket központilag telepíthetővé kell tenni. További információért lásd a következő blogbejegyzést az összesítő mértékek előkészítésének eljárásáról az entitástárban: [Power BI és az entitástár integrálása](power-bi-integration-entity-store.md). A következő kulcs összesítő mértékek közvetlenül a számla sorai entitásból érhetők el, és a tartalom alapjául szolgálnak.

| Entitás        | Kulcs összesítő mértékek | Adatforrás                                 | Mező              | Leírás                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| Számlasorok | Beszerzés                   | VendInvoiceTrans                            | SUM(LineAmountMST) | Összeg a könyvelési pénznemben. |

Az alábbi táblázat a kulcs mértékeket mutatja, amelyeknek a kiszámítása a tartalomban történik a számla sorai entitásból.

| Méret               | Számítás                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Aktuális év beszerzései | Aktuális év beszerzései = SUM('Számlasorok'\[Beszerzés\])                                            |
| Tavalyi év beszerzései    | Tavalyi év beszerzései = CALCULATE(SUM('Számlasorok'\[Beszerzés\]), SAMEPERIODLASTYEAR(Dátumok\[Dátum\])) |
| Egy éves időszak beszerzési növekedése   | Egy éves időszak beszerzési növekedése = \[Aktuális év beszerzései\] – \[Tavalyi év beszerzései\]                            |

A tartalomban a következő fő dimenziók szolgálnak szűrőként az összesítő mértékek szeletelésére, nagyobb részletességet és mélyebb elemzési betekintések elérését téve lehetővé.

| Entitás                 | Példák az attribútumok                                |
|------------------------|-------------------------------------------------------|
| Szállítók                | Szállítói csoportok, Szállító országok vagy régiók, Szállító neve |
| Termékek               | Termékszám, Termék neve, Cikkcsoportok neve        |
| Beszerzési kategóriák | Beszerzési kategória, Beszerzési kategórianevek      |
| Jogi személyek         | Jogi személy neve                                     |
| Dátumok                  | Dátumok, Év eltolása                                    |

Alapértelmezés szerint a tartalom a folyó naptári év adatait jeleníti meg. Azonban módosíthatja a dátumszűrőt a jelentésszűrők szakaszban. A vállalatszűrőt is módosíthatja.
