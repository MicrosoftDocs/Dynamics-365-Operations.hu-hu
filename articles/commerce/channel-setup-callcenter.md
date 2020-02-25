---
title: Hívásközpont csatorna beállítása
description: Ez a témakör azt mutatja be, hogyan lehet egy új hívásközpont csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6ec42ab920868f541eeac54556f4f24cb1efaa3a
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002450"
---
# <a name="set-up-a-call-center-channel"></a>Hívásközpont csatorna beállítása


[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet egy új hívásközpont csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A Dynamics 365 Commerce szolgáltatásban a hívásközpont egyfajta kiskereskedelmi csatorna, amelyet az alkalmazásban lehet megadni. Ha meghatároz egy csatornát a hívásközpont entitások számára, azzal a rendszer képes lesz specifikus adatok és megrendelések feldolgozásához tartozó alapértelmezéseket értékesítési rendelésekhez kötni. A vállalat több hívásközponti csatornát is meghatározhat a Commerce rendszerben. 

Új hívásközpont-csatorna létrehozása előtt győződjön meg arról, hogy végrehajtotta a [Csatornbeállítás előfeltételeit](channels-prerequisites.md).

## <a name="create-and-configure-a-new-call-center-channel"></a>Új hívásközpont csatorna létrehozása és konfigurálása

Új hívásközpont csatorna létrehozásához és konfigurálásához kövesse ezeket a lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Csatornák \> Hívásközpontok \> Minden hívásközpont** részhez.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Név** mezőben adja meg az új csatorna nevét.
1. Válassza ki a megfelelő **Jogi személyt** a legördülő listából.
1. Válassza ki a megfelelő **Raktár** helyet a legördülő listából.
1. Az **Alapértelmezett ügyfél** mezőben adjon meg egy érvényes alapértelmezett ügyfelet.
1. Az **E-mail értesítési profilja** mezőben adjon meg egy érvényes e-mail-értesítési profilt.
1. Adja meg az **Ár-felülbírálás** infókódot. Ne feledje: elképzelhető, hogy először létre kell hoznia egy információs kódot.
1. Adja meg a **Várakoztatási kód** infókódot. Ne feledje: elképzelhető, hogy először létre kell hoznia egy információs kódot.
1. Adja meg a **Hitel** infókódot. Ne feledje: elképzelhető, hogy először létre kell hoznia egy információs kódot.
1. Válassza a **Mentés** lehetőséget.

A következő kép bemutatja egy új hívásközpont csatorna létrehozását.

![Új hívásközponti csatorna](media/channel-setup-callcenter-1.png)

A következő kép egy példát mutat a hívásközpont csatornára.

![Hívásközponti csatorna – példa](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a>További csatornák beállítása

A hívásközpont csatorna beállításához szükséges további feladatok közé tartozik a fizetési módok és szállítási módok beállítása.

A következő képen láthatók a **Szállítási módok** és a **Fizetési módok** beállított lehetőségei a **Beállítás** lapon.

![További hívásközpont-csatorna-beállítási műveletek](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a>Fizetési módok beállítása

A fizetési módok beállításához a csatornán támogatott valamennyi fizetési típusnál kövesse az alábbi lépéseket.

1. A műveleti ablaktáblán válassza a **Beállítás** lapot, majd válassza ki a **Fizetési módokat**.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A navigációs ablakban válassza ki a kívánt fizetési módot.
1. Az **általános** szakaszban adjon meg egy **művelet nevét**, és adja meg a kívánt beállításokat.
1. Adja meg a fizetési típushoz szükséges további beállításokat.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A következő kép egy példát mutat a készpénzfizetési módra.

![Fizetési módok – példa](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a>Szállítási módok beállítása

A konfigurált szállítási módokat a **Szállítási módok** kiválasztásával tekintheti meg a **Beállítás** lapon a **Műveleti ablaktáblán**.  

Szállítási mód módosításához vagy hozzáadásához kövesse az alábbi lépéseket.

1. A navigációs ablakban nyissa meg a **Modulok \> Készletkezelés \> Szállítási módok** elemet.
1. A műveleti ablaktáblán válassza az **Új** elemet új szállítási mód létrehozásához, vagy válasszon meglévő módot.
1. A **kiskereskedelmi csatornák** területen válassza a **sor hozzáadása** parancsot a csatorna hozzáadásához. Csatornák hozzáadása a szervezeti csomópontok használatával, nem pedig az egyes csatornák hozzáadásával egyszerűsítheti a csatornák hozzáadását.

A következő kép egy példát mutat a szállítási módra.

![Szállítási módok beállítása](media/channel-setup-retail-7.png)

## <a name="additional-resources"></a>További erőforrások

[Csatornák beállításának előfeltételei](channels-prerequisites.md)

[Hívásközpont értékesítési funkciói](call-center-functionality.md)

[Hívásközpont rendelésfeldolgozási beállításainak meghatározása](set-up-order-processing-options.md)

[Hívásközpont-katalógusok](call-center-catalogs.md)

[Csalással kapcsolatos figyelmeztetések beállítása és használata](set-up-fraud-alerts.md)

[Folytonossági programok beállítása hívásközpontok számára](set-up-continuity-program.md)
