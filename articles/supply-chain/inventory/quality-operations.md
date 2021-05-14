---
title: Műveletek szabálytalanságokhoz kapcsolódóan
description: Ez a témakör azt ismerteti, hogyan lehet létrehozni és használni a szabálytalanságokhoz kapcsolódó műveleteket.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestOperations, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6454a56323ea66369696dd6e3310a41b4eb9ee58
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956690"
---
# <a name="operations-for-nonconformances"></a>Műveletek szabálytalanságokhoz kapcsolódóan

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet létrehozni és használni a szabálytalanságokhoz kapcsolódó műveleteket.

A **Műveletek** lapot használhatja a jóváhagyott szabálytalanságokon elvégezhető műveletek osztályzásához. Amikor a szabálytalansághoz egy kapcsolódó műveletet rendel, részleteket adhat meg a kapcsolódó anyagról, például a munkaidőről és költségekről, amelyek a művelet végrehajtásához szükségesek. A rendszer ezen információ alapján számítja ki a művelet becsült költségét. A részletes adatok és a becsült költségek csak tájékoztató jellegűek. A minőséggel kapcsolatos műveletek nem olyan műveletek, mint a termelési útvonalban meghatározható műveletek.

> [!NOTE]
> Bár a szabálytalansághoz kapcsolódó műveletben nyomon követhetők a költségek, az idő és a cikkek, a beírható adatok csak tájékoztató jellegűek. Nem integrálódik automatikusan a főkönyvvel, a készlet főkönyvével vagy a **Munkaidő és jelenlét** modullal.

## <a name="examples-of-operations"></a>Példák a műveletekre

Egy gyártó cégnek dolgozik. Szabálytalanságot hoztak létre és jóváhagyták a minőségi teszten meg nem feleskedő cikkeknél. Létrehoztak egy korrekciót, amely azt jelzi, hogy a probléma a gép egy hibás csapágyával volt kapcsolatos. Az csapágy lecserélését több lépésben kell elvégezni, és a rendszer nyomon követi az egyes műveletek felelősségét. Például a következő lépésekre lehet szükség:

1. A gyártósor le van állítva, és a tisztítási rutint végzik.
1. A karbantartási személyzet lecseréli a csapágyat.
1. A minőségbiztosítást végző személyek megvizsgálják a gépet, mielőtt visszakapcsolnák.

Ebben a példában a következő műveleteket lehet létrehozni az elvégzendő munka megjelölése érdekében:

- A gyártósor leállítása.
- A gyártósor tisztítása.
- A gép rendszeres karbantartása.
- A gép megvizsgálása.

## <a name="create-an-operation"></a>Egy művelet létrehozása

1. Ugorjon a **Készletkezelés \> Beállítás \> Minőségkezelés \> Műveletek** pontra.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz. Ezután új sorhoz állítsa be a következő mezőket:

    - **Művelet** – Adja meg a művelet egyedi azonosítóját vagy nevét.
    - **Leírás** – Adja meg a művelet részletes leírását.
    - **Típus** – Ha a művelet csak egy bizonyos típusú rendeléshez kapcsolódó szabálytalanságokkal használható, válassza ki a rendelés típusát (*Beszerzési rendelés* vagy *Értékesítési rendelés*).

1. Zárja be a lapot.

## <a name="additional-resources"></a>További erőforrások

- [Minőségkezelés áttekintése](quality-management-processes.md)
- [A minőség- és a szabálytalanságkezelés engedélyezése](enable-quality-management.md)
- [Szabálytalanság létrehozása és feldolgozása](tasks/create-process-non-conformance.md)
- [A szabálytalanságok jóváhagyásáért felelős dolgozók](quality-responsible-workers.md)
- [A szabálytalanságok karanténzónái](quality-quarantine-zones.md)
- [A szabálytalanságok diagnosztikai típusai](quality-diagnostic-types.md)
- [Szabálytalanságok minőségi költségei](quality-charges.md)
- [A szabálytalanságok problématípusai](quality-operations.md)
- [Raktári folyamatok minőségkezelése](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
