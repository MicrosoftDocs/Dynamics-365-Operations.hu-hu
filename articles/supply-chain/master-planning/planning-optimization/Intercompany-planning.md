---
title: Vállalatközi tervezés
description: Ez a témakör bemutatja a vállalatközi tervezést, és bemutatja, hogyan kell konfigurálni a vállalatközi tervezést a Microsoft Dynamics 365 Supply Chain Management Tervezési optimalizálás megoldásával.
author: ChristianRytt
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a3b48667bb266fec082c48e777fd71d8e5ef6dae
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6357023"
---
# <a name="intercompany-planning"></a>Vállalatközi tervezés

[!include [banner](../../includes/banner.md)]

Néhány szervezetnél a logisztikai műveletek a szervezet többi jogi személyétől (vállalatától) függenek. Ezeket a műveleteket vállalatközi értékesítések és beszerzések használatával kezeli a program, mert mindegyik jogi személyhez külön számlatükör tartozik.

Ez a témakör bemutatja a vállalatközi tervezést, és bemutatja, hogyan kell konfigurálni a vállalatközi tervezést a Microsoft Dynamics 365 Supply Chain Management Tervezési optimalizálás megoldásával.

Ez a témakör a következő fontos vállalatközi kifejezéseket használja:

- **Felfelé irányuló** – Relatív hivatkozás egy vállalatban vagy egy ellátási láncban. Az alapanyag beszállítója irányába mutató mozgást jelez.
- **Lefelé irányuló** – Relatív hivatkozás egy vállalatban vagy egy ellátási láncban. A vevő irányába mutató mozgást jelez.
- **Tervezett vállalatközi igény** – A termék tervezett igénye egy vállalaton belül a termék egy alsóbb vállalattól fennálló tervezett igénye alapján.

Az alaptervezésben az egyik vállalatnál a terv tartalmazhatja azt a tervezett vállalatközi igényt, amely egy másik vállalat tervének tervezett rendeléseihez kapcsolódik. Ez a funkció hasznos, mivel teljes láthatóságot ad a tervezett rendelésekről a vállalatok között. Biztosítja azt is, hogy minden szükséges tervezett beszerzési rendelés létrejöjjön, de a vállalatközi igényhez tartozó tervezett rendelések megerősítésének megkövetelése nélkül.

Ha egy alaptervből futtatja az alaptervezést, amely tartalmazza a tervezett lefelé irányuló igényt, akkor a kapcsolódó vállalatközi szállítóktól származó tervezett beszerzési rendelések igényként szerepelnek a tervben.

## <a name="required-setup"></a>Szükséges beállítás

A vállalatközi tervezés használatához a következő módon kell felkészíteni a rendszert:

1. A releváns termékeket minden érintett vállalatnál ki kell adni. További tudnivalókért lásd: [Vállalatközi kereskedelem konfigurálása és használata itt: Dynamics 365 Supply Chain Management](/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) Microsoft Learn a rendszerében.
1. A lefelé irányuló igényt a felsőbb vállalattal vállalatközi kapcsolattal rendelkező szállítótól érkező beszerzéseknek és a vevő megfelelő alapértelmezett készletdimenzióinak (hely és raktár) kell fedezniük. További tudnivalókért lásd: [Vállalatközi kereskedelem konfigurálása és használata itt: Dynamics 365 Supply Chain Management](/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) Microsoft Learn a rendszerében.
1. A felsőbb szintű vállalat alaptervének tartalmaznia kell a tervezett lefelé irányuló igényt, és meg kell adni az érintett vállalatot és alaptervet a lefelé irányuló tervekben.

## <a name="include-planned-downstream-demand"></a>Tervezett alsóbb rétegbeli igény figyelembevétele

Ha egy alaptervet úgy kíván konfigurálni, hogy az tartalmazza a tervezett lefelé irányuló igényt, hajtsa végre az alábbi lépéseket.

1. Válassz az **Alaptervezés \> Beállítás \> Tervek \> Alaptervezések** lehetőséget.
1. Válasszon ki vagy hozzon létre egy alaptervet.
1. Az **Vállalatközi tervezés** gyorslapon állítsa be a következő mezőket:

    - **Tervezett lefelé irányuló igény belefoglalása** – Ezt a beállítást *Igen* értékre állítva engedélyezheti az alaptervhez tartozó vállalatközi tervezést.
    - **Lefelé irányuló tervek** – Ha a **Tervezett lefelé irányuló igény belefoglalása** beállítást *Igen* értékűre állítja, akkor az eszköztár és a rács segítségével adja hozzá a többi vállalattól a kívánt alapterveket.

## <a name="peg-across-companies-by-using-multilevel-pegging"></a>Kövesse az igényeket a vállalatok között többszintű igénykövetéssel

A többszintű igénykövetésben megtekintheti a vállalatok közötti igénykövetést, hogy megtekintse az ellátással fedezett igény kezdeti forrását.

A többszintű igénykövetési adatok megtekintéséhez kövesse az alábbi lépéseket.

1. Ugorjon az **Alaptervezés \> Alaptervezés \> Tervezett rendelések** pontra.
1. Válasszon ki vagy nyisson meg egy tervezett rendelést.
1. A Művelet ablaktábla **Nézet** lapjának **Követelmények** csoportjában válassza a **Többszintű igénykövetés** elemet.

### <a name="intercompany-example-that-involves-two-companies"></a>Vállalatközi példa, amely két vállalatot érint

Ehhez a példához egy tervezett termelési rendelés jön létre a USMF vállalatban, amely fedezi az értékesítési rendelést a DEMF vállalatban. A USMF vállalatban a közvetlen igény a tervezett vállalatközi igény. Ha azt szeretné, hogy ez az igény megjelenjen a USMF-ben, akkor az alaptervezést először a DEMF, majd a USMF esetében kell futtatni.

A következő ábra azt mutatja be, hogyan jelenhet meg ez a példa a tervezett termelési rendelés **Többszintű igénykövetés** oldalán.

![Vállalatközi példa, amely két vállalatot érint.](media/IntercompanyPlanning1.png)

### <a name="intercompany-example-that-involves-three-companies"></a>Vállalatközi példa, amely három vállalatot érint

Ehhez a példához egy tervezett beszerzési rendelés jön létre a USMF vállalatban, amely fedezi az értékesítési rendelést a FRRT vállalatban. A DEMF és USMF vállalatban a közvetlen igény a tervezett vállalatközi igény. Ha azt szeretné, hogy ez az igény megjelenjen a USMF-ben, akkor az alaptervezést először az FRRT, majd a DEMF, végül a USMF esetében kell futtatni.

A következő ábra azt mutatja be, hogyan jelenhet meg ez a példa a tervezett termelési rendelés **Többszintű igénykövetés** oldalán.

![Vállalatközi példa, amely három vállalatot érint.](media/IntercompanyPlanning2.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]