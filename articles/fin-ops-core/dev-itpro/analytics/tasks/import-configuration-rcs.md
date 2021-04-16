---
title: (ER) Konfigurációk importálása RCS-ből
description: Ez a témakör azt mutatja be, hogyan képes a felhasználó az RCS-ből egy ER-konfiguráció új verzióját importálni.
author: NickSelin
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 77d637b2ec1deeabc04a6796644363b330f5756e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744891"
---
# <a name="er-import-configurations-from-rcs"></a>(ER) Konfigurációk importálása RCS-ből

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként importálhat új Elektronikus jelentés (ER) konfigurációt a Microsoft Regulatory Configuration Services (RCS) rendszerből. Ebben a példában kiválasztja majd az ER-konfiguráció adott verzióját, amelyet egy RCS-példányban konfigurált, és importálja a mintavállalat, a Litware Inc. aktuális példányába. Ezeket a lépéseket bármilyen vállalatban végre lehet hajtani, mivel az ER-konfigurációk megoszthatók vállalatok között. Az alábbi lépések végrehajtásához először hajtsa végre a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) cikk lépéseit. Ezeknek a lépéseknek a végrehajtásához hozzáféréssel kell rendelkeznie egy olyan RCS-példányhoz is, amely legalább egy ER-konfigurációt tartalmaz vagy **Befejezett** vagy **Megosztott** állapotban.

1. Lépjen a **Szervezeti adminisztráció** > **Munkaterületek** > **Elektronikus jelentés** részre. 
2. Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) témakör lépéseit. 
3. Ha nincs RCS környezete a vállalathoz, válassza a **Regulatory services – Konfiguráció** külső hivatkozást, és kövesse az RCS-környezet létrehozására vonatkozó instrukciókat. 
4. Válassza az **Elektronikus jelentéskészítés paraméterei** elemet. 
5. Válassza az **RCS** fület. 
6. Ha a RCS környezet már ki lett építve a vállalatnál, akkor a lapon megjelenő URL-címen érheti el. 
7. Zárja be a lapot. 

## <a name="register-a-new-er-repository"></a>Új ER-tárház regisztrálása. 
1. A listában jelölje meg a kiválasztott sort. 
2. Válassza ki a Litware, Inc. szolgáltatót. 
3. Válassza ki a Tárházak lehetőséget. 
4. A Hozzáadás gombra kattintva nyissa meg a legördülő párbeszédpanelt. 
5. A Konfiguráció tárházának típusa mezőbe írja be az „RCS” értéket. 
6. Válassza a Tárház létrehozása lehetőséget. 
7. Az RCS környezet megjelenítése mezőben adjon meg vagy válasszon ki egy értéket. 
8. Válassza ki a kívánt RCS-példányt. Több ilyen is lehet. 
9. Válassza ki az OK lehetőséget. 

## <a name="import-er-configurations-from-rcs-based-repository"></a>ER-konfigurációk importálása az RCS-alapú tárházból
1. Válassza ki a **Szűrők megjelenítése** elemet. 
2. Adja meg az „RCS” szűrőértéket a **Név** mezőben az **ezzel kezdődik** szűrési operátor használatával. 
3. Amikor megnyitja a kiválasztott tárházat a **Csatlakozás a Regulatory Configuration Services szolgáltatáshoz** oldalon, válassza az **Ide kattintva csatlakozhat a Regulatory Configuration Services szolgáltatáshoz** hivatkozást. 
4. Válassza ki a **Megnyitás** lehetőséget. 
5. Válassza **Bezárás** lehetőséget. 
6. Válassza ki az ER-konfiguráció kívánt verzióját, és válassza az **Importálás** lehetőséget az aktuális példányba való behúzáshoz.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]