---
title: A kettős írás pénzügyi és műveleti alkalmazásokban és a Dataverse-ben történő konfigurálásának igazolása
description: Ez a témakör ismerteti, hogyan lehet megállapítani, hogy a kettős írás a pénzügyi és műveleti alkalmazásokban, valamint a Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 4ff7821fce661f174f57fb45667d4ceb3cfcede9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289390"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>A kettős írás pénzügyi és műveleti alkalmazásokban és a Dataverse-ben történő konfigurálásának igazolása

[!include [banner](../../includes/banner.md)]





Ez a témakör hibaelhárítási információkat tartalmaz a pénzügyek és a műveletalkalmazások, valamint a Dataverse. Ez a témakör ismerteti, hogyan lehet megállapítani, hogy a kettős írás a pénzügyi és műveleti alkalmazásokban, valamint a Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Ellenőrizze, hogy a kettős írás a Pénzügy és műveletek alkalmazásban van-e beállítva.

Annak eldöntéséhez, hogy a sorok frissítésre való mentéskor megjelenő hibák a kettős írásból származnak-e, először ellenőrizze, hogy a kettős írás konfigurálva van-e.

+ Ha rendszergazdai jogosultságai vannak a Pénzügy és műveletek alkalmazásban, **menjen a Munkaterületek \>** adatai kezelése lapra, és **válassza a Kétírásos csempe** lehetőséget. Ha megjelenik a csatolt környezetek részletei és a futó táblaleképezések listája, akkor a kettős írás konfigurálva van.

    ![A Pénzügy és műveletek alkalmazáskapcsolat ellenőrzése, ha rendszergazdai jogosultságai vannak.](media/verify_fin_ops_1.png)

+ Ha nincs rendszergazdai jogosultsága, a következő hibaüzenet jelenik meg: *Nem lehet adatokat írni az \<entity name\>* entitásba. A következő példában nem lehet vevősort létrehozni a pénzügyek és műveletek alkalmazásában, mivel a kettős írás van beállítva, de a vevőcsoport és a fizetési feltételek hivatkozási adatai nem léteznek itt Dataverse.

    ![A Pénzügy és műveletek alkalmazáskapcsolatának ellenőrzése, ha nincsenek rendszergazdai jogosultságai.](media/verify_fin_ops_2.png)

Az adatok pénzügyi és [műveletalkalmazásokban való létrehozásakor a problémák megoldásáról az Élő szinkronizálási problémák elhárítása témakörben található tájékoztatás](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Ellenőrizze, hogy a kettős írás be van-e állítva a Dataverse szolgáltatásban

Amikor adatokat hoz létre, ha a **Vállalat** oszlopot látja a Dataverse lapjain, akkor a kettős írás konfigurálva van.

![A Dataverse kapcsolatának ellenőrzése.](media/verify_cds.png)

Az Dataverse szolgáltatásban adatok létrehozásakor jelentkező problémák megoldásával kapcsolatos tudnivalókat lásd az [Élő szinkronizálási problémák elhárítása](dual-write-troubleshooting-live-sync.md) című témakörben.

Azzal kapcsolatosan, hogy hogyan tekinteti meg a hibák részleteit, amikor a Dataverse szolgáltatásban hoz létre adatokat következő témakörben talál: [A beépülő modul nyomkövetési naplójának engedélyezése és megtekintése a Dataverse szolgáltatásban a hiba részleteinek megtekintéséhez](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
