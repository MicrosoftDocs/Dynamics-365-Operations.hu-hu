---
title: Hiba történik a beépített alaptervezési motor futtatásakor
description: Az elavult beépített főtervező motor futtatásakor hibaüzenetet kap.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: Dialog_ReqCalcScheduleItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c950292a4f43319d21a7deafdfb341b7bef15d8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294093"
---
# <a name="you-receive-an-error-when-running-the-built-in-master-planning-engine"></a>Hiba történik a beépített alaptervezési motor futtatásakor

Hibakód: ReqCalcScheduleItemTablePlanningOptimizationFitError

## <a name="symptoms"></a>Tünetek

Amikor az elavult beépített főtervező motor segítségével futtatja a főtervezést, a következő hibaüzenetet kapja:

> Ez a hibaüzenet akkor jelenik meg, ha a beépített alaptervezési motort a Tervezési optimalizálás által támogatott esetekhez használta. Most át kell telepítenie rendszerét a Tervezés optimalizálásra, mivel az aktuális beépített alaptervezés elavult. Ne feledje, hogy ennek az alaptervezésnek a futtatása sikeresen befejeződött. Abban az esetben, ha az áttelepítés erősen függ a függőben lévő szolgáltatásoktól, kérhető a beépített alaptervezési motor további használatának kivétele. Töltse ki a következő kérdőívet a kezdéshez, illetve a szükséges, kérelmezzen kivételt a Tervezési optimalizálásra való átállítás alól. [Tervezési optimalizálási áttelepítés és kivételi kérdőív](https://go.microsoft.com/fwlink/?linkid=2144962)

## <a name="cause"></a>Ok

Ha futtatja a tervezést, és nem használja a gyártásvezérlési funkciókat, fontolja meg a tervezési optimalizálási beállításra való áttelepítést. A beépített alaptervezési motor elavult. Ezért ha továbbra is azt szeretné, hogy hibaüzenet fogadása nélkül használja, kivételt kell alkalmaznia a Microsofttól.

## <a name="resolution"></a>Megoldás

Ha további tájékoztatást ad arról, hogyan lehet áttérni a tervezési optimalizálásra, vagy hogyan lehet kivételeket alkalmazni, hogy továbbra is használni tudja az elavult beépített tervezőmotort, akkor tekintse át az [Áttelepítés tervezési optimalizálásra alaptervezéshez](/dynamics365/supply-chain/master-planning/new-master-planning-engine) részt.
