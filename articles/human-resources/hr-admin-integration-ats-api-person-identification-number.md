---
title: Személy személyazonosító száma
description: Ez a témakör a Személy személyazonosító száma entitást írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: 0991f5b2e17e64e23f78b346c451f7c43bc20378
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067151"
---
# <a name="person-identification-number"></a>Személy személyazonosító száma


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Személy személyazonosító száma entitást írja le a Dynamics 365 Human Resources rendszerhez.

Fizikai név: mshr_hcmpersonidentificationnumberentity

## <a name="description"></a>Leírás

Ez az entitás a jelölt személyazonosító számait írja le. Lehetővé teszi az API-felhasználó számára, hogy azonosítószámokat írjon a jelöltrekordba, például társadalombiztosítási számokat vagy útlevélszámokat. Az azonosítószámok a dolgozói rekordon jelennek meg, de a jelöltrekordon nem. Egy integráló alkalmazás beírhatja az értékeket a Human Resources-adatbázisba, de a számok nem jelennek meg a Human Resources alkalmazásban, amíg a jelölt dolgozói rekordja létre nem jön.

## <a name="json-representation"></a>JSON-ábrázolás

```json
{
    "mshr_entrytype": "String",
    "mshr_description": "String",
    "mshr_expirationdate": "Datetime",
    "mshr_isprimary": Int,
    "mshr_identificationnumber": "String",
    "mshr_partynumber": "String",
    "mshr_identificationtypeid": "String",
    "mshr_issuingagencyid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_issuingagency_id_value": "Guid",
    "_mshr_fk_identificationtype_id_value": "Guid",
    "mshr_hcmpersonidentificationnumberentityid": "Guid",
    "mshr_issueddate": "Datetime"
}
```

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Személy személyazonosító száma entitásazonosító**<br>mshr_hcmpersonidentificationnumberentityid<br>*GUID* | Írásvédett<br>Szükséges<br>Rendszer által előállított | A személyazonosító szám rekordjának egyedi elsődleges azonosítója. |
| **Bejegyzéstípus**<br>mshr_entrytype<br>*Sztring* | Olvasás/írás<br>Választható | Az azonosítószám bejegyzéstípusának hivatkozását lehetővé tévő szabad érték. |
| **Leírás**<br>mshr_description<br>*Sztring* | Olvasás/írás<br>Választható | Az azonosítószám leírása. |
| **Lejárat dátuma**<br>mshr_expirationdate<br>*Datetime* | Olvasás/írás<br>Választható | Az azonosítószám vagy a hozzá kapcsolódó dokumentum lejáratának dátuma. |
| **Elsődleges**<br>mshr_isprimary<br>*mshr_noyes beállításkészlet* | Olvasás/írás<br>Választható | Azt határozza meg, hogy az azonosítószám-e a személy elsődleges rekordja ezen azonosítási típus esetében. |
| **Azonosítószám**<br>mshr_identificationnumber<br>*Sztring* | Olvasás/írás<br>Szükséges | Az azonosítószám. |
| **Fél száma**<br>mshr_partynumber<br>*Sztring* | Olvasás/írás<br>Szükséges | Az azonosítószámmal rendelkező fél (személy) rekordjának egyedi azonosítója. |
| **Személyazonosító értéke**<br>_mshr_fk_person_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_dirpersonentityid / mshr_dirpersonentity entitás | A fél (személy) egyedi azonosítója. |
| **Azonosítótípus azonosítója**<br>mshr_identificationtypeid<br>*Sztring* | Olvasás/írás<br>Szükséges | Az azonosítószám típusa. |
| **Azonosítótípus azonosítójának értéke**<br>_mshr_fk_identificationtype_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmidentificationtypeentityid / mshr_hcmidentificationtypeentity entitás | Az azonosítótípus rendszer által generált egyedi azonosítója. |
| **Kibocsátó hatóság azonosítója**<br>mshr_issuingagencyid<br>*Sztring* | Olvasás/írás<br>Választható | Az azonosítószámot kiállító ügynökség vagy szervezet. |
| **Kibocsátó hatóság azonosítójának értéke**<br>_mshr_fk_issuingagency_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: mshr_hcmissuingagencyentityid / mshr_hcmissuingagencyentity entitás | Az azonosítószámot kibocsátó ügynökség rendszer által generált egyedi azonosítója. |
| **Elsődleges mező**<br>mshr_primaryfield<br>*Sztring* | Írásvédett<br>Szükséges | Az entitásrekord azonosítójaként használandó mező. A fél számának, az azonosítótípus azonosítójának és az azonosítószámnak a kombinációja. |
| **Kiadás dátuma**<br>mshr_issuedate<br>*Dátum* | Olvasás/írás<br>Választható | Az azonosítószám kibocsátásának dátuma. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre a Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
