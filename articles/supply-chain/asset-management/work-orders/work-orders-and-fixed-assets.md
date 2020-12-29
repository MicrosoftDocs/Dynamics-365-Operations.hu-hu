---
title: Munkarendelések és tárgyi eszközök
description: Ez a témakör a munkarendeléseket és tárgyi eszközöket mutatja be az Eszközkezelésben.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ca7a5d88de4308d7be9c1bc749b9dbf1da027c2c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429727"
---
# <a name="work-orders-and-fixed-assets"></a>Munkarendelések és tárgyi eszközök

[!include [banner](../../includes/banner.md)]


Az Eszközkezelésben az eszközök kapcsolódhatnak tárgyi eszközökhöz, és ezekhez az eszközökhöz munkarendeléseket is létrehozhat. A funkció használatával teljeskörű áttekintést kaphat a tárgyi eszközökről, kapcsolódó befektetési projektekről és a befektetési projekteken rögzített költségekről a **Projektvezetés és könyvelés** modulokban és a **Tárgyi eszközök** modulokban a Microsoft Dynamics 365 for Finance and Operations szolgáltatásban.

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

