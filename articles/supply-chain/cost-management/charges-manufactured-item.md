---
title: A gyártott cikk költségeinek megjelenítése
description: A legyártott cikk állandó költségei a művelet beállítási idejét és az állandó mennyiséggel vagy állandó selejtmennyiséggel megadott összetevőket tükrözik.
author: JennySong-SH
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: f97495488dbbe504a5e79ef7f65fa97eb287d17b
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675431"
---
# <a name="display-charges-for-a-manufactured-item"></a>A gyártott cikk költségeinek megjelenítése

[!include [banner](../includes/banner.md)]

A legyártott cikk állandó költségei a művelet beállítási idejét és az állandó mennyiséggel vagy állandó selejtmennyiséggel megadott összetevőket tükrözik.

A cikk költségének kiszámított összege megjeleníthető a cikk egységenkénti költségével. A költségek azonban néha két külön mező formájában jelennek meg, és nem szerepelnek a cikk egységköltségeiben. Amikor a költségek külön mezőkben jelennek meg, az egyik mező a költségek teljes összegét, a második mező pedig a költségszámítási adag méretét jeleníti meg, amelyet az összeg amortizációjához használ a rendszer. A Cikk ára lap például a költségeket két külön mezőként jeleníti meg. A Teljesített lap azonban a cikk teljes egységenkénti költségét jeleníti meg, és az egységköltségben szerepelnek az amortizált költségek.

A legyártott cikkeknél a költségek az elszámolóárak szempontjából mindig szerepelnek a cikk egységköltségében. A tervezett költségek szempontjából választhatóan szerepeltethetők. A költségszámítási verzióban alkalmazott szabály érvényesíti a költségeknek a legyártott cikk költségében való szerepeltetését. A cikk költségrekordjának aktiválása frissíti a cikk alapköltségadataihoz tartozó költségeket, amely a Cikk ára lapon látható. A költségek két külön mező formájában jelennek meg, és nem szerepelnek a cikk egységköltségében. Minden aktiválás frissíti a cikk alapköltségadatait, még abban az esetben is, ha az aktiválás különböző helyekre vonatkozik. Ennek megfelelően az alapköltségadatokat referenciaadatnak kell tekinteni.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]