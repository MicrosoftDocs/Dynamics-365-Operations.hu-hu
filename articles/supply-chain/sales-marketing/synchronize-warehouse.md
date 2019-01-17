---
title: "Raktárak szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti raktárszinkronizálásra használhatók."
author: ChristianRytt
manager: AnnBe
ms.date: 10/10/2018
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
ms.openlocfilehash: eb8ba6051777e27bd44504a8160118e8096b1435
ms.contentlocale: hu-hu
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a>Raktárak szinkronizálása a Finance and Operations alkalmazásból a Field Service alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti raktárszinkronizálásra használhatók.

[![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok
A következő sablon és a kapcsolódó feladatok a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Field Service közötti raktárszinkronizálás futtatására használhatók.

**A sablon neve az adatintegrációban:**
- Raktárak (a Finance and Operations megoldásból a Field Service megoldásba)

**A feladatok nevei az adatintegrációs projektben:**
- Raktár

## <a name="entity-set"></a>Entitás beállítása
| Field Service    | Finance and Operations                 |
|------------------|----------------------------------------|
| msdyn_warehouses | Raktárak                             |

## <a name="entity-flow"></a>Entitás folyamata
A Finance and Operations megoldásban létrehozott és kezelt raktárak a Common Data Service (CDS) adatintegrációs projekten keresztül szinkronizálhatók a Field Service megoldásba. A Field Service megoldásba szinkronizáló kívánt raktárak a speciális lekérdezés és szűrés segítségével vezérelhetők a projekten. A Finance and Operations megoldásból szinkronizáló raktárak a Field Service megoldásban vannak létrehoz úgy, hogy a Külső karbantartású mező Igen értékre van állítva, valamint a rekord csak olvashatóra van állítva.
Field Service CRM-megoldás A Field Service és a Finance and Operations közötti integrálás támogatásához további funkciók szükségesek a Field Service CRM megoldásból. A megoldás a következő változásokat tartalmazza.
A **Külső karbantartású** mező hozzá lett adva a **Raktár (msdyn_warehouses)** entitáshoz. Ennek a mezőnek a segítségével ellenőrizheti, hogy a raktár kezelése az Operations megoldásból történik, vagy csak a Field Service szolgáltatásban létezik.
- Igen – A raktár a Finance and Operations szolgáltatásból származik, és nem lesz szerkeszthető a Sales szolgáltatásban.
- Nem – A raktár megadása közvetlenül a Field Service megoldásban történt, és itt is tartják karban.

A **Külső karbantartású** mező segítségével szabályozhatja a készletszintek, a kiigazítások, az átvitelek és a munkarendelések használatának szinkronizálását. Csak a **Külső karbantartású** = Igen beállítású raktárak használhatók közvetlen szinkronizáláshoz ugyanabba a raktárba a másik rendszerben. 

Megjegyzés: Lehetőség van több raktár létrehozására a Field Service megoldásban (ahol a **Külsőleg karbantartott** = Nem), majd a leképezésükre egy raktárba a Finance and Operations megoldásban, a speciális lekérdezési és szűrési funkcióval. Ez olyan helyzetekben használt, amikor azt szeretnénk, hogy a Field Service kezelje a részletes készletszintet, és csak frissítéseket küldjön a Finance and Operations megoldásba. Ebben az esetben a Field Service nem kap készletszint-frissítéseket a Finance and Operations megoldásból. További információért lásd: Készletátvitelek és szinkronizálása a Field Service alkalmazásból a Finance and Operations alkalmazásba és A Field Service szolgáltatásokban lévő munkarendelések szinkronizálása a Finance and Operations értékesítési rendeléseivel.

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás
### <a name="in-the-data-integration-project"></a>Az adatintegrációs projektben
A raktárak szinkronizálás előtt ellenőrizze, hogy frissítése a speciális lekérdezés és szűrést a projekten, hogy csak azokat a raktárakat foglalja magában, amelyeket át akar vinni a Field Service megoldásból Finance and Operations megoldásba. Vegye figyelembe, hogy szüksége lesz a raktárra a Field Service megoldásban az alkalmazásához a munkarendeléseken, a kiigazításokon és az átviteleken.  

Ügyeljen arra, hogy az **integrációs kulcs** létezzen ehhez: **msdyn_warehouses**
1. Lépjen az Adatintegrációra
2. Válassza ki a **Csatlakozás beállítása** fület
3. Válassza ki a munkarendelés szinkronizálásához használt csatlakozási beállítást.
4. Válassza ki az **Integrációs kulcs** fület
5. Keresse meg a msdyn_warehouses elemet, és ügyeljen arra, hogy a **msdyn_name (név)** legyen hozzáadva. Ha nem látható, kattintson a **Kulcs hozzáadása** elemre a hozzáadáshoz, majd kattintson a **Mentés** elemre a lap tetején.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon látható a sablonleképezés az Adatintegrálásban.

### <a name="warehouses-finance-and-operations-to-field-service-warehouse"></a>Raktárak (a Finance and Operations megoldásból a Field Service megoldásba): Raktár

[![Sablonleképezés az adatintegrátorban](./media/Warehouse1.png)](./media/Warehouse1.png)

