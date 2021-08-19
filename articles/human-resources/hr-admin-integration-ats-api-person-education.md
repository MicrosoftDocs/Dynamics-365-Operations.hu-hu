---
title: Személy végzettsége
description: Ez a témakör a Személy végzettsége entitást írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: 5e24188674c7746794c0e531dea21aa9b7f57b3534d4b67298cad19b6bec2a53
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731367"
---
# <a name="person-education"></a>Személy végzettsége

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Személy végzettsége entitást írja le a Dynamics 365 Human Resources rendszerhez.

Fizikai név: mshr_hcmpersoneducationentity

## <a name="description"></a>Leírás

Ez az entitás tartalmazza a jelölt tanulmányi előzményeit. A végzettség ahhoz a személyrekordhoz kapcsolódik, amely lehetővé teszi, hogy a végzettség a jelölt rekordján kívül más szerepkörökhöz is társítva legyen (dolgozó, alvállalkozó stb.).

## <a name="json-representation"></a>JSON-ábrázolás

```json
{
    "mshr_creditbasis": Int,
    "mshr_creditscompleted": Decimal,
    "mshr_creditsearned": Decimal,
    "mshr_creditsneeded": Decimal,
    "mshr_description": "String",
    "mshr_duration": Decimal,
    "mshr_durationunit": Int,
    "mshr_educationdisciplineid": "String",
    "mshr_educationinstitutionid": "String",
    "mshr_educationlevelid": "String",
    "mshr_enddate": "Date",
    "mshr_gradepointaverage": Decimal,
    "mshr_gradescale": "String",
    "mshr_notes": "String",
    "mshr_secondaryemphasis": "String",
    "mshr_startdate": "Date",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_educationinstitution_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmpersoneducationentityid": "Guid"
}
```

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Személy végzettsége entitás azonosítója**<br>mshr_hcmpersoneducationentityid<br>*GUID* | Írásvédett<br>Szükséges | A személy végzettsége entitásrekord rendszer által generált egyedi azonosítója. |
| **Fél száma**<br>mshr_partynumber<br>*Sztring* | Olvasás/írás<br>Szükséges | A jelölt fél (személy) rekordjának egyedi azonosítója. |
| **Személyazonosító értéke**<br>_mshr_fk_person_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_dirpersonentityid / mshr_dirpersonentity | A jelölt személyi rekordjának rendszer által generált egyedi azonosítója. |
| **Tanulmányi pontszám alapja**<br>mshr_creditbasis<br>*mshr_hcmeducationcreditbasis beállításkészlet* | Olvasás/írás<br>Választható | A fokozat tanulmányi pontszámának alapja. |
| **Teljesített tanulmányi egységek**<br>mshr_creditscompleted<br>*Decimális* | Olvasás/írás<br>Választható | A végzettség során teljesített tanulmányi egységek száma. |
| **Megszerzett tanulmányi pontszám**<br>mshr_creditsearned<br>*Decimális* | Olvasás/írás<br>Választható | A folyamatban lévő fokozat végzettségrekordjában megszerzett tanulmányi pontszám. |
| **Szükséges pontszám**<br>mshr_creditsneeded<br>*Decimális* | Olvasás/írás<br>Választható | A folyamatban lévő fokozathoz szükséges pontszám. |
| **Leírás**<br>mshr_description<br>*Sztring* | Olvasás/írás<br>Választható | A jelölt fokozatának leírása. |
| **Végzettségi szint azonosítója**<br>mshr_educationlevelid<br>*Sztring* | Olvasás/írás<br>Választható | A végzettségi szint azonosítója. | 
| **Végzettségi szint értéke**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: mshr_hcmeducationdegreeentityid / mshr_hcmeducationdegreeentity entitás | A végzettségrekord rendszer által generált egyedi azonosítója. Ez az azonosító biztosítja a szervezethez meghatározott fokozatokat és végzettségi szinteket. |
| **Végzettség tantárgyazonosítója**<br>mshr_educationdisciplineid<br>*Sztring* | Olvasás/írás<br>Szükséges<br>Idegen kulcs: EducationDiscipline | A végzettség tantárgyazonosítója. |
| **Végzettség tantárgyazonosítójának értéke**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmeducationdisciplineentityid / mshr_hcmeducationdisciplineentity | A végzettség tantárgyhoz tartozó végzettségrekord rendszer által generált egyedi azonosítója. |
| **Másodlagos hangsúly**<br>mshr_secondaryemphasis<br>*Sztring* | Olvasás/írás<br>Választható | A megszerzett fokozat másodlagos hangsúlya. |
| **Oktatási intézmény azonosítója**<br>mshr_educationinstitutionid<br>*Sztring* | Olvasás/írás<br>Választható | Az oktatási intézmény azonosítója. |
| **Oktatási intézmény azonosítójának értéke**<br>_mshr_fk_educationinstitution_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: mshr_hcmeducationinstitutionentityid / mshr_hcmeducationinstitutionentity | Az oktatási intézmény rendszer által generált azonosítója. |
| **Kezdő dátum**<br>mshr_startdate<br>*Datetime* | Olvasás/írás<br>Választható | A megszerzett fokozat oktatásának kezdő dátuma. |
| **Záró dátum**<br>mshr_enddate<br>*Datetime* | Olvasás/írás<br>Szükséges | A fokozat kibocsátásának dátuma. |
| **Időtartam**<br>mshr_duration<br>*Decimális* | Olvasás/írás<br>Választható | A végzettségrekord időtartama. |
| **Időtartam egysége**<br>mshr_durationunit<br>*mshr_periodunit beállításkészlet* | Olvasás/írás<br>Választható | A végzettségrekord időtartamához kapcsolódó időegység. |
| **Osztályzatok átlaga**<br>mshr_gradepointaverage<br>*Decimális* | Olvasás/írás<br>Választható | A fokozathoz megszerzett osztályzatok átlaga. |
| **Osztályzatok skálája**<br>mshr_gradescale<br>*Sztring* | Olvasás/írás<br>Választható | Az osztályzatok átlagához használt skála. |
| **Jegyzetek**<br>mshr_notes<br>*Sztring* | Olvasás/írás<br>Választható | A toborzási vagy felvételi vezető által használható megjegyzések. |
| **Elsődleges mező**<br>mshr_primaryfield<br>*Sztring* | Írásvédett<br>Szükséges | Az entitásrekord egy másik elsődleges azonosítójaként használt mező. A fél számának, a tantárgyazonosítónak, az oktatási intézmény azonosítójának és a végzettségi szintnek a kombinációja. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre a Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]