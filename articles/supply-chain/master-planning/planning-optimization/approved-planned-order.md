---
title: Tervezett rendelések jóváhagyása
description: Ez a témakör a Tervezés optimalizálása során támogatott tervezett rendelések jóváhagyását írja le.
author: ChristianRytt
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 6c215a89403f16336caae5c62cde6df469c4091c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825891"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]