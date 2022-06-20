---
title: Beszerzés
description: Ez a témakör bemutatja a beszerzéseket az Eszközkezelésben.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderPurchaseListPagePreviewPane, EntAssetWorkOrderPurchaseListPage, EntAssetWorkOrderPurchaseLineAmountInfoPart, EntAssetWorkOrderPurchReqListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 015499463f1eab4aaa3f3658b3204229382e73cb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893642"
---
# <a name="procurement"></a>Beszerzés

[!include [banner](../../includes/banner.md)]

Az Eszközkezelés modulban áttekintheti a munkarendelésekhez kapcsolódó beszerzési igényléseket és beszerzési rendeléseket. Lehetősége van arra is, hogy beszerzési rendelést vagy beszerzési igénylést hozzon létre egy munkarendelésből.

A **Munkarendelés beszerzési igénylése** listaoldalon (**Eszközkezelés** > **Közös** > **Beszerzés** > **Munkarendelés beszerzési igénylése**) láthatók a munkarendelésekhez kapcsolódó beszerzési igénylések. Amikor ezen a lapon munkarendelési feladatot jelöl ki, a **Munkarendelés beszerzési igénylés** Műveleti paneljének **Megjelenítés** csoportjának gombjaival különböző műveleteket lehet végrehajtani:

- A kapcsolódó beszerzési igénylés megnyitásához válassza ki **Beszerzési igénylés** lehetőséget. 
- A kapcsolódó munkarendelés megnyitásához válassza a **Munkarendelés** lehetőséget.
- Ha szeretne áttekintést kapni arról, hogy hol használják a kiválasztott sorban található cikket az eszközökkel, alapértelmezett feladattípusokkal, pótalkatrészekkel és munkarendelésekkel kapcsolatban, válassza a **Cikket hol használják** elemet. Az áttekintéssel kapcsolatos további tudnivalókat lásd a [Cikk használati helye](../controlling-and-reporting/item-where-used.md)részben.

Az alábbi ábra a **Munkarendelés beszerzési igénylés** listaoldal egy példáját mutatja be.

![1. ábra](media/08-work-orders.png)


A **Munkarendelés beszerzési igénylése** listaoldalon (**Eszközkezelés** > **Közös** > **Beszerzés** > **Munkarendelés beszerzési igénylése**) láthatók a munkarendelésekhez kapcsolódó beszerzési rendelések. Amikor ezen a lapon munkarendelési feladatot jelöl ki, a **Munkarendelés beszerzési igénylés** lapon a Műveleti paneljen a **Megjelenítés** csoportjának gombjaival különböző műveleteket lehet végrehajtani:

- A kapcsolódó beszerzési rendelés megnyitásához válassza a **Beszerzési rendelés** lehetőséget. 
- A kapcsolódó munkarendelés megnyitásához válassza a **Munkarendelés** lehetőséget.
- Ha szeretne áttekintést kapni arról, hogy hol használják a kiválasztott sorban található cikket az eszközökkel, alapértelmezett feladattípusokkal, pótalkatrészekkel és munkarendelésekkel kapcsolatban, válassza a **Cikket hol használják** elemet. Az áttekintéssel kapcsolatos további tudnivalókat lásd a [Cikk használati helye](../controlling-and-reporting/item-where-used.md)részben.

Az alábbi ábra a **Munkarendelés beszerzés** listaoldal egy példáját mutatja be.

![2. ábra](media/09-work-orders.png)


A **Munkarendelés-beszerzése** listaoldal és a **Munkarendelés beszerzési igénylés** listaoldalon a szállítási dátum vezérlőelemhez kapcsolódó szimbólum jelenik meg az egyes sorok jobb oldalán. Ha a szimbólum egy piros körben lévő felkiáltójel, akkor a kapcsolódó beszerzési rendeléshez vagy beszerzési igényléshez tartozó szállítás késhet.

Beszerzési rendelésnél a beszerzési rendelés sorához kapcsolódó dátumot használja a rendszer a lehetséges késések kiszámítására. A dátum megtekintéséhez a **Beszerzési rendelés** lapon válassza ki a beszerzésirendelés-sort. A dátum a **Sor részletei** gyorslapjának **Beállítás** lapjának, a **Visszaigazolt szállítási dátum** mezőjében jelenik meg. Ha nincs beállítva a **Visszaigazolt szállítási dátum** mező, akkor a program a számításhoz a **Beszerzési rendelés fejléce** gyorslap **Szállítási dátum** mezőjének a dátumát használja. Az egyik dátumot a következő sorrendben kell összehasonlítani a munkarendelésen vagy a munkarendelési feladaton szereplő dátummal:

1. A munkarendelésen lévő tényleges kezdési dátum  

2. A kapcsolódó munkarendelési feladat ütemezett kezdési dátuma 

3. A munkarendelés ütemezett kezdési dátuma, vagy 

4. A munkarendelés várt kezdési dátuma 

A beszerzési igénylésen az esetleges késés kiszámításához használatos dátum a **Beszerzési igénylések** képernyő **Beszerzési igénylés fejléce** gyorslap **Igényelt dátum** mezőben látható. A dátumot abban a mezőben ugyanolyan sorrendben kell összehasonlítani a munkarendelésen vagy a munkarendelési feladaton szereplő dátummal, mint a beszerzési rendelés dátumát.


## <a name="create-a-purchase-order-from-a-work-order"></a>Beszerzési rendelés létrehozása munkarendelésből

Az **Összes munkarendelés** listaoldalon kiválaszthatja a munkarendelési feladatot, majd létrehozhat egy kapcsolódó beszerzési rendelést vagy beszerzési igénylést. Így biztosíthatja a projekt kapcsolatát a beszerzési rendelés vagy a beszerzési igénylés és a munkarendelés között.

1. Válassza az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** lehetőséget.

2. Válassza ki azt a munkarendelést, amelyhez beszerzési rendelést szeretne létrehozni, majd válassza a **Szerkesztés** parancsot.

3. A **Munkarendelés karbantartási feladatai** gyorslapon válassza ki azt a munkarendelési feladatot, amelyhez beszerzési rendelést szeretne létrehozni.

4. Válassza a **Cikkfeladatok** > **Beszerzési rendelés munkarendelési feladatból** elemet.

5. A **Projekt beszerzési rendelései** listaoldalon kattintson az **Új** gombra.

6. Hozza létre a beszerzési rendelést.

>[!NOTE]
>Kapcsolódó beszerzési igénylés létrehozásához hajtsa végre ugyanezeket a lépéseket. Ugyanakkor 4. lépésben válassza ki a **Cikkfeladatok** > **Beszerzési igénylés a munkarendelési feladatból** lehetőséget.


## <a name="project-relation-between-work-order-and-purchase-order-or-purchase-requisition"></a>A munkarendelés és a beszerzési rendelés vagy a beszerzési igénylés közötti projektkapcsolat

Egy beszerzési rendelés vagy egy beszerzési igénylés sora egy munkarendelési feladathoz kapcsolódik a munkarendelési projekten és a kapcsolódó projekttevékenység-számon. Amikor egy beszerzési rendelést vagy beszerzési igénylést munkarendelési feladatból hoz létre, a kapcsolódó projekttevékenység-számot meg kell adni. A projekttevékenység-száma automatikusan rákerül a beszerzési rendelésre vagy beszerzési igénylésre, ha a kapcsolódó munkarendelés csak olyan munkarendelési feladatokat tartalmaz, amelyek mindegyike ugyanazt a karbantartási feladattípust használja. Ha a munkarendelési feladatokhoz eltérő karbantartási feladattípusok tartoznak, manuálisan kell megadnia a projekttevékenység számát a beszerzési rendelésen vagy beszerzési igénylésen.

A beszerzési rendelési sorhoz kapcsolódó tevékenység számának megtekintéséhez vagy megadásához válassza ki a beszerzési rendelés rekordját a **Beszerzési rendelés** listaoldalon, majd a **Beszerzési rendelés** oszlopában válassza ki a beszerzési rendelés hivatkozását. A **Tevékenység száma** mező a **Sor részletei** gyorslap **Projekt** lapján található.

A lenti ábra egy példát mutat a **Beszerzési rendelés** oldalára, amelynek középpontjában a **Tevékenység száma** áll.

![3. ábra](media/10-work-orders.png)

Hasonlóan, a beszerzési igénylési sorhoz kapcsolódó tevékenység számának megtekintéséhez vagy megadásához válassza ki a beszerzési rendelés rekordját a **Beszerzési rendelés igénylése** listaoldalon, majd a **Beszerzési rendelés** oszlopában válassza ki a beszerzési rendelés hivatkozását. A **Tevékenység száma** mező a **Sor részletei** gyorslap **Projekt** lapján található.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]