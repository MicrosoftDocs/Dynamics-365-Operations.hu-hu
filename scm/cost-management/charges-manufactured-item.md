---
title: "A gyártott cikk költségeinek megjelenítése"
description: "A legyártott cikk állandó költségei a művelet beállítási idejét és az állandó mennyiséggel vagy állandó selejtmennyiséggel megadott összetevőket tükrözik."
author: YuyuScheller
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: cd1d44362006fd5d2f439888f5ab59c66bb48169
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017

---

# <a name="display-charges-for-a-manufactured-item"></a>A gyártott cikk költségeinek megjelenítése

[!include[banner](../includes/banner.md)]


A legyártott cikk állandó költségei a művelet beállítási idejét és az állandó mennyiséggel vagy állandó selejtmennyiséggel megadott összetevőket tükrözik.

A cikk költségének kiszámított összege megjeleníthető a cikk egységenkénti költségével. A költségek azonban néha két külön mező formájában jelennek meg, és nem szerepelnek a cikk egységköltségeiben. Amikor a költségek külön mezőkben jelennek meg, az egyik mező a költségek teljes összegét, a második mező pedig a költségszámítási adag méretét jeleníti meg, amelyet az összeg amortizációjához használ a rendszer. A Cikk ára lap például a költségeket két külön mezőként jeleníti meg. A Teljesített lap azonban a cikk teljes egységenkénti költségét jeleníti meg, és az egységköltségben szerepelnek az amortizált költségek.
A legyártott cikkeknél a költségek az elszámolóárak szempontjából mindig szerepelnek a cikk egységköltségében. A tervezett költségek szempontjából választhatóan szerepeltethetők. A költségszámítási verzióban alkalmazott szabály érvényesíti a költségeknek a legyártott cikk költségében való szerepeltetését. A cikk költségrekordjának aktiválása frissíti a cikk alapköltségadataihoz tartozó költségeket, amely a Cikk ára lapon látható. A költségek két külön mező formájában jelennek meg, és nem szerepelnek a cikk egységköltségében. Minden aktiválás frissíti a cikk alapköltségadatait, még abban az esetben is, ha az aktiválás különböző helyekre vonatkozik. Ennek megfelelően az alapköltségadatokat referenciaadatnak kell tekinteni.






