---
title: A szabálytalanságok diagnosztikai típusai
description: Ez a témakör azt ismerteti, hogyan lehet a szabálytalanságokkal használható diagnosztikai típusokat használni és létrehozni.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestDiagnosticType, InventTestCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7a5c593f1d9e8f7a77f693f6e652e9355a985fb
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022276"
---
# <a name="diagnostic-types-for-nonconformances"></a>A szabálytalanságok diagnosztikai típusai

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet a szabálytalanságokkal használható diagnosztikai típusokat használni és létrehozni.

A **Diagnosztikai típusok** oldal használatával határozhatja meg a diagnosztikai műveletek osztályozását. Ezután a szabálytalanság korrekciójának létrehozásakor ki kell választani egy diagnosztikai vizsgálatot. A javítás meghatározza, hogy milyen típusú diagnosztikai műveletet kell végrehajtani a jóváhagyott szabálytalanságon, valamint hogy kinek kell elvégeznie. Azt is meghatározza, melyik napra kérték és mikorra tervezik a végrehajtást.

## <a name="examples-of-diagnostic-types"></a>Néhány példa a diagnosztikai típusokra

Egy gyártó cégnél dolgozik, és több cikknél nem sikerült a minőségi teszt. Ezeket a cikkeket karanténterületre helyezik át, és nem megfelelő termékként jelölik meg. Szabálytalanságrekordot hoz létre a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban, hogy a probléma megoldása közben nyomon kövesse a részleteket.

Ebben az esetben a minőségbiztosítási problémák azért fordulnak elő, mert a csomagológépben található olyan csapágyak elromlottak és túlmelegedtek. A problémát úgy tudják megszűntetni, ha kicserélik az alkatrészt.

A diagnosztikai típusok konfigurálása során több rekordot is létre lehet hozni, amelyek a gép számára eltérő típusú problémát képviselnek. Másik lehetőségként létrehozhat egy általános diagnosztikai típust, amely a gép javítását jelzi.

## <a name="create-a-diagnostic-type"></a>Diagnosztikai típus létrehozása

1. Ugorjon a **Készletgazdálkodás \> Beállítás \> Minőségkezelés \> Diagnosztikai típusok** pontra.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz. Ezután új sorhoz állítsa be a következő mezőket:

    - **Diagnosztika** – A diagnosztikai típus egyedi azonosítójának vagy nevének megadása.
    - **Leírás** – Adja meg a diagnosztikai típus részletes leírását.

1. Zárja be a lapot.

## <a name="additional-resources"></a>További erőforrások

- [Minőségkezelés áttekintése](quality-management-processes.md)
- [A minőség- és a szabálytalanságkezelés engedélyezése](enable-quality-management.md)
- [A szabálytalanságok jóváhagyásáért felelős dolgozók](quality-responsible-workers.md)
- [A szabálytalanságok karanténzónái](quality-quarantine-zones.md)
- [A szabálytalanságok problématípusai](quality-problem-types.md)
- [Szabálytalanságok minőségi költségei](quality-charges.md)
- [Műveletek szabálytalanságokhoz kapcsolódóan](quality-operations.md)
- [Raktári folyamatok minőségkezelése](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
