--- 
title: "Egy cikk vagy egy alapanyag nyomon követése"
description: "Ez az eljárás bemutatja, hogy a cikk-követéssel, hogyan lehet azonosítani, hogy hol használtak vagy használnak egy adott cikket vagy nyersanyagot."
author: pjacobse
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria, InventTrackingItemIdLookup, InventBatchIdLookup, CustTable, SalesLine
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: pjacobse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d7eb282ddf9597385d6660a3fc0ef73f403ab898
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="trace-an-item-or-raw-material"></a>Egy cikk vagy egy alapanyag nyomon követése

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogy a cikk-követéssel, hogyan lehet azonosítani, hogy hol használtak vagy használnak egy adott cikket vagy nyersanyagot. Ezzel az eljárással azonosíthat egy cikket, visszakövetheti a forráshoz, majd onnan előre követheti a termelésen és a késztermék értékesítésén keresztül. A folyamat segítségével kivizsgálhatók az érintett ügyfelek és értékesítési rendelések, illetve még több minden más is. Ez az eljárás az USP2 bemutatócéget használja.


## <a name="trace-an-item-backwards-using-a-known-batch-number"></a>Egy cikk visszakövetése ismert kötegszám alapján
1. Ugrás a Készletgazdálkodás > Lekérdezések és jelentések > Nyomon követési dimenziók > Cikk-követés menüpontba.
2. A Cikkszám mezőben válassza ki a P9100 értéket.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Az Előrefelé vagy visszafelé mezőben válassza a „Visszafelé” lehetőséget.
5. A Kötegszám mezőben válassza a „mint-12-344-01” lehetőséget.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. Kattintson az OK gombra.

## <a name="identify-an-item-trace-it-forward-and-make-an-analysis"></a>Egy cikk azonosítása, előre irányuló követése és az elemzés végrehajtása
    * A fastruktúra felső csomópontja a kiválasztott cikk és köteg aktuális készletmennyiségét jelöli. Ki kell bontani a fastruktúra csomóit annak érdekében, hogy megtalálja azt a cikket, amelyen az előre irányuló követést végre kell hajtani.   
1. Bontsa ki a fastruktúrában „az alább leírt csomópontot, és válassza ki a legutóbbi csomópontot”.
    * Bontsa ki: „P9100 1 / 10 / mint-12-344-01 ● 2 hordó ● 7,00 gallon \P9100 ● Kitárolva ● 000072 Értékesítési rendelés ● 2015.12.22. ● -1 hordó ● -4,00 gallon ● Hely = 1, Raktár = 10, Kötegszám = -12-344-01 \P9100 ● B-000050 Termelés● 2015.09.12. ● 7 hordó ● 27,00 gallon ● Hely = 1, Raktár = 10, Kötegszám = -12-344-01 ● Társtermékek: P9101” és válassza ki azt a csomópontot.     
2. Bontsa ki a fastruktúrában „az alább leírt csomópontot, és válassza ki ezt a csomópontot”.
    * Kezdve az imént kijelölt csomóponttal bontsa ki a „M9103 ● B-000050 Termelési sor ● 2015.09.12. ●-160,00 kg ● Méret = 70, Szín = OK, Hely= 1, Raktár = 10, Kötegszám = App01” és válassza ki azt a csomópontot.  
3. Kattintson a Nyomkövetés csomópontból lehetőségre.
4. Kattintson az Előrefelé lehetőségre.
5. A Művelet panelen kattintson a Nyomkövetés elemre.
    * Számos nyomkövetési beállítás megtalálható, amelyek tájékoztatást nyújtanak a nyomkövetési cikk által érintett vevőkkel, és a kiszállított és a ki nem szállított cikkhez kapcsolódó értékesítési rendelésekkel kapcsolatban.   
6. Kattintson az Ügyfelek lehetőségre.
7. Zárja be a lapot.
8. A Művelet panelen kattintson a Nyomkövetés elemre.
9. Kattintson a Kiszállított értékesítési rendelések lehetőségre.
10. Zárja be a lapot.


