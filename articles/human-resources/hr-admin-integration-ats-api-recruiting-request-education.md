---
title: Toborzási kérelem – végzettség
description: Ez a témakör a toborzási kérelem végzettség entitását írja le Dynamics 365 Human Resources.
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
ms.openlocfilehash: bcdb5e2cc61ce551af21401ea34d8e85bc21fc6c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893845"
---
# <a name="recruiting-request-education"></a>Toborzási kérelem – végzettség


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a toborzási kérelem végzettség entitását írja le Dynamics 365 Human Resources.

Fizikai név: mshr_hcmrecruitingrequesteducationentity

### <a name="description"></a>Leírás

A RecruitingRequest dokumentumra vonatkozó végzettségi követelményeket írja le.

### <a name="json-representation"></a>JSON-ábrázolás

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_educationdisciplineid": "String",
    "mshr_educationdisciplinedescription": "String",
    "mshr_educationlevelid": "String",
    "mshr_educationleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequesteducationentityid": "Guid"
}
```

### <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Toborzási kérelem – végzettség entitás azonosítója**<br>mshr_hcmrecruitingrequesteducationentityid<br>*GUID* | Írásvédett<br>Szükséges | A Toborzási kérelem – végzettség rekord rendszer által generált egyedi azonosítója. |
| **Toborzási kérelem azonosítója**<br>mshr_recruitingrequestid<br>*Sztring* | Írás egyszer<br>Szükséges | A kapcsolódó toborzási kérelem felhasználó által olvasható egyedi azonosítója. |
| **Toborzási kérelem azonosítójának értéke**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmrecruitingrequestentityid / mshr_hcmrecruitingrequestentity | A kapcsolódó toborzási kérelem rendszer által generált egyedi azonosítója. |
| **Végzettségi szint azonosítója**<br>mshr_educationlevelid<br>*Sztring* | Írás egyszer<br>Szükséges | A szükséges végzettségi szint. |
| **Végzettségi szint azonosítójának értéke**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmeducationlevelentityid / mshr_hcmeducationlevelentity | A szükséges végzettségi szint rendszer által generált egyedi azonosítója. |
| **Végzettségi szint leírása**<br>mshr_educationleveldescription<br>*Sztring* | Írásvédett<br>Szükséges | A szakértelemhez szükséges szint leírása. |
| **Végzettség tantárgyazonosítója**<br>mshr_educationdisciplinedescription<br>*Sztring* | Írás egyszer<br>Szükséges | Tantárgyterület. |
| **Végzettség tantárgyazonosítójának értéke**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmeducationdisciplineentityid / mshr_hcmeducationdisciplineentity | A tantárgyterület rendszer által generált egyedi azonosítója. |
| **Tantárgy leírása**<br>mshr_educationdisciplinedescription<br>Sztring | Írásvédett<br>Szükséges | A tantárgyterület leírása. |
| **Adatterület azonosítója**<br>mshr_dataareaid<br>*Sztring* | Olvasás/írás<br>Választható | Megadja a jogi személyt (vállalatot).|
| **Adatterület azonosítójának értéke**<br>_mshr_dataareaid_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: cdm_companyid / cdm_company entitás | A jogi személyt (vállalatot) azonosító, rendszer által generált GUID-érték. |
| **Elsődleges mező**<br>mshr_primaryfield<br>*Sztring* | Írásvédett<br>Szükséges | A toborzási kérelem értékének, a végzettségi szint azonosítójának és a tantárgyazonosítónak összefűzése alternatív módszerként a rekord egyedi azonosítására. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre Toborzási kérelemmel kapcsolatban](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
