---
title: Személy szakértelme
description: Ez a témakör a Személy szakértelme entitást írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: b6bcbbd1203f4e9e80f6c5264cf4d5ea7d0970fc
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126098"
---
# <a name="person-skill"></a>Személy szakértelme

Ez a témakör a Személy szakértelme entitást írja le a Dynamics 365 Human Resources rendszerhez.

Fizikai név: mshr_hcmpersonskillentity

## <a name="description"></a>Leírás

Ez az entitás bemutatja a jelölt szakértelmét.

## <a name="json-representation"></a>JSON-ábrázolás

```json
{
    "mshr_certifier": "String",
    "mshr_partynumber": "String",
    "mshr_levelid": "String",
    "mshr_ratinglevelexaminer": "String",
    "mshr_skillid": "String",
    "mshr_ratingid": "String",
    "mshr_leveltype": Int,
    "mshr_yearsofexperience": Decimal,
    "mshr_verified": Int,
    "mshr_leveldate": "Date",
    "mshr_primaryfield": "String",
    "_mshr_fk_certifier_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratinglevelexaminer_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "mshr_hcmpersonskillentityid": "Guid"
}
```

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Személy szakértelme entitás azonosítója**<br>mshr_hcmpersonskillentityid<br>*GUID* | Írásvédett<br>Szükséges | Az entitásrekord rendszer által generált egyedi azonosítója. |
| **Fél száma**<br>mshr_partynumber<br>*Sztring* | Olvasás/írás<br>Szükséges |   A társított fél (személy) rekordjának azonosítója. |
| **Személyazonosító értéke**<br>_mshr_fk_person_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_dirpersonentityid / mshr_dirpersonentity | A fél (személy) entitásrekord rendszer által generált egyedi azonosítója. |
| **Tanúsító**<br>mshr_certifier<br>*Sztring* | Olvasás/írás<br>Választható | Annak a dolgozónak a személyzeti száma, aki tanúsította ezt a szakértelemet. |
| **Tanúsító azonosítójának értéke**<br>_mshr_fk_certifier_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: mshr_hcmworkerentityid / mshr_hcmworkerentity | A szakértelmet tanúsító dolgozó dolgozói rekordjának rendszer által generált egyedi azonosítója. |
| **Szakértelem azonosítója**<br>mshr_skillid<br>*Sztring* | Olvasás/írás<br>Szükséges | A Human Resources rendszerben definiált szakértelem azonosítója. |
| **Szakértelemazonosító értéke**<br>_mshr_fk_skill_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmskillentityid / mshr_hcmskillentity | A kiválasztott szakértelem rendszer által generált azonosítója. |
| **Tapasztalat (év)**<br>mshr_yearsofexperience<br>*Decimális* | Olvasás/írás<br>Választható | A jelölt tapasztalata években az adott szakértelemre vonatkozóan. |
| **Minősítés azonosítója**<br>mshr_ratingid<br>*Sztring* | Olvasás/írás<br>Szükséges | A minősítési skála típusa. Ennél az entitásnál az érték **Szakértelem**. |
| **Szinttípus**<br>mshr_leveltype<br>*mshr_hrmskillleveltype beállításkészlet* | Olvasás/írás<br>Szükséges | A szakértelemhez rendelt szint típus szerinti kategorizálása. |
| **Szintazonosító**<br>mshr_levelid<br>*Sztring* | Olvasás/írás<br>Szükséges | A jelölt minősítési szintjének azonosítója ehhez a szakértelemhez. |
| **Minősítési szint azonosítójának értéke**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmratinglevelentityid / mshr_hcmratinglevelentity | A minősítési szint rendszer által generált azonosítója. |
| **Szint dátuma**<br>mshr_leveldate<br>*Datetime* | Olvasás/írás<br>Szükséges | A jelölt szakértelemhez kapcsolódó minősítésének dátuma. |
| **Minősítési szint vizsgálója**<br>mshr_ratinglevelexaminer<br>*Sztring* | Olvasás/írás<br>Választható | Annak a dolgozónak a személyzeti száma, aki a jelöltet minősítette. |
| **Minősítési szint vizsgálói azonosítójának értéke**<br>_mshr_fk_ratinglevelexaminer_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: mshr_hcmworkerentityid / mshr_hcmworkerentity | A jelölt szakértelmét vizsgáló dolgozó rendszer által generált azonosítója. |
| **Ellenőrizve**<br>mshr_verified<br>*mshr_noyes beállításkészlet* | Olvasás/írás<br>Szükséges | Jelzi, hogy a felmért szakértelem szintjét ellenőrizték. |
| **Elsődleges mező**<br>mshr_primaryfield<br>*Sztring* | Írásvédett<br>Szükséges | Az entitásrekord azonosítójaként használandó mező. A fél számának, a szinttípusnak, a szakértelem azonosítójának és a szint dátumának a kombinációja. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre a Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

