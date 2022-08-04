---
title: Munkarendelések és tárgyi eszközök
description: Ez a cikk bemutatja a munkarendeléseket és tárgyi eszközöket az Eszközkezelésben.
author: johanhoffmann
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ed83450592d85205743c9ff1aefd0e66e5d2b90c
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111988"
---
# <a name="work-orders-and-fixed-assets"></a>Munkarendelések és tárgyi eszközök

[!include [banner](../../includes/banner.md)]


Az Eszközkezelésben az eszközök kapcsolódhatnak tárgyi eszközökhöz, és ezekhez az eszközökhöz munkarendeléseket is létrehozhat. Ha használja ezt a funkciót, teljes áttekintést kaphat a tárgyi eszközökről, a kapcsolódó beruházási projektekről, **·** **valamint** a Projektvezetés és könyvelés, valamint a Pénzügy és műveletek modulok projektvezetési és könyvelési moduljaiban regisztrált beruházási projektek költségeiről.

>[!NOTE]
>A **Tárgyi eszköz száma** mező csak akkor van beállítva munkarendelési feladat projektjén, ha a munkarendelési feladat projektjén a kiválasztott projekttípus **Befektetés**.

Az alábbi ábra a **Projekt menedzsment és a könyvelés** modul egy beruházási projektje, valamint egy munkarendelési feladatprojekt közötti kapcsolatot mutatja.

![1. ábra](media/24-work-orders.png)

A következő eljárás az eszközök, munkarendelések, munkarendelés-feladatok projektjei és tárgyi eszközök közötti kapcsolatot írja le.

1. Egy tárgyi eszközhöz kapcsolódó eszközt hoz létre.

![2. ábra](media/25-work-orders.png)

2. A munkarendelési típusok beállítása során a **Munkarendelés-típusok** oldalon (**Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Munkarendelés-típusok**) létrehoz egy munkarendelési típust a befektetések kezelése céljából. Lásd még: [Munkarendelés-típusok ](../setup-for-work-orders/work-order-types.md).

![3. ábra](media/26-work-orders.png)

3. A munkarendelési projektcsoportok beállítása során a **Projektcsoport** lapon a **Munkarendelés projektbeállítása** oldalon (**Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Projektbeállítás** hivatkozáson) kapcsolatot hoz létre a befektetésekhez használt munkarendelés-típus és a befejtetésekhez létrehozott projektcsoport között a Projektvezetés és könyvelés modulban a **Projektcsoportok** oldalon a **Projektmenedzsment és könyvelés** modulban (**Projektvezetés és könyvelés** > **Beállítás** > **Feladás** > **Projektcsoportok**).

![4. ábra](media/27-work-orders.png)

4. Amikor egy tárgyieszköz-objektumhoz kapcsolódó munkarendelést hoz létre, kiválasztja a befektetések kezeléséhez használt munkarendelés-típust, például **Befektetés**.

5. A munkarendelés létrehozása után a létrejött munkarendelés-típus megjelenik az **Összes munkarendelés** oldalon.

![5. ábra](media/28-work-orders.png)

6. A Munkarendelés létrehozásakor a munkarendeléshez kapcsolódó projekt létrejön az **Összes projekt** oldalon a **Projektmenedzsment és könyvelés** modul modulban (**Projektmenedzsment és könyvelés** > **Projektek** > **Minden projekt**). Ha meg szeretné tekinteni a projekttel kapcsolatos adatokat, válassza ki a hivatkozást a **Projekt azonosítója** mezőben, az **Általános** lapon a **Sor részletei** gyorslapon a részletek nézetben az **Összes munkarendelés lapon** az **Eszközkezelés** modulban (**Eszközkezelés** > **Közös** > **Munkarendelések** > **Minden munkarendelés**).

![6. ábra](media/29-work-orders.png)

7. A tárgyi eszközhöz társított projektek áttekintésének megtekintéséhez válassza a **Tárgyi eszközök** > **Tárgyi eszközök** > **Tárgyi eszközök** elemet, majd a **Tárgyi eszköz száma** mezőben válassza ki a tárgyi eszköz hivatkozását a megnyitásához a részletek nézetben. Bontsa ki a lap jobb oldalán a **Kapcsolódó információk** ablaktáblát, és válassza ki a **Társított projektek** gyorslapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
