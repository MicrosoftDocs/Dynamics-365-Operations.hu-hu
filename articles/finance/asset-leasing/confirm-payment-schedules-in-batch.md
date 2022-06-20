---
title: Eszközlízing fizetési ütemezések megerősítése kötegben
description: Ez a cikk bemutatja, hogyan lehet egy kötegben több fizetési ütemezést megerősíteni.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePaymConfirmationDetails
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: bd75e22f6407d6bc25a78c1dfeacf70022238e94
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895051"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a>Eszközlízing fizetési ütemezések megerősítése kötegben

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet egy kötegben több fizetési ütemezést megerősíteni. A kifizetési ütemezéseket vagy a lízingtől-lízingig alapján vagy a megerősítési köteg folyamatán keresztül lehet megerősíteni. A naplóbejegyzés csak a jóváhagyott fizetési ütemezéssel rendelkező lízingek esetében adható fel. A kifizetési ütemezés megerősítése a lízing pénzügyi adatainak végleges jóváhagyására szolgál. A lízing pénzügyi adatainak jövőbeli változásai – például a kifizetések és a lízingfutamidő – a lízingkiigazítást jelentik, és ennek megfelelően kell feldolgozni.

Több fizetési ütemezés jóváhagyásához kövesse az alábbi lépéseket.

1. Nyissa meg az **Eszközlízing \> Időszakos \> Megerősített köteg** lehetőséget.
2. A **Megerősített köteg** lapon válassza ki a **Megerősített köteg** lehetőséget.
3. A megjelenő párbeszédpanelen szűrje a megerősíteni kívánt könyveket.

    - Egy adott lízingcsoportba tartozó összes könyv jóváhagyásához válassza ki a csoportot a **Lízingcsoport** mezőben.
    - Meghatározott könyvek jóváhagyásához válassza ki a könyveket a **Könyvazonosító** mezőben.
    - Az összes könyv jóváhagyásához kapcsolja be az **Összes könyvhöz** paramétert.

Az újonnan visszaigazolt könyvekre vonatkozó információk a **Megerősített könyvek** oldalon láthatók. A kifizetési ütemezések jóváhagyása után a rendszer a lízingek alapján feladja a kezdeti megjelenítési naplóbejegyzéseket.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
