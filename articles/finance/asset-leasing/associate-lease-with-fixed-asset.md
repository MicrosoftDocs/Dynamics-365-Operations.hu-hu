---
title: Lízingek társítása tárgyi eszközhöz
description: A témakör bemutatja, hogyan társítható egy meglévő tárgyi eszköz egy új lízinghez.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: bd55d433b0961b8b210b9c28d7340ff880635a85
ms.sourcegitcommit: 3af457fc216bd0020843291ca57fd379acb53c96
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/17/2021
ms.locfileid: "7392474"
---
# <a name="associate-fixed-assets-with-leases"></a>Lízingek társítása tárgyi eszközhöz

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

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

Amikor egy lízinget egy tárgyi eszközhöz társítanak, a tárgyi eszköz könyvében a **Szolgáltatási élettartam** mezőt úgy frissítik, hogy az a következő kritériumok közül a legkisebb értékkel egyezik meg: 

 - Az eszköz hasznos élettartama
 - A lízing futamideje a kapcsolódó lízingkönyvből

Ha a **Tulajdonjog átadása** mező a lízingkönyv esetében **Igen**-re van állítva, a **Használati idő** mezőben szereplő érték mindig az eszköz hasznos élettartama lesz. 
 
A használati élettartamot minden alkalommal frissíteni kell, amikor a lízinget módosítják, hogy a használati joggal rendelkező eszköz értékcsökkenése a lízing időtartama alatt történjen, mintha az eszközlízingben értékcsökkenne.

> [!NOTE]
> Ha a tárgyi eszközt lízinghez rendeli hozzá, akkor az **Eszköz értékcsökkenése** és a **Lízing értékvesztése** gombok le vannak tiltva az Eszközlízingelésnél. Megtekintheti a tárgyi eszközökből származó eszközök értékcsökkenését és a lízing-értékvesztési tranzakciókat. Az **Eszköztranzakciók** gomb, amely megnyitja a lekérdezési képernyőt is, le van tiltva. Az **Eszközranzakciók** lekérdezési űrlapot a Tárgyi eszközökben is megnyithatja.  

A **Befektetett eszközök** és a **Befektetett eszközök könyve** oldalakon megjelenik a tárgyi eszközhöz tartozó lízingazonosító. Ha egy tárgyi eszköz lízinghez kapcsolódik, a lízing azonosítója és a lízing leírása megjelenik a **Lízinginformációk** gyorslapon a **Tárgyi eszközök** lapon. A lízingkönyvekhez kapcsolódó tárgyi eszközkönyvek esetében a **Lízingazonosító**, a **Lízingleírás** és a **Könyvtípus** mezők a **Lízinginformációk** gyorslapon megjelenítik a kiválasztott tárgyi eszközkönyvre vonatkozó információkat, jelezve, hogy az egy lízingkönyvhöz kapcsolódik.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
