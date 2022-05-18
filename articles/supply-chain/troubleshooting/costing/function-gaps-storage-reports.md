---
title: A készletérték/korosítási jelentések és tárolási verzióik közötti működési hézagok
description: A készletérték/korosítási jelentések és tárolási verzióik közötti működési hézagok
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f74389648034bf036ce48ac84b3421a8a340f105
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686653"
---
# <a name="functional-gaps-between-inventory-valueaging-reports-and-their-storage-versions"></a>A készletérték/korosítási jelentések és tárolási verzióik közötti működési hézagok

A [kKészletkorosítási jelentés tárolása](/dynamics365/supply-chain/cost-management/inventory-aging-report-storage) és a [Készletérték-tárolási jelentés](/dynamics365/supply-chain/cost-management/inventory-value-report-storage) funkció lehetővé teszik a Supply Chain Management számára, hogy megjelenítse a készlettranzakciók nagy mennyiségét. Minden esetben a jelentés eredményei a böngészés és az exportálás esetében kerülnek mentésre, ellentétben a jelentések nem tárolt verzióival. Előfordulhat azonban, hogy a jelentések nem tárolt verzióiban létező funkciók nem szerepelnek a tárolási verziókban. A következő alszakaszok összefoglalják a különbségeket, és megoldásokat kínálnak.

## <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>A tárolási jelentések nem tartalmazzák a részösszegeket, még akkor sem, ha engedélyezve vannak a jelentés elrendezésében.

A részösszegek problémákat okozhatnak az eredmény exportálásakor, különösen akkor, ha a felhasználók módosítják a rekordsorozatot.

A részösszegek ellenőrzéséhez exportálni lehet az eredményt Microsoft Excel. Ha azt szeretné, hogy a Supply Chain Managementen belül ellenőrizze a részösszegeket, használja [Funkciókezelést](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) és engedélyezze az *Új rácsvezérlő* és a *Csoportosítás a rácsokban* funkciókat, amelyek sokkal rugalmasabban használhatók a csoportosítási oszlop részösszegeinak megjelenítéséhez. További információkért lásd az [Rácsfunkciók](/dynamics365/fin-ops-core/fin-ops/get-started/grid-capabilities) részt.

## <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>A készletérték-tárolási jelentés nem támogatja a főkönyvi fiók adatait

A főkönyvi kivonatot úgy futtathatja, hogy beolvassa a készletfiókok egyenlegét, és összehasonlítja a **Készletérték-tárolás** jelentéssel.
