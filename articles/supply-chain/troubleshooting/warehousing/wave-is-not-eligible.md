---
title: A hullám nem jogosult tisztításra
description: A hullám nem jogosult tisztításra
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWaveTable_WHSWaveProcessingDataCleanup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 99d76b6a90045be7630785769b11e43abaf4b789b1c4a134050b6ee396c71199
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778506"
---
# <a name="wave-isnt-eligible-for-cleanup"></a>A hullám nem jogosult tisztításra

Hibakód: WaveNotEligibleForCleanup

## <a name="symptoms"></a>Tünetek

A rendszer a következő hibaüzenetet jeleníti meg:

> A(z) %1 hullám nem törölhető.

A hullámadatok nem tisztíthatóak.  

## <a name="cause"></a>Ok

A hullám feldolgozása jelenleg folyamatban van, az alábbi feltételek egyikének megfelelően:

- Állítsa a **Hullám állapota** mező értékét erre: *Végrehajtás*.
- Ha a műveletpanel **Hullám lapján** a **Hullám** csoportban a **Kötegelt feladat** lehetőséget választja, az **Állapot** mező nincs beállítva *Befejezve*, *Hiba* vagy *Megszakítva* értékre. Emiatt jelenleg egy kötegelt feladat fut.

## <a name="resolution"></a>Felbontás

A műveletpanel **Hullám** lapján, a **Hullám** csoportban válassza a **Kötegelt feladatot**, majd hajtsa végre a következő lépések valamelyikét:

- Ha az **Állapot** mező *Végrehajtás* értékre van állítva: A Műveleti panelen a **Kötegelt feladat** lap **Kötegelt feladat** csoportjában válassza a **Feladatok megtekintése** lehetőséget. A **Kötegelt feladatok** lap frissítésével figyelemmel követheti a folyamat állapotát.
- Ha az **Állapot** mező nem *Végrehajtás* értékre van állítva: A Műveleti panelen a **Kötegelt feladat** lap **Funkciók** csoportjában válassza az **Állapot módosítása** lehetőséget. Az **Új állapot kiválasztása** mezőben válassza az *Várakozás* lehetőséget. Majd kattintson az **OK** lehetőségre.
