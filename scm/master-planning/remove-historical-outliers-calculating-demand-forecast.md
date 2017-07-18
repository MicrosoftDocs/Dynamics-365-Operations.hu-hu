---
title: "Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor"
description: "Ez a cikk bemutatja, hogyan zárhatja ki a kiugró értékeket az igény-előrejelzés számítására szolgáló előzményadatokból. A kiugró értékek kizárásával, javíthatja az előrejelzés pontosságát."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 72735c9e3fb4291076f0b577f45384dec319b2a7
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017

---

# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a>Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor

[!include[banner](../includes/banner.md)]


Ez a cikk bemutatja, hogyan zárhatja ki a kiugró értékeket az igény-előrejelzés számítására szolgáló előzményadatokból. A kiugró értékek kizárásával, javíthatja az előrejelzés pontosságát.

A kiugró értékek kizárásával javíthatja az előrejelzés pontosságát. Ez a feladat nem kötelező. Itt következik egy áttekintés a folyamatról:

1.  Kattintson az **Alaptervezés** &gt; **Beállítások** &gt; **Igény-előrejelzés** &gt; **Kívülálló tételek eltávolítása** elemekre, hogy megnyissa a **Kívülálló tételek eltávolítása** lapot, ahol egy lekérdezés használatával kiválaszthatja a kizárandó tranzakciókat.
2.  Válassza ki a vállalatot, amelyre a lekérdezés vonatkozik, majd adjon meg egy nevet és leírást. A **Dátum lekérdezés** mező értéke automatikusan az aktuális dátum.
3.  Válasza ki az **Aktív** jelölőnégyzetet, hogy kizárja azokat a tranzakciókat, amiket a lekérdezés az előzményinformációkban talál. Ez a beállítás a kiinduló előrejelzés létrehozásakor lép érvénybe.
4.  Az **Lekérdezés kívülálló tételek eltávolításához** képernyőn hozzáadhat, eltávolíthat és kiválaszthat egyes feltételeket, amelyek meghatározzák a kiinduló előrejelzésből kizárandó tranzakciók körét. A kiválasztással kizárhat például egy adott cikket vagy rendelési tranzakciót.
5.  Kattintson a **Tranzakciók megjelenítése** elemre. Az **Kívülálló tranzakciók** lap felsorolja azokat a tranzakciókat, amelyek a lekérdezésben meghatározott feltételeknek megfelelnek, és ezért nem tartoznak bele az igény-előrejelzés számításakor használt előzményadatokba.

**Megjegyzés:** Létrehozhat egy lekérdezést, amely egy meglévő lekérdezésen alapul. Válassza ki azt a változót, amelyből másolni szeretne, és kattintson a **Másolás** elemre. A **Lekérdezés dátuma** mező azonosítja a verziót. Használhatja a lekérdezést úgy, ahogy van vagy rákattinthat a **Lekérdezés szerkesztése** gombra, hogy módosítsa a feltételeket. Az új lekérdezés neve és leírása tetszés szerint módosítható.

<a name="see-also"></a>Lásd még
--------

[Igény-előrejelzés – bevezetés](introduction-demand-forecasting.md)

[Az előrejelzés pontosság megfigyelése](monitor-forecast-accuracy.md)




