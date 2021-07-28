---
title: Folyamatautomatizálási folyamatok meghívása minőségi rendelések létrehozásához
description: Ez a témakör olyan erőforrásokat tartalmaz, amelyekkel a Power Automate-ben, a minőségi rendelések példájának használatával automatizálhatók az üzleti folyamatok.
author: cabeln
ms.date: 05/28/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-05-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0ebb34f58a4bfbe8bda935d7b40e9d89c3dacd03
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6353988"
---
# <a name="invoke-process-automation-flows-to-create-quality-orders"></a>Folyamatautomatizálási folyamatok meghívása minőségi rendelések létrehozásához

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

A szervezetek számára egyre fontosabb a szabványos üzleti folyamatok automatizálására, a munkatársak számára biztosított kényelmesebb kommunikációs környezet, és a különféle adatjelek és rendszerek használata az üzleti folyamatok automatizálásához. A robotikus folyamatautomatizálással (RPA) és a Microsoft Power Automate rendszerrel a cégek kód nélkül automatizálhatják az ismétlődő folyamatokat, így hatékonyabbá és pontosabbá válhat a munkavégzés.

A Supply Chain Management automatizálási megoldásokhoz használható, letölthető sablonja jól példázza, hogy a Power Automate hogyan használható az üzleti folyamatok minőségi rendelések példaként való használatával történő automatizálásához.

Az automatizálási megoldás sablonja [itt](https://aka.ms/D365SCMQualityOrderRPASolution) tölthető le.

A funkció és a funkció előnyeinek ismertetése a következő videóban tekinthető meg: [Minőségi rendelések készítése a Dynamics 365 Supply Chain Management rendszerben az RPA használatával](https://www.youtube.com/watch?v=LFbzJ6-H89w)

![Az RPA automatizálási beállításai.](media/rpa-automation-options.png "Az RPA automatizálási beállításai")

A Power Automate megoldássablonja olyan felhőautomatizálási folyamatot és asztali automatizálási folyamatot tartalmaz, amely automatizálja a minőségi rendelések létrehozását a Supply Chain Management szolgáltatásban.

Az automatizálás számos eseményre és jelre – többek között felhasználó bevitelre vagy gépi jelekre (többek között az eszközök internetes hálózata) – adott válaszként indítható. A *Q-rendelés* Power Application-példa a megoldássablon része. Lehetővé teszi a felhasználó számára, hogy beolvassa egy cikk QR-kódját, megadja a mennyiséget, és képeket csatoljon kamera használatával.

Olyan megoldásparaméterek is rendelkezésre állnak, amelyekkel konfigurálni lehet egy termelési létesítményben egy adott használati esetre vonatkozó automatizálást.

![Minőségi rendelés létrehozása.](media/rpa-create-quality-roder.png "Minőségi rendelés létrehozása")

A minőségi rendelés automatizálásához használható mintamegoldás letöltésével, telepítésével és használatával kapcsolatban a következő útmutató nyújt részletes útmutatást: [Minőségi rendelés létrehozásának automatizálása a Dynamics 365 Supply Chain Management rendszerben robotikus folyamatautomatizálással a Power Automate Desktop rendszerben](/power-automate/desktop-flows/dynamics365-scm-rpa).

