---
title: Minősítési szint
description: Ez a témakör a Minősítési szint entitást írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: a42fdc28c7c2b7127563be88bc3119abaa225fc662bd7017fc82843d73658215
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748081"
---
# <a name="rating-level"></a>Minősítési szint

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Minősítési szint entitást írja le a Dynamics 365 Human Resources rendszerhez.

Fizikai név: mshr_hcmratinglevelentity

## <a name="description"></a>Leírás

Ez az entitás biztosítja a szakértelemhez rendelkezésre álló minősítési szinteket. A minősítési szintek minden jogi személyre érvényesek.

## <a name="json-representation"></a>JSON-ábrázolás

```json
{
    "mshr_description": "String",
    "mshr_factor": Int,
    "mshr_note": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_ratingmodelentity_id_value": "Guid",
    "mshr_hcmratinglevelentityid": "Guid"
}
```

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Minősítési szint entitásazonosítója**<br>mshr_hcmratinglevelentityid<br>*GUID* | Írásvédett<br>Szükséges<br>Rendszer által előállított | A szint rendszer által generált egyedi azonosítója. |
| **Minősítési szint azonosítója**<br>mshr_ratinglevelid<br>*Sztring* | Olvasás/írás<br>Szükséges | A szint egyedi, felhasználó által olvasható azonosítója. |
| **Minősítési modell azonosítója**<br>mshr_ratingmodelid<br>*Sztring* | Olvasás/írás<br>Szükséges | Az a minősítési modell, amelyhez a minősítési szint tartozik. |
| **Minősítési modell entitásazonosítója**<br>_mshr_fk_ratingmodelentity_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_hcmratingmodelentityid / mshr_hcmratingmodelentity | Annak a minősítési modellnek a rendszer által generált azonosítója, amelyhez a minősítési szint tartozik. |
| **Leírás**<br>mshr_description<br>*Sztring* | Olvasás/írás<br>Szükséges | A minősítési szint leírása. |
| **Szorzó**<br>mshr_factor<br>*Egész* | Olvasás/írás<br>Szükséges | A minősítési szint tényezője. Amikor egyes elemeket különböző minősítési szintszámokkal vet össze, ezen tényező alapján normalizálhatja a pontszámokat. Az értéknek 0 és 9 közötti egész számnak kell lennie. |
| **Megjegyzés**<br>mshr_note<br>*Sztring* | Olvasás/írás<br>Választható | A minősítési szinthez kapcsolódó megjegyzések. |
| **Elsődleges mező**<br>mshr_primaryfield<br>*Sztring* | Írásvédett<br>Szükséges | Az entitásrekord azonosítójaként használandó mező. A minősítési szint azonosítójának és az értékelési modell azonosítójának kombinációja. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre a Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]