---
title: "Beszerzési kiadások elemzése Power BI-tartalom"
description: "Ez a témakör leírja, hogy mi szerepel a Microsoft Power BI beszerzési kiadások elemzése tartalomcsomagjában. Leírja, hogy hogyan kell hozzáférni a tartalmi csomagban szereplő jelentésekhez, és információkat nyújt a tartalmi csomag összeállításához használt entitásokkal és adatmodellekkel kapcsolatban."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ad0ee95113d05710cccc1a5e9d215b38244c2047
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="purchase-spend-analysis-power-bi-content"></a>Beszerzési kiadások elemzése Power BI-tartalom

[!include[banner](../includes/banner.md)]


Ez a témakör leírja, hogy mi szerepel a Microsoft Power BI beszerzési kiadások elemzése tartalomcsomagjában. Leírja, hogy hogyan kell hozzáférni a tartalmi csomagban szereplő jelentésekhez, és információkat nyújt a tartalmi csomag összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.

<a name="overview"></a>Áttekintés
--------

A Microsoft Power BI Beszerzési kiadások elemzése tartalomcsomagja a beszerzési menedzserek, valamint a költségvetésekért felelős vezetők számára készült. Célja az, hogy segítse őket a beszerzési kiadások ellenőrzés alatt tartásában. A Microsoft Dynamics 365 for Operations beszerzési tranzakciós adatait használja, és egyrészt összesített adatokat nyújt a vállalati szintű beszerzési számokról, másrészt a kiadások szállító és termék szerinti lebontását kínálja. A jelentések kiemelik a beszerzési kiadások időbeli változásait. Ezért riasztásokat jelezhetnek a menedzserek számára a kiadások pozitív és negatív trendjeiről az egyes szállítókra és termékekre nézve. Diagramok jelenítik meg a beszerzési kiadásokat a különböző beszerzési kategóriákra és szállítói csoportokra nézve. A kategória- és regionális vezetők számára hasznosak lehetnek ezek a diagramok, segítséget nyújtva a kiadások viselkedési változásainak azonosításához. A tartalomcsomag segítségével a beszerzési menedzserek és a költségvetésekért felelős vezetők a következő módokon elemezheti a beszerzési kiadásokat:

-   Az év megadott napjáig tartó beszerzések (szállítói csoport és az egyes szállítók , beszerzési kategória és egyes termékek, valamint a szállító helye szerint)
-   Egy éves időszak beszerzési változásai (szállítói csoport és a beszerzési kategória szerint)

## <a name="accessing-the-content-pack"></a>A tartalmi csomag elérése
A beszerzési kiadások elemzése tartalomcsomag a Microsoft Dynamics Lifecycle Services (LCS) végrehajtási eszközeként van közzétéve, és a Microsoft Dynamics 365 for Operations programból férhető hozzá. A Power BI jelentések elérésével és megnyitásával kapcsolatos további tudnivalókért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](power-bi-content-microsoft-partners.md).
Megjegyzés: A KB 4011327 ezen Power BI-tartalom előfeltétele. A Lifecycle Servicesbe való bejelentkezést követően itt férhet hozzá a tudásbázishoz: https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## <a name="metrics-that-are-included-in-the-content-pack"></a>A tartalomcsomag által tartalmazott metrikák
A beszerzési kiadások elemzése tartalomcsomag tartalmaz egy jelentést, amely metrikák készletéből áll. Ezek a metrikák mozaikok, táblázatok és diagramok formájában jelennek meg. Az alábbi táblázatban a tartalomcsomag megjelenítési formáinak áttekintése található.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Jelentéslap</th>
<th>Diagramok</th>
<th>Mozaik</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Szállító beszerzés</td>
<td><ul>
<li>10 legmagasabb szállító beszerzés szerint (halmozott sávdiagram)</li>
<li>Teljes beszerzések szállítói csoport / ország / név szerint (kördiagram)</li>
<li>Beszerzések szállítói csoport / ország / név szerint (oszlopdiagram)</li>
<li>Átlagos beszerzések szállítói csoport / ország / név szerint (oszlopdiagram)</li>
</ul></td>
<td><ul>
<li>Összes beszerzés</li>
<li>Egy éves időszak beszerzési növekedése</li>
<li>Összes szállító száma</li>
<li>Aktív szállítók száma</li>
</ul></td>
</tr>
<tr class="even">
<td>Beszerzés termékenként</td>
<td><ul>
<li>Beszerzés beszerzési kategória / termék neve szerint (oszlopdiagram)</li>
<li>Összes beszerzés beszerzési kategória / termék neve szerint (kördiagram)</li>
<li>10 legmagasabb termék beszerzés szerint (halmozott sávdiagram)</li>
</ul></td>
<td><ul>
<li>Termékek összes száma</li>
<li>Összes aktív termék, teljes termékszám százaléka</li>
<li>A beszerzések 80%-át lefedő termékek száma</li>
</ul></td>
</tr>
<tr class="odd">
<td>Beszerzés időszak szerint*</td>
<td><ul>
<li>Beszerzés hónap / nap szerint (oszlopdiagram)</li>
<li>Összesített beszerzés, egy éves időszak eltérése (vízesésdiagram)</li>
<li>Teljes beszerzés, egy éves időszak növekedése (oszlopdiagram)</li>
<li>Beszerzési kimutatás (mátrix)</li>
</ul></td>
<td><ul>
<li>Egy éves időszak beszerzési növekedése</li>
<li>Egy éves időszak beszerzési növekedése %</li>
</ul></td>
</tr>
<tr class="even">
<td>Beszerzés a szállító helye szerint</td>
<td><ul>
<li>Beszerzés település szerint</li>
<li>Egy éves időszak beszerzési növekedési százaléka</li>
<li>Beszerzési ország szerint</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Beszerzési kiadások elemzése idő szerint</td>
<td><ul>
<li>Beszerzési folyó év, hónap / nap szerint (vonaldiagram)</li>
<li>Beszerzés, jelenlegi és az előző év (vonal- és oszlopdiagram)</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Beszerzési kiadások elemzése szállító szerint</td>
<td><ul>
<li>A legjobb szállítói beszerzési %-a a beszerzésekből (tölcsér)</li>
<li>Top 10 szállító megnövekedett kiadásokkal egy éves időszakban</li>
<li>Top 10 szállító csökkent kiadásokkal egy éves időszakban</li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

\*Erre az évre és az előző évre eső beszerzés, és növekedés beszerzési kategória szerint

## <a name="data-model-and-entities"></a>Adatmodell és entitások
A Beszerzési kiadások elemzése tartalomcsomag jelentése a Dynamics 365 for Operations adatait használja. Ezek az adatok az entitástárban előkészített összesített mérések formájában jelennek meg - az entitástár egy elemzési célra optimalizált Microsoft SQL-adatbázis. Az entitástárolóval kapcsolatos további információért lásd: [A Power BI és az entitástár integrálása a Dynamics programban](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/) blogbejegyzést. A tartalomcsomag összesítő mértékek a következőkben rendelkezésre álló összesítő mértékek részhalmazát alkotják: Purchase Cube in Microsoft Dynamics AX 2012 és Microsoft Dynamics AX 2012 R3. A kocka összesítő mértékeinek előkészítéséhez az entitástárban, a mértékeket központilag telepíthetővé kell tenni. További információért lásd a következő blogbejegyzést az összesítő mértékek előkészítésének eljárásáról az entitástárban: [A Power BI és az entitástár integrálása a Dynamics programban](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). A következő kulcs összesítő mértékek közvetlenül a számla sorai entitásból érhetők el, és a tartalomcsomag alapjául szolgálnak.

| Entitás        | Kulcs összesítő mértékek | A Dynamics 365 for Operations adatforrása | Mező              | Leírás                           |
|---------------|----------------------------|---------------------------------------------|--------------------|---------------------------------------|
| Számlasorok | Beszerzés                   | VendInvoiceTrans                            | SUM(LineAmountMST) | Összeg a könyvelési pénznemben |

Az alábbi táblázat a kulcs mértékeket mutatja, amelyeknek a kiszámítása a tartalomcsomagban történik a számla sorai entitásból.

| Méret               | Számítás                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Aktuális év beszerzései | Aktuális év beszerzései = SUM('Számlasorok'\[Beszerzés\])                                            |
| Tavalyi év beszerzései    | Tavalyi év beszerzései = CALCULATE(SUM('Számlasorok'\[Beszerzés\]), SAMEPERIODLASTYEAR(Dátumok\[Dátum\])) |
| Egy éves időszak beszerzési növekedése   | Egy éves időszak beszerzési növekedése = \[Aktuális év beszerzései\] – \[Tavalyi év beszerzései\]                            |

A tartalomcsomagban a következő fő dimenziók szolgálnak szűrőként az összesítő mértékek szeletelésére, nagyobb részletességet és mélyebb elemzési betekintések elérését téve lehetővé.

| Entitás                 | Példák az attribútumok                                |
|------------------------|-------------------------------------------------------|
| Szállítók                | Szállítói csoportok, Szállító országok vagy régiók, Szállító neve |
| Termékek               | Termékszám, Termék neve, Cikkcsoportok neve        |
| Beszerzési kategóriák | Beszerzési kategória, Beszerzési kategórianevek      |
| Jogi személyek         | Jogi személy neve                                     |
| Dátumok                  | Dátumok, Év eltolása                                    |

Alapértelmezés szerint a tartalomcsomag a folyó naptári év adatait jeleníti meg. Azonban módosíthatja a dátumszűrőt a jelentésszűrők szakaszban. A vállalatszűrőt is módosíthatja.

## <a name="additional-resources"></a>További erőforrások
Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

-   [Adatentitások](..\data-entities\data-entities.md)
-   [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Kiemelt Üzletiintelligencia-lapok hozzáadása munkaterületekhez](configure-power-bi-integration.md)





