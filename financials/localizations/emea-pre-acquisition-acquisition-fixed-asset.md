---
title: "Tárgyi eszköz beszerzés előtti műveleteinek feladása"
description: "Ez a témakör bemutatja, hogyan állíthatja be és könyvelheti a tárgyi eszközök beszerzése előtti műveleteket."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 264704
ms.search.region: Czech Republic, Hungary
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 239611a90e077c1e55fe7832ff0cf7806287eccd
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017

---

# <a name="post-the-pre-acquisition-of-a-fixed-asset"></a>Tárgyi eszköz beszerzés előtti műveleteinek feladása

[!include[banner](../includes/banner.md)]


Ez a témakör bemutatja, hogyan állíthatja be és könyvelheti a tárgyi eszközök beszerzése előtti műveleteket.

**Megjegyzés:** a tárgyi eszközök beszerzése előtti műveletek könyvelése funkció csak azon jogi személyeknél érhető el, amelyek elsődleges címe Magyarországon vagy Csehországban található. Tárgyi eszköz beszerzés előtti műveletei nem használhatók fel értékcsökkenésben, és ezek nem befolyásolják sem a tárgyi eszköz beszerzési költségeit, sem pedig a tárgyi eszköz nettó könyv szerinti értékét. Beszerzés előtti művelet feladásakor a tárgyi eszköz állapota **Beszerzett** értékre módosul. A **Beszerzett** állapotú tárgyi eszközök nem használhatók fel értékcsökkenésben. Beszerzés feladásakor ellenben a tárgyi eszköz állapota **Nyitva** értékre módosul, és így felhasználható értékcsökkenésben.

## <a name="set-up-preacquisitions"></a>Beszerzési előzmények beállítása
Beszerzési előzmények feladása előtt meg kell adnia a következő beállításokat:

-   A **Tárgyi eszközök paraméterei** oldalon állítsa a **Beszerzés előtti műveletek engedélyezése** elemet **Igen** értékre.
-   A **Tárgyieszköz-feladási profilok** lapon állítsa be a beszerzés előtti műveletek feladástípusához használni kívánt tárgyieszköz-feladási profilt.

## <a name="post-a-preacquisition-of-a-fixed-asset"></a>Tárgyi eszköz beszerzés előtti műveletének feladása
1.  A **Tárgyi eszközök** lapon hozzon létre egy új naplót, és szükség szerint adja meg a vonatkozó információkat.
2.  Az imént létrehozott naplónál kattintson a **Sorok** elemre a **Naplóbizonylat** oldal megnyitásához.
3.  Új sor létrehozásához kattintson az **Új** elemre.
4.  A **Tranzakciótípus** mezőben válasszon ki egy tranzakciót, amelynek a **Beszerzés előtti** a tranzakciótípusa.
5.  Igény szerint adjon meg értékeket a fennmaradó mezőkben.
6.  Kattintson az **Ellenőrzés** elemre a naplósorok ellenőrzéséhez.
7.  Kattintson a **Javaslatok** &gt; **Beszerzés előtti javaslat** elemre.
8.  Kattintson a **Kiválasztás** elemre a kijelölési szempontok konfigurálásához, majd kattintson az **OK** gombra.
9.  Kattintson a **OK** gombra a **Beszerzés előtti javaslat** oldal bezárásához.
10. A beszerzés előtti tranzakció feladásához kattintson a **Feladás** &gt; **Feladás** lehetőségre. A **Könyvek** oldalon a tárgyi eszköz állapota most elvileg **Beszerzett**.





