---
title: Nem található munka a fürthöz a profil konfigurálása után
description: Ha fürtprofilt konfigurál, akkor egy hibaüzenet jelenhet meg arról, hogy nem található elég munka. Szerkessze a profilt, és állítsa a Pozíciók aktiválása beállítást Nem értéke.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 139fd72e571c8ef83af2fd0e497cf334b6ef0ea4
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476518"
---
# <a name="not-enough-work-found-for-cluster-when-using-system-directed-cluster-picking"></a>Nincs elég munka a fürthöz rendszer által irányított fürt kitárolása esetén

## <a name="symptoms"></a>Tünetek

A *Rendszer által irányított fürtkitárolás* folyamat használatakor, ha olyan fürtprofilt állít be, amelyben például 10 pozíció tárolható ki, a folyamat a tervek szerint működik, ha elegendő munka áll rendelkezésre a 10 pozíció kitárolásához. Ha azonban csak nyolc kitárolni való beosztás van, akkor a következő hibaüzenet jelenik meg:

> Nem található elég munka a fürthöz.

## <a name="resolution"></a>Megoldás

A probléma megoldásához szerkesztse a fürtprofilt, és állítsa a **Pozíciók aktiválása** lehetőséget *Nem* értékre.
