---
title: A szolgáltatási állapot és az állapotjelző mező közötti kapcsolat
description: A Szervizrendelések képernyőn a szervizrendelés fejlécének Folyamat mezője a teljes szervizrendelés, míg az Állapot mező az egyes szervizrendelési sorok állapotát mutatja.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0758c370fd1548770d596115b18f133071f3bbc0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566095"
---
# <a name="service-status-and-progress-field-interaction"></a>A szolgáltatási állapot és az állapotjelző mező közötti kapcsolat

[!include [banner](../includes/banner.md)]

A **Szervizrendelések** képernyőn a szervizrendelés fejlécének **Folyamat** mezője a teljes szervizrendelés, míg az **Állapot** mező az egyes szervizrendelési sorok állapotát mutatja.

<table>
<colgroup>
<col />
<col />
<col />
<col />
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

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
