---
title: Osztott időszakok az időszaki naplókban
description: Ez a cikk a Cseh Köztársaságban, Észt Köztársaságban, Lettországban, Litvániában, Lengyelországban és Oroszországban található jogi személyek időszakai közötti időszakokkal és ismétlődő naplókval kapcsolatban tartalmaz tájékoztatást.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: kfend
ms.custom: 261354
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 113b936aab15e9c8f28fc63f745780a76f6f3ab7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848483"
---
# <a name="split-periods-in-periodic-journals"></a>Osztott időszakok az időszaki naplókban

[!include [banner](../includes/banner.md)]

Az időszaki naplókat olykor ismétlődő naplónak is nevezik, mivel az összeg, a szöveg és más adatok a napló feladásakor minden alkalommal megismétlődnek. Napló létrehozásakor adja meg az ismétlődéshez tartozó időszakot (pl. nap vagy hónap). Azoknak az időszakoknak a számát is adja meg, amelyek szerint a napló fel lesz adva.

Tranzakciósorok többszöri beolvasásához és feladásához használja az **Időszaki naplók** oldalt. A Cseh Köztársaság, Észtország, Magyarország, Lettország, Litvánia, Lengyelország és Oroszország területén működő jogi személyek esetében az **Időszaki naplók** oldal az időszaki felosztás funkció révén bővítésre került. További tudnivalók: [Időszaki naplók feladása](../general-ledger/tasks/post-periodic-journals.md)

### <a name="example-split-for-periods-in-periodic-journals"></a>Példa: Időszaki felosztás időszaki naplókban

Egy biztosítótársaság egyéves kedvezményt ajánl a szervezetének, ha előre kifizeti a biztosítást. A kifizetést egy eszközszámlán adják fel például előre kifizetett biztosításként. A biztosítás havidíja ezután egész évben csökken egy olyan időszaki napló létrehozásával, amelyhez tartozik egy követelés az előre kifizetett biztosítási számlán, illetve egy tartozás a biztosítási költségszámlán. Ebben az esetben használhatja az időszaki felosztás funkciót. Kattintson az **Időszaki felosztás** gombra a műveletpanelen a **Időszaki** **naplósorok** oldalon, és adja meg a következő mezőket.


| Mező            | Leírás                                                                                                                                                                                             |
|-----------------------|---------------------------------------------------------------|
| **Kezdő dátum**        | Válassza ki az első időszakinapló-sorhoz tartozó dátumot.                                                                                                                                                        |
| **Időszakok száma** | Adja meg azon időszakok számát, amelyek alapján felosztja a naplósort. Ez az érték határozza meg, hány új tranzakció jön létre. A tranzakció összege egyenlően oszlik meg az új tranzakciók között. |
| **Egység**              | Válassza ki az időszakhoz tartozó mértékegységet.                                                                                                                                                                  |
| **Időszak intervalluma**   | Adja meg a feladási időszakok közötti időközt.                                                                                                                                                              |

Például negyedéves feladások létrehozásához írja a **4**-es számot az **Időszakok száma** mezőbe, válassza a **Hónapok** értéket az **Egység** mezőben, majd írja a **3**-as számot az **Időszak intervalluma** mezőbe. A rendszer négy naplósort hoz létre, egyet-egyet a megadott naplósor-összegek egynegyedéhez, 3 hónapos időszakonként. A főkönyvi naplóban is elérhető hasonló funkcionalitás. Főkönyvi napló sorainak megtekintésekor válassza az **Időszaknapló** &gt; **Napló mentése** elemet.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]