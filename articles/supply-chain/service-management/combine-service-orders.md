---
title: Szervizrendelések kombinálása
description: Lehetőség van a szervizrendelések kombinálására
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b94d81c431a068e891a0e05e996594f7e0be19f9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "311864"
---
# <a name="combine-service-orders"></a>Szervizrendelések kombinálása   

[!include [banner](../includes/banner.md)]


Ha automatikusan hoz létre szervizrendeléssorokat a **Szolgáltatási szerződések** képernyőn, kiválaszthat egyet a következő beállítások közül, hogy megadja a csoportosításuk módját:

  - **Szolgáltatási szerződés szerint**

  - **Szervizfeladat szerint**

  - **Alkalmazott szerint**

  - **A szolgáltatás tárgya szerint**

## <a name="example"></a>Példa

Létrehoz egy szolgáltatási szerződést, amelynek kezdő dátuma 2017. 03. 31. A **Szervizrendelések kombinálása** mezőben válassza ki a **Szolgáltatási tárgy szerint** lehetőséget. Ezzel létrehozza a következő szolgáltatásiszerződés-sorokat:

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Szerződéssor száma</p></th>
<th><p>Tranzakció típusa</p></th>
<th><p>Leírás</p></th>
<th><p>Intervallum</p></th>
<th><p>A szolgáltatás tárgya</p></th>
<th><p>Kezdő dátum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p><strong>Óra</strong></p></td>
<td><p>SAL1</p></td>
<td><p>Heti</p></td>
<td><p>X-1</p></td>
<td><p>2007. 04. 01.</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p><strong>Óra</strong></p></td>
<td><p>SAL2</p></td>
<td><p>Kéthetente</p></td>
<td><p>X-2</p></td>
<td><p>2007. 04. 01.</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p><strong>Óra</strong></p></td>
<td><p>SAL3</p></td>
<td><p>Heti</p></td>
<td><p>X-2</p></td>
<td><p>2007. 04. 01.</p></td>
</tr>
</tbody>
</table>


Nincs megadva időkeretet a szolgáltatási szerződés egyik sorához sem. Emiatt a szervizrendeléssorok nem kerülnek át másik napra arról a napról, amelyre a számítás után estek.

Ezután hozzon létre szervizrendeléssorokat a **Szervizrendelések létrehozása** képernyőn, 2007. 04. 01-től 2007. 04. 30-ig.

Összesen 10 szervizrendelést hoz létre. Mivel a kombinált beállítás, amelyet kiválasztott, **A szolgáltatás tárgya szerint** volt, minden létrehozott szervizrendelésben csak olyan szervizrendeléssorok szerepelnek, melyekben egy meghatározott szolgáltatási objektum szerepel. Azok a szervizrendeléssorok, amelyeket a szolgáltatási szerződésből generál, és amelyekben megegyezik a dátum és a szolgáltatási objektum, ugyanabba a szervizrendelésbe kerülnek.


> [!NOTE]
> <P>Ebben a példában a <STRONG>Szolgáltatáskezelés paraméterei</STRONG> képernyőn megadott naptárban nem szerepelnek lezárt napok.</P>



A szolgáltatási szerződés soraira megadott időkeretek meghatározzák a szervizrendeléssorok szervizrendeléseken történő további csoportosítását.

## <a name="see-also"></a>Lásd még

[Szervizrendelések automatikus létrehozása](create-service-orders-automatically.md)

  


