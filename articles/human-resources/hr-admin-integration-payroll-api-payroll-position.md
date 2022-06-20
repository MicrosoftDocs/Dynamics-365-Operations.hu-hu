---
title: Bérlista beosztásokra vonatkozó részletei
description: Ez a cikk részletes adatokat és példa-lekérdezést nyújt a beosztások entitás bérszámfejtési adatairól Dynamics 365 Human Resources.
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
ms.openlocfilehash: ac36b0386312e1631528b8ab5976db2cb3924caf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904130"
---
# <a name="payroll-position"></a>Bérlista szerinti beosztás


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör leírja a bérszámfejtési pozíciók entitást a következőben:Dynamics 365 Human Resources

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
