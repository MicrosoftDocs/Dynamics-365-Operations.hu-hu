---
title: Bérlista beosztásokra vonatkozó részletei
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérszámfejtési részletek a beosztáshoz entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 2bbb234d2f51391ea65e3d6153d6cee250f3c6dc
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069807"
---
# <a name="payroll-position"></a>Bérlista szerinti beosztás


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Dynamics 365 Human Resources bérlistabeosztások entitását írja le.

Fizikai név: mshr_payrollpositionentity.

### <a name="description"></a>Leírás

Ez az entitás pozícióval kapcsolatos információkat biztosít az adott alkalmazotthoz.

Fizikai név: mshr_payrollpositionentity.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság</br>**Fizikai név**</br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Beosztásazonosító**</br>mshr_positionid</br>*Sztring* | Írásvédett | A pozíció azonosítója. |
| **Fizetési ciklus azonsítója**</br>mshr_paycycleid</br>*Sztring* | Írásvédett | A beosztáshoz meghatározott fizetési ciklus. |
| **Éves rendes munkaidő**</br>annualregularhours</br>*Decimális* | Írásvédett | A beosztáshoz meghatározott éves rendszeres munkaidő. |
| **Jogi személy által fizetett**</br>paidbylegalentity</br>*Sztring* | Írásvédett | A fizetés kiadásáért felelős beosztáshoz meghatározott jogi személy. |
| **Érvényesség vége:**</br>validto</br>*Dátum és idő eltolása* | Írásvédett | Az a dátum, ameddig a beosztás adatai érvényesek. |
| **Érvényesség kezdete**</br>validfrom</br>*Dátum és idő eltolása* | Írásvédett | Az a dátum, amikortól a beosztás adatai érvényesek. |
| **Elsődleges mező**</br>mshr_primaryfield</br>*Sztring* | Rendszer által előállított | Az elsődleges mező. |
| **Bérlista szerinti beosztás részletei entitás azonosítója**</br>payrollpositiondetailsentityid</br>*Guid* | Szükséges</br>Rendszer által előállított. | Rendszer által generált globálisan egyedi azonosító (GUID) érték, amely egyedileg azonosítja a beosztást. |

## <a name="relations"></a>Kapcsolatok

| Eszközérték | Kapcsolódó entitás | Navigációs tulajdonság | Gyűjtemény típusa |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_PayrollPosition |
| _mshr_fk_hcmpositionhierarchy_id_value | mshr_hcmpositionhierarchyentity | mshr_FK_HcmPositionHierarchy_id | Nem alkalmazható |
| _mshr_fk_job_id_value | mshr_payrollpositionjobentity | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_Payroll |
| _mshr_fk_positionassignmentv2_id_value | mshr_hcmpositionworkerassignmentv2entity | mshr_FK_PositionAssignmentV2_id | Nem alkalmazható |

## <a name="example-query"></a>Példa lekérdezésre

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

## <a name="see-also"></a>Lásd még

[Bérlista-integrációs API bemutatása](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
