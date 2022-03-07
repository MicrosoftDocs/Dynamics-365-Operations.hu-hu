---
title: A vegyes azonosítótábla-fogadás nem működik az összes intézkedési kódnál
description: Ha egy intézkedési kód Művelet mezőjének beállítása Jóváírás vagy Selejt, akkor csak a Vegyes azonosítótábla bevételezése menüpontot használhatja a visszaküldött elemek feldolgozásához.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b762255bc5ef6a1e15688a9c635940e92e67db3c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476577"
---
# <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-but-credit"></a>A vegyes azonosítótábla-fogadás nem működik semmilyen intézkedési kódnál, csak a Jóváírásnál.

## <a name="symptoms"></a>Tünetek

Ha egy intézkedési kód **Művelet** mezőjének beállítása *Jóváírás* vagy *Selejt*, akkor csak a [Vegyes azonosítótábla bevételezése](/dynamics365/supply-chain/warehousing/mixed-license-plate-receiving) menüpontot használhatja a visszaküldött elemek feldolgozásához.

## <a name="resolution"></a>Megoldás

A Microsoft kiértékelte ezt a hibát, és megállapította, hogy ez egy funkciókorlátozás. Jelenleg csak azok az [intézkedési kódok](/dynamics365/supply-chain/service-management/set-up-disposition-codes) támogatottak a vegyes azonosítótábla fogadása esetén, ahol a **Művelet** mező *Jóváírás* vagy *Selejt*.
