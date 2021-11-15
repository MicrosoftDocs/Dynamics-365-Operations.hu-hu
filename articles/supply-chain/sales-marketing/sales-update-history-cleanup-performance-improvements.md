---
title: Értékesítési előzmények adattisztítási teljesítményének javításai
description: Ez a témakör az értékesítési előzmények tisztítása teljesítményjavítási funkcióját és engedélyezését ismerteti.
author: myvakalo
ms.date: 10/05/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: d4eeee3c1228b278fea07464f35946c295c5aea8
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/25/2021
ms.locfileid: "7679055"
---
# <a name="saleshistorycleanupperformanceimprovements"></a>Értékesítési előzmények adattisztítási teljesítményének javításai

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)] <!-- GA with 10.0.24 -->

Az **Értékesítési előzményadatok megtisztítása** időszakos kötegelt feladat hosszú ideig tart, ha ritkán olyan környezetben futtatják, ahol nagy mennyiségű értékesítési frissítés van. Az *Értékesítési előzmények tisztítása teljesítményjavításai* szolgáltatás ilyen helyzetekben csökkentheti a futási időtartamot, és javíthatja a megbízhatóságot.

A funkció a következőképpen javítja a meglévő tisztítási feladatot:

- A tisztítást kötegekre osztja (a testreszabásokkal módosíthatja a kötegméretet).
- Maximum 2 óráig fog futni (testreszabásokkal módosíthatja az időtartamot).
- Ahol lehetséges, az adatbázissal kapcsolatos funkciókat használ a zárolási versengés minimalizálásához, hogy a tisztítás során ne kelljen csatlakoztatni a tranzakciós táblákat.

A funkció engedélyezése után az **Értékesítések frissítési előzményeinek tisztítása** kötegelt feladat (**Értékesítési és marketing \> Időszakos feladatok \> Tisztítás \> Értékesítés frissítési előzményeinek tisztítása**) a korábbiakkal megegyezően fog futni, de jobb teljesítménnyel és maximum 2 órás működéssel fog futni. Ez azt jelenti, hogy egy adott megőrzési időkeret minden adatának tisztítása többször is szükséges lehet.

## <a name="turn-on-the-saleshistorycleanupperformanceimprovements-feature"></a>Értékesítési előzmények adattisztítási teljesítményének javításai funkció bekapcsolása

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Értékesítés és marketing*
- **Funkció neve:** *Értékesítési előzmények adattisztítási teljesítményének javításai*