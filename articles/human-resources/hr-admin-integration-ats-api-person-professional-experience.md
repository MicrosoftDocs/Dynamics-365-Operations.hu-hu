---
title: Személy szakmai tapasztalata
description: Ez a témakör a Személy szakmai tapasztalata entitást írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: 1defaff8397c41feedbd85893766106338a28941
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798057"
---
# <a name="person-professional-experience"></a>Személy szakmai tapasztalata

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Személy szakmai tapasztalata entitást írja le a Dynamics 365 Human Resources rendszerhez.

Fizikai név: mshr_hcmpersonprofessionalexperienceentity

## <a name="description"></a>Leírás

Ez az entitás a pályázó szakmai tapasztalatát vagy munkaelőzményét írja le.

## <a name="json-representation"></a>JSON-ábrázolás

```json
{
    "mshr_partynumber": "String",
    "mshr_employerposition": "String",
    "mshr_startdate": "Date",
    "mshr_allowcontactemployer": Int,
    "mshr_employerlocation": "String",
    "mshr_employername": "String",
    "mshr_enddate": "Date",
    "mshr_note": "String",
    "mshr_phone": "String",
    "mshr_url": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonprofessionalexperienceentityid": "Guid"
}
```

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Személy szakmai tapasztalata entitás azonosítója**<br>mshr_hcmpersonprofessionalexperienceentityid<br>*GUID* | Írásvédett<br>Szükséges | Az entitásrekord rendszer által generált egyedi azonosítója. |
| **Fél száma**<br>mshr_partynumber<br>*Sztring* | Olvasás/írás<br>Szükséges | A jelölt személyi rekordjának egyedi azonosítója. |
| **Személyazonosító értéke**<br>_mshr_fk_person_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_dirpersonentityid / mshr_dirpersonentity | A személyentitás-rekord rendszer által generált egyedi azonosítója. |
| **Munkáltatói pozíció**<br>mshr_employerposition<br>*Sztring* | Olvasás/írás<br>Szükséges | A jelölt pozíciója a foglalkoztatása alatt. |
| **Munkáltató neve**<br>mshr_employername<br>*Sztring* | Olvasás/írás<br>Szükséges | A munkáltató neve. |
| **Munkáltató helye**<br>mshr_employerlocation<br>*Sztring* | Olvasás/írás<br>Választható | A munkáltató helye. Maximális hossz: 60. Nincs konkrét meghatározott vagy kötelező formátum. |
| **Telefon**<br>mshr_phone<br>*Sztring* | Olvasás/írás<br>Választható | A munkáltató telefonszáma. |
| **URL-cím**<br>mshr_url<br>*Sztring* | Olvasás/írás<br>Választható | A munkáltató webhelyének URL-címe. |
| **Kezdő dátum**<br>mshr_startdate<br>*Datetime* | Olvasás/írás<br>Szükséges | A jelölt foglalkoztatásának kezdő dátuma. |
| **Záró dátum**<br>mshr_enddate<br>*Datetime* | Olvasás/írás<br>Választható | A jelölt foglalkoztatásának záró dátuma, vagy null, ha a jelölt továbbra is itt van alkalmazva. |
| **Munkáltatóval való kapcsolatfelvétel engedélyezése**<br>mshr_allowcontactemployer<br>*mshr_hrmblankyesno beállításkészlet* | Olvasás/írás<br>Választható | Jelzi, hogy a jelölt engedélyezi-e a korábbi munkáltatóval való kapcsolatfelvételt. |
| **Jegyzetek**<br>mshr_note<br>*Sztring* | Olvasás/írás<br>Választható | A toborzási vagy felvételi vezető által használható megjegyzések. |
| **Elsődleges mező**<br>mshr_primaryfield<br>*Sztring* | Írásvédett<br>Szükséges | Az entitásrekord elsődleges azonosítójaként használt mező. A fél számának, a kezdő dátumnak, a munkáltatói pozíciónak és a munkáltató nevének a kombinációja. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre a Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]