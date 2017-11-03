---
title: "Egy értékesítési rendelés foglalása ugyanazon kötegből"
description: "Ez a cikk ismerteti, hogyan végezze el termék beállítását a készletfoglalás engedélyezéséhez a készlet egyetlen adott kötegéből."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8e0f8f85609e7c3095f13738d43cdf5734018eaa
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="reserve-the-same-batch-for-a-sales-order"></a>Egy értékesítési rendelés foglalása ugyanazon kötegből

[!include[banner](../includes/banner.md)]


Ez a cikk ismerteti, hogyan végezze el termék beállítását a készletfoglalás engedélyezéséhez a készlet egyetlen adott kötegéből.

Az ugyanazon kötegből való foglalás funkcióval egy értékesítési rendelést a készlet egyetlen adott kötegéből foglalhatja le. Tegyük fel, hogy egy tapétát rendelő vevő azt szeretné, hogy a teljes rendelést egy adott kötegből vagy adagból szállítsák neki, nehogy eltérő legyen a tekercsek minősége. Ha egyazon kötegből szeretne foglalni, az alábbi beállításoknak kell aktívnak lenniük a termékhez rendelt cikkmodellcsoportban, a nyomon követési dimenzióban és a tárolási dimenziócsoportban:

-   **Cikkmodellcsoportok** – A cikkmodellcsoportnál be kell jelölni az **Azonos köteg kiválasztása** és az **Összesített követelmény** mezőket a **Foglalás** mezőcsoportban, a készletirányelvek között.
-   **Nyomon követési dimenziócsoportok** – A nyomon követési dimenziócsoportoknál be kell jelölni a kötegszámhoz tartozó **Fedezeti terv dimenziónként** mezőt.
-   **Tárolási dimenziócsoportok** – A tárolási dimenziócsoportoknál be kell jelölni a **Fedezeti terv dimenziónként** mezőt a **Hely** és a **Raktár** vonatkozásában.

Amikor ugyanazon kötegből foglalja egy értékesítési rendelés termékeit, a Microsoft Dynamics 365 for Finance and Operations megpróbálja a teljes rendelt mennyiséget egyetlen készletkötegből foglalni. Az esetleges specifikus kötegattribútumokat is figyelembe veszi. Ha a mennyiség rendelhető be egyetlen kötegől, akkor az **Azonos köteg foglalása miatti ütközés** lap jelenik meg. Ez az oldal leírja a problémákat, és a lehetséges megoldásokat is, amelyekkel folytathatja a foglalást. A következő események akadályozhatják meg a tétel foglalását:

-   A kötegrendelkezési kódnál **Foglalás letiltása** van beállítva a **Zárolva** állapotú értékesítésekre.
-   A köteg a lejárati dátum alapján és a vevői eladhatósági napok alapján már lejárt. A cikk még nem alkalmas lefoglalásra, ha a cikkmodellcsoportja FEFO dátumvezérelt, és a komissiózási feltétel a lejárati nap.
-   A köteg eltarthatósági napjaiból fennmaradó idő nem elégséges, a lejárati dátum és a szavatosság dátuma alapján, illetve a vevői eladhatósági napok alapján.





