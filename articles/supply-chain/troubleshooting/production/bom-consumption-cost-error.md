---
title: Anyagjegyzék consumptionCost értékhiba történt egy megrendelés befejezésekor
description: Amikor egy termelési rendelést próbál befejezni, egy hibaüzenet jelenik meg, amely szerint az anyagjegyzék consumptionCost értéke negatív kell legyen. A probléma ki lett javítva.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 737329d06022e899df8e4de5a27d76b21480da9e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476559"
---
# <a name="cant-end-a-production-order-because-of-a-bom-consumptioncost-value-error"></a>Anyagjegyzék consumptionCost értékhiba miatt nem lehet véglegesíteni a termelési rendelést

## <a name="symptoms"></a>Tünetek

Amikor egy termelési rendelést próbál véglegesíteni, a következő hibaüzenetet kapja:

> Az anyagjegyzék consumptionCost értéknek negatívnak kell lennie a készletből való kiadáskor.

## <a name="resolution"></a>Megoldás

A problémát a 10.0.15-ös kiadás javította.
