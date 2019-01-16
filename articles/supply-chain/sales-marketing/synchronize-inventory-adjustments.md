---
title: "Készletátvitelek és -kiigazítások szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a készletátvitelek és -kiigazítások szinkronizálására használhatók a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service között."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: 79a1cfac3fa94223cc9af73e758ce95fd47065c9
ms.contentlocale: hu-hu
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a>Készletátvitelek és szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a készletátvitelek és -kiigazítások szinkronizálására használhatók a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service között.

[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok
A következő sablon és a kapcsolódó feladatok a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti aktuális készletkorrekciók szinkronizálásának futtatására használhatók.

**A sablonok neve az adatintegrációban:**
- Készletkiigazítás (a Field Service megoldásból a Finance and Operations megoldásba)
- Készletátvitelek (a Field Service megoldásból a Finance and Operations megoldásba)

**A feladatok nevei az adatintegrációs projektekben:**
- Készletkiigazítás
- Készletátvitelek

## <a name="entity-set"></a>Entitás beállítása
| Field Service                     | Finance and Operations                             |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   CDS készletkiigazítási napló fejlécei és sorai |
| msdyn_inventoryadjustmentproducts | CDS készletátviteli napló fejlécei és sorai   |

## <a name="entity-flow"></a>Entitás folyamata
A Field Service alkalmazásban végzett készletkiigazítások és átvitelek szinkronizálva lesznek a Finance and Operations alkalmazásba, miután a **Feladása állapota** Létrehozottról Feladottra lesz módosítva. Ekkor a korrekciós vagy átviteli rendelés zárolva lesz és írásvédetté válik, mivel a korrekciók vagy átvitelek beküldhetők a Finance and Operations számára, ezért ezeket nem lehet módosítani.
A Finance and Operations alkalmazásban beállíthat egy kötegelt feladatot, hogy automatikusan beküldje a kiigazításokat és átviteli készletnaplókat az integrációba. A kötegelt feladat engedélyezésének előfeltétel alább találja.

## <a name="field-service-crm-solution"></a>Field Service CRM megoldás 
A Készletegység mezőt hozzá kell adni a Termékentitáshoz. Ez a mező szükséges, hiszen az értékesítési és készletegység nem mindig ugyanaz az Operations alkalmazásban és az Operations raktárkészletéhez szükséges a készletegység.
Amikor beállít egy Terméket egy Raktárkiigazítási termékhez a Készletkiigazításokhoz és a Készletátvitelekhez is az egység a Termékkészlet termékértékből lesz lekérve. Ha egy érték megtalálható az egység mező zárolva lesz a készletkiigazítás termékben

A feladás állapota mező hozzá lett adva a Készletkiigazítás és a Készletátvitel entitáshoz is. Ezzel a mezővel szűrhető, hogy mikor lett a kiigazítás vagy átvitel elküldve az Operations alkalmazásnak. A mező alapértelmezett Létrehozott(1), ekkor az nincs átküldve az Operations alkalmazásnak. Ha Feladva (2) értékre módosítja, akkor át lesz küldve az Operations alkalmazásnak, de többé nem módosíthat semmit a Kiigazítás vagy Átvitel terén, és nem adhat hozzá új sorokat.
A Számsorozat mező hozzá lett adva a Készletkiigazítás termékentitáshoz. Ezt a mezőt segít abban, hogy az integrációnak egyedi száma legyen, hogy az integráció tudja, hogy mikor végezzen létrehozást, és mikor végezzen frissítést. Az első Készletkiigazítási terméket létrehozásakor az létrehoz egy új rekordot a P2C AutoNumbe entitásban, hogy megtartsa a számsorozatot és a használt előtagot.

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

### <a name="in-finance-and-operations"></a>A Finance and Operations alkalmazásban
Az integráció által generált integrációs készletnaplókat automatikusan kötegelt feladatként fel lehet adni. Ez a következő helyről engedélyezhető: Készletkezelés > Ismétlődő feladatok > CDS-integráció > Integrációs készlet naplóinak feladása

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.

### <a name="inventory-adjustment-field-service-to-finance-and-operations-inventory-adjustment"></a>Készletkiigazítás (a Field Service megoldásból a Finance and Operations megoldásba): Készletkiigazítás

[![Sablonleképezés az adatintegrátorban](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-finance-and-operations-inventory-transfer"></a>Készletátvitel (a Field Service megoldásból a Finance and Operations megoldásba): Készletátvitel

[![Sablonleképezés az adatintegrátorban](./media/FSTrans1.png)](./media/FSTrans1.png)

