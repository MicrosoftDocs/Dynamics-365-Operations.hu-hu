---
title: Az utolsó lezárt munkasornak betárolásnak kell lennie
description: Az utolsó lezárt munkasornak betárolásnak kell lennie
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
ms.openlocfilehash: bbc5797df2b7465b36ec5ea546a67441626daeb1c72f82dfca4eb7db3503b713
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760274"
---
# <a name="the-last-closed-work-line-must-be-a-put"></a>Az utolsó lezárt munkasornak betárolásnak kell lennie

Hibakód: WAX1285

## <a name="symptoms"></a>Tünetek

A rendszer a következő hibaüzenetet jeleníti meg:

> Az utolsó lezárt munkasornak betárolásnak kell lennie.

## <a name="cause"></a>Ok

A munka a jelenlegi állapotában nem szakítható meg.

Az utolsó munkasor **Munkaállapot** mezőjének beállítása *Lezárt*, de a **Munkatípus** mező nincs beállítva *Betárolás* értékre.

## <a name="resolution"></a>Felbontás

A munka megszakításához kövesse az alábbi lépéseket.

1. Menjen a **Raktárkezelés \> Időszakos feladatok \> Tisztítás \> Munka megszakítása** menühöz.
1. A **Munkaazonosító** mezőben adja meg a megszakítani kívánt munka azonosítóját.
1. Válassza ki az **OK** lehetőséget.
1. Válassza az **Igen** lehetőséget a munka megszakításához.

További információ: [A kivétel kezelésére vonatkozó raktári munka visszavonása](../../warehousing/cancel-warehouse-work.md).
