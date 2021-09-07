---
title: Ellenőrizze a kettős írás konfigurálását a Finance and Operations alkalmazások és a Dataverse esetében
description: Ez a témakör azt mutatja be, hogyan lehet meghatározni, hogy a kettős írás konfigurálva van-e a Finance and Operations alkalmazásokban és a Dataverse szolgáltatásban.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 074cfd5dc2d2877e83e7e65a8b2178ed954a288e
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416681"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>Ellenőrizze a kettős írás konfigurálását a Finance and Operations alkalmazások és a Dataverse esetében

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Ez a cikk a Finance and Operations és a Dataverse alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz. Pontosan elmagyarázza, hogyan lehet meghatározni, hogy a kettős írás konfigurálva van-e a Finance and Operations alkalmazásokban és a Dataverse szolgáltatásban.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Annak ellenőrzése hogy a kettős írás be van-e állítva a Finance and Operations alkalmazásban

Annak eldöntéséhez, hogy a sorok frissítésre való mentéskor megjelenő hibák a kettős írásból származnak-e, először ellenőrizze, hogy a kettős írás konfigurálva van-e.

+ Ha Finance and Operations alkalmazásban rendszergazdai jogosultságokkal rendelkezik nyissa meg a **Munkaterületek \> Adatkezelés** modulját, és válassza ki a **Kettős írás** csempét. Ha megjelenik a csatolt környezetek részletei és a futó táblaleképezések listája, akkor a kettős írás konfigurálva van.

    ![A Finance and Operations alkalmazás kapcsolatának ellenőrzése adminisztrátori jogosultságok birtokában.](media/verify_fin_ops_1.png)

+ Ha nincs rendszergazdai jogosultsága, a következő hibaüzenet jelenik meg: *Nem lehet adatokat írni az \<entity name\>* entitásba. A következő ábrán szereplő példában nem lehet vevői sort létrehozni az Finance and Operations alkalmazásban, mert a kettős írás konfigurálva van de a vevőcsoport és a fizetési feltételek hivatkozási adatai nem szerepelnek a Dataverse szolgáltatásban.

    ![A Finance and Operations alkalmazás kapcsolatának ellenőrzése adminisztrátori jogosultságok nélkül.](media/verify_fin_ops_2.png)

Az Finance and Operations alkalmazásokban adatok létrehozásakor jelentkező problémák megoldásával kapcsolatos tudnivalókat lásd az [Élő szinkronizálási problémák elhárítása](dual-write-troubleshooting-live-sync.md) című témakörben.

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Ellenőrizze, hogy a kettős írás be van-e állítva a Dataverse szolgáltatásban

Amikor adatokat hoz létre, ha a **Vállalat** oszlopot látja a Dataverse lapjain, akkor a kettős írás konfigurálva van.

![A Dataverse kapcsolatának ellenőrzése.](media/verify_cds.png)

Az Dataverse szolgáltatásban adatok létrehozásakor jelentkező problémák megoldásával kapcsolatos tudnivalókat lásd az [Élő szinkronizálási problémák elhárítása](dual-write-troubleshooting-live-sync.md) című témakörben.

Azzal kapcsolatosan, hogy hogyan tekinteti meg a hibák részleteit, amikor a Dataverse szolgáltatásban hoz létre adatokat következő témakörben talál: [A beépülő modul nyomkövetési naplójának engedélyezése és megtekintése a Dataverse szolgáltatásban a hiba részleteinek megtekintéséhez](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]