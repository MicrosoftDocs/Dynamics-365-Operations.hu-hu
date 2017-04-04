---
title: "A feladat-alkatrészek beállítása"
description: "Ez a témakör ismerteti, hogy a feladat lehetnek, és hogyan használhatja a szervezet azon elemeinek példákat tartalmaz a fogalmi elemek."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: d96b1f01a5cb4370436888deae8fd4835a0dbb80
ms.openlocfilehash: b8143db5b133337603a7f2f46028d91bb81cd947
ms.lasthandoff: 03/31/2017


---

# <a name="setting-up-the-components-of-a-job"></a>A feladat-alkatrészek beállítása

Ez a témakör ismerteti, hogy a feladat lehetnek, és hogyan használhatja a szervezet azon elemeinek példákat tartalmaz a fogalmi elemek. 

Feladatok létrehozása előtt be kell állítania néhány hivatkozási információt. A feladat, amely csak egy nevet hozhat létre. További információk, például a beosztást, együtt alapértelmezett értékeket biztosít a beosztások a feladathoz rendelt. Emellett a beírt adatok egy része használható kompenzációs konstrukciók konkrét feladatok szűréséhez. Ha juttatási programok egy bizonyos feladathoz szűrésére használható jogosultsági beállítandó kell beállíthatja beosztások és feladattípusok feladatok beállítása előtt. Úgy, hogy ezeket az alapértelmezett értékeket érhető el, ha beosztások hozzáadása a projekthez időt takaríthat meg. 

Néhány feladat részletei, például a beosztás, a típus és a függvény olyan dátum-hatékony. Hozzon létre egy projektet ma, de nem adja hozzá ezeket az adatokat később, és a feladat a létrehozás dátuma szerint, majd keresse meg, ha ezek az adatok nem jelennek meg. Ezért célszerű létrehozni ezeket az információkat néhány előtt szükség van rá. Ily módon az információkat adhat új feladatok létrehozásakor.

## <a name="job-titles"></a>Beosztások
A létrehozni kívánt beosztásokhoz titulusokat is be kell állítania. A pozíciók azon beosztások titulusait öröklik, amelyekhez hozzárendelték őket. 

Használatával a beosztások karbantartása a **címek** lapot, amely a keresés funkció segítségével is megnyithatja. A a ** címek ** lapon, írja be a címeket fogja használni a feladatok.

## <a name="job-types"></a>Beosztástípusok
Feladattípusok segítségével kategóriákba csoportosítani a hasonló feladatokat. Feladattípusok nem lesz szükség. azonban ha a későbbiekben a kompenzációkezelés jogosultsági szabályainak beállításakor szeretne beosztástípusokat használni, ezeket még a beosztások előtt kell beállítania. Feladattípusok például teljes és részmunkaidős, vagy Munkabér és hourly fizet. Megmaradjanak a feladattípusok segítségével a **projekt-típusok** oldalon. A a **projekt-típusok** lap, adja meg nevét és rövid leírását a feladat típusa. A a **alól állapot** mezőben, ez a feladattípus feladatok alól tisztességes munkára vonatkozó szabványok törvény (FLSA) állapotának jelzésére a következő lehetőségek közül választhat:

-   **Adómentes** – feladatok mentesek a FLSA a túlóra.
-   **Nem mentes** – feladatok nem mentesek a FLSA a túlóra.
-   **Nem alkalmazható** – FLSA fedezeti nem vonatkozik.

## <a name="job-functions"></a>Beosztások
Feladat találkozását magas szintű funkcionális kategóriák írják le, és magas szintű vámok vonatkoznak. Beosztások nem lesz szükség. Beosztások típusai, és segítségével kiszűrheti a kompenzációs konstrukciók konkrét projektekre. Társítania beosztások és feladattípusok juttatási programok által a támogathatósági szabályok beállítása a **támogathatósági szabályok** oldalon. A feladat típusa és a jogosultság-szabály segítéségével beállított feladatkör egyedi kombinációja érvényes kompenzációs terv is csatolhatja a szintek egy halmazát. (Ezek a funkciók fix kompenzációs tervek és a változó kompenzációs konstrukciók vonatkozik.) Azonban ha szeretné használni a beosztások, kompenzációs kezelésére vonatkozó támogathatósági szabályok beállításakor, állítson be beosztások feladatok beállítása előtt. A következő táblázat néhány példát mutat feladatokkal kapcsolatos funkciókat.

| Munka           | Beosztás      |
|---------------|-------------------|
| Értékesítési igazgató | Középkategóriás kezelő |
| Könyvelő    | Szakemberek számára     |

Megmaradjanak a projekt funkciók segítségével a **feladatkörét** oldalon. A a **feladatkörét** lap, adja meg azonosítóját és a feladatkör rövid leírását.

## <a name="job-tasks"></a>Munkaköri feladatok
Munkaköri feladatok leírása alapvető feladatok, a munkavállaló, aki a projekt olyan helyzetben kell végeznie. Az azonos projektfeladat több feladat, és a projektfeladatok alkalmazó feladatok beosztások adhatók meg. A következő táblázat néhány példát mutat a projektfeladatok.

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
<li><strong>A Teljesítményfigyelő-áttekintés</strong> – tekintse át az egyes üzletkötők teljesítménye-feldolgozás.</li>
<li><strong>ABS-felülvizsgálati</strong> – jóváhagyása vagy elutasítása az egyes üzletkötők távolléti kérelmek vagy -regisztráció.</li>
</ul></td>
</tr>
<tr class="even">
<td>Könyvelő</td>
<td><strong>FIN-jelentés</strong> – heti pénzügyi jelentéseket nyújt be a pénzügyi igazgató.</td>
</tr>
</tbody>
</table>

Megmaradjanak a munkaköri feladatok segítségével a **projektfeladatok** oldalon. A a **projektfeladatok** lap, adja meg nevét és leírását a projektfeladatra vonatkozóan. A a **Megjegyzés:** mező, tetszés szerint adjon meg további információkat. A megjegyzések egy adott feladat az itt megadott megjegyzések módosítása nélkül lehet frissíteni.

## <a name="areas-of-responsibility"></a>Hatáskörök
Hatáskörök segítségével adja meg a munka szerepek, folyamatok és termékek, amely felelős a munkavállaló, aki a projekt olyan helyzetben van. Például "Könyvelő" nevű projekt, egy felelősségi köre lehet "Pénzügyi jelentési termék A." Megmaradjanak a hatáskörök segítségével a **hatáskörök** lapot, amely a keresés funkció használatával is megtalálhatja. A a **hatáskörök** lap, adja meg nevét és leírását a felelősség. A a **Megjegyzés:** mező, tetszés szerint adjon meg további információkat. A megjegyzések egy adott feladat az itt megadott megjegyzések módosítása nélkül lehet frissíteni.


