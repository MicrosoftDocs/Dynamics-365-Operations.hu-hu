---
title: Ugyanaz a kereskedelmi szerződés van kiválasztva értékesítésirendelés-sorok létrehozásakor
description: Ha egy adott dátumra vonatkozóan egynél több kereskedelmi megállapodás van megadva, a legalacsonyabb árat tartalmazó kereskedelmi megállapodás van mindig kiválasztva értékesítésirendelés-sorok létrehozásakor.
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
ms.openlocfilehash: a586a399fb349965b972191bec1271651bec5fcb
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476557"
---
# <a name="if-two-trade-agreements-exist-for-overlapping-dates-the-same-one-is-always-selected"></a>Ha két egymást átfedő dátumhoz létezik kereskedelmi megállapodás, akkor a program mindig ugyanazt választja

## <a name="symptoms"></a>Tünetek

Ha ugyanarra az időszakra vagy egymást átfedő időszakokra két kereskedelmi megállapodást határoznak meg, minden alkalommal úgy tűnik, hogy az adott cikkeket tartalmazó értékesítésirendelés-sorok létrehozásakor ugyanez a kereskedelmi megállapodás van kiválasztva.

## <a name="resolution"></a>Megoldás

Ha egy adott dátumra vonatkozóan egynél több kereskedelmi megállapodás van megadva, a legalacsonyabb árat tartalmazó kereskedelmi megállapodás van mindig kiválasztva. További tájékoztatásért töltse le a következő tanulmányt: [Kereskedelmi megállapodások a Microsoft Dynamics AX 2012-ben](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).
