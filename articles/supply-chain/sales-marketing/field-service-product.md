---
title: A Supply Chain Management-termékek közvetlen szinkronizálása a Field Service-termékekre
description: Ez a cikk be tárgyalja a sablonokat és a mögöttes feladatokat, amelyek alapján szinkronizálni lehet a termékeket a következőbe Dynamics 365 Supply Chain Management :Dynamics 365 Field Service
author: Henrikan
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
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 114550f01f3aed197480fb6830fe913dbfa7b570
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860551"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a>A Supply Chain Management-termékek közvetlen szinkronizálása a Field Service-termékekre

[!include[banner](../includes/banner.md)]

Ez a témakör a Dynamics 365 Supply Chain Management Dynamics 365 mezőszolgáltatásból származó termékek szinkronizálására használt sablonokat és a mögöttes feladatokat tárgyalja.

A használt **Field Service termékek (Supply Chain Management – Field Service)** sablon A potenciális ügyfelek készpénzre váltása alkalmazásból eredő **Termékek (Supply Chain Management – Sales) – Közvetlen** sablonon alapul. További tudnivalókért lásd: [Termékek (Supply Chain Management – Sales) – Közvetlen](/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Ez a cikk csak a **szolgáltatási termékek (Ellátásilánc-kezelés – Mezőszolgáltatás)** **és a Termékek (Ellátásilánc-kezelés – Értékesítés) – közvetlen sablonok** közötti különbségeket írja le.

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