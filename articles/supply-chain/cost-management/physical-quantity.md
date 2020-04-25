---
title: Készletobjektum-értékek
description: Ez a cikk tájékoztatást egy készletobjektum értékekének számításáról.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ff3a21e87b9cb0bb371b0772c948cb62a4cb36b1
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214619"
---
# <a name="inventory-object-values"></a>Készletobjektum-értékek

[!include [banner](../includes/banner.md)]

Ez a cikk tájékoztatást egy készletobjektum értékekének számításáról. 

Egy új funkció, aminek a neve **Fizikai mennyiség**, lehetővé teszi, hogy lássa egy megadott készletobjektum értékét. 

Egy költségobjektum annak az entitás szintnek felel meg, ahol a készletkönyvelést végzik. A költségobjektummal kapcsolatos további tudnivalókat lásd: [Költségobjektum](cost-object.md). 

Egy adott készletobjektum értékeinek megtekintéséhez kattintson a **Fizikai mennyiség** lehetőségre a **Költségobjektum** oldalon. Egy készletobjektum értéke az alábbi módon lesz kiszámolva: 

Készletobjektum.Értéke = Költségobjektum.Átlagos egységenkénti költsége × Készletobjektum.Mennyisége. 

Az alábbi példában látható, hogy a készletobjektum értéke és a költségobjektum hogyan számolható ki. Két termékbevételezési esemény van az A cikken rögzítve:

-   Termékbevételezés 1: Mennyiség = 100 darab. Összeg = 1 000,00 $ Hely = 1 Raktár = 11, Köteg száma = B1
-   Termékbevételezés 2: Mennyiség = 50 darab. Összeg = 800,00 $ Hely = 1 Raktár = 11, Köteg száma = B2

Az alábbi táblázat a költségobjektum-számítás eredményét mutatja. Az eredményeket megtekintheti a **Költségobjektum** oldalon.

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th>Objektumtípus</th>
<th>Cikkszám</th>
<th>Hely</th>
<th>Mennyiség</th>
<th>Készletegység</th>
<th>Érték</th>
<th>Átlagos egységenkénti költség</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Költségobjektum</td>
<td>N</td>
<td>1</td>
<td>150</td>
<td>Darab</td>
<td><p>1800.00 $</p></td>
<td><p>12.00 $</p></td>
</tr>
</tbody>
</table>

Az alábbi táblázat a készletobjektum-számítás eredményét mutatja. Az eredményeket megtekintheti a **Fizikai mennyiség** lehetőségnél, a **Költségobjektum** oldalon.

<table style="width:100%;">
<colgroup>
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th>Objektumtípus</th>
<th>Cikkszám</th>
<th>Hely</th>
<th>Raktár</th>
<th>Kötegsz.</th>
<th>Mennyiség</th>
<th>Készletegység</th>
<th>Érték</th>
<th>Átlagos egységenkénti költség</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Készletobjektum</td>
<td>N</td>
<td>1</td>
<td>11</td>
<td>B1</td>
<td>100</td>
<td>Darab</td>
<td><p>1200.00 $</p></td>
<td><p>12.00 $</p></td>
</tr>
<tr class="even">
<td>Készletobjektum</td>
<td>A</td>
<td>1</td>
<td>11</td>
<td>B2</td>
<td>50</td>
<td>Darab</td>
<td><p>600.00 $</p></td>
<td><p>12.00 $</p></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a>További erőforrások
--------

[Költségobjektumok](cost-object.md)

[Költségbejegyzések](cost-entries.md)

[Új és módosult elemek](../../fin-and-ops/get-started/whats-new-changed.md)



