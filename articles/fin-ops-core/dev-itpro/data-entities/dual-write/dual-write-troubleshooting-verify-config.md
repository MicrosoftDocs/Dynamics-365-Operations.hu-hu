---
title: Ellenőrizze a kettős írás konfigurálását a Finance and Operations alkalmazások és a Dataverse esetében
description: Ez a témakör azt mutatja be, hogyan lehet meghatározni, hogy a kettős írás konfigurálva van-e a Finance and Operations alkalmazásokban és a Dataverse szolgáltatásban.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 0a1da32713f3d4d19b4d343c5b67b416a6c4ffbb
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566765"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>Ellenőrizze a kettős írás konfigurálását a Finance and Operations alkalmazások és a Dataverse esetében

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Ez a cikk a Finance and Operations és a Dataverse alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz. Pontosan elmagyarázza, hogyan lehet meghatározni, hogy a kettős írás konfigurálva van-e a Finance and Operations alkalmazásokban és a Dataverse szolgáltatásban.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Annak ellenőrzése hogy a kettős írás be van-e állítva a Finance and Operations alkalmazásban

Annak eldöntéséhez, hogy a sorok frissítésre való mentéskor megjelenő hibák a kettős írásból származnak-e, először ellenőrizze, hogy a kettős írás konfigurálva van-e.

+ Ha Finance and Operations alkalmazásban rendszergazdai jogosultságokkal rendelkezik nyissa meg a **Munkaterületek \> Adatkezelés** modulját, és válassza ki a **Kettős írás** csempét. Ha megjelenik a csatolt környezetek részletei és a futó táblaleképezések listája, akkor a kettős írás konfigurálva van.

    ![A Finance and Operations alkalmazás kapcsolatának ellenőrzése adminisztrátori jogosultságok birtokában](media/verify_fin_ops_1.png)

+ Ha nincs rendszergazdai jogosultsága, a következő hibaüzenet jelenik meg: *Nem lehet adatokat írni az \<entity name\>* entitásba. A következő ábrán szereplő példában nem lehet vevői sort létrehozni az Finance and Operations alkalmazásban, mert a kettős írás konfigurálva van de a vevőcsoport és a fizetési feltételek hivatkozási adatai nem szerepelnek a Dataverse szolgáltatásban.

    ![A Finance and Operations alkalmazás kapcsolatának ellenőrzése adminisztrátori jogosultságok nélkül](media/verify_fin_ops_2.png)

Az Finance and Operations alkalmazásokban adatok létrehozásakor jelentkező problémák megoldásával kapcsolatos tudnivalókat lásd az [Élő szinkronizálási problémák elhárítása](dual-write-troubleshooting-live-sync.md) című témakörben.

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Ellenőrizze, hogy a kettős írás be van-e állítva a Dataverse szolgáltatásban

Amikor adatokat hoz létre, ha a **Vállalat** oszlopot látja a Dataverse lapjain, akkor a kettős írás konfigurálva van.

![A Dataverse kapcsolatának ellenőrzése](media/verify_cds.png)

Az Dataverse szolgáltatásban adatok létrehozásakor jelentkező problémák megoldásával kapcsolatos tudnivalókat lásd az [Élő szinkronizálási problémák elhárítása](dual-write-troubleshooting-live-sync.md) című témakörben.

Azzal kapcsolatosan, hogy hogyan tekinteti meg a hibák részleteit, amikor a Dataverse szolgáltatásban hoz létre adatokat következő témakörben talál: [A beépülő modul nyomkövetési naplójának engedélyezése és megtekintése a Dataverse szolgáltatásban a hiba részleteinek megtekintéséhez](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]