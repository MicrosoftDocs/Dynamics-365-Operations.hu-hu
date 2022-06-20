---
title: Készletegységgel rendelkező termékek szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba
description: Ez a cikk a készletegység és a készletegység között szinkronizált termékek sablonjairól és a mögöttes feladatokról ad tárgyalja Dynamics 365 Supply Chain Management Dynamics 365 Field Service.
author: Henrikan
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 5f7658eacd20aa69a64d6288e9d29e53b6ccb002
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887254"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a>Készletegységgel rendelkező termékek szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a cikk a készletegység és a készletegység között szinkronizált termékek sablonjairól és a mögöttes feladatokról ad tárgyalja Dynamics 365 Supply Chain Management Dynamics 365 Field Service.

[![Üzleti folyamatok szinkronizálása a Supply Chain Management és a Field Service között.](./media/FSProductsOW.png)](./media/FSProductsOW.png)

A használt **Field Service termékek készletegységgel (Supply Chain Management – Field Service)** sablon a **Field Service termékek (Supply Chain Management – Field Serivce)** sablonon alapul. További információért, lásd: [Termékek szinkronizálása a Supply Chain Management szolgáltatásban a Field Service szolgáltatás termékeivel](field-service-product.md).

Ez a témakör csak a két sablon közötti különbségeket írja le: 
- **Készletegységgel rendelkező Field Service-termékek (Supply Chain Management alkalmazásból a Sales alkalmazásba)**
- **Field Service-termékek (Supply Chain Management és Field Service között)** 

## <a name="templates-and-tasks"></a>Sablonok és feladatok

**A sablon neve az adatintegrációban:**

- Készletegységgel rendelkező Field Service-termékek (Supply Chain Management alkalmazásból a Sales alkalmazásba)

**A feladat neve az adatintegrációs projektben:**

- Termékek

A **Készletegységgel rendelkező Field Service termékek (Supply Chain Management to Field Service)** sablon egy leképezést tartalmaz, amely nem szerepel a **Field Service termékek (Supply Chain Management – Field Serivce)** sablonban. Ez a hozzárendelés gondoskodik arról, hogy szerepeljen a készletszint-szinkronizáláshoz szükséges készletegység.

```plaintext
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a>Készletegységgel rendelkező Field Service termékek (Supply Chain Management – Field Service): termékek

[![Sablonleképezés az adatintegrátorban.](./media/FSProduct1.png)](./media/FSProduct1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]