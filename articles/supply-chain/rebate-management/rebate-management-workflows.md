---
title: Visszatérítés-kezelési ügylet munkafolyamatai
description: Ez a cikk bemutatja, hogyan lehet beállítani visszatérítéskezelési ügyleti munkafolyamatokat az ügyletek jóváhagyásához és aktiválásához.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2b1611ff7877efc4a2f98b8f84a1ef91971902ab
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869517"
---
# <a name="rebate-management-deal-workflows"></a>Visszatérítés-kezelési ügylet munkafolyamatai

[!include [banner](../includes/banner.md)]

Visszatérítési ügyletek jóváhagyásához a visszatérítéskezelés ugyanazt a munkafolyamat-platformot használja, mint a többi Pénzügyi és Művelet-alkalmazás. Minden munkafolyamathoz két feladatfolyamat van társítva:

- A munkafolyamat egyik eleme jóváhagyja az ügyletet.
- A munkafolyamat egyik eleme aktiválja az ügyletet, így a felhasználó vagy munkafolyamat jóváhagyhatja a tranzakciókat.

Visszatérítési ügylet használata előtt aktívnak kell lennie a **Visszatérítés-kezelés** modulban. Az ügylet aktiválásához előbb létre kell hoznia és be kell állítania egy *Visszatérítés-kezelési ügylet munkafolyamatát*.

A felhasználók nem hagyhatják jóvá manuálisan az ajánlatokat. Mindig a munkafolyamatot kell használni.

## <a name="create-and-manage-rebate-management-deal-workflows"></a>Visszatérítés-kezelési ügyletek munkafolyamatainak létrehozása és kezelése

A Visszatérítés-kezelési ügylet munkafolyamataival való munkához lépjen a **Visszatérítés-kezelés \> Beállítás \> Visszatérítés-kezelési munkafolyamatok** lehetőségre. A munkafolyamatokat szükség szerint megtekintheti, létrehozhatja és frissítheti. Egyszerre csak egy ilyen típusú munkafolyamat lehet aktív. A munkafolyamatokkal, **a Visszatérítések kezelése munkafolyamatokkal**[kapcsolatos](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) lap és a munkafolyamatok létrehozásáról a Munkafolyamat rendszer áttekintése és kapcsolódó cikkei nyújtanak további tájékoztatást.

## <a name="use-a-workflow-to-activate-a-deal"></a>Munkafolyamat használata ügylet aktiválásához

Ha egy ügyletet egy munkafolyamaton keresztül szeretne aktiválni, nyissa meg az ügyletet (például az **Összes visszatérítés-kezelési ügylet** oldalon). Majd a műveleti ablaktáblán válassza ki a **Munkafolyamat \> Elküldés** elemet. Az új ügylet munkafolyamaton keresztüli feldolgozása és jóváhagyása után aktív lesz, és használatra kész.

Az ügylet aktiválása után a legtöbb beállítása nem változtatható meg. Ha módosítania kell egy aktív ügyletet, először inaktiválnia kell, majd létre kell hoznia egy új ügyletet. Ha az új ügylet hasonlít a régi ügyletre, akkor a régi ügylet másolásával is létrehozhatja.

Az aktiválást követően az ajánlat következő beállításait módosíthatja:

- Egyeztető
- Kumulatív garancia
- Feladási profil
- Garancia feladási profilja
- Dokumentum megjegyzései
- Pénznem
- Kezdő dátum
- Záró dátum

Ezenkívül a visszatérítési sorok eltávolíthatók.
