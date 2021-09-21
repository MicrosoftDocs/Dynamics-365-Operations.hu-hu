---
title: Készletállapot-változás végrehajtása részleges mennyiségi munkához
description: Ez az oldal bemutatja, hogyan lehet olyan menüelemet létrehozni a megfelelő beállításokkal, amely lehetővé teszi, hogy a dolgozók módosítsák egy köteg egy részmennyiségének készletállapotát.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 056ce412955808ddf126025ad917b874c54a5e62
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476502"
---
# <a name="enable-inventory-status-change-for-partial-quantity-work"></a>Készletállapot-változás engedélyezése részleges mennyiségi munkához

## <a name="symptoms"></a>Tünetek

Egy köteg részleges mennyiségéről létre kell hozni egy készletállapot módosítást.

## <a name="resolution"></a>Megoldás

Ha engedélyezni szeretné, hogy a dolgozók elvégezzék ezt a módosítást, akkor létrehozhat egy menüelemet a Raktárkezelés mobilalkalmazás számára. A **Mobileszköz menüpontok** oldalon hozzon létre (vagy szerkesszen) egy menüpontot a következő beállításokkal:

- **Mód:** *Munka*
- **Meglévő munka használata:** *Nem*
- **Munkalétrehozási folyamat:** *Áthelyezés*
- **Készletállapot megjelenítése:** *Igen*

A lapon szükség szerint megadhat más mezőket is.
