---
title: Váltás a szállítói arculatok között
description: Ez a cikk a szállítói adatok Finance and Operations-alkalmazások és Common Data Service közötti integrációjának átváltási módjáról ad felvilágosítást.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 0ecc401706911f8b92146b95bb6415185df8b451
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997552"
---
# <a name="switch-between-vendor-designs"></a>Váltás a szállítói arculatok között

[!include [banner](../../includes/banner.md)]



## <a name="vendor-data-flow"></a>Szállítói adatok áramlása 

Ha úgy dönt, hogy a **Fiók** entitást használja a **Szervezeti** típus és a **Kapcsolattartó** entitás **Személy** típusú szállítóinak tárolásához, akkor a következő munkafolyamatokat konfigurálja. Máskülönben nem szükséges ez a konfiguráció.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a>A kibővített szállítói kialakítás használata a Szervezet típusú szállítókhoz

A **Dynamics365FinanceExtended** megoldáscsomag a következő munkafolyamat-feldolgozási sablonokat tartalmazza. Minden sablonhoz létrehoz egy munkafolyamatot.

+ Szállítók létrehozása a Fiókok entitásban
+ Szállítók létrehozása a Szállítók entitásban
+ Szállítók frissítése a Fiókok entitásban
+ Szállítók frissítése a Szállítók entitásban

A munkafolyamat-feldolgozási sablonokkal új munkafolyamat-feldolgozások létrehozásához kövesse az alábbi lépéseket:

1. Hozzon létre munkafolyamat-feldolgozást a **Szállító** entitáshoz a **Szállítók létrehozása a fiókentitásban** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra. Majd kattintson az **OK** lehetőségre. Ez a munkafolyamat kezeli a szállító létrehozásának menetét a **Számla** entitáshoz.

    ![Szállítók létrehozása a Fiókok entitás munkafolyamatban](media/create_process.png)

2. Hozzon létre munkafolyamat-feldolgozást a **Szállító** entitáshoz a **Szállítók frissítése a fiókentitásban** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra. Majd kattintson az **OK** lehetőségre. Ez a munkafolyamat kezeli a szállító frissítésének menetét a **Számla** entitáshoz.
3. Hozzon létre munkafolyamat-feldolgozást a **Fiók** entitáshoz a **Szállítók létrehozása a Szállítók entitásban** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.
4. Hozzon létre munkafolyamat-feldolgozást a **Fiók** entitáshoz a **Szállítók frissítése a Szállítók entitásban** munkafolyamat-feldolgozási sablonban.
5. A munkafolyamatokat igény szerint valós idejű vagy háttérben futó munkafolyamatként állíthatja be. Ha egy munkafolyamatot háttér-munkafolyamatként szeretne beállítani, válassza az **Átalakítás háttérben futó munkafolyamattá** lehetőséget.

    ![Átalakítás háttérben futó munkafolyamattá gomb](media/background_workflow.png)

6. Aktiválja a **Fiók** és a **Szállító** entitáson létrehozott munkafolyamatokat, hogy a **Fiók** entitást használja a **Szervezet** típusú szállítókhoz.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a>A kibővített szállítói kialakítás használata a Személy típusú szállítókhoz

A **Dynamics365FinanceExtended** megoldáscsomag a következő munkafolyamat-feldolgozási sablonokat tartalmazza. Minden sablonhoz létrehoz egy munkafolyamatot.

+ Személy típusú szállítók létrehozása a Szállítók entitásban
+ Személy típusú szállítók létrehozása a Kontaktok entitásban
+ Személy típusú szállítók frissítése a Kontaktok entitásban
+ Személy típusú szállítók frissítése a Szállítók entitásban

A munkafolyamat-feldolgozási sablonokkal új munkafolyamat-feldolgozások létrehozásához kövesse az alábbi lépéseket:

1. Hozzon létre munkafolyamat-feldolgozást a **Szállító** entitáshoz a **Személy típusú szállítók létrehozása a Kontaktok entitásban** munkafolyamat-feldolgozási sablonban. Majd kattintson az **OK** lehetőségre. Ez a munkafolyamat kezeli a szállító létrehozásának menetét a **Kapcsolattartó** entitáshoz.
2. Hozzon létre munkafolyamat-feldolgozást a **Szállító** entitáshoz a **Személy típusú szállítók frissítése a Kapcsolattartók entitásban** munkafolyamat-feldolgozási sablonban. Majd kattintson az **OK** lehetőségre. Ez a munkafolyamat kezeli a szállító frissítésének menetét a **Névjegy** entitáshoz.
3. Hozzon létre munkafolyamat-feldolgozást a **Névjegy** entitáshoz a **Személy típusú Szállítók létrehozása a Szállítók entitásban** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.
4. Hozzon létre munkafolyamat-feldolgozást a **Névjegy** entitáshoz a **Személy típusú Szállítók frissítése a Szállítók entitásban** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.
5. A munkafolyamatokat igény szerint valós idejű vagy háttérben futó munkafolyamatként állíthatja be. Ha egy munkafolyamatot háttér-munkafolyamatként szeretne beállítani, válassza az **Átalakítás háttérben futó munkafolyamattá** lehetőséget.
6. Aktiválja a **Névjegy** és a **Szállító** entitáson létrehozott munkafolyamatokat, hogy a **Névjegy** entitást használja a **Személy** típusú szállítókhoz.
