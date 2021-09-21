---
title: A tranzakciók feladhatók a felfüggesztett főkönyvi számlára
description: Ha egy termékbevételezés érvénytelenítve van, a rendszer lehetővé teszi a tranzakciók feladását a felfüggesztett főkönyvi számlákra, még akkor is, ha a főszámlákat felfüggesztették
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
ms.openlocfilehash: 20df0ee4107ad62bec0dd9a683660fe2375a3dd1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476600"
---
# <a name="transactions-can-be-posted-to-a-suspended-ledger-account"></a>A tranzakciók feladhatók a felfüggesztett főkönyvi számlára

## <a name="symptoms"></a>Tünetek

Ha egy termékbevételezés érvénytelenítve van, a rendszer lehetővé teszi a tranzakciók feladását a felfüggesztett főkönyvi számlákra, még akkor is, ha a fő számlákat felfüggesztették.

## <a name="reproduce-the-issue"></a>A hiba reprodukálása

A következő eljárás bemutatja a hiba reprodukálásának egyik módját.

1. A **Kötelezettségek paraméterei** lap **Általános** lapján győződjön meg arról, hogy a **Termékbevételezés feladása a főkönyvben** beállítás *Igen* értékre van állítva.
1. Hozzon létre egy beszerzési rendelést, és adjon hozzá egy *1000* mennyiséget tartalmazó rendelési sort a termékhez.
1. Erősítse meg a beszerzési rendelést.
1. Adja fel a termékbevételezést, és ellenőrizze a bizonylatokat.
1. Függessze fel a kapcsolódó fő számlákat: *200140* és *140200*.
1. Vonja vissza feladott termékbevételezést.
1. Figyelje meg, hogy a tranzakciók feladhatók a felfüggesztett főkönyvi számlákra.

## <a name="resolution"></a>Megoldás

A tranzakciókat fel lehet adni a felfüggesztett főkönyvi számlákra, ha a termékbevételezéseket érvénytelenítik, mert ez a viselkedés lehetővé teszi a megfelelő feladásokat.
