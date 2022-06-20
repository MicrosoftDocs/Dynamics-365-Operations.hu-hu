---
title: Hiba hozzáadása munkarendeléshez
description: Ez a témakör azt ismerteti, hogyan lehet hibaregisztrációkat hozzáadni az eszközkezelési munkarendelésekhez.
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
ms.openlocfilehash: 7905dcd4c29872ec2601359baefa78545140397c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857895"
---
# <a name="add-fault-to-work-order"></a>Hiba hozzáadása munkarendeléshez

[!include [banner](../../includes/banner.md)]



A lekérdezéstervezőben megadott hibák a munkarendeléshez hozzáadhatók. A munkarendelésen kijelölt eszköznek tartalmaznia kell egy vagy több hibarekorddal rendelkező eszköztípust. A szolgáltatásokról további tájékoztatásért lásd: [Hibakezelés](../setup-for-work-orders/fault-management.md).

1. Válassza az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** lehetőséget.

2. Válassza ki azt a munkarendelést, amelynek a hibaregisztrációját kívánja végezni, majd kattintson a művelet ablaktábla **Munkarendelés** lapján az **Eszköz** csoport **Eszközhiba** elemére.

3. A **Tünetek** gyorslapon válassza a **Sor hozzáadása** lehetőséget. A **Hiba** mezőben a sorrendben következő hibaszám automatikusan bekerül.

4. A **Hibatünet** mezőben válassza ki a megfelelő tünetet.

5. Válassza ki a megfelelő értékeket a **Hibaterület** és a **Hibatípus** mezőkben.

6. A **Hibadátum** mezőbe automatikusan az aktuális dátum kerül. Igény esetén más dátumot is megadhat.

7. A **Kiválasztott tünet oka** gyorslapon adja hozzá a probléma okát leíró sort.

8. A **Kiválasztott tünet orvoslása** gyorslapon adja hozzá a probléma lehetséges megoldását leíró sort.

9. Válassza a **Mentés** lehetőséget.

A következő ábrán egy hibaregisztráció példája látható.

![1. ábra](media/19-work-orders.png)


## <a name="view-asset-faults"></a>Eszközhibák megtekintése

Az **Eszközhibák** listán áttekintést kaphat az összes eszközön regisztrált hibáról.

Az **Eszközhibák** listaoldalon áttekintést kaphat az összes eszközön regisztrált hibáról. A lap megnyitásához kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközhiba** > **Eszközhibák** elemre.


## <a name="print-asset-fault-report"></a>Eszközhiba-jelentés nyomtatása

Az **Összes eszköz** listája lapon kinyomtathat egy eszközhiba-jelentést, amely minden hibaregisztrációt megjelenít, valamint a hibák statisztikáinak grafikus áttekintését is.

1. Válassza ki az **Eszközkezelés** > **Általános** > **Eszközök** > **Összes eszköz** lehetőséget.

2. Jelölje ki az eszközt amelyhez hibajelentést szeretne nyomtatni.

3. A Művelet ablaktábla **Általános** lapjának **Jelentések** csoportjában válassza az **Eszközhiba** elemet.

4. Egy adott időszak megadása vagy a hiba típusának kiválasztása.

5. A jelentés nyomtatásához válassza az **OK** lehetőséget.

>[!NOTE]
>Számos eszközre vagy eszköztípusra vonatkozó hibajelentést is kinyomtathat úgy, hogy ezt választja: **Eszközkezelés** > **Jelentések** > **Eszközök** > **Eszközhiba**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]