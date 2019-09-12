---
title: Cikk használati helye
description: Ez a témakör azt mutatja be, hogyan lehet áttekintést kapni arról, hogy egy cikk hol van használva Eszközkezelésben.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.openlocfilehash: 84ab803aedf5b803b6c5f39ff1907726335cb45d
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918326"
---
# <a name="item-where-used"></a>Cikk használati helye

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Egy adott cikkhez számítást készíthet, amely áttekintést nyújt arról, hogy hol volt használatban a cikk az Eszközkezelésben. Az eredmények megmutatják a kontextust, amelyben a cikk használva volt az élettartama során. A **Hol van az eszköz használva** lapot a fő Eszközkezelés menüből lehet megnyitni, és a következő oldalakról is elérhető:

[Eszköz DBJ](../objects/object-BOM.md)

[Pótalkatrészek az eszköztípus alapértelmezéseken](../setup-for-objects/object-types.md)

[A karbantartási feladattípus alapértelmezett előrejelzések cikkekelőrejelzései](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

[Munkarendelés karbantartási előrejelzése](../work-orders/maintenance-forecasts.md)

[Munkarendelés beszerzési igénylése](../work-orders/procurement.md)

[Munkarendelés beszerzése](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a>Cikk használati helye számítás létrehozása

1. Kattintson az **Eszközkezelés** > **Lekérdezések** > **Cikk használati helye** elemre, és válassza ki a **Cikk használati helye** gombot a fent említett oldalak valamelyikén.

2. A **Cikk használati helye** párbeszédpanelen válassza ki, hogy melyik elemhez szeretné elvégezni a számítást **Cikk száma** mezőben.

3. A **Szint** mezőben megadhatja, hogy a cikksorok milyen részletesen jelenítsék meg a munkavégzési helyszíneket. Ha például beszúrja az „1ö számot a mezőbe, és a többszintű munkavégzési helyszínszerkezete van, akkor a legfelső szinten jelenik megy egy munkavégzési helyszín minden sora. Ennek megfelelően a sorban szereplő kapcsolat/mennyiség az alacsonyabb szinten található munkavégzési helyszínekről összeadódhat. Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely minden cikksort megjelenít az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.

4. Ha a számításban szerepeltetni szeretné a munkarendelés feladatokat, válassza az „Igen” beállítást a **Belefoglalás** szakaszban.

5. Kattintson az **OK** gombra az számítás indításához.

6. A **Cikk használati helye** lapon a **Csoportosítási szempont...** műveleti ablaktáblacsoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez. A kiválasztott műveleti ablaktábla gombjai ki vannak emelve. A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.

7. Ha meg szeretné jeleníteni a cikkel kapcsolatos dimenziókat, kattintson a **Dimenziók megjelenítése** lehetőségre majd válassza ki a megjelenítendő dimenziókat.

A lenti ábra egy példát mutat be, amely az „1000” cikkszám használatára vonatkozó Cikk használati helye számítást tartalmaz.

![1. ábra](media/12-controlling-and-reporting.png)

