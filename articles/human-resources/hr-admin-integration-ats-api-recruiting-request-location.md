---
title: Toborzási kérelem helye
description: Ez a témakör a Toborzási kérelem helye entitást írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: 9a3b47c76094adb6c601daf2f9583116255b0a99
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465942"
---
# <a name="recruiting-request-location"></a>Toborzási kérelem helye

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Toborzási kérelem helye entitást írja le a Dynamics 365 Human Resources rendszerhez.

Fizikai név: mshr_hcmrecruitingrequestlocationentity

### <a name="description"></a>Leírás

Azon helyek listája, amelyek olyan helyekként vannak meghatározva, ahol a felvett alkalmazottak a felvétel után dolgozni fognak. Ezek a helyek jogi személyeken belül vannak létrehozva.

### <a name="json-representation"></a>JSON-ábrázolás

```
{
    "mshr_recruitingrequestlocationid": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_telephone": "String",
    "mshr_email": "String",
    "mshr_internetaddress": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_dataareaid": "String",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmrecruitingrequestlocationentityid": "Guid"
}
```

### <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Helyazonosító**<br>mshr_locationid<br>*Sztring* | Írás egyszer<br>Szükséges | A toborzási hely felhasználó által olvasható, rendszer által generált egyedi azonosítója. |
| **Toborzási kérelem helye**<br>mshr_recruitingrequestlocationid<br>*Sztring* | Írás egyszer<br>Szükséges | A toborzási hely felhasználó által definiált egyedi azonosítója. |
| **Toborzási kérelem helye entitás azonosítója**<br>mshr_hcmrecruitingrequestlocationentityid<br>*GUID* | Írásvédett<br>Szükséges | A Toborzási kérelem helye rekord rendszer által generált egyedi azonosítója. |
| **Leírás**<br>mshr_description<br>*Sztring* | Olvasás/írás<br>Szükséges | A hely leírása |
| **Ország/régió azonosítója**<br>mshr_countryregionid<br>*Sztring* | Írásvédett<br>Választható | Megadja, hogy a jelölt melyik országban vagy régióban rendelkezik állampolgársággal. |
| **Ország/régió azonosítójának értéke**<br>_mshr_fk_countriregion_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: mshr_logisticaddresscountryregionentityid / mshr_logisticsaddresscountryregionentity | A cím országának/régiójának rendszer által generált egyedi azonosítója. |
| **Irányítószám**<br>mshr_zipcode<br>*Sztring* | Írásvédett<br>Választható | Irányítószám / postai kód. |
| **Utca**<br>mshr_street<br>*Sztring* | Írásvédett<br>Választható | Utca. |
| **Város**<br>mshr_city<br>*Sztring* | Írásvédett<br>Választható | Város . |
| **Állami**<br>mshr_state<br>*Sztring* | Írásvédett<br>Választható | Állam vagy tartomány. |
| **Megye**<br>mshr_county<br>*Sztring* | Írásvédett<br>Választható | Megye. |
| **Telefonszám**<br>mshr_telephone<br>*Sztring* | Olvasás/írás<br>Választható | A helyszín telefonszáma. |
| **E-mail-cím**<br>mshr_email<br>*Sztring* | Olvasás/írás<br>Választható | E-mail-cím. |
| **Internetcím**<br>mshr_internetaddress<br>*Sztring* | Olvasás/írás<br>Választható | A hely webhelyének URL-címe. |
| **Adatterület azonosítója**<br>mshr_dataareaid<br>*Sztring* | Olvasás/írás<br>Választható | Megadja a jogi személyt (vállalatot). |
| **Adatterület azonosítójának értéke**<br>_mshr_dataareaid_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: cdm_companyid / cdm_company entitás | A jogi személyt (vállalatot) azonosító, rendszer által generált GUID-érték. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre Toborzási kérelemmel kapcsolatban](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]