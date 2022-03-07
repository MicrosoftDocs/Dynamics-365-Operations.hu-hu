---
title: Létrehoz egy vállalatközi értékesítési rendelést egy külső vevő számára
description: Ez a témakör bemutatja, hogyan hozhat létre és számlázhat egy vállalatközi értékesítési rendelést egy külső vevő számára
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 72273a125da2e6c4a2fc16b449cd5077f3d767df
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548303"
---
# <a name="create-and-invoice-an-intercompany-sales-order-for-an-external-customer"></a>Létrehoz egy vállalatközi értékesítési rendelést egy külső vevő számára

[!include [banner](../../includes/banner.md)]

Vállalatközi kereskedelem használhatja a értékesítés a termék egy jogi személy egy másik jogi személyhez, amely az adott szervezeten belül.

Eredeti értékesítési rendelés létrehozása során lehetőség van a vállalatközi szállítónak benyújtandó vállalatközi beszerzési rendelés automatikus létrehozására. Ez automatikusan létrehoz egy vállalatközi értékesítési rendelést a vállalatközi szállító jogi személy.

A következő ábrán a tranzakciók a folyamat során létrehoz egy külső vevő számára egy értékesítési rendelést, de ez a termék a szervezeten belüli egy másik jogi személyhez kell rendelni ahhoz a termék a vevőnek szállítsa. Ebben az esetben egy vállalatközi beszerzési rendelés jön létre a jogi személy felel meg a szállítói számlára. A jogi személyt jelenti a vevői számlához más jogi személy, a vállalatközi értékesítési rendelés jön létre. Egy vállalatközi beszerzési rendelés számlájának feladásakor, ha az eredeti értékesítési rendelés egy közvetlen kiszállítás, automatikusan az eredeti értékesítési rendelésről szóló számlát adja fel.

![Vállalatközi külső értékesítési folyamat](media/intercompanyexternalsalesprocess.png)

Ha közvetlen kiszállítást használ, és a **Szállítólevél** beállítást választja a **Számla feladása** oldal **Mennység** mezőjében, a vállalatközi beszerzési számla a korábban feladott vállalatközi beszerzési rendelési csomagjegyzéken alapul.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt hozzálátna, győződjön meg róla, hogy a következő előfeltételek teljesülnek-e automatikusan adja fel, és a vállalatközi számlák nyomtatása.

1. Lépjen az **Értékesítés és marketing \> Vevők \> Összes vevő** menüpontba.
1. A Műveleti ablaktábla **Általános** lapján válassza a **Vállalatközi** menüpontot.
1. Ugrás a **Beszerzés és forrás \> Beszállítók \> Minden szállító** pontra.
1. A Műveleti ablaktábla **Általános** lapján válassza a **Vállalatközi** menüpontot.
1. A **Vállalatközi beszerzési rendelés (közvetlen kiszállítás)** mezőcsoportban **Beszerzési rendelés irányelveinek** területén a szállító vagy a vevő **Vállalatközi** lapján jelölje be a **Számla automatikus feladása** jelölőnégyzetet.
1. A **Beszerzési rendelések irányelvei** területen az **Eredeti értékesítési rendelés (közvetlen kiszállítás)** mezőcsoportban jelölje be a **Számla automatikus feladása** jelölőnégyzetet. Jelölje be ezt a jelölőnégyzetet, ha azt szeretné, hogy a rendszer automatikusan nyomtassa a vállalatközi szállítói számla feladásakor az eredeti értékesítési rendelés számlájának.

> [!NOTE]
> A számla nyomtatási beállítások határozzák meg a beállítások a modul, a bizonylat vagy a tranzakciót a **Nyomtatáskezelés beállítása** oldalon.

## <a name="create-an-original-sales-order-for-an-external-customer"></a>Létrehoz egy eredeti értékesítési rendelést egy külső vevő számára

Hajtsa végre ezeket a lépéseket a következő jogi személynél A. Ezzel az eljárással felel meg az 1, az ábrán látható jelölőnégyzetet.

1. Ugrás a **Kinnlevőségek \> Értékesítési rendelések \> Minden értékesítési rendelésre**.
1. Az **Összes értékesítési rendelés** listaoldalon hozza létre az eredeti értékesítési rendelést. A program a vevő adatait automatikusan átmásolja az értékesítési rendelésbe.
1. A Művelet panel **Értékesítési rendelés** oldalán válassza a **Fejlécnézet** menüpontot.
1. A **Vállalatközi beállítások** gyorslapon jelölje be a **Vállalatközi rendelések automatikus létrehozása** jelölőnégyzetet.
1. Ha azt szeretné, hogy a vállalatközi szállító közvetlenül a külső vevőnek szállítsa a cikket, jelölje be a **Közvetlen kiszállítás** mezőt.
1. Amikor befejezte az értékesítési rendelés bevitelét, zárja be az **Értékesítési rendelés** oldalt.

Automatikusan létrehoz egy vállalatközi beszerzési rendelést a vállalatközi szállítóhoz társított minden cikkről, majd készít egy vállalatközi értékesítési rendelést. Egy tájékoztató üzenet tájékoztat arról, hogy egy vállalatközi beszerzési rendelés és egy vállalatközi értékesítési rendelés készült. Az üzenet az ezekre a rendelésekre hivatkozásokat is tartalmaz. Ha egy cikk nem található, egy piros figyelmeztetés jelenik meg, ami azt jelenti, hogy a rendelés-létrehozási folyamat nem fejeződött be.

> [!NOTE]
> Ha több rendelést ad le különböző vállalatoknak, és az egyik vállalatnál nem találhatók meg a cikkek, akkor a program leállítja a rendelések létrehozását, még azon vállalatok esetén is, amelyek teljesíteni tudnák a rendelést.

## <a name="invoice-an-intercompany-sales-order"></a>Vállalatközi értékesítési rendelés számlázása

A vállalatközi értékesítési rendelés számlájának számlázása esetén a program automatikusan feladja a megfelelő vállalatközi beszerzési rendelést, ha az egy közvetlen kiszállítás. Ekkor, ha az eredeti értékesítési rendelés közvetlen kiszállítású rendelés, az eredeti értékesítési rendelés automatikusan ki van számlázva.

Hajtsa végre ezeket a lépéseket a B jogi személynél. Ezzel az eljárással felel meg az 2. az ábrán látható jelölőnégyzetet.

1. Ugrás a **Kinnlevőségek \> Értékesítési rendelések \> Minden értékesítési rendelésre**.
1. Az **Összes értékesítési rendelés** listaoldalon, válassza a vállalatközi értékesítési rendelést.
1. A Műveleti ablaktáblán válassza a **Számla** lapot, majd válassza a **Számla** menüpontot.
1. Jelölje be az **Feladás** jelölőnégyzetet.
1. Válassza ki a termelési rendelést, majd válassza az **OK** lehetőséget.

A vevői számlához tartozó vállalatközi értékesítési rendelést a program automatikusan feladja a B jogi személynél. A vállalatközi szállítói számla akkor az automatikusan létrejön az A jogi személynél. Ha az eredeti értékesítési rendelés közvetlen kiszállításként van beállítva, a vevői számla jön létre az eredeti értékesítési rendelés a következő jogi személynél A.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
