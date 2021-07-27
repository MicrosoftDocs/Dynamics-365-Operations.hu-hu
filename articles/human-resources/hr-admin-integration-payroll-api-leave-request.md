---
title: Távozási kérelem
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a szabadságkérelmezési entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
author: marcelbf
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b7f5744265dd106f11e6ffe7334873e697a7ea13
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314399"
---
# <a name="leave-request"></a>Távozási kérelem

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a szabadságkérelmezési entitást írja le a Dynamics 365 Human Resources rendszerhez.

### <a name="description"></a>Leírás

Ez az entitás a szabadságkérelmezéshez nyújt információkat.

Fizikai név: mshr_essleaverequestentity.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság</br>**Fizikai név**</br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Kérelemazonosító**</br>mshr_requestid</br>*Sztring* | Írásvédett | A kérésazonosító. |
| **Szabadságtípus azonosítója**</br>mshr_leavetypeid</br>*Sztring* | Írásvédett | A szabadságtípus azonosítója. |
| **Dátum**</br>mshr_leavedate</br>*Dátum és idő eltolása* | Írásvédett | A szabadságra vonatkozó kérelem dátuma. |
| **Összeg**</br>mshr_amount</br>*Decimális* | Írásvédett | A szabadságkérés összege. |
| **Félnap típusa**</br>mshr_halfdaydefinition</br>*mshr_LeaveHalfDayDefinition beállításkészlet* | Írásvédett | A félnapos szabadság típusa. |
| **Megjegyzés**</br>mshr_comment</br>*Sztring* | Írásvédett | Megjegyzés a kéréshez. |
| **Állapot**</br>mshr_status</br>*mshr_status beállításkészlet* | Írásvédett | A kérelem állapota. |
| **Dátum**</br>mshr_requestdate</br>*Dátum és idő eltolása* | Írásvédett | A kérelem dátuma. |
| **Személyzeti szám**</br>mshr_personnelnumber</br>*Sztring* | Írásvédett | Az alkalmazott egyedi személyzeti száma. |
| **Okkód azonosítója**</br>mshr_reasoncodeid</br>*Sztring* | Írásvédett | Az okkód azonosítója. |
| **Adatterület azonosítója**</br>mshr_dataareaid</br>*Sztring* | Írásvédett | Megadja a jogi személyt (vállalatot). |
| **Elsődleges mező**</br>mshr_primaryfield</br>*GUID* | Írásvédett</br>Rendszer által előállított | |
| **Szabadság típusú entitás**</br>mshr_essleaverequestentityid</br>*GUID* | Rendszer által előállított | A szabadságkérelem egyedi azonosítására szolgáló, rendszer által generált GUID-értéke. |

## <a name="example-query"></a>Példa lekérdezésre

**Kérelem**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleaverequestentities?$filter=mshr_personnelnumber eq '000020'
```

**Válasz**

```json
{
    "mshr_requestid": "USMF-000001",
    "mshr_leavetype": "PTO",
    "mshr_leavedate": "2017-01-02T00:00:00Z",
    "mshr_amount": 8,
    "mshr_halfdaydefinition": 200000000,
    "mshr_comment": "Taking a week off to relax",
    "mshr_status": 200000009,
    "mshr_requestdate": "2017-07-31T00:00:00Z",
    "mshr_personnelnumber": "000020",
    "mshr_reasoncodeid": "",
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "USMF-000001 | PTO | 1/2/2017",
    "mshr_essleaverequestentityid": "000004dd-0000-0000-0f00-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Lásd még

[Bérlista-integrációs API bemutatása](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
