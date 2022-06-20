---
title: Előzményadatok importálása az igény-előrejelzésekhez
description: Ahhoz, hogy pontos igény-előrejelzéseket kaphasson, cikkenként vagy cikkfelosztási kulcsonként kell rendelkeznie a korábbi igényadatokkal. Ez a cikk bemutatja, hogyan lehet az entitásokat használni a korábbi igényadatok bármely rendszerből történő importálására, így hosszabb ideig tart az igény-előrejelzési adatok előzményei.
author: t-benebo
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e36ea72322c31f7e0ea3377b474cd148d78bdd3d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877595"
---
# <a name="import-historical-data-for-demand-forecasts"></a>Előzményadatok importálása az igény-előrejelzésekhez

[!include [banner](../includes/banner.md)]

Az igény-előrejelzések pontosságának biztosítása érdekében minél több adatra van szükség a korábbi igényekről cikkenként vagy cikkfelosztási kulcsonként. Ha a korábbi igényadatok még nincsenek importálva, használja a **Korábbi külső igény** (ReqDemPlanHistoricalExternalDemandEntity) adatentitást a Dynamics 365 Supply Chain Management szolgáltatásban az importálásukhoz.

Az **Adatkezelés** munkaterületen megtekintheti az entitás összes mezőjének áttekintését.

1. Nyissa meg az **Adatkezelés** munkaterületet.
2. Válassza ki az **Adatentitások** mozaikot.
3. Keresse ki a **Korábbi külső igény** entitáslistáját.
4. Válassza ki a **Célmezők** lehetőséget. A következő entitásmezők kötelezőek: hely (**DeliveringSiteId**), dátum (**DemandDate**), mennyiség (**DemandQuantity**), továbbá vagy a cikkszám (**ItemNumber**), vagy a cikkfelosztási kulcs (**ProductAllocationKeyId**).

Az adatentitás használatához rendelkeznie kell egy olyan Microsoft Excel fájllal vagy CSV-fájllal, amely tartalmazza a korábbi igényadatokat. Az alábbi példa az adatok CSV-fájlból való importálását mutatja be.

Az adatok importálásával és az [adatok](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) importálás utáni tisztításával kapcsolatos további tudnivalókat lásd az Adatok importálása és exportálása – áttekintés és kapcsolódó cikkek.

Lásd még: [Statisztikai kiinduló előrejelzés létrehozása](generate-statistical-baseline-forecast.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]