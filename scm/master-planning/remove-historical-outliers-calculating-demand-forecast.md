---
title: "Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor"
description: "Ez a cikk bemutatja, hogyan zárhatja ki a kiugró értékeket az igény-előrejelzés számítására szolgáló előzményadatokból. A kiugró értékek kizárásával, javíthatja az előrejelzés pontosságát."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 6f44e1ce566781f1586203528d55b13b28001a2c
ms.lasthandoff: 03/31/2017


---

# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a>Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor

Ez a cikk bemutatja, hogyan zárhatja ki a kiugró értékeket az igény-előrejelzés számítására szolgáló előzményadatokból. A kiugró értékek kizárásával, javíthatja az előrejelzés pontosságát.

Kizárhatja a kiugró előrejelzési pontosságának növelése érdekében. Ez a feladat nem kötelező. Itt következik egy áttekintés a folyamatról:

1.  Kattintson a **fő tervezési**&gt;**telepítő**&gt;**igény-előrejelzés**&gt;**ítélünk eltávolító** megnyitása a **ítélünk eltávolító** lap, ahol segítségével egy lekérdezést a kizárni kívánt tranzakcióinak kiválasztására.
2.  Válassza ki a vállalatot, amelyre a lekérdezés vonatkozik, majd adjon meg egy nevet és leírást. A **Dátum lekérdezés** mező értéke automatikusan az aktuális dátum.
3.  Válasza ki az **Aktív** jelölőnégyzetet, hogy kizárja azokat a tranzakciókat, amiket a lekérdezés az előzményinformációkban talál. Ez a beállítás a kiinduló előrejelzés létrehozásakor lép érvénybe.
4.  Az **Lekérdezés kívülálló tételek eltávolításához** képernyőn hozzáadhat, eltávolíthat és kiválaszthat egyes feltételeket, amelyek meghatározzák a kiinduló előrejelzésből kizárandó tranzakciók körét. A kiválasztással kizárhat például egy adott cikket vagy rendelési tranzakciót.
5.  Kattintson a **Tranzakciók megjelenítése** elemre. Az **Kívülálló tranzakciók** lap felsorolja azokat a tranzakciókat, amelyek a lekérdezésben meghatározott feltételeknek megfelelnek, és ezért nem tartoznak bele az igény-előrejelzés számításakor használt előzményadatokba.

**Megjegyzés:** Létrehozhat egy lekérdezést, amely egy meglévő lekérdezésen alapul. Válassza ki azt a változót, amelyből másolni szeretne, és kattintson a **Másolás** elemre. A **Lekérdezés dátuma** mező azonosítja a verziót. Használhatja a lekérdezést úgy, ahogy van vagy rákattinthat a **Lekérdezés szerkesztése** gombra, hogy módosítsa a feltételeket. Az új lekérdezés neve és leírása tetszés szerint módosítható.

<a name="see-also"></a>Lásd még
--------

[Introduction to demand forecasting](introduction-demand-forecasting.md)

[Monitoring forecast accuracy](monitor-forecast-accuracy.md)


