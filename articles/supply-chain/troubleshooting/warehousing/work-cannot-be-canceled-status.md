---
title: A munka nem vonható vissza az állapota miatt
description: A munka nem vonható vissza az állapota miatt
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
ms.openlocfilehash: f983501b490c5516525b4d5904603ed62e8799f9e6124e5672b36a12804ecb0a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755978"
---
# <a name="work-cant-be-canceled-because-of-its-status"></a>A munka nem vonható vissza az állapota miatt

Hibakód: WAX2190

## <a name="symptoms"></a>Tünetek

A rendszer a következő hibaüzenetet jeleníti meg:

> A(z) %1 munka nem vonható vissza, mivel az állapota %2.

## <a name="cause"></a>Ok

A munka a jelenlegi állapotában nem szakítható meg.

A munka fejléce vagy munkasorai nem a munka várt **Munkaállapot** értékkel rendelkeznek. A munkafejléc **Munka állapota** mezője nincs beállítva *Nyitott* vagy *Folyamatban* állapotúra.

## <a name="resolution"></a>Felbontás

A munka megszakításához kövesse az alábbi lépéseket.

1. Menjen a **Raktárkezelés \> Időszakos feladatok \> Tisztítás \> Munka megszakítása** menühöz.
1. A **Munkaazonosító** mezőben adja meg a megszakítani kívánt munka azonosítóját.
1. Válassza ki az **OK** lehetőséget.
1. Válassza az **Igen** lehetőséget a munka megszakításához.

További információ: [A kivétel kezelésére vonatkozó raktári munka visszavonása](../../warehousing/cancel-warehouse-work.md).
