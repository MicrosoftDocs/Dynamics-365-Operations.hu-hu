---
title: Hiba hozzáadása munkarendeléshez
description: Ez a témakör azt mutatja be, hogyan lehet az Eszközkezelésben a munkarendelésekhez hibás regisztrációkat hozzáadni.
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c86973ca44d9113d14e180e27cc51343da5d2c0
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875698"
---
# <a name="add-fault-to-work-order"></a>Hiba hozzáadása munkarendeléshez

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


A lekérdezéstervezőben megadott hibák a munkarendeléshez adhatók hozzá. A munkarendelésen kiválasztott eszköznek tartalmaznia kell egy vagy több hibarekorddal rendelkező eszköztípust. További tájékoztatás a beállításról a [Hibakezelés](../setup-for-work-orders/fault-management.md) részben.

1. Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.

2. A listáról válassza ki azt a munkarendelést, amelynél hibaregisztrációt kíván végezni, majd kattintson az **Eszközhiba** elemre.

3. A **Tünetek** gyorslapon kattintson a **Sor hozzáadása** parancsra. A **Hiba** mezőben a sorrendben következő hibaszám automatikusan bekerül.

4. Válassza ki a megfelelő tünetet a **Hibatünet** mezőben.

5. Válassza ki a **Hibaterületet** és a **Hiba típusát**.

6. A **Hibadátum** mezőbe automatikusan az aktuális dátum kerül. Szükség esetén másik dátumot is kiválaszthat.

7. A **Kiválasztott tünet oka** gyorslapon adja hozzá a probléma okát leíró sort.

8. A **Kiválasztott tünet orvoslása** gyorslapon adja hozzá a probléma lehetséges megoldását leíró sort.

9. Kattintson a **Mentés** gombra.

![1. ábra](media/19-work-orders.png)


## <a name="view-asset-faults"></a>Eszközhibák megtekintése

Az **Eszközhibák** listán áttekintést kaphat az összes eszközön regisztrált hibáról.

Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközhiba** > **Eszközhibák** elemre.


## <a name="print-asset-fault-report"></a>Eszközhiba-jelentés nyomtatása

Az **Összes eszköz** listája lapon kinyomtathat egy eszközhiba-jelentést, amely minden hibaregisztrációt megjelenít, valamint a hibák statisztikáinak grafikus áttekintését is.

1. Kattintson az **Eszközkezelés** > **Általános** > **Eszközök** > **Összes eszköz** elemre.

2. Az **Eszközök** listáról válassza ki azt az eszközt, amelyhez hibajelentés szeretne nyomtatni.

3. Kattintson az **Általános** lap > **Jelentések szakasz** **Eszközhiba** elemére.

4. Egy adott időszak beszúrása vagy a hiba típusának kiválasztása.

5. A jelentés nyomtatásához kattintson az **OK** gombra.

>[!NOTE]
>Számos eszközre vagy eszköztípusra vonatkozó hibajelentést is ki lehet nyomtatni úgy, hogy ide kattint: **Eszközkezelés** > **Jelentések** > **Eszközök** > **Eszközhiba**.

