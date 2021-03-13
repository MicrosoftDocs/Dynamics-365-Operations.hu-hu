---
title: Fél kapcsolattartója
description: Ez a témakör a Fél kapcsolattartója entitást írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: 38f53d402ebe9f9f358281dd3996797a20923056
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125473"
---
# <a name="party-contact"></a>Fél kapcsolattartója

Ez a témakör a Fél kapcsolattartója entitást írja le a Dynamics 365 Human Resources rendszerhez.

Fizikai név: mshr_dirpartycontactentities

## <a name="description"></a>Leírás

Ez az entitás leírja a jelölt kapcsolattartási adatait, többek között a telefonszámát és e-mail-címét, valamint a közösségimédia-fiókjait.

## <a name="json-representation"></a>JSON-ábrázolás

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_type": Int,
    "mshr_countryregioncode": "String",
    "mshr_locator": "String",
    "mshr_locatorextension": "String",
    "mshr_purpose": "String",
    "mshr_ismobilephone": Int,
    "mshr_isinstantmessage": Int,
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "String",
    "mshr_dirpartycontactentityid": "String"
}
```

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Fél kapcsolattartójának entitásazonosítója**<br>mshr_dirpartycontactentityid<br>*Sztring* | Írásvédett<br>Szükséges | Az entitásrekord rendszer által generált egyedi azonosítója. |
| **Fél száma**<br>mshr_partynumber<br>*Sztring* | Olvasás/írás<br>Szükséges | A társított fél (személy) rekordjának azonosítója. |
| **Személyazonosító értéke**<br>_mshr_fk_person_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_dirpersonentityid / mshr_dirpersonentity | A fél (személy) entitásrekord rendszer által generált egyedi azonosítója. |
| **Helyazonosító**<br>mshr_locationid<br>*Sztring* | Olvasás/írás<br>Szükséges | A címrekord helyazonosítója. Beállítás egy mshr_logisticspostaladdresslocationcdsentity entitásban. |
| **Leírás**<br>mshr_description<br>*Sztring* | Olvasás/írás<br>Szükséges | A kapcsolattartó részleteinek leírása. |
| **Típus**<br>mshr_type<br>*mshr_logisticselectronicaddressmethodtype beállításkészlet* | Olvasás/írás<br>Szükséges | A kapcsolattartó részleteinek típusa. |
| **Ország/régió kódja**<br>mshr_countryregioncode<br>*Sztring* | Olvasás/írás<br>Választható | A címhez tartozó ország vagy régió megadása |
| **Lokátor**<br>mshr_locator<br>*Sztring* | Olvasás/írás<br>Választható | A kapcsolattartó adatai. Ha például a típus **E-mail-cím**, akkor ez a mező a jelölt e-mail-címét tartalmazza. |
| **Lokátor bővítménye**<br>mshr_locatorextension<br>*Sztring* | Olvasás/írás<br>Választható | A lokátor bővítménye. Ha például a típus **Telefon**, ez a tulajdonság a telefonszámmelléket tartalmazza. |
| **Mobil**<br>mshr_ismobile<br>*mshr_noyes beállításkészlet* | Olvasás/írás<br>Szükséges | Azt adja meg, hogy a telefon mobiltelefonszám-e. |
| **Azonnali üzenet**<br>mshr_isinstantmessage<br>*mshr_noyes beállításkészlet* | Olvasás/írás<br>Szükséges | Megadja, hogy a telefon engedélyezve van-e azonnali üzenetküldésre. |
| **Elsődleges**<br>mshr_isprimary<br>*mshr_noyes beállításkészlet* | Olvasás/írás<br>Szükséges | Meghatározza a kapcsolattartó típusának elsődleges kapcsolattartóját. Kapcsolattartó-típusonként csak egy elsődleges rekord lehet. |
| **Magánjellegű**<br>mshr_isprivate<br>*mshr_noyes beállításkészlet* | Olvasás/írás<br>Szükséges | Azt jelzi, hogy ez a cím a személy privát címe-e. |
| **Alkalmazás célja**<br>mshr_purpose<br>*Sztring* | Olvasás/írás<br>Választható | A kapcsolattartó céljának/szerepkörének leírása. |
| **Elsődleges mező**<br>mshr_primaryfield<br>*Sztring* | Írásvédett<br>Szükséges | Az entitásrekord elsődleges azonosítójaként használt mező. Fél számának, típusának, leírásának és lokátorának kombinációja. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre a Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

