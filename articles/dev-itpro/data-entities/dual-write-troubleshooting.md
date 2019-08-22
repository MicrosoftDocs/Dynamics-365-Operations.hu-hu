---
title: Hibaelhárítási útmutató – adatintegráció
description: Ez a cikk a Microsoft Dynamics 365 for Finance and Operations és a Common Data Service közötti adatintegráció során felmerülő hibák elhárítását tekinti át.
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
ms.openlocfilehash: ca62a6b3aa64ec2383ee3ded3b7bbf4650a41166
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797275"
---
# <a name="troubleshooting-guide-for-data-integration"></a>Hibaelhárítási útmutató – adatintegráció

## <a name="enable-plugin-trace-in-common-data-service-and-check-the-dual-write-plugin-error-details"></a>Engedélyezze a Beépülő modul nyomkövetését a Common Data Service szolgáltatásban, és tekintse át a kettős írású beépülő modul hibáinak részleteit

Ha hiba történik a kettős írású szinkronizálás során, akkor a nyomon követési naplóban tekintheti át a hibákat:

1. A hibák áttekintése előtt engedélyeznie kell a Beépülő modul nyomkövetését. Az útmutató a következő helyen található: [Beépülő modul regisztrálása](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs). Ezután megtekintheti a hibákat.
2. Jelentkezzen be a Dynamics 365 for Sales rendszerbe.
3. Kattintson a Beállítások ikonra (fogaskerék), és válassza a **Speciális beállítások** lehetőséget.
4. A **Beállítások** menüben válassza a **Testreszabás > Beépülő modul nyomkövetési naplója** lehetőséget.
5. A hiba részleteinek megtekintéséhez kattintson a típusnévre: **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin**.

## <a name="check-dual-write-synchronization-errors-in-finance-and-operations"></a>A Finance and Operations kettős írású szinkronizálási hibáinak ellenőrzése

A hibák a következő lépésekkel tekinthetők meg a tesztelés során:

+ Jelentkezzen be a LifeCycle Services (LCS) szolgáltatásba.
+ Nyissa meg azt az LCS-projektet, amelyen kettős írású tesztelést szeretne végezni.
+ Lépjen a Felhőbeli környezetek részre.
+ Távoli asztal szolgáltatással nyissa meg a Finance and Operations VM-et. Használja az LCS-ben látható helyi fiókot.
+ Nyissa meg az eseménynaplót. 
+ Lépjen az **Alkalmazás- és szolgáltatásnaplók > Microsoft > Dynamics > AX-DualWriteSync > Működő** részre. Megjelennek a hibák és a részletek.

## <a name="how-to-unlink-and-link-another-common-data-service-environment-from-finance-and-operations"></a>Másik Common Data Service-környezet összekapcsolása és az összekapcsolás megszüntetése a Finance and Operationsben

Az összekapcsolások a következő lépésekkel frissíthetők:

+ Lépjen a Finance and Operations-környezethez.
+ Nyissa meg az Adatkezelést.
+ Kattintson **A CDS for Apps hivatkozása** elemre.
+ Válassza ki az összes futó leképezést, és kattintson a **Leállítás** elemre. 
+ Válassza ki az összes futó leképezést, és kattintson a **Törlés** elemre.

    > [!NOTE]
    > A **Törlés** beállítás nem látható, ha a **CustomerV3-Account** sablont választja ki. Ha szükséges, törölje a sablon kiválasztását. A **CustomerV3-Account** egy régebben létesített sablon, amely együttműködik a Potenciális ügyfelek készpénzre váltása sablonnal. Mivel globálisan kiadott sablon, minden sablon alatt megjelenik.

+ Kattintson a **Környezet leválasztása** elemre.
+ A megerősítéshez kattintson az **Igen** gombra.
+ Az új környezet összekapcsolásához kövesse a [telepítési útmutató](https://aka.ms/dualwrite-docs) lépéseit.

