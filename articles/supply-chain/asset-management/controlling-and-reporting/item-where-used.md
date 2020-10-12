---
title: Cikk használati helye
description: Ez a témakör azt mutatja be, hogyan lehet áttekintést kapni arról, hogy egy cikk hol van használva Eszközkezelésben.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetItemWhereUsed, EntAssetItemWhereUsedCalculate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bc78568e314c7cf83848ed2c39f9613d6ed638ba
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889625"
---
# <a name="item-where-used"></a>Cikk használati helye

[!include [banner](../../includes/banner.md)]

 

Egy adott cikkhez számítást készíthet, amely áttekintést nyújt arról, hogy hol volt használatban a cikk az Eszközkezelésben. Az eredmények megmutatják a kontextust, amelyben a cikk használva volt az élettartama során. A **Hol van az eszköz használva** lapot a fő Eszközkezelés menüből lehet megnyitni, és a következő oldalakról is elérhető:

- [Eszköz DBJ-k](../objects/object-BOM.md)

- [Pótalkatrészek az eszköztípus alapértelmezéseken](../setup-for-objects/object-types.md#spare-parts-on-the-asset-type-setup)

- [Karbantartásifeladat-típusok kategóriái és karbantartásifeladat-típusok, karbantartásifeladat-típusok változatai, karbantartási szakmák és karbantartási ellenőrző listák](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [Karbantartási előrejelzés](../work-orders/maintenance-forecasts.md)

- [Beszerzés](../work-orders/procurement.md)

- [Munkarendelés beszerzése](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a>Cikk használati helye számítás létrehozása

1. Kattintson az **Eszközkezelés** > **Lekérdezések** > **Cikk használati helye** elemre, és válassza ki a **Cikk használati helye** gombot a fent említett oldalak valamelyikén.

2. A **Cikk használati helye** párbeszédpanelen válassza ki, hogy melyik elemhez szeretné elvégezni a számítást **Cikk száma** mezőben.

3. A **Szint** mezőben megadhatja, hogy a cikksorok milyen részletesen jelenítsék meg a munkavégzési helyszíneket. 

    Ha például beszúrja az „1ö számot a mezőbe, és a többszintű munkavégzési helyszínszerkezete van, akkor a legfelső szinten jelenik megy egy munkavégzési helyszín minden sora. Ennek megfelelően a sorban szereplő kapcsolat/mennyiség az alacsonyabb szinten található munkavégzési helyszínekről összeadódhat. 
    
    Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely minden cikksort megjelenít az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.

4. Ha a számításban szerepeltetni szeretné a munkarendelés feladatokat, válassza az „Igen” beállítást a **Belefoglalás** szakaszban.

5. Kattintson az **OK** gombra az számítás indításához.

6. A **Cikk használati helye** lapon kattintson a megfelelő **Csoportosítási szempont...** gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez. A kiválasztott **Csoportosítási szempont…** ablaktáblacsoport gombjai ki vannak emelve. A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.

7. Ha meg szeretné jeleníteni a cikkel kapcsolatos dimenziókat, kattintson a **Dimenziók megjelenítése** lehetőségre majd válassza ki a megjelenítendő dimenziókat.

## <a name="example"></a>Példa

A lenti képernyőfotó egy példát mutat be, amely az „1000” cikkszám használatára vonatkozó Cikk használati helye számítást tartalmaz.

![Cikk használati helye számítás példája](media/12-controlling-and-reporting.png)

