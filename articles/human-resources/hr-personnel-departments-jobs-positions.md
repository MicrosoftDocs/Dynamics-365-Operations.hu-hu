---
title: Munkaerő optimalizálása részlegek, munkák és beosztások használatával
description: A részlegek, a munkák és a beosztások mind szervezeti elemek, melyeket az Emberi erőforrásokon belül kezelnek. Ez a cikk általános tájékoztatást ad ezeket az elemeket illetően.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmJob, HcmPosition, OMOperatingUnit, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources, Retail
ms.custom: 87933
ms.assetid: eb5dcacb-a5fe-451d-b30a-7ef14da65d81
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 826de9e1e5d70ba1ec088b44254c871726b5c38e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418833"
---
# <a name="organize-your-workforce-by-using-departments-jobs-and-positions"></a>Munkaerő szervezése részlegek, feladatok és beosztások szerint

A részlegek, a munkák és a beosztások mind szervezeti elemek, melyeket az Emberi erőforrásokon belül kezelnek. Ez a cikk általános tájékoztatást ad ezeket az elemeket illetően. 

Az alábbi példa mutatja be a jelen cikkben leírt koncepciókat.

|**Részleg**|**Beosztás**|**Munka**|
|---|---|---|
|**Értékesítés**|Értékesítési igazgató (Kelet)|Értékesítési igazgató|
|**Értékesítések**|Értékesítési igazgató (Nyugat)|Értékesítési igazgató|
|**Értékesítések**|Értékesítési igazgató (Közép)|Értékesítési igazgató|
|**Könyvelés**|Számviteli felügyelő|Főkönyvelő|
|**Könyvelés**|Könyvelés-A|Könyvelő|
|**Emberi erőforrások**|HR vezető (Kelet)|HR vezető|
|**Emberi erőforrások**|HR vezető (Nyugat)|HR vezető|
|**Emberi erőforrások**|HR vezető (Közép)|HR vezető|


 <a name="departments"></a>Osztályok
------------

A részleg egy olyan üzemi egység, amely a szervezet egy kategóriáját vagy funkcionális területét képviseli, amely a szervezet egy specifikus területéért felel, ilyen például az értékesítés vagy a könyvelés. A részlegekkel – amelyeknek profitjuk és veszteségi felelősségük lehet – funkcionális területekkel kapcsolatos jelentések tehetők. Emellett egy részleg költséghelyek egy csoportját is magában foglalhatja. Az értékesítés, a könyvelés és a HR csak néhány példa a szervezeten belüli részlegekre.

## <a name="jobs-and-positions"></a> Munkakörök és beosztások
A munkakör azon feladatok és felelősségek gyűjteménye, amelyek egy adott munkát végrehajtó személytől elvárt. Egy beosztás egy feladat egyedi példánya. Egy adott munkakörhöz szükséges felelősségi területek, munkafeladatok, beosztások, képességek, tanulmányi adatok és tanúsítványok az adott munkához rendelt pozíciók esetén is elvárt.
### <a name="job-tasks"></a>Munkaköri feladatok

Létrehozhat olyan munkaköri feladatokat, amelyek bemutatják az adott pozíciójú dolgozótól elvárt alapvető feladatokat. Ugyanazon munkaköri feladatok több munkához is hozzáadhatók, valamint az adott munkához tartozó pozíciók öröklik ezen munkaköri feladatokat. Az alábbi táblázatban látható néhány példa munkaköri feladatokra.

<table>
<thead>
<tr class="header">
<th>Munka</th>
<th>Munkaköri feladat</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Értékesítési igazgató</td>
<td><ul>
<li><span class="input">Teljesítményellenőrzés</span> – Az egyes értékesítők teljesítményének áttekintése.</li>
<li><span class="input">Hiányzásellenőrzési</span> – Az üzletkötők távolléti kérelmeinek vagy regisztrációnak jóváhagyása vagy elutasítása.</li>
</ul></td>
</tr>
<tr class="even">
<td>Könyvelő</td>
<td><span class="input">Pénzügyi jelentés</span> – Heti pénzügyi jelentések bemutatása a pénzügyi igazgatónak.</td>
</tr>
</tbody>
</table>

### <a name="job-functions"></a>Beosztások

A beosztási funkciók hasonlók a munkaköri feladatokhoz. A beosztási funkció egy munkához rendelt egy vagy több feladat, kötelezettség és feladatkör. A beosztásokat a munkákhoz lehet hozzárendelni, és segítségükkel a kompenzációs tervekhez kapcsolódó jogosultsági szabályokat lehet beállítani és alkalmazni. Az alábbi táblázatban látható néhány példa munkaköri beosztásokra.

| Munka           | Beosztás                                                |
|---------------|-------------------------------------------------------------|
| Értékesítési igazgató | Személyek kezelése – Azon személyek kezelése, akik Önnek jelentenek.               |
| Könyvelő    | Pénzügyi ellenőrzés – Pénzügyi adatok karbantartása számlák csoportjainak esetében. |

### <a name="job-types"></a>Beosztástípusok

Feladattípusok segítségével a hasonló beosztások kategóriákba sorolhatók. A feladattípusokat a beosztási funkciókhoz hasonlóan a feladatokhoz lehet hozzárendelni, és segítségükkel a kompenzációs tervekhez kapcsolódó jogosultsági szabályokat lehet beállítani és alkalmazni. Az alábbi táblázatban látható néhány példa a feladattípusokra:
-   Teljes munkaidős
-   Részmunkaidős
-   Fizetés
-   Órabér

### <a name="areas-of-responsibility"></a>Hatáskörök

Alkalmazzon hatásköröket azon a szerepkörök, folyamatok, termékek és műveletek megjelöléséhez, amelyekért a dolgozó egy adott beosztásban felelős. A „Könyvelő” nevű beosztáshoz tartozó hatáskörre példa lehet a „Pénzügyi jelentés az A termékkel kapcsolatban”.

<a name="positions"></a>Beosztások
----------

A beosztások szervezeti hierarchia alacsonyabb szintjének fontos részei. Egy beosztás egy feladat egyedi példánya. Például az „Értékesítési igazgató (Kelet)” pozíció csak egyike azon beosztásoknak, amelyek hozzárendelhetők az „Értékesítési igazgató” munkához. A pozíciók egy részlegen belül léteznek, és dolgozókhoz kerülnek hozzárendelésre.
### <a name="position-creation-and-maintenance"></a>Beosztások létrehozása és karbantartása

-   Az egyszerű hozzáférést biztosító listaoldalon megtekintheti a pozíciókkal kapcsolatos rendszermódosítások előzményeit.
-   Okkódokat is létrehozhat, amelyeket a felhasználók a pozíciók létrehozásakor vagy módosításakor választhatnak.
-   Létrehozhat személyzeti művelet típusokat, és számsorozatokat rendelhet a személyzeti műveletekhez.
-   Be lehet állítani munkafolyamat úgy, hogy a beosztásokkal kapcsolatos kiegészítésekhez és módosításokhoz jóváhagyásra is szükség legyen.

### <a name="position-duration"></a>Beosztás időtartama

Minden pozícióhoz tartozik egy időtartam, amely a beosztás érvényességi idejét határozza meg. Ezen intervallumot időtartamnak nevezik. Például a nyári beosztások időtartam lehet: 2015. május 1-től 2015. augusztus 31-ig.

### <a name="worker-assignments"></a>Dolgozó-hozzárendelések

Ha hozzárendel egy dolgozót egy beosztáshoz, akkor betölti a pozíciót. Egy dolgozót több beosztáshoz is hozzárendelhet, de egy beosztáshoz egyszerre csak egy dolgozót lehet hozzárendelni.

### <a name="reporting-relationships"></a>Jelentési kapcsolatok

A beosztások a szervezeti hierarchia alacsonyabb szintjének fontos részei. A Beosztás képernyőn megadhatja azon beosztást, amely felé az adott beosztottnak jelentenie kell. Ha hozzárendel egy dolgozót egy olyan pozícióhoz, amely egy másik pozíció számára jelent, akkor jelentési kapcsolatot hoz létre a két beosztáshoz hozzárendelt dolgozók között. Például a „Könyvelő-A” pozíció a „Számviteli felügyelő” számára tesz jelentéseket. A „Számviteli felügyelő” pozícióhoz Kim Akers, a „Könyvelő-A” pozícióhoz Sanjay Patel kerül hozzárendelésre. Ez azt jelenti, hogy Sanjay Patel Kim Akers felé jelent. 

Ha szervezete mátrix hierarchiát vagy egyéb egyéni hierarchiát alkalmaz, beállíthat pozíció hierarchia típusokat, majd hozzáadhat jelentési kapcsolatokat minden egyes beállított hierarchia típushoz. Például Lori Penor az Adventure Works általános igazgatója, így hozzá van rendelve az „Általános igazgató” beosztáshoz. Lori kezeli a fejlesztését egy olyan terméknek, amely különböző eszközök tisztítására szolgál. Lorinak szüksége van egy könyvelőre, aki segít neki a termékfejlesztéssel kapcsolatos pénzügyek kezelésében. Ezért felvette Sanjay Patelt könyvelőnek. Sanjay közvetlenül Kim Akers felé jelent, ugyanakkor együtt dolgozik Lori Penorral is, aki szintén az eszköztisztító fejlesztésével kapcsolatos pénzügyek kezelésében vesz részt. 

Az előző példához a következő feladatokat kellene végrehajtani Sanjay Patel és Anna Penor munkakapcsolatának beállításához:
1.  Egyéni pozícióhierarchia létrehozása „Eszköz” néven az eszköztisztító termék fejlesztéséért felelős beosztásokat magában foglaló hierarchia létrehozásához.
2.  Az Általános igazgatói pozíció hozzárendelése a Könyvelő-A pozícióhoz úgy, hogy utóbbi jelentsen az előző számára.

A beosztáshierarchia a pozíciók jelentési szerkezetének megtekintésére használható. Ha több beosztáshierarchiával rendelkezik, a beosztáshierarchia minden egyes hierarchiatípusához kapcsolódóan megtekintheti a hierarchiákat. Emellett a pozícióazonosító vagy a beosztáshoz hozzárendelt dolgozó neve alapján is megkereshet egy pozíciót. A beosztáshierarchia egy szervezeti hierarchia.

## <a name="date-effective-records"></a>Érvényességidátum-rekordok
Bizonyos rekordok esetében jövőbeni módosításokat is be lehet állítani a rekordhoz. A következő adatok érvényességi dátumhoz kötöttek.

<table>
<thead>
<tr class="header">
<th>Rekordok</th>
<th>Hatályba lépési dátumhoz kötött adat</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Feladatok</td>
<td><ul>
<li>Részletes információk a munkával kapcsolatban</li>
<li>Beosztási kategória adatai</li>
<li>Kompenzációs adatok</li>
</ul></td>
</tr>
<tr class="even">
<td>Pozíciók</td>
<td><ul>
<li>Részletes információk a pozícióval kapcsolatban</li>
<li>Dolgozó-hozzárendelések</li>
<li>Beosztások időtartamai</li>
<li>Beosztáshierarchiák</li>
</ul></td>
</tr>
</tbody>
</table>

Módosíthatja az előző táblázatban említett, az egyes beosztásokhoz és feladatokhoz tartozó adatokat, és megadhat egy dátumot, amikor a beosztáshoz vagy feladathoz kapcsolódó módosításoknak érvénybe kell lépniük. Például egy beosztás csak egy dolgozóhoz rendelhető hozzá, de Sanjay Patel, aki a Könyvelő-A beosztáshoz van rendelve, két hét múlva távozik. Sanjay Patel távozását követően Joe Healey veszi át a pozíciót. Annak ellenére, hogy Sanjay továbbra is hozzá van rendelve a beosztáshoz, Joe Healy is hozzárendelhető ugyanehhez a pozícióhoz úgy, hogy a hozzárendelés ténylegesen csak Sanjay utolsó napját követően lépjen hatályba.







[!INCLUDE[footer-include](../includes/footer-banner.md)]