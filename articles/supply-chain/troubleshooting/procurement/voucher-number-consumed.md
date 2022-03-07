---
title: A rendszer akkor is felhasználja a termékbevételezési bizonylatszámot, ha nem generál bizonylatot
description: A termék bevételezési bizonylatának száma akkor is fel lesz használva, ha a termék bevételezése során nem készül pénzügyi bizonylat
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 0556969950c45e80d177a0e96096c4157d690ae3
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476546"
---
# <a name="a-product-receipt-voucher-number-is-consumed-even-when-not-generating-a-voucher"></a>A rendszer akkor is felhasználja a termékbevételezési bizonylatszámot, ha nem generál bizonylatot

## <a name="symptoms"></a>Tünetek

A termék bevételezési bizonylatának száma akkor is fel lesz használva, ha a termék bevételezése során nem készül pénzügyi bizonylat.

## <a name="resolution"></a>Megoldás

Ha a **Kötelezettség elhatárolása termékbevételezéskor** beállítás értéke *Nem* cikkmodell-csoporthoz, akkor nem történik feladás a főkönyvbe. A program azonban egy fizikai eseményt rögzít egy analitikába történő könyvelés céljából, és az eseményhez bizonylatszámot kell megadni. Ez a bizonylatszám a készlettranzakciókban hivatkozott bizonylatszám.

Azt ajánljuk, hogy a **Kötelezettség elhatárolása termékbevételezéskor** beállítás *Igen* értékre állítsa , a következő blogbejegyzésben leírtak szerint: [Vegyes költségek feladása terméknyugta időpontjában](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).
