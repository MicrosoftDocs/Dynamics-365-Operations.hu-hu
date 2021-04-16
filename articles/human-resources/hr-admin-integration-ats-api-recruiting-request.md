---
title: Toborzási kérelem
description: Ez a témakör a Toborzási kérelem entitást írja le a Dynamics 365 Human Resources rendszerhez.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dd2f2fc74261c6eea3033567fe020c4e03c60637
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805178"
---
# <a name="recruiting-request"></a>Toborzási kérelem

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Toborzási kérelem entitást írja le a Dynamics 365 Human Resources rendszerhez.

Fizikai név: mshr_hcmrecruitingrequestentity

### <a name="description"></a>Leírás

Egy állásra való toborzásra vonatkozó kérelmet mutat be.

### <a name="json-representation"></a>JSON-ábrázolás

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_hiringmanagerpersonnelnumber": "String",
    "mshr_recruiterpartynumber": "String",
    "mshr_status": Int,
    "mshr_description": "String",
    "mshr_recruitingrequestlocationid": "String",
    "mshr_comments": "String",
    "mshr_jobid": "String",
    "mshr_titleid": "String",
    "mshr_jobfunctionid": "String",
    "mshr_defaultfulltimeequivalency": Decimal,
    "mshr_regulatoryjobcategory": Int,
    "mshr_jobtypeid": "String",
    "mshr_exemptstatus": Int,
    "mshr_estimatedstartdate": "Date",
    "mshr_externaldescription": "String",
    "mshr_compensationlevelid": "String",
    "mshr_compensationlowthreshold": Decimal,
    "mshr_compensationcontrolpoint": Decimal,
    "mshr_compensationhighthreshold": Decimal,
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "_mshr_fk_hiringmanager_id_value": "Guid",
    "_mshr_fk_recruiter_id_value": "Guid",
    "_mshr_fk_job_id_value": "Guid",
    "_mshr_fk_title_id_value": "Guid",
    "_mshr_fk_jobtype_id_value": "Guid",
    "_mshr_fk_compensationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequestentityid": "Guid",
    "_mshr_fk_recruitingrequestlocation_id_value": “Guid”
}
```

### <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Toborzási kérelem azonosítója**<br>mshr_recruitingrequestid<br>*Sztring* | Írásvédett<br>Szükséges<br>Rendszer által előállított | A HR-alkalmazásban megjelenített kérelem egyedi, felhasználó által olvasható azonosítója. Számsorozat. |
| **Toborzási kérelem entitásának azonosítója**<br>mshr_hcmrecruitingrequestentityid<br>*GUID* | Írásvédett<br>Szükséges<br>Rendszer által előállított | A toborzási kérelemegyedi azonosítására szolgáló, rendszer által generált GUID-értéke. |
| **Adatterület azonosítója**<br>mshr_dataareaid<br>*Sztring* | Olvasás/írás<br>Választható<br> | Megadja a jogi személyt (vállalatot) a toborzási kérelemhez. |
| **Adatterület azonosítójának értéke**<br>_mshr_dataareaid_id_value<br>*GUID*<br> | Írásvédett<br>Választható<br>Idegen kulcs: cdm_companyid / cdm_company entitás | A toborzási kérelem mögött álló jogi személyt (vállalatot) azonosító, rendszer által generált GUID-érték. |
| **Felvételi vezető személyzeti száma**<br>mshr_hiringmanagerpersonnelnumber<br>*Sztring* | Olvasás/írás<br>Választható | A toborzási kérelemhez társított felvételi vezető személyzeti száma. |
| **Felvételi vezető azonosítójának értéke**<br>_mshr_fk_hiringmanager_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: mshr_hcmworkerbaseentityid / mshr_hcmworkerbaseentity entitás | A toborzási kérelemhez társított vezető azonosítására szolgáló, a rendszer által generált GUID-érték. |
| **Toborzási fél száma**<br>mshr_recruiterpartynumber<br>*Sztring* | Olvasás/írás<br>Választható | A kérelemhez kiválasztott toborzó személyi (fél) száma. |
| **Toborzási azonosító értéke**<br>_mshr_fk_recruiter_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: mshr_dirpersonentityid / mshr_dirpersonentity entitás | A toborzási kérelemhez társított toborzó azonosítására szolgáló, a rendszer által generált GUID-érték. |
| **Állapot**<br>mshr_status<br>*RecruitingRequestStatus* beállításkészlet | Olvasás/írás<br>Szükséges<br> | Megadja a toborzási kérelem állapotát. |
| **Leírás**<br>mshr_description<br>*Sztring* | Olvasás/írás<br>Szükséges | Bemutatja a kérelmet. |
| **Toborzási kérelemhely azonosítója**<br>mshr_recruitingrequestlocationid<br>*Sztring* | Olvasás/írás<br>Választható | A kérelemhez társított állás helyének a felhasználó számára olvasható egyedi azonosítója. |
| **Toborzási hely azonosítójának értéke**<br>_mshr_fk_recruitinglocation_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: mshr_hcmrecruitingrequestlocationentityid / mshr_hcmrecruitingrequestlocationentity entitás | A toborzási kérelemhez kiválasztott hely azonosítására szolgáló, a rendszer által generált GUID-érték. |
| **Megjegyzések**<br>mshr_comments<br>*Sztring* | Olvasás/írás<br>Választható | A vezetők és toborzók által a kérelemmel kapcsolatban használható megjegyzések. |
| **Beosztásazonosító**<br>mshr_jobid<br>*Sztring* | Írás egyszer<br>Szükséges |   A kérelemhez társított összes pozícióval megosztott állásnak a felhasználó számára olvasható egyedi azonosítója. |
| **Állásazonosító értéke**<br>_mshr_fk_job_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmjobentityid / mshr_hcmjobentity entitás | A toborzási kérelemhez társított összes pozícióval megosztott állásnak a rendszer által generált egyedi azonosítója. |
| **Beosztásazonosító**<br>mshr_titleid<br>*Sztring* | Írásvédett<br>Szükséges | A kérelemhez társított beosztásnak a felhasználó számára olvasható egyedi azonosítója. |
| **Beosztásazonosító értéke**<br>_mshr_fk_title_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmtitleid / mshr_hcmtitleentity entitás | A toborzási kérelemhez kiválasztott állás beosztásának rendszer által generált egyedi azonosítója. |
| **Beosztás funkciójának azonosítója**<br>mshr_jobfunctionid<br>*Sztring* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_jobfunctionid / mshr_hcmjobfunctionentity entitás | A kérelemhez társított beosztáűs funkciójának a felhasználó számára olvasható egyedi azonosítója. |
| **Teljes munkaidős foglalkoztatással való egyenértékűség**<br>mshr_defaultfulltimeequivalency<br>*Dupla* | Írásvédett<br>Szükséges | Az állás teljes munkaidős beosztással egyenértékű értéke, ahol az 1,0 a teljes munkaidős dolgozót jelöli. |
| **Jogszabállyal kapcsolatos álláskategória**<br>mshr_regulatoryjobcategory<br>*RegulatoryJobCategory* beállításkészlet | Írásvédett<br>Választható | Az álláshoz kiválasztott beosztás funkciójának EEO-álláskategóriája. A HcmRegulatoryJobCatetory (mshr_hcmregulatoryjobcategory) beállításkészletben szereplő érvényes értékek. |
| **Feladattípus azonosítója**<br>mshr_jobtypeid<br>*Sztring* | Írásvédett<br>Választható | A pozícióhoz társított beosztás típusa. Az állástípusok a felhasználó által definiált értékek, amelyek a mshr_hcmjobtypeentity entitásban érhetők el. |
| **Állástípus azonosítójának értéke**<br>_mshr_fk_jobtype_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: mshr_hcmjobtypeentityid / mshr_hcmjobtypenentity entitás | A toborzási kérelemhez társított állástípus rendszer által generált egyedi azonosítója. |
| **Mentességi állapot**<br>mshr_exemptstatus<br>*JobExemptStatus* beállításkészlet | Írásvédett<br>Választható | Az FLSA-mentesség állapota az állás típusa alapján. |
| **Becsült kezdő dátum**<br>mshr_estimatedstartdate<br>*Dátum* | Olvasás/írás<br>Szükséges | Az a becsült dátum, amikor a jelölt dolgozni kezd. |
| **Külső leírás**<br>mshr_externaldescription<br>*Sztring* | Olvasás/írás<br>Választható | Az állás/beosztás jelölt által látható leírása. | 
| **Kompenzáció – alsó küszöb**<br>mshr_compensationlowthreshold<br>*Dupla* | Olvasás/írás<br>Választható | A kompenzációs szint alsó határa. |
| **Kompenzáció ellenőrzőpont**<br>mshr_compensationcontrolpoint<br>*Dupla* | Olvasás/írás<br>Választható | A kompenzációs szint ellenőrzőpontja. |
| **Kompenzáció – felső küszöb**<br>mshr_compensationhighthreshold<br>*Dupla* | Olvasás/írás<br>Választható | A kompenzációs szint felső határa. |
| **Kompenzációs szint**<br>mshr_compensationlevelid<br>*Sztring* | Olvasás/írás<br>Választható | Az állás kompenzációs szintje. Egy állás több kompenzációs szinttel is beállítható. Ez az attribútum a kérelemhez kiválasztott állás kompenzációs szintjét jelzi. |
| **Álláskompenzáció azonosítója**<br>_mshr_fk_jobcompensation_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: mshr_hcmjobcompensationentityid / mshr_hcmjobcompensationentity entitás | A toborzási kérelem beosztásához társított kompenzációs szint rendszer által generált egyedi azonosítója. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre Toborzási kérelemmel kapcsolatban](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
