---
title: Raktárak szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba
description: Ez a cikk a raktárak szinkronizálásához használt sablonokat és mögöttes feladatokat tárgyalja Dynamics 365 Supply Chain Management Dynamics 365 Field Service.
author: Henrikan
ms.date: 03/13/2019
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
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 8b86b6a59344299a7a2d277543c3186ed2b8cee4
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103233"
---
# <a name="synchronize-warehouses-from-supply-chain-management-to-field-service"></a>Raktárak szinkronizálása a Supply Chain Management alkalmazásból a Field Service alkalmazásba

[!include[banner](../includes/banner.md)]



Ez a cikk a raktárak szinkronizálásához használt sablonokat és mögöttes feladatokat tárgyalja Dynamics 365 Supply Chain Management Dynamics 365 Field Service.

[![Üzleti folyamatok szinkronizálása a Supply Chain Management és a Field Service között.](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok
A következő sablonokat és alapul szolgáló feladatokat használják a raktárszinkronizálás futtatásához a Supply Chain Management és a Field Service között:

**Sablon az adatintegrációban**
- Raktárak (Supply Chain Management és Field Service között)

**Feladat az adatintegrációs projektben**
- Raktár

## <a name="table-set"></a>Táblakészlet
| Field Service    | Ellátásilánc-kezelés                 |
|------------------|----------------------------------------|
| msdyn_warehouses | Raktárak                             |

## <a name="table-flow"></a>Táblafolyamat
A Supply Chain Management megoldásban létrehozott és kezelt raktárak a Microsoft Dataverse adatintegrációs projekten keresztül szinkronizálhatók a Field Service megoldásba. A Field Service megoldásba szinkronizálni kívánt raktárak a speciális lekérdezés és szűrés segítségével vezérelhetők a projekten. A Supply Chain Management megoldásból szinkronizálódó raktárak a Field Service megoldásban úgy jönnek létre, hogy a **Külsőleg karbantartva** oszlop **Igen** értékre van állítva, valamint a rekord csak olvasható.

## <a name="field-service-crm-solution"></a>Field Service CRM megoldás
A Field Service és a Supply Chain Management közötti integrálás támogatásához további funkciók szükségesek a Field Service CRM megoldásból. A megoldásban **Külső karbantartású** oszlop hozzá lett adva a **Raktár (msdyn_warehouses)** táblához. Ennek az oszlopnak a segítségével ellenőrizheti, hogy a raktár kezelése a Supply Chain Management megoldásból történik, vagy csak a Field Service szolgáltatásban létezik. A beállítások az oszlopban a következők lehetnek:
- **Igen** – A raktár a Supply Chain Management szolgáltatásból származik, és nem lesz szerkeszthető a Sales szolgáltatásban.
- **Nem** – A raktár megadása közvetlenül a Field Service megoldásban történt, és itt is tartják karban.

A **Külső karbantartású** oszlop segítségével szabályozhatja a készletszintek, a kiigazítások, az átvitelek és a munkarendelések használatának szinkronizálását. Csak a **Külső karbantartású** = **Igen** beállítású raktárak használhatók közvetlen szinkronizáláshoz ugyanabba a raktárba a másik rendszerben. 

> [!NOTE]
> Megjegyzés: Lehetőség van több raktár létrehozására a Field Service megoldásban (ahol a **Külsőleg karbantartott** = Nem), majd a leképezésükre egy raktárba a speciális lekérdezési és szűrési funkcióval. Ez olyan helyzetekben használt, amikor azt szeretnénk, hogy a Field Service kezelje a részletes készletszintet, és mindössze frissítéseket küldjön a Supply Chain Management megoldásba. Ebben az esetben a Field Service nem kap készletszintű frissítéseket a Supply Chain Management megoldásból. További információért lásd: [Készletátvitelek és szinkronizálása a Field Service alkalmazásból a Supply Chain Management alkalmazásba](/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) és [A Field Service szolgáltatásokban lévő munkarendelések szinkronizálása a Supply Chain Management értékesítési rendeléseivel](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás
### <a name="data-integration-project"></a>Adatintegrációs projekt
A raktárak szinkronizálása előtt mindenképpen frissítse a speciális lekérdezést és szűrést a projekten, hogy csak azokat a raktárakat foglalja magában, amelyeket át akar vinni a Supply Chain Management megoldásból a Field Service megoldásba. Vegye figyelembe, hogy szüksége lesz a raktárra a Field Service megoldásban az alkalmazásához a munkarendeléseken, a kiigazításokon és az átviteleken.  

Ügyeljen arra, hogy az **integrációs kulcs** létezzen ehhez: **msdyn_warehouses**:
1. Lépjen az Adatintegrációra.
2. Válassza ki a **Csatlakozás beállítása** fület.
3. Válassza ki a munkarendelés szinkronizálásához használt csatlakozási beállítást.
4. Válassza ki az **Integrációs kulcs** fület.
5. Keresse meg a msdyn_warehouses elemet, és erősítse meg, hogy a **msdyn_name (név)** van hozzáadva. Ha nem látható, kattintson a **Kulcs hozzáadása** elemre a hozzáadáshoz, majd kattintson a **Mentés** elemre a lap tetején.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrán látható a sablonleképezés az Adatintegrálásban.

### <a name="warehouses-supply-chain-management-to-field-service-warehouse"></a>Raktárak (Supply Chain Management és Field Service között): Raktár

[![Sablonleképezés az adatintegrátorban.](./media/Warehouse1.png)](./media/Warehouse1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
