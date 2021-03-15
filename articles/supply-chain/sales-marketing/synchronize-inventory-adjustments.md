---
title: Készletátvitelek és -kiigazítások szinkronizálása a Field Service alkalmazásból a Supply Chain Management alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management készletkorrekcióinak és átviteleinek közvetlenül a Dynamics 365 Field Service szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: tfehr
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: a598f0356034a22ee7fc0902360b8862a1944558
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010972"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a>Készletátvitelek és -kiigazítások szinkronizálása a Field Service alkalmazásból a Supply Chain Management alkalmazásba

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

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

## <a name="table-set"></a>Táblakészlet
| Field Service                     | Ellátásilánc-kezelés                          |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts | Dataverse készletkiigazítási napló fejlécei és sorai |
| msdyn_inventoryadjustmentproducts | Dataverse készletátviteli napló fejlécei és sorai   |

## <a name="table-flow"></a>Táblafolyamat
A Field Service alkalmazásban végzett készletkiigazítások és átvitelek szinkronizálva lesznek a Supply Chain Management alkalmazásba, miután a **Feladása állapota** **Létrehozottról** **Feladottra** lesz módosítva. Amikor ez megtörténik a kiigazítás vagy átmozgatási rendelés zárolva lesz, és csak olvasható. Ez azt jelenti, átviteleket és a kiigazításokat is fel lehet adni a Supply Chain Management rendszerbe, de nem lehet azokat módosítani. A Supply Chain Management alkalmazásban beállíthat egy kötegelt feladatot, hogy az automatikusan beküldje a kiigazításokat és átviteli készletnaplókat az integrációba. Tekintse meg kötegelt feladat engedélyezésének előfeltételeit.

## <a name="field-service-crm-solution"></a>Field Service CRM megoldás 
A **Készletegység** oszlopot hozzá kell adni a **Termék** táblához. Ez az oszlop szükséges, mivel az Értékesítési és készletegység nem mindig ugyanaz a Supply Chain Management alkalmazásban és a Supply Chain Management raktárkészletéhez szükséges a készletegység.
Amikor beállít egy terméket egy Raktárkiigazítási termékhez a Készletkiigazításokhoz és a Készletátvitelekhez is az egység a Termékkészlet termékértékből lesz lekérve. Ha egy érték megtalálható az **Egység** oszlop zárolva lesz a készletkiigazítás termékben.

A **Feladás állapota** oszlop hozzá lett adva a **Készletkiigazítás** és a **Készletátvitel** táblához is. Ezzel az oszloppal szűrhető, hogy mikor lett egy kiigazítás vagy átvitel elküldve a Supply Chain Management alkalmazásnak. Ezen oszlop alapértelmezett értéke Létrehozott (1), de nincs elküldve a Supply Chain Management számára. Ha Feladva (2) értékre módosítja, akkor át lesz küldve a Supply Chain Management alkalmazásnak, de többé nem módosíthat semmit a kiigazítás vagy átvitel terén, és nem adhat hozzá új sorokat.

A **Számsorozat** oszlop hozzá lett adva a **Készletkiigazítási termék** táblához. Ez az oszlop gondoskodik arról, hogy az integrációnak egyedi száma legyen, hogy az integráció létrehozhassa és frissíthesse a kiigazítást. Az első készletkiigazítási termék létrehozásakor az létrehoz egy új rekordot a **P2C AutoNumber** táblában, hogy megtartsa a számsorozatot és a használt előtagot.

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

### <a name="supply-chain-management"></a>Ellátásilánc-kezelés
Az integráció által generált integrációs készletnaplókat automatikusan kötegelt feladat használatával is fel lehet adni. Ez a következő helyről engedélyezhető: **Készletkezelés > Ismétlődő feladatok > Dataverse-integráció > Integrációs készlet naplóinak feladása**.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a>Készletkiigazítás (Field Service alkalmazásból a Supply Chain Management alkalmazásba): Készletkiigazítás

[![Sablonleképezés az adatintegrátorban](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a>Készletűtvitel (Field Service alkalmazásból a Supply Chain Management alkalmazásba): Készletátvitel

[![Sablonleképezés az adatintegrátorban](./media/FSTrans1.png)](./media/FSTrans1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]