---
title: Lízingek társítása tárgyi eszközhöz
description: A témakör bemutatja, hogyan társítható egy meglévő tárgyi eszköz egy új lízinghez.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d627633e43c2e6f5cad90dfe4100ff95a71541f7
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444183"
---
# <a name="associate-fixed-assets-with-leases"></a>Lízingek társítása tárgyi eszközhöz

[!include [banner](../includes/banner.md)]

A témakör bemutatja, hogyan társítható egy meglévő tárgyi eszköz egy új lízinghez. Amikor egy tárgyi eszközt egy lízinghez társít, a használatijog-eszköz (ROU) értéke a kezdeti megjelenítéskor a tárgyi eszköz beszerzési költsége lesz.

Mielőtt egy befektetett eszközt egy lízinghez társítana, létre kell hoznia egy rekordot a tárgyi eszközhöz a Tárgyi eszközökben. Ezután a **Lízing összegzése** lapon létre kell hoznia egy lízinget, és csatolnia kell az eszközt az adott lízinghez.

1. Lízing hozzáadása a [Lízing hozzáadása vagy másolása](add-lease.md) című részben leírt lépések végrehajtásával. A **Lízing hozzáadása** lap **Tárgyi eszköz száma** mezőjében válassza ki azt az eszközt, amely még nem lett beszerezve.
2. Válassza a **Könyvek** lehetőséget, és erősítse meg a fizetési ütemezést.
3. Válassza a **Kezdeti elszámolás** lehetőséget.
4. Válassza az **Eszközlízing-napló** lehetőséget.

    A lízing kezdeti kivezetési naplóbejegyzése a tárgyi eszközt a ROU eszközszámlára általában megterhelt összegre terheli.

    Most már megtekintheti a tárgyi eszköz tranzakciótípusát és könyvét.

5. Válassza a **Napló részletei** lehetőséget.
6. Válassza a **Sorok** lehetőséget a naplóbejegyzés egyes sorainak megtekintéséhez.
7. Jelölje ki az eszközt tartalmazó naplósort, majd válassza a **Tárgyi eszközök** lapot.

    A **Tárgyi eszközök** lapon látható a tranzakció típusa és a könyv. Alapértelmezés szerint a **Tranzakció típusa** mező **Beszerzés** értékre, a **Könyv** mező pedig a tárgyi eszköz aktuális könyvére van állítva.

A kezdeti elszámolásnapló-bejegyzés könyvelése után a tranzakció a tárgyi eszköz beszerzési tranzakciójaként jelenik meg. A tranzakciótábla megtekintéséhez lépjen a **Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** elemre, válassza ki a megfelelő eszközt, és az **Értékelések** lehetőséget. Azt kell látnia, hogy a kezdeti elszámolásnapló-bejegyzés létrehozta egy megadott tárgyi eszköz beszerzési tranzakcióját.

A tárgyi eszköz értékcsökkenése a tárgyi eszközök standard értékcsökkenési funkciójának használatával. Az értékcsökkenéssel kapcsolatos további tudnivalókért lásd: [Értékcsökkenési módszerek és szabályok](../fixed-assets/depreciation-methods-conventions.md).

> [!NOTE]
> Ha a tárgyi eszközt lízinghez rendeli hozzá, akkor az **Eszköz értékcsökkenése** és a **Lízing értékvesztése** gombok le vannak tiltva az Eszközlízingelésnél. Megtekintheti a tárgyi eszközökből származó eszközök értékcsökkenését és a lízing-értékvesztési tranzakciókat. Az **Eszköztranzakciók** gomb, amely megnyitja a lekérdezési képernyőt is, le van tiltva. Az **Eszközranzakciók** lekérdezési űrlapot a Tárgyi eszközökben is megnyithatja.  
