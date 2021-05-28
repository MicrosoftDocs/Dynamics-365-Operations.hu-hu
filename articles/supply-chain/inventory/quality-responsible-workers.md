---
title: A szabálytalanságok jóváhagyásáért felelős dolgozók
description: Ez a témakör leírja, hogyan kell konfigurálni a szabálytalanságok jóváhagyásáért felelős dolgozókat.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d3f647de2c188661c2c9c5f31e2642c3f8ca0b5
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021780"
---
# <a name="workers-responsible-for-approving-nonconformances"></a>A szabálytalanságok jóváhagyásáért felelős dolgozók

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan kell konfigurálni a szabálytalanságok jóváhagyásáért felelős dolgozókat.

A szabálytalanságokat jóvá kell hagyni, mielőtt a felhasználók elkezdhetnék megadni a részleteket, például a javításokat vagy a műveleteket. Ahhoz, hogy a felhasználók jóváhagyhassák vagy elutasíthassák a szabálytalanságokat, a felhasználói azonosítójukat (felhasználói rekordjukat) hozzá kell kapcsolni egy dolgozói rekordhoz. A minőségért felelős dolgozókat opcionálisan beállíthatja, majd egy dolgozó számára engedélyezheti, hogy egy másik dolgozó nevében jóváhagyja a munkát.

## <a name="enable-a-user-for-nonconformance-processing"></a>Engedélyezzen a szabálytalanságok feldolgozására egy felhasználót

Ahhoz, hogy egy falhasználó jóváhagyhasson vagy elutasíthasson a szabálytalanságokat, a felhasználói azonosítóját (felhasználói rekordját) hozzá kell kapcsolni egy dolgozói rekordhoz. Ezt követően automatikusan be lehet állítani a jóváhagyási mezőket, és az aktuális felhasználó automatikusan kitölthető az időnyilvántartáshoz. Mielőtt a felhasználó használhatná a dokumentummegjegyzéseket, aktiválnia kell a dokumentumkezelése a felhasználói beállításaiban.

1. Ugrás a **Rendszerfelügyelet \> Felhasználók \> Felhasználók** elemre.
1. Keresse meg és nyissa meg azt a felhasználót, akinek képesnek kell lennie szabálytalanságok jóváhagyására vagy elutasítására.
1. A **Személy** mezőt állítsa be az aktuális felhasználói rekordhoz kapcsolódó dolgozó nevére.
1. A műveleti ablaktáblán válassza ki a **Felhasználói beállítások** elemet.
1. Az aktuális felhasználói rekord **Beállítások** lapján, a **Beállítások** lapon állítsa a **Dokumentumkezelés engedélyezése** lehetőséget *Igen* beállításra.
1. Zárja be a lapokat.

## <a name="define-workers-that-are-responsible-for-quality"></a>Határozza meg a minőségért felelős dolgozókat

1. Ugorjon a következőhöz: **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Minőségért felelős dolgozók**.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. A **Dolgozó** mezőben válassza ki azt a dolgozót, aki a minőségi adatokat megadja.
4. A **Felelős dolgozó** mezőben válassza ki azt a dolgozót, aki helyett a kiválasztott dolgozó munkát ad meg. A szabálytalanságok létrehozásakor és frissítésekor a dolgozó alapértelmezés szerint meg lesz adva a **Dolgozó** mezőkben.

## <a name="additional-resources"></a>További erőforrások

- [Minőségkezelés áttekintése](quality-management-processes.md)
- [A minőség- és a szabálytalanságkezelés engedélyezése](enable-quality-management.md)
- [Minőségbiztosítási költségek](quality-charges.md)
- [A szabálytalanságok karanténzónái](quality-quarantine-zones.md)
- [A szabálytalanságok diagnosztikai típusai](quality-diagnostic-types.md)
- [Szabálytalanságok minőségi költségei](quality-charges.md)
- [Műveletek szabálytalanságokhoz kapcsolódóan](quality-operations.md)
- [Raktári folyamatok minőségkezelése](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
