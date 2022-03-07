---
title: A termékbevételezési feladat frissítése megerősíti a nem megerősített rendeléseket
description: A termékbizonylatok frissítése funkció futtatása után a rendszer megerősíti az olyan meg nem erősített rendeléseket, amelyek állapota Regisztrált. Ismerje meg a problémát kijavító funkciót.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 171a978efc6b55b92f429381e72036cb1b3296c6
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476517"
---
# <a name="unconfirmed-purchase-orders-are-confirmed-after-running-update-product-receipts"></a>A Termékbevételezések frissítése futtatása után a meg nem erősített beszerzési rendelések megerősítést nyernek

## <a name="symptoms"></a>Tünetek

A *Termékbevételezések frissítése* időszakos feladat futtatása után a rendszer automatikusan megerősíti a *Regisztrált* készlettranzakciós állapotú meg nem erősített beszerzési rendeléseket.

## <a name="resolution"></a>Megoldás

Egy új bejövő rakománykezelési funkció, a *Rakománymennyiségek túlbevételezése* megoldja ezt a problémát. A funkció bekapcsolásához, menjen a [Funkciókezelés](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) munkaterületre, és kapcsolja be a következő funkciókat ebben a sorrendben:

1. Beszerzési rendelés készlettranzakcióinak társítása rakománnyal
2. Rakománymennyiségek túlbevételezése

További információ: [A regisztrált termékmennyiségek feladása a beszerzési rendelésekkel szemben](/dynamics365/supply-chain/warehousing/inbound-load-handling).
