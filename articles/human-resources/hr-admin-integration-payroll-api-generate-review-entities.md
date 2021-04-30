---
title: Bérlistaentitások létrehozása és áttekintése
description: Ez a témakör azt ismerteti, hogyan lehet bérlistaentitásokat létrehozni és áttekinteni.
author: andreabichsel
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
ms.openlocfilehash: c6e043498d4e36e38575a16c6475a5edfef51fc6
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881999"
---
# <a name="generate-payroll-entities"></a><span data-ttu-id="6bd5d-103">Bérlistaentitások létrehozása</span><span class="sxs-lookup"><span data-stu-id="6bd5d-103">Generate payroll entities</span></span>

<span data-ttu-id="6bd5d-104">Ezzel az OData funkcióval lehet létrehozni a bérlista-integrációhoz szükséges entitásokat.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-104">Use this OData function to generate the entities needed for payroll integration.</span></span> <span data-ttu-id="6bd5d-105">Ha ezen entitások bármilyen változtatása történik az emberi erőforrásokban, például egyéni mezők hozzáadása, akkor a funkció újra meghívható, hogy frissítse az egyes entitások metaadatait.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-105">If any changes are made to these entities in Human Resources, such as adding custom fields, this function can be called again to refresh the metadata of each entity.</span></span> <span data-ttu-id="6bd5d-106">A válasz egy műveletazonosítót tartalmaz, amelyet figyelemmel kísérhet, így tudhatja, hogy mikor fejeződött be a generálás.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-106">The response contains an operation ID that you can monitor so you know when the generation process has completed.</span></span>

<span data-ttu-id="6bd5d-107">**Kérelem**</span><span class="sxs-lookup"><span data-stu-id="6bd5d-107">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/RefreshHumanResourcesVirtualEntities
```

<span data-ttu-id="6bd5d-108">**törzs**</span><span class="sxs-lookup"><span data-stu-id="6bd5d-108">**body**</span></span>

```json
{
    "PhysicalNames" : ["PayrollEmployeeEntity", "HcmWorkerBaseEntity", "PayrollPositionEntity", "PayrollPositionJobEntity", "PayrollWorkerAddressEntity", "HcmJobDetailEntity", "HcmCompFixedPlanTableEntity", "PayrollFixedCompensationPlanEntity", "HcmEmploymentDetailEntity"]
}
```

<span data-ttu-id="6bd5d-109">**Válasz**</span><span class="sxs-lookup"><span data-stu-id="6bd5d-109">**Response**</span></span>

```json
{
    "AsyncOperationId": "8b98d338-f939-4c86-9a91-80b76b6ab2ea"
}
```

## <a name="review-payroll-entities"></a><span data-ttu-id="6bd5d-110">Bérlistaentitások áttekintése</span><span class="sxs-lookup"><span data-stu-id="6bd5d-110">Review payroll entities</span></span>

<span data-ttu-id="6bd5d-111">Az API-val beolvashatja azon entitások listáját, amelyek sikeresen létre vannak hozva, és használatra készek.</span><span class="sxs-lookup"><span data-stu-id="6bd5d-111">Use this API to retrieve a list of the entities that have been successfully generated and are ready for use.</span></span>

<span data-ttu-id="6bd5d-112">**Kérelem**</span><span class="sxs-lookup"><span data-stu-id="6bd5d-112">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_hrvirtualentitycatalogs?$filter=mshr_hasbeengenerated eq true
```

<span data-ttu-id="6bd5d-113">**Válasz**</span><span class="sxs-lookup"><span data-stu-id="6bd5d-113">**Response**</span></span>

```json
{
      "value": [
        {
            "mshr_physicalname": "PayrollWorkerAddressEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-1c00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmJobDetailEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-6400-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmCompFixedPlanTableEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-6b00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "PayrollEmployeeEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-6d00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmEmploymentDetailEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-7e00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "PayrollFixedCompensationPlanEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-9300-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmWorkerBaseEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-c000-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "PayrollPositionJobEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-e700-005001000000",
            "mshr_refresh": null
        }
    ]
}
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]