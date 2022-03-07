---
title: Készlettulajdonos nem engedélyezett mozgások feldolgozásakor
description: A hiba akkor jelenik meg, ha "A(z) %1 készlettulajdonos nem engedélyezett". A Warehouse management folyamatok csak a jogi személy tulajdonában álló készletet támogatják.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4ee29cfc7bad990cd1ee5deaa98fca217af772ed
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476528"
---
# <a name="inventory-owner-not-allowed-when-processing-movements-in-the-warehouse-app"></a>Készlettulajdonos nem engedélyezett mozgások feldolgozásakor a raktári alkalmazásban

## <a name="symptoms"></a>Tünetek

A Warehouse Management mobilalkalmazásban a mozgások feldolgozásakor a következő hibaüzenet jelenik meg:

> A(z) %1 készlettulajdonos nem engedélyezett ebben a folyamatban.

## <a name="cause"></a>Ok

Ennek oka, hogy a **Tulajdonos** követési dimenziója hiányzik, amikor a Warehouse Management mobilalkalmazásban készletmozgatásokat végeznek. Úgy látszik, hogy a Supply Chain Management kliens rendszeres készletmozgatási naplót használ, és csak akkor lehet feladni, ha a **Tulajdonos** dimenzió ki van töltve.

## <a name="resolution"></a>Megoldás

A Microsoft kiértékelte ezt a hibát, és megállapította, hogy ez egy funkciókorlátozás. A raktárkezelési folyamatok jelenleg csak a jogi személy tulajdonában álló készletet támogatják.
