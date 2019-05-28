---
title: Raktárak szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations raktárainak a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.
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
ms.openlocfilehash: 7e6d7626c00b9d7d98ce872652653c36ce7bc975
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1535675"
---
# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a>Raktárak szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations raktárainak a Microsoft Dynamics 365 for Field Service szolgáltatásba történő szinkronizálására használatosak.

[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok
A következő sablonok és a mögöttes tevékenységek használatosak a raktárak szinkronizálásához a Microsoft Dynamics 365 for Finance and Operations alkalmazásból a Microsoft Dynamics 365 for Field Service alkalmazásba.

**Sablon az adatintegrációban**
- Raktárak (a Fin and Ops megoldásból a Field Service megoldásba)

**Feladat az adatintegrációs projektben**
- Raktár

## <a name="entity-set"></a>Entitás beállítása
| Field Service    | Finance and Operations                 |
|------------------|----------------------------------------|
| msdyn_warehouses | Raktárak                             |

## <a name="entity-flow"></a>Entitás folyamata
A Finance and Operations megoldásban létrehozott és kezelt raktárak a Common Data Service (CDS) adatintegrációs projekten keresztül szinkronizálhatók a Field Service megoldásba. A Field Service megoldásba szinkronizálni kívánt raktárak a speciális lekérdezés és szűrés segítségével vezérelhetők a projekten. A Finance and Operations megoldásból szinkronizáló raktárak a Field Service megoldásban vannak létrehoz úgy, hogy a **Külső karbantartású mező** **Igen** értékre van állítva, valamint a rekord csak olvashatóra van állítva.

## <a name="field-service-crm-solution"></a>Field Service CRM megoldás
A Field Service és a Finance and Operations közötti integrálás támogatásához további funkciók szükségesek a Field Service CRM megoldásból. A megoldásban **Külső karbantartású** mező hozzá lett adva a **Raktár (msdyn_warehouses)** entitáshoz. Ennek a mezőnek a segítségével ellenőrizheti, hogy a raktár kezelése a Finance and Operations megoldásból történik, vagy csak a Field Service szolgáltatásban létezik. A beállítások a mezőben a következők lehetnek:
- **Igen** – A raktár a Finance and Operations szolgáltatásból származik, és nem lesz szerkeszthető a Sales szolgáltatásban.
- **Nem** – A raktár megadása közvetlenül a Field Service megoldásban történt, és itt is tartják karban.

A **Külső karbantartású** mező segítségével szabályozhatja a készletszintek, a kiigazítások, az átvitelek és a munkarendelések használatának szinkronizálását. Csak a **Külső karbantartású** = **Igen** beállítású raktárak használhatók közvetlen szinkronizáláshoz ugyanabba a raktárba a másik rendszerben. 

> [!NOTE]
> Megjegyzés: Lehetőség van több raktár létrehozására a Field Service megoldásban (ahol a **Külsőleg karbantartott** = Nem), majd a leképezésükre egy raktárba a Finance and Operations megoldásban, a speciális lekérdezési és szűrési funkcióval. Ez olyan helyzetekben használt, amikor azt szeretnénk, hogy a Field Service kezelje a részletes készletszintet, és csak frissítéseket küldjön a Finance and Operations megoldásba. Ebben az esetben a Field Service nem kap készletszintű frissítéseket a Finance and Operations megoldásból. További információért lásd: [Készletátvitelek és szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) és [A Field Service szolgáltatásokban lévő munkarendelések szinkronizálása a Finance and Operations értékesítési rendeléseivel](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás
### <a name="data-integration-project"></a>Adatintegrációs projekt
A raktárak szinkronizálása előtt ellenőrizze, hogy frissítése a speciális lekérdezés és szűrést a projekten, hogy csak azokat a raktárakat foglalja magában, amelyeket át akar vinni a Field Service megoldásból Finance and Operations megoldásba. Vegye figyelembe, hogy szüksége lesz a raktárra a Field Service megoldásban az alkalmazásához a munkarendeléseken, a kiigazításokon és az átviteleken.  

Ügyeljen arra, hogy az **integrációs kulcs** létezzen ehhez: **msdyn_warehouses**:
1. Lépjen az Adatintegrációra.
2. Válassza ki a **Csatlakozás beállítása** fület.
3. Válassza ki a munkarendelés szinkronizálásához használt csatlakozási beállítást.
4. Válassza ki az **Integrációs kulcs** fület.
5. Keresse meg a msdyn_warehouses elemet, és erősítse meg, hogy a **msdyn_name (név)** van hozzáadva. Ha nem látható, kattintson a **Kulcs hozzáadása** elemre a hozzáadáshoz, majd kattintson a **Mentés** elemre a lap tetején.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrán látható a sablonleképezés az Adatintegrálásban.

### <a name="warehouses-fin-and-ops-to-field-service-warehouse"></a>Raktárak (a Fin and Ops megoldásból a Field Service megoldásba): Raktár

[![Sablonleképezés az adatintegrátorban](./media/Warehouse1.png)](./media/Warehouse1.png)
