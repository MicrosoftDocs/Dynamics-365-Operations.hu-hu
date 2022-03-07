---
title: Bérlista szerinti beosztás feladata
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista szerinti beosztás feladata entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 842c459acd8b5e1a8b6074243b3afa18dc6a13c5
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314237"
---
# <a name="payroll-position-job"></a>Bérlista szerinti beosztás feladata

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Dynamics 365 Human Resources Bérlistabeosztás feladatentitását írja le.

### <a name="description"></a>Leírás

Ez az entitás kapcsolatot biztosít egy adott fix kompenzációs konstrukcióhoz tartozó beosztás és feladat között.

Fizikai név: mshr_payrollpositionjobentity.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Beosztásazonosító**<br>mshr_jobid<br>*Sztring* | Írásvédett<br>Szükséges |A feladat azonosítója. |
| **Érvényesség kezdete**<br>mshr_validto<br>*Dátum és idő eltolása* | Írásvédett <br>Szükséges | Az a dátum, amelytől a beosztás és a feladat kapcsolata érvényes. |
| **Érvényesség vége:**<br>mshr_validto<br>*Dátum és idő eltolása* | Írásvédett <br>Szükséges | Az a dátum, ameddig a pozíció és a beosztás kapcsolata érvényes.  |
| **Beosztásazonosító**<br>mshr_positionid<br>*Sztring* | Írásvédett<br>Szükséges | A pozíció azonosítója. |
| **Elsődleges mező**<br>mshr_primaryfield<br>*Sztring* | Szükséges<br>Rendszer által előállított |  |
| **Beosztáshoz tartozó feladat azonosítójának értéke**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs:mshr_PayrollPositionJobEntity ehhez: mshr_payrollpositionjobentity |A pozícióhoz társított beosztás azonosítója.|
| **Fix kompenzációs konstrukció azonosítójának értéke**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_payrollfixedcompensationplanentity entitáshoz tartozó mshr_FixedCompPlan_id  | A pozícióhoz társított fix kompenzációs konstrukció azonosítója. |
| **Bérlista szerinti beosztás feladata azonosítója**<br>mshr_payrollpositionjobentityid<br>*Guid* | Szükséges<br>Rendszer által előállított. | A beosztás egyedi azonosítására szolgáló, rendszer által generált GUID-értéke.  |

## <a name="example-query"></a>Példa lekérdezésre

**Kérelem**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionjobentities?$filter=mshr_positionid eq '000276'
```

**Válasz**

```json
{
    "mshr_positionid": "000276",
    "mshr_validfrom": "2016-07-06T18:11:33Z",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_jobid": "Accountant",
    "mshr_primaryfield": "000276 | Accountant | 7/6/2016 06:11:33 pm",
    "_mshr_fk_jobdetail_id_value": "00000b8d-0000-0000-b0ff-004105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000058a-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": "00000427-0000-0000-df00-014105000000",
    "mshr_payrollpositionjobentityid": "00000906-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>Lásd még

[Bérlista-integrációs API bemutatása](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
