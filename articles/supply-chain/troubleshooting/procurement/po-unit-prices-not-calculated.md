---
title: A beszerzési rendeléseken szereplő egységárak számítása nem a mértékegység-átváltás alapján történik
description: A beszerzési rendeléseken szereplő egységárak számítása nem a mértékegység-átváltás alapján történik
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
ms.openlocfilehash: 4695f4661c3abb8ab38e3ca74b513e8529e37d20
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476547"
---
# <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a>A beszerzési rendeléseken szereplő egységárak számítása nem a mértékegység-átváltás alapján történik

## <a name="symptoms"></a>Tünetek

Amikor egy egység megváltozik egy beszerzési rendelésen, a kereskedelmi megállapodás árai nem lesznek újraszámítva a mértékegység-átváltás definíciói szerint.

## <a name="cause"></a>Ok

Az árak mindig a kereskedelmi megállapodásokból (vagy a rendszerben szereplő egyéb áraktól, például az értékesítési megállapodások vagy a cikkek áraiból) vannak lekérve, és egy mértékegységhez vannak beállítva.

Ha egy rendelési sorban módosul az egység, a rendszer az új árat keres az egységhez, és ezt az árat alkalmazza. Ha nem talál árat a egységhez, akkor a rendszer nem alkalmaz árat. A mértékegység-átalakítás nem használható az ár másik egységbe történő átszámítására. Elméletileg a tíz dobozt tartalmazó egység ára nem biztos, hogy tízszerese egy doboz árának.

## <a name="workaround"></a>Megkerülő megoldás

A probléma megkerülésének egyik módja annak ellenőrzése, hogy vannak-e kereskedelmi megállapodások azokhoz az egységekhez, amelyek várhatóan használva lesznek a cikk rendelési soraihoz.
