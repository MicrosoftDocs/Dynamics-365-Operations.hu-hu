---
title: Kompenzáció - fizetés gyakorisága
description: Ez a cikk részletes adatokat és példa-lekérdezést nyújt a Kompenzációs fizetési gyakoriság entitáshoz a következőben:Dynamics 365 Human Resources
author: marcelbf
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9afe27776797b2355a32226bbd7fa514b5c5d962
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894614"
---
# <a name="compensation-pay-frequency"></a>Kompenzáció - fizetés gyakorisága


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör leírja a Kompenzáció - fizetési gyakoriság entitást a következőben:Dynamics 365 Human Resources

Fizikai név: mshr_hcmpayrateconversionentity.

### <a name="description"></a>Leírás

Ez az entitás az adott kompenzációs fizetési gyakoriságra vonatkozó fizetési díjalap-átalakításról ad információkat.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság</br>**Fizikai név**</br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Éves fizetési díjalap-átalakítás**</br>mshr_annualconversionfactor</br>*Decimális* | Írásvédett | A fizetési gyakoriság éves átváltási tényezője. |
| **Leírás**</br>mshr_description</br>*Sztring* | Írásvédett | Az átváltási árfolyam leírása. |
| **Órás fizetési díjalap-átalakítás**</br>mshr_hourlyconversionfactor</br>*Decimális* | Írásvédett | A fizetési gyakoriság óránkénti átváltási tényezője. |
| **Havi fizetési díjalap-átalakítás**</br>mshr_monthlyconversionfactor</br>*Decimális* | Írásvédett | A fizetési gyakoriság havi átváltási tényezője. |
| **Fizetési díjalap átalakítása**</br>mshr_payrateconversion</br>*Sztring* | Írásvédett | Az átváltási árfolyamot azonosító egyedi karakterlánc. |
| **Időszak**</br>mshr_period</br>*időszak-értékkészlet* | Írásvédett | Az adott fizetésidíjalap-átalakítás fő időszaka. |
| **Heti fizetési díjalap-átalakítás**</br>mshr_weeklyconversionfactor</br>*Decimális* | Írásvédett | A fizetési gyakoriság heti átváltási tényezője. |
| **Adatterület azonosítója**</br>mshr_dataareaid</br>*Sztring* | Írásvédett | A jogi személy (vállalat). |
| **Kompenzáció - fizetés gyakoriságának azonosítója**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | Rendszer által előállított | Rendszer által generált globálisan egyedi azonosító (GUID) érték, amely egyedileg azonosítja a rekordot. |

## <a name="example-query-for-payroll-employee"></a>Példa lekérdezés a bérszámfejtési alkalmazotthoz

**Kérelem**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_hcmpayrateconversionentities?$filter=mshr_payrateconversion eq 'Annual' and mshr_dataareaid eq 'usmf'
```

**Válasz**

```json
{
    "mshr_annualconversionfactor": 1,
    "mshr_description": "Annual",
    "mshr_hourlyconversionfactor": 0.0004807692,
    "mshr_monthlyconversionfactor": 0.0833333333,
    "mshr_payrateconversion": "Annual",
    "mshr_period": 200000000,
    "mshr_weeklyconversionfactor": 0.0192307692,
    "mshr_dataareaid": "usmf",
    "mshr_hcmpayrateconversionentityid": "0000056e-0000-0000-b027-fef003000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Lásd még

[Bérlista-integrációs API bemutatása](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
