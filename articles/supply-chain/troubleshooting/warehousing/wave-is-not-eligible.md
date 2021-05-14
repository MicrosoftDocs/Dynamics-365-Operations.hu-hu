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
ms.openlocfilehash: 3e5142cf40a6c0d308e8e952bbe17e85b498826d
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924327"
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
