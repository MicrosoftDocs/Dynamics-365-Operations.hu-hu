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
ms.openlocfilehash: a72e2d32e755e137cebbc0bf7afb0bed08fb93f2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476576"
---
# <a name="functional-gaps-between-inventory-valueaging-reports-and-their-storage-versions"></a>A készletérték/korosítási jelentések és tárolási verzióik közötti működési hézagok

A [kKészletkorosítási jelentés tárolása](/dynamics365/supply-chain/cost-management/inventory-aging-report-storage.md) és a [Készletérték-tárolási jelentés](/dynamics365/supply-chain/cost-management/inventory-value-report-storage.md) funkció lehetővé teszik a Supply Chain Management számára, hogy megjelenítse a készlettranzakciók nagy mennyiségét. Minden esetben a jelentés eredményei a böngészés és az exportálás esetében kerülnek mentésre, ellentétben a jelentések nem tárolt verzióival. Előfordulhat azonban, hogy a jelentések nem tárolt verzióiban létező funkciók nem szerepelnek a tárolási verziókban. A következő alszakaszok összefoglalják a különbségeket, és megoldásokat kínálnak.

## <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>A tárolási jelentések nem tartalmazzák a részösszegeket, még akkor sem, ha engedélyezve vannak a jelentés elrendezésében.

A részösszegek problémákat okozhatnak az eredmény exportálásakor, különösen akkor, ha a felhasználók módosítják a rekordsorozatot.

A részösszegek ellenőrzéséhez exportálni lehet az eredményt Microsoft Excel. Ha azt szeretné, hogy a Supply Chain Managementen belül ellenőrizze a részösszegeket, használja [Funkciókezelést](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) és engedélyezze az *Új rácsvezérlő* és a *Csoportosítás a rácsokban* funkciókat, amelyek sokkal rugalmasabban használhatók a csoportosítási oszlop részösszegeinak megjelenítéséhez. További információkért lásd az [Rácsfunkciók](/dynamics365/fin-ops-core/fin-ops/get-started/grid-capabilities.md) részt.

## <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>A készletérték-tárolási jelentés nem támogatja a főkönyvi fiók adatait

A főkönyvi kivonatot úgy futtathatja, hogy beolvassa a készletfiókok egyenlegét, és összehasonlítja a **Készletérték-tárolás** jelentéssel.
