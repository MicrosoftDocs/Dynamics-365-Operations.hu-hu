---
title: "Projektfeladatok szinkronizálása a Project Service Automation alkalmazásból"
description: "Ez a témakör azt a sablont és kapcsolódó feladatot mutatja be, mely a projektfeladatok a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Project Service Automation közötti közvetlen szinkronizálásra szolgál."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 399b519ab0da4de405aeb06f3e7f4bf29a6c5cc3
ms.openlocfilehash: 89df0d99d780441ad08cd6bff3e1fd203694eb8e
ms.contentlocale: hu-hu
ms.lasthandoff: 05/30/2018

---

# <a name="synchronize-project-tasks-from-project-service-automation-directly-to-project-activities-in-finance-and-operations"></a>Projektfeladatok szinkronizálása a Project Service Automation alkalmazásból a Finance and Operations projekttevékenységeibe

Ez a témakör azt a sablont és kapcsolódó feladatot mutatja be, mely a projektfeladatok a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Project Service Automation közötti közvetlen szinkronizálásra szolgál.

> [!NOTE]
> Projektfeladatok integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása a Dynamics 365 for Finance and Operations 8.0-ás verziójában érhető el.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Adatáramlás a Project Service Automation és a Finance and Operations között

A Project Service Automation és Finance and Operations közötti integrációs megoldása az adatintegrációs funkciót használja a Project Service Automation and Finance és Operations példányok közötti szinkronizáláshoz. Az integrációs sablon, amelyek elérhető az adatintegrációs funkcióval lehetővé teszi a projektfeladatok adatainak áramlását a Project Service Automation alkalmazásból a Finance and Operations alkalmazásba.

A következő ábra bemutatja a Project Service Automation és a Finance and Operations közötti adatszinkronizálást.

[![Adatáramlás a Project Service Automation és a Finance and Operations integrációjához](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)

## <a name="template-and-task"></a>Sablon és feladat

A rendelkezésre álló sablon eléréséhez a Microsoft PowerApps Admin Centerben válassza a **Projektek** lehetőséget, majd kattintson a jobb felső sarkában **Új projekt** lehetőségre a nyilvános sablonok kiválasztásához.

A következő sablon és alapul szolgáló feladat használható az aktuális projektfeladatok szinkronizálásához a Project Service Automation és Finance and Operations között:

-**A sablon neve az adatintegrációban:** Projektfeladatok (PSA to Fin and Ops) -**A feladat neve a projektben:** Projektfeladatok

Projektfeladatok szinkronizálása előtt szinkronizálnia kell a projektszerződéseket és a projekteket..

## <a name="entity-set"></a>Entitás beállítása

|Projekt szolgáltatásautomatizálása               | Finance and Operations                |
|-----------------------------------------|---------------------------------------|
| Projektfeladatok                           | Integrációs entitás a projektfeladathoz.   |

## <a name="entity-flow"></a>Entitás folyamata

Projektfeladatok kezelése a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance and Operations alkalmazásba projekttevékenységként.

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

Projektfeladatok szinkronizálása előtt szinkronizálnia kell a projektszerződéseket és a projekteket..

## <a name="power-query"></a>Power Query

Microsoft Power Query-t kell használnia az adatok szűréséhez, ha teljesülnek ezek feltételek:

- Erőforrásspecifikus bejegyzései vannak egy projekttevékenységen belül.

Ha a Power Query-t kell használnia, kövesse az alábbiakat:

- A Projektfeladatok (Fin és Ops PSA) sablon rendelkezik egy alapértelmezett szűrővel az erőforrás-specifikus rekordokat egy projektfeladaton belül azáltal, hogy az **IsLineTask** szűrőjét **hamis** értékre állítja. Ha saját sablont hoz létre, hozzá kell adnia ezt a szűrőt.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésekre az Adatintegrációban A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance and Operations irányban.

[![Sablon-hozzárendelés](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)


