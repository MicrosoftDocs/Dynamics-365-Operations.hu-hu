---
title: Kettős írás beállítása a Lifecycle Services szolgáltatásból
description: Ez a témakör bemutatja, hogyan lehet kettős írású kapcsolatot beállítani a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.
author: RamaKrishnamoorthy
ms.date: 05/11/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: eb4170ef6cb09c862f6a4163670c519d5d8077fb
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103569"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Kettős írás beállítása a Lifecycle Services szolgáltatásból

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör bemutatja, hogyan lehet engedélyezni a kettős írást a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.

## <a name="prerequisites"></a>Előfeltételek

A következő témakörökben leírtak szerint végre kell hajtani a Power Platform-integrációt:

+ [Power Platform-integráció – engedélyezés a környezet telepítése során](../../power-platform/overview.md#enable-during-environment-deployment)
+ [Power Platform-integráció – beállítás a környezet telepítése után](../../power-platform/overview.md#set-up-after-environment-deployment)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a>Kettős írás beállítása az új Dataverse-környezetekhez

A kettős írás **Környezet részletes adatai** LCS-oldalról történő beállításához hajtsa végre a következő lépéseket:

1. A **Környezet részletes adatai** oldalon bontsa ki a **Power Platform-integráció** szakaszt.

2. Kattintson a **Kettős írású alkalmazás** gombra.

    ![Power Platform-integráció](media/powerplat_integration_step2.png)

3. Olvassa el az Általános Szerződési Feltételeket, majd válassza a **Konfigurálás** lehetőséget.

4. A folytatáshoz válassza az **OK** lehetőséget.

5. A haladás nyomon követéséhez időnként frissítse a Környezet részletes adatai odalt. A telepítéshez általában nem kell 30 percnél hosszabb idő.  

6. Ha a telepítés befejeződött, egy üzenet tájékoztatja arról, hogy a folyamat sikeres volt-e, vagy történt-e hiba. Ha a beállítás sikertelen, erre vonatkozó hibaüzenet jelenik meg. Csak akkor léphet tovább a következő lépésre, ha kijavítja az esetleges hibákat.

7. Válassza az **Összekapcsolás Power Platform-környezettel** a Dataverse és az aktuális környezet adatbázisainak összekapcsolásához. Ehhez általában nem kell 5 percnél hosszabb idő.

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Összekapcsolás Power Platform-környezettel":::

8. Ha befejeződött az összekapcsolás, megjelenik egy hivatkozás. A hivatkozásra kattintva jelentkezzen be a Finance and Operations-környezet kettős íráshoz használatos felügyeleti területére. Itt beállíthatja az entitások leképezését.

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a>Kettős írás beállítása meglévő Dataverse-környezetekhez

Ha meglévő Dataverse-környezetben szeretne kettős írást beállítani, [támogatási jegyet](../../lifecycle-services/lcs-support.md) kell küldenie a Microsoftnak. A jegynek a következőket kell tartalmaznia:

+ A Finance and Operations-környezet azonosítója.
+ A környezet neve a Lifecycle Services szolgáltatásból.
+ A Dataverse-szervezetazonosító, vagy a Power Platform-környezetazonosító a Power Platform Adminisztrációs központjából. A jegyben kérje, hogy az azonosító legyen a Power Platform-integrációhoz használt példány.

> [!NOTE]
> A környezetek nem csatolhatók le az LCS használatával. Egy környezet kapcsolatának megszüntetése érdekében nyissa meg az **Adatintegráció** munkaterületet a Finance and Operations környezetben , majd válassza a **Csatolás megszüntetése** parancsot.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
