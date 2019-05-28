---
title: Készletegységgel rendelkező termékek szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Microsoft Dynamics 365 for Finance and Operations raktáregységeinek a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
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
ms.openlocfilehash: 080672b9a6acd9fd6137580b5b7e14d12cfccf19
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1535859"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a>Készletegységgel rendelkező termékek szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Microsoft Dynamics 365 for Finance and Operations raktáregységeinek a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.

[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSProductsOW.png)](./media/FSProductsOW.png)

A használt **Field Service termékek készletegységgel (Fin and Ops – Field Service)** sablon a **Field Service termékek (Fin and Ops – Field Serivce)** sablonon alapul. További tudnivalókért lásd: [Field Service termékek (Finance and Operations – Field Service)](field-service-product.md).

Ez a témakör csak a két sablonok eltéréseit írja le: 
- **Készletegységgel rendelkező Field Service termékek (a Fin and Ops alkalmazásból a Sales alkalmazásba)**
- **Field Service termékek (Fin and Ops – Field Service)** 

## <a name="templates-and-tasks"></a>Sablonok és feladatok

**A sablon neve az adatintegrációban:**

- Készletegységgel rendelkező Field Service termékek (a Fin and Ops alkalmazásból a Sales alkalmazásba)

**A feladat neve az adatintegrációs projektben:**

- Termékek

A **Field Service termékek készletegységgel (Fin and Ops – Field Service)** sablon tartalmaz egy megfeleltetést, amely nem szerepel a **Field Service termékek (Fin and Ops – Field Serivce)** sablonban. Ez a hozzárendelés gondoskodik arról, hogy szerepeljen a készletszint-szinkronizáláshoz szükséges készletegység.

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.

### <a name="field-service-products-with-inventory-unit-fin-and-ops-to-field-service-products"></a>Készletegységgel rendelkező Field Service termékek (Fin and Ops – Field Service): termékek

[![Sablonleképezés az adatintegrátorban](./media/FSProduct1.png)](./media/FSProduct1.png)
