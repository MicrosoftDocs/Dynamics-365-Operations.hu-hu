---
title: (ER) Konfigurációk importálása RCS-ből
description: Ez a témakör azt mutatja be, hogyan képes a felhasználó az RCS-ből egy ER-konfiguráció új verzióját importálni.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32c9c17d8b63e4c0806559c2dcc2e11ae9825a53
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184623"
---
# <a name="er-import-configurations-from-rcs"></a>(ER) Konfigurációk importálása RCS-ből

[!include [task guide banner](../../includes/task-guide-banner.md)]

A következő lépések leírják, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként importálhat új Elektronikus jelentés (ER) konfigurációt a Microsoft Regulatory Configuration Services (RCS) rendszerből. Ebben a példában kiválasztja majd az ER-konfiguráció adott verzióját, amelyet egy RCS-példányban konfigurált, és importálja a mintavállalat, a Litware Inc. aktuális példányába. Ezeket a lépéseket bármilyen vállalatban végre lehet hajtani, mivel az ER-konfigurációk megoszthatók vállalatok között. Az alábbi lépések végrehajtásához először hajtsa végre a [Konfigurációszolgáltató létrehozása és aktívként történő megjelölése](er-configuration-provider-mark-it-active-2016-11.md) témakör lépéseit. Ezeknek a lépéseknek a végrehajtásához hozzáféréssel kell rendelkeznie egy olyan RCS-példányhoz is, amely legalább egy ER-konfigurációt tartalmaz vagy **Befejezett** vagy **Megosztott** állapotban.

1. Lépjen a **Szervezeti adminisztráció** > **Munkaterületek** > **Elektronikus jelentés** részre. 
2. Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltató létrehozása, és megjelölés aktívként](er-configuration-provider-mark-it-active-2016-11.md) témakörben szereplő lépéseket. 
3. Ha nincs RCS környezete a vállalathoz, kattintson a **Regulatory services – Konfiguráció** külső hivatkozásra, és kövesse az RCS-környezet létrehozására vonatkozó instrukciókat. 
4. Kattintson az **Elektronikus jelentéskészítés paraméterei** elemre. 
5. Kattintson az **RCS** lapra. 
6. Ha a RCS környezet már ki lett építve a vállalatnál, akkor a lapon megjelenő URL-címen érheti el. 
7. Zárja be a lapot. 

## <a name="register-a-new-er-repository"></a>Új ER-tárház regisztrálása. 
1. A listában jelölje meg a kiválasztott sort. 
2. Válassza ki a Litware, Inc. szolgáltatót. 
3. Kattintson a Tárházak gombra. 
4. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt. 
5. A Konfiguráció tárházának típusa mezőbe írja be az „RCS” értéket. 
6. Kattintson a Tárház létrehozása lehetőségre. 
7. Az RCS környezet megjelenítése mezőben adjon meg vagy válasszon ki egy értéket. 
8. Válassza ki a kívánt RCS-példányt. Ne feledje, hogy több is lehet. 
9. Kattintson az OK gombra. 

## <a name="import-er-configurations-from-rcs-based-repository"></a>ER-konfigurációk importálása az RCS-alapú tárházból
1. Kattintson a **Szűrők megjelenítése** pontra. 
2. Adja meg az „RCS” szűrőértéket a **Név** mezőben az **ezzel kezdődik** szűrési operátor használatával. 
3. Amikor megnyitja a kiválasztott tárházat a **Csatlakozás a Regulatory Configuration Services szolgáltatáshoz** oldalon, kattintson az **Ide kattintva csatlakozhat a Regulatory Configuration Services szolgáltatáshoz** hivatkozásra. 
4. Kattintson a **Megnyitás** gombra. 
5. Kattintson a **Bezárás** gombra. 
6. Válassza ki az ER-konfiguráció kívánt verzióját, és kattintson az **Importálás** lehetőségre az aktuális példányba való behúzáshoz.

