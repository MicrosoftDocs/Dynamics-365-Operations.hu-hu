---
title: Tárgyi eszközök átsorolása
description: Ez a cikk bemutatja az eszközök átsorolásának folyamatát. A tárgyi eszközök átsorolása előtt át kell vinni az eszközöket egy új tárgyieszköz-csoportba, vagy ugyanazon a csoporton belül új tárgyieszközszámot kell társítani a tárgyi eszközhöz.
author: moaamer
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4bd901b1709f0b006cecfbbf6d8c170b56f89d19
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284363"
---
# <a name="reclassify-fixed-assets"></a>Tárgyi eszközök átsorolása

[!include [banner](../../includes/banner.md)]

A tárgyi eszközök átsorolása előtt át kell vinni az eszközöket egy új tárgyieszköz-csoportba, vagy ugyanazon a csoporton belül új tárgyieszközszámot kell társítani a tárgyi eszközhöz. 

Ha egy tárgyi eszközt átsorolnak:

- A létező tárgyi eszköz valamennyi könyve létrejön az új tárgyi eszközhöz. Az eredeti tárgyi eszköznél beállított valamennyi adat az új tárgyi eszköz adataként jelenik meg. Az eredeti tárgyi eszköz könyveinek állapota Lezárt lesz. 

- Az új tárgyi eszköz könyvénél az átsorolás dátuma fog szerepelni a **Beszerzési dátum** mezőben. Az **Értékcsökkenés** futtatásának dátuma mezőben szereplő dátum az eredeti eszközadatokból lesz átmásolva. Ha már elkezdődött az értékcsökkenés, akkor az **Utolsó értékcsökkenés futtatásának** dátuma mezőben az átsorolás dátuma jelenik meg. 

- Az eredeti tárgyi eszköz tárgyieszköz-tranzakciói törlődnek, és ismét létrejönnek az új tárgyi eszközhöz.

- Ha egy átsorolási tranzakcióval rendelkező eszközt átsorolnak akkor a rendszer egy üzenetet jelenít meg a **Műveletközpontban**, amely azt jelzi, hogy az átsorolási folyamat során nem fejeződött be az átviteli tranzakció. Ahhoz, hogy a meglévő átsorolási tranzakciókat a megfelelő pénzügyi dimenziókba át lehessen helyezni végre kell hajtani egy átátviteli tranzakciót. 

   Az átsorolási folyamat során a rendszer a következő műveleteket futtatja az eszközegyenleg átsorolásához az eredeti eszközről az új eszközre. 
   
   - Az átsorolási folyamat az eredeti tárgyieszköz-könyv adatait az új tárgyieszköz-könyvbe másolja.

   - Az átsorolási tranzakció az eredeti feladott beszerzés adatait használja fel, és tartalmazza a beszerzési tranzakcióban szereplő pénzügyi dimenzióadatokat.  
   
   - Ugyanakkor az átsorolási folyamat sztornírozza az eredeti eszközbeszerzési és eszközátadási tranzakciót. 

Az alábbi ábra és eljárás az átsorolási folyamatra mutat be egy példát. 

[![Az átsorolási folyamatot megjelenítő diagram.](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)

A tárgyi eszköz átsorolásához kövesse az alábbi lépéseket:

1. Ugorjon a **Tárgyi eszközök > Időszakos feladatok > Újbóli osztályozás** elemre.
2. A **Tárgyieszköz-csoport** mezőben válassza ki az újraosztályozandó csoport.
3. A **Tárgyi eszköz száma** mezőben válassza ki a tárgyi eszközt az újraosztályozáshoz.
4. Az **Új tárgyieszköz-csoport** mezőjében válassza ki a csoportot, amelybe át szeretné vinni a tárgyi eszközt.
    * Ha az új tárgyieszköz-csoport hozzá van csatolva egy specifikus számsorozathoz, az **Új tárgyieszköz-szám** mező frissítése az új tárgyieszköz-csoport számsorozatából származó számmal történik. Ellenkező esetben az **Új tárgyieszköz-szám** mező frissítése azzal a számmal történik, amelyik a **Tárgyi eszköz paraméterei** oldalon beállított számsorozatból származik. Ha a **Tárgyi eszköz paraméterei** oldalon nincs beállítva számsorozat, írjon be egy számot az **Új tárgyieszköz-szám** mezőbe.  
5. Adjon meg egy dátumot az **Átsorolás dátuma** mezőben.
6. A **Bizonylatsorozat** mezőben adjon meg vagy válasszon ki egy értéket.
7. Válassza ki az **OK** lehetőséget.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
