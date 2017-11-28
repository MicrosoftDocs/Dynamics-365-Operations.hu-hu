---
title: "Beszerzési kiadások elemzése Power BI-tartalom"
description: "Ez a témakör a Beszerzési kiadások elemzése Power BI-tartalom modul tartalmát ismerteti. Leírja, hogy hogyan kell hozzáférni a tartalomban szereplő jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban."
author: FrankDahl
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6485f36802fc4e327e223f47d65c4bdca11c1609
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="purchase-spend-analysis-power-bi-content"></a>Beszerzési kiadások elemzése Power BI-tartalom

[!include[banner](../includes/banner.md)]

Ez a témakör a **Beszerzési kiadások elemzése** Power BI-tartalom modul tartalmát ismerteti. Leírja, hogy hogyan kell hozzáférni Power BI-jelentésekhez, és információkat nyújt a tartalom összeállításához használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="overview"></a>Áttekintés

A **Beszerzési kiadások elemzése** Power BI-tartalom a beszerzési vezetők és olyan vezetők segítségével készült, akik a beszerzési kiadások költségvetéésért felelősek. A vezetők az alábbi módokon elemezhetik a beszerzési költségeket:

-   Az év megadott napjáig tartó beszerzések (szállítói csoport és az egyes szállítók , beszerzési kategória és egyes termékek, valamint a szállító helye szerint)
-   Egy éves időszak beszerzési változásai (szállítói csoport és a beszerzési kategória szerint)

A tartalom beszerzési tranzakciós adatokat használ, és egyrészt összesített adatokat nyújt a vállalati szintű beszerzési számokról, másrészt a kiadások szállító és termék szerinti lebontását kínálja. A jelentések kiemelik a beszerzési kiadások időbeli változásait. Ezért a jelentések riasztásra használhatók a menedzserek számára a kiadások pozitív és negatív trendjeiről az egyes szállítókra és termékekre nézve. Ezenkívül diagramok jelenítik meg a beszerzési kiadásokat a különböző beszerzési kategóriákra és szállítói csoportokra nézve. Ezért a kategória- és regionális vezetők a diagramok segítségével a kiadások viselkedési változásait azonosíthatják.

## <a name="accessing-the-power-bi-content"></a>Power BI-tartalom elérése
Amennyiben a Microsoft Dynamics 365 for Finance and Operations Enterprise edition (2017. július) rendszert használja, a **Beszerzési kiadások elemzése** Power BI-tartalom a **Beszerzési és ráfordítási elemzés** (**Beszerzés és forrás** > **Lekérdezések és jelentések** > **Beszerzési teljesítményelemzés** > **Beszerzési és ráfordítási elemzés**) lap található. 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>A Power BI-tartalomhoz tartozó metrikák
A **Beszerzési kiadások elemzése** Power BI-tartalom tartalmaz egy jelentést, amely metrikák készletéből áll. Ezek a metrikák mozaikok, táblázatok és diagramok formájában jelennek meg. Az alábbi táblázat tartalmazza a megjelenítések áttekintését.

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

\* Erre az évre és az előző évre eső beszerzés, és növekedés beszerzési kategória szerint

## <a name="extending-the-power-bi-content"></a>Power BI-tartalom kibővítése
A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban található tartalomcsomagok révén nagyszerű elemzési lehetőségeket nyújthat azoknak a személyeknek, akik nem jelentkeztek be a Microsoft Dynamics 365 szolgáltatásba. Ezek a tartalomcsomagok módosíthatók, hogy más jelentéseket vagy megjelenítéseket is tartalmazhassanak, majd a tartalomcsomagok elemzés céljából közzétehetők a Power BI.com-bérlőjénél. 

A **Beszerzési kiadások elemzése** Power BI-tartalmat az LCS Megosztott eszközök könyvtárában találja. A tartalom letöltésére és szervezeténél való megvalósítására vonatkozó további információért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](power-bi-content-microsoft-partners.md). Ha meg szeretne tekinteni egy demót, amely bemutatja a Power BI-tartalmak megvalósítását, lásd a [Power BI-tartalom a Microsofttól és az Ön partnereitől a Dynamics Lifecycle Services szolgáltatásban](https://mix.office.com/watch/9puyb1b2xs1w) című részt (Office Mix).

Ügyeljen arra, hogy azt a **Beszerzési kiadások elemzése** tartalmat töltse le, amely a Dynamics 365 ön által használt verziójára vonatkozik.

> [!NOTE]
> Amennyiben a Microsoft Dynamics 365 for Finance and Operations Enterprise edition 1611-es verzióját használja, a KB 4011327 a Power BI-tartalom előfeltétele. A Lifecycle Services szolgáltatásba való bejelentkezést követően itt férhet hozzá a tudásbázishoz: https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## <a name="data-model-and-entities"></a>Adatmodell és entitások
A **Beszerzési kiadások elemzése** Power BI-tartalom jelentési oldalainak feltöltésére a következő adatok szolgálnak. Ezeket az adatokat az Entitástárban lebonyolított összesített mérések jelenítik meg. Az entitástár a Microsoft analitikai célokra optimalizált SQL-szerveradatbázisa. További tudnivalókért lásd: [Az entitástár és a Power BI integrációjának áttekintése](power-bi-integration-entity-store.md).

A tartalom összesítő mértékek a következőkben rendelkezésre álló összesítő mértékek részhalmazát alkotják: Purchase Cube in Microsoft Dynamics AX 2012 és Microsoft Dynamics AX 2012 R3. A kocka összesítő mértékeinek előkészítéséhez az entitástárban, a mértékeket központilag telepíthetővé kell tenni. További információért lásd a következő blogbejegyzést az összesítő mértékek előkészítésének eljárásáról az entitástárban: [A Power BI és az entitástár integrálása a Dynamics programban - áttekintés](power-bi-integration-entity-store.md). A következő kulcs összesítő mértékek közvetlenül a számla sorai entitásból érhetők el, és a tartalom alapjául szolgálnak.

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

