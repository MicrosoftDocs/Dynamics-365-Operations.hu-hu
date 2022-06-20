---
title: Személynév előzményei
description: Ez a cikk részletes adatokat és példalekérdezéseket tartalmaz a személynév-előzmények entitáshoz a következőben:Dynamics 365 Human Resources
author: twheeloc
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e34b0d7bebd1c4037347161087ff3a4485a58878
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875771"
---
# <a name="person-name-history"></a>Személynév előzményei


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Személyek neve előzményentitását írja le a következőben:Dynamics 365 Human Resources

Fizikai név: mshr_dirpersonnamehistoricalentity.

### <a name="description"></a>Leírás

Ez az entitás információt nyújt az adott személyhez tartozó névelőzményekről.

> [!IMPORTANT] 
> A **FirstName**, **MiddleName**, **LastName**, **NameValidFrom** és **NameValidTo** mezők már nem állnak rendelkezésre a Bérlista alkalmazottja entitáson. Ezek el lettek távolítva annak biztosításához, hogy csak egy hatályos dátummal rendelkező adatforrás álljon az entitás mögött.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság</br>**Fizikai név**</br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Utónév**</br>mshr_firstname</br>*Sztring* | Írásvédett | Az utónév. |
| **Vezetéknév előtagja**</br>mshr_lastnameprefix</br>*Sztring*) | Írásvédett | Az utónév előtagja. |
| **Vezetéknév**</br>mshr_lastname</br>*Sztring*) | Írásvédett | A vezetéknév. |
| **Második utónév**</br>mshr_middlename</br>*Sztring*) | Írásvédett | A második utónév. |
| **Érvényesség vége:**</br>mshr_validto</br>*Sztring*) | Írásvédett | A név érvényességének befejező dátuma. |
| **Fél száma**</br>mshr_partynumber</br>*Sztring* | Írásvédett | A személy felhasználó által olvasható, rendszer által generált egyedi azonosítója. |
| **Elsődleges mező**</br>mshr_primaryfield</br>*Sztring* | Írásvédett | A rekord egyedi azonosítója. |
| **Személynév előzményei entitásazonosító**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | Rendszer által előállított | Rendszer által generált globálisan egyedi azonosító (GUID) érték, amely egyedileg azonosítja a rekordot. |

## <a name="relations"></a>Kapcsolatok

| Eszközérték | Kapcsolódó entitás | Navigációs tulajdonság | Gyűjtemény típusa |
| --- | --- | --- | --- |
| Nem alkalmazható | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | Nem alkalmazható | mshr_FK_PayrollEmployeeEntity_Name |

## <a name="example-query-for-payroll-employee"></a>Példa lekérdezés a bérszámfejtési alkalmazotthoz

**Kérelem**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_dirpersonnamehistoricalentities?$filter=mshr_partynumber eq 'HR000001606'
```

**Válasz**

```json
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "middle",
    "mshr_validto": "2021-09-10T21:23:53Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | ",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-c12b-014105000000",
    "mshr_validfrom": null
},
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | 9/10/2021 09:23:54 pm",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-d20b-000010000000",
    "mshr_validfrom": "2021-09-10T21:23:54Z"
}
```

## <a name="see-also"></a>Lásd még

[Bérlista-integrációs API bemutatása](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
