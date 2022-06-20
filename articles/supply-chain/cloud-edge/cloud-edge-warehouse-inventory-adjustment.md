---
title: Raktárkészlet helyesbítése
description: Ez a cikk a raktári készletkorrekció-naplóról és a mérlegegységek használata esetén történő feldolgozásról nyújt tájékoztatást.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventoryAdjustmentJournal, InventJournalCount
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a4d892cd9e7f518c43df7197fc443b9a284e72b6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893555"
---
# <a name="warehouse-inventory-adjustment"></a>Raktárkészlet helyesbítése

[!include [banner](../includes/banner.md)]

A Raktárkészlet-korrekció funkció a felhő- és peremalapú skálázási egységek futtatásakor használatos a [gyártási munkaterhelések](cloud-edge-workload-manufacturing.md) és a [raktárkezelési munkaterhelések](cloud-edge-workload-warehousing.md) során.

Ha egy dolgozó a raktári alkalmazás segítségével végez készletkorrekciót a skálázási egység raktárkezelési munkaterhelése alapján, a tényleges aktuális készlet frissítését a **Raktárkészlet-korrekciós napló** kötegelt feladattal kell feldolgozni, amelyet a következő helyen futtathat és ütemezhet: **Raktárkezelés > Időszakos feladatok > Raktárkészlet-korrekciós napló**.

A raktári alkalmazás következő munkafolyamatai jelenleg a **Raktárkészlet-korrekciós naplót** használják a skálázási egység munkaterhelésein:

- Korrekció be/ki
- Ciklikus leltározás
- Azonosítótábla rakodása

Számos készlettranzakció jön létre a készletkorrekciós folyamat során, mivel a központ és a skálázási egységek telepítése osztoznak a készletrekordokon.

## <a name="inventory-adjustment-example"></a>Készletkorrekció - példa

Ebben a példában egy raktári dolgozó a raktári alkalmazást használta az aktuális készlet hozzáadásának regisztrálásakor.

Először a skálázási egység munkaterhelése létrehoz egy raktárkészlet-korrekciós tranzakciót a pozitív fizikai korrekcióhoz, amelyet ezután szinkronizál a központtal, és ez az aktuális készlet növekedését eredményezi a központon.

| Típus                                    | Skálázási egység | Irány | Központ |
|-----------------------------------------|------------|-----------|-----|
| Raktárkészlet helyesbítése          | +1         | ->        | +1  |

A központ ezután feldolgoz egy leltárnapló-feladást, amely az [üzenetfeldolgozó üzenetei](cloud-edge-message-processor-messages.md) révén érkezik meg. Ezzel frissíti a további aktuális készletet. A dupla aktuális készlet megakadályozása érdekében a központ létrehoz egy ellentranzakciót a folyamat részeként, és eltávolítja a raktárkészlet-korrekcióhoz kapcsolódó, korábban rögzített aktuális készletet.

| Típus                                    | Skálázási egység | Irány | Központ |
|-----------------------------------------|------------|-----------|-----|
| Leltár                                | +1         | <-        | +1  |
| Raktárkészlet-korrekció (ellenszámla) | -1         | <-        | -1  |

Miután a skálázási egység létrehozta a **Raktárkészlet-korrekciós naplót** a központban, mind a **Leltárnaplót** és az **Ellenszámlanaplót** is áttekintheti, amelyeket a központ a helyesbítési folyamat részeként hoz létre.

A Supply Chain Managementben ezeket a naplóbejegyzéseket és tranzakciókat a következő lépésekkel lehet áttekintheti:

1. Jelentkezzen be a skálázási egységbe.
1. Lépjen a **Raktárkezelés \> Ismétlődő feladatok \> Raktárkészlet-korrekciós napló** menüpontra.
1. A **Raktárkészlet-korrekciós napló** oldalon keresse meg és nyissa meg azt a naplót, amely rögzítette az aktuális készlet változását. A **Naplósorok** szakasz az e naplóval rögzített minden egyes módosítást megjeleníti.
1. Jelentkezzen be a központba.
1. Lépjen a **Raktárkezelés \> Ismétlődő feladatok \> Raktárkészlet-korrekciós napló** menüpontra.
1. A **Raktárkészlet-korrekciós napló** oldalon ekkor látnia kell ugyanazt a naplót, ha szinkronizálta a központot és a skálázási egységet.
1. Nyissa meg a naplót. Ha az [üzenetfeldolgozó üzeneteit](cloud-edge-message-processor-messages.md) feldolgozták, a fejlécben a **Leltárnaplóra** és az **Ellenszámlanaplóra** mutató hivatkozások jelennek meg.
    - A **Leltárnaplónak** a naplósorokkal azonos dimenzióértékeket kell mutatnia.
    - Az **Ellenszámlanaplónak** az ellenszámlát kell megjelenítenie, amely eltávolítja a dupla készletkorrekciót.
    > [!NOTE]
    > Amikor minden szinkronizálás és feldolgozás befejeződött, a **Leltárnapló** és az **Ellenszámlanapló** szinkronizálva lesz a skálázási egységgel. Ezek a **Raktárkészlet-korrekciós napló** megfelelő lapján is megtekinthetők.
