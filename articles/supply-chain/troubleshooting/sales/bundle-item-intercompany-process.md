---
title: Csomagcikk nem támogatott a vállalatközi folyamatban
description: A csomagcikk nem érhető el beszerzésre. Az értékesítési rendelés csak a csomagcikk összetevőit vásárolja meg, magát a csomagcikket nem.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 21adc7d071837b762157364f6f8ed370c69c7fd3
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476554"
---
# <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a>Csomagcikkek nem támogatottak vállalatközi folyamatban

## <a name="symptoms"></a>Tünetek

A csomagolt cikk nem érhető el a beszerzési rendeléshez, mivel a csomagolt cikkhez tartozó értékesítésirendelés-sorok vizsgálatakor láthatja, hogy a mennyiség *0* (nulla), és az állapot *Visszavonva*.

## <a name="resolution"></a>Megoldás

Ez szándékosan van. Az értékesítési rendelés csak a csomagolt cikk elemeit vásárolja. Nem vásárolja meg magát a csomagolt elemet. Ha csomagban kell vásárolnia, gondolja végig, hogy csomagként kell-e megjelölni , mivel ez a funkció a bevétel-megjelenítési forgatókönyvekhez van tervezve. További információ a csomagolt cikkekkel kapcsolatosan: [Csomagok](/dynamics365/finance/accounts-receivable/revenue-recognition-setup).
