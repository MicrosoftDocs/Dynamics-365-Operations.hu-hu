---
title: Számlastruktúrák létrehozása
description: Ez az útmutató bemutatja a számlastruktúra létrehozásának folyamatát.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b75ee76a1fb874652415a2174441f629955d763a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444056"
---
# <a name="create-account-structures"></a>Számlastruktúrák létrehozása

[!include [banner](../../includes/banner.md)]

Ez az útmutató bemutatja a számlastruktúra létrehozásának folyamatát. A lépés a USMF bemutató vállalati adatait használja.

1. Ugrás a következő útvonalra: **Navigációs ablaktábla > Modulok > Főkönyv > Számlatükör > Struktúrák > Számlastruktúrák konfigurálása**.
2. Az **Művelet ablaktáblán** kattintson az **Új** elemre a legördülő párbeszédpanel megnyitásához.
3. A **Számlastruktúra** mezőbe írjon be egy nevet, amely leírja a számlastruktúra célját.
4. A **Leírás** mezőbe írjon be egy leírást, amely megadja a számlastruktúra célját.
5. Kattintson az **Új** > lehetőségre.
6. A **Szegmensek és megengedett értékek** területen kattintson a **Szegmens hozzáadása** elemre.
7. A dimenziók listájában válassza ki a számlastruktúrához adandó dimenziót.
8. A lista végén kattintson a **Szegmens hozzáadása** hivatkozásra.
9. Szükség szerint ismételje meg a 6–9. lépést.
10. Az **Megengedett értékek részletei** szakaszban jelölje ki a szegmenst a megengedett értékek módosításához.
    Kattintson például a **Fő számla** mezőre.  
11. A **Kezelő** mezőben válasszon ki egy lehetőséget, például a „között”, vagy a „tartalmazza” elemet.
12. Érték beírása az **Érték** mezőbe. Például 600 000.  
13. Írjon be egy értéket a **–** mezőbe. Például 699 999.  
14. Az **Engedélyezett érték részletei** szakaszban kattintson az **Alkalmaz** gombra.
15. Szükség szerint ismételje meg a 10–15. lépést.  
16. Az **Engedélyezett érték részletei** szakaszban kattintson az **Új feltétel hozzáadása** gombra.
17. A Kezelő mezőben válasszon ki egy lehetőséget, például a „között”, vagy a „tartalmazza” elemet.
18. Érték beírása az **Érték** mezőbe. Például: 033.  
19. Írjon be egy értéket a **–** mezőbe. Például: 034.  
20. Kattintson az **Alkalmaz** gombra.
21. A rácson jelölje ki a szegmenst a megengedett értékek módosításához. Például: költséghely.  
22. Írjon be egy értéket a **Költséghely** mezőbe. Például 007..021.  
23. A **Szegmensek és megengedett értékek** területen kattintson a **Hozzáadás** elemre.
24. Írjon be egy értéket a **Fő számla** mezőbe. Például: 600000..699999  
25. A rácson jelölje ki a szegmenst a megengedett értékek módosításához. Például: részleg.  
26. Írjon be egy értéket a Részleg mezőbe. Például: 032.  
27. Írjon be egy értéket a Költséghely mezőbe. Például: 086.  
28. A **Művelet panelen** kattintson az **Érvényesítés** elemre.
29. A **Művelet panelen** kattintson az **Aktiválás** elemre.
30. Kattintson az **Aktiválás** gombra.

