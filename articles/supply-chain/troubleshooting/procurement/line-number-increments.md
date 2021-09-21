---
title: Az importált beszerzési rendelések helytelen sorszámokat mutatnak.
description: Amikor a beszerzési rendeléseket adatkezelés útján importálja, a beszerzésirendelés-sorok száma nem követi a rendszer paraméterei között megadott növekményt
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: e1cf5cf1d04824213f495ac3ebf556796c96611a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476507"
---
# <a name="imported-purchase-orders-show-incorrect-line-numbers"></a>Az importált beszerzési rendelések helytelen sorszámokat mutatnak.

## <a name="symptoms"></a>Tünetek

Alapértelmezés szerint a az automatikusan generált sorszámok a beszerzésirendelés-sorokhoz, amelyek a *Beszerésirendelés-sorok V2* adatentitáson keresztül vannak importálva, nem használják a rendszer számnövekményét, ami a rendszerparaméterekben van meghatározva. Ha kézzel hoz létre egy beszerzési rendelést, és a felhasználói felületen (UI) keresztül ad hozzá sorokat, akkor a program a sorszámokat helyesen növeli. Az Adatkezelési keretrendszer (DMF) használata esetén azonban nem megfelelőek a növekmények.

Ez a probléma azért fordulhat elő, mert amikor DMF keresztül importál sorokat, ha a sorok száma még nincs hozzárendelve az importált entitáshoz, akkor a rendszer a DMF metódusát használja a hozzárendelésekhez. Ez a módszer mindig eggyel növeli a sorszámokat.

## <a name="workaround"></a>Megkerülő megoldás

Ügyeljen arra, hogy a kívánt sorszámok már meg legyenek adva az adatelem sorszám mezőiben a beszerzésirendelés-sorok importálásakor. Ebben az esetben a DMF nem írja felül a sorszámokat.
