---
title: A szállítói visszatérítés nem halmozott a számlák alapján
description: A szállítói visszatérítés nem halmozott a számlák alapján
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
ms.openlocfilehash: 9d4596a7351969bf181982a24ea1dcc6f5732831
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476595"
---
# <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a>A szállítói visszatérítés nem halmozott a számlák alapján

## <a name="symptoms"></a>Tünetek

Ha a feladott számlák különböző esedékességi dátummal rendelkeznek, akkor ezek a számlák nem tükröződnek a belőlük létrejövő szállítói visszatérítésekben.

## <a name="resolution"></a>Megoldás

A program nem veszi figyelembe a határidőt a szállítói visszatérítés kiszámításakor. Fontolja meg a rendszer testreszabását úgy, hogy a fizetési határidő és a számlához való viszonya jobban látható legyen a szállító tényleges visszatérítése kapcsán.
