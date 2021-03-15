---
title: Előzményadatok importálása az igény-előrejelzésekhez
description: Ahhoz, hogy pontos igény-előrejelzéseket kaphasson, cikkenként vagy cikkfelosztási kulcsonként kell rendelkeznie a korábbi igényadatokkal. Ez a témakör azt ismerteti, hogy miként használhatja az adatentitásokat a korábbi igényadatok bármely rendszerből való importálására annak érdekében, hogy Ön több igény-előrejelzési adattal rendelkezhessen.
author: roxanadiaconu
manager: tfehr
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6ba2e1a3a884d29bff491f914aa2d5f9ece2b84
ms.sourcegitcommit: 79621e667cd7f48ba3bdbf2731f6f33d8e9f57f6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/10/2021
ms.locfileid: "5154227"
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

Az adatok importálásával és az adatok importálás utáni tisztításával kapcsolatos további tudnivalókat lásd az [Adatimportálási és -exportálási feladatok áttekintése](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) és a kapcsolódó témakörökben.

## <a name="example"></a>Példa

A következő fájlt példaként használhatja. Töltse le a [HistoricalDemandData](https://docs.microsoft.com/dynamics/s-e/) fájlt. Ez a fájl a D0001 cikk korábbi igényadatait tartalmazza. Csak a következő kötelező mezők szerepelnek benne: hely, mennyiség és az igény dátuma.

1. Válassza ki azt a vállalatot, amelyikbe a korábbi igényadatokat importálni szeretné.
2. Nyissa meg az **Adatkezelés** munkaterületet.
3. Válassza ki az **Importálás** mozaikot.
4. Adjon meg egy nevet az importálási projektnek, mint például a következőt: **A D0001 cikk korábbi igényének importálása**.
5. A **Forrásadatok formátuma** mezőben válassza ki az importált fájl formátumát. Ennél a példánál a HistoricalDemandData fájl importálásához jelölje be a **CSV** lehetőséget.
6. Az **Entitásnév** mezőben válassza a **Korábbi külső igény** lehetőséget.
7. Mentse a fájlt a számítógépre, majd töltse fel.
8. Válassza az **Importálás** lehetőséget.
9. A **Végrehajtás összefoglalása** lap automatikusan megnyílik. Ellenőrizze az importált adatokat a lapon.

A korábbi igényadatok importálása után létrehozhatja az igény-előrejelzést.

## <a name="additional-resources"></a>További erőforrások

[Statisztikai kiinduló előrejelzés létrehozása](generate-statistical-baseline-forecast.md)  
[Adatimportálási és -exportálási feladatok áttekintése](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]