---
title: Degresszív értékcsökkenés felosztás után
description: Ez a témakör azt a módszert ismerteti, amelyet a Tárgyi eszközök eszköz felosztása utáni értékcsökkenés kiszámítására használnak az egyenleg csökkentése módszerrel.
author: moaamer
manager: Ann Beebe
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-17
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ea89d54b9b8287d9c81b75a99c5808b5deb05cef
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976091"
---
# <a name="reduce-balance-depreciation-after-a-split"></a>Degresszív értékcsökkenés felosztás után

[!include [banner](../includes/banner.md)]

Ez a témakör azt a módszert ismerteti, amelyet a Tárgyi eszközök egy másik eszköz felosztása utáni értékcsökkenés kiszámítására használnak az egyenleg csökkentése módszerrel. Az eszközkönyvben konfigurált értékcsökkenési év a pénzügyi év. További információ: [Degresszív értékcsökkenés](reduce-balance-depreciation.md) és [Tárgyi eszköz felosztása](tasks/split-fixed-asset.md).

Ha egy tárgyi eszközt olyan pénzügyi időszakban oszt fel, amely későbbi, mint az eszköz beszerzésének időszaka, a degresszív értékcsökkenés az eszköz előző évi nettó könyv szerinti értékét (NBV) veszi figyelembe. Figyelembe veszi az eszközt felosztó tranzakcióból származó beszerzési és értékcsökkenés-kiigazítási tranzakciókat is. Ez a viselkedés azt feltételezi, hogy az eszközt egy pénzügyi évben szerezték be, és egy későbbi pénzügyi évben osztották fel. Az az összeg, amelyet a felosztás után az eredeti eszközre le kell csökkenteni, az eszköz felosztása előtti NBV-t, valamint a felosztásra feladott beszerzési és értékcsökkenési kiigazítási tranzakciót tükrözi.

Például a következő feltételek vannak érvényben:

- A pénzügyi időszak június 30-tól július 1-ig tart.
- A csökkentési egyenleg százaléka 18 százalék, és egy eszközt 2019 júniusában 10.000 dollár beszerzési áron szereznek be.
- Az első pénzügyi év értékcsökkenése 18.000 dollár, a havi értékcsökkenés 150 dollár, majd az eszköz értékcsökkenése 2019 novemberéig 738,75 dollár.
- 2019 novemberében az eszköz 80 százaléka feloszlik egy másik tárgyi eszközre.

[![Degresszív értékcsökkenés felosztás után](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)

Az eredeti eszköz értékcsökkenésének összege 1.822,25 dollár. Ez az összeg megegyezik az NBV-vel a felosztásos tranzakció feladása előtt (9111,25 dollár), valamint a felosztásos tranzakció feladása során keletkező beszerzési helyesbítés (-8000 dollár), valamint a felosztásos tranzakció során keletkező értékcsökkenési helyesbítés (711 dollár). Ezért a második év értékcsökkenése (1.822,25 × 18 százalék) ÷ 12 = 27,33 dollár.

Az új tárgyi eszköz értékcsökkenésének összege az első évben (8 000 × 18 százalék) ÷ 12 = 120 dollár.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]