---
title: Fix kompenzációs konstrukció bérlistája
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista fix kompenzációs konstrukció entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 85cfce6f626090adab422ea6c60fc0778fd1ac67
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021296"
---
# <a name="payroll-fixed-compensation-plan"></a>Fix kompenzációs konstrukció bérlistája

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista fix kompenzációs konstrukció entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Alkalmazott azonosítója**<br>mshr_fk_employee_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_payrollemployeeentity entitáshoz tartozó mshr_Employee_id  | Alkalmazott azonosítója |
| **Fizetési díjalap**<br>mshr_payrate<br>*Decimális* | Írásvédett<br>Szükséges | A fix kompenzációs konstrukcióban meghatározott fizetési díj. |
| **Tervazonosító**<br>mshr_planid<br>*Sztring* | Írásvédett<br>Szükséges |A kompenzációs konstrukciót adja meg.  |
| **Érvényesség kezdete**<br>mshr_validfrom<br>*Dátum és idő eltolása* |  Írásvédett<br>Szükséges |Az a dátum, amelytől az alkalmazott fix kompenzációja érvényes.  |
| **Fix kompenzációs konstrukció bérlistája entitás**<br>mshr_payrollfixedcompensationplanentityid<br>*GUID* | Szükséges<br>Rendszer által előállított | A kompenzációs konstrukció azonosítására szolgáló, rendszer által generált GUID-értéke. |
| **Fizetési gyakoriság**<br>mshr_payfrequency<br>*Sztring* | Írásvédett<br>Szükséges |Az alkalmazott fizetésének gyakorisága.  |
| **Érvényesség vége:**<br>mshr_validto<br>*Dátum és idő eltolása* | Írásvédett <br>Szükséges | Az a dátum, amelyig az alkalmazott fix kompenzációja érvényes. |
| **Beosztásazonosító**<br>mshr_positionid<br>*Sztring* | Írásvédett <br>Szükséges | Az alkalmazotthoz és a fix kompenzációs konstrukcióba való belépéshez társított pozícióazonosító. |
| **Pénznem**<br>mshr_currency<br>*Sztring* | Írásvédett <br>Szükséges |A fix kompenzációs konstrukcióhoz meghatározott pénznem   |
| **Személyzeti szám**<br>mshr_personnelnumber<br>*Sztring* | Írásvédett<br>Szükséges |Az alkalmazott egyedi személyzeti száma.  |

**Lekérdezés**

**Kérelem**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**Válasz**

```json
{
            "mshr_planid": "GradeC",
            "mshr_personnelnumber": "000041",
            "mshr_payrate": 75200,
            "mshr_positionid": "000276",
            "mshr_validfrom": "2011-04-05T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_payfrequency": "Annual",
            "mshr_currency": "USD",
            "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
            "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
            "_mshr_fk_payroll_id_value": null
}
```
