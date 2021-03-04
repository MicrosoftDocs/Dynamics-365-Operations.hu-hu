---
title: Feladat összetevőinek beállítása
description: Ez a cikk azt ismerteti, milyen fogalmi elemek alkothatnak egy feladatot, és példákat ad arra, hogyan használhatja ezen elemeket a szervezetben.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: anbichse
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources, Retail
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 69759c0488563a904f6e80afacb1802611ab1930
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418839"
---
# <a name="set-up-the-components-of-a-job"></a>Feladat összetevőinek beállítása

Ez a cikk azt ismerteti, milyen fogalmi elemek alkothatnak egy feladatot, és példákat ad arra, hogyan használhatja ezen elemeket a szervezetben. 

Feladatok létrehozása előtt be kell állítania bizonyos referenciaadatokat. Létrehozhat olyan feladatot is, amelynek csak neve van. További információk - például beosztás - megadásával viszont alapértelmezett értékek biztosíthatók a feladathoz rendelt beosztások számára. Emellett a beírt adatok egy része használható kompenzációs konstrukciók szűréséhez konkrét feladatokhoz. Ha szeretne jogosultságot beállítani, amelyet felhasználhat bizonyos feladathoz tartozó kompenzációs konstrukciók szűrésére, úgy állítson be feladatbeosztásokat és feladattípusokat a feladatok beállítása előtt. Ha ezen alapértelmezett értékek elérhetők, időt takaríthat meg, amikor beosztások hozzáadását végzi a feladathoz. 

Egyes feladatadatok, például a beosztás, a típus és a funkció dátumfüggőek. Ha ma létrehoz egy feladatot, de ezeket az adatokat csak később adja hozzá, és aztán megnézi a feladatot a létrehozás dátuma szerint, úgy ezek az adatok nem jelennek meg. Ezért célszerű létrehozni ezeket az információkat még azelőtt, hogy szükség lenne rájuk. Ily módon az információkat hozzáadhatja új feladatok létrehozásakor.

## <a name="job-titles"></a>Beosztások
A létrehozni kívánt beosztásokhoz titulusokat is be kell állítania. A pozíciók azon beosztások titulusait öröklik, amelyekhez hozzárendelték őket. 

Beosztások karbantartásához használja a **Beosztások** oldalt, amely a keresés funkció segítségével nyitható meg. A **Beosztások** oldalon írja be a beosztásokat, amelyeket használni tervez a feladatokhoz.

## <a name="job-types"></a>Beosztástípusok
Beosztástípusok segítségével a hasonló feladatok kategóriákba sorolhatók. A beosztástípusok használata nem kötelező, azonban ha a későbbiekben a kompenzációkezelés jogosultsági szabályainak beállításakor szeretne beosztástípusokat használni, ezeket még a beosztások előtt kell beállítania. Beosztástípusok például teljes és részmunkaidős, illetve a munkabéres és az órabéres. A beosztástípusok karbantartásához használja a **Beosztástípusok** oldalt. A **Beosztástípusok** oldalon adja meg a beosztástípus nevét és rövid leírását. A **Mentességi állapot** mezőben a következő lehetőségek közül választhat annak jelzésére az ilyen beosztástípusú feladatoknál, hogy az Egyesült Államok munkajogi törvénye (FLSA, Fair Labor Standards Act) ezekre a feladatokra nem vonatkozik:

-   **Mentes** – A beosztásokhoz az FLSA szerint túlórapénz nem jár.
-   **Nem mentes** – A beosztásokhoz az FLSA szerint túlórapénz jár.
-   **Nem alkalmazható** – Az FLSA hatálya erre nem terjed ki.

## <a name="job-functions"></a>Beosztások
A beosztási funkciók magas szintű funkcionális kategóriákat írnak le magas szintű feladatokat írnak elő. A beosztási funkciók használata nem kötelező, A beosztási funkciókat és beosztási típusokat együttesen felhasználva az egyes feladatokhoz hozzá lehet szűrni a kompenzációs konstrukciókat. A feladatfunkciók és feladattípusok kompenzációs konstrukciókhoz társítása az **Alkalmazhatósági szabályok** oldalon, alkalmazhatósági szabályok felállításával történik. Ezen túlmenően a kompenzációs konstrukcióhoz hozzá lehet csatolni a szintek azon csoportját, amelyek az alkalmazhatósági szabály által behatárolt, adott feladattípus/feladatfunkció kombinációra vonatkoznak. (Ezek a funkciók mind a fix, mind a változó kompenzációs konstrukcióra vonatkoznak.) A beosztásfunkciók használata nem kötelező, azonban ha a későbbiekben a kompenzációkezelés jogosultsági szabályainak beállításakor szeretne beosztásfunkciókat használni, ezeket még a beosztások előtt kell beállítania. Az alábbi táblázatban látható néhány példa munkaköri beosztásokra.

| Munka           | Beosztás         |
|---------------|----------------------|
| Értékesítési igazgató | Középvezetői szint    |
| Könyvelő    | Szakemberek        |

A beosztási funkciók karbantartásához használja a **Beosztási funkciók** oldalt. A **Beosztási funkciók** oldalon adja meg a beosztási funkció azonosító kódját és rövid leírását.

## <a name="job-tasks"></a>Munkaköri feladatok
A munkaköri feladatok bemutatják az adott pozíciójú dolgozótól elvárt alapvető feladatokat. Ugyanazon munkaköri feladatok több munkához, valamint a munkaköri feladatokat használó munkákkal kapcsolatos beosztásokhoz is hozzáadhatók. Az alábbi táblázatban látható néhány példa munkaköri feladatokra.

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
<li><strong>Teljesítményellenőrzés</strong> – Az egyes értékesítők teljesítményének áttekintése.</li>
<li><strong>Hiányzásellenőrzés</strong> – Az üzletkötők távolléti kérelmeinek vagy regisztrációnak jóváhagyása vagy elutasítása.</li>
</ul></td>
</tr>
<tr class="even">
<td>Könyvelő</td>
<td><strong>Pénzügyi jelentés</strong> – Heti pénzügyi jelentések bemutatása a pénzügyi igazgatónak.</td>
</tr>
</tbody>
</table>

A munkaköri feladatok karbantartásához használja a **Munkaköri feladatok** oldalt. A **Munkaköri feladatok** oldalon adja meg a munkaköri feladat nevét és leírását. A **Megjegyzés** mezőben igény szerint további információkat is megadhat. A megjegyzések anélkül frissülnek az adott feladathoz, hogy az itt Ön által megadott megjegyzések módosulnának.

## <a name="areas-of-responsibility"></a>Hatáskörök
Alkalmazzon hatásköröket azon a szerepkörök, folyamatok, termékek és műveletek megjelöléséhez, amelyekért a dolgozó egy adott beosztásban felelős. Például a „Könyvelő” nevű beosztáshoz tartozó hatáskörre példa lehet a „Pénzügyi jelentés az A termékkel kapcsolatban”. A hatáskörök karbantartására használja a **Hatáskörök** oldalt, amelyet a keresés funkció használatával találhat meg. A **Hatáskörök** oldalon adja meg a hatáskör nevét és leírását. A **Megjegyzés** mezőben igény szerint további információkat is megadhat. A megjegyzések anélkül frissülnek az adott feladathoz, hogy az itt Ön által megadott megjegyzések módosulnának.

## <a name="steps-for-creating-a-job"></a>A feladat létrehozásának lépései
Lásd az [Új feladatok meghatározása](../fin-and-ops/hr/tasks/define-new-jobs.md) cikket az új feladat létrehozásának lépésről lépésre útmutatójához. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]