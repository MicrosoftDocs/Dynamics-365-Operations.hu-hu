---
title: Késleltetett adó számításának engedélyezése a naplón
description: Ez a témakör azt mutatja be, hogyan lehet a **Késleltetett adó számításának engedélyezése a naplón** funkciót az adószámítás hatékonyságának növelésére használni, ha a naplósorok mennyisége hatalmas.
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
ms.author: vstehman
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 5a8ae30a007d3e2b8b7a9bc9eb7786f6e58246d0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178058"
---
# <a name="enable-delayed-tax-calculation-on-journal"></a>Késleltetett adó számításának engedélyezése a naplón
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör azt mutatja be, hogyan lehet a **Késleltetett adó számításának engedélyezése a naplón** funkciót az adószámítás hatékonyságának növelésére használni, ha a naplósorok mennyisége hatalmas.

A napló jelenlegi ÁFA-számítási viselkedése valós idejű, akkor indul el, amikor a felhasználó az adóval kapcsolatos mezőket, például a áfacsoportok vagy a cikkáfacsoport csoportját frissíti. A naplósorban szereplő bármilyen frissítés újraszámítja az összes naplósorban szereplő adóösszeg értékét. Segít a felhasználó számára a valós idejű kiszámított adó összegének megjelenítésében, de a teljesítményproblémákat is okozhat, ha a naplósorok száma magas.

Ez a funkció lehetőséget ad az adószámítás késleltetésére a teljesítmény-probléma megoldása érdekében. Ha ez a funkció be van kapcsolva, akkor az adó összegét csak akkor számítja ki a rendszer, amikor a felhasználó az „ÁFA” parancsra kattint vagy feladja a naplót.

A felhasználó a paramétereket három szinten kapcsolja be/ki:
- Jogi személy szerint
- Napló neve szerint
- Napló fejléce szerint

A rendszer a napló fejlécében szereplő paraméterértékét használja véglegesként. A napló fejlécének paraméter-értéke a napló nevéből származik. A napló nevének paraméter-értéke a főkönyvi paraméterből lesz származtatva a naplónév létrehozásakor.

A „tényleges áfaösszeg” és a „számított áfaösszeg" mező a naplóban elrejtésre kerül, ha a paraméter be van kapcsolva. A cél nem tévesztendő össze a felhasználóval, mert a két mező értéke mindig 0 lesz, mielőtt a felhasználó elindítja az adószámítást.

## <a name="enable-delayed-tax-calculation-by-legal-entity"></a>A késleltetett adószámítás engedélyezése jogi személy szerint

1. Ugorjon a **Főkönyv > Főkönyv beállítás > Főkönyv paraméterei** pontra.
2. Kattintson az **Áfa** fülre.
3. Az **Általános** gyorslap alatt megkeresheti a **Késleltetett adószámítás** paramétert, hogy be- vagy kikapcsolja azt.

![](media/delayed-tax-calculation-gl.png)



## <a name="enable-delayed-tax-calculation-by-journal-name"></a>Késleltetett adószámítás engedélyezése a naplónév szerint

1. Ugorjon a **Főkönyv > Naplóbeállítások > Naplónevek** pontra.
2. Az **Általános** gyorslap alatt megkeresheti a **Késleltetett adószámítás** paramétert, hogy be- vagy kikapcsolja azt.

![](media/delayed-tax-calculation-journal-name.png)

## <a name="enable-delayed-tax-calculation-by-journal"></a>Késleltetett adó számításának engedélyezése napló szerint

1. Ugorjon a **Főkönyv > Naplóbejegyzések > Általános naplók** pontra.
2. Kattintson az **Új** elemre.
3. Válasszon egy naplónevet.
4. Kattintson a **Beállítások** elemre.
5. Keresse meg a **Késleltetett adószámítás** paramétert, hogy be- vagy kikapcsolja azt.

![](media/delayed-tax-calculation-journal-header.png)
