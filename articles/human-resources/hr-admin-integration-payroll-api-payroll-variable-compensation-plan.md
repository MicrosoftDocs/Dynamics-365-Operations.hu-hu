---
title: Változó kompenzációs konstrukció bérlistája
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista változó kompenzációs konstrukció entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
author: marcelbf
ms.date: 06/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-15
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5dc096c08ed808f577c8cdc96ca84000a0b80679
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314401"
---
# <a name="payroll-variable-compensation-plan"></a>Változó kompenzációs konstrukció bérlistája

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Dynamics 365 Human Resources bérszámfejtési változó kompenzációs konstrukció entitását ismerteti.

### <a name="description"></a>Leírás

Ez az entitás biztosítja az alkalmazott adott beosztásához hozzárendelt változó kompenzációs konstrukciót.

Fizikai név: mshr_payrollvariablecompensationawardentity.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság</br>**Fizikai név**</br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Személyzeti szám**</br>mshr_personnelnumber</br>*Sztring* | Írásvédett</br>Szükséges |Az alkalmazott egyedi személyzeti száma.  |
| **Jutalom dátuma**</br>mshr_awarddate</br>*Dátum és idő eltolása* | Írásvédett</br>Szükséges | A jutalom dátuma. |
| **Jutalom típusa**</br>mshr_awardtype</br>*[mshr_HrmCompVarAwardEmplType beállításkészlet](hr-admin-integration-payroll-api-award-type.md)* | Írásvédett</br>Szükséges | A változó kompenzációs konstrukcióhoz meghatározott jutalomtípus. |
| **Pénznem**</br>mshr_unitcurrencycode</br>*Sztring* | Írásvédett </br>Szükséges |A változó kompenzációs konstrukcióhoz meghatározott pénznem.   |
| **Fix kompenzációs konstrukció azonosítója**</br>mshr_fixedplanid</br>*Sztring* | Írásvédett | A jutalom számításához alapként használt fix fizetési konstrukció. |
| **Egységérték**</br>mshr_awardamount</br>*Decimális* | Írásvédett | Az egység értéke |
| **Folyamat típusa**</br>mshr_processtype</br>*[mshr_hrmCompProcessType beállításkészlet](hr-admin-integration-payroll-api-process-type.md)* | Írásvédett | A folyamat típusa. |
| **Változó kompenzációs konstrukció típusa**</br>Sztring</br>*mshr_typeid* | Írásvédett | A változó kompenzációs konstrukció típusa. |
| **Változó kompenzációs konstrukció azonosítója**</br>Sztring</br>*mshr_planid* | Írásvédett | A változó kompenzációs konstrukció azonosítója. |
| **Elsődleges mező**</br>mshr_primaryfield</br>*GUID* | Írásvédett</br>Rendszer által előállított. | |
| **Alkalmazott azonosítója**</br>mshr_fk_employee_id_value</br>*GUID* | Írásvédett</br>Szükséges</br>Idegen kulcs: mshr_payrollemployeeentity entitáshoz tartozó mshr_Employee_id  | Alkalmazott azonosítója. |
| **Változó kompenzációs konstrukció bérlistájának entitása**</br>mshr_payrollvariablecompensationawardentityid</br>*GUID* | Szükséges</br>Rendszer által előállított | A kompenzációs konstrukció azonosítására szolgáló, rendszer által generált GUID-értéke. |


## <a name="example-query"></a>Példa lekérdezésre

**Kérelem**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollvariablecompensationawardentities?$filter=mshr_personnelnumber eq '000001'
```

**Válasz**

```json
{
    "mshr_personnelnumber": "000001",
    "mshr_awarddate": "2015-01-15T00:00:00Z",
    "mshr_awardtype": 200000000,
    "mshr_unitcurrencycode": "USD",
    "mshr_fixedplanid": "",
    "mshr_awardamount": 1,
    "mshr_processtype": 200000003,
    "mshr_typeid": "Bonus",
    "mshr_planid": "MgBonus",
    "mshr_primaryfield": "000001 | MgBonus | Bonus | 1/15/2015",
    "_mshr_fk_employee_id_value": "00000655-0000-0000-adff-004105000000",
    "mshr_payrollvariablecompensationawardentityid": "000001a1-0000-0000-adff-004105000000",
    "_mshr_fk_fixedcomp_id_value": null
}
```

## <a name="see-also"></a>Lásd még

[Bérlista-integrációs API bemutatása](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
