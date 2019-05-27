---
title: Készletátvitelek és -kiigazítások szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations készletkorrekcióinak és átviteleinek közvetlenül a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: AnnBe
ms.date: 04/30/2019
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
ms.openlocfilehash: e94fa87c2f8b66574d6c5b2930cebf2e1b144fea
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1536296"
---
# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a>Készletátvitelek és szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations készletkorrekcióinak és átviteleinek közvetlenül a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.

[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok
A következő sablon és a mögöttes feladatok, amelyek a Microsoft Dynamics 365 for Field Service készletkorrekcióinak és átviteleinek közvetlenül a Microsoft Dynamics 365 for Finance and Operations szolgáltatásba történő szinkronizálására használatosak.

**Sablonok az adatintegrációban**
- Készletkiigazítás (a Field Service megoldásból a Fin and Ops megoldásba)
- Készletátvitelek (a Field Service megoldásból a Fin and Ops megoldásba)

**Feladatok az adatintegrációs projektekben:**
- Készletkiigazítás
- Készletátvitelek

## <a name="entity-set"></a>Entitás beállítása
| Field Service                     | Finance and Operations                             |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   CDS készletkiigazítási napló fejlécei és sorai |
| msdyn_inventoryadjustmentproducts | CDS készletátviteli napló fejlécei és sorai   |

## <a name="entity-flow"></a>Entitás folyamata
A Field Service alkalmazásban végzett készletkiigazítások és átvitelek szinkronizálva lesznek a Finance and Operations alkalmazásba, miután a **Feladása állapota** **Létrehozottról** **Feladottra** lesz módosítva. Amikor ez megtörténik a kiigazítás vagy átmozgatási rendelés zárolva lesz, és csak olvasható. Ez azt jelenti, átviteleket és a kiigazításokat is fel lehet adni a Finance and Operations rendszerbe, de nem lehet azokat módosítani. A Finance and Operations alkalmazásban beállíthat egy kötegelt feladatot, hogy az automatikusan beküldje a kiigazításokat és átviteli készletnaplókat az integrációba. Tekintse meg kötegelt feladat engedélyezésének előfeltételeit.

## <a name="field-service-crm-solution"></a>Field Service CRM megoldás 
A **Készletegység** mezőt hozzá kell adni a **Termék** entitáshoz. Ez a mező szükséges, mivel az Értékesítési és készletegység nem mindig ugyanaz a Finance and Operations alkalmazásban és az Finance and Operations raktárkészletéhez szükséges a készletegység.
Amikor beállít egy terméket egy Raktárkiigazítási termékhez a Készletkiigazításokhoz és a Készletátvitelekhez is az egység a Termékkészlet termékértékből lesz lekérve. Ha egy érték megtalálható az **Egység** mező zárolva lesz a készletkiigazítás termékben

A **Feladás állapota** mező hozzá lett adva a **Készletkiigazítás** és a **Készletátvitel** entitáshoz is. Ezzel a mezővel szűrhető, hogy mikor lett egy kiigazítás vagy átvitel elküldve a Finance and Operations alkalmazásnak. Ezen mező alapértelmezett értéke Létrehozott (1), de nincs elküldve a Finance and Operations számára. Ha Feladva (2) értékre módosítja, akkor át lesz küldve a Finance and Operations alkalmazásnak, de többé nem módosíthat semmit a kiigazítás vagy átvitel terén, és nem adhat hozzá új sorokat.

A **Számsorozat** mező hozzá lett adva a **Készletkiigazítás termékentitáshoz**. Ez a mező gondoskodik arról, hogy az integrációnak egyedi száma legyen, hogy az integráció létrehozhassa és frissíthesse a kiigazítást. Az első készletkiigazítási termék létrehozásakor az létrehoz egy új rekordot a **P2C AutoNumbe** entitásban, hogy megtartsa a számsorozatot és a használt előtagot.

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

### <a name="finance-and-operations"></a>Finance and Operations
Az integráció által generált integrációs készletnaplókat automatikusan kötegelt feladat használatával is fel lehet adni. Ez a következő helyről engedélyezhető: **Készletkezelés > Ismétlődő feladatok > CDS-integráció > Integrációs készlet naplóinak feladása**.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.

### <a name="inventory-adjustment-field-service-to-fin-and-ops-inventory-adjustment"></a>Készletkiigazítás (a Field Service megoldásból a Fin and Ops megoldásba): Készletkiigazítás

[![Sablonleképezés az adatintegrátorban](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-fin-and-ops-inventory-transfer"></a>Készletátvitel (a Field Service megoldásból a Fin and Ops megoldásba): Készletátvitel

[![Sablonleképezés az adatintegrátorban](./media/FSTrans1.png)](./media/FSTrans1.png)
