---
title: "Munkaterületek konfigurálása és szűrése"
description: "Ez a cikk a munkaterületek konfigurálásáról és szűréséről nyújt áttekintést."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17491
ms.assetid: 541e6012-4680-4684-8494-e9b5ca4684ee
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: af071e009cd3f5edd918a6ab2d6d4c0119900a4e
ms.openlocfilehash: 30d86674bce2ed65b0ccdac0862f208b02b02e5c
ms.lasthandoff: 03/31/2017


---

# <a name="configure-and-filter-workspaces"></a>Munkaterületek konfigurálása és szűrése

Ez a cikk a munkaterületek konfigurálásáról és szűréséről nyújt áttekintést.

<a name="configuring-a-workspace"></a>Munkaterület konfigurációja
-----------------------

Teljes munkaterületre vonatkozó beállítások módosításával megváltoztathatja bizonyos munkaterületek megjelenését és viselkedését. Konfigurálható munkaterületek esetén a Művelet panel tartalmaz egy olyan gombot, amellyel az ott megjelenő leírás szerint megváltoztatható a konfiguráció. Például az alábbi példában a megfelelő gomb neve: **Munkaterület konfigurálása**. 

[![Állítsa be-és-szűrő-munkaterületek](./media/configure-and-filter-workspaces.png)](./media/configure-and-filter-workspaces.png)   

Amikor rákattint a gombra, megjelenik egy párbeszédpanel, ahol módosíthatja a munkaterület előre megadott beállításait. A párbeszédpanelen látható beállítási lehetőségek munkaterületenként változnak, az adott munkaterületen elérhető vezérlőktől és üzleti adatoktól függenek. 

[![konfigurálása-a-munkaterület](./media/configure-my-workspace.png)](./media/configure-my-workspace.png)

## <a name="filtering-a-workspace"></a>Egy munkaterület szűrése
Sok munkaterületen szűrhető az ott megjelenő tartalom. Az elérhető vezérlők lehetővé tehetik a munkaterület teljes tartalmának a szűrését, vagy a munkaterület egy bizonyos szakaszában lévő tartalomnak a szűrését. A munkaterület szűrői lehetnek keresések, kombinált listák, szabadszöveges mezők, vagy egyéb vezérlőtípusok. Azonban minden szűrőtípusnak ugyanolyan a hatása; ez a következő szakaszokban olvasható.

### <a name="workspace-wide-filters"></a>Munkaterület szintű szűrés

Lehetősége van az egész munkaterület szűrésére egy munkaterület szintű szűrő segítségével. A munkaterület szintű szűrő a munkaterület bal felső sarkában jelenik meg. Ha kiválaszt egy konkrét értéket a legördülő menüből, a munkaterületen lévő tartalom a kiválasztott érték szerinti szűrés alapján rendeződik át. 

[![munkaterület-szűrő](./media/workspace-filter.png)](./media/workspace-filter.png) 

Kattintással megnyílik a szűrő; ezután több lehetőség közül választhat. 

[![munkaterület-szűrő-bővített](./media/workspace-filter-expanded.png)](./media/workspace-filter-expanded.png) 

Válasszon ki egy lehetőséget, amely alapján szűrni kívánja a munkaterületet.

### <a name="workspace-section-filters"></a>Munkaterület szakasz szűrők

Ha a munkaterület szakaszai rendelkeznek saját szűrővel, az egyes szakaszok külön-külön is szűrhetők. A következő ábra a szabadszöveges mező típusú szűrőre mutat példát (a szűrő az a mező, amely a „Szűrő” szöveget tartalmazza). 

[![munkaterület-szakasz-szűrők](./media/workspace-section-filters.png)](./media/workspace-section-filters.png) 

Ahogyan a munkaterület szintű szűrőnél, itt is válassza ki vagy adja meg azt az értékét, amely alapján a szakasz tartalmát szűkíteni kívánja.


