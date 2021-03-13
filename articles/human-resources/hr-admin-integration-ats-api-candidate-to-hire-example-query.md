---
title: Példa lekérdezésre a Felvenni kívánt jelölt esetében
description: Ez a témakör példalekérdezést tartalmaz a Felvenni kívánt jelölt entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 963e12e9114664a995b92ffe22063c14f904da35
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125761"
---
# <a name="example-query-for-candidate-to-hire"></a>Példa lekérdezésre a Felvenni kívánt jelölt esetében

Ez a témakör példalekérdezést tartalmaz a Felvenni kívánt jelölt entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.

Ez a témakör egy példán keresztül bemutatja, hogyan használhatja a *mély beszúrásokat* egy új jelöltrekord minden részletének létrehozásához egyetlen API-műveletben. A mély beszúrásokról további információt a [Kapcsolódó entitásrekordok létrehozása egyetlen műveletben](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation) című témakörben talál.

A **mshr_hcmcandidatetohireentity** entitás egyedi, mert kapcsolatban áll a **mshr_dirpersonentity** entitással. A **mshr_hcmcandidatetohireentity** számos tulajdonsága (például **mshr_firstname**, **mshr_lastname** és **mshr_birthdate**) a **mshr_dirpersonentity** rekordból származik. Ha mély beszúrások használata nélkül ad fel új jelöltrekordot a **mshr_hcmcandidatetohireentity** entitáshoz, ezen tulajdonságok értékeit közvetlenül a **mshr_hcmcandidatetohireentity** rekordban határozhatja meg. A társított **mshr_dirpersonentity rekord** implicit módon jön létre a tulajdonságokhoz meghatározott értékekkel. Ezután létrehozhat bármely más kapcsolódó entitásrekordokat (például készségeket vagy végzettséget) külön API-hívásként.

Ha azonban mély beszúrások használatával szeretné létrehozni az összes kapcsolódó entitást egy műveletben, akkor a **mshr_dirpersonentity** entitásra jellemző tulajdonságokat a művelet adott beágyazott szintjén kell definiálni.

Ez a példa bemutatja, hogyan hozhat létre egy jelöltrekordot, a társított személyes rekordot, valamint a személy képességeit és végzettségét három egymásba ágyazott szinten, mély beszúrásokkal egyetlen API-műveletben.

> [!NOTE]
> A példa nem tartalmazza az API-entitások összes tulajdonságát. A példa demonstrációs célok érdekében le van egyszerűsítve.

**Kérelem**

```http

POST [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities
Content-Type: application/json; charset=utf-8
OData-MaxVersion: 4.0
OData-Version: 4.0
Accept: application/json

{
    "mshr_dataareaid": "usmf",
    "mshr_recruitingrequestid": "USMF-000141",
    "mshr_positionid": "000601",
    "mshr_iswillingtorelocate": 200000000,
    "mshr_availabilitydate": "2021-03-18",
    "mshr_comments": "Evelyn's experience is exactly what we need for this position.",
    "mshr_FK_Person_id":
        {
            "mshr_firstname": "Evelyn",
            "mshr_lastname": "Chambers",
            "mshr_namesequencedisplayas": "FirstMiddleLast",
            "mshr_FK_HcmPersonSkillEntity_Person":
            [
                {
                    "mshr_skillid": "CustFocus",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                },
                {
                    "mshr_skillid": "CashFlow",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                }
            ],
            "mshr_FK_HcmPersonEducationEntity_Person": [
                {
                    "mshr_creditbasis": 200000000,
                    "mshr_enddate": "2021-02-22T00:00:00Z",
                    "mshr_educationlevelid": "Bachelor",
                    "mshr_creditsearned": 0,
                    "mshr_startdate": "2017-02-21T00:00:00Z",
                    "mshr_creditscompleted": 0,
                    "mshr_educationinstitutionid": "Cottonwood Univ",
                    "mshr_educationdisciplineid": "Business Mgmt",
                    "mshr_durationunit": 200000000
                }              
            ]
        }
}
```

**Válasz**

```http

HTTP/1/1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities(00000d2d-0000-0000-7317-005001000000)

```

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
