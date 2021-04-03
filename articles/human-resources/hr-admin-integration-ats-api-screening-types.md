---
title: Szűréstípusok
description: Ez a témakör a Szűréstípusok entitást mutatja be a Dynamics 365 Human Resources rendszerben.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d3a45d802ab6b574338a09e77d432357cb9df507
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465918"
---
# <a name="screening-types"></a>Szűréstípusok

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Szűréstípusok entitást mutatja be a Dynamics 365 Human Resources rendszerben.

Fizikai név: mshr_hcmscreeningtypeentity

## <a name="description"></a>Leírás

Ez az entitás leírja a vállalat által a foglalkoztatás előtti és a folyamatban lévő alkalmazotti szűrési folyamatokhoz beállított szűréstípusokat.

## <a name="json-representation"></a>JSON-ábrázolás

```json
{
    "mshr_description": "String",
    "mshr_frequencyunit": Int,
    "mshr_generatefrom": Int,
    "mshr_frequencyinterval": Int,
    "mshr_screeningtypeid": "String",
    "mshr_hcmscreeningtypeentityid": "Guid"
}
```

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Szűréstípus entitás azonosítója**<br>mshr_hcmscreeningtypeentityid<br>*GUID* | Írásvédett<br>Szükséges<br>Rendszer által előállított | A szűréstípus rekordjának egyedi elsődleges azonosítója. |
| **Szűréstípus azonosítója**<br>mshr_screeningtypeid<br>*Sztring* | Olvasás/írás<br>Szükséges | A szűréstípus felhasználó által meghatározott egyedi azonosítója. |
| **Leírás**<br>mshr_description<br>*Sztring* | Olvasás/írás<br>Szükséges | A szűrési típus leírása. |
| **Gyakoriság egysége**<br>mshr_frequencyunit<br>*mshr_hcmfrequencyunit beállításkészlet* | Olvasás/írás<br>Szükséges | Leírja, hogy milyen gyakorisággal kell végrehajtani a szűrést a hozzárendelt személy esetében. |
| **Létrehozás alapja**<br>mshr_generatefrom<br>*mshr_hcmfrequencygeneratefrom beállításkészlet* | Olvasás/írás<br>Szükséges | Ha a Gyakoriság értéke nem Csak egyszeri, akkor a GenerateFrom érték határozza meg azt a dátumot, amelytől ki kell számítani a következő szűrési eseményt. |
| **Gyakorisági intervallum**<br>mshr_frequencyinterval<br>*Egész* | Olvasás/írás<br>Szükséges | Ha a Gyakoriság értéke nem Csak egyszeri, meg kell határoznia egy intervallumot az egyes szűrési események közötti időegységekre. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre a Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]