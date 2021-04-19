---
title: Online csatorna beállítása
description: Ez a témakör azt mutatja be, hogyan lehet egy új online csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b6bf158361f95b6551b29f195616cf21f908b802
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800639"
---
# <a name="set-up-an-online-channel"></a>Online csatorna beállítása


[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet egy új online csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A Dynamics 365 Commerce rendszer támogatja a többszörös kiskereskedelmi csatornák használatát. Ezek a kiskereskedelmi csatornák lehetnek online áruházak, hívásközpontok és kiskereskedelmi áruházak (más néven rendes, nem online üzletek). Az online áruházak segítségével a vevők a kiskereskedelmi üzletek mellett a kiskereskedőtől online is vásárolhatnak termékeket.

A Commerce online áruház létrehozásához először létre kell hoznia egy online csatornát. Új online csatorna létrehozása előtt győződjön meg arról, hogy végrehajtotta a [Csatornbeállítás előfeltételeit](channels-prerequisites.md).

Új webhely létrehozása előtt legalább egy online áruházat létre kell hoznia a Commerce alkalmazásban. További információért lásd: [E-kereskedelmi webhely létrehozása](create-ecommerce-site.md).

## <a name="create-and-configure-a-new-online-channel"></a>Új online csatorna létrehozása és konfigurálása

Új online csatorna létrehozásához és konfigurálásához kövesse ezeket a lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Csatornák \> Online áruházak** részhez.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Név** mezőben adja meg az új csatorna nevét.
1. A **jogi személy** legördülő listában adja meg a megfelelő jogi személyt.
1. A **raktár** legördülő listában adja meg a megfelelő raktárat.
1. Az **Üzlet időzónája** mezőből válasszon egy megfelelő időzónát.
1. A **Pénznem** mezőben válassza ki a megfelelő pénznemet.
1. Az **Alapértelmezett ügyfél** mezőben adjon meg egy érvényes alapértelmezett ügyfelet.
1. Az **Ügyfél címjegyzéke** mezőben adjon meg érvényes címjegyzéket.
1. A **Funkcióprofil** mezőben válasszon ki egy funkcióprofilt, ha van ilyen.
1. Az **E-mail értesítési profilja** mezőben adjon meg egy érvényes e-mail-értesítési profilt.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A következő kép bemutatja egy új online csatorna létrehozását.

![Új online csatorna](media/channel-setup-online-1.png)

A következő kép egy példát mutat a online csatornára.

![Online csatorna – példa](media/channel-setup-online-2.png)

## <a name="set-up-languages"></a>Nyelvek beállítása

Ha az e-kereskedelmi webhely több nyelvet is támogat, bontsa ki a **Nyelvek** szakaszt, és szükség esetén adja meg a további nyelveket.

## <a name="set-up-payment-account"></a>Fizetési számla beállítása

A **fizetési számla** szakaszból kiválaszthatja azt a külső fél fizetési szolgáltatót. Az Adyen fizetési összekötő beállításával kapcsolatos tudnivalókat lásd: [Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](../retail/dev-itpro/adyen-connector.md).

## <a name="additional-channel-setup"></a>További csatornák beállítása

Az online csatorna beállításához szükséges további feladatok közé tartozik a fizetési módok, szállítási módok és a teljesítési csoport hozzárendelésének beállítása.

A következő képen láthatók a **Szállítási módok**, a **Fizetési módok** és a **Teljesítési csoport hozzárendelése** beállított lehetőségei a **Beállítás** lapon.

![További online csatorna-beállítási műveletek](media/channel-setup-online-3.png)

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

### <a name="set-up-a-fulfillment-group-assignment"></a>Teljesítési csoport hozzárendelésének beállítása

A teljesítési csoport hozzárendelésének beállításához tegye a következőket.

1. A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **Teljesítési csoport hozzárendelése**.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A **teljesítési csoport** legördülő listából válassza ki a teljesítési csoportot.
1. Ha a **Leírás** legördülő listában adjon meg egy leírást.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A következő kép egy példát mutat be a teljesítési csoport hozzárendelésének beállítására.

![Teljesítési csoport hozzárendelésének beállítása](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a>További erőforrások

[Csatornák áttekintése](channels-overview.md)

[Csatornák beállításának előfeltételei](channels-prerequisites.md)

[Kiskereskedelmi csatorna beállítása](channel-setup-retail.md)

[Hívásközpont csatorna beállítása](channel-setup-callcenter.md)

[Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](../retail/dev-itpro/adyen-connector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]