---
title: Készletegységgel rendelkező termékek szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Microsoft Dynamics 365 for Finance and Operations raktáregységeinek a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 8e421be79fde6103be6344040b6ae6cda0626c5a
ms.sourcegitcommit: d9ed934a142b88340d268fd2bd3753475a3712b0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2019
ms.locfileid: "836302"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a>Készletegységgel rendelkező termékek szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Microsoft Dynamics 365 for Finance and Operations raktáregységeinek a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.

[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSProductsOW.png)](./media/FSProductsOW.png)

A használt **Field Service termékek készletegységgel (Finance and Operations – Field Service)** sablon a **Field Service termékek (Finance and Operations – Field Serivce)** sablonon alapul. További tudnivalókért lásd: [Field Service termékek (Finance and Operations – Field Service)](field-service-product.md).

Ez a témakör csak a két sablonok eltéréseit írja le: 
- **Készletegységgel rendelkező Field Service termékek (a Finance and Operations alkalmazásból a Sales alkalmazásba)**
- **Field Service termékek (Finance and Operations – Field Service)**. 

## <a name="templates-and-tasks"></a>Sablonok és feladatok

**A sablon neve az adatintegrációban:**

- Készletegységgel rendelkező Field Service termékek (a Finance and Operations alkalmazásból a Sales alkalmazásba)

**A feladat neve az adatintegrációs projektben:**

- Termékek

A **Field Service termékek készletegységgel (Finance and Operations – Field Service)** sablon tartalmaz egy megfeleltetést, amely nem szerepel a **Field Service termékek (Finance and Operations – Field Serivce)** sablonban. Ez a hozzárendelés gondoskodik arról, hogy szerepeljen a készletszint-szinkronizáláshoz szükséges készletegység.

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a>Készletegységgel rendelkező Field Service termékek (Finance and Operations – Field Service): termékek

[![Sablonleképezés az adatintegrátorban](./media/FSProduct1.png)](./media/FSProduct1.png)
