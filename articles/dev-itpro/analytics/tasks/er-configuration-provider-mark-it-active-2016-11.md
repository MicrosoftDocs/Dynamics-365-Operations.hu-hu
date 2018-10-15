--- 
title: "Konfigurációszolgáltatók létrehozása, és megjelölésük aktívként"
description: "A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER)."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 13a27c2fec2a2b226e9ae8d5b8f9a61e8b79ceb0
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Konfigurációszolgáltatók létrehozása, és megjelölésük aktívként

[!include [task guide banner](../../includes/task-guide-banner.md)]

A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER). Minden egyes ER konfiguráció a konfiguráció szerzőjeként hivatkozik a szolgáltatóra. Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket minden vállalat minden vállalat között megosztott ER konfigurációs szolgáltatókként hajthatók végre az egyes vállalatoknál.


## <a name="create-a-provider"></a>Szolgáltató létrehozása
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. Kattintson a konfigurációszolgáltatókra.
3. Kattintson az Új lehetőségre.
    * Egy szolgáltató rekord egyedi névvel és URL-címmel rendelkezik. Tekintse át ezen oldal tartalmát és ugorja át ezt az eljárást, ha a rekord a Litware, Inc. (http://www.litware.com) számára már létezik.  
4. A Név mezőbe írja be a „Litware, Inc.” nevet.
    * Litware, Inc.  
5. Írja be a(z) „http://www.litware.com” értéket az internetcím mezőbe.
    * http://www.litware.com  
6. Kattintson a Mentés gombra.
7. Zárja be a lapot.

## <a name="select-as-an-active-provider"></a>Kiválasztás aktív szolgáltatónak
1. Válassza ki a „Litware, Inc.” szolgáltatót.
2. Kattintson erre: Beállítás aktívként.


