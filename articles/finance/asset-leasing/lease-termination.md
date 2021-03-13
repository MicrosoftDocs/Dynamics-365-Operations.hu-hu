---
title: Javaslat lízing felmondására
description: Ez a témakör bemutatja, hogyan történik egy lízing megszüntetésének javasolása.
author: moaamer
manager: Ann Beebe
ms.date: 1/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 144559b14878a44afd8a77648bb5ce1d3ba17832
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2021
ms.locfileid: "5131288"
---
# <a name="propose-a-lease-for-termination"></a>Lízing megszüntetésének javasolása

[!include [banner](../includes/banner.md)]

Ha egy lízinget korábban szüntetnek meg, az Eszközlízing rögzíthet egy felmondási naplóbejegyzést a lízingkötelezettség, a használatijog-eszköz és a halmozott értékcsökkenés leírásának, valamint nyereség vagy veszteség könyvelése érdekében. A korai megszüntetési folyamat lezárja a lízinget és a hozzá tartozó lízingkönyveket. Nem szünteti meg az egyes lízingkönyveket. Ez a témakör ismerteti azokat a funkciókat, amelyek segítségével javasolhatja egy lízing megszüntetését, és feldolgozhatja a lízing megszüntetésével kapcsolatos naplóbejegyzést.

Ha egy lízing nem minősül halasztott bérleti díjkezelési lízingnek, és nincs tárgyi eszközhöz társítva, az Eszközlízing a következő megszüntetési naplóbejegyzést állítja elő.

| Tranzakció                           | Tartozás (Dr.) | Jóváírás (Cr.) |
|---------------------------------------|-------------|--------------|
| Dr. Lízingkötelezettség                   | X           |              |
| Dr. Halmozott értékcsökkenés          | X           |              |
| Dr. Nyereség (veszteség) a lízing módosításakor | X           |              |
| Cr. Lízingeszköz                       |             | X            |
| Cr. Nyereség (veszteség) a lízing módosításakor |             | X            |

Ha a lízingkönyv halasztott bérleti díj típusú könyvnek minősül, a bejegyzés a halasztott bérleti díj egyenlegét a nyereség- vagy veszteségszámla megszüntetése előtt leírja, amint az itt látható.

| Tranzakció                           | Tartozás (Dr.) | Jóváírás (Cr.) | 
|---------------------------------------|-------------|--------------|
| Dr. Halasztott bérleti díj                     | X           |              |
| Cr. Nyereség (veszteség) a lízing módosításakor |             | X            |
| Cr. Halasztott bérleti díj                     |             | X            |
| Dr. Nyereség (veszteség) a lízing módosításakor | X           |              |

Ha a lízingkönyv tárgyi eszközhöz kapcsolódik, akkor a Tárgyi eszközök pontban megtörténik a ROU-eszköz elszámolása. Ez a könyvelés tartalmazza a korai megszüntetések könyvelését. Az Eszközlízing a következő naplóbejegyzést hozza létre a lízingkötelezettség leírásához.

| Tranzakció                           | Tartozás (Dr.) | Jóváírás (Cr.) |
|---------------------------------------|-------------|--------------|
| Dr. Lízingkötelezettség                   | X           |              |
| Cr. Nyereség (veszteség) a lízing módosításakor |             | X            |

A ROU-eszköz kivezetésének helyes módszeréről lásd: [Leselejtezett tárgyi eszközök kivezetése](../fixed-assets/dispose-of-a-fixed-asset-as-scrap.md).

## <a name="propose-a-lease-for-termination"></a>Lízing megszüntetésének javasolása

1. Menjen a megszüntetni kívánt lízinghez, majd a Művelet ablaktáblán válassza ki a **Megszüntetési javaslat** lehetőséget.

    > [!NOTE]
    > A **Megszüntetési javaslat** gomb nem érhető el, ha egy könyvhöz kapcsolódóan fel nem adott naplóbejegyzések léteznek. A lízing megszüntetése előtt fel kell adnia vagy törölnie kell minden olyan naplóbejegyzést, amelyet a lízinghez hoztak létre.

2. A megjelenő párbeszédpanelen állítsa be a megszüntetési naplóbejegyzés **Érvényesség dátuma** és a **Feladási dátum** mezőit.
3. Válassza ki **Megszüntetési javaslat** lehetőséget a lízing megszüntetésének javasolása érdekében.
4. Válassza a **Lízing megszüntetésének feladása** lehetőséget a lízingmegszüntetési naplóbejegyzés automatikus feladásához.
5. A **Lízing megszüntetése** oldalon válassza ki a megszüntetésre javasolt lízing azonosítóját a megszüntetési sorok megtekintéséhez. A megszüntetési sorok mutatják a ROU-eszköz, a lízingkötelezettség, a halmozott értékcsökkenés, az esetleges halasztott bérleti díj és a lízing megszűnése esetén megjelenítendő nyereség vagy veszteség értékét.

A lízing készen áll a megszüntetésre. A lízingkönyv **Megszüntetés állapota** mezőjének értéke **Megszüntetésre kész** értékre módosul. Ezen a ponton már nem adhat fel naplóbejegyzéseket, nem módosíthat és nem könyvelhet értékvesztést a lízinggel kapcsolatban. 

## <a name="process-leases-that-are-ready-for-termination"></a>Megszüntetésre kész lízingek feldolgozása

A megszüntetésre kész lízingek feldolgozásához és a megszüntetési naplóbejegyzés feladásához hajtsa végre ezeket a lépéseket.

1. A **Lízing megszüntetése** lapon válassza ki a feldolgozni kívánt lízinget, majd válassza a **Megszüntetés** lehetőséget.
2. A megjelenő párbeszédpanelen jelölje be az **OK** lehetőséget.

A rendszer feladja a megszüntetési naplóbejegyzést. A lízingkönyv **Lízing állapota** mezője **Megszüntetve** értéken van, a **Megszüntetési javaslat állapota** mező pedig **Befejeződött** értéken van.

## <a name="reverse-a-lease-termination"></a>Lízing megszüntetésének sztornírozása

Ha sztornírozni kell egy lízingmegszüntetési naplóbejegyzést, és meg kell nyitni egy megszüntetett lízinget, kövesse ezt a lépést.

- A **Lízing megszüntetése** lapon válassza ki a sztornírozni kívánt megszüntetett lízinget, majd válassza a **Megszüntetés sztornírozása** lehetőséget.

A rendszer sztornírozza a megszüntetési naplóbejegyzést. A lízingkönyv **Lízing állapota** mezője **Nyitva** értékre van állítva. A lízing már nem jelenik meg **Lízing megszüntetése** oldalon, és újra javasolható megszüntetésre.

## <a name="example-of-a-lease-termination"></a>Példa lízing megszüntetésére

Ebben a példában a lízing egy nem specializált eszközhöz van társítva, és nem adja át az eszköz tulajdonjogát, valamint nem adja meg a lízingbevevőnek az eszköz megvásárlásának lehetőségét.

### <a name="setup"></a>Beállítás

Az alábbi táblázatok a példában használt lízing **Általános** és **Fizetési ütemezési sorai** fülön beállított értékeket mutatják be.

**Általános fül**

| Mező                      | Érték            |
|----------------------------|------------------|
| Az eszköz valós értéke    | 600,000          |
| Pénznem                   | USD              |
| Kezdeti közvetlen költségek       | 1000            |
| Járulékos kamatláb | 7%               |
| Összetételi intervallum       | Évente         |
| Eszköz hasznos élettartama (hónap) | 600              |
| Annuitás típusa               | Szokásos annuitás |
| Kezdési dátum          | 2019.01.01.         |

**Kifizetési lista sorai fül**

| Mező             | Érték      |
|-------------------|------------|
| Kezdés dátuma        | 2019.01.01.   |
| Időszak intervalluma   | Havi    |
| Időszakok           | 120        |
| Befejezés          | 2028.12.31. |
| Fizetés gyakorisága | Évente   |
| Fizetés összege    | 10,000     |

### <a name="steps-for-terminating-the-lease"></a>A lízing megszüntetésének lépései

1. Miután létrehozta a lízinget a témakörben korábban leírtak szerint, lépjen a lízingkönyvre, és erősítse meg a fizetési ütemezést. Ezután adja fel a kezdeti megjelenítési naplóbejegyzést. Az eredeti ROU-eszköz 71,235.81 dollár, a lízingkötelezettségnek pedig 70.235,81 dollárnak kell lennie. Ebben a példában a lízinget a Könyvelési standardok kodifikációs témaköre 842 (ASC 842) szerinti operatív lízingnek minősítették.
2. Futtassa a kötegnapló-folyamatot háromszor, hogy szimulálja a három év áthaladását a lízingfizetések, a kamatköltségek és az értékcsökkenési költségek esetében.
3. Miután befejezte mindhárom kötegfeladat futtatását, lépjen vissza a lízingkönyvbe, és nyissa meg a Kötelezettség- és Eszköztranzakciók tábláit a ROU-eszköz és a lízingkötelezettség aktuális könyv szerinti értékének megtekintéséhez. Három év elteltével a kötelezettség értékének körülbelül -53.893,00 dollárnak kell lennie, és az eszköz értékének körülbelül 54.593,00 dollárnak kell lennie.

    A három év eltelte után a vállalat és a lízingbeadó kölcsönösen elfogadja a lízing megszüntetését. Ezért most meg kell szüntetnie a lízinget.

4. Menjen a megszüntetni kívánt lízinghez, majd a Művelet ablaktáblán válassza ki a **Megszüntetési javaslat** lehetőséget. 
5. A megjelenő párbeszédablakban az **Érvényesség dátuma** és a **Feladási dátum** mezőbe írja be a következőt: **2021.01.01.**.
6. Válassza ki **Megszüntetési javaslat** lehetőséget a lízing megszüntetésének javasolása érdekében.

    Megjelenik a **Lízing megszüntetése** oldal, és megjeleníti a megszüntetni kívánt lízinget.

7. A megszüntetési sorok megjelenítéséhez válassza ki a megszüntetésre javasolt lízing azonosítóját. A megszüntetési sorok a lízing könyv szerinti értékét mutatják. A következő tábla megjeleníti, hogy ezeknek milyen értékeknek kell lenniük ebben a példában. 

    | Mező                                                 | Érték      |
    |-------------------------------------------------------|------------|
    | Forrásegyenleg készletezése a tranzakció pénznemében | 53,892.89 dollár |
    | Használatijog-eszköz a tranzakció pénznemében            | 71,235.81 dollár |
    | Halmozott értékcsökkenés a tranzakció pénznemében      | 16,642.92 dollár |
    | Nyereség (veszteség) a tranzakció pénznemében                   | -700.00 dollár   |

8. A megszüntetési naplóbejegyzés feladásához a **Lízing megszüntetése** lapon válassza ki a lízinget, majd válassza a **Megszüntetés** lehetőséget.
9. A megjelenő párbeszédpanelen jelölje be az **OK** lehetőséget.
10. A létrehozott és feladott megszüntetési naplóbejegyzés megtekintéséhez lépjen a tárgyi eszköz naplójára a lízingkönyvben. A következő tábla megjeleníti, hogy ennek a bejegyzésnek milyennek kell lennie ebben a példában.

    | Tranzakció                           | Tartozás (Dr.) | Jóváírás (Cr.) |
    |---------------------------------------|-------------|--------------|
    | Dr. Lízingkötelezettség                   | 53,892.89   |              |
    | Dr. Halmozott értékcsökkenés          | 16,642.92   |              |
    | Dr. Nyereség (veszteség) a lízing módosításakor | 700.00      |              |
    | Cr. Lízingeszköz                       |             | 71,235.81    |

11. A megszüntetés nettó hatásának megtekintéséhez, ahol a ROU-eszköz és a lízingkötelezettség 0 (nulla) lesz, nyissa meg a Kötelezettség- és Eszköztranzakciók táblákat.

A lízing állapotának most **Megszüntetve** értéken kell lennie. A rendszer erre a lízingre nem ad fel további naplóbejegyzéseket, kivéve, ha a megszüntetést sztornírozták.
