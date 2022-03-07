---
title: A fürtprofil nem található
description: A bejövő raktári műveleteknél hibaüzenet jelenik meg arról, hogy a fürtprofil nem található. Ellenőrizze, hogy a fürtprofilok helyesen vannak-e beállítva.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bbf9c5bc70c8f3ba1fa26db425249e65e82c0518
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476596"
---
# <a name="cluster-profile-cant-be-found"></a>A fürtprofil nem található

## <a name="symptoms"></a>Tünetek

A bejövő raktári műveletekkel kapcsolatos munka során a következő hibaüzenet jelenhet meg:

> "Megtörtént a(z) %1 minőségi rendelés generálása. A fürtprofil nem található. Ellenőrizze a konfigurációt."

Ez a hibaüzenet egy olyan fogadási folyamathoz kapcsolódik, ahol a minőségirányítás (QMS) be van kapcsolva. A környezet konfigurációjától függően a hibaüzenetet generáló tranzakció további részletei segíthetnek a probléma megoldásában.

## <a name="resolution"></a>Megoldás

Először tekintse át a fürtkitárolási beállítást, és győződjön meg arról, hogy a fürtprofilok megfelelően vannak beállítva. A fürtprofilok beállítása nem használható mobileszköz-menüelem fürtkitároláshoz. A környezettől függően előfordulhat, hogy más kapcsolódó konfigurációkat is át kell tekintenie.
