---
title: Projekt beszerzési rendelései
description: Ez a cikk különböző a módszereket ismerteti, amelyekkel beszerzési rendeléseket hozhat létre egy projekthez. A használt módszer attól függ, hogy mi a beszerzési rendelés célja, hogy a cikkek mikor kerülnek felhasználásra, hogy mikor kerül sor a cikkek elszámolására egy projektnél.
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a4975b9f9e20906fb1259e36a07d8ef3db4f4fee
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174558"
---
# <a name="purchase-orders-for-a-project"></a>Projekt beszerzési rendelései

[!include [banner](../includes/banner.md)]

Ez a cikk különböző a módszereket ismerteti, amelyekkel beszerzési rendeléseket hozhat létre egy projekthez. A használt módszer attól függ, hogy mi a beszerzési rendelés célja, hogy a cikkek mikor kerülnek felhasználásra, hogy mikor kerül sor a cikkek elszámolására egy projektnél.

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

További tudnivalókért lásd: [Cikkek átvétele cikkszükségletből származó beszerzési rendelés alapján](tasks/receive-items-purchase-order-item-requirement.md).

