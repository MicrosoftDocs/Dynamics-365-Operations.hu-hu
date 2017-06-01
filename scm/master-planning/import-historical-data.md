---
title: "Előzményadatok importálása az igény-előrejelzésekhez"
description: "Ahhoz, hogy pontos igény-előrejelzéseket kaphasson, cikkenként vagy cikkfelosztási kulcsonként kell rendelkeznie a korábbi igényadatokkal. Ez a témakör azt ismerteti, hogy miként használhatja az adatentitásokat a korábbi igényadatok bármely rendszerből való importálására annak érdekében, hogy Ön több igény-előrejelzési adattal rendelkezhessen."
author: YuyuScheller
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 0d1e2b9a51c2d7a7c30c2458b7babf8ac5c08118
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="import-historical-data-for-demand-forecasts"></a>Előzményadatok importálása az igény-előrejelzésekhez

[!include[banner](../includes/banner.md)]

Az igény-előrejelzések pontosságának biztosítása érdekében minél több adatra van szükség a korábbi igényekről cikkenként vagy cikkfelosztási kulcsonként. Ha a korábbi igényadatok még nincsenek importálva, használja a **Korábbi külső igény** (ReqDemPlanHistoricalExternalDemandEntity) adatentitást a Microsoft Dynamics 365 for Operations szolgáltatásban az importálásukhoz.

Az **Adatkezelés** munkaterületen megtekintheti az entitás összes mezőjének áttekintését.

1. Nyissa meg az **Adatkezelés** munkaterületet.
2. Kattintson az **Adatentitások** mozaikra.
3. Keresse ki a **Korábbi külső igény** entitáslistáját.
4. Kattintson a **Célmezők** pontra. A következő entitásmezők kötelezőek: hely (**DeliveringSiteId**), dátum (**DemandDate**), mennyiség (**DemandQuantity**), továbbá vagy a cikkszám (**ItemNumber**), vagy a cikkfelosztási kulcs (**ProductAllocationKeyId**).

Az adatentitás használatához rendelkeznie kell egy olyan Microsoft Excel-fájllal vagy CSV-fájllal, amely tartalmazza a korábbi igényadatokat. Az alábbi példa az adatok CSV-fájlból való importálását mutatja be.

## <a name="example"></a>Példa

A következő fájlt példaként használhatja. Töltse le a [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast) fájlt. Ez a fájl a D0001 cikk korábbi igényadatait tartalmazza. Csak a következő kötelező mezők szerepelnek benne: hely, mennyiség és az igény dátuma.

1. Válassza ki azt a vállalatot, amelyikbe a korábbi igényadatokat importálni szeretné.
2. Nyissa meg az **Adatkezelés** munkaterületet.
3. Kattintson az **Importálás** mozaikra.
4. Adjon meg egy nevet az importálási projektnek, mint például a következőt: **A D0001 cikk korábbi igényének importálása**.
5. A **Forrásadatok formátuma** mezőben válassza ki az importált fájl formátumát. Ennél a példánál a HistoricalDemandData fájl importálásához jelölje be a **CSV** lehetőséget.
6. Az **Entitásnév** mezőben válassza a **Korábbi külső igény** lehetőséget.
7. Mentse a fájlt a számítógépre, majd töltse fel.
8. Kattintson az **Importálás** gombra.
9. A **Végrehajtás összefoglalása** lap automatikusan megnyílik. Ellenőrizze az importált adatokat a lapon.

A korábbi igényadatok importálása után létrehozhatja az igény-előrejelzést.

## <a name="see-also"></a>Lásd még

[Statisztikai kiinduló előrejelzés létrehozása](generate-statistical-baseline-forecast.md)

