---
title: "A jelentések és dokumentumok összegek megjelenítésének módosítása"
description: "Ez a témakör információt a jelentések és egyéb dokumentumok az Észtország, Lettország, Litvánia, Lengyelország, Cseh Köztársaság, Magyarország és Oroszország összegek megjelenítésének frissítése."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264254
ms.assetid: 70b32d8d-6fa7-4617-ba74-a74bc6568d6e
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 870341b81e49c9fc677052e9ef87a580892f486f
ms.lasthandoff: 03/31/2017


---

# <a name="update-how-amounts-are-displayed-on-reports-and-documents"></a>A jelentések és dokumentumok összegek megjelenítésének módosítása

Ez a témakör információt a jelentések és egyéb dokumentumok az Észtország, Lettország, Litvánia, Lengyelország, Cseh Köztársaság, Magyarország és Oroszország összegek megjelenítésének frissítése.

Észtország, Lettország, Litvánia, Lengyelország, Cseh Köztársaság, Magyarország és Oroszország jogalanyok állíthat be a teljes nevét és rövid neveket valutaegységek és alegységekben. Ezek a nevek hogyan jelennek meg a dokumentumok és jelentések összegek átalakításához használható. Például: az összeg **LTL 100.20** jeleníthető **100 Litas 20 Centas**.

## <a name="set-up-full-and-short-names-for-currency-units-and-subunits"></a>Teljes és rövid neve valutaegységek és részegységeknek beállítása
Pénznem egység teljes és rövid nevek és nyelvek részegységeknek beállításához kövesse az alábbi lépéseket:

1.  Nyissa meg a **pénznemek** oldalon.
2.  Válassza ki a pénznemet.
3.  Kattintson a műveletpanel a **Declension**.
4.  Teljes nevét és rövid nevét a nyelv hozzáadásához kattintson a **új**, és töltse ki a következő mezőket.
    |                                                           |                                                                                                                                                                                                                    |
    |-----------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | **Field**                                                 | **Description**                                                                                                                                                                                                    |
    | **Language**                                              | Adja meg az aktuális szöveg nyelvét.                                                                                                                                                                          |
    | **Egyes szám alanyeset (egységek mezőcsoport neve)**       | Adja meg a pénznem egyes számú alak. Például az egyes Litas formátuma Litas.                                                                                                                         |
    | **Többes szám alanyeset (egységek mezőcsoport neve)**         | Adja meg annak a pénznemnek a többes számú alak. Írja be például a Litai. **Megjegyzés:**: A **egyes szám birtokos eset** és **többes szám birtokos eset** mezők állnak rendelkezésre a kiválasztott nyelv alapján a **nyelv** mezőben. |
    | **Egyes személyes mező (részek mezőcsoport neve)** | Adja meg a pénznem alegység egyes számú formája.                                                                                                                                                            |
    | **Többes szám alanyeset (részek mezőcsoport neve)**         | Adja meg a pénznem alegység többes számú formája.                                                                                                                                                              |
    | **(Rövid név mezőcsoport) egységek billentyűparancsneve**       | Adja meg az ISO-kód azonosítja a pénznem. Például a litván litas azonosítására az LTL karaktersort adja meg.                                                                                                                             |
    | **Billentyűparancsneve (rövid név mezőcsoport)**      | Adja meg a pénznem alegység megnevezése. Írja be például a Centas.                                                                                                                                         |
    | **Conjunction 'and' between units and parts**             | Bejelölésével kinyomtathatja a együtt "és" a pénznem egységek és az egység részek között. A számlákon vagy a jelentések, például a LTL 100.20 összege 100 Litas és 20 Centas megjelennek.                      |

5.  Click **Save**.



