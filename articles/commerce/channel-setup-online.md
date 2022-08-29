---
title: Online csatorna beállítása
description: Ez a témakör azt ismerteti, hogyan lehet új online csatornát létrehozni a Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 02/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: be9fafe8ece771ad6577db1cdb70af6f48e054cc
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272880"
---
# <a name="set-up-an-online-channel"></a>Online csatorna beállítása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet új online csatornát létrehozni a Microsoft Dynamics 365 Commerce.

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

![Új online csatorna.](media/channel-setup-online-1.png)

A következő kép egy példát mutat a online csatornára.

![Online csatorna – példa.](media/channel-setup-online-2.png)

## <a name="assign-the-channel-to-a-commerce-scale-unit"></a>Csatorna hozzárendelése Commerce Scale Unit egységhez

Az új csatornát hozzá kell rendelni egy Commerce Scale Unit egységhez. Az utasításokat lásd a [Csatornák konfigurálása a Commerce Scale Unit használatával való használatra](../fin-ops-core/dev-itpro/deployment/initialize-retail-channels.md#configure-channels-to-use-commerce-scale-unit).

## <a name="set-up-languages"></a>Nyelvek beállítása

Ha az e-Commerce webhely több nyelvet is támogat, bontsa **ki a Nyelvek** szakaszt, és szükség szerint adjon meg további nyelveket.

## <a name="set-up-payment-account"></a>Fizetési számla beállítása

A **fizetési számla** szakaszból kiválaszthatja azt a külső fél fizetési szolgáltatót. Az Adyen fizetési összekötő beállításával kapcsolatos tudnivalókat lásd: [Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](./dev-itpro/adyen-connector.md).

## <a name="additional-channel-setup"></a>További csatornák beállítása

Az online csatorna beállításához szükséges további feladatok közé tartozik a fizetési módok, szállítási módok és a teljesítési csoport hozzárendelésének beállítása.

A következő képen láthatók a **Szállítási módok**, a **Fizetési módok** és a **Teljesítési csoport hozzárendelése** beállított lehetőségei a **Beállítás** lapon.

![További onlinecsatorna-beállítási műveletek.](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a>Fizetési módok beállítása

A fizetési módok beállításához a csatornán támogatott valamennyi fizetési típusnál kövesse az alábbi lépéseket.

1. A műveleti ablaktáblán válassza a **Beállítás** lapot, majd válassza ki a **Fizetési módokat**.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A navigációs ablakban válassza ki a kívánt fizetési módot.
1. Az **általános** szakaszban adjon meg egy **művelet nevét**, és adja meg a kívánt beállításokat.
1. Adja meg a fizetési típushoz szükséges további beállításokat.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A következő kép egy példát mutat a készpénzfizetési módra.

![Fizetési módok – példa.](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a>Szállítási módok beállítása

A konfigurált szállítási módokat a **Szállítási módok** kiválasztásával tekintheti meg a **Beállítás** lapon a **Műveleti ablaktáblán**.  

Szállítási mód módosításához vagy hozzáadásához kövesse az alábbi lépéseket.

1. A navigációs ablakban nyissa meg a **Modulok \> Készletkezelés \> Szállítási módok** elemet.
1. A műveleti ablaktáblán válassza az **Új** elemet új szállítási mód létrehozásához, vagy válasszon meglévő módot.
1. A **kiskereskedelmi csatornák** területen válassza a **sor hozzáadása** parancsot a csatorna hozzáadásához. Csatornák hozzáadása a szervezeti csomópontok használatával, nem pedig az egyes csatornák hozzáadásával egyszerűsítheti a csatornák hozzáadását.

A következő kép egy példát mutat a szállítási módra.

![Szállítási módok beállítása.](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a>Teljesítési csoport hozzárendelésének beállítása

A teljesítési csoport hozzárendelésének beállításához tegye a következőket.

1. A műveleti ablaktáblán válassza a **Beállítás** lapot, és válassza ki a **Teljesítési csoport hozzárendelése**.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A **teljesítési csoport** legördülő listából válassza ki a teljesítési csoportot.
1. Ha a **Leírás** legördülő listában adjon meg egy leírást.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A következő kép egy példát mutat be a teljesítési csoport hozzárendelésének beállítására.

![Teljesítési csoport hozzárendelésének beállítása.](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a>További erőforrások

[Csatornák áttekintése](channels-overview.md)

[Csatorna beállításainak előfeltételei](channels-prerequisites.md)

[Kiskereskedelmi csatorna beállítása](channel-setup-retail.md)

[Hívásközpont csatorna beállítása](channel-setup-callcenter.md)

[Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](./dev-itpro/adyen-connector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
