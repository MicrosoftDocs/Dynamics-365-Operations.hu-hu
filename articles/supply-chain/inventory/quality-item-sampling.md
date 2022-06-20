---
title: Minőségkezelési cikkmintavétel
description: Ez a témakör a cikkmintavétel beállításának a beállítását ismerteti.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 644eae4fbd9f82027c1cb69efba00dc893f8fc66
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865150"
---
# <a name="quality-management-item-sampling"></a>Minőségkezelési cikkmintavétel

[!include [banner](../includes/banner.md)]

A cikkmintavétel a minőségi társítás részeként használatos. Meghatározza az aktuális fizikai készlet vizsgálandó mennyiségét. A mintavétel történhet rögzített mennyiség, százalékos érték vagy teljes azonosítótábla alapján.

## <a name="set-up-item-sampling"></a>Cikk-mintavétel beállítása

A cikkmintavétel beállításához kövesse az alábbi lépéseket.

1. Ugorjon a következőhöz: **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Cikkmintavétel**.
1. Válassza az **Új** lehetőséget.
1. Adjon meg egy értéket a **Cikkmintavétel** mezőben.
1. A **Leírás** mezőben adjon meg egy értéket.
1. Adjon meg egy számot az **Érték** mezőben. Ez az érték a szomszédos mezőben kiválasztott megadott mennyiségre vonatkozik.
1. A **Folyamat** szakaszban jelölje be a **Teljes zárolás** jelölőnégyzetet, ha a teszt sikertelensége esetén a teljes tétel- vagy rendeléssormennyiséget le kell tiltani. Ha a jelölőnégyzet nincs bejelölve, akkor ha a teszt sikertelen, csak a minőségi rendelés cikkeket tiltja le a rendszer.
1. Válassza a **Mentés** lehetőséget.
1. Zárja be a lapot.

> [!NOTE]
> A *Raktári folyamatok minőségkezelése* funkció további cikkmintavételi képességeket ad hozzá. Bevezeti a *Cikkmintaétel hatókörének* fogalmát, és lehetővé teszi egy teljes azonosítótábla meghatározását mennyiségi specifikációnak. Ha bekapcsolta ezt a funkciót, lásd: [Raktári folyamatok minőségkezelése](quality-management-for-warehouses-processes.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
