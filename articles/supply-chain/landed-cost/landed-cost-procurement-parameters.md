---
title: Partraszállási költség beszerzési és forrásparaméterei
description: Ez a témakör leírja, hogyan lehet beállítani a vonatkozó beszerzés- és forrásparamétereket a Partra kerülve költségmodul használata esetén.
author: Weijiesa
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 92ce3e3d09bed15970375735f680b1b8348bbca8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905979"
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
