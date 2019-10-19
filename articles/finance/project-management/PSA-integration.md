---
title: A Project Service Automation áttekintése
description: Ez a témakör a Dynamics 365 Project Service Automation – Dynamics 365 Finance integrálási megoldásról nyújt tájékoztatást.
author: KimANelson
manager: AnnBe
ms.date: 07/25/2019
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
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 31d72591041f8d8cc327aa7c6578c15731ba13c5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250553"
---
# <a name="project-service-automation-overview"></a>A Project Service Automation áttekintése

[!include[banner](../includes/banner.md)]

A Project Service Automation és Finance közötti integrációs megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Dynamics 365 Finance és a Dynamics 365 Project Service Automation példányai között a Common Data Service szolgáltatással. Az integrációs sablonok, mely az adatintegráció funkcióban érhetők el lehetővé teszik, a projektek, projektszerződések, a projektszerződéssorok és projektszerződéssor mérföldkövek, kiadástranzakció-kategóriák, becsült órák és becsült költségek áramoltatását a Project Service Automation és a Finance között.

> [!NOTE]
> - A 7.3.0 verzió használata esetén telepítenie kell a KB 4074835 csomagot. Ezt követően lehetséges a rögzített árú projektek integrálása.
> - Ha a 7.3.0 verziót használja, tranzakciókat hív be a Project Service Automation alkalmazásból, telepítenie kell KB 4345320 frissítést annak érdekében, hogy a díjakat megjelenítse a projektszámlán.
> - Amennyiben a 8.0-ás verzióját használja a projektfeladat integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása funkciókat használhatja.
> - Amennyiben a 8.0.1 vagy újabb verzióját használja, szinkronizálhatja azt aktuális adatokat.

Mielőtt integrálhatná a Project Service Automation és Finance alkalmazásokat, konfigurálnia kell a Project Service Automation integráció paramétereit. További tudnivalókért lásd [Project Service Automation integrálási paraméterek](PSA-parameters.md).

Az integráció közvetlen szinkronizálást nyújt az alábbi helyzetekben:

- Projektszerződések karbantartása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance között.
- Projektek létrehozása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance között.
- Projektszerződés-sorok karbantartása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance között.
- Projektszerződés-sorok mérföldköveinek karbantartása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance között.
- Projektfeladatok karbantartása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance között.
- Kiadási tranzakció kategóriák karbantartása a Finance alkalmazásban, és azok közvetlen szinkronizálása a Finance és a Project Service Automation között.
- Projektóra becslések létrehozása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance között.
- Projektköltség-becslések létrehozása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance között.
- Projektidő, költség és tényleges díjak létrehozása a Project Service Automation alkalmazásban, és projekttranzakciók létrehozása a Project Service Automation integrációs naplójában, hogy azok beküldhetők legyenek a Finance alkalmazásba.

## <a name="data-synchronization"></a>Adatszinkronizálás

A következő ábra bemutatja az adatszinkronizálást a Project Service Automation és a Finance közötti integráció részeként.

> [!NOTE]
> Jelenleg nem áll rendelkezésre minden sablon. A sablonok az elkészülés időpontjában lesznek kiadva.

[![Project Service Automation és Finance integráció paraméterei](./media/PSA-integration.png)](./media/PSA-integration.png)

## <a name="system-requirements-for-finance"></a>A Finance rendszerkövetelményei

A Project Service Automation és Finance megoldás használatához telepítenie kell az Enterprise edition 7.3 verzióját, 12-es vagy újabb platformfrissítéssel.

## <a name="system-requirements-for-project-service-automation"></a>A Project Service Automation rendszerkövetelményei

A Project Service Automation és Finance integráció használatához telepítenie kell a következő összetevőket:

- Dynamics 365 Project Service Automation 9.0.0.0 vagy újabb verziója
- A potenciális ügyfelek készpénzre váltása megoldás Dynamics 365 Sales szolgáltatáshoz, 1.14.0.0 (v14) vagy későbbi verzió
- Project Service Automation és a Finance integrációs megoldás a Dynamics 365 Project Service Automation 1.0.0.0 vagy újabb verziójához

## <a name="install-the-project-service-automation-to-finance-integration-solution-in-your-project-service-automation-instance"></a>A Project Service Automation to Finance integrációs megoldást Project Service Automation példányába telepítse

Töltse le a Project Service Automation to Finance integrációs megoldást a [Microsoft letöltőközpontból](https://www.microsoft.com/download/details.aspx?id=57016), és kövesse a megoldáshoz tartozó utasításokat.
