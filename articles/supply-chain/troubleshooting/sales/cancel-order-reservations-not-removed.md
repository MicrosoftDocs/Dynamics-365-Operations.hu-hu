---
title: Rendelés törlésekor a foglalások nem távolíthatók el
description: Az értékesítési rendelés nem törölhető, amíg a hozzá társított munka nincs érvénytelenítve és visszavonva. Ehhez kövesse a következő három lépést.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a8d947e64568246dba5eff3c21fd3920b6494b73
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476563"
---
# <a name="reservations-cannot-be-removed-when-canceling-an-order"></a>Rendelés törlésekor a foglalások nem távolíthatók el

## <a name="symptoms"></a>Tünetek

Ha egy értékesítési rendeléshez munka van társítva, és megpróbálja érvényteleníteni a rendelést, a következő hibaüzenet jelenik meg:

> A foglalások nem távolíthatók el, mert létezik a foglalásokon alapuló munka.

Az értékesítési rendelés nem törölhető, amíg a munka nincs érvénytelenítve és visszavonva. Ez a követelmény akkor is érvényes, ha az értékesítési rendeléshez társított munka le van zárva.

## <a name="resolution"></a>Megoldás

A probléma megoldásához kövesse az alábbi lépéseket:

1. Érvénytelenítse a munkát és a készletet helyezze vissza a kívánt helyre. Nyissa meg az értékesítési rendelés megfelelő rakományát, majd válassza a **Kitárolt mennyiség csökkentése** lehetőséget a rakománysorban vagy a **Munka sztornírozása** lehetőséget Műveleti ablaktáblán.

    A munka állapota most *Érvénytelenítve*, és a rendszer automatikusan létrehozza és feldolgozza az új készletmozgatási munkát, hogy a készletet visszahelyezze arra a helyre, amely a sztornírozásnál le van írva.

2. Törölje a rakományt. A szállítmány is törölve lesz.

3. Most el kell tudnia menni az értékesítési rendeléshez, és érvényteleníteni azt.
