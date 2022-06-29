---
title: Munkarendelések létrehozása karbantartási kérésekből
description: Ez a cikk bemutatja, hogyan lehet munkarendelést létrehozni az Eszközkezelésben karbantartási kérésből.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bb54ec3466086afbd87a023a40e346a6a3464c98
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9017174"
---
# <a name="create-work-orders-from-maintenance-requests"></a>Munkarendelések létrehozása karbantartási kérésekből

[!include [banner](../../includes/banner.md)]

 


Miután létrehozta a karbantartási kéréseket, egyszerűen átalakíthatja azokat a munkarendelésekké. Ez a témakör a karbantartási kérések gyors munkához, egyszerre több karbantartási kérés frissítéséhez, majd több karbantartási kéréshez egyidejűleg több munkarendelés létrehozásához ad le. Az **Aktív karbantartási kérések** vagy **Saját munkavégzési helyszínhez tartozó karbantartási kérések** oldalon egyszerre egy karbantartási kéréssel is dolgozhat, és egy karbantartási kérést is átalakíthat munkarendeléssé.

> [!NOTE]
> Minden karbantartási kérés csak egy munkarendeléshez kapcsolható. Azonban több karbantartási kérés is szerepelhet egy munkarendelésben, még akkor is, ha a karbantartási kérések különböző eszközökkel rendelkeznek.

1. Válassza ki **az Eszközkezelés** \> **karbantartási kérései közül** \> **az összes karbantartási kérést**.
2. Ahhoz, hogy a karbantartási kérésekből munkarendeléseket hozhasson létre, ki kell választania legalább egy karbantartási feladattípust a karbantartási kérésekhez, valamint egy karbantartási feladattípust- változatot és szakmát ha ez az információ releváns. A rácsnézetben egyszerűen frissítheti a karbantartási kérések adatait.
3. Ha készen áll a munkarendelés létrehozására, válassza ki azokat a karbantartási kéréseket, amelyeket bele szeretne foglalni abba.

    - Ha több karbantartási kérést választ egy munkarendeléssé konvertáláshoz, akkor a munkarendelés létrehozása előtt az **Eszköz** és a **Karbantartási feladat típusa** mezőt is be kell állítania.
    - Ha egy munkarendelésre való átalakításhoz kiválaszt egy karbantartási kérést, csak az **Eszköz** mezőt kell megadni a munkarendelés létrehozása előtt. A munkarendelés létrehozásakor azonban a **Munkarendelés létrehozása** párbeszédpanelen kiválaszthatja a karbantartási feladat típusát (és a kapcsolódó karbantartási feladattípus változatát és szakmáját, ha ez az információ releváns).

4. **Munkarendelés** kiválasztása.
5. A **A Munkarendelés létrehozása** párbeszédpanelen állítsa be a mezőket, majd kattintson az **OK** gombra.

    Egy üzenetsáv figyelmeztetést adhat arról, hogy új munkarendelést hoztak létre.

    Ezenkívül amikor karbantartási kérésen alapuló munkarendelést hoz létre, ha a karbantartási kéréssel kapcsolatos eszköz szerepel egy garanciális megállapodásban, egy üzenetsáv értesíti a garanciamegállapodásról.

6. Válassza ki **az Eszközkezelés** \> **munkarendelések minden** \> **munkarendelését**, és nyissa meg az új munkarendelést.

    ![Új munkarendelés nyitása.](media/05-manage-maintenance-requests.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]