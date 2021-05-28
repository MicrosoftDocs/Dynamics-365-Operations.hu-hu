---
title: Több készlettranzakció kötegszámokhoz, ha a Tényleges frissítéskor nincs engedélyezve
description: Több készlettranzakció jön létre, miután módosította a beszerzésirendelés-sort az olyan cikkekhez, amelyeknél a kötegszámcsoport Tényleges frissítésekor beállításának értéke Nem.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventNumGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1fa54cdfdbc5608fb6c7114dced0f96bab47253e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026589"
---
# <a name="multiple-inventory-transactions-for-batch-numbers-when-on-physical-update-is-disabled"></a>Több készlettranzakció kötegszámokhoz, ha a Tényleges frissítéskor nincs engedélyezve

Tudásbáziscikk száma: 4613390

## <a name="symptoms"></a>Tünetek

Több készlettranzakció jön létre, miután módosította a beszerzésirendelés-sort az olyan cikkekhez, amelyeknél a kötegszámcsoport **Tényleges frissítésekor** beállításának értéke *Nem*.

Ha olyan cikket hoz létre, ahol a kötegszámcsoport **Tényleges frissítéskor** beállítási beállítása *Nem*, a rendszer automatikusan létrehoz egy új kötegszámot, ha módosítja egy beszerzési sor mennyiségét, és menti a beszerzési rendelés lapját.

## <a name="resolution"></a>Felbontás

A kötegszámcsoportok **Tényleges frissítéskor** beállítása a következő módon működik:

- Ha a beállítás *Igen*, az új kötegszámok csak a tényleges frissítés után (például a cikkek kiszállításakor vagy fogadásakor jönnek létre).
- Ha a beállítás *Nem*, egy új kötegszám jön létre minden alkalommal, amikor egy vonatkozó frissítés történik (például amikor új mennyiséget adnak hozzá egy beszerzési rendeléshez).
