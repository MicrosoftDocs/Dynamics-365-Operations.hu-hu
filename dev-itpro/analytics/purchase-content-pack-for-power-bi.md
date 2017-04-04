---
title: "Beszerzési kiadások kiemelt BI tartalom elemzése"
description: "Ez a témakör leírja, hogy mi szerepel a beszerzési kiadások elemzése a Microsoft kiemelt BI csomagot. Ismerteti, hogyan lehet elérni a jelentések, amelyek szerepelnek a csomagot, és tájékoztatást nyújt az adatmodell és a csomag létrehozásához használt entitások."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-12-30 09 - 40 - 51
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 8cb928cbf1316e63a8c7de833587168cd36a455c
ms.lasthandoff: 03/29/2017


---

# <a name="purchase-spend-analysis-power-bi-content"></a>Beszerzési kiadások kiemelt BI tartalom elemzése

Ez a témakör leírja, hogy mi szerepel a beszerzési kiadások elemzése a Microsoft kiemelt BI csomagot. Ismerteti, hogyan lehet elérni a jelentések, amelyek szerepelnek a csomagot, és tájékoztatást nyújt az adatmodell és a csomag létrehozásához használt entitások.

<a name="overview"></a>Áttekintés
--------

A beszerzési kiadások tartalom csomag a Microsoft kiemelt BI jött létre beszerzési menedzserek és vezetők, akik felelősek a költségvetések elemzése. Célja az, hogy segítse azokat a beszerzési kiadások szemmel tarthatja. Műveletek beszerzési Microsoft Dynamics 365 tranzakciós adatait használja, és itt is az összesített adatok vállalati szintű beszerzési nézet és a kiadások a szállító és a termék beszerzési. Jelentés beszerzési kiadások időbeli változásainak kiemelése. Ezért azok segítségével riasztási menedzserek pozitív és negatív kiadások alakulását az egyes szállítók és termékek. Diagramok megjelenítése beszerzési kiadások különböző beszerzési kategóriák és szállítói csoportok. Kategória- és regionális vezetők számára hasznos ezek a diagramok segítségével azonosíthatja a kiadások viselkedés változásai. A csomag most Beszerzési menedzserek és vezetők, akik felelősek a költségvetések elemzése beszerzési kiadások a következő módon:

-   Év megadott napjáig beszerzési (által a szállítói csoport és az egyes szállítókhoz, beszerzési kategória és egyes termékek és szállító helye)
-   Over-éves beszerzési módosítása (szállítói csoport és a beszerzési kategória szerint)

## <a name="accessing-the-content-pack"></a>A csomag elérése
A beszerzési kiadások content pack végrehajtása eszközként a Microsoft Dynamics életciklus szolgáltatások (LCS) közzé van téve, és elérhető a Microsoft Dynamics 365 műveletek elemzése. Access és Power BI megnyitott jelentések kapcsolatos további tudnivalókért lásd: [a Microsoft és a partnerek LCS kiemelt BI-tartalom](power-bi-content-microsoft-partners.md).

## <a name="metrics-that-are-included-in-the-content-pack"></a>A csomag tartalmazott metrikák
A beszerzési kiadások elemzése tartalom csomag tartalmaz egy jelentést, amely metrikák összessége alkotja. Ezeket a metrikákat, mozaikok, táblázatok és diagramok formájában jelenik meg. A következő táblázat áttekintést content Pack a képi megjelenítések tartoznak.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Jelentés lap</th>
<th>Diagramok</th>
<th>Mozaik</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Szállítói beszerzési</td>
<td><ul>
<li>10 legmagasabb visszáruaránnyal beszerzési (halmozott sávdiagram)</li>
<li>Beszerzések szállítók szerint teljes csoport / country / name (kördiagram)</li>
<li>Szállító beszerzési csoport / country / name (oszlopdiagram)</li>
<li>Beszerzések szállítók szerint átlagos csoport / country / name (oszlopdiagram)</li>
</ul></td>
<td><ul>
<li>Összes beszerzés</li>
<li>Műhelykapacitás beszerzési növekedés</li>
<li>Szállítók teljes száma</li>
<li>Aktív szállítók száma</li>
</ul></td>
</tr>
<tr class="even">
<td>Beszerzési termék szerint</td>
<td><ul>
<li>Beszerzési kategória szerinti beszerzési / termék neve (oszlopdiagram)</li>
<li>Beszerzés beszerzési kategória összes / termék neve (kördiagram)</li>
<li>TOP 10 termékek beszerzési (halmozott sávdiagram)</li>
</ul></td>
<td><ul>
<li>Termékek száma</li>
<li>Aktív termékek teljes százaléka termékek száma</li>
<li>80 %-os beszerzési elszámolása termékek száma</li>
</ul></td>
</tr>
<tr class="odd">
<td>Beszerzési időszak *</td>
<td><ul>
<li>Beszerzési hónap / nap (oszlopdiagram)</li>
<li>Összesített beszerzési Műhelykapacitás eltérés (vízesés diagram)</li>
<li>Teljes beszerzési Műhelykapacitás növekedés (oszlopdiagram)</li>
<li>Beszerzési utasítás (mátrix)</li>
</ul></td>
<td><ul>
<li>Műhelykapacitás beszerzési növekedés</li>
<li>Műhelykapacitás beszerzési növekedés %</li>
</ul></td>
</tr>
<tr class="even">
<td>Beszerzési szállító helye szerint</td>
<td><ul>
<li>Beszerzési település szerint</li>
<li>Beszerzési Műhelykapacitás növekedés %</li>
<li>Beszerzési ország szerint</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Beszerzési idő szerinti kiadások elemzése</td>
<td><ul>
<li>Beszerzési folyó év, hónap / nap (grafikon)</li>
<li>Beszerzési a jelenlegi és az előző év (sor- és oszlopsablonok diagram)</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Beszerzési kiadások szállító elemzése</td>
<td><ul>
<li>A legjobb szállítói beszerzési 10 %-a beszerzési (tölcsér)</li>
<li>TOP 10 megnövekedett kiadások Műhelykapacitás szállítókhoz</li>
<li>TOP 10 csökkent elkölthető Műhelykapacitás szállítókhoz</li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

\*Erre az évre és az előző év beszerzési és növekedési beszerzési kategória szerint

## <a name="data-model-and-entities"></a>Adatmodell és szervezetek
365 Dynamics műveletekhez használt adatok a jelentés a beszerzési töltött vizsgálati csomagot. Összesített mérések előkészítettek ki ezeket az adatokat az entitás üzlet Ez az analytics optimalizált Microsoft SQL adatbázis. Az entitás tároló kapcsolatos további tudnivalókért tanulmányozza a [kiemelt BI integrálása a Dynamics entitás tároló](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/) blogbejegyzést. A csomag összesített méréseket elérhető a Microsoft Dynamics AX 2012 és a Microsoft Dynamics 365 2012 R3 műveletekre vonatkozó beszerzési kocka összesített mérések részhalmaza. A kocka az entitás tároló összesített mérések előkészítése, ügyelnie kell azok központilag telepíthető. További tudnivalókért tanulmányozza az összesített mérések az entitás üzlethez előkészítési eljárás a [kiemelt BI integrálása a Dynamics entitás tároló](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/) blogbejegyzést. A következő kulcs összesített mérések érhetők el közvetlenül a számla sorai entitásból és a csomag alapjául szolgálnak.

| Entitás        | Kulcs összesített mérések | Adatforrás Dynamics 365 műveletek | Mező              | Leírás                           |
|---------------|----------------------------|---------------------------------------------|--------------------|---------------------------------------|
| Számlasorok | Beszerzés                   | A VendInvoiceTrans                            | Sum(LineAmountMST) | Összeg a könyvelési pénznemben |

Az alábbi táblázat mutatja a csomagot a számla sorai entitásból a kiszámított kulcs mérések.

| Méret               | Számítás                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Beszerzési folyó év | Beszerzési folyó év = SZUM ("Sor számlázásához"\[beszerzési\])                                            |
| Beszerzési tavaly    | Beszerzési tavaly számítás = (SZUM ("Sor számlázásához"\[beszerzési\]), SAMEPERIODLASTYEAR (dátumok\[dátum\])) |
| Műhelykapacitás beszerzési növekedés   | Műhelykapacitás beszerzési növekedés = \[folyó évi beszerzési\] – \[beszerzési tavaly\]                            |

A csomag a következő főbb dimenziókra szolgálnak szűrőként szeletelése összesített mérések, így több beállítási lehetőséget és mélyebb analitikai elképzelések érhet.

| Entitás                 | Példák az attribútumok                                |
|------------------------|-------------------------------------------------------|
| Szállítók                | Szállítói csoportok, szállító országok vagy régiók, a szállító neve |
| Termékek               | Termékszám, a termék neve, a cikk csoportok neve        |
| Beszerzési kategóriák | Beszerzési kategória beszerzési kategória neve      |
| Jogi személyek         | Jogi személy neve                                     |
| Dátumok                  | Dátum év eltolása                                    |

Alapértelmezés szerint a csomagot a folyó naptári év az adatokat jelenít meg. A dátum szűrő szűrők jelentés szakaszában azonban módosíthatja. A vállalat szűrőt is módosíthatja.

## <a name="additional-resources"></a>További erőforrások
Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

-   [Adatentitások](..\data-entities\data-entities.md)
-   [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Kiemelt Üzletiintelligencia-lapok hozzáadása munkaterületekhez](configure-power-bi-integration.md)



