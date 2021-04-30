---
title: Bárlista alkalmazottja
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérszámfejtés alkalmazott entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: d3977b758f65875a36749a49459c2a81459a7b69
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5882002"
---
# <a name="payroll-employee"></a>Bárlista alkalmazottja

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérszámfejtés alkalmazott entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Személyzeti szám**<br>mshr_personnelnumber<br>*Sztring* | Írásvédett<br>Szükséges | Az alkalmazott egyedi személyzeti száma. |
| **Elsődleges mező**<br>mshr_primaryfield<br>*Sztring* | Szükséges<br>Rendszer által előállított |  |
| **Vezetéknév**<br>mshr_lastname<br>*Sztring* | Csak olvasható<br>Szükséges | Alkalmazott vezetékneve. |
| **Jogi személy azonosítója**<br>mshr_legalentityID<br>*Sztring* | Írásvédett<br>Szükséges | Megadja a jogi személyt (vállalatot). |
| **Érvényesség kezdete**<br>mshr_namevalidfrom<br>*Dátum és idő eltolása* | Írásvédett <br>Szükséges | Az a dátum, amelytől az alkalmazotti információ érvényes.  |
| **Nem**<br>mshr_gender<br>*Int32* | Írásvédett<br>Szükséges | Az alkalmazott neme. |
| **Bérlista alkalmazotti entitás azonosítója**<br>mshr_payrollemployeeentityid<br>*GUID* | Szükséges<br>Rendszer által előállított | Az alkalmazott egyedi azonosítására szolgáló, rendszer által generált GUID-értéke. |
| **Foglalkoztatás kezdő dátuma**<br>mshr_employmentstartdate<br>*Dátum és idő eltolása* | Írásvédett<br>Szükséges | Az alkalmazott foglalkoztatásának kezdő dátuma. |
| **Azonosítótípus azonosítója**<br>mshr_identificationtypeid<br>*Sztring* |Írásvédett<br>Szükséges | Az alkalmazotthoz meghatározott azonosító típus. |
| **Munkaviszony záró dátuma**<br>mshr_employmentenddate<br>*Dátum és idő eltolása* | Írásvédett<br>Szükséges |Az alkalmazott foglalkoztatásának vége.  |
| **Adatterület azonosítója**<br>mshr_dataareaid_id<br>*GUID* | Szükséges <br>Rendszer által előállított | A jogi személyt (vállalatot) azonosító, rendszer által generált GUID-érték. |
| **Érvényesség vége:**<br>mshr_namevalidto<br>*Dátum és idő eltolása* |  Írásvédett<br>Szükséges | Az a dátum, ameddig az alkalmazotti információ érvényes. |
| **Születési dátum**<br>mshr_birthdate<br>*Dátum és idő eltolása* | Írásvédett <br>Szükséges | Az alkalmazott születési dátuma. |
| **Az azonosítószám ehhez**<br>mshr_identificationnumber<br>*Sztring* | Írásvédett <br>Szükséges |Az alkalmazotthoz meghatározott azonosítószám.  |
| **Keresztnév**<br>mshr_firstname<br>*Sztring* | Írásvédett<br>Szükséges | Alkalmazott utóneve. |
| **Második utónév**<br>mshr_middlename<br>*Sztring* | Írásvédett<br>Szükséges |Az alkalmazott második utóneve.  |

## <a name="example-query-for-payroll-employee"></a>Példa lekérdezés a bérszámfejtési alkalmazotthoz

**Kérelem**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_identificationtypeid eq @idtype and mshr_namevalidfrom le @asofdate and mshr_namevalidto ge @asofdate&@personnelnumber='000041'&@idtype='SSN'&@asofdate=2021-04-01
```

**Válasz**

```json
{
         "mshr_legalentityid": "USMF",
            "mshr_personnelnumber": "000041",
            "mshr_employmentstartdate": "2011-04-05T07:00:00Z",
            "mshr_employmentenddate": "2154-12-31T23:59:59Z",
            "mshr_firstname": "Cassie",
            "mshr_middlename": "Lassie",
            "mshr_lastname": "Hicks",
            "mshr_namevalidfrom": "2021-03-12T20:34:25Z",
            "mshr_namevalidto": "2154-12-31T23:59:59Z",
            "mshr_birthdate": "1987-09-12T00:00:00Z",
            "mshr_gender": 200000002,
            "mshr_identificationtypeid": "SSN",
            "mshr_identificationnumber": "888-99-9342",
            "mshr_dataareaid": "USMF",
            "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
            "_mshr_fk_worker_id_value": "000000ad-0000-0000-d5ff-004105000000",
            "_mshr_fk_employment_id_value": "00000d0d-0000-0000-0600-014105000000",
            "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
            "mshr_payrollemployeeentityid": "00000d3c-0000-0000-d5ff-004105000000",
            "_mshr_dataareaid_id_value": null
}
```
