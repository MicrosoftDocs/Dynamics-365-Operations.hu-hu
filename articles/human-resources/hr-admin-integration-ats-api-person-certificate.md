---
title: Személy tanúsítványa
description: Ez a témakör a Személy tanúsítványa entitást írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: 5cdd742d6d36ccd7136f95e416507ed6e5e5a75a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055196"
---
# <a name="person-certificate"></a>Személy tanúsítványa

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Személy tanúsítványa entitást írja le a Dynamics 365 Human Resources rendszerhez.

Fizikai név: mshr_hcmpersoncertificateentity

## <a name="description"></a>Leírás

Ez az entitás a jelölt szakmai tanúsítványait írja le.

## <a name="json-representation"></a>JSON-ábrázolás

```json
{
    "mshr_certificatetypeid": "String",
    "mshr_startdate": "Date",
    "mshr_enddate": "Date",
    "mshr_notes": "String",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_certificatetype_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersoncertificateentityid": "Guid"
}
```

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Személy tanúsítványa entitás azonosítója**<br>mshr_hcmpersoncertificateentityid<br>*GUID* | Írásvédett<br>Szükséges | A személy tanúsítványa entitásrekord rendszer által generált egyedi azonosítója. |
| **Fél száma**<br>mshr_partynumber<br>*Sztring* | Olvasás/írás<br>Szükséges | A jelölt fél (személy) rekordjának azonosítója. |
| **Személyazonosító értéke**<br>_mshr_fk_person_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_dirpersonentityid / mshr_dirpersonentity | A fél (személy) entitásrekord rendszer által generált egyedi azonosítója. |
| **Tanúsítványtípus azonosítója**<br>mshr_certificatetypeid<br>*Sztring* | Olvasás/írás<br>Szükséges |  A Human Resources rendszerben definiált tanúsítványtípus azonosítója. |
| **Tanúsítványtípus azonosítójának értéke**<br>_mshr_fk_certificatetype_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmcertificatetypeentityid / mshr_hcmcertificatetypeentity | A társított entitás tanúsítványtípusának rendszer által generált egyedi azonosítója. |
| **Kezdő dátum**<br>mshr_startdate<br>*Datetime* | Olvasás/írás<br>Szükséges | A tanúsítvány kibocsátásának dátuma. |
| **Záró dátum**<br>mshr_enddate<br>*Datetime* | Olvasás/írás<br>Választható | A tanúsítvány lejáratának dátuma. |
| **Jegyzetek**<br>mshr_notes<br>*Sztring* | Olvasás/írás<br>Választható | A toborzási vagy felvételi vezetők által használható megjegyzések. |
| **Elsődleges mező**<br>mshr_primaryfield<br>*Sztring* | Írásvédett<br>Szükséges |  Az entitásrekord azonosítójaként használandó mező. A fél számának, a tanúsítványtípus azonosítójának és a kezdő dátumnak a kombinációja. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre a Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]