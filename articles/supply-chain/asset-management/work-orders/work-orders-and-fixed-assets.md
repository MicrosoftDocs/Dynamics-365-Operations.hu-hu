---
title: Munkarendelések és tárgyi eszközök
description: Ez a témakör a munkarendeléseket és tárgyi eszközöket mutatja be az Eszközkezelésben.
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
ms.openlocfilehash: 95fe394d22f9fe81511c230a2cf7b8ddf00d896f
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250829"
---
# <a name="work-orders-and-fixed-assets"></a>Munkarendelések és tárgyi eszközök


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Az Eszközkezelésben az eszközök kapcsolódhatnak tárgyi eszközökhöz, és ezekhez az eszközökhöz munkarendeléseket is létrehozhat. A funkció használatával teljeskörű áttekintést kaphat a tárgyi eszközökről, kapcsolódó befektetési projektekről és a befektetési projekteken rügzített költségekről a **Projektvezetés és könyvelés** modulban és a **Tárgyi eszközök** modulban.

>[!NOTE]
>A **Tárgyi eszköz száma** mező csak akkor tölthető ki a munkarendelési feladat projektjén, ha a munkarendelési feladat projektjén a kiválasztott projekttípus „Befektetés”.

![1. ábra](media/24-work-orders.png)

A következő eljárás az eszközök, munkarendelések, munkarendelés-feladatok projektjei és tárgyi eszközök közötti kapcsolatot írja le.

1. A tárgyi eszközhöz kapcsolódó eszköz létrehozása az alábbi ábrán látható módon történik.

![2. ábra](media/25-work-orders.png)

2. A munkarendelési típusok beállítása során (**Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Munkarendelés-típusok**) létrehoz egy munkarendelési típust a befektetések kezelése céljából. Lásd még: [Munkarendelés-típusok ](../setup-for-work-orders/work-order-types.md).

![3. ábra](media/26-work-orders.png)

3. A munkarendelési projektcsoportok beállítása során (**Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Projektbeállítás** > **Projektcsoport** hivatkozáson) kapcsolatot hoz létre a befektetésekhez használt munkarendelés-típus és a befejtetésekhez létrehozott projektcsoport között a **Projektvezetés és könyvelés** modulban (**Projektvezetés és könyvelés** > **Beállítás** > **Feladás** > **Projektcsoportok**).

![4. ábra](media/27-work-orders.png)

4. Amikor egy tárgyieszköz-objektumhoz kapcsolódó munkarendelést hoz létre, kiválasztja a befektetések kezeléséhez használt munkarendelés-típust, például „Befektetés”.

5. A munkarendelés létrehozása után a létrejött munkarendelés-típus megjelenik az **Összes munkarendelés** pontban.

![5. ábra](media/28-work-orders.png)

6. A munkarendelés létrehozása után a munkarendeléshez kapcsolódó projekt létrejön a **Projektvezetés és könyvelés** > **Összes projekt** pontban. A projekttel kapcsolatos információkat a munkarendelésen található **Projektazonosító** hivatkozásra kattintva tekintheti meg (az **Eszközkezelés** pontban nyissa meg a munkarendelést részletes nézetben > **Sor részletei** gyorslap > **Általános** lap > **Projektazonosító** mező).

![6. ábra](media/29-work-orders.png)

7. A **Tárgyi eszközök** pontban láthatja az adott tárgyi eszközhöz társított projektek áttekintését (**Tárgyi eszközök** > **Tárgyi eszközök** > **Tárgyi eszközök** > kattintson a tárgyi eszközre a **Tárgyi eszköz száma** mezőben > tekintse meg a **Kapcsolódó információk** ablaktábla tartalmát > **Társított projektek** szakasz).

