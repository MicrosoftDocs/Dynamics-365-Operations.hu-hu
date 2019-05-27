---
title: A Finance and Operations-termékek szinkronizálása a Field Service-termékekre
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Microsoft Dynamics 365 for Finance and Operations termékeinek Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 3f26240ec289f5ddcc2682e598bbf93f516b99af
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562695"
---
# <a name="synchronize-products-in-finance-and-operations-to-products-in-field-service"></a>A Finance and Operations-termékek szinkronizálása a Field Service szolgáltatásokban lévő termékekkel

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Microsoft Dynamics 365 for Finance and Operations termékeinek Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.

A használt **Field Service termékek (Fin and Ops – Field Service)** sablon A potenciális ügyfelek készpénzre váltása alkalmazásból eredő **Termékek (Fin and Ops – Sales) – Közvetlen** sablonon alapul. További tudnivalókért lásd: [Termékek (Fin and Ops – Sales) – Közvetlen](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Ez a témakör csak a **Field Service termékek (Fin and Ops – Field Service)** és a **Termékek (Fin and Ops – Sales) – Közvetlen** sablono közötti különbségeket mutatja be.

## <a name="templates-and-tasks"></a>Sablonok és feladatok

**A sablon neve az adatintegrációban:**

- Field Service termékek (Fin and Ops – Field Service)

**A feladat neve az adatintegrációs projektben:**

- Termékek – Termékek

A **Field Service termékek (Fin and Ops – Field Service)** sablon egy leképezést tartalmaz, amely nem található meg a **Termékek (Fin and Ops – Sales) – Közvetlen** sablonban. Ezt a leképezés biztosítja, hogy a szükséges Field Service-re jellemző mező, a **Szolgáltatás-terméktípus** megfelelően van beállítva.

```
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

A következő értékleképezés van használatban.

```
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

A Finance and Operations alkalmazásban a **Field Service terméktípus** értéke az **Értékesíthető kiadott termékek** adatentitásban a következőképpen számítódik ki:

- **Készlet:** Termék típusa = Termék és cikk modellcsoport, Raktározott termék = Igaz
- **Készleten kívül:** Termék típusa = Termék és cikk modellcsoport, Raktározott termék = Hamis
- **Szolgáltatás:** Terméktípus = Szolgáltatás

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.

### <a name="field-service-products-fin-and-ops-to-field-service-products---products"></a>A Field Service szolgáltatásokban lévő termékek (Finance and Operations-- Field Service): Termékek - Termékek

[![Sablonleképezés az adatintegrátorban](./media/FSProduct.png)](./media/FSProduct.png)
