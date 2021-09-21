---
title: A közvetlen szállítás nem képes feldolgozni a WMS-t engedélyező raktárat
description: Ha a raktárban engedélyezve van a WMS, akkor nem támogatja a közvetlen szállítást. A közvetlen szállítás használatához ki kell választania egy nem WMS-típusú terméket és raktárat.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 090e17091e9fb92c2065679bb9b04637214e2eea
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476604"
---
# <a name="direct-delivery-not-able-to-process-for-wms-enabled-warehouse"></a>A közvetlen szállítás nem képes feldolgozni a WMS-t engedélyező raktárat

## <a name="symptoms"></a>Tünetek

Ha egy cikket egy értékesítési sorhoz adnak hozzá közvetlen szállításra egy olyan raktárból, amely engedélyezve van raktárkezelésre (WMS), az értékesítési sor frissítése esetén a következő hibaüzenet jelenik meg:

> A közvetlen kiszállítás nem tudja feldolgozni az 1% raktárat, mert engedélyezve van a raktárkezelés. Adjon meg egy másik raktárat, amelyben nincs engedélyezve a raktárkezelés.

## <a name="resolution"></a>Megoldás

A Microsoft kiértékelte ezt a hibát, és megállapította, hogy ez egy funkciókorlátozás. Jelenleg a WMS nem támogatja a közvetlen kiszállítást. Ezért a közvetlen kiszállítás használatához ki kell választania egy nem WMS-típusú terméket és raktárat.
