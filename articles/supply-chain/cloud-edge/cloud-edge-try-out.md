---
title: Skálázási egységek kipróbálása osztott hibrid topológiában
description: Ez a cikk a gyártás- és raktárkezelési terhelések felhő- és szélskálaegységének az alkalmazásával kapcsolatban tartalmaz tájékoztatást.
author: perlynne
ms.date: 05/02/2022
ms.topic: article
ms.search.form: ScaleUnitWorkloadsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-03-03
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 5645955109e7a942e617b3b90a27065c2a8fe4a3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893584"
---
# <a name="try-out-scale-units-in-a-distributed-hybrid-topology"></a>Skálázási egységek kipróbálása osztott hibrid topológiában

[!include [banner](../includes/banner.md)]

Az elosztott topológia vizsgálatának folyamata egyszerű. Az első fokozatban ellenőrizni kell a testreszabásokat, hogy azok az elosztott topológiában működjön. Két lehetőség áll rendelkezésre.

## <a name="option-1-evaluate-customizations-in-development-environments"></a>1. beállítás: A testreszabások kiértékelése fejlesztői környezetekben

A beérkezett üzenetek környezetének a telepítése előtt ajánlott a mérlegegységeket egy fejlesztői beállításban, például egy dobozos környezetben (más néven 1. szintű környezetben) ellenőrizni, hogy érvényesíteni tudja a folyamatokat, a testreszabásokat és a megoldásokat. Ebben a fokozatban az adatok és a testreszabások alkalmazva lesznek a különálló környezetekre. Egyetlen környezetben is futtatható, amely a nagyvállalati központ és a mérlegegység szerepét is át tudja venni. Másik lehetőségként két fejlesztői környezet is lehet, amelyek közül az egyik a központ szerepe, a másik a mérlegegység szerepköre. Ez a beállítás a legjobb lehetőség a problémák azonosításához és megoldásához. A legutolsó [előnézeti](../../fin-ops-core/fin-ops/get-started/one-version.md#how-can-i-get-early-access-to-non-released-platform-updates) build is használható ennek a fokozatnak a befejezésére.

A környezetek telepítéséhez [és karbantartásához a mérlegegység-telepítési](https://github.com/microsoft/SCMScaleUnitDevTools) eszközöket egy doboz fejlesztési környezetben kell használni. Ezekkel az eszközökkel központi és mérlegegységeket konfigurálhet egy vagy két egy dobozos környezetben. Az eszközök bináris kiadásként és Forráskódként is rendelkezésre állnak a Felügyeletihubon. A projekt felmérése, amely tartalmazza az [eszközök](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide) használatát lépésről lépésre bevezető útmutatót. Ha a peremhálózati [egységeket helyi üzleti adatok alapján](cloud-edge-edge-scale-units-lbd.md) telepíti egyéni hardvereszközökre, akkor egy másik folyamatot kell követnie.

## <a name="option-2-acquire-add-ins-and-deploy-in-your-sandbox-environments"></a>2. beállítás: Bővítmények beszerzése és telepítése a beérkezett üzenetek környezetében

Az elosztott topológia kiosztásához két üzenetkészlet-környezet (2. szint) szükséges, amelyek egyike az ön adatait (nagyvállalati központ), a másik a mérleg egységét jelenti, és az "üres adatokat".

Legalább egy felhő- vagy szélskálaegységhez bővítményt kell szereznie. Ezt követően a [Microsoft Dynamics megfelelő projekt- és környezeti pontokat meg lehet adni a Lifecycle Services (LCS)](https://lcs.dynamics.com/) szolgáltatásban, [így a mérlegegység-környezeteket a Scale Unit Manager portál használatával lehet telepíteni](https://aka.ms/SCMSUM).

Forduljon a Microsoft támogatási szolgálatához, és kérje abox környezetek engedélyezéset.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
