---
title: Termelési rendelés életciklusának áttekintése
description: A termelési rendelés létrehozása egy kérést kezdeményez egy cikk gyártásának az elindítására. A termelési rendelés tartalmazza azokat az információkat, hogy mit fognak gyártani, milyen mennyiségben és a mi a tervezett befejezési dátum. Azokat az információkat is tartalmazza, hogy mely anyagokat használják fel és hogy mely folyamatot kell követni a cikk előállításához.
author: johanhoffmann
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80031737ab0d0c4ab1e4dbd5646ad91f1a010cd5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429663"
---
# <a name="production-order-lifecycle-overview"></a>Termelési rendelés életciklusának áttekintése

[!include [banner](../includes/banner.md)]

A termelési rendelés létrehozása egy kérést kezdeményez egy cikk gyártásának az elindítására. A termelési rendelés tartalmazza azokat az információkat, hogy mit fognak gyártani, milyen mennyiségben és a mi a tervezett befejezési dátum. Azokat az információkat is tartalmazza, hogy mely anyagokat használják fel és hogy mely folyamatot kell követni a cikk előállításához.

A termelési megrendelés végighalad a termék életciklus-szakaszain. Amikor egy megrendelés létrejön hozzárendelődik a **Létrehozva** állapot. Amikor egy megrendelés befejeződik hozzárendelődik a **Befejezett** állapot. Minden szakaszban egy paraméter-beállítás engedélyei a felhasználónak, hogy konfigurálja az egyes lépéseket. A beállítás alkalmazható egy felhasználónak vagy az összes felhasználónak.

A termelési anyagjegyzék és a termelési útvonal a termelési megrendelés fő entitásai. A termelési megrendelésbe másolódnak a kiválasztott termelésre kerülő cikk és mennyisség alapján. Mielőtt a termelési megrendelés megkezdődik a termelési anyagjegyzék és útvonal szerkeszthető.

Egy termelési megrendelés a következő esetekben hozható létre:

-   Az alaptermelés végrehajtásával anyagi igény alapján létrehozva.
-   Közvetlenül az értékesítési megrendelés sorból vagy magasabb szintű termelési megrendelés létrejöttekor és becslésekor (rögzített készletek) létrehozva.
-   Manuálisan létrehozva.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]