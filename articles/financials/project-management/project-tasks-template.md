---
title: "Projektfeladatok közvetlen szinkronizálása a Project Service Automation alkalmazásból közvetlenül a Finance and Operations alkalmazásba"
description: "Ez a témakör azt a sablont és kapcsolódó feladatot mutatja be, melyek a projektfeladatoknak a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Project Service Automation közötti szinkronizálásra használhatók."
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 53e4eab0d455af4ac1e17754f31d46458db742c3
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="synchronize-project-tasks-directly-from-project-service-automation-to-finance-and-operations"></a>Projektfeladatok közvetlen szinkronizálása a Project Service Automation alkalmazásból közvetlenül a Finance and Operations alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör azt a sablont és kapcsolódó feladatot mutatja be, melyek a projektfeladatoknak a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Project Service Automation közötti szinkronizálásra használhatók.

> [!NOTE]
> - Projektfeladat integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása a Microsoft Dynamics 365 for Finance and Operations 8.0-ás verziójában érhetők el.
> - Amennyiben a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0-ás verziót használja, a KB 4132657 és KB 4132660 telepítését követően, használhat sablonokat projektfeladatok, kiadási tranzakciókategóriák, becsült órák, becsült kiadások és a tényleges értékek integrálásához, és a funkciók zárolásának beállításához. Ha a könyvelési felosztásokat kell visszaállítania, ajánlott a KB 4131710 telepítése is.
> - A tényleges adatok integrációja a Microsoft Dynamics 365 for Finance and Operations 8.01-es vagy újabb verziójában érhető el.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Adatáramlás a Project Service Automation és a Finance and Operations között

A Project Service Automation és Finance and Operations közötti integrációs megoldása az adatintegrációs funkciót használja a Project Service Automation and Finance és Operations példányok közötti szinkronizáláshoz. Az integrációs sablon, amelyek elérhető az adatintegrációs funkcióval lehetővé teszi a projektfeladatok adatainak áramlását a Project Service Automation alkalmazásból a Finance and Operations alkalmazásba.

A következő ábra bemutatja a Project Service Automation és a Finance and Operations közötti adatszinkronizálást.

[![Adatáramlás a Project Service Automation és a Finance and Operations integrációjához](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)

## <a name="template-and-task"></a>Sablon és feladat

A rendelkezésre álló sablon eléréséhez a Microsoft PowerApps admin centerben válassza a **Projektek** lehetőséget, majd kattintson a jobb felső sarkában **Új projekt** lehetőségre a nyilvános sablonok kiválasztásához.

A következő sablon és alapul szolgáló feladat használható az aktuális projektfeladatok szinkronizálásához a Project Service Automation és Finance and Operations között:

- **Sablon neve az adatintegrációban:** Projektfeladatok(PSA to Fin and Ops)
- **A feladat neve a projektben:** Projektfeladatok

Projektfeladatok szinkronizálása előtt szinkronizálnia kell a projektszerződéseket és a projekteket..

## <a name="entity-set"></a>Entitás beállítása

| Projekt szolgáltatásautomatizálása | Finance and Operations              |
|----------------------------|-------------------------------------|
| Projektfeladatok              | Integrációs entitás a projektfeladathoz |

## <a name="entity-flow"></a>Entitás folyamata

Projektfeladatok kezelése a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance and Operations alkalmazásba projekttevékenységként.

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

Projektfeladatok szinkronizálása előtt szinkronizálnia kell a projektszerződéseket és a projekteket..

## <a name="power-query"></a>Power Query

Microsoft Power Query for Excelt kell használnia az adatok szűréséhez, ha teljesül a következő feltétel:

- Erőforrásspecifikus bejegyzései vannak egy projekttevékenységen belül.

Ha a Power Query-t kell használnia, kövesse az alábbi útmutatást:

- A Projektfeladatok (Fin és Ops PSA) sablon rendelkezik egy alapértelmezett szűrővel, mely kizárja az erőforrás-specifikus rekordokat egy projektfeladaton belül azáltal, hogy az **IsLineTask** szűrőjét **hamis** értékre állítja. Ha saját sablont hoz létre, hozzá kell adnia ezt a szűrőt.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésekre az Adatintegrációban A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance and Operations irányban.

[![Sablon-hozzárendelés](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)

