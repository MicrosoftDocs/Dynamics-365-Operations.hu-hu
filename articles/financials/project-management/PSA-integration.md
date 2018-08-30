---
title: "Projekt szolgáltatásautomatizálása"
description: "Ez a témakör a Project Service Automation és Finance and Operations közötti integrálási megoldásról szolgál információkkal Ez az integráció az Adatintegráció funkció segítségével szinkronizálja az adatokat a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Project Service Automation példányai között Common Data Service környezetben."
author: KimANelson
manager: AnnBe
ms.date: 06/29/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 841ea53f754f61c2930e77fdafc85eac72f47d7a
ms.openlocfilehash: 4b1d2ae69899a2937d47f6547ee4ba72b2d1ece4
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="project-service-automation"></a>Projekt szolgáltatásautomatizálása

[!include[banner](../includes/banner.md)]

The Project Service Automation to Finance és Operations integrációs funkció Adatintegráció funkció segítségével szinkronizálja az adatokat a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Project Service Automation példányai között a Common Data Service környezetben. Az integrációs sablonok, mely az adatintegráció funkcióban érhetők el lehetővé teszik, a projektek, projektszerződések, a projektszerződéssorok és projektszerződéssor mérföldkövek, kiadástranzakció-kategóriák, becsült órák és becsült költségek áramoltatását a Project Service Automation és a Finance and Operations között.

> [!NOTE]
> - Amennyiben a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0-ás verziót használja, a KB 4132657 és KB 4132660 telepítését követően, használhat sablonokat projektfeladatok, kiadási tranzakciókategóriák, becsült órák, becsült kiadások és a tényleges értékek integrálásához, és a funkciók zárolásának beállításához. Ha a könyvelési felosztásokat kell visszaállítania, ajánlott a KB 4131710 telepítése is.
> - A Finance and Operations 7.3.0 használata esetén, telepítenie kell a KB 4074835. Ezt követően lehetséges a rögzített árú projektek integrálása.
> - Ha a Finance and Operations 7.3.0 verzióját használja, tranzakciókat hív be a Project Service Automation alkalmazásból, telepítenie kell KB 4345320 frissítést annak érdekében, hogy a díjakat megjelenítse a projektszámlán.
> - Amennyiben a Microsoft Dynamics 365 for Finance and Operations 8.0-ás verzióját használja a projektfeladat integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása funkciókat használhatja.
> - Amennyiben a Microsoft Dynamics 365 for Finance and Operations 8.0.1-es vagy újabb verzióját használja, lépes lesz szinkronizálni a tényleges értékeket.

Mielőtt integrálhatná a Project Service Automation és Finance and Operations alkalmazásokat, konfigurálnia kell a Project Service Automation integráció paramétereit. További tudnivalókért lásd [Project Service Automation integrálási paraméterek](PSA-parameters.md).

Az integráció közvetlen szinkronizálást nyújt az alábbi helyzetekben:

- Projektszerződések karbantartása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance and Operations között.
- Projektek létrehozása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance and Operations között.
- Projektszerződéssorok karbantartása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance and Operations között.
- Projektszerződéssor mérföldkövek karbantartása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance and Operations között.
- Projektfeladatok karbantartása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance and Operations között.
- Kiadási tranzakció kategóriák karbantartása a Finance and Operations alkalmazásban, és azok közvetlen szinkronizálása a Finance and Operations és a Project Service Automation között.
- Projektóra becslések létrehozása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance and Operations között.
- Projektköltség becslések létrehozása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance and Operations között.
- Projektidő, költség és tényleges díjak létrehozása a Project Service Automation alkalmazásban, és projekttranzakciók létrehozása a Project Service Automation integrációs naplójában, hogy azok beküldhetők legyenek a Finance and Operations alkalmazásba.

## <a name="data-synchronization"></a>Adatszinkronizálás

A következő ábra bemutatja az adatszinkronizálást a Project Service Automation és a Finance and Operations közötti integráció részeként.

> [!NOTE]
> Jelenleg nem áll rendelkezésre minden sablon. A sablonok az elkészülés időpontjában lesznek kiadva.

[![Project Service Automation és Finance and Operations integráció](./media/PSA-integration.png)](./media/PSA-integration.png)

## <a name="system-requirements-for-finance-and-operations"></a>Rendszerigény a Finance and Operations rendszerhez

A Project Service Automation és Finance and Operations megoldás használatához telepítenie kell a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 verzióját, 12-es vagy újabb platformfrissítéssel.

## <a name="system-requirements-for-project-service-automation"></a>A Project Service Automation rendszerkövetelményei

A Project Service Automation és Finance and Operations integráció használatához telepítenie kell a következő összetevőket:

- Microsoft Dynamics 365 for Project Service Automation 9.0.0.0 vagy újabb verzió
- A potenciális vevők készpénzre váltása megoldás Microsoft Dynamics 365 for Sales szolgáltatáshoz, 1.14.0.0 (v14) vagy későbbi verzió
- Project Service Automation to Finance and Operations solution for Microsoft Dynamics 365 for Project Service Automation 1.0.0.0 vagy újabb verzió

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a>A Project Service Automation to Finance and Operations integrációs megoldást Project Service Automation példányába telepítse

Töltse le a Project Service Automation to Finance and Operations integrációs megoldást a [Microsoft letöltőközpontból](https://www.microsoft.com/en-us/download/details.aspx?id=57016), és kövesse a megoldáshoz tartozó utasításokat.

