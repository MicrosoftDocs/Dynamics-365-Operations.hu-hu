---
title: Kettős írás beállítása a Lifecycle Services szolgáltatásból
description: Ez a témakör bemutatja, hogyan lehet két írásos kapcsolatot létesíteni a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásaival.
author: laneswenka
ms.date: 05/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 5cccba580d23c3a0e9aed62f76a305926a58585f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879804"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Kettős írás beállítása a Lifecycle Services szolgáltatásból

[!include [banner](../../includes/banner.md)]



Ez a témakör bemutatja, hogyan lehet két írást engedélyezni a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.

## <a name="prerequisites"></a>Előfeltételek

A vevőknek az alábbi témakörökben Power Platform leírtak szerint kell végrehajtaniuk az integrációt:

- Ha még nem használja, Microsoft Power Platform és a platform-funkciók hozzáadásával ki szeretné bonteni a Pénzügyi és műveleti környezetet, [Power Platform akkor lásd az Integráció – engedélyezés a környezet telepítése során](../../power-platform/enable-power-platform-integration.md#enable-during-deploy).
- Ha már vannak környezetei Dataverse Power Platform és környezetei, és szeretné csatlakoztatni őket a Pénzügyi és műveleti környezetekhez, [Power Platform akkor tekintse meg az integrációt – engedélyezze a környezet telepítését követően](../../power-platform/enable-power-platform-integration.md#enable-after-deploy).

## <a name="set-up-dual-write-for-new-or-existing-dataverse-environments"></a>Kettős írás beállítása új vagy meglévő környezetekhez Dataverse

A kettős írás **Környezet részletes adatai** LCS-oldalról történő beállításához hajtsa végre a következő lépéseket:

1. A **Környezet részletes adatai** oldalon bontsa ki a **Power Platform-integráció** szakaszt.

2. Kattintson a **Kettős írású alkalmazás** gombra.

    ![Power Platform integráció.](media/powerplat_integration_step2.png)

3. Olvassa el az Általános Szerződési Feltételeket, majd válassza a **Konfigurálás** lehetőséget.

4. A folytatáshoz válassza az **OK** lehetőséget.

5. A haladás nyomon követéséhez időnként frissítse a Környezet részletes adatai odalt. A telepítéshez általában nem kell 30 percnél hosszabb idő.  

6. Ha a telepítés befejeződött, egy üzenet tájékoztatja arról, hogy a folyamat sikeres volt-e, vagy történt-e hiba. Ha a beállítás sikertelen, erre vonatkozó hibaüzenet jelenik meg. Csak akkor léphet tovább a következő lépésre, ha kijavítja az esetleges hibákat.

7. Válassza az **Összekapcsolás Power Platform-környezettel** a Dataverse és az aktuális környezet adatbázisainak összekapcsolásához. Ehhez általában nem kell 5 percnél hosszabb idő.

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Összekapcsolás Power Platform-környezettel.":::

8. Ha befejeződött az összekapcsolás, megjelenik egy hivatkozás. A hivatkozás segítségével jelentkezzen be a Pénzügy és műveletek környezet két írásos felügyeleti területére. Itt beállíthatja az entitások leképezését.

## <a name="linking-mismatch"></a>Kapcsolódási eltérés

Lehetséges, hogy a kétírásos Dataverse környezet egy példányhoz kapcsolódik, miközben az LCS nincs beállítva integrációra Power Platform. Az ilyen csatolási eltérés nem várt viselkedést okozhat. Javasolt, hogy az LCS-környezet részletei megegyeznek azzal, amihez két írás alatt kapcsolódik, hogy ugyanazt a kapcsolatot használni tudja üzleti események, virtuális táblák és bővítmények.

Ha környezete nem egyező a környezetben, az LCS egy figyelmeztetést mutat, amely hasonlít a környezeti részleteket tartalmazó lap következő példájához: "A Microsoft azt észlelte, hogy a környezete két írással kapcsolódik egy Power Platform másik célhoz, mint amit az integrációban meghatároztak, ami nem ajánlott."

:::image type="content" source="media/powerplat_integration_mismatchLink.png" alt-text="Power Platform integrációs kapcsolat nem egyező.":::

Ha megkapja ezt a figyelmeztetést, próbálkozzon a következő megoldások egyikével:

- Ha az LCS-környezet még Power Platform nincs beállítva integrációra, Dataverse az ebben a cikkben található utasítások szerint kapcsolódhat a két írásban konfigurált példányhoz.
- Ha az LCS-környezet Power Platform már be van állítva integrációra, akkor fel kell szabad szünnni a kettős írást, és újracsatlakozni az LCS [által megadotthoz az Eset: Visszaállítás vagy a csatolás módosítása](relink-environments.md#scenario-reset-or-change-linking) segítségével.

A múltban egy manuális támogató jegy rendelkezésre áll, de ez a fenti 1. lehetőségnél korábbi volt.  A Microsoft már nem támogatja a manuális újrakapcsolati kéréseket a támogatási webhelyről.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
