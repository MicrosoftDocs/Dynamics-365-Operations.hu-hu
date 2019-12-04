---
title: A tervezésoptimalizálása illeszkedési elemzése
description: Ez a témakör azt mutatja be, hogyan lehet ellenőrizni az aktuális beállításokat és adatokat a Tervezésoptimalizálás funkció szolgáltatásaival szemben.
author: ChristianRytt
manager: AnnBe
ms.date: 1030/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 26b067f8526df16474c0ab52d0abf816170ff5cb
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773974"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="planning-optimization-fit-analysis"></a>A tervezésoptimalizálása illeszkedési elemzése

Ha szeretné megtekinteni, hogy az aktuális beállítások és adatok kompatibilisek-e a tervezésoptimalizálás funkcióval, nyissa meg az **Alaptervezés** \> **Beállítás** \> **Tervezésoptimalizálás illeszkedési elemzése** lehetőséget, majd az **Elemzés futtatása** parancsot. Ha az elemzés bármilyen következetlenséget talál, akkor ugyanazon a lapon szerepelnek. (Az elemzés néhány percet is igénybe vehet.)

> [!NOTE]
> Ha találhatók következetlenségek, akkor a tervezésoptimalizálása továbbra is használható. Az illeszkedési elemzés eredményei csak azokat a helyeket jelenítik meg, ahol a tervezési szolgáltatás nem tiszteli az aktuális beállításokat. Más szóval azokat a helyeket jelenítik meg, ahol bizonyos folyamatok figyelmen kívül lehetnek hagyva, vagy esetleg nem támogatottak.

## <a name="analysis-results-example-1"></a>Elemzési eredmények: 1. példa

- **Funkció:** Termelés
- **Hiba:** Nullánál nagyobb BOM-szinttel rendelkező cikkek: 56
- **Magyarázat:** Az illeszkedési elemzés 56 olyan cikket talál, amelynél a termeléshez anyagjegyzéket (BOM) állítottak be. Mivel a tervezésoptimalizálás modul jelenlegi verziója nem támogatja a termelést, a tervezésoptimalizálás a tervezett termelési rendelések helyett tervezett beszerzési rendeléseket fog generálni. Emellett figyelmeztetés jelenik meg, amely felsorolja az érintett cikkeket.

### <a name="analysis-results-example-2"></a>Elemzési eredmények: 2. példa

- **Funkció:** műveletek
- **Probléma:** Fedezeti csoportok, ahol műveletek számítása engedélyezett: 6
- **Magyarázat:** Az illeszkedési elemzés hat olyan fedezeti csoportot talált, ahol a műveletszámítás be van kapcsolva. Mivel a tervezésoptimalizálás jelenlegi verziója nem támogatja a műveleteket, az Alaptervezés során nem jönnek létre műveletek.

## <a name="related-resources"></a>Kapcsolódó erőforrások

[Tervezés optimalizálása – áttekintés](planning-optimization-overview.md)

[Első lépések a tervezési optimalizálással](get-started.md)

[Tervelőzmények és tervezési naplók megtekintése](plan-history-logs.md)

[Szűrők alkalmazása egy tervre](plan-filters.md)

[Tervezési feladat érvénytelenítése](cancel-planning-job.md)
