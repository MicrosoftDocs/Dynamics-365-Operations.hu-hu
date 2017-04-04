---
title: "Készlet érték"
description: "Ez a cikk tájékoztatást egy készletobjektum értékekének számításáról."
author: YuyuScheller
manager: AnnBe
ms.date: 2015-12-07 09 - 09 - 05
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 8898d5d91ffb4f73ea68f1251e1a99440e81bcd4
ms.lasthandoff: 03/29/2017


---

# <a name="inventory-object-values"></a>Készlet érték

Ez a cikk tájékoztatást egy készletobjektum értékekének számításáról. 

Egy új funkció nevű ** fizikai mennyiség ** lehetővé teszi egy adott készletdimenziós objektum mezőiben szereplő értékek. Egy költségobjektum annak az entitás szintnek felel meg, ahol a készletkönyvelést végzik. A költségobjektummal kapcsolatos további tudnivalókat lásd: [Költségobjektum](cost-object.md). Egy adott készletdimenziós objektum értékének megtekintéséhez kattintson **fizikai mennyiség** meg a **költség objektum** oldalon. Itt van egy készlet objektum értékének kiszámítási módját: készlet objektum. Érték = költség objektum. Átlagos egységköltség x készlet objektum. Mennyiség a következő példa mutatja a készlet objektum és a költség objektum értékének kiszámítási módját. Két termékbevételezési esemény van az A cikken rögzítve:

-   Szállítólevél 1: mennyiség = 100 pcs., összege = $1,000.00, hely = 1, raktári = 11, a Köteg száma = B1
-   Szállítólevél 2: mennyiség = 50 pcs., összege = $800.00, hely = 1, raktári = 11, a Köteg száma = B2

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
<td>A:</td>
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



<a name="see-also"></a>Lásd még
--------

[Cost objects](cost-object.md)

[Cost entries](cost-entries.md)

[Mi az új és módosult, a Microsoft Dynamics AX rendszerben](/dynamics365/operations/dev-itpro/get-started/whats-new-changed)


