---
title: Bérlista szerinti beosztás feladata
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista szerinti beosztás feladata entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 9444a36f5ddf92bd41008c83ec77ab7ff5191fa3
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019346"
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

