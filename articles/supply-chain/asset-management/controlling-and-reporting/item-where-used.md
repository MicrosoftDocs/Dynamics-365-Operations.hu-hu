---
title: Cikk használati helye
description: Ez a témakör ismerteti, hogyan lehet áttekintést kapni arról, hogy hol használják az egyes cikkeket az Eszközkezelésben.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetItemWhereUsed, EntAssetItemWhereUsedCalculate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5232b7554f542fd183d3002e6d94ca49bfde06ec
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861015"
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

![Cikk használati helye számítás példája.](media/12-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]