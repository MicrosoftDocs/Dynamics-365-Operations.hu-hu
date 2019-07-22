---
title: Konfigurációszolgáltatók létrehozása és megjelölése aktívként
description: A témakör leírja, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER) a Dynamics 365 for Finance and Operations alkalmazásban.
author: NickSelin
manager: AnnBe
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e02cd51478528db56a4f50b134fabf7f9e1dc8ea
ms.sourcegitcommit: a1354c6218b328d4d7dcc149d1339a7af10c48bf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2019
ms.locfileid: "1723120"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Konfigurációszolgáltatók létrehozása és megjelölése aktívként

[!include [task guide banner](../../includes/task-guide-banner.md)]

A témakör leírja, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER) a Dynamics 365 for Finance and Operations alkalmazásban. Minden egyes ER konfiguráció a konfiguráció szerzőjeként hivatkozik a szolgáltatóra. Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket minden vállalat minden vállalat között megosztott ER konfigurációs szolgáltatókként hajthatók végre az egyes vállalatoknál.

## <a name="create-a-provider"></a>Szolgáltató létrehozása
1. Nyissa meg a bal felső sarokban látható **navigációs ablaktáblát**, és válassza ki a **Szervezet adminisztrációját**.
2. Ugorjon a **Munkaterületek > Elektronikus jelentés** pontra.
3. Ugrás a **Kapcsolódó linkek > Konfigurációs szolgáltatók** pontra.
4. Válassza az **Új** lehetőséget.
    - Egy szolgáltató rekord egyedi névvel és URL-címmel rendelkezik. Tekintse át ezen oldal tartalmát és ugorja át ezt az eljárást, ha a rekord a Litware, Inc. (https://www.litware.com) számára már létezik.  
5. A Név mezőbe írja be a „`Litware, Inc.`” szöveget.
6. Írja be a `https://www.litware.com` értéket az internetcím mezőbe.
7. Válassza a **Mentés** lehetőséget.
8. Zárja be a lapot.

## <a name="select-as-an-active-provider"></a>Kiválasztás aktív szolgáltatónak
1. Válassza ki a „Litware, Inc.” szolgáltatót.
2. Válassza ki az **Aktív beállítása** elemet.

