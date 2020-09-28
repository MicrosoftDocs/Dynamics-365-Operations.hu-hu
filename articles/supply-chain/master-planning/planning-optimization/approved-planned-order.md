---
title: Tervezett rendelések jóváhagyása
description: Ez a témakör a Tervezés optimalizálása során támogatott tervezett rendelések jóváhagyását írja le.
author: ChristianRytt
manager: tfehr
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: b7975088be898ccecceb1f7be009cecff107f6e6
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759688"
---
# <a name="approve-planned-orders"></a>Tervezett rendelések jóváhagyása

[!include [banner](../../includes/banner.md)]

Ez a témakör a tervezett rendelések állapotának a Tervezés optimalizálásában történő frissítésével kapcsolatban tartalmaz tájékoztatást.

Ne feledje, hogy a tervezett rendelések jóváhagyása nem kötelező lépés, amellyel megerősített rendelést hozhat létre egy tervezett rendelésből. Ajánlott jóváhagyni a módosított tervezett rendeléseket, különben a program figyelmen kívül hagyja a módosításokat, és a következő tervezés futtatásakor felülírja őket.

![Tervezett rendelés folyamata](media/approved-planned-orders-1.png)

Az **Állapot** mező a következő értékek használatával segít a folyamat követésében:

- **Feldolgozatlan** Amikor az alaptervezés tervezett rendeléseket készít, akkor a tervezett rendelések állapota *Feldolgozatlan*. Az ilyen állapotú tervezett rendeléseket a program a következő tervezés futtatásakor törli.
- **Befejezve:** Ha úgy dönt, hogy nem erősít meg egy tervezett rendelést, akkor az állapot *Befejezett* értékre módosításával jelezheti, hogy befejezte a tervezett rendelés kiértékelését. Ne feledje, hogy a rendszer a *Feldolgozatlan* és a *Befejezett* állapotot ugyanúgy kezeli.
- **Jóváhagyva:** Ha meg akarja tartabi a módosításokat, vagy tervezett rendelést szeretne megerősíteni, akkor módosítsa az állapotot *Jóváhagyott* értékre. Az Alaptervezés megerősített és várt ellátásnak veszi a *Jóváhagyott* állapotú tervezett rendeléseket, így azokat nem módosítja vagy nem törli a program későbbi alaptervezés futtatása során. Ennek elérése érdekében a tervezési logika átmásolja a *Jóváhagyott* tervezett rendeléseket a régi terv verzióból az új terv verzióba az alaptervezés során. Ne felejtse el, hogy a *Jóváhagyott* tervezett rendelések csak az adott alaptervben számítanak ellátásnak.

A tervezett rendeléseket kezelheti az **Alaptervezés** munkaterületen, a **Tervezett rendelés** listában, vagy a **Tervezett termelési rendelések**, **Tervezett beszerzési rendelések**, és **Tervezett átmozgatás** listákban.
