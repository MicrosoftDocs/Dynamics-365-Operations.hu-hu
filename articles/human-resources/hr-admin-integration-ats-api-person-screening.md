---
title: Személy szűrési adatai
description: Ez a témakör a Személy szűrése entitást mutatja be a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: c6287f30aaa008ea77b91fd46a8dfb2b7c905036
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467241"
---
# <a name="person-screening"></a>Személy szűrési adatai

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Személy szűrése entitást mutatja be a Dynamics 365 Human Resources rendszerben.

Fizikai név: mshr_hcmpersonscreeningentity

## <a name="description"></a>Leírás

Ez az entitás olyan szűréseket ír le, amelyeken a jelölt átment vagy amelyeken át kell mennie az állás betöltéséhez.

## <a name="json-representation"></a>JSON-ábrázolás

```json
{
    "mshr_note": "String",
    "mshr_requiredby": "Date",
    "mshr_status": Int,
    "mshr_partynumber": "String",
    "mshr_screeningtypeid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Személy szűrése entitás azonosítója**<br>mshr_hcmpersonscreeningentityid<br>*GUID* | Írásvédett<br>Szükséges<br>Rendszer által előállított | A személy szűrési rekordjának egyedi elsődleges azonosítója. |
| **Fél száma**<br>mshr_partynumber<br>*Sztring* | Olvasás/írás<br>Szükséges | A jelölthöz társított fél (személy) száma. |
| **Személyazonosító értéke**<br>_mshr_fk_person_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_dirpersonentityid / mshr_dirpersonentity | A fél (személy) entitásrekord rendszer által generált egyedi azonosítója. |
| **Szűréstípus azonosítója**<br>mshr_screeningtypeid<br>*Sztring* | Olvasás/írás<br>Szükséges<br>Idegen kulcs: ScreeningType | A Human Resources rendszerben definiált szűréstípus azonosítója. |
| **Szűréstípus azonosítójának értéke**<br>_mshr_fk_screeningtype_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmscreeningtypeentityid / mshr_hcmscreeningtypeentity | A társított entitás szűréstípusrekordjának rendszer által generált egyedi azonosítója. |
| **A következőig szükséges:**<br>mshr_requiredby<br>*Datetime* | Olvasás/írás<br>Választható | Az a dátum, amikorra a szűrést el kell végezni. |
| **Állapot**<br>mshr_status<br>*mshr_hcmcompletionstatus beállításkészlet*<br>Olvasás/írás<br>Szükséges | Megadja a jelölt állapotát a szűréshez. |
| **Befejezés dátuma**<br>mshr_completeddate<br>*Datetime* | Olvasás/írás<br>Választható | A szűrés befejezésének dátuma. |
| **Jegyzetek**<br>mshr_note<br>*Sztring* | Olvasás/írás<br>Választható | A toborzási vagy felvételi vezetők által használható megjegyzések. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre a Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]