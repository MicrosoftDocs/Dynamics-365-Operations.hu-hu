---
title: Szabadság típusa
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a szabadságtípus entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 5e64b533ad7be23060701e8826a25736a078b59d1ecf824bee0e2dd05c9c78f8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713102"
---
# <a name="leave-type"></a>Szabadság típusa

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a szabadságtípus entitást írja le a Dynamics 365 Human Resources rendszerhez.

### <a name="description"></a>Leírás

Ez az entitás az adott szabadságtípushoz nyújt információkat.

Fizikai név: mshr_essleavetypeentity.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság</br>**Fizikai név**</br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Szabadságtípus azonosítója**</br>mshr_leavetypeid</br>*Sztring* | Írásvédett | A szabadságtípus azonosítója. |
| **Leírás**</br>mshr_description</br>*Sztring* | Írásvédett | A szabadaságtípus leírása. |
| **Kategória**</br>mshr_category</br>*mshr_LeaveTypeCategory beállításkészlet* | Írásvédett | A szabadságtípus kategóriája. |
| **Az okkódot meg kell adni**</br>mshr_isreasoncoderequired</br>*mshr_NoYes beállításkészlet* | Írásvédett | Azt határozza meg, hogy kötelező-e okkódot megadni a szabadságtípushoz. |
| **Szabadságegység**</br>mshr_leaveamountunit</br>*mshr_LeaveAmountUnit beállításkészlet* | Írásvédett | Ennek a szabadságtípusnak az egysége. |
| **Fél nap engedélyezése**</br>mshr_enablehalfdaydefinition</br>*mshr_NoYes beállításkészlet* | Azt határozza meg, hogy engedélyezve van-e a fél nap a szabadságtípusnál. |
| **Adatterület azonosítója**</br>mshr_dataareaid_id</br>*Sztring* | Írásvédett | Megadja a jogi személyt (vállalatot). |
| **Szabadságtípus entitás**</br>mshr_essleavetypeentityid</br>*GUID* | Rendszer által előállított | A szabadságtípus egyedi azonosítására szolgáló, rendszer által generált GUID-értéke. |

## <a name="example-query"></a>Példa lekérdezésre

**Kérelem**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavetypeentities?$filter=mshr_leavetypeid eq 'PTO'
```

**Válasz**

```json
{
    "mshr_leavetypeid": "PTO",
    "mshr_description": "Paid time off",
    "mshr_category": 200000000,
    "mshr_isreasoncoderequired": 200000000,
    "mshr_leaveamountunit": 200000000,
    "mshr_enablehalfdaydefinition": 200000000,
    "mshr_dataareaid": "usmf",
    "mshr_essleavetypeentityid": "00000a6c-0000-0000-0000-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Lásd még

[Bérlista-integrációs API bemutatása](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
