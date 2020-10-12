---
title: Felelős karbantartási dolgozók
description: Ez a témakör azt mutatja be, hogyan lehet felelős karbantartási dolgozókat beállítani az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkerResponsible
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 113ee2b45c569c7dae3609f1027e31c4e5e5c54a
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/25/2020
ms.locfileid: "3890081"
---
# <a name="responsible-maintenance-workers"></a>Felelős karbantartási dolgozók

[!include [banner](../../includes/banner.md)]

 

A felelős karbantartási dolgozók eszköztípusokhoz, eszközökhöz, munkavégzési helyszínekhez, karbantartási feladat típusának kategóriáihoz, karbantartási feladatok típusaihoz, karbantartási feladat típusának változataihoz és ügyletekhez egyaránt kapcsolódhatnak. Feltüntethetők a munkarendeléseken és a karbantartási kérelmeken annak jelzésére, hogy kik azok az előnyben részesített karbantartási dolgozók, akiket a munkarendeléshez célszerű rendelni. (Ezek a karbantartási dolgozók azonban nem feltétlenül egyeznek meg azokkal, akiket a munkarendelés elvégzésére ütemeztek.) Ennek a funkciónak a használata nem kötelező. Használható például felelős dolgozók vagy dolgozói csoportok konkrét munkatípusokhoz vagy munkaterületekhez történő kiválasztásához.

A munkarendelés-életciklus vagy a karbantartás iránti kérelem életciklusa során van lehetőség a felelős karbantartási dolgozók módosítására vagy aktualizálására. Ez a módosítás vagy frissítés kapcsolódhat például a karbantartási kérelem vagy a munkarendelés életciklus-állapotának változásához.

A **Felelős karbantartási dolgozók** oldalon való beállítás munkarendelés-ütemezés során *nem* használatos.

> [!NOTE]
> Az Eszközkezelés modulban azokat az *előnyben részesített* karbantartási dolgozókat is beállíthatja, akiket a munkarendelés-ütemezés során a munkarendelésekhez lehet rendelni.

A felelős karbantartási dolgozók beállítása előtt be kell állítania a kiválasztáshoz rendelkezésre álló dolgozók és karbantartási dolgozók csoportjait. A dolgozói és karbantartási dolgozói csoportok beállítására vonatkozó további tudnivalókért tanulmányozza a [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md) című témakört.

## <a name="set-up-responsible-maintenance-workers"></a>Felelős karbantartási dolgozók beállítása

1. Válassza ki az **Eszközkezelés**\>**Beállítás**\>**Dolgozók**\>**Felelős karbantartási dolgozók** lehetőséget.
2. Válassza az **Új** lehetőséget egy rekord létrehozásához.
3. Először hozzon létre egy alapértelmezett felelős karbantartási dolgozót vagy felelős karbantartási dolgozói csoportra vonatkozó beállítást, ahol csak a **Felelős karbantartási dolgozói csoport** mezőt és/vagy **Felelős dolgozó** mezőt állítja be. Hagyja üresen a fennmaradó mezőket. A program ezt az alapértelmezett beállítást használja a munkarendelés-ütemezés során, ha nincs más konkrétabb kombináció, amely jobban megfelel a munkarendelés tartalmának.

    > [!NOTE]
    > A karbantartási kérés létrehozása során, amikor egy felelős karbantartási dolgozó vagy egy felelős karbantartási dolgozói csoport rendelkezésre áll az **Összes karbantartási kérés** lapon történő kiválasztáshoz, az Eszközkezelő lehetséges egyezést keresve végigellenőrzi az összes felelős karbantartási dolgozó rekordját. Mindig a leginkább meghatározott kombinációt ellenőrzi először. Más szóval az Eszközkezelés modul először a **Kereskedelem** mezővel való egyezést ellenőrzi. Ha nem talál egyezést, akkor a **Karbantartási feladat típusának változata** mezővel való egyezést ellenőrzi. Ha nem talál egyezést, akkor a **Karbantartási feladat típusa** mezővel való egyezést ellenőrzi, és így tovább. Mint látható az oldal elrendezésén, ez azt jelenti, hogy a legspecifikusabb kombináció megtalálása érdekében az Eszközkezelés modul jobbról balra haladva minden egyes rekordot ellenőriz (elsőként a **Kereskedelem**, majd a **Karbantartási feladat típusának változata**, majd a **Karbantartási feladat típusa**, majd a **Karbantartási feladat típuskategóriája**, majd a **Munkavégzési helyszín**, majd az **Eszköz** és végül az **Eszköztípus** elemet). Ha nem talál egyezést, akkor a rendszer azt az alapértelmezett rekordot használja, amely a hét mező egyikében sem tartalmaz választási lehetőséget.

A következő ábra a **Felelős karbantartási dolgozók** oldalt szemlélteti.

![Felelős karbantartási dolgozók oldal](media/08-setup-for-requests.png)
