---
title: Hibaelhárítási útmutató – adatintegráció
description: Ez a cikk a Finance and Operations alkalmazások és a Common Data Service közötti adatintegrációk során felmerülő hibák elhárítását tekinti át.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 35c0a1e6342008bc2ee6ff25a1663e199c8cb985
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771025"
---
# <a name="troubleshooting-guide-for-data-integration"></a>Hibaelhárítási útmutató – adatintegráció

## <a name="enable-plug-in-trace-logs-in-common-data-service-and-inspect-the-dual-write-plug-in-error-details"></a>Engedélyezze a Beépülő modul nyomkövetési naplóját a Common Data Service szolgáltatásban, és vizsgálja meg át a kettős írású beépülő modul hibáinak részleteit

[!include [banner](../includes/banner.md)]

Ha a kettős írású szinkronizálás során problémát vagy hibát észlel, hajtsa végre a következő lépéseket a nyomkövetési napló hibáinak ellenőrzése érdekében.

1. A hibák ellenőrzése előtt engedélyeznie kell a beépülő modul nyomonkövetési naplókat. További információért tekints meg az [Oktatás: beépülő modul írása vagy regisztrálás](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) „Nyomonkövetési naplók megtekintése” szakaszát.

    Most megtekintheti a hibákat.

2. Jelentkezzen be a Microsoft Dynamics 365 Sales alkalmazásba.
3. Válassza ki a **Beállítások** gombot (a fogaskerék szimbólumát), majd válassza ki a **Speciális beállítások** lehetőséget.
4. A **Beállítások** menüben válassza a **Testreszabás \> Beépülő modul nyomkövetési naplója** lehetőséget.
5. A hiba részleteinek megjelenítéséhez kattintson a típusnévre: **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin**.

## <a name="inspect-dual-write-synchronization-errors"></a>Kettős írás szinkronizálási hibák ellenőrzése

Kövesse az alábbi lépéseket a hibák tesztelés során történő ellenőrzésére.

1. Jelentkezzen be a Microsoft Dynamics LifeCycle Services (LCS) szolgáltatásba.
2. Nyissa meg az LCS-projektet a kettős írási teszt elvégzéséhez.
3. Válassza a **Felhőbeli környezetek** lehetőséget.
4. Hozzon létre távoli asztali kapcsolatot az alkalmazás virtuális gépével (VM) az LCS modulban megjelenített helyi fiók használatával.
5. Nyissa meg az eseménynaplót. 
6. Lépjen az **Alkalmazás- és szolgáltatásnaplók \> Microsoft \> Dynamics \> AX-DualWriteSync \> Működő** részre. Megjelennek a hibák és a részletek.

## <a name="unlink-one-common-data-service-environment-from-the-application-and-link-another-environment"></a>Kapcsoljon le egy Common Data Service környezetet az alkalmazásból és kapcsoljon egy másik környezetet

A linkek frissítéséhez hajtsa végre a következő lépéseket.

1. Nyissa meg az alkalmazáskörnyezet.
2. Nyissa meg az Adatkezelést.
3. Válassza a **CDS for Apps hivatkozása** lehetőséget
4. Válassza ki az összes futó leképezést, majd válassza a **Leállítás**parancsot.
5. Válassza ki az összes leképezést, majd válassza a **Törlés** elemet.

    > [!NOTE]
    > A **Törlés** beállítás nem elérhető, ha a **CustomerV3-Account** sablont választja ki. Szükség esetén törölje a sablon kiválasztását. A **CustomerV3-Account** egy régebben létesített sablon, amely együttműködik a Potenciális ügyfelek készpénzre váltása sablonnal. Mivel globálisan kiadott sablon, minden sablon alatt megjelenik.

6. Válassza a **Környezet leválasztása** elemet.
7. A művelet jóváhagyásához válassza az **Igen** lehetőséget.
8. Az új környezet összekapcsolásához kövesse a [telepítési útmutató](https://aka.ms/dualwrite-docs) lépéseit.
