---
title: Váltás a szállítói arculatok között
description: Ez a cikk a szállítói adatok Finance and Operations-alkalmazások és Dataverse közötti integrációjának átváltási módjáról ad felvilágosítást.
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
ms.openlocfilehash: d2c22123d5f05945b34eb107c5b912852aec387a
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744465"
---
# <a name="switch-between-vendor-designs"></a>Váltás a szállítói arculatok között

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a>Szállítói adatok áramlása 

Ha úgy dönt, hogy a **Fiók** táblát használja a **Szervezeti** típus és a **Kapcsolattartó** tábla **Személy** típusú szállítóinak tárolásához, akkor a következő munkafolyamatokat konfigurálja. Máskülönben nem szükséges ez a konfiguráció.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a>A kibővített szállítói kialakítás használata a Szervezet típusú szállítókhoz

A **Dynamics365FinanceExtended** megoldáscsomag a következő munkafolyamat-feldolgozási sablonokat tartalmazza. Minden sablonhoz létrehoz egy munkafolyamatot.

+ Szállítók létrehozása a Partnerek táblában
+ Szállítók létrehozása a Szállítók táblában
+ Szállítók frissítése a Fiókok táblában
+ Szállítók frissítése a Szállítók táblában

A munkafolyamat-feldolgozási sablonokkal új munkafolyamat-feldolgozások létrehozásához kövesse az alábbi lépéseket:

1. Hozzon létre munkafolyamat-feldolgozást a **Szállító** táblához a **Szállítók létrehozása a partnerek táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra. Majd kattintson az **OK** lehetőségre. Ez a munkafolyamat kezeli a szállító létrehozásának menetét a **Számla** táblához.

    ![Szállítók létrehozása a Fiókok tábla munkafolyamatban](media/create_process.png)

2. Hozzon létre munkafolyamat-feldolgozást a **Szállító** táblához a **Szállítók frissítése a partnerek táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra. Majd kattintson az **OK** lehetőségre. Ez a munkafolyamat kezeli a szállító frissítésének menetét a **Számla** táblában.
3. Hozzon létre munkafolyamat-feldolgozást a **Számla** táblához a **Szállítók létrehozása a szállítók táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.
4. Hozzon létre munkafolyamat-feldolgozást a **Számla** táblához a **Szállítók frissítése a szállítók táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.
5. A munkafolyamatokat igény szerint valós idejű vagy háttérben futó munkafolyamatként állíthatja be. Ha egy munkafolyamatot háttér-munkafolyamatként szeretne beállítani, válassza az **Átalakítás háttérben futó munkafolyamattá** lehetőséget.

    ![Átalakítás háttérben futó munkafolyamattá gomb](media/background_workflow.png)

6. Aktiválja a **Fiók** és a **Szállító** táblákban létrehozott munkafolyamatokat, hogy a **Fiók** táblát használja a **Szervezet** típusú szállítókhoz.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a>A kibővített szállítói kialakítás használata a Személy típusú szállítókhoz

A **Dynamics365FinanceExtended** megoldáscsomag a következő munkafolyamat-feldolgozási sablonokat tartalmazza. Minden sablonhoz létrehoz egy munkafolyamatot.

+ Személy típusú szállítók létrehozása a Szállítók táblában
+ Személy típusú szállítók létrehozása a Kapcsolattartók táblában
+ Személy típusú szállítók frissítése a Kapcsolattartók táblában
+ Személy típusú szállítók frissítése a Szállítók táblában

A munkafolyamat-feldolgozási sablonokkal új munkafolyamat-feldolgozások létrehozásához kövesse az alábbi lépéseket:

1. Hozzon létre munkafolyamat-feldolgozást a **Szállító** táblához a **Személy típusú szállítók létrehozása a Kontaktok táblában** munkafolyamat-feldolgozási sablonban. Majd kattintson az **OK** lehetőségre. Ez a munkafolyamat kezeli a szállító létrehozásának menetét a **Kapcsolattartó** táblához.
2. Hozzon létre munkafolyamat-feldolgozást a **Szállító** táblához a **Személy típusú szállítók frissítése a Kontaktok táblában** munkafolyamat-feldolgozási sablonban. Majd kattintson az **OK** lehetőségre. Ez a munkafolyamat kezeli a szállító frissítésének menetét a **Névjegy** táblához.
3. Hozzon létre munkafolyamat-feldolgozást a **Névjegy** táblához a **Személy típusú Szállítók létrehozása a Szállítók táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.
4. Hozzon létre munkafolyamat-feldolgozást a **Névjegy** táblához a **Személy típusú Szállítók frissítése a Szállítók táblában** munkafolyamat-feldolgozási sablonban, és kattintson az OK gombra.
5. A munkafolyamatokat igény szerint valós idejű vagy háttérben futó munkafolyamatként állíthatja be. Ha egy munkafolyamatot háttér-munkafolyamatként szeretne beállítani, válassza az **Átalakítás háttérben futó munkafolyamattá** lehetőséget.
6. Aktiválja a **Névjegy** és a **Szállító** táblákban létrehozott munkafolyamatokat, hogy a **Névjegy** táblát használja a **Személy** típusú szállítókhoz.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]