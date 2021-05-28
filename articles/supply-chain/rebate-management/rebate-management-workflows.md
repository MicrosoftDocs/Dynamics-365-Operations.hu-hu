---
title: Visszatérítés-kezelési ügylet munkafolyamatai
description: Ez a témakör bemutatja, hogyan lehet beállítani visszatérítés-kezelési ügylet munkafolyamatát az ügyletek jóváhagyásához és aktiválásához.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: ee342de6d069131e230120c5d65aef58da8e632a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020386"
---
# <a name="rebate-management-deal-workflows"></a>Visszatérítés-kezelési ügylet munkafolyamatai

[!include [banner](../includes/banner.md)]

Visszatérítési ügyletek jóváhagyásához a visszatérítés-kezelés a többi Finance and Operations-alkalmazással azonos munkafolyamat-platformot használja. Minden munkafolyamathoz két feladatfolyamat van társítva:

- A munkafolyamat egyik eleme aktiválja az ügyletet, így a felhasználó vagy munkafolyamat jóváhagyhatja a tranzakciókat.
- A munkafolyamat egyik eleme jóváhagyja az ügyletet.

Visszatérítési ügylet használata előtt aktívnak kell lennie a **Visszatérítés-kezelés** modulban. Az ügylet aktiválásához előbb létre kell hoznia és be kell állítania egy *Visszatérítés-kezelési ügylet munkafolyamatát*.

Miután aktiváltak egy munkafolyamatot a Visszatérítés-kezeléshez, a felhasználók manuálisan nem hagyhatnak jóvá ügyleteket. A munkafolyamatot mindig használni kell.

## <a name="create-and-manage-rebate-management-deal-workflows"></a>Visszatérítés-kezelési ügyletek munkafolyamatainak létrehozása és kezelése

A Visszatérítés-kezelési ügylet munkafolyamataival való munkához lépjen a **Visszatérítés-kezelés \> Beállítás \> Visszatérítés-kezelési munkafolyamatok** lehetőségre. A munkafolyamatokat szükség szerint megtekintheti, létrehozhatja és frissítheti. Egyszerre csak egy ilyen típusú munkafolyamat lehet aktív. A munkafolyamatokkal, a **Visszatérítés-kezelési munkafolyamatok** oldalon végzett munkával és a munkafolyamatok létrehozásával kapcsolatos további információkért tekintse meg a [Munkafolyamati rendszer áttekintése](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) részt és a kapcsolódó témaköröket.

## <a name="use-a-workflow-to-activate-a-deal"></a>Munkafolyamat használata ügylet aktiválásához

Ha egy ügyletet egy munkafolyamaton keresztül szeretne aktiválni, nyissa meg az ügyletet (például az **Összes visszatérítés-kezelési ügylet** oldalon). Majd a műveleti ablaktáblán válassza ki a **Munkafolyamat \> Elküldés** elemet. Az új ügylet munkafolyamaton keresztüli feldolgozása és jóváhagyása után aktív lesz, és használatra kész.

Az ügylet aktiválása után a beállítása nem változtatható meg. Ha módosítania kell egy aktív ügyletet, inaktiválnia kell, majd létre kell hoznia egy új ügyletet. Ha az új ügylet hasonlít a régi ügyletre, akkor a régi ügylet másolásával is létrehozhatja.
