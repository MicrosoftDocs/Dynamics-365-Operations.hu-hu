---
title: Konfigurációszolgáltatók létrehozása és megjelölése aktívként
description: Ez a cikk bemutatja, hogy hogyan hozhatnak létre konfigurációs szolgáltatót a rendszergazdai vagy elektronikus jelentéskészítő szerepkörbe bekészítő felhasználók.
author: kfend
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
ms.openlocfilehash: db5226720a4e0c0f167921a972429c0a5ecdd2e9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267813"
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
