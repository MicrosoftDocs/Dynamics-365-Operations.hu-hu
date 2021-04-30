---
title: Bérlista szerinti beosztás feladata
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista szerinti beosztás feladata entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
author: jcart
manager: tfehr
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
ms.openlocfilehash: 72f3109f5bea36a390b04b7165fc3831d777b640
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5882000"
---
# <a name="payroll-position-job"></a>Bérlista szerinti beosztás feladata

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista szerinti beosztás kapcsolat entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Beosztásazonosító**<br>mshr_jobid<br>*Sztring* | Írásvédett<br>Szükséges |A feladat azonosítója. |
| **Érvényesség kezdete**<br>mshr_validto<br>*Dátum és idő eltolása* | Írásvédett <br>Szükséges | Az a dátum, amelytől a pozíció és a beosztás kapcsolata érvényes. |
| **Érvényesség vége:**<br>mshr_validto<br>*Dátum és idő eltolása* | Írásvédett <br>Szükséges | Az a dátum, ameddig a pozíció és a beosztás kapcsolata érvényes.  |
| **Beosztásazonosító**<br>mshr_positionid<br>*Sztring* | Írásvédett<br>Szükséges | A pozíció azonosítója. |
| **Elsődleges mező**<br>mshr_primaryfield<br>*Sztring* | Szükséges<br>Rendszer által előállított |  |
| **Beosztáshoz tartozó feladat azonosítójának értéke**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs:mshr_PayrollPositionJobEntity ehhez: mshr_payrollpositionjobentity |A pozícióhoz társított beosztás azonosítója.|
| **Fix kompenzációs konstrukció azonosítójának értéke**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Írásvédett<br>Szükséges<br>Idegen kulcs: mshr_payrollfixedcompensationplanentity entitáshoz tartozó mshr_FixedCompPlan_id  | A pozícióhoz társított fix kompenzációs konstrukció azonosítója. |
| **Bérlista szerinti beosztás feladata azonosítója**<br>mshr_payrollpositionjobentityid<br>*Guid* | Szükséges<br>Rendszer által előállított. | A beosztás egyedi azonosítására szolgáló, rendszer által generált GUID-értéke.  |

