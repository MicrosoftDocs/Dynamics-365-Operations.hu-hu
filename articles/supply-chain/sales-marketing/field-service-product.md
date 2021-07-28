---
title: A Supply Chain Management-termékek közvetlen szinkronizálása a Field Service-termékekre
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Dynamics 365 Supply Chain Management termékeinek Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
ms.date: 04/09/2018
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
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: f765a6f0cbdc99604e0b0191e1cb6a200546769b
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359581"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a>A Supply Chain Management-termékek közvetlen szinkronizálása a Field Service-termékekre

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a sablonokat és a mögöttes feladatot, amelyek a Dynamics 365 Supply Chain Management termékeinek közvetlenül a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.

A használt **Field Service termékek (Supply Chain Management – Field Service)** sablon A potenciális ügyfelek készpénzre váltása alkalmazásból eredő **Termékek (Supply Chain Management – Sales) – Közvetlen** sablonon alapul. További tudnivalókért lásd: [Termékek (Supply Chain Management – Sales) – Közvetlen](/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Ez a témakör csak a **Field Service termékek (Supply Chain Management – Field Service)** és a **Termékek (Supply Chain Management – Sales) – Közvetlen** sablono közötti különbségeket mutatja be.

## <a name="templates-and-tasks"></a>Sablonok és feladatok

**A sablon neve az adatintegrációban**

- Field Service-termékek (Supply Chain Management és Field Service között)

**A feladat neve az adatintegrációs projektben**

- Termékek – Termékek

A **Field Service termékek (Supply Chain Management – Field Service)** sablon tartalmaz egy leképezést, amely be része a **Termékek (Supply Chain Management – Sales) – Közvetlen** sablonnak. Ezt a leképezés biztosítja, hogy a szükséges Field Service-re jellemző mező, a **Szolgáltatás-terméktípus** megfelelően van beállítva.

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

A következő értékleképezés van használatban.

```plaintext
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

A Supply Chain Management alkalmazásban a **Field Service terméktípus** értéke az **Értékesíthető kiadott termékek** adatentitásban a következőképpen számítódik ki:

- **Készlet:** Termék típusa = Termék és cikk modellcsoport, Raktározott termék = Igaz
- **Készleten kívül:** Termék típusa = Termék és cikk modellcsoport, Raktározott termék = Hamis
- **Szolgáltatás:** Terméktípus = Szolgáltatás

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a>Field Service-termékek (Supply Chain Management és Field Service között): Termékek – Termékek

[![Sablonleképezés az adatintegrátorban.](./media/FSProduct.png)](./media/FSProduct.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]