---
title: Szabadságegyenleg
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a szabadságegyenleg entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: ab136e9b40de280387dc3c5207a08a6bb357941feb3a8c736d9671f7850f2bf8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6782683"
---
# <a name="leave-balance"></a>Szabadságegyenleg

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a szabadságegyenleg entitást írja le a Dynamics 365 Human Resources rendszerhez.

### <a name="description"></a>Leírás

Ez az entitás biztosítja a szabadságegyenleget szabadságtípusonként egy adott alkalmazotthoz.

Fizikai név: mshr_essleavebalanceentities.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság</br>**Fizikai név**</br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Személyzeti szám**</br>mshr_personnelnumber</br>*Sztring* | Írásvédett | Az alkalmazott egyedi személyzeti száma. |
| **Aktuális egyenleg**</br>mshr_balanceavailable</br>*Decimális* | Írásvédett | Az alkalmazott aktuális egyenlege. |
| **Típus**</br>mshr_balanceavailable</br>*Sztring* | Írásvédett | A szabadságtípus azonosítója. |
| **Növekedési ráta**</br>mshr_accrualratedescription</br> | Írásvédett | Az elhatárolási ráta. |
| **Legutóbbi átvitel összege**</br>mshr_lastcarryforwardamount</br>*Decimális* | Írásvédett | Az utolsó átvitt mennyiség. |
| **Ebben az évben alkalmazott**</br>mshr_takenthisyear</br>*Decimális* | Írásvédett | Az idei évben kivett szabadság mennyisége. |
| **Idén összesen**</br>mshr_totalthisyear</br>*Decimális* | Írásvédett | A teljes mennyiség az idei évben. |
| **Adatterület azonosítója**</br>mshr_dataareaid_id</br>*Sztring* | Írásvédett | Megadja a jogi személyt (vállalatot). |
| **Elsődleges mező**</br>mshr_primaryfield</br>*GUID* | Írásvédett</br>Rendszer által előállított | |
| **Szabadságtípus azonosítója**</br>_mshr_fk_leavetype_id_value</br>*GUID* | Írásvédett</br>Idegen kulcs: az mshr_essleavetypeentity entitás mshr_essleavetypeentityid kulcsa  | Szabadságtípus azonosítója |
| **Szabadságegyenleg entitás**</br>mshr_essleavebalanceentityid</br>*GUID* | Rendszer által előállított | Az egyenleg egyedi azonosítására szolgáló, rendszer által generált GUID-értéke. |

## <a name="example-query"></a>Példa lekérdezésre

**Kérelem**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavebalanceentities?$filter=mshr_personnelnumber eq '000013'
```

**Válasz**

```json
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 67.76,
    "mshr_leavetypeid": "PTO",
    "mshr_accrualratedescription": "6.16 hrs / Semimonthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 67.76,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | PTO",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-0000-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-2703-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 80,
    "mshr_leavetypeid": "Sick",
    "mshr_accrualratedescription": "80.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 80,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Sick",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-ee02-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-3003-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 0,
    "mshr_leavetypeid": "Bereavement",
    "mshr_accrualratedescription": "0.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 0,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Bereavement",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f402-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-4403-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 66.65,
    "mshr_leavetypeid": "Vacation",
    "mshr_accrualratedescription": "13.33 hrs / Monthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 66.65,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Vacation",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f502-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-1009-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Lásd még

[Bérlista-integrációs API bemutatása](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
