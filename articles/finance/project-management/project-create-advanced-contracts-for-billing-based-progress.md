---
title: Speciális szerződések létrehozása a folyamat alapján történő számlázáshoz
description: Ez a témakör azt mutatja be, hogyan lehet létrehozni projekt-szerződéseket, hogy a teljesített munka százaléka alapján számlákat lehessen generálni a vevők számára.
author: RadhikaRS
manager: AnnBe
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 90cae104d0abad909606ef6a0e0c45ed95e74de2
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282829"
---
# <a name="create-advanced-contracts-for-billing-based-on-progress"></a>Speciális szerződések létrehozása a folyamat alapján történő számlázáshoz
[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet létrehozni projekt-szerződéseket, hogy a teljesített munka százaléka alapján számlákat lehessen létrehozni a vevők számára. A számlaösszegek kiszámítása automatikusan, a projekt keretén belül végzett munkához beállított költségvetési kategóriák alapján történik. A számlázási időszakokról a projektszerződés egyeztetésekor kell megállapodni a vevővel.

A témakör eljárásaival hozhatja létre a szerződést, az ahhoz kapcsolódó projektet és a számlázási szabályokat, melyek alapján kiszámíthatja a projekthez megadott munka egyes költségvetési kategóriáira eső számlaösszegeket.

A szerződés és a projekt létrehozása után beállíthatja a projekt részletes adatait. például meghatározhatja a tevékenységeket, és dolgozókat rendelhet a projekthez.

## <a name="example"></a>Példa

Ön egy szoftverfejlesztő cégnél dolgozik. Megyegyezik a vevővel abban, hogy egy bérszámfejtési programcsomagot fejlesztenek számára 20 000 dollár (USD) értékben. Az Ön cége vállalja, hogy a projekt meghatározott százalékainak teljesítésekor számlát állít ki a vevőnek. A következő projektkategóriáka állítja be a munkához, hogy a számlázási folyamat során ezeket használhassa:

- Konzultáció
- Terv
- Telepítés

Azt is be lehet állítani olyan számlázási szabályokat, amelyek alapján az egyes kategóriákban elvégzett projektmunka százaléka után járó számlaösszegek kiszámítása automatikusan történjen.

A projektkategóriák költségvetését a költségvetés-kezelő hozza létre. Az elvégzett munka mennyisége automatikusan kiszámítható mint a munka ténylegesen elvégzett százaléka a költségvetési összegekhez viszonyítva.

## <a name="prerequisites"></a>Előfeltételek

Számlázási szabályokat használó projekt létrehozása előtt be kell állítania a számlázási szabályokhoz tartozó számsorozatokat, valamint a folyamatalapú számlázások feladásához használt díjnaplót.

1. Nyissa meg a **Projektvezetés és könyvelés** \> **Beállítások** \> **Projektvezetési és könyvelési paraméterek** pontot.
2. A **Projektvezetési és könyvelési paraméterek** oldal **Számsorozatok** lapján állítsa be azt a számsorozatot, amelyet a számlázási szabályok létrehozásakor kíván használni.
3. Ugorjon a **Projektvezetés és könyvelés** \> **Naplók** \> **Díj** lehetőséget.
4. A **Díjnapló** oldalon válassza az **Új** lehetőséget, majd írja be a napló nevét.

## <a name="create-a-contract-for-progress-billings"></a>Szerződés létrehozása a folyamatalapú számlázáshoz

Az alábbi eljárás segítségével projektszerződést hozhat létre rögzített árú projekthez. Projektszámlát akkor hozhat létre, amikor a projekt során elvégzett munka elér egy bizonyos százalékot.

1. Lépjen a **Projektvezetés és könyvelés** \> **Projektek** \> **Projektszerződések** menüpontba.
2. A **Projektszerződések** oldalon válassza az **Új** elemet.
3. Az **Új projektszerződés** párbeszédpanelen a következő mezőket állíthatja be:

    - **Név**
    - **Finanszírozás típusa**
    - **Finanszírozási forrás**
    - **Értékesítés pénzneme** – A rendszer alapértelmezés szerint ezt a pénznemet használja a projektszerződéshez társított vevői számlákhoz. az egyes vevői számlák értékesítési pénzneme ugyanakkor külön is módosítható.

4. Válassza ki az **OK** lehetőséget. A program átmásolja az információt a **Projektszerződések** lap fejlécébe.
5. Töltse ki a **Projektszerződések** oldalon a többi szükséges információt a projekthez.

## <a name="create-a-project-for-progress-billings"></a>Projekt létrehozása folyamatalapú számlázáshoz

Az alábbi lépéseket követve hozhat létre projektet és alprojekteket egy adott projektszerződéshez kapcsolódóan.

1. Ugorjon a **Projektvezetés és könyvelés** \> **Projektek** \> **Minden projekt** pontra.
2. A **Minden projekt** oldalon válassza az **Új** lehetőséget.
3. Az **Új projekt** párbeszédpanel **Projekt típusa** mezőjében válassza az **Idő és anyag** elemet.
4. Válasszon egy projektcsoportot. A projektcsoport határozza meg a csoporthoz rendelt projektek feladási információit.
5. Válassza a **Projekt létrehozása** elemet.
6. A projekt létrehozása után, állítsa a projektszakaszt **Folyamatban** értékre.

## <a name="create-a-budget-for-a-project"></a>A projekt költségvetésének létrehozása

A költségvetési kategóriák alapján automatikusan kiszámíthatók az egyes kategóriákban elvégzett munka százaléka után kiszámlázandó összegek. Hajtsa végre a következő lépéseket a becsült költségek költségvetési kategóriáinak létrehozásához.

1. Ugorjon a **Projektvezetés és könyvelés** \> **Projektek** \> **Minden projekt** pontra.
2. A **Minden projekt** lapon válassza ki a kívánt projektet, majd nyissa meg azt.
3. A **Projektek** lap műveleti panelén a **Terv** lapon a **Költségvetés** csoportban válassza ki a **Projektköltségvetés** lehetőséget.
4. A **Projektköltségvetés** oldalon adja meg a projekt egyes kategóriának becsült költségét.

## <a name="create-billing-rules-for-progress-billings"></a>Számlázási szabályok létrehozása a folyamatalapú számlázáshoz

1. Lépjen a **Projektvezetés és könyvelés** \> **Projektek** \> **Projektszerződések** menüpontba.
2. A **Projektszerződések** lapon válassza ki, majd nyisson meg egy projektszerződést.
3. A projektszerződés lap **Számlázási szabályok** gyorslapján válassza a **Hozzáadás** elemet.
4. A **Számlázási szabály** oldal **Sor típusa** mezőjében válassza a **Folyamat** elemet.
5. Adja meg a szerződés teljes értékét a **Számlázási szabály sorának részletes adatai gyorslap** **Szerződéses értéke** mezőjében adja meg.
6. A **Kategória** mezőben válassza ki a kategóriát a díjtranzakció feladásához.
7. A **Projekt** mezőben válassza ki azt a projektet vagy feladatot, amely ezt a számlázási szabályt használja.
8. Opcionális: A számlázási szabályt további projektekhez is hozzárendelheti. Jelöljön ki egy projektet a **Projekt** gyorslapon a **Rendelkezésre álló projektek** szakaszban, majd válassza a jobbra mutató nyilat, és adja hozzá a projektet a **Kiválasztott projektek** szakaszhoz.
9. Opcionális: Számítsa ki a százalékos értéket, amelyet a vevő visszatart egy számla kifizetésénél. A **Fizetés-visszatartási feltételek** gyorslapon válassza ki a finanszírozási forrást, majd a **Visszatartás százaléka** mezőben adja meg a visszatartási százalékot.
10. Ismételje meg ezeket a lépéseket a projektszerződés további számlázási szabályainak létrehozásához.
