---
title: Toborzási kérelem – szakértelem
description: Ez a témakör a toborzási kérelem szakértelem-entitását írja le Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b17bbdfbc977112344302deada085681ceca9bb6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856396"
---
# <a name="recruiting-request-skill"></a>Toborzási kérelem – szakértelem


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a toborzási kérelem szakértelem-entitását írja le Dynamics 365 Human Resources.

Fizikai név: mshr_hcmrecruitingrequestskillentity

### <a name="description"></a>Leírás

A RecruitingRequest dokumentumra vonatkozó, szakértelemmel kapcsolatos követelményeket írja le.

### <a name="json-representation"></a>JSON-ábrázolás

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_skillid": "String",
    "mshr_skilldescription": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_ratingleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratingmodel_id_value": "Guid",
    "mshr_hcmrecruitingrequestskillentityid": "Guid"
}
```

### <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Toborzási kérelem – szakértelem entitás azonosítója**<br>mshr_hcmrecruitingrequestskillentityid<br>*GUID* | Írásvédett<br>Szükséges | A **Toborzási kérelem – szakértelem** rekord rendszer által generált egyedi azonosítója. |
| **Toborzási kérelem azonosítója**<br>mshr_recruitingrequestid<br>*Sztring* | Írás egyszer<br>Szükséges | A társított toborzási kérelem felhasználó által olvasható egyedi azonosítója. |
| **Toborzási kérelem azonosítójának értéke**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Írásvédett<br>Szükséges<br> Idegen kulcs: mshr_hcmrecruitingrequestentityid / mshr_hcmrecruitingrequestentity entitás | A társított toborzási kérelem rendszer által generált egyedi azonosítója. |
| **Szakértelem azonosítója**<br>mshr_skillid<br>*Sztring*<br> | Írás egyszer<br>Szükséges | A szükséges szakértelem felhasználó által olvasható egyedi azonosítója. |
| **Szakértelemazonosító értéke**<br>_mshr_fk_skill_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmskillentityid / mshr_hcmskillentity entitás | A szükséges szakértelem rendszer által generált egyedi azonosítója. |
| **Minősítési szint azonosítója**<br>mshr_ratinglevelid<br>*Sztring* | Írás egyszer<br>Választható | Az álláshoz kiválasztott szükséges szakértelem szintjének értéke a szakértelemhez rendelt minősítési modell alapján. |
| **Minősítési szint azonosítójának értéke**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: mshr_hcmratinglevelentityid / mshr_hcmratinglevelentity entitás | A szint rendszer által generált egyedi azonosítója. |
| **Szakértelem leírása**<br>mshr_skilldescription<br>*Sztring* | Írásvédett<br>Szükséges | A szakértelem leírása. |
| **Minősítési szint leírása**<br>mshr_ratingleveldescription<br>*Sztring* | Írásvédett<br>Választható | A kiválasztott szakértelmi szint leírása. |
| **Adatterület azonosítója**<br>mshr_dataareaid<br>*Sztring* | Olvasás/írás<br>Választható | Megadja a jogi személyt (vállalatot). |
| **Adatterület azonosítójának értéke**<br>_mshr_dataareaid_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: cdm_companyid / cdm_company entitás | A jogi személyt (vállalatot) azonosító, rendszer által generált GUID-érték. |
| **Elsődleges mező**<br>mshr_primaryfield<br>*Sztring* | Írásvédett<br>Szükséges | A toborzási kérelem értékének és a szakértelem azonosítójának összefűzése alternatív módszerként a rekord egyedi azonosítására. |
| **Minősítési modell azonosítója**<br>mshr_ratingmodelid<br>*Sztring* | Olvasás/írás<br>Szükséges | A szakértelem minősítésére használt minősítési modell. |
| **Minősítési modell azonosítójának értéke**<br>_mshr_fk_hcmratingmodel_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmratingmodelentityid / mshr_hcmratingmodelentity entitás | A szakértelem minősítésére használt minősítési modell rendszer által generált egyedi azonosítója. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre Toborzási kérelemmel kapcsolatban](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
