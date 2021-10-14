---
title: Vállalatközi beszerzési rendelés létrehozása és számlázása belső használatra
description: Ez a témakör bemutatja, hogyan lehet vállalatközi értékesítési rendelést létrehozni és számlázni belső használatra
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 88a14ff962c5cf0cd1cff24b16cc7a62e9e1c8ce
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548308"
---
# <a name="create-and-invoice-an-intercompany-purchase-order-for-internal-use"></a>Vállalatközi beszerzési rendelés létrehozása és számlázása belső használatra

[!include [banner](../../includes/banner.md)]

Vállalatközi szállító számára vállalatközi beszerzési rendelést is létrehozhat. Ez automatikusan létrehozz egy vállalatközi értékesítési rendelést a vállalatközi szállítónál.

![Vállalatközi belső beszerzési folyamat](media/intercompanypurchaseprocess.png)

## <a name="create-an-intercompany-purchase-order-and-a-corresponding-intercompany-sales-order"></a>Vállalatközi beszerzési rendelés és a kapcsolódó vállalatközi értékesítési rendelés létrehozása

Végezze el az alábbi ábrán, az AAA jogi személy által végrehajtott lépéseket.

1. Válassza a következőt: **Kötelezettségek** \> **Beszerzési rendelések** \> **Minden beszerzési rendelés**.
1. Az **Minden beszerzési rendelés** listaoldalon hozzon létre egy beszerzési rendelést a vállalatközi szállítóhoz. A mezőértékeket a rendszer a szállítói számlából másolja át a beszerzési rendelésbe.

    Mivel ez esetben vállalatközi szállítót használ, vállalatközi értékesítési rendelés jön létre a szállítóként megjelölt jogi személyre. A vállalatközi értékesítési rendelés száma megegyezhet a vállalatközi beszerzési rendelés számával, és tartalmazhatja a jogi személy azonosítóját is. A használt számstruktúra a **Vállalatközi** oldal **Értékesítési rendelés számozása** mezőjében megadott beállításoktól függ. Ha például egy 00029\_064 számú beszerzési rendelést hoz létre az AAA jogi személyre, akkor a BBB jogi személy értékesítési rendelésének száma AAA00029\_64..

    Egy tájékoztató üzenet tájékoztat arról, hogy egy vállalatközi beszerzési rendelés és egy vállalatközi értékesítési rendelés készült. Az üzenet tájékoztatási célból a vállalatközi értékesítési rendelési számát és adatait is tartalmazza.

1. Sorok hozzáadása a beszerzési rendeléshez. A megfelelő sorcikkek automatikusan hozzáadódnak a vállalatközi értékesítési rendeléshez. Ha egy cikk nem létezik a másik jogi személynél, akkor a rendszer megjelenít egy üzenetet, és a cikket nem adhatja hozzá a beszerzési rendeléshez. A probléma megoldásához váltson át a másik jogi személyre és oldja fel a terméket a számára. A cikk ezután elérhetővé válik a másik jogi személynél az értékesítési rendelésekhez való hozzáadásra. Ezt követően váltson vissza a beszerzési rendelés jogi személyére, és folytassa a sorcikkek hozzáadását.
1. Ha befejezte a beszerzési rendelés adatainak bevitelét, erősítse meg azt.

## <a name="process-the-intercompany-packing-slip-and-customer-invoice"></a>A vállalatközi szállítólevél és a vevői számla feldolgozása

Végezze el az alábbi ábrán, az BBB jogi személy által végrehajtott lépéseket.

1. Ugrás a **Kinnlevőségek \> Értékesítési rendelések \> Minden értékesítési rendelésre**.
1. Az **Összes értékesítési rendelés** listaoldalon, válassza a vállalatközi értékesítési rendelést.
1. A munkaablakban válassza a **Kitárolás és csomagolás** lapot, majd válassza a **Csomagjegyzék** lehetőséget.
1. Jelölje be az **Feladás** jelölőnégyzetet.
1. Válassza ki az **OK** lehetőséget. A szállítólevél a BBB jogi személyben lesz feladva.
1. Az **Összes értékesítési rendelés** listaoldalon, válassza a vállalatközi értékesítési rendelést.
1. A Műveleti ablaktáblán válassza a **Számla** lapot, majd válassza a **Számla** menüpontot.
1. Jelölje be az **Feladás** jelölőnégyzetet.
1. Válassza ki az **OK** lehetőséget.

    A vállalatközi értékesítési rendeléshez kapcsolódó vevői számla a BBB jogi személyben kerül feladásra.

## <a name="process-the-intercompany-product-receipt-and-vendor-invoice"></a>A vállalatközi termékbevételezés és a szállítói számla feldolgozása

Végezze el az alábbi ábrán, az AAA jogi személy által végrehajtott lépéseket.

1. Nyissa meg a következőt: **Kötelezettségek \> Beszerzési rendelések \> Minden beszerzési rendelés**.
1. Az **Összes beszerzési rendelés** listaoldalon, válassza a vállalatközi beszerzési rendelést.
1. A Műveleti ablaktáblán válassza a **Fogadás** lapot, majd válassza a **Termékbevételezés** menüpontot. Létrejön a termékbevételezés. A termékbevételezés száma megegyezik a vállalatközi szállítólevél számával.
1. Jelölje be az **Feladás** jelölőnégyzetet.
1. Válassza ki az **OK** lehetőséget.
1. Az **Összes beszerzési rendelés** listaoldalon, válassza a vállalatközi beszerzési rendelést.
1. A műveleti ablaktáblán válassza ki a **Számla**, majd ismét a **Számla** elemet. Létrejön a szállítói számla. A szállítói számla száma megegyezik a vállalatközi vevői számla számával.
1. Fejezze be a szállítói számla rögzítését, majd adja fel.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
