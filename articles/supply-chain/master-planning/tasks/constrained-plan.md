---
title: Korlátozott terv létrehozása
description: Ez a témakör elmagyarázza, hogyan lehet olyan tervet létrehozni, amely számításba veszi mind az anyagi mind pedig a kapacitásbeli megszorításokat.
author: ShylaThompson
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c35d5a7465cc6cfe0bc12cb00796eff2aeed1ece
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808016"
---
# <a name="generate-a-constrained-plan"></a>Korlátozott terv létrehozása

[!include [banner](../../includes/banner.md)]

Ez a témakör elmagyarázza, hogyan lehet olyan tervet létrehozni, amely számításba veszi mind az anyagi mind pedig a kapacitásbeli megszorításokat. A terv gondoskodik arról, hogy a gyártás ne induljon el az anyagok elérhetővé válása előtt, és hogy az erőforrások ne legyenek túlfoglalva. 

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