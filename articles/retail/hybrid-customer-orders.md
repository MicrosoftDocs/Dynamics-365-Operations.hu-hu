---
title: "Hibrid vevői rendelések"
description: "A hibrid vevői rendelés lehet egyetlen rendelés, amely az ügyfél által az üzletből kivihető termékeket tartalmaz, illetve tartalmazhat olyan termékeket, amelyek átvételére vagy kiszállítására később kerül sor."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ed5d403c1321e2573df38d60956e6f89282b3de8
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="hybrid-customer-orders"></a>Hibrid vevői rendelések

[!INCLUDE [banner](includes/banner.md)]

A hibrid vevői rendelés lehet egyetlen rendelés, amely az ügyfél által az üzletből kivihető termékeket tartalmaz, illetve tartalmazhat olyan termékeket, amelyek átvételére vagy kiszállítására később kerül sor.

A Microsoft Dynamics 365 for Retail programban választhatja az összes termék végrehajtását, vagy végrehajthat kijelölt termékeket az adott vevői rendeléshez. A végrehajtandóként megjelölt terméksorok számlázása automatikusan megtörténik a rendelés létrehozása után, és hasonlóképpen azon megrendeléseknél, amelyek átvétele a rendelés létrehozása után történik. A hibrid rendeléseknél esedékes összeg meghatározása a végrehajtandó sorokhoz a letéti százalék hozzáadásával történik a kitárolási és szállítási soroknál. A hibrid rendelések esetén a rendszer az alábbiak szerint vált a vevői rendelési mód és a cash and carry mód között:

-   Ha a bevásárlókosárban található összes termék **Szállítás elvégzése** értékre van állítva, a rendelést a rendszer Cash and Carry tranzakcióként fogja kezelni.
-   Ha a kosár bármely vagy összes sora **Kitárolás** vagy **Kiszállítás** értékre van állítva, a rendelést a rendszert vevői rendelési tranzakcióként fogja kezelni.

Ha a bevásárlókocsi egy soránál kiválasztja a **Kijelölt kitárolása**, **Kijelölt szállítása** vagy **Kiválasztott elvégzése** értéket, ez a szállítási mód csak az adott bevásárlókocsisorra lesz érvényes. Ebben az esetben a művelet lefelé irányuló folyamata a szokásos módon folytatódik. Azonban ha a **Kijelölt kitárolása**, **Kijelölt szállítása**, vagy **Kiválasztott elvégzése** lehetőséget anélkül választja ki, hogy a bevásárlókocsi egy sora ki lenne jelölve, megnyílik egy új lap, amely az összes bevásárlókocsi-sort felsorolja. Ezen a képernyőn több sort kijelölhet egyszerre a kézbesítési mód beállítására. Ha ezt a módszert használja sorok kijelöléséhez, a rendszer az adott sorhoz rendelt minden korábbi kézbesítési módot felülbírálja.

<a name="see-also"></a>Lásd még
--------

[Vevői rendelések – áttekintés](customer-orders-overview.md)




