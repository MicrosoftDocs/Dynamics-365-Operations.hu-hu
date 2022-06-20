---
title: Toborzási kérelem beosztása
description: Ez a témakör a Toborzási kérelem beosztás entitását írja le Dynamics 365 Human Resources.
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
ms.openlocfilehash: 0996532edf09ea5159e143d92fb2a93c4d6f826d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904246"
---
# <a name="recruiting-request-position"></a>Toborzási kérelem beosztása


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Toborzási kérelem beosztás entitását írja le Dynamics 365 Human Resources.

Fizikai név: mshr_hcmrecruitingrequestpositionentity

### <a name="description"></a>Leírás

A toborzási kérelemben bemutatott betöltendő beosztás(oka)t tartalmazza. A toborzási kérelemhez nem kötelező beosztást hozzáadni. A beosztás tulajdonságai csak olvashatók, mivel a beosztás tulajdonságai nem különbözhetnek a toborzási kérelemtől, mint amikor a beosztás törzsnyilvántartásában vannak. Ha a tulajdonságokat módosítani kell, akkor ezt a beosztás törzsnyilvántartása alapján kell megtenni, mielőtt hozzáadja a beosztást a toborzási kérelemhez.

### <a name="json-representation"></a>JSON-ábrázolás
```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_positionid": "String",
    "mshr_description": "String",
    "mshr_positiontypeid": "String",
    "mshr_status": Int,
    "mshr_departmentnumber": "String",
    "mshr_reportstopositionid": "String",
    "mshr_reportstopersonnelnumber": "String",
    "mshr_financialdimension": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_position_id_value": "Guid",
    "_mshr_fk_positiontype_id_value": "Guid",
    "_mshr_fk_department_id_value": "Guid",
    "_mshr_fk_reportstoposition_id_value": "Guid",
    "_mshr_fk_reportstoworker_id_value": "Guid",
    "mshr_hcmrecruitingrequestpositionentityid": "Guid"
}
```

### <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Toborzási kérelem – beosztás entitás azonosítója**<br>mshr_hcmrecruitingrequestpositionentityid<br>*GUID* | Írásvédett<br>Szükséges |    A toborzási kérelem beosztásrekordjának a rendszer által generált azonosítója. |
| **Toborzási kérelem azonosítója**<br>mshr_recruitingrequestid<br>*Sztring* | Írás egyszer<br>Szükséges | A toborzási kérelem felhasználó által olvasható egyedi azonosítója. |
| **Toborzási kérelem azonosítójának értéke**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmrecruitingrequestentityid / mshr_hcmrecruitingrequestentity entitás | A toborzási kérelem azon, a rendszer által generált azonosítója, amelyhez a beosztás hozzá van rendelve. |
| **Beosztásazonosító**<br>mshr_positionid<br>*Sztring* | Írás egyszer<br>Szükséges | A beosztás felhasználó által olvasható egyedi azonosítója. |
| **Beosztásazonosító értéke**<br>_mshr_fk_position_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmpositionv2entityid / mshr_hcmpositionv2entity entitás | A beosztás rendszer által generált azonosítója. |
| **Leírás**<br>mshr_description<br>*Sztring* | Írásvédett<br>Szükséges | A beosztás leírása. |
| **Beosztás típusának azonosítója**<br>mshr_positiontypeid<br>*Sztring* | Írásvédett<br>Választható | A beosztáshoz kapcsolódó beosztás típusának a felhasználó által olvasható egyedi azonosítója. |
| **Beosztástípus azonosítójának értéke**<br>_mshr_fk_positiontype_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: mshr_hcmpositiontypeentityid / mshr_hcmpositiontypeentity entitás | A beosztáshoz kapcsolódó beosztás típusának a rendszer által generált egyedi azonosítója. |
| **Állapot**<br>mshr_status<br>*RecruitingRequestPositionStatus* beállításkészlet | Olvasás/írás<br>Szükséges | A toborzási kérelem beosztásának állapota. |
| **Részleg száma**<br>mshr_departmentnumber<br>*Sztring* | Írásvédett<br>Választható<br> | A beosztás részlegének száma. |
| **Részlegazonosító értéke**<br>_mshr_fk_department_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: mshr_omdepartmententityid / mshr_omdepartmententity entitás | A beosztáshoz kapcsolódó részleg rendszer által generált egyedi azonosítója. |
| **Felettes beosztásazonosítója**<br>mshr_reportstopositionid<br>*Sztring* | Írásvédett<br>Szükséges | Annak a beosztásnak a felhasználó számára olvasható azonosítója, amelynek a toborzott beosztás a szervezeti hierarchiában jelent. |
| **Felettes beosztásazonosítójának értéke**<br>_mshr_fk_reportstoposition_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmpositionv2entityid / mshr_hcmpositionv2entity entitás | Annak a beosztásnak a rendszer által generált azonosítója, amelynek a toborzott beosztás jelent. |
| **Felettes személyzeti száma**<br>mshr_reportstopersonnelnumber<br>*Sztring* | Írásvédett<br>Szükséges | Annak a dolgozónak az azonosítója, akinek a felvett jelölt jelenteni fog. |
| **Felettes dolgozói azonosítójának értéke**<br>_mshr_fk_reportstoworker_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmworkerbaseentityid / mshr_hcmworkerbaseentity entitás | Annak a dolgozónak a rendszer által generált azonosítója, akinek a felvett jelölt jelenteni fog. |
| **Pénzügyi dimenzió**<br>mshr_financialdimension<br>*Sztring* | Írásvédett<br>Választható | A beosztáshoz rendelt pénzügyi dimenzió (például költséghely). A pénzügyi dimenzió jogi személyenként van hozzárendelve minden egyes beosztáshoz. A dimenziókban definiált költséghelyek az mshr_dimattributeomcostcenterentity entitáson keresztül érhetők el. |
| **Adatterület azonosítója**<br>mshr_dataareaid<br>*Sztring* | Olvasás/írás<br>Választható | Megadja a jogi személyt (vállalatot) a toborzási kérelem beosztásához. |
| **Adatterület azonosítójának értéke**<br>_mshr_dataareaid_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: cdm_companyid / cdm_company entitás | A toborzási kérelem beosztása mögött álló jogi személyt (vállalatot) azonosító, rendszer által generált GUID-érték. |
| **Elsődleges mező**<br>mshr_primaryfield<br>*Sztring* | Írásvédett<br>Szükséges | A toborzási kérelem értékének és a beosztás azonosítójának összefűzése alternatív módszerként a rekord egyedi azonosítására. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre Toborzási kérelemmel kapcsolatban](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
