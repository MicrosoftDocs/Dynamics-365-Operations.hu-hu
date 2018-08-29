--- 
title: "Konfigurációszolgáltatók létrehozása, és megjelölésük aktívként"
description: "A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER)."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 37957f224cb57fd9f6c5014740bcea124a99a03a
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Konfigurációszolgáltatók létrehozása, és megjelölésük aktívként

[!include [task guide banner](../../includes/task-guide-banner.md)]

A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER). Minden egyes ER konfiguráció a konfiguráció szerzőjeként hivatkozik a szolgáltatóra. Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket minden vállalat minden vállalat között megosztott ER konfigurációs szolgáltatókként hajthatók végre az egyes vállalatoknál.


## <a name="create-a-provider"></a>Szolgáltató létrehozása
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. Kattintson a konfigurációszolgáltatókra.
3. Kattintson az Új lehetőségre.
    * Egy szolgáltató rekord egyedi névvel és URL-címmel rendelkezik. Tekintse át ezen oldal tartalmát és ugorja át ezt az eljárást, ha a rekord a Litware, Inc. (`http://www.litware.com`) számára már létezik.  
4. A Név mezőbe írja be a „Litware, Inc.” nevet.
    * Litware, Inc.  
5. Írja be a `http://www.litware.com` értéket az Internetcím mezőbe.
6. Kattintson a Mentés gombra.
7. Zárja be a lapot.

## <a name="select-as-an-active-provider"></a>Kiválasztás aktív szolgáltatónak
1. Válassza ki a „Litware, Inc.” szolgáltatót.
2. Kattintson erre: Beállítás aktívként.


