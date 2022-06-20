---
title: Konfigurációszolgáltatók létrehozása és megjelölése aktívként
description: Ez a cikk bemutatja, hogy hogyan hozhatnak létre konfigurációs szolgáltatót a rendszergazdai vagy elektronikus jelentéskészítő szerepkörbe bekészítő felhasználók.
author: NickSelin
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 93c2e114c97290347b71e94d87ea5339688791cc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883596"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Konfigurációszolgáltatók létrehozása és megjelölése aktívként

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan hozhat létre az elektronikus jelentéskészítő (ER) konfigurációs szolgáltatót a Rendszergazda vagy elektronikus jelentéskészítő fejlesztő szerepkör egyik felhasználója. Minden egyes ER konfiguráció a konfiguráció szerzőjeként hivatkozik a szolgáltatóra. Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket minden vállalat minden vállalat között megosztott ER konfigurációs szolgáltatókként hajthatók végre az egyes vállalatoknál.

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

![Elektronikus jelentések munkaterületoldala.](../media/GER-Task-ActiveProvider-1.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]