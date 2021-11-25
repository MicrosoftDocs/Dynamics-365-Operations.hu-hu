---
title: Kettős írás beállítása a Lifecycle Services szolgáltatásból
description: Ez a témakör bemutatja, hogyan lehet kettős írású kapcsolatot beállítani a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.
author: laneswenka
ms.date: 08/03/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 1fd15b5d664fead10949750678a2d3eab967af22
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781392"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Kettős írás beállítása a Lifecycle Services szolgáltatásból

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör bemutatja, hogyan lehet engedélyezni a kettős írást a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.

## <a name="prerequisites"></a>Előfeltételek

A következő témakörökben leírtak szerint végre kell hajtani a Power Platform-integrációt:

+ [Power Platform-integráció – engedélyezés a környezet telepítése során](../../power-platform/enable-power-platform-integration.md#enable-during-deploy)
+ [Power Platform-integráció – engedélyezés a környezet telepítése után](../../power-platform/enable-power-platform-integration.md#enable-after-deploy)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a>Kettős írás beállítása az új Dataverse-környezetekhez

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

8. Ha befejeződött az összekapcsolás, megjelenik egy hivatkozás. A hivatkozásra kattintva jelentkezzen be a Finance and Operations-környezet kettős íráshoz használatos felügyeleti területére. Itt beállíthatja az entitások leképezését.

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a>Kettős írás beállítása meglévő Dataverse-környezetekhez

Ha meglévő Dataverse-környezetben szeretne kettős írást beállítani, [támogatási jegyet](../../lifecycle-services/lcs-support.md) kell küldenie a Microsoftnak. A jegynek a következőket kell tartalmaznia:

+ A Finance and Operations-környezet azonosítója.
+ A környezet neve a Lifecycle Services szolgáltatásból.
+ A Dataverse-szervezetazonosító, vagy a Power Platform-környezetazonosító a Power Platform Adminisztrációs központjából. A jegyben kérje, hogy az azonosító legyen a Power Platform-integrációhoz használt példány.

> [!NOTE]
> A környezetek nem csatolhatók le az LCS használatával. Egy környezet kapcsolatának megszüntetése érdekében nyissa meg az **Adatintegráció** munkaterületet a Finance and Operations környezetben , majd válassza a **Csatolás megszüntetése** parancsot.

## <a name="linking-mismatch"></a>Kapcsolódási eltérés

Lehetséges, hogy az Ön LCS-környezete egy Dataverse példányhoz, míg a kétírásos környezet egy másik Dataverse példányhoz kapcsolódik. Ez a kapcsolódási eltérés váratlan viselkedést okozhat, és a végén a rendszer rossz környezetbe küldhet adatokat. A kettős íráshoz a Power Platform integráció részeként létrehozott környezet használata ajánlott, és hosszú távon ez lesz az egyetlen módja a környezetek közötti kapcsolat létrehozásának.

Ha a környezetben nem egyezik a kapcsolat, az LCS figyelmeztetést jelenít meg a környezet adatlapján, amely a következőhöz hasonló: "A Microsoft észlelte, hogy a környezet a kettős írás segítségével a Power Platform integrációban megadottól eltérő célhoz van kapcsolva, ami nem ajánlott":

:::image type="content" source="media/powerplat_integration_mismatchLink.png" alt-text="Power Platform integrációs kapcsolat nem egyező.":::

Ha ezzel a hibával találkozik, az Ön igényei alapján két lehetősége van:

+ [A kétírásos környezetek összekapcsolásának feloldása és újbóli összekapcsolása (összekapcsolás visszaállítása vagy módosítása)](relink-environments.md#scenario-reset-or-change-linking) az LCS-környezet adatlapján megadottak szerint. Ez az ideális megoldás, mert a Microsoft támogatása nélkül is futtatható.  
+ Ha a kapcsolatot továbbra is kettős írással szeretné fenntartani, kérhet segítséget a Microsoft ügyfélszolgálattól a Power Platform integráció módosításához, hogy a meglévő Dataverse környezetet használja az előző szakaszban dokumentáltak szerint.  

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
