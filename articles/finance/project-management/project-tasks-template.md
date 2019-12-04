---
title: Projektfeladatok közvetlen szinkronizálása a Project Service Automation alkalmazásból közvetlenül a Finance and Operations alkalmazásba
description: Ez a témakör bemutatja a sablont és a mögöttes feladatot, amelyek a Dynamics 365 Project Service Automation projektfeladatainak közvetlenül a Microsoft Dynamics 365 Finance szolgáltatásba történő szinkronizálására használatosak.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: ba475721b69e7c75dfd2197597b54050a3598d37
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770266"
---
# <a name="synchronize-project-tasks-directly-from-project-service-automation-to-finance-and-operations"></a>Projektfeladatok közvetlen szinkronizálása a Project Service Automation alkalmazásból közvetlenül a Finance and Operations alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a sablont és a mögöttes feladatot, amelyek a Dynamics 365 Project Service Automation projektfeladatainak közvetlenül a Dynamics 365 Finance szolgáltatásba történő szinkronizálására használatosak.

> [!NOTE]
> - Ha a 8.0-ás verzióját használja a projektfeladat integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása funkciókat használhatja.
> - Amennyiben az Enterprise edition 7.3.0-ás verziót használja, a KB 4132657 és KB 4132660 telepítését követően, használhat sablonokat projektfeladatok, kiadási tranzakciókategóriák, becsült órák, becsült kiadások és a tényleges értékek integrálásához, és a funkciók zárolásának beállításához. Ha a könyvelési felosztásokat kell visszaállítania, ajánlott a KB 4131710 telepítése is.
> - Tényleges integráció a 8.0.1 vagy újabb verzióiban érhető el.

## <a name="data-flow-for-project-service-automation-to-finance"></a>Adatáramlás a Project Service Automation és a Finance között

A Project Service Automation és a Finance közötti integrációs megoldás az adatintegrációs funkciót használja a Project Service Automation és Finance példányok közötti szinkronizáláshoz. Az integrációs sablon, amelyek elérhető az adatintegrációs funkcióval lehetővé teszi a projektfeladatok adatainak áramlását a Project Service Automation alkalmazásból a Finance alkalmazásba.

A következő ábra bemutatja a Project Service Automation és a Finance közötti adatszinkronizálást.

[![Adatáramlás a Project Service Automation és a Finance integrációjához](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)

## <a name="template-and-task"></a>Sablon és feladat

A rendelkezésre álló sablon eléréséhez a Microsoft Power Apps adminisztrációs központban válassza a **Projektek** lehetőséget, majd kattintson a jobb felső sarkában **Új projekt** lehetőségre a nyilvános sablonok kiválasztásához.

A következő sablon és alapul szolgáló feladat használható az aktuális projektfeladatok szinkronizálásához a Project Service Automation és Finance között:

- **Sablon neve az adatintegrációban:** Projektfeladatok(PSA to Fin and Ops)
- **A feladat neve a projektben:** Projektfeladatok

Projektfeladatok szinkronizálása előtt szinkronizálnia kell a projektszerződéseket és a projekteket..

## <a name="entity-set"></a>Entitás beállítása

| Project Service Automation | Pénzügy                             |
|----------------------------|-------------------------------------|
| Projektfeladatok              | Integrációs entitás a projektfeladathoz |

## <a name="entity-flow"></a>Entitás folyamata

Projektfeladatok kezelése a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance alkalmazásba projekttevékenységként.

## <a name="prerequisites-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

Projektfeladatok szinkronizálása előtt szinkronizálnia kell a projektszerződéseket és a projekteket..

## <a name="power-query"></a>Power Query

Microsoft Power Query for Excelt kell használnia az adatok szűréséhez, ha teljesül a következő feltétel:

- Erőforrásspecifikus bejegyzései vannak egy projekttevékenységen belül.

Ha a Power Query-t kell használnia, kövesse az alábbi útmutatást:

- A Projektfeladatok (Fin és Ops PSA) sablon rendelkezik egy alapértelmezett szűrővel, mely kizárja az erőforrás-specifikus rekordokat egy projektfeladaton belül azáltal, hogy az **IsLineTask** szűrőjét **hamis** értékre állítja. Ha saját sablont hoz létre, hozzá kell adnia ezt a szűrőt.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésekre az Adatintegrációban A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance irányban.

[![Sablon-hozzárendelés](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)
