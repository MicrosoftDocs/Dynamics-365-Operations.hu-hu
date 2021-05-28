---
title: Minőségkezelési cikkmintavétel
description: Ez a témakör a cikkmintavételek beállítását ismerteti.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae8bfd329ca0d7c30adcd93a759ee6bea7b76278
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022228"
---
# <a name="quality-management-item-sampling"></a>Minőségkezelési cikkmintavétel

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
