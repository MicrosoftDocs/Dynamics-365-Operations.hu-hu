---
title: Készletátvitelek és -kiigazítások szinkronizálása a Field Service alkalmazásból a Supply Chain Management alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management készletkorrekcióinak és átviteleinek közvetlenül a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: AnnBe
ms.date: 04/30/2019
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
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: d76adf10b9df48f5a7a5196e0469bb7cb1dbb34f
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/03/2019
ms.locfileid: "2552233"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a>Készletátvitelek és -kiigazítások szinkronizálása a Field Service alkalmazásból a Supply Chain Management alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management készletkorrekcióinak és átviteleinek közvetlenül a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.

[![Üzleti folyamatok szinkronizálása a Supply Chain Management és a Field Service között](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok
A következő sablonokat és alapul szolgáló feladatokat használják a tényleges készletkiigazítások és -átvitelek szinkronizálásához a Field Service szolgáltatásból a Supply Chain Management szolgáltatásba.

**Sablonok az adatintegrációban**
- Készletkiigazítás (Field Service-ből Supply Chain Management szolgáltatásba)
- Készletátvitel (Field Service-ből Supply Chain Management szolgáltatásba)

**Feladatok az adatintegrációs projektekben:**
- Készletkiigazítás
- Készletátvitelek

## <a name="entity-set"></a>Entitás beállítása
| Field Service                     | Ellátásilánc-kezelés                          |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   CDS készletkiigazítási napló fejlécei és sorai |
| msdyn_inventoryadjustmentproducts | CDS készletátviteli napló fejlécei és sorai   |

## <a name="entity-flow"></a>Entitás folyamata
A Field Service alkalmazásban végzett készletkiigazítások és átvitelek szinkronizálva lesznek a Supply Chain Management alkalmazásba, miután a **Feladása állapota** **Létrehozottról** **Feladottra** lesz módosítva. Amikor ez megtörténik a kiigazítás vagy átmozgatási rendelés zárolva lesz, és csak olvasható. Ez azt jelenti, átviteleket és a kiigazításokat is fel lehet adni a Supply Chain Management rendszerbe, de nem lehet azokat módosítani. A Supply Chain Management alkalmazásban beállíthat egy kötegelt feladatot, hogy az automatikusan beküldje a kiigazításokat és átviteli készletnaplókat az integrációba. Tekintse meg kötegelt feladat engedélyezésének előfeltételeit.

## <a name="field-service-crm-solution"></a>Field Service CRM megoldás 
A **Készletegység** mezőt hozzá kell adni a **Termék** entitáshoz. Ez a mező szükséges, mivel az Értékesítési és készletegység nem mindig ugyanaz a Supply Chain Management alkalmazásban és a Supply Chain Management raktárkészletéhez szükséges a készletegység.
Amikor beállít egy terméket egy Raktárkiigazítási termékhez a Készletkiigazításokhoz és a Készletátvitelekhez is az egység a Termékkészlet termékértékből lesz lekérve. Ha egy érték megtalálható az **Egység** mező zárolva lesz a készletkiigazítás termékben

A **Feladás állapota** mező hozzá lett adva a **Készletkiigazítás** és a **Készletátvitel** entitáshoz is. Ezzel a mezővel szűrhető, hogy mikor lett egy kiigazítás vagy átvitel elküldve a Supply Chain Management alkalmazásnak. Ezen mező alapértelmezett értéke Létrehozott (1), de nincs elküldve a Supply Chain Management számára. Ha Feladva (2) értékre módosítja, akkor át lesz küldve a Supply Chain Management alkalmazásnak, de többé nem módosíthat semmit a kiigazítás vagy átvitel terén, és nem adhat hozzá új sorokat.

A **Számsorozat** mező hozzá lett adva a **Készletkiigazítás termékentitáshoz**. Ez a mező gondoskodik arról, hogy az integrációnak egyedi száma legyen, hogy az integráció létrehozhassa és frissíthesse a kiigazítást. Az első készletkiigazítási termék létrehozásakor az létrehoz egy új rekordot a **P2C AutoNumbe** entitásban, hogy megtartsa a számsorozatot és a használt előtagot.

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

### <a name="supply-chain-management"></a>Ellátásilánc-kezelés
Az integráció által generált integrációs készletnaplókat automatikusan kötegelt feladat használatával is fel lehet adni. Ez a következő helyről engedélyezhető: **Készletkezelés > Ismétlődő feladatok > CDS-integráció > Integrációs készlet naplóinak feladása**.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a>Készletkiigazítás (Field Service alkalmazásból a Supply Chain Management alkalmazásba): Készletkiigazítás

[![Sablonleképezés az adatintegrátorban](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a>Készletűtvitel (Field Service alkalmazásból a Supply Chain Management alkalmazásba): Készletátvitel

[![Sablonleképezés az adatintegrátorban](./media/FSTrans1.png)](./media/FSTrans1.png)
