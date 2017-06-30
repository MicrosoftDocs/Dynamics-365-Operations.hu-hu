---
title: "Termelési rendelések létrehozása"
description: "A termelési rendelés létrehozása egy kérést kezdeményez egy cikk gyártásának az elindítására. A termelési rendelés tartalmazza azokat az információkat, hogy mit fognak gyártani, milyen mennyiségben és a mi a tervezett befejezési dátum. Azokat az információkat is tartalmazza, hogy mely anyagokat használják fel és hogy mely folyamatot kell követni a cikk előállításához."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: bcbb07553d990c35057ba32fd56d26fbc9c6f71b
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="create-production-orders"></a>Termelési rendelések létrehozása

[!include[banner](../includes/banner.md)]


A termelési rendelés létrehozása egy kérést kezdeményez egy cikk gyártásának az elindítására. A termelési rendelés tartalmazza azokat az információkat, hogy mit fognak gyártani, milyen mennyiségben és a mi a tervezett befejezési dátum. Azokat az információkat is tartalmazza, hogy mely anyagokat használják fel és hogy mely folyamatot kell követni a cikk előállításához.

A termelési megrendelés végighalad a termék életciklus-szakaszain. Amikor egy megrendelés létrejön hozzárendelődik a **Létrehozva** állapot. Amikor egy megrendelés befejeződik hozzárendelődik a **Befejezett** állapot. Minden szakaszban egy paraméter-beállítás engedélyei a felhasználónak, hogy konfigurálja az egyes lépéseket. A beállítás alkalmazható egy felhasználónak vagy az összes felhasználónak.

A termelési anyagjegyzék és a termelési útvonal a termelési megrendelés fő entitásai. A termelési megrendelésbe másolódnak a kiválasztott termelésre kerülő cikk és mennyisség alapján. Mielőtt a termelési megrendelés megkezdődik a termelési anyagjegyzék és útvonal szerkeszthető.

Egy termelési megrendelés a következő esetekben hozható létre:

-   Az alaptermelés végrehajtásával anyagi igény alapján létrehozva.
-   Közvetlenül az értékesítési megrendelés sorból vagy magasabb szintű termelési megrendelés létrejöttekor és becslésekor (rögzített készletek) létrehozva.
-   Manuálisan létrehozva.





