---
title: Felveendő jelentkező
description: Ez a témakör azt a Felvenni kívánt jelöltentitást írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: f0ddf7bd403c926b231f9e010280083d1638b3ad
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795045"
---
# <a name="candidate-to-hire"></a>Felveendő jelentkező

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör azt a Felvenni kívánt jelöltentitást írja le a Dynamics 365 Human Resources rendszerhez.

Fizikai név: mshr_hcmcandidatetohireentity

## <a name="description"></a>Leírás

Ez az entitás tartalmazza egy dolgozó Dynamics 365 Human Resources rendszerben történő létrehozásához használt jelöltadatokat. Ezzel beolvassa a jelölt összes rekordját, valamint belső és külső jelöltrekordokat hoz létre, lehetővé téve, hogy személyes adatokat hozzon létre az új jelölt számára.

Amikor olyan külső jelöltrekordot hoz létre, amely a rendszerben új személyes rekord lesz, tilos nem adhatja meg a fél (személy) számát, ha új jelöltrekordot tesz közzé. Az új személyentitás-rekord az új jelöltrekorddal jön létre.

Belső jelöltrekord (a vállalatnál alkalmazotti rekorddal már rendelkező személy) létrehozása során meg kell határoznia annak a rekordnak a személyi számát, amely már létezik a mshr_partynumber jelöltrekordban az adott személlyel kapcsolatban, ahelyett, hogy megadja az új személyes rekord létrehozásához használt személyes adatokat (például név, nem vagy születési dátum).

## <a name="json-representation"></a>JSON-ábrázolás

```json
        {
            "mshr_candidateid": "String",
            "mshr_partynumber": "String",
            "mshr_partytype": "String",
            "mshr_recruitingrequestid": "String",
            "mshr_positionid": "String",
            "mshr_firstname": "String",
            "mshr_middlename": "String",
            "mshr_lastnameprefix": "String",
            "mshr_lastname": "String",
            "mshr_gender": Int,
            "mshr_birthdate": "Date",
            "mshr_citizenshipcountrycode": "String",
            "mshr_veteranstatusid": "String",
            "mshr_isdisabledveteran": Int,
            "mshr_availabilitydate": "Date",
            "mshr_iswillingtorelocate": Int,
            "mshr_comments": "String",
            "mshr_applicantintegrationresult": Int,
            "mshr_donothirereasoncodeid": "String",
            "mshr_dataareaid": "String",
            "_mshr_dataareaid_id_value": "Guid",
            "_mshr_fk_person_id_value": "Guid",
            "_mshr_fk_recruitingrequest_id_value": "Guid",
            "_mshr_fk_position_id_value": "Guid",
            "mshr_hcmcandidatetohireentityid": "Guid",
            "_mshr_fk_veteranstatus_id_value": "Guid",
            "_mshr_fk_reasoncode_id_value": "Guid",
            "mshr_militaryserviceenddate": "Guid",
            "mshr_militaryservicestartdate": "Guid"
        }
```

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Felvenni kívánt jelölt entitásazonosítója**<br>mshr_hcmcandidatetohireentityid<br>GUID | Írásvédett<br>Szükséges<br>Rendszer által előállított | Az entitásrekord rendszer által generált egyedi azonosítója. |
| **Jelölt azonosítója**<br>mshr_candidateid<br>Sztring | Írásvédett<br>Szükséges<br>Rendszer által előállított | Az entitás egyedi azonosítója. |
| **Fél száma**<br>mshr_partynumber<br>Sztring | Írásvédett<br>Szükséges | A jelölt személyes rekordjának személyes száma. |
| **Személyazonosító értéke**<br>_mshr_fk_person_id_value<br>GUID | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_dirpersonentityid / mshr_direpersonentity | A pályázó fél (személy) rekordjának rendszer által generált egyedi azonosítója. |
| **A fél típusa**<br>mshr_partytype<br>mshr_dirpartytype beállításkészlet | Írásvédett<br>Szükséges | A rekord típusa a fél vonatkozásában a mshr_dirpartytype beállításkészletében meghatározottak szerint. Ehhez az entitáshoz a típus mindig Személy lesz. |
| **Toborzási kérelem azonosítója**<br>mshr_recruitingrequestid<br>Sztring | Írás egyszer<br>Választható | A jelölt által teljesített toborzási kérelemre hivatkozik. |
| **Toborzási kérelem azonosítójának értéke**<br>_mshr_fk_recruitingrequest_id_value<br>GUID | Olvasás/írás<br>Választható<br>Idegen kulcs: mshr_hcmrecruitingrequestentityid / mshr_hcmrecruitingrequestentity | A jelölt által teljesített toborzási kérelem rendszer által generált egyedi azonosítója. |
| **Beosztásazonosító**<br>mshr_positionid<br>Sztring | Olvasás/írás<br>Választható | Annak a beosztásnak az azonosítója, amelyhez kapcsolódóan a jelöltet figyelembe veszik. |
| **Beosztásazonosító értéke**<br>_mshr_fk_position_if_value<br>GUID | Írásvédett<br>Választható<br>Idegen kulcs: mshr_hcmpositionv2entityid / mshr_hcmpositionv2entity | Azon beosztás rendszer által generált azonosítója, amelyhez kapcsolódóan a jelöltet figyelembe veszik. |
| **Utónév**<br>mshr_firstname<br>Sztring | Olvasás/írás<br>Szükséges | Pályázó utóneve. |
| **Második utónév**<br>mshr_middlename<br>Sztring | Olvasás/írás<br>Választható | Pályázó második neve. |
| **Vezetéknév előtagja**<br>mshr_lastnameprefix<br>Sztring | Olvasás/írás<br>Választható | Jelölt vezetéknevének előtagja. |
| **Vezetéknév**<br>mshr_lastname<br>Sztring | Olvasás/írás<br>Választható | Jelölt vezetékneve. |
| **Nem**<br>mshr_gender<br>mshr_hcmpersongender beállításkészlet | Olvasás/írás<br>Választható | A jelölt neme. |
| **Születési dátum**<br>mshr_birthdate<br>Dátum és idő | Olvasás/írás<br>Választható | A jelölt születési dátuma. |
| **Állampolgárság országkódja**<br>mshr_citizenshipcountrycode<br>Sztring | Olvasás/írás<br>Választható | Megadja, hogy a jelölt melyik országban rendelkezik állampolgársággal. Az érvényes országkódok a mshr_logisticaddresscountryregionentity pontban találhatók. |
| **Veteránállapot azonosítója**<br>mshr_veteranstatusid<br>Sztring | Olvasás/írás<br>Választható | Megadja a jelölt veteránállapotát. |
| **Veteránállapot azonosítójának értéke**<br>_mshr_fk_veteranstatus_id_value<br>GUID | Írásvédett<br>Választható<br>Idegen kulcs: mshr_hcmveteranstatusentityid / mshr_hcmveteranstatusentity | A veteránállapot entitásrekord rendszer által generált egyedi azonosítója. |
| **Katonai szolgálat kezdő dátuma**<br>mshr_militaryservicestartdate<br>Dátum és idő | Olvasás/írás<br>Választható | A jelölt katonai szolgálatának kezdő dátuma. |
| **Katonai szolgálat záró dátuma**<br>mshr_militaryserviceenddate<br>Dátum és idő | Olvasás/írás<br>Választható | A jelölt katonai szolgálatának záró dátuma. |
| **Rokkant veterán**<br>mshr_isdisabledveteran<br>mshr_noyes beállításkészlet | Olvasás/írás<br>Választható | Megadja, hogy a jelölt rokkant veterán-e. |
| **Elérhetőség dátuma**<br>mshr_availabilitydate<br>Dátum és idő | Olvasás/írás<br>Választható | A lehető legkorábbi dátum, amikor a jelölt munkába tud állni. |
| **Mobilis**<br>mshr_iswillingtorelocate<br>mshr_noyes beállításkészlet | Olvasás/írás<br>Választható | Azt jelzi, hogy a jelölt hajlandó-e költözni a beosztás betöltése érdekében. |
| **Megjegyzések**<br>mshr_comments<br>Sztring | Olvasás/írás<br>Választható | A toborzási vagy felvételi vezető által használandó megjegyzések. |
| **Alkalmazásintegrációs eredmény**<br>mshr_applcantintegrationresult<br>mshr_applicantintegrationresult beállításkészlet | Olvasás/írás<br>Szükséges | A jelölt állapota a toborzási folyamatban az integrációhoz kapcsolódóan. |
| **Nincs felvétel okkódazonosítója**<br>mshr_donothirereasoncodeid<br>Sztring | Olvasás/írás<br>Választható | Ha az állapot (alkalmazásintegrációs eredmény) beállítása Nincs felvétel, igény szerint okkódot adhat meg. |
| **Okkód azonosítójának értéke**<br>_mshr_fk_reasoncode_id_value<br>GUID | Írásvédett<br>Választható<br>Idegen kulcs: mshr_hcmreasoncodeentityid / mshr_hcmreasoncodeentity entitás | A **Nincs felvétel** okkód rendszer által generált egyedi azonosítója. |
| **Adatterület azonosítója**<br>mshr_dataareaid<br>Sztring | Olvasás/írás<br>Választható |  Megadja a jogi személyt (vállalatot). |
| **Adatterület azonosítójának értéke**<br>_mshr_dataareaid_id_value<br>GUID | Írásvédett<br>Választható<br>Idegen kulcs: cdm_companyid / cdm_company entitás | A jogi személyt (vállalatot) azonosító, rendszer által generált GUID-érték. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre a Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]