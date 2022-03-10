---
title: A szabálytalanságok problématípusai
description: Ez a témakör azt ismerteti, hogyan lehet létrehozni és használni a szabálytalanságokhoz kapcsolódó problématípusokat.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventProblemType, InventProblemTypeSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26705dd12f478f4ca6046c7265d4ae3cb1d08c69
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568807"
---
# <a name="problem-types-for-nonconformances"></a>A szabálytalanságok problématípusai

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet létrehozni és használni a szabálytalanságokhoz kapcsolódó problématípusokat.

A **Problématípusok** oldalon határozhatja meg a különböző szabálytalanságtípusok esetében esetlegesen felmerülő minőségproblémák osztályozását. Minden létrehozott problématípushoz meg kell adnia, hogy a problématípus milyen típusú szabálytalanságokkal használható. A következő szabálytalanságtípusokat állíthatja be:

- **Belső** – Az ilyen típusú szabálytalanságok az aktuális készlettel (például minőségi rendelések vagy karanténrendelések) kapcsolatosak.
- **Vevő** – az ilyen típusú szabálytalanságok értékesítési rendelésekhez kapcsolódnak.
- **Szállító** – az ilyen típusú szabálytalanságok beszerzési rendelésekhez kapcsolódnak.
- **Szervizkérelem** – az ilyen típusú szabálytalanságok a szervizrendelésekhez kapcsolódnak.
- **Termelés** – Az ilyen típusú szabálytalanságok a kötegelt rendelésekhez vagy termelési rendelésekhez kapcsolódnak.
- **Társtermék gyártása** – Az ilyen típusú szabálytalanságok a kötegelt rendelésekhez vagy társtermékekhez kapcsolódnak.

Új problématípus létrehozásakor a Műveleti panelen válassza ki a **Szabálytalanságtípusok** lehetőséget a problématípushoz engedélyezett egy vagy több szabálytalanságtípus listájának létrehozásához. Például egy hibás kódhoz kapcsolódó problématípus minden szabálytalanságtípusra vonatkozhat. A vevői panaszokkal kapcsolatos problématípus azonban csak a **Vevő** és **Szervizkérelem** szabálytalanságtípusokra vonatkozhat.

## <a name="examples-of-problem-types"></a>Néhány példa a problématípusokra

Az alábbiakban néhány példa látható az olyan problématípusokra, amelyek a különböző szabálytalanságtípusokhoz használhatók:

- **Vevő**: Egy vevő panaszt nyújtott be, a vevő visszaküldött egy terméket, vagy nem teljesültek a minőségi specifikációk.
- **Szállító:** A termék sérült, vagy nem teljesültek a minőségi specifikációk, vagy nem megfelelő termék érkezett.
- **Szervizkérelem**: Nem teljesültek a minőségi specifikációk, egy vevő reklamációt nyújtott be, vagy a gép karbantartást igényel.
- **Termelés:** Nem teljesültek a minőségi specifikációk, a gépkarbantartásra van szükség, vagy a termék megsérült.
- **Társtermék gyártása:** Nem teljesültek a minőségi specifikációk, a gépkarbantartásra van szükség, vagy a termék megsérült.

## <a name="create-a-problem-type-and-assign-it-to-nonconformance-types"></a>Problématípus létrehozása és hozzárendelése szabálytalanságtípusokhoz

1. Ugorjon a **Készletgazdálkodás \> Beállítás \> Minőségkezelés \> Problématípusok** pontra.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz. Ezután új sorhoz állítsa be a következő mezőket:

    - **Problématípus** – A problématípus egyedi azonosítójának vagy nevének megadása.
    - **Leírás** – Adja meg a problématípus részletes leírását.

1. Amíg az új sor még ki van választva, válassza ki a **Szabálytalanságtípusokat** a műveleti panelen.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz. Ezután az új sorhoz állítsa a **Szabálytalanságtípus** mezőt a problématípus számára engedélyezni kívánt szabálytalanságtípusra.
1. Ismételje meg az előző lépést minden további olyan szabálytalanságtípussal, amelyhez engedélyezni szeretné a problématípust.
1. Zárja be a lapokat.

## <a name="additional-resources"></a>További erőforrások

- [Minőségkezelés áttekintése](quality-management-processes.md)
- [A minőség- és a szabálytalanságkezelés engedélyezése](enable-quality-management.md)
- [A szabálytalanságok jóváhagyásáért felelős dolgozók](quality-responsible-workers.md)
- [A szabálytalanságok karanténzónái](quality-quarantine-zones.md)
- [A szabálytalanságok diagnosztikai típusai](quality-diagnostic-types.md)
- [Szabálytalanságok minőségi költségei](quality-charges.md)
- [Műveletek szabálytalanságokhoz kapcsolódóan](quality-operations.md)
- [Raktári folyamatok minőségkezelése](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
