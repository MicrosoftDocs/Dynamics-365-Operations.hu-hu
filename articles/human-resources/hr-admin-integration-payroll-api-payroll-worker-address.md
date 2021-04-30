---
title: Bérlista dolgozói címe
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista szerinti dolgozó címe entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 6d93c38b21e953446142fc32cc2a0911616ac61d
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881998"
---
# <a name="payroll-worker-address"></a>Bérlista dolgozói címe

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista szerinti dolgozó címe entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Város**<br>mshr_city<br>*Sztring* | Írásvédett<br>Szükséges | A címhez megadott város.   |
| **Személyzeti szám**<br>mshr_personnelnumber<br>*Sztring* | Írásvédett<br>Szükséges | Az alkalmazott egyedi személyzeti száma.  |
| **Ország régió**<br>mshr_countryregionid<br>*Sztring* | Írásvédett<br>Szükséges | A címhez tartozó ország régió megadása  |
| **Érvényesség kezdete**<br>mshr_postaladdressvalidfrom<br>*Dátum és idő eltolása* | Írásvédett <br>Szükséges | A cím érvényességének kezdő dátuma |
| **A címen dolgozott**<br>mshr_isworkedinaddressbr>*Int32* | Írásvédett<br>Szükséges | Azt jelzi, hogy a címen dolgozik-e az alkalmazott. |
| **Megye**<br>mshr_county<br>*Sztring* | Írásvédett<br>Szükséges | A címhez megadott megye.  |
| **Bérlista dolgozói címe azonosítója**<br>mshr_payrollworkeraddressentityid<br>*GUID* | Szükséges<br>Rendszer által előállított | A cím egyedi azonosítására szolgáló, rendszer által generált GUID-értéke.  |
| **Elsődleges mező**<br>mshr_primaryfield<br>*Sztring* | Írásvédett<br>Szükséges |  |
| **Utca**<br>mshr_street<br>*Sztring* | Írásvédett<br>Szükséges | A címhez megadott utca. |
| **Érvényesség vége:**<br>mshr_postaladdressvalidto<br>*Dátum és idő eltolása* | Írásvédett <br>Szükséges | A cím érvényességének befejező dátuma.  |
| **Helyazonosító**<br>mshr_locationidbr>*karakterlánc* | Írásvédett <br>Szükséges | A cím azonosítója.  |
| **Irányítószám**<br>mshr_zipcode<br>*Sztring* | Írásvédett <br>Szükséges |Az alkalmazotthoz meghatározott azonosítószám.  |
| **A címen lakott**<br>mshr_islivedinaddressbr>*karakterlánc* | Írásvédett<br>Szükséges | Azt jelzi, hogy a címen lakott-e az alkalmazott. |
| **Állami**<br>mshr_state<br>*Sztring* | Írásvédett<br>Szükséges | A címhez megadott állam.  |

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
