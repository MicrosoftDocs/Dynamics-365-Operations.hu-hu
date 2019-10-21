---
title: Adja meg a számla és dimenzió kombinációkat (szegmentált bejegyzés ellenőrzés)
description: A cikk bemutatja, hogyan adhat meg számla és dimenzió kombinációkat vagy főkönyvi számlákat. A bejegyzés tapasztalatot gyakran nevezik szegmentált bejegyzés ellenőrzésnek.
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14071
ms.assetid: e6fce826-c403-4d91-a78b-e9a58c44ac03
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 872ee7812d98e6102798c3a10773176541c02c90
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186647"
---
# <a name="enter-account-and-dimension-combinations-segmented-entry-control"></a>Adja meg a számla és dimenzió kombinációkat (szegmentált bejegyzés ellenőrzés)

[!include [banner](../includes/banner.md)]

A cikk bemutatja, hogyan adhat meg számla és dimenzió kombinációkat vagy főkönyvi számlákat. A bejegyzés tapasztalatot gyakran nevezik szegmentált bejegyzés ellenőrzésnek.

A felhasználók több oldalon adhatnak meg számla- és dimenziókombinációkat, például általános naplók, költségvetés-tervezés és feladásdefiníciók. Az érvényes számla és dimenzió kombináció a főkönyvhöz rendelt számlastruktúrától és a számlastruktúrához rendelt speciális szabályok függ. Amikor egy felhasználó megad egy kombinációt, begépelheti az értékeket vagy élvezheti a gazdag keresési tapasztalatok előnyeit. Amikor belép a mezőbe, elkezdhet gépelni, és a rendszer megkeresi az értéket és a leírást. Például ha 180-at ír be, a rendszer minden értéket megkeres, amely ezzel a számkombinációval kezdődik. Vagy ha azt írja be, hogy Készpénz, a rendszer minden értéket megkeres, amely leírása a Készpénz szóval kezdődik. Helyettesítő karaktert is használhat (például \*Készpénz vagy \*180) a keresésre, ha az érték vagy a leírás tartalmazza a keresési feltételeket. 

A következő táblázat leírja a gyorsbillentyűket, amelyek akkor használhatóak, amikor a keresés le van zárva.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Billentyűparancs</th>
<th>Művelet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Alt+Lefelé nyíl</td>
<td>A keresés megnyitása Alt + le billentyű másodszori lenyomása után a fókusz a menü szegmenseire áll.</td>
</tr>
<tr class="even">
<td><ul>
<li>Adja meg, és nyomja le a Shift + Enter kombinációt</li>
<li>Számlatükör-elválasztó</li>
<li>Felfelé nyíl és jobbra nyíl</li>
</ul></td>
<td>Ugrás a következő vagy az előző szegmensre</td>
</tr>
<tr class="odd">
<td>Lap</td>
<td>Lépjen a következő mezőre a rácson.</td>
</tr>
</tbody>
</table>

A következő táblázat leírja a gyorsbillentyűket, amelyek akkor használhatóak, amikor a keresés nyitott.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Billentyűparancs</th>
<th>Művelet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Esc</td>
<td>Zárja be a keresést.</td>
</tr>
<tr class="even">
<td><ul>
<li>Felfelé nyíl és lefelé nyíl</li>
<li>Page Up és Page Down</li>
<li>Home és End</li>
</ul></td>
<td>Lépjen az előző vagy következő értékre a listában, az előző vagy a következő értékcsoportra, vagy a keresés első vagy utolsó elemére.</td>
</tr>
<tr class="odd">
<td><ul>
<li>Számlatükör-elválasztó</li>
<li>Felfelé nyíl és jobbra nyíl</li>
</ul></td>
<td>Ugrás a következő vagy az előző szegmensre</td>
</tr>
<tr class="even">
<td>Lap</td>
<td>Lépjen a következő mezőre a rácson.</td>
</tr>
<tr class="odd">
<td>Alt+W</td>
<td>Váltás <strong>Minden megjelenítése</strong> és <strong>Érvényesek megjelenítése</strong> módok között.</td>
</tr>
</tbody>
</table>





