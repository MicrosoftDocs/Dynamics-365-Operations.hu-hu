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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 587a9b98f28b11e303aff4b59e9726f220d956eb
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019813"
---
# <a name="switch-between-vendor-designs"></a>Váltás a szállítói arculatok között

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

## <a name="vendor-data-flow"></a>Szállítói adatok áramlása 

Ha a szállítói alapadatokhoz más Dynamics 365-alkalmazásokat szeretne használni, és el szeretné különíteni a szállítók adatait a vevőktől, akkor használhatja a szállítói alapkialakítást.  

![Alapszintű szállítói folyamat](media/dual-write-vendor-data-flow.png)
 
Ha a szállítói alapadatokhoz más Dynamics 365-alkalmazásokat szeretné használni, és továbbra is a **Számla** entitást szeretné használni a szállítók adatainak tárolásához; használhatja ezt a bővített szállítói kialakítást. Ebben a kialakításban a bővített szállítói adatokat, például a szállító várakoztatott állapotát vagy a szállítói profilt a **szállítók** entitásban tárolja a Common Data Service. 

![Bővített szállítói folyamat](media/dual-write-vendor-detail.jpg)
 
A bővített szállítói kialakítás használatához hajtsa végre az alábbi lépéseket: 
 
1. A **SupplyChainCommon** megoldáscsomag a következő képen látható munkafolyamat-feldolgozási sablonokat tartalmazza.
    > [!div class="mx-imgBorder"]
    > ![Munkafolyamat-feldolgozási sablonok](media/dual-write-switch-3.png)
2. A munkafolyamat-feldolgozási sablonokkal hozzon létre új munkafolyamat-feldolgozásokat: 
    1. Hozzon létre új munkafolyamat-feldolgozást a **Szállító** entitáshoz a **Szállítók létrehozása a számlaentitásban** munkafolyamat-feldolgozási sablonban, és kattintson az **OK** gombra. Ez a munkafolyamat kezeli a szállító létrehozásának menetét a **Számla** entitáshoz.
        > [!div class="mx-imgBorder"]
        > ![Szállítók létrehozása a számlaentitásban](media/dual-write-switch-4.png)
    2. Hozzon létre új munkafolyamat-feldolgozást a **Szállító** entitáshoz a **Számlák entitás frissítése** munkafolyamat-feldolgozási sablonban, és kattintson az **OK** gombra. Ez a munkafolyamat kezeli a szállító frissítésének menetét a **Számla** entitáshoz. 
        > [!div class="mx-imgBorder"]
        > ![A Számlák entitás frissítése](media/dual-write-switch-5.png)
    3. Hozzon létre új munkafolyamat-feldolgozásokat a **Számlák** entitáson létrehozott sablonokból. 
        > [!div class="mx-imgBorder"]
        > ![Szállítók létrehozása a szállítóentitásban](media/dual-write-switch-6.png)
        > [!div class="mx-imgBorder"]
        > ![Szállítók entitásának frissítése](media/dual-write-switch-7.png)
    4. A munkafolyamatokat igény szerint valós idejű vagy háttérben futó munkafolyamatként állíthatja be. 
        > [!div class="mx-imgBorder"]
        > ![Átalakítás háttérben futó munkafolyamattá](media/dual-write-switch-8.png)
    5. Aktiválja a **Számla** és a **Szállító** entitáson létrehozott munkafolyamatokat, hogy a **Számla** entitását használja majd a szállítói adatok tárolásához. 
 
