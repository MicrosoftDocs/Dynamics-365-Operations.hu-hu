---
title: Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához
description: Ez a témakör azt mutatja be, hogyan lehet ügyféloldali parancsfájlt hozzáadni a webhely lapjaihoz, hogy támogassa az ügyfél-oldali telemetria gyűjtését.
author: bicyclingfool
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a5f82426d87cd2e0faa0195a841899bb03f9df08
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697336"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a>Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet ügyféloldali parancsfájlt hozzáadni a webhely lapjaihoz, hogy támogassa az ügyfél-oldali telemetria gyűjtését.

## <a name="overview"></a>Áttekintés

A webanalitika fontos eszköz, ha meg szeretné tudni, hogyan lépnek interakcióba a vevők a webhellyel, és amelyek alapján a felhasználói élmény maximális konverzió érdekében történő optimalizálására szolgáló döntéseket hozhat. Számos webes elemzési csomag érhető el, amely segít elérni ezeket a célokat, például a Google Analytics, a Clicky, a Moz Analytics és a KISSMetrics. A legtöbb webanalitikai csomag megköveteli, hogy a webhely összes oldalán található HTML **\<head\>**-eleméhez hozzáadjon ügyféloldali parancsfájlkódot.

> [!NOTE]
> Az ebben a témakörben található utasítások a Microsoft Dynamics 365 Commerce által natív módon nem kínált egyéni ügyféloldali funkciókra is vonatkoznak.

## <a name="create-a-reusable-fragment-for-your-script-code"></a>Újra felhasználható töredék létrehozása a parancsfájl kódjához

Miután létrehozott egy töredéket a parancsfájl kódjához, az újra felhasználható a webhelye összes lapján.

1. Lépjen a **Töredékek \> Új oldaltöredék** elemhez.
2. Válassza ki a **Külső parancsfájl** elemet, adja meg a töredék nevét, majd kattintson az **OK** gombra.
3. A töredékhierarchiában válassza ki az **imént létrehozott töredék** alárendelt parancsfájl-betöltő modulját.
4. A jobb oldali tulajdonságpanelen adja meg az ügyféloldali parancsfájlt, és állítsa be szükség szerint a többi konfigurációs beállítást.

## <a name="add-the-fragment-to-templates"></a>A töredék hozzáadása sablonokhoz

1. Nyissa mega **Sablonok** pontot, majd nyissa meg azon oldalakhoz tartozó sablont, amelyhez hozzá szeretné adni a parancsfájlkódot.
2. A bal oldali panelen bontsa ki a sablon hierarchiáját a **HTML-fejléc** helyének megjelenítéséhez.
3. Válassza ki a **HTML-fejléc** helyhez tartozó három pont (**…**) gombot, majd válassza a **Töredék hozzáadása** elemet.
4. Válassza ki a parancsfájl kódjához létrehozott töredéket.
5. Mentse a sablont és adja be.

> [!NOTE]
> Miután befejezte a munkát, közzé kell tennie a töredéket és az alapsablont. 

## <a name="additional-resources"></a>További erőforrások

[Embléma hozzáadása](add-logo.md)

[Webhely témájának kiválasztása](select-site-theme.md)

[Kedvencek ikon hozzáadása](add-favicon.md)

[Üdvözlő üzenet hozzáadása](add-welcome-message.md)

[Szerzői jogi értesítés hozzáadása](add-copyright-notice.md)

[Nyelvek hozzáadása a webhelyhez](add-languages-to-site.md)

