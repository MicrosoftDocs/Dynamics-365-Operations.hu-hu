---
title: "Szállítói tranzakciók listája oldal"
description: "Ez a témakör a Microsoft Dynamics 365 for Finance and Operations a Szállítói tranzakció lista oldalát mutatja be."
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: 1ef7d97f059801f2fb2c0d451546b57055208f81
ms.contentlocale: hu-hu
ms.lasthandoff: 08/31/2018

---

# <a name="vendor-transaction-list-page"></a>Szállítói tranzakciók listája oldal

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Kiegyenlítések megjelenítése

A **Kiegyenlítések megjelenítése** a műveleti panelen gyorsan hozzáférhet a kiegyenlítési előzményekhez és a teljes kiegyenlítés tranzakció további adataihoz. További kapcsolódó tranzakciókat is megjeleníthet, amelyek kapcsolódna a kiválasztott tranzakcióhoz vagy azért, mert ugyanazon kiegyenlítés részei vagy azért, mert olyan fizetések, amelyeket ugyanazon fizetési naplóban hoztak létre.

1. Válassza a **Kötelezettségek \> Minden szállító** lehetőséget.
2. Válasszon ki egy szállítót, amelyekhez tranzakciók tartoznak, majd válassza a **Szállító \> Tranzakciók** lehetőséget.
3. Válasszon egy tranzakciót a kutatáshoz
4. Válassza ki a **Kiegyenlítések megjelenítése** lapot a műveleti panelen.

    A **Kiegyenlítések megjelenítése** párbeszédpanel megnyílik, és mutatja a kijelölt tranzakciót minden dokumentumot, amelyek ki lettek egyenlítve vele szemben. Ezen a párbeszédpanelen hasonlít a kiegyenlítési előzmények nézetre, de az összes kapcsolódó dokumentumot tartalmazza.

5. Ezen a párbeszédpanelen a különböző feladatok hajthatók végre. Válasszon ki egy vagy több bizonylatot majd, válassza ki az alábbi menük egyikét:

   - **Könyvelés megtekintése** – A kiválasztott dokumentumhoz kapcsolódó összes bizonylat megtekintése. A **Bezárás** gombbal zárja be a párbeszédpanelt.
   - **Exportálás** – A kijelölt bizonylatok exportálása az Microsoft Excelbe.
   - **Kapcsolódó fizetések megtekintése** – a fizetési napló összes tranzakciója jelenik meg, amely a kifizetési naplóban lett létrehozva és kapcsolódik a dokumentumhoz. Ezenkívül ezek a kifizetésekhez kapcsolódó valamennyi kiegyenlítés jelenik meg. A menü címkéje is módosul: **Kiegyenlítések megjelenítése**. Válassza a **Kiegyenlítések megjelenítése** lehetőséget hogy csak azokat a tranzakciókat jelenítse meg, amelyek meg lettek jelenítve amikor először nyitotta meg a  **Kiegyenlítések megjelenítése** párbeszédpanelt.
    - **Tranzakciók kiegyenlítése** – Ez a menü jelenik meg, ha a kiválasztott eredeti dokumentum nem lett teljesen kiegyenlítve. Ha bejelöli ezt a **Tranzakciók kiegyenlítése** párbeszédpanel jelenik meg, ahol kiválaszthatja a tranzakciókat a kiegyenlítéshez.
    - **Kiegyenlítések visszavonása** – Ez a menü jelenik meg, ha a kiválasztott eredeti dokumentum teljesen ki lett egyenlítve. Ha kiválasztja a **Kiegyenlítések visszavonása** párbeszédpanel jelenik meg, ahol visszavonhatók a dokumentumhoz végrehajtott kiegyenlítések.

