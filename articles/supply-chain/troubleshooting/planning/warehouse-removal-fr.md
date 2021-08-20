---
title: A Raktári igényelőrejelzés-dimenzió nem távolítható el az előrejelzési sorokból
description: A Raktári igényelőrejelzés-dimenzió nem távolítható el az előrejelzési sorokból.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 96af593d2e8a738258fe614f0f252620cb48c5f19eeb4425c9659ee6f9cd8c0c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741213"
---
# <a name="you-cant-remove-the-warehouse-demand-forecast-dimension-from-forecast-lines"></a>A Raktári igényelőrejelzés-dimenzió nem távolítható el az előrejelzési sorokból

Tudásbáziscikk száma: 4614408

## <a name="symptoms"></a>Tünetek

Ez a probléma akkor fordul elő, ha nincs hozzárendelve a **Raktár** dimenzió az **Igény-előrejelzési** laphoz az **Igény-előrejelzés paraméter** oldalon. Ettől függetlenül megjelenik a **Raktár** oszlop az **Igény-előrejelzés** oldalon(**Alaptervezés \> Előrejelzés \> Manuális előrejelzés entitás \> Igény-előrejelzés sorok**).

## <a name="resolution"></a>Felbontás

Az **Igény-előrejelzési paraméter** lap **Előrejelzési dimenziók** lapján megadott beállítások nincsenek hatással az **Igény-előrejelzés** lapra. A módosított igény-előrejelzésben generált és látható kiinduló előrejelzést szabályozzák. Nem ellenőrzik azonban a "valódi" igény-előrejelzéshez szükséges dimenziókat. Ha a **Módosított igény-előrejelzés** oldalon megjelenő rekordokat jóváhagyásával, akkor ezeket "valódi" előrejelzési bejegyzésekké konvertálhatja egy előrejelzési modellben. Ez a modell ezután használható az alaptervezésben.

Az **Igény-előrejelzés** lapon az igény-előrejelzési sorokban megjelenő "valódi" előrejelzés dimenziói részei a készletdimenzióknak. (Ez a viselkedés hasonlít az értékesítésirendelés-sorok viselkedésére.) Ha a rendszer nem úgy van beállítva, hogy kötelező készletdimenzióként használja a **Raktárat**, akkor az oszlop elrejtéséhez testreszabhatja az oldalt.
