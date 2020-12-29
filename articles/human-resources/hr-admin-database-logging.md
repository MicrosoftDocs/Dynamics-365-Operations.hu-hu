---
title: Adatbázis-naplózás konfigurálása és kezelése
description: Nyomon követheti a táblák és a mezők módosításait az Dynamics 365 Human Resources adatbázisnaplózás funkciójával.
author: Darinkramer
manager: AnnBe
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3dc4658a0a13af95978c66f5aab882902f754a2d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418848"
---
# <a name="configure-and-manage-database-logging"></a>Adatbázis-naplózás konfigurálása és kezelése

Nyomon követheti a táblák és a mezők módosításait az Dynamics 365 Human Resources adatbázisnaplózás funkciójával. Ez a témakör ismerteti, hogyan végezheti el a következőket:

- Adatbázis-naplózás biztonságának és teljesítményének kezelése
- Adatbázis-naplózás beállítása
- Adatbázisnaplók karbantartása

## <a name="overview-of-database-logging"></a>Adatbázisnaplózás áttekintése

Az adatbázisnaplózás nyomon követi a Microsoft Dynamics 365 Human Resources tábláinak és mezőinek bizonyos módosításait. Ilyen módosítások a beszúrást, a frissítés vagy a törlés. Az adatbázis-naplózás egy rekordot tárol az adatbázis-napló táblájában lévő táblák és mezők változásairól.

Az adatbázis-naplózás üzleti felhasználási módjai a következők:

- A bizalmas adatokat tartalmazó konkrét táblák változásai naplózási rekordjának létrehozása.
- Egyes tranzakciók nyomon követése. Az adatbázis-naplózás nem a kötegelt feladatokban futó automatizált tranzakciók nyomon követésére szolgál.

## <a name="security-for-database-logging"></a>Adatbázisnaplózás biztonsága

Az adatbázisnaplók bizalmas adatokat tartalmazhatnak. A hozzáférés korlátozásával csak azokat a biztonsági jogosítja fel, amelyek számára a napló adatainak elérése szükséges.

## <a name="database-logging-and-performance"></a>Adatbázis naplózása és teljesítménye

Ugyan üzleti szempontok alapján értékes, az adatbázis-naplózás költséges lehet az erőforrás-felhasználás és-kezelés modulban.szempontjából. Az adatbázis-naplózás teljesítményre gyakorolt hatásai a következők:

- Az adatbázisnapló-tábla gyorsan nőhet, ami növeli az adatbázis méretét. A növekedés a megtartani kívánt naplózott adatok mennyiségétől függ. Alapértelmezés szerint az adatbázis-napló tábla csak 30 napnyi naplóadatot tart meg. 

- Az adatbázis naplózása hátrányosan érintheti a hosszú ideig futó automatizált folyamatokat, például a hosszú ideig futó adatimportálásokat.

### <a name="best-practices"></a>Gyakorlati tanácsok

A teljesítmény javítása érdekében a teljes táblák naplózása helyett csak bizonyos mezőket válasszon ki naplózásra, így korlátozhatja a naplóbejegyzések számát. Az általános teljesítmény fenntartásához az adatbázis naplózása legfeljebb 20 táblára korlátozódik.

> [!NOTE]
> Az egyedi mezők esetében csak a frissítéseket lehet naplózni.

## <a name="set-up-database-logging"></a>Adatbázis-naplózás beállítása

Az **Adatbázis-változások naplózása** varázsló használatával állíthatja be az adatbázis naplózását. A varázslóval rugalmasan beállíthatja a táblák és a mezők naplózását.

1. Nyissa meg a **Rendszeradminisztráció > Hivatkozások > Adatbázis-> Adatbázis-napló beállítása** elemet. Válassza az **Új** parancsot a **Adatbázis-változások naplózása** varázsló elindításához.
2. Hajtsa végre a varázsló lépéseit.

## <a name="clean-up-database-logs"></a>Adatbázisnaplók karbantartása

Az adatbázis-naplókat egészben vagy egy részben törölheti a következő beállításokkal:

- Egy adott táblához tartozó összes napló kiválasztása.
- Adja meg az adatbázis-napló meghatározott típusait.
- Válassza ki a napló létrehozásának dátumát és időpontját.

Az adatbázis-tisztítás beállításához kövesse az alábbi lépéseket: 

1. Nyissa meg a **Rendszeradminisztráció > Hivatkozások > Adatbázis-> Adatbázis-napló** elemet. Válassza ki a **Napló tisztítása** lehetőséget.

2. Válassza ki a törölni kívánt naplók kiválasztására szolgáló módszert a következő lehetőségek egyikének megadásával:

   - Táblaazonosító (ID)
   - Napló típusa
   - Létrehozás dátuma és időpontja

3. Az **Adatbázis-napló tisztítása** lapon megadhatja, hogy mikor fusson a naplókarbantartási feladat. Alapértelmezés szerint az adatbázisnaplók 30 napig érhetők el.
