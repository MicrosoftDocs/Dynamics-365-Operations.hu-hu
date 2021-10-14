---
title: Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor
description: Ez a cikk bemutatja, hogyan zárhatja ki a kiugró értékeket az igény-előrejelzés számítására szolgáló előzményadatokból. A kiugró értékek kizárásával, javíthatja az előrejelzés pontosságát.
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup, ReqDemPlanOutlierQueryPreview
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc0826d3a0dd8ded19590867e9a8138bb772c89a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568639"
---
# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a>Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogyan zárhatja ki a kiugró értékeket az igény-előrejelzés számítására szolgáló előzményadatokból. A kiugró értékek kizárásával, javíthatja az előrejelzés pontosságát.

A kiugró értékek kizárásával javíthatja az előrejelzés pontosságát. Ez a feladat nem kötelező. Itt következik egy áttekintés a folyamatról:

1.  Kattintson az **Alaptervezés** &gt; **Beállítások** &gt; **Igény-előrejelzés** &gt; **Kívülálló tételek eltávolítása** elemekre, hogy megnyissa a **Kívülálló tételek eltávolítása** lapot, ahol egy lekérdezés használatával kiválaszthatja a kizárandó tranzakciókat.
2.  Válassza ki a vállalatot, amelyre a lekérdezés vonatkozik, majd adjon meg egy nevet és leírást. A **Dátum lekérdezés** mező értéke automatikusan az aktuális dátum.
3.  Válasza ki az **Aktív** jelölőnégyzetet, hogy kizárja azokat a tranzakciókat, amiket a lekérdezés az előzményinformációkban talál. Ez a beállítás a kiinduló előrejelzés létrehozásakor lép érvénybe.
4.  Az **Lekérdezés kívülálló tételek eltávolításához** képernyőn hozzáadhat, eltávolíthat és kiválaszthat egyes feltételeket, amelyek meghatározzák a kiinduló előrejelzésből kizárandó tranzakciók körét. A kiválasztással kizárhat például egy adott cikket vagy rendelési tranzakciót.
5.  Kattintson a **Tranzakciók megjelenítése** elemre. Az **Kívülálló tranzakciók** lap felsorolja azokat a tranzakciókat, amelyek a lekérdezésben meghatározott feltételeknek megfelelnek, és ezért nem tartoznak bele az igény-előrejelzés számításakor használt előzményadatokba.

**Megjegyzés:** Létrehozhat egy lekérdezést, amely egy meglévő lekérdezésen alapul. Válassza ki azt a változót, amelyből másolni szeretne, és kattintson a **Másolás** elemre. A **Lekérdezés dátuma** mező azonosítja a verziót. Használhatja a lekérdezést úgy, ahogy van vagy rákattinthat a **Lekérdezés szerkesztése** gombra, hogy módosítsa a feltételeket. Az új lekérdezés neve és leírása tetszés szerint módosítható.

## <a name="additional-resources"></a>További erőforrások

[Igény-előrejelzés áttekintése](introduction-demand-forecasting.md)

[Előrejelzés pontosságának követése](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]