---
title: Bérlista beosztásokra vonatkozó részletei
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérszámfejtési részletek a beosztáshoz entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 7b23ac5d11b18c77109be21afe1570755dccba20
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019322"
---
# <a name="payroll-position"></a>Bérlista szerinti beosztás

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérszámfejtési részletek a beosztáshoz entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Éves rendes munkaidő**<br>annualregularhours<br>*Decimális* | Írásvédett<br>Szükséges | A beosztáshoz meghatározott éves rendszeres munkaidő.  |
| **Bérlista szerinti beosztás részletei entitás azonosítója**<br>payrollpositiondetailsentityid<br>*Guid* | Szükséges<br>Rendszer által előállított. | A pozíció egyedi azonosítására szolgáló, rendszer által generált GUID-értéke.  |
| **Elsődleges mező**<br>mshr_primaryfield<br>*Sztring* | Szükséges<br>Rendszer által előállított |  |
| **Beosztáshoz tartozó feladat azonosítójának értéke**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs:mshr_PayrollPositionJobEntity ehhez: mshr_payrollpositionjobentity |A pozícióhoz társított beosztás azonosítója.|
| **Fix kompenzációs konstrukció azonosítójának értéke**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_payrollfixedcompensationplanentity entitáshoz tartozó mshr_FixedCompPlan_id  | A pozícióhoz társított fix kompenzációs konstrukció azonosítója. |
| **Fizetési ciklus azonsítója**<br>mshr_primaryfield<br>*Sztring* | Írásvédett<br>Szükséges | A beosztáshoz meghatározott fizetési ciklus. |
| **Jogi személy által fizetett**<br>paidbylegalentity<br>*Sztring* | Írásvédett<br>Szükséges | A fizetés kiadásáért felelős beosztáshoz meghatározott jogi személy. |
| **Beosztásazonosító**<br>mshr_positionid<br>*Sztring* | Írásvédett<br>Szükséges | A pozíció azonosítója. |
| **Érvényesség vége:**<br>validto<br>*Dátum és idő eltolása* | Írásvédett<br>Szükséges |Az a dátum, amelytől a beosztás adatai érvényesek.  |
| **Érvényesség kezdete**<br>validfrom<br>*Dátum és idő eltolása* | Írásvédett<br>Szükséges |Az a dátum, ameddig a beosztás adatai érvényesek.  |

**Lekérdezés**

**Kérelem**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

**Válasz**

```json
{
            "mshr_positionid": "000276",
            "mshr_paycycleid": "w",
            "mshr_annualregularhours": 3000,
            "mshr_paidbylegalentity": "USMF",
            "mshr_validfrom": "2021-03-14T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_primaryfield": "000276 | 3/14/2021",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
            "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```
