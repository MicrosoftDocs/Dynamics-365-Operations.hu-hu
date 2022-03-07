---
title: A dimenzió helye nem lehet üres, ha a sorozatszám be van állítva
description: Ha a sorozatszámos cikk átszállítási rendelésének létrehozása után a szállítás megerősítésekor hibaüzenet jelenik meg, az alapértelmezett bevételezési hely mező üres.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6f58c72438d5d1d93e59e46525debd65d44d9a76
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476588"
---
# <a name="error-when-confirming-shipment-after-creating-a-transfer-order-for-a-serial-item"></a>Hiba a szállítmány megerősítésekor egy sorozatszámos cikk átszállítási rendelésének létrehozása után

## <a name="symptoms"></a>Tünetek

Ha egy sorozatszámos cikkhez olyan raktárat hoz létre, amely engedélyezve van a speciális raktárkezelésnél (WMS), majd a munka befejezése után megpróbálja megerősíteni a szállítmányt, a következő hibaüzenet jelenik meg:

> A dimenzió helye nem lehet üres, ha a dimenziószám be van állítva.

## <a name="cause"></a>Ok

Ennek oka, hogy az **Alapértelmezett bevételezési hely** mező üres a raktár tranzitraktár „érkezési” raktárában.

## <a name="resolution"></a>Megoldás

A probléma megoldásához adjon meg egy alapértelmezett bevételezési helyet a tranzitraktárban. Győződjön meg arról, hogy ez a hely azonosítótábla-vezérelt.
