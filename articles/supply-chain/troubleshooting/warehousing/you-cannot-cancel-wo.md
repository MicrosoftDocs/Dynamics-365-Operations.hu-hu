---
title: Felhasználóhoz rendelt munkát nem lehet megszakítani
description: Felhasználóhoz rendelt munkát nem lehet megszakítani
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e5f6912cfb1d5be8e46b7989856af99f8a611c11
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924401"
---
# <a name="you-cant-cancel-work-that-is-on-a-user"></a>Felhasználóhoz rendelt munkát nem lehet megszakítani

Hibakód: WAX708

## <a name="symptoms"></a>Tünetek

A rendszer a következő hibaüzenetet jeleníti meg:

> Felhasználóhoz rendelt munkát nem lehet érvényteleníteni.

## <a name="cause"></a>Ok

A munka zárolva van a felhasználó által, ezért nem lehet megszakítani. Ennek megerősítéshez nyissa meg a munkaazonosítót, majd nyissa meg az **Általános** lapot. Ha a munka zárolva van, a **Munka állapota** mező *Folyamatban van* értéket kap, a **Zárolta** mezőben pedig egy felhasználói azonosító látható.

## <a name="resolution"></a>Felbontás

A munka megszakításához kövesse az alábbi lépéseket.

1. Menjen a **Raktárkezelés \> Időszakos feladatok \> Tisztítás \> Munka megszakítása** menühöz.
1. A **Munkaazonosító** mezőben adja meg a megszakítani kívánt munka azonosítóját.
1. Válassza ki az **OK** lehetőséget.
1. Válassza az **Igen** lehetőséget a munka megszakításához.

További információ: [A kivétel kezelésére vonatkozó raktári munka visszavonása](../../warehousing/cancel-warehouse-work.md).
