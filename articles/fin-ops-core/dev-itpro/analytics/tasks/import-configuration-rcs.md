---
title: (ER) Konfigurációk importálása RCS-ből
description: Ez a cikk arról nyújt tájékoztatást, hogyan importálhat egy felhasználó egy ER-konfiguráció új verzióját az RCS rendszerből.
author: kfend
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ''
ms.openlocfilehash: 55e7a3ae23b708acecb5ac219b885f43b4c7aa0a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290034"
---
# <a name="er-import-configurations-from-rcs"></a>(ER) Konfigurációk importálása RCS-ből

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként importálhat új Elektronikus jelentés (ER) konfigurációt a Microsoft Regulatory Configuration Services (RCS) rendszerből. Ebben a példában kiválasztja majd az ER-konfiguráció adott verzióját, amelyet egy RCS-példányban konfigurált, és importálja a mintavállalat, a Litware Inc. aktuális példányába. Ezeket a lépéseket bármilyen vállalatban végre lehet hajtani, mivel az ER-konfigurációk megoszthatók vállalatok között. Ezeket a lépéseket csak akkor lehet végrehajtani, ha előbb a cikk lépéseit létrehozza, [majd aktívként megjelöli őket](er-configuration-provider-mark-it-active-2016-11.md). Ezeknek a lépéseknek a végrehajtásához hozzáféréssel kell rendelkeznie egy olyan RCS-példányhoz is, amely legalább egy ER-konfigurációt tartalmaz vagy **Befejezett** vagy **Megosztott** állapotban.

1. Lépjen a **Szervezeti adminisztráció** > **Munkaterületek** > **Elektronikus jelentés** részre. 
2. Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató. Ha nem látja ezt a konfigurációs szolgáltatót, a következő lépésekkel hozza létre a konfigurációs szolgáltatókat, [és jelölje meg aktívként](er-configuration-provider-mark-it-active-2016-11.md). 
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
