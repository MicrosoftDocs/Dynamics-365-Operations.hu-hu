---
title: Fizetési számlák létrehozása
description: Ez a témakör bemutatja, hogyan lehet havi lízingszámlákat létrehozni. Létrehozhat számlákat az egyes lízingekhez, vagy kötegelt folyamattal több lízinghez is létrehozhatja őket.
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
ms.openlocfilehash: 32618814d00cb1e1f1082169a64b187cce1e76b4
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444165"
---
# <a name="create-payment-invoices"></a>Fizetési számlák létrehozása

[!include [banner](../includes/banner.md)]

Létrehozhat havi számlákat az egyes lízingekhez, vagy kötegelt folyamattal több lízinghez is létrehozhatja őket. Az alábbi eljárás bemutatja, hogyan hozhat létre egyéni lízingfizetési bejegyzést, ha a **Lízingkönyv beállítás** lapján a **Fizetés szállítónak** paraméter be van kapcsolva.

1. A **Lízing összegzése** lapon válasszon ki egy lízinget, majd válassza a **Könyvek \> Fizetés ütemezése** lehetőséget.
2. Válassza ki az elvégzendő kifizetést, majd a **Napló létrehozása** lehetőséget. Megjelenik egy üzenet, amely arról szól, hogy a kijelölt kifizetéssel szemben naplót hoztak létre.
3. Válassza a **Számlanaplók** lehetőséget, majd a kifizetendő számlát.
4. A **Sorok** fülön tekintse át a naplóbejegyzést, mielőtt a főkönyvbe feladná.

    > [!NOTE]
    > Alapértelmezés szerint a létrehozott szállítói számlasorok a szállító feladási profilt használják a **Kötelezettségek paraméterei** lapból.

5. Válassza a napló helyesbítése lehetőséget, majd a kifizetendő számlát.

    Ebben a példában a lízingkönyv **Fizetés a szállítónak** paramétere be van kapcsolva. Ezért a számla a számlanaplóban lesz. Az **Áttekintés** szakasz a naplóbejegyzés összegzését, a **Sorok** szakasz pedig a tényleges naplósorok részleteit jeleníti meg.

    > [!NOTE]
    > Ha a **Fizetés a szállítónak** paraméter ki van kapcsolva, a kifizetési napló bejegyzései megjelennek a lízingkönyv **Eszközlízing** oldalán, és a rendszer számla helyett eszközlízing-bejegyzést hoz létre. A lízingdíjfizetés bejegyzés a **Havi lízingnapló** mezőben megadott naplónévre lesz feladva.

6. A tranzakció feladása után megtekintheti a tranzakció adatainak és a lízingkötelezettség könyv szerinti értékét a **Kötelezettségtranzakciók** lehetőség kiválasztásával a lízingkönyvben.

    A fizetési ütemezésben be van jelölve a **Feladott napló** jelölőnégyzet, és a sorban megjelenik a számlanapló száma. A kifizetési napló és a naplóhoz való bejegyzés létrehozása után a tétel újbóli létrehozása előtt sztornírozásra van szüksége.