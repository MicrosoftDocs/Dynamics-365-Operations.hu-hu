---
title: Kapcsolja be a Sensor Data Intelligence szolgáltatást a rendszerben
description: Ez a témakör bemutatja, hogy hogyan lehet bekapcsolni a rendszerben az Adatintelligencia adatokat.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 68b9daa6ffdc50d28f746cae060efc1a97ccd57a
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689967"
---
# <a name="turn-on-sensor-data-intelligence-for-your-system"></a>Kapcsolja be a Sensor Data Intelligence szolgáltatást a rendszerben

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

## <a name="video-instructions"></a>Video-utasítások

Az alábbi videofelvétel bemutatja, hogyan lehet bekapcsolni az Intelligens adatintelligencia szolgáltatást, és [telepíteni a szükséges Azure-erőforrásokat](sdi-deploy-iot-solution-on-azure.md). A cikk másik része szöveges formátumú utasításokat tartalmaz.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE58g3I]

## <a name="procedure"></a>Eljárás

Az Adatintelligencia adatkapcsolati adatok csak akkor használhatók, ha be van kapcsolva a rendszeren.

1. Lépjen a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** részre. (További tájékoztatás: [Funkciókezelés áttekintése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).)
1. A Mind **lapon** található **Szűrő** mezővel keresse *meg a Vezérlőadat-intelligencia nevű funkciót*.
1. Ha a *rendszeren engedélyezve van az Intelligence* funkció, jelölje ki a listán, **majd** tiltsa le. A funkciónak ez a régebbi verziója nem használható együtt azzal az új előnézeti verzióval, amely a következő lépésben engedélyezhető.
1. A Szűrő **mezőben** keresse meg *a (Előnézet)* nevű funkciót.
1. Válassza ki a funkciót a listából, majd az **engedélyezéshez válassza az** Engedélyezés lehetőséget.
