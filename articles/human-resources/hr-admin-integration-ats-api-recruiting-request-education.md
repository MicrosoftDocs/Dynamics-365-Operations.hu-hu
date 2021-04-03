---
title: Toborzási kérelem – végzettség
description: Ez a témakör a Toborzási kérelem – végzettség entitást írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: efc5c4813f8abd869e8137052c4aeb356a930d0b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465966"
---
# <a name="recruiting-request-education"></a>Toborzási kérelem – végzettség

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Toborzási kérelem – végzettség entitást írja le a Dynamics 365 Human Resources rendszerhez.

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