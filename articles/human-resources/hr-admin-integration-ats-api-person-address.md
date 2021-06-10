---
title: Személy címe
description: Ez a témakör a Személy címe entitást írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: 14db209e420770234583add93fa72d086f1b5ea6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053779"
---
# <a name="person-address"></a>Személy címe

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Személy címe entitást írja le a Dynamics 365 Human Resources rendszerhez.

Fizikai név: mshr_hcmpersonaddressentities

## <a name="description"></a>Leírás

Ez az entitás a jelöltrekordok postai címeinek listáját tartalmazza.

## <a name="json-representation"></a>JSON-ábrázolás

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_roles": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmpersonaddressentityid": "Guid"
}
```

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Személy címe entitás azonosítója**<br>mshr_hcmpersonaddressentityid<br>*Sztring* | Írásvédett<br>Szükséges | Az entitásrekord rendszer által generált egyedi azonosítója. |
| **Fél száma**<br>mshr_partynumber<br>*Sztring* | Olvasás/írás<br>Szükséges | A társított fél (személy) rekordjának azonosítója. |
| **Személyazonosító értéke**<br>_mshr_fk_person_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_dirpersonentityid / mshr_dirpersonentity | A fél (személy) entitásrekord rendszer által generált egyedi azonosítója. |
| **Helyazonosító**<br>mshr_locationid<br>*Sztring* | Olvasás/írás<br>Szükséges | A címrekord helyazonosítója. Beállítás egy mshr_logisticspostaladdresslocationcdsentity entitásban. |
| **Leírás**<br>mshr_description<br>*Sztring* | Olvasás/írás<br>Szükséges | A jelölt címének leírása. |
| **Szerepkörök**<br>mshr_roles<br>*Sztring* | Olvasás/írás<br>Szükséges | A címhez hozzárendelt szerepkörök. Több szerepkört is hozzárendelhet. Minden szerepkört pontosvesszővel kell elválasztani egymástól. Az mshr_logisticslocationroleentity entitásban lévő érvényes értékek. |
| **Utca**<br>mshr_street<br>*Sztring* | Olvasás/írás<br>Választható | Utca, házszám. |
| **Város**<br>mshr_city<br>*Sztring* | Olvasás/írás<br>Választható | A címben szereplő város. Beállítás az mshr_logisticsaddresscityentity entitásban. |
| **Állami**<br>mshr_state<br>*Sztring* | Olvasás/írás<br>Választható | A címhez tartozó állam. Beállítás az mshr_logisticsaddressstateentity entitásban. |
| **Megye**<br>mshr_county<br>*Sztring* | Olvasás/írás<br>Választható | A címhez tartozó megye megadása. Beállítás az mshr_logisticsaddresscountyentity entitásban. |
| **Irányítószám**<br>mshr_zipcode<br>*Sztring* | Olvasás/írás<br>Választható | A címhez tartozó postai irányítószám. Beállítás az mshr_logisticsaddresspostalcodeentity entitásban. |
| **Ország/régió azonosítója**<br>mshr_countryregionid<br>*Sztring* | Olvasás/írás<br>Választható | A címhez tartozó ország vagy régió megadása |
| **Ország/régió azonosítójának értéke**<br>_mshr_fk_countriregion_id_value<br>*GUID* | Írásvédett<br>Választható<br>Idegen kulcs: mshr_logisticaddresscountryregionentityid / mshr_logisticsaddresscountryregionentity | A cím országának/régiójának rendszer által generált egyedi azonosítója. |
| **Elsődleges**<br>mshr_isprimary<br>*mshr_noyes beállításkészlet* | Olvasás/írás<br>Szükséges | Azt jelzi, hogy ez a cím-e a beállított szerepkörhöz tartozó személy elsődleges címe. |
| **Privát**<br>mshr_isprivate<br>*mshr_noyes beállításkészlet* | Olvasás/írás<br>Szükséges | Azt jelzi, hogy ez a cím a személy privát címe-e. |
| **Elsődleges mező**<br>mshr_primaryfield<br>*Sztring* | Írásvédett<br>Szükséges | Az entitásrekord elsődleges azonosítójaként használt mező. Fél száma és helyazonosító kombinációja. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre a Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]