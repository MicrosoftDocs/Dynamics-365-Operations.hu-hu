---
title: "Projekt beszerzési rendelései"
description: "Ez a cikk különböző a módszereket ismerteti, amelyekkel beszerzési rendeléseket hozhat létre egy projekthez. A használt módszer attól függ, hogy mi a beszerzési rendelés célja, hogy a cikkek mikor kerülnek felhasználásra, hogy mikor kerül sor a cikkek elszámolására egy projektnél."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 2a0c21c2937600d1e31f9326970e52e3bdcff90c
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="purchase-orders-for-a-project"></a>Projekt beszerzési rendelései

[!include[banner](../includes/banner.md)]


Ez a cikk különböző a módszereket ismerteti, amelyekkel beszerzési rendeléseket hozhat létre egy projekthez. A használt módszer attól függ, hogy mi a beszerzési rendelés célja, hogy a cikkek mikor kerülnek felhasználásra, hogy mikor kerül sor a cikkek elszámolására egy projektnél.

A Microsoft Dynamics 365 for Operations rendszerben többféleképpen hozhat létre beszerzési rendeléseket egy projekthez. A használt módszer attól függ, hogy mi a beszerzési rendelés célja, hogy a beszerzett cikkek mikor kerülnek felhasználásra, hogy mikor kerül sor a beszerzett cikkek elszámolására egy projektnél.

### <a name="methods-for-creating-a-purchase-order"></a>Beszerzési rendelés létrehozásának módszerei

A következő módszerek valamelyikét használhatja egy beszerzési rendelés létrehozásához a Projektvezetés és könyvelés modulban. A beszerzési rendelés célja meghatározza, hogy mikor történik meg a beszerzési rendelés felhasználása, és így azt is, hogy mikor kerül sor a cikkek elszámolására egy projektnél.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Mód</th>
<th>Cél</th>
<th>Cikkek felhasználása</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Beszerzési rendelés létrehozása közvetlenül egy projektből.</td>
<td>Ezzel a módszerrel a külső szállítótól egy projektben történő felhasználására szerezhet be cikkeket. A beszerzési rendelést két módon hozhatja létre:
<ul>
<li>Magából a projektből. Ilyenkor eleve definiálva van a beszerzési rendelés projektje.</li>
<li>A projekt beszerzési rendelés kikeresésével. Ki kell választani a létrehozandó beszerzési rendelés szállítóját és projektjét is.</li>
</ul></td>
<td>A cikkek felhasználása a szállítói számla frissítésekor történik.</td>
</tr>
<tr class="even">
<td>Beszerzési rendelés létrehozása egy értékesítési rendelés alapján.</td>
<td>Akkor használja ezt a módszert cikkek beszerzésére, amikor egy értékesítési rendelést hoz létre egy projektben.</td>
<td>A cikkek felhasználása az értékesítési rendelés vevőnek való számlázása esetén történik meg.</td>
</tr>
<tr class="odd">
<td>Beszerzési rendelés létrehozása cikkszükségletből.</td>
<td>Akkor használja ezt a módszert cikkek beszerzésére, amikor cikkszükségletet hoz létre egy projektből.</td>
<td>A cikkek felhasználása akkor történik meg, amikor a cikkszükséglet csomagjegyzéke frissül.</td>
</tr>
</tbody>
</table>

> [!NOTE] 
> Ha frissíti a szállítói számlát vagy a szállítólevelet, a program figyelmezteti, hogy a cikkszükséglet szállítólevelét is frissítse.




