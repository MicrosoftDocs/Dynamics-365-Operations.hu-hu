---
title: Tárgyi eszközök átsorolása
description: A tárgyi eszközök átsorolása előtt át kell vinni az eszközöket egy új tárgyieszköz-csoportba, vagy ugyanazon a csoporton belül új tárgyieszközszámot kell társítani a tárgyi eszközhöz.
author: saraschi2
manager: AnnBe
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 85132ee72a72c712f726bec9e3450dbd4e1d8f0b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5224717"
---
# <a name="reclassify-fixed-assets"></a>Tárgyi eszközök átsorolása

[!include [banner](../../includes/banner.md)]

A tárgyi eszközök átsorolása előtt át kell vinni az eszközöket egy új tárgyieszköz-csoportba, vagy ugyanazon a csoporton belül új tárgyieszközszámot kell társítani a tárgyi eszközhöz. 

Ha egy tárgyi eszközt átsorolnak:

* A létező tárgyi eszköz valamennyi könyve létrejön az új tárgyi eszközhöz. Az eredeti tárgyi eszköznél beállított valamennyi adat az új tárgyi eszköz adataként jelenik meg. Az eredeti tárgyi eszköz könyveinek állapota Lezárt lesz. 

* Az új tárgyi eszköz könyvénél az átsorolás dátuma fog szerepelni a **Beszerzési dátum** mezőben. Az **Értékcsökkenés** futtatásának dátuma mezőben szereplő dátum az eredeti eszközadatokból lesz átmásolva. Ha már elkezdődött az értékcsökkenés, akkor az **Utolsó értékcsökkenés futtatásának** dátuma mezőben az átsorolás dátuma jelenik meg. 

* Az eredeti tárgyi eszköz tárgyieszköz-tranzakciói törlődnek, és ismét létrejönnek az új tárgyi eszközhöz.

A tárgyi eszköz átsorolásához kövesse az alábbi lépéseket:

1. Ugorjon a **Tárgyi eszközök > Időszakos feladatok > Újbóli osztályozás** elemre.
2. A **Tárgyieszköz-csoport** mezőben válassza ki az újraosztályozandó csoport.
3. A **Tárgyi eszköz száma** mezőben válassza ki a tárgyi eszközt az újraosztályozáshoz.
4. Az **Új tárgyieszköz-csoport** mezőjében válassza ki a csoportot, amelybe át szeretné vinni a tárgyi eszközt.
    * Ha az új tárgyieszköz-csoport hozzá van csatolva egy specifikus számsorozathoz, az **Új tárgyieszköz-szám** mező frissítése az új tárgyieszköz-csoport számsorozatából származó számmal történik. Ellenkező esetben az **Új tárgyieszköz-szám** mező frissítése azzal a számmal történik, amelyik a **Tárgyi eszköz paraméterei** oldalon beállított számsorozatból származik. Ha a **Tárgyi eszköz paraméterei** oldalon nincs beállítva számsorozat, írjon be egy számot az **Új tárgyieszköz-szám** mezőbe.  
5. Adjon meg egy dátumot az **Átsorolás dátuma** mezőben.
6. A **Bizonylatsorozat** mezőben adjon meg vagy válasszon ki egy értéket.
7. Kattintson az **OK** gombra.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]