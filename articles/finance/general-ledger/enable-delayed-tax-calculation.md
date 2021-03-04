---
title: Késleltetett adószámítás engedélyezése a naplókban
description: Ez a témakör azt mutatja be, hogyan lehet a Késleltetett adó számításának engedélyezése funkciót a számítási teljesítmény növelésére használni, ha a naplósorok mennyisége nagyon nagy.
author: ericwang
manager: Ann Beebe
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: d4ce0343ac766b30d532be0866a381dc520fd462
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444080"
---
# <a name="enable-delayed-tax-calculation-on-journals"></a>Késleltetett adószámítás engedélyezése a naplókban
[!include [banner](../includes/banner.md)]


Ez a témakör azt mutatja be, hogyan lehet késleltetni az áfa számítását a naplókon. Ez a lehetőség segít az adószámítás hatékonyságának javításában, ha sok naplósor van.

Alapértelmezés szerint a rendszer a naplósorokban szereplő áfaösszegeket akkor számítja ki, amikor az adóval kapcsolatos mezőket frissítették. Ezek a mezők tartalmazzák az áfacsoportok és a cikkáfacsoportok mezőit. A naplósor frissítésével az összes naplósor esetében újra lesznek számítva az adózási összegek. Annak ellenére, hogy ez a viselkedés segít a felhasználó számára a valós időben számított adóknál, hatással lehet a teljesítményre is, ha a naplósorok száma nagyon nagy.

A Késleltetett adószámítási funkció lehetővé teszi az adószámítás elhalasztását a naplókon, és így segít a teljesítménnyel kapcsolatos problémák megoldásában. Ha ez a funkció be van kapcsolva, akkor az adó összegeket csak akkor számítja ki a rendszer, amikor a felhasználó az **Áfa** parancsra kattint vagy feladja a naplót.

A áfa kiszámítását három szinten teheti meg:

- Jogi személy
- Napló neve
- Napló fejléce

A rendszer prioritást ad a naplófejléc beállításának. Alapértelmezés szerint ez a beállítás a napló nevéből származik. Alapértelmezés szerint a naplónév beállítását a rendszer a **Főkönyvi paraméterek** lap beállításából veszi, amikor a napló neve létrejön. A következő szakaszok azt mutatják be, hogyan lehet bekapcsolni az adó késleletett számítását a jogi személyek, a naplónevek és a naplófejlécek esetében.

## <a name="turn-on-delayed-tax-calculation-at-the-legal-entity-level"></a>A késleltetett adószámítás bekapcsolása a jogi személy szintjén

1. Menjen a **Főkönyv \> Főkönyv beállítás \> Főkönyv paraméterei** pontra.
2. Az **Áfa** lapon, az **Általános** gyorslapon állítsa a **Késleltetett adószámítás** beállítást **Igen** értékre.

![Főkönyvi paraméterek képe](media/delayed-tax-calculation-gl.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-name-level"></a>A késleltetett adószámítás bekapcsolása a naplónév szintjén

1. Menjen a **Főkönyv \> Naplóbeállítások \> Naplónevek** pontra.
2. Az **Általános** gyorslapon az **Áfa** szakaszban állítsa a **Késleltetett adószámítás** beállítást **Igen** értékre.

![Naplónevek képe](media/delayed-tax-calculation-journal-name.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-header-level"></a>A késleltetett adószámítás bekapcsolása a naplófejléc szintjén

1. Válassza a **Főkönyv \> Naplóbejegyzések \> Általános naplók** lehetőséget.
2. Válassza az **Új** lehetőséget.
3. Válasszon egy naplónevet.
4. A **Beállítás** lapon adja meg a **Késleltetett adószámítás** beállítását **Igen** értékre.

![Általános naplólap képe](media/delayed-tax-calculation-journal-header.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]