---
title: "A szolgáltatási állapot és az állapotjelző mező közötti kapcsolat"
description: "A Szervizrendelések képernyőn a szervizrendelés fejlécének Folyamat mezője a teljes szervizrendelés, míg az Állapot mező az egyes szervizrendelési sorok állapotát mutatja."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 51ef39266e8de00488954918568d00a297a9b50a
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---


# <a name="service-status-and-progress-field-interaction"></a>A szolgáltatási állapot és az állapotjelző mező közötti kapcsolat 

[!include [banner](../includes/banner.md)]


A **Szervizrendelések** képernyőn a szervizrendelés fejlécének **Folyamat** mezője a teljes szervizrendelés, míg az **Állapot** mező az egyes szervizrendelési sorok állapotát mutatja.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Folyamat</p></th>
<th><p>1. sor állapota</p></th>
<th><p>2. sor állapota</p></th>
<th><p>3. sor állapota</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Folyamatban</strong></p></td>
<td><p><strong>Létrehozva</strong></p></td>
<td><p><strong>Létrehozva</strong></p></td>
<td><p><strong>Létrehozva</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Folyamatban</strong></p></td>
<td><p><strong>Törölve</strong></p></td>
<td><p><strong>Létrehozva</strong></p></td>
<td><p><strong>Létrehozva</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Folyamatban</strong></p></td>
<td><p><strong>Létrehozva</strong></p></td>
<td><p><strong>Törölve</strong></p></td>
<td><p><strong>Feladva</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Törölve</strong></p></td>
<td><p><strong>Törölve</strong></p></td>
<td><p><strong>Törölve</strong></p></td>
<td><p><strong>Törölve</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Feladva</strong></p></td>
<td><p><strong>Feladva</strong></p></td>
<td><p><strong>Feladva</strong></p></td>
<td><p><strong>Feladva</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Feladva</strong></p></td>
<td><p><strong>Feladva</strong></p></td>
<td><p><strong>Törölve</strong></p></td>
<td><p><strong>Törölve</strong></p></td>
</tr>
</tbody>
</table>


A szervizrendelés folyamatban van, ha minden sor **Létrehozva** állapotú, és még mindig folyamatban levőnek számít, ha egyes sorok **Törölve** vagy **Feladva** állapotúak.

Ha egy szervizrendelés összes sor **Feladva** állapotúnak van megjelölve, a rendelés **Feladva** állapotú. Ha egyes sorok **Feladva**, mások **Törölve** állapotúak, a folyamat továbbra is **Feladva** állapotú.

  


