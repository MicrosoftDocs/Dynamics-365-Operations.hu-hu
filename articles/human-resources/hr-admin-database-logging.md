---
title: Adatbázis-naplózás konfigurálása és kezelése
description: Nyomon követheti a táblák és a mezők módosításait az Dynamics 365 Human Resources adatbázisnaplózás funkciójával.
author: andreabichsel
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ae974436469c00a3df6fd40d9d60521a0883a917
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054812"
---
# <a name="configure-and-manage-database-logging"></a>Adatbázis-naplózás konfigurálása és kezelése

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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
2. Válassza ki **Következő** lehetőséget. 
3. A varázsló **Táblák és mezők** lapján jelölje ki azokat a táblákat és mezőket, amelyeken engedélyezni szeretné az adatbázis naplózását, és válassza a **Tovább** gombot.

   > [!Note]
   > Az adatbázis naplózása nem érhető el a Human Resources adatbázisának minden táblája esetén. A lista alatti **Összes tábla megjelenítése** lehetőség választásával kibontja a táblák és mezők listáját, hogy minden olyan adatbázistábla látható legyen, amelyekhez az adatbázisnaplózás elérhető, de ez az adatbázistáblák teljes listájának részhalmaza lesz.

4. A varázsló **Módosítás típusai** lapján jelölje ki azokat az adatműveleteket, amelyekben nyomon szeretné követni az egyes táblák és mezők módosításait, majd válassza a **Tovább** gombot. Az alábbi táblázatban található a naplózáshoz elérhető adatműveletek leírása.
5. Tekintse át a módosításokat a **Befejezés** lapon, és válassza a **Befejezés** lehetőséget.

| Művelet | Leírás |
| -- | -- |
| Új tranzakciók nyomon követése | Napló létrehozása a táblában létrehozott új rekordokhoz. |
| Módosítás | Napló létrehozása a táblarekordok frissítéséhez, illetve a tábla egyes kiválasztott mezőinek frissítéséhez. Ha a táblához választ naplófrissítést, akkor minden alkalommal létrejön egy naplórekord, amikor a tábla bármely mezőjében frissítés történik. Ha azt választja, hogy bizonyos mezők frissítéseit naplózza, akkor egy naplórekord csak akkor jön létre, amikor a táblarekordok ezen mezőiben frissítés történik. |
| Eltávolítás | Napló létrehozása a táblából törölt rekordokhoz. |
| Kulcs átnevezése | Naplórekord létrehozása táblakulcs átnevezése után. |


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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
