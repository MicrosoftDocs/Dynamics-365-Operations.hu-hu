---
title: "Az aktuális készlet költségértékeinek korrekciója"
description: "Az Aktuális készlet korrekciója lapon beállíthatja az aktuális készlet mennyiségeinek költségértékét a készletzárási folyamat futtatása után."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d1ef775c9783b975fd0f852dc7112506d3897605
ms.lasthandoff: 03/31/2017


---

# <a name="adjust-on-hand-inventory-cost-values"></a>Az aktuális készlet költségértékeinek korrekciója

Az Aktuális készlet korrekciója lapon beállíthatja az aktuális készlet mennyiségeinek költségértékét a készletzárási folyamat futtatása után.

Az **Aktuális készlet korrekciója** oldalon módosíthatja az aktuális készlet mennyiségeinek költségértékét a készletzárási folyamat futtatása után. **Megjegyzés:** megnyitásához a **az aktuális készlet korrekciója** oldalon, a a **zárás és helyesbítés** lapon, jelölje ki a bejegyzést egy befejezett készlet szoros folyamat, és kattintson **korrekciós**&gt;**aktuális**. **Példa:** Februárban a következő tranzakciók voltak:

-   Február 1.: pénzügyi bevételezés készletre, 2 mennyiséggel, 10,00 USD áron
-   Február 5.: pénzügyi bevételezés készletre, 1 mennyiséggel, 13,00 USD áron
-   Február 19.: pénzügyi kiadás készletről, 1 mennyiséggel, 11, 00 USD mozgóátlagon alapuló önköltségi áron

Ez az elem a lett beállítva az első, először ki (FIFO) Készletmodell, és zárja be a készlet február 28 szerint történt. A programnak a február 1 pénzügyi átvételi elismervény ellenében a USD 11.00 a pénzügyi kiadási tranzakció rendezik, és a USD 1.00 fogja igazítani. A következő készletbevételezések ekkor nyitott készletmennyiségeket tartalmaznak:

-   Febuár 1: mennyiség: 1, a költség 10,00 USD.
-   Febuár 5: mennyiség: 1, a költség 13,00 USD.

Ahhoz, hogy ennek a két cikknek az árát 15,00 USD értékre lehessen beállítani, az aktuális készlet módosítására használható funkcióval korrigálni kell a nyitott aktuális készletmennyiségeket a legutolsó készletzárási időszaknak megfelelően. **Megjegyzés:** Az aktuális készletet korrigáló tranzakció feladási dátuma a legutóbbi készletzárás dátuma lesz. Ez a dátum nem módosítható.


