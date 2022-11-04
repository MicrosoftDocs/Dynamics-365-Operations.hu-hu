---
title: Hibakeresési mód engedélyezése az Adószámítási szolgáltatásban
description: Ez a cikk bemutatja, hogyan lehet engedélyezni a hibakeresési módot az adószámítási szolgáltatásban a problémák kivizsgálásához.
author: hangwan
ms.date: 03/25/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: ''
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 03/23/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 2bb381939ebe32cb51caf730cdd441557d83a4c0
ms.sourcegitcommit: 088a7b5eb9a3b68710dfe012abf4c24776978750
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2022
ms.locfileid: "9620898"
---
# <a name="enable-debug-mode-in-the-tax-calculation-service"></a>Hibakeresési mód engedélyezése az Adószámítási szolgáltatásban

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet engedélyezni a hibakeresési módot az Adószámítás szolgáltatásban a problémák kivizsgálásához.

1. Adja **hozzá a &debug=vs%2 CconfirmExit>** et az Application Object Server (AOS) URL-címéhez, majd frissítse az oldalt.
2. Amikor kiválasztja az **áfa kiszámítását** az áfa kiszámításához, megnyílik **egy TaxServiceAlaubleshootingLog.txt** nevű szövegfájl. A **TaxService AubleshootingLog.txt** fájl tartalmazza **a TaxableDocument** fájlt és a számítási paramétert. Ezek az eredmények az adószolgáltatásból, valamint hibaelhárítási kivételadatokat tartalmaznak.

## <a name="sample"></a>Minta

```json
===============================Tax service calculation input JSON:=====================================
{
    "TaxableDocument": {
    "Header": [
        {
        "Lines": [
            {
            "Transaction Line ID": "5816,68719677391",
            ...
            }
        ],
        "Transaction Header ID": "2022,68719506302",
        ...
        }
    ]
    },
    "Parameter": {
    "ContinueOnErrors": true,
    ...
    },
    "Adjustment": {
    "Lines": {}
    }
}
===========================Tax service calculation result JSON:=================================
{
    "taxDocument": {
    "Header": [
        {
        "Lines": [
            {
            "Tax Codes": {
                ...
            }
        ],
        "Measures": {
            "List Code": "EUTrade"
        },
        "Tax Registration ID": null,
        "Transaction Header ID": "2022,68719506302",
        "Errors": null
        }
    ]
    },
    "solutionId": "b51e0025-cbbe-4d37-bf0b-90d7be4f214d|1",
    "isPartialSuccess": false
}
=============================CorrelationId:==============================
"21f3a8a1-ee9a-477b-b44e-b8ec79e74d16"
```

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
