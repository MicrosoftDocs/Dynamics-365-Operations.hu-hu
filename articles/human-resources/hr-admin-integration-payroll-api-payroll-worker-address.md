---
title: Bérlista dolgozói címe
description: Ez a cikk részletes adatokat és példa-lekérdezést tartalmaz a bérszámfejtési dolgozó címének entitáshoz a következőben:Dynamics 365 Human Resources
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
ms.openlocfilehash: 683994b24113b8c2017f1bb3c1055e7e0f0eb75e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901118"
---
# <a name="payroll-worker-address"></a>Bérlista dolgozói címe


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a bérszámfejtési dolgozó címének entitását ismerteti Dynamics 365 Human Resources.

Fizikai név: mshr_payrollworkeraddressentity.

### <a name="description"></a>Leírás

Ez az entitás biztosítja az adott alkalmazott bérlista szerinti lakó- és munkahelyét.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság</br>**Fizikai név**</br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Személyzeti szám**</br>mshr_personnelnumber</br>*Sztring* | Írásvédett | Az alkalmazott egyedi személyzeti száma. |
| **Helyazonosító**</br>mshr_locationidbr>*karakterlánc* | Írásvédett | A cím azonosítója. |
| **A címen lakott**</br>mshr_islivedinaddressbr </br> *[mshr_NoYes beállításkészlet](hr-admin-integration-payroll-api-no-yes.md)* | Írásvédett | Ez az érték azt a címet jelzi, ahol él az alkalmazott. |
| **A címen dolgozott** </br> mshr_isworkedinaddressbr </br>*[mshr_NoYes beállításkészlet](hr-admin-integration-payroll-api-no-yes.md)* | Írásvédett | Ez az érték azt a címet jelzi, ahol dolgozik az alkalmazott. |
| **Ország régió**</br>mshr_countryregionid</br>*Sztring* | Írásvédett</br>Szükséges | A címhez meghatározott ország/régió. |
| **Irányítószám**</br>mshr_zipcode<br>*Sztring* | Írásvédett | Az alkalmazotthoz meghatározott azonosítószám. |
| **Utca**</br>mshr_street</br>*Sztring* | Írásvédett | A címhez megadott utca. |
| **Város**</br>mshr_city</br>*Sztring* | Írásvédett | A címhez megadott város. |
| **Állami**</br>mshr_state</br>*Sztring* | Írásvédett | A címhez meghatározott állam vagy tartomány. |
| **Megye**</br>mshr_county</br>*Sztring* | Írásvédett | A címhez megadott megye. |
| **Érvényesség kezdete**</br>mshr_postaladdressvalidfrom</br>*Dátum és idő eltolása* | Írásvédett | A cím érvényességének kezdő dátuma. |
| **Érvényesség vége:**</br>mshr_postaladdressvalidto</br>*Dátum és idő eltolása* | Írásvédett | A cím érvényességének befejező dátuma. |
| **Elsődleges mező**</br>mshr_primaryfield</br>*Sztring* | Írásvédett | Az elsődleges mező. |
| **Bérlista dolgozói címe azonosítója**</br>mshr_payrollworkeraddressentityid</br>*GUID* | Rendszer által előállított | Rendszer által generált globálisan egyedi azonosító (GUID) érték, amely egyedileg azonosítja a címet. |

## <a name="relations"></a>Kapcsolatok

| Eszközérték | Kapcsolódó entitás | Navigációs tulajdonság | Gyűjtemény típusa |
| --- | --- | --- | --- |
| _mshr_fk_worker_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Worker_id | mshr_FK_PayrollEmployeeEntity_Address |

## <a name="example-query"></a>Példa lekérdezésre

**Kérelem**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**Válasz**

```json
{
    "mshr_personnelnumber": "000041",
    "mshr_locationid": "000000538",
    "mshr_islivedinaddress": 200000001,
    "mshr_isworkedinaddress": 200000000,
    "mshr_countryregionid": "USA",
    "mshr_zipcode": "99025",
    "mshr_street": "6543 Cypress Ave",
    "mshr_city": "Tacoma",
    "mshr_state": "WA",
    "mshr_county": "KING",
    "mshr_postaladdressvalidfrom": "2012-09-20T20:14:27Z",
    "mshr_postaladdressvalidto": "2154-12-31T23:59:59Z",
    "mshr_primaryfield": "000041 | 000000538 | 9/20/2012 08:14:27 pm",
    "_mshr_fk_worker_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "mshr_payrollworkeraddressentityid": "000006f0-0000-0000-f90f-014105000000"

}
```

## <a name="see-also"></a>Lásd még

[Bérlista-integrációs API bemutatása](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
