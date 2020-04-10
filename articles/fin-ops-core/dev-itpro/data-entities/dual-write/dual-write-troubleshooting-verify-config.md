---
title: Ellenőrizze, hogy a kettős írás be van-e állítva a(z) Finance and Operations alkalmazásokban és a(z) Common Data Service
description: Ez a témakör azt mutatja be, hogyan lehet meghatározni, hogy a kettős írás konfigurálva van-e a Finance and Operations alkalmazásokban és a Common Data Service szolgáltatásban.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 2f2ba2564ad3e8e444e27fcc0c586ddf252afabd
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172645"
---
# <a name="verify-that-dual-write-is-configured-in-finance-and-operations-apps-and-common-data-service"></a>Ellenőrizze, hogy a kettős írás be van-e állítva a(z) Finance and Operations alkalmazásokban és a(z) Common Data Service

[!include [banner](../../includes/banner.md)]



Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz. Pontosan elmagyarázza, hogyan lehet meghatározni, hogy a kettős írás konfigurálva van-e a Finance and Operations alkalmazásokban és a Common Data Service szolgáltatásban.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Annak ellenőrzése hogy a kettős írás be van-e állítva a Finance and Operations alkalmazásban

Annak eldöntéséhez, hogy a rekordok frissítésre való mentéskor megjelenő hibák a kettős írásból származnak-e, először ellenőrizze, hogy a kettős írás konfigurálva van-e.

+ Ha Finance and Operations alkalmazásban rendszergazdai jogosultságokkal rendelkezik nyissa meg a **Munkaterületek \> Adatkezelés** modulját, és válassza ki a **Kettős írás** csempét. Ha megjelenik a csatolt környezetek részletei és a futó entitások listája, akkor a kettős írás konfigurálva van.

    ![A Finance and Operations alkalmazás kapcsolatának ellenőrzése adminisztrátori jogosultságok birtokában](media/verify_fin_ops_1.png)

+ Ha nincs adminisztrátori jogosultsága, a következő hibaüzenet jelenik meg *Nem lehet adatokat írni az \<entitás neve\> entitásba*. A következő ábrán szereplő példában nem lehet vevői rekordot létrehozni az Finance and Operations alkalmazásban, mert a kettős írás konfigurálva van de a vevőcsoport és a fizetési feltételek hivatkozási adatai nem szerepelnek a Common Data Service szolgáltatásban.

    ![A Finance and Operations alkalmazás kapcsolatának ellenőrzése adminisztrátori jogosultságok nélkül](media/verify_fin_ops_2.png)

Az Finance and Operations alkalmazásokban adatok létrehozásakor jelentkező problémák megoldásával kapcsolatos tudnivalókat lásd az [Élő szinkronizálási problémák elhárítása](dual-write-troubleshooting-live-sync.md) című témakörben.

## <a name="verify-that-dual-write-is-configured-in-common-data-service"></a>Ellenőrizze, hogy a kettős írás be van-e állítva a Common Data Service szolgáltatásban

Amikor adatokat hoz létre, ha a **Vállalat** mezőt látja a Common Data Service lapjain, akkor a kettős írás konfigurálva van.

![A Common Data Service kapcsolatának ellenőrzése](media/verify_cds.png)

Az Common Data Service szolgáltatásban adatok létrehozásakor jelentkező problémák megoldásával kapcsolatos tudnivalókat lásd az [Élő szinkronizálási problémák elhárítása](dual-write-troubleshooting-live-sync.md) című témakörben.

Azzal kapcsolatosan, hogy hogyan tekinteti meg a hibák részleteit, amikor a Common Data Service szolgáltatásban hoz létre adatokat következő témakörben talál: [A beépülő modul nyomkövetési naplójának engedélyezése és megtekintése a Common Data Service szolgáltatásban a hiba részleteinek megtekintéséhez](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).
