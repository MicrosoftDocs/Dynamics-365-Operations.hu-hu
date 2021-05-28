---
title: Partraszállási költség beszerzési és forrásparaméterei
description: Ez a témakör ismerteti, hogyan lehet beállítani a releváns beszerzési és forrásparamétereit a Partraszállási költség modul használata során.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: ccda3bd769a646e2390711883b8e40bec50e4d6a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020983"
---
# <a name="procurement-and-sourcing-parameters-for-landed-cost"></a>Partraszállási költség beszerzési és forrásparaméterei

[!include [banner](../../includes/banner.md)]

A **Beszerzés és forrásparaméterek** oldalon néhány olyan beállítás is van, amelyek különösen fontosak a **Partraszállási költség** modul használatakor. A **Beszerzési és forrásparaméterek** oldaláról megnyitott **Rendeléssorok frissítése** párbeszédpanellel megadhatja, hogy a beszerzésirendelés-sorokat a rendszer automatikusan frissítse, amikor módosítják a beszerzési rendelés fejlécét.

Ennek a beállításnak a befejezéséhez kövesse az alábbi lépéseket.

1. Nyissa meg a **Beszerzés és forrás \> Beállítás \> Beszerzés és forrás paraméterei** pontot.
1. Az **Általános** lapon válassza a **Rendeléssorok frissítése** hivatkozást.
1. A **Rendeléssorok frissítése** párbeszédpanel felsorolja a rendelés fejlécében található mezőket, amelyek a rendeléssorok kapcsolódó mezőire automatikus frissítéseket is alkalmazhatnak. A lista minden mezőjét a következő értékek egyikére állíthatja:

    - **Mindig** – A rendelésfejléc frissítése esetén a rendeléssoroknak automatikusan frissülniük kell.
    - **Soha** – A rendelésfejléc frissítése esetén a rendeléssoroknak sosem szabad frissülniük.
    - **Rákérdezés** – A program megkéri a felhasználót, hogy döntse el, hogy kell-e frissíteni a rendelési sorokat.
