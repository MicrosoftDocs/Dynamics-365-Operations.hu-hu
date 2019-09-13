---
title: Beszerzés
description: Ez a témakör az Eszközkezelésben történő beszerzést ismerteti.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1678dbe2432e4be46aebb40a12e73dfd695c3e77
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875691"
---
# <a name="procurement"></a>Beszerzés


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Az Eszközkezelés modulban áttekintheti a munkarendelésekhez kapcsolódó beszerzési igényléseket és beszerzési rendeléseket. Lehetőség van arra is, hogy beszerzési rendelést vagy beszerzési igénylést hozzon létre egy munkarendelésből.

A **Munkarendelés beszerzési igénylése** listában (**Eszközkezelés** > **Közös** > **Beszerzés** > **Munkarendelés beszerzési igénylése**) láthatók a munkarendelésekhez kapcsolódó beszerzési igénylések.

- Válasszon egy munkarendelési feladatot a **Munkarendelés beszerzési igénylése** listán, majd a **Beszerzési igénylés** gombra kattintva nyissa meg a beszerzési igénylést.  
- Válasszon egy munkarendelési feladatot a **Munkarendelés beszerzési igénylése** listán, majd a **Munkarendelés** gombra kattintva nyissa meg a munkarendelést.  
- Válasszon egy munkarendelést a **Munkarendelés beszerzési igénylése** listában, majd kattintson a **Cikk használati helye** gombra, ha áttekintést szeretne kapni arról, hogy a kiválasztott sorban szereplő cikkek az Eszközkezelés melyik eszközeihez, alapértelmezett karbantartási feladattípusaihoz, pótalkatrészeihez és munkarendeléseihez használatos. 

![1. ábra](media/08-work-orders.png)


A **Munkarendelés beszerzése** listában (**Nagyvállalati eszközkezelés** > **Közös** > **Beszerzés** > **Munkarendelés beszerzése**) láthatók a munkarendelésekhez kapcsolódó beszerzési rendelések.

- Válasszon egy munkarendelési feladatot a **Munkarendelés beszerzése** listán, majd a **Beszerzési rendelés** gombra kattintva nyissa meg a beszerzési rendelést.  
- Válasszon egy munkarendelési feladatot a **Munkarendelés beszerzése** listán, majd a **Munkarendelés** gombra kattintva nyissa meg a kapcsolódó munkarendelést.  
- Válasszon egy munkarendelést a **Munkarendelés beszerzése** listában, majd kattintson a **Cikk használati helye** gombra, ha áttekintést szeretne kapni arról, hogy a kiválasztott sorban szereplő cikkek az Eszközkezelés melyik eszközeihez, alapértelmezett karbantartási feladattípusaihoz, pótalkatrészeihez és munkarendeléseihez használatos. 

![2. ábra](media/09-work-orders.png)


A fent látható listákban az egyes sorok jobb oldalán a szállítási dátum ellenőrzésével kapcsolatos ikon látható. Ha az ikon egy piros körben lévő felkiáltójel, akkor a kapcsolódó beszerzési igényléshez vagy beszerzési rendeléshez tartozó szállítás késhet.

A beszerzési igénylésen az esetleges késés kiszámítására használatos dátum a **Beszerzési igénylések** képernyő > **Beszerzési igénylés fejléce** gyorslap > **Igényelt dátum** mezőben látható. Ezt a dátumot ugyanúgy kell összehasonlítani a munkarendelésen vagy a munkarendelési feladaton szereplő dátummal, mint a beszerzési rendelés dátumát.

A beszerzési rendelésen az esetleges késés kiszámításához használt dátum a beszerzési rendelés sorához kapcsolódó dátum, ami a **Beszerzési rendelés** űrlap > beszerzési rendelés kiválasztott sora > **Sor részletei** gyorslap > **Beállítás** lap > **Visszaigazolt szállítási dátum** mezőben látható. Ha ez a mező nincs kitöltve, akkor a program a **Beszerzési rendelés fejléce** gyorslap **Szállítási dátum** mezőjében lévő dátumot használja. Az egyik dátumot a következő sorrendben kell összehasonlítani a munkarendelésen vagy a munkarendelési feladaton szereplő dátummal:

- A munkarendelésen lévő tényleges kezdési dátum, vagy  

- A kapcsolódó munkarendelési feladat ütemezett kezdési dátuma, vagy  

- A munkarendelésen ütemezett kezdési dátuma, vagy  

- A munkarendelés várt kezdési dátuma  


## <a name="create-purchase-order-from-a-work-order"></a>Beszerzési rendelés létrehozása munkarendelésből

Az **Összes munkarendelés** részen kiválaszthatja a munkarendelési feladatot, és létrehozhat egy kapcsolódó beszerzési rendelést vagy beszerzési igénylést. Így biztosítható a projekt kapcsolata a beszerzési rendelés vagy a beszerzési igénylés és a munkarendelés között.

1. Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.

2. Az **Összes munkarendelés** vagy az **Aktív munkarendelések** listában válassza ki azt a munkarendelést, amelyhez beszerzési rendelést szeretne létrehozni, majd kattintson a **Szerkesztés** elemre.

3. A **Munkarendelés** képernyő > **Munkarendelés karbantartási feladatai** gyorslapon válassza ki azt a munkarendelési feladatot, amelyhez beszerzési rendelést szeretne létrehozni.

4. Kattintson a **Cikkfeladatok** > **Beszerzési rendelés munkarendelésből** elemre.

5. A **Projekt beszerzési rendelései** listaoldalon kattintson az **Új**gombra.

6. Hozza létre a beszerzési rendelést.

>[!NOTE]
>A beszerzési igénylések létrehozása majdnem teljesen úgy történik, mint a beszerzési rendelések létrehozása. Az egyetlen különbség az, hogy a fenti eljárás 2. lépésében a **Cikkfeladatok** > **Beszerzési igénylés munkarendelési feladatból** elemre kell kattintani.

## <a name="project-relation-between-work-order-and-purchase-order-or-purchase-requisition"></a>A munkarendelés és a beszerzési rendelés vagy a beszerzési igénylés közötti projektkapcsolat

Egy beszerzési rendelés vagy egy beszerzési igénylés sora egy munkarendelési feladathoz kapcsolódik a munkarendelési projekten és a kapcsolódó projekttevékenység-számon. Amikor egy beszerzési rendelést vagy beszerzési igénylést munkarendelési feladatból hoz létre, a kapcsolódó projekttevékenység-számot meg kell adni. A projekttevékenység-száma automatikusan rákerül a beszerzési rendelésre vagy beszerzési igénylésre, ha a kapcsolódó munkarendelés olyan munkarendelési feladatokat tartalmaz, amelyek mindegyike ugyanazt a karbantartási feladattípust használja. Ha a munkarendelési feladatok különböző karbantartási feladattípusokat tartalmaznak, akkor manuálisan kell beszúrni a projekttevékenység számát.

A beszerzési rendelés sorához kapcsolódó tevékenység számának megtekintéséhez vagy beszúrásához nyissa meg a **Munkarendelés beszerzése** részt > válassza ki a beszerzési rendelés rekordját > kattintson a beszerzési rendelésre a **Beszerzési rendelés** oszlopban > tekintse meg **Sor részletei** gyorslap > **Projekt** lap > **Tevékenység száma** mezőt.


![3. ábra](media/10-work-orders.png)


Hasonlóképpen, ha egy munkarendelés beszerzési igénylésének sorához kapcsolódó számot szeretne megtekinteni vagy beszúrni, nyissa meg a **Munkarendelés beszerzési igénylése** részt > válassza ki a beszerzési igénylés rekordját > kattintson a beszerzési igénylésre a **Beszerzési igénylés** oszlopban > tekintse meg **Sor részletei** gyorslap > **Projekt** lap > **Tevékenység száma** mezőt.

