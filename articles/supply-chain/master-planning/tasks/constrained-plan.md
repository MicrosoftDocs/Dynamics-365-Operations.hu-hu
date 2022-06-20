---
title: Korlátozott terv létrehozása
description: Ez a cikk bemutatja, hogyan lehet olyan tervet létrehozni, amely mind az anyag, mind a kapacitás megszorítását figyelembe veszi.
author: t-benebo
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 65884d556724cd6132fe328e95a5bec78885c174
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904014"
---
# <a name="generate-a-constrained-plan"></a>Korlátozott terv létrehozása

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet olyan tervet létrehozni, amely mind az anyag, mind a kapacitás megszorítását figyelembe veszi. A terv gondoskodik arról, hogy a gyártás ne induljon el az anyagok elérhetővé válása előtt, és hogy az erőforrások ne legyenek túlfoglalva. 

Ez az eljárás az USMF bemutatócéget használja. Ezt az eljárást a termeléstervező használja.


## <a name="set-up-a-constrained-plan"></a>Korlátozott terv beállítása
1. Válassza ki az **Alaptervezés** munkaterületet a kezdőlapon.
2. Válassza ki az **Alapterveket** a munkaterület jobb szélén található hivatkozások listáján.
3. Keresse meg és jelölje ki a kívánt rekordot a listán. Példa: **StaticPlan**  
4. Válassza az **Igen** lehetőséget a **Véges kapacitás** mezőben.
5. A **Végleges kapacitás időkorlátja** mezőbe, írja be: `30`.
6. Bontsa ki az **Időkorlátokat napokban** szakaszt.
7. Válassza az **Igen** lehetőséget a **Kapacitás** mezőben.
8. A **Kapacitásütemezési időkorlát (napok)** mezőbe írjon be egy számot. Példa: `60`  
9. Válassza ki az **Igen** lehetőséget a **Kiszámított késések** mezőben.
10. A **Kiszámított késések időkorlátja (napok)** mezőbe írjon be egy számot. Példa: `60` 
11. A **Kiszámított késések** szakasz kibontása.
12. Válassza ki az **Igen** lehetőséget az összes **Számított késés hozzáadása a követelménydátumhoz** mezőben.
13. Zárja be a lapot.

## <a name="create-a-constrained-plan"></a>Korlátozott terv létrehozása
1. Válassza a **Futtatás** parancsot.
2. Az **Alapterv** mezőbe írja be vagy válassza ki azt a tervet, amelyhez be szeretné állítani a megszorításokat.  
3. Válassza ki az **OK** lehetőséget.
4. **Tervezett rendelések** kiválasztása.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]