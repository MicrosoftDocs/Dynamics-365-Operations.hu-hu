---
title: A beszerzési rendelés nyugtája nem tartalmaz minden költséget
description: A beszerzési rendelés nyugtája nem tartalmaz minden költséget
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: bb567e00ef52269db0dc866148a37c73f0a9827c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476510"
---
# <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a>A beszerzési rendelés nyugtája nem tartalmaz minden költséget

## <a name="symptoms"></a>Tünetek

Beszerzési rendelés bevételezése esetén nem minden költség szerepel a nyugtán.

### <a name="reproduce-the-issue"></a>A hiba reprodukálása

A következő eljárás bemutatja a hiba reprodukálásának egyik módját.

1. A **Beszerzés és forrás paraméterei lap** **Szállítás** lapján győződjön meg arról, hogy a **Díjak generálása terméknyugtán** beállítás *Igen* értékre van állítva.
1. Hozzon létre egy költségeket tartalmazó beszerzési rendelést.
1. Erősítse meg a beszerzési rendelést.
1. Fogadja a beszerzési rendelést.
1. Tekintse meg a nyugta összegét, és hasonlítsa össze a várt összeggel.
1. Figyelje meg, hogy nem minden költség szerepel a beszerzési rendelés nyugtáján.

## <a name="resolution"></a>Megoldás

A megoldás a vegyes költségek beállításának módjától függ. A vegyes költségnek az igények teljesítése céljából történő beállításával kapcsolatos további tudnivalókat lásd a következő blogbejegyzésben: a [Vegyes költségek feladása terméknyugta időpontjában](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).
