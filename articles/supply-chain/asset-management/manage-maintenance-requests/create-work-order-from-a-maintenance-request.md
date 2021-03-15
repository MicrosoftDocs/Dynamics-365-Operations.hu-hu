---
title: Munkarendelések létrehozása karbantartási kérésekből
description: Ez a témakör azt mutatja be, hogyan lehet munkarendelést létrehozni karbantartási kérésből az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 23039306bb827beb861eaacc3177f4917fabc8bf
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018096"
---
# <a name="create-work-orders-from-maintenance-requests"></a>Munkarendelések létrehozása karbantartási kérésekből

[!include [banner](../../includes/banner.md)]

 


Miután létrehozta a karbantartási kéréseket, egyszerűen átalakíthatja azokat a munkarendelésekké. Ez a témakör a karbantartási kérésekkel végzett munkával kapcsolatos leggyorsabb módszert írja le, egyszerre több karbantartási kérelmet frissít, majd egyszerre több karbantartási kérelemhez készít munkarendelést. Az **Aktív karbantartási kérések** vagy **Saját munkavégzési helyszínhez tartozó karbantartási kérések** oldalon egyszerre egy karbantartási kéréssel is dolgozhat, és egy karbantartási kérést is átalakíthat munkarendeléssé.

> [!NOTE]
> Minden karbantartási kérés csak egy munkarendeléshez kapcsolható. Azonban több karbantartási kérés is szerepelhet egy munkarendelésben, még akkor is, ha a karbantartási kérések különböző eszközökkel rendelkeznek.

1. Válassza az **Eszközkezelés** \> **Közös** \> **Karbantartási kérések** \> **Összes karbantartási kérés** lehetőséget.
2. Ahhoz, hogy a karbantartási kérésekből munkarendeléseket hozhasson létre, ki kell választania legalább egy karbantartási feladattípust a karbantartási kérésekhez, valamint egy karbantartási feladattípust- változatot és szakmát ha ez az információ releváns. A rácsnézetben egyszerűen frissítheti a karbantartási kérések adatait.
3. Ha készen áll a munkarendelés létrehozására, válassza ki azokat a karbantartási kéréseket, amelyeket bele szeretne foglalni abba.

    - Ha több karbantartási kérést választ egy munkarendeléssé konvertáláshoz, akkor a munkarendelés létrehozása előtt az **Eszköz** és a **Karbantartási feladat típusa** mezőt is be kell állítania.
    - Ha egy munkarendelésre való átalakításhoz kiválaszt egy karbantartási kérést, csak az **Eszköz** mezőt kell megadni a munkarendelés létrehozása előtt. A munkarendelés létrehozásakor azonban a **Munkarendelés létrehozása** párbeszédpanelen kiválaszthatja a karbantartási feladat típusát (és a kapcsolódó karbantartási feladattípus változatát és szakmáját, ha ez az információ releváns).

4. **Munkarendelés** kiválasztása.
5. A **A Munkarendelés létrehozása** párbeszédpanelen állítsa be a mezőket, majd kattintson az **OK** gombra.

    Egy üzenetsáv figyelmeztetést adhat arról, hogy új munkarendelést hoztak létre.

    Ezenkívül amikor karbantartási kérésen alapuló munkarendelést hoz létre, ha a karbantartási kéréssel kapcsolatos eszköz szerepel egy garanciális megállapodásban, egy üzenetsáv értesíti a garanciamegállapodásról.

6. Válassza az **Eszközkezelés** \> **Közös** \> **Munkarendelések** \> **Összes munkarendelés** lehetőséget, és nyissa meg az új munkarendelést.

    ![Új munkarendelés nyitása](media/05-manage-maintenance-requests.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]