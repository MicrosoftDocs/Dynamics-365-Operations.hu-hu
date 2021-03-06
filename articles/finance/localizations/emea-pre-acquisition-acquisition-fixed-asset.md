---
title: Tárgyi eszköz beszerzés előtti műveleteinek feladása
description: Ez a témakör bemutatja, hogyan állíthatja be és könyvelheti a tárgyi eszközök beszerzése előtti műveleteket.
author: EvgenyPopovMBS
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 264704
ms.search.region: Czech Republic, Hungary
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d430b59e9865fe219cd0427cc9b03c72500b8b74
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818339"
---
# <a name="post-the-pre-acquisition-of-a-fixed-asset"></a>Tárgyi eszköz beszerzés előtti műveleteinek feladása

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan állíthatja be és könyvelheti a tárgyi eszközök beszerzése előtti műveleteket.

**Megjegyzés:** a tárgyi eszközök beszerzése előtti műveletek könyvelése funkció csak azon jogi személyeknél érhető el, amelyek elsődleges címe Magyarországon vagy Csehországban található. Tárgyi eszköz beszerzés előtti műveletei nem használhatók fel értékcsökkenésben, és ezek nem befolyásolják sem a tárgyi eszköz beszerzési költségeit, sem pedig a tárgyi eszköz nettó könyv szerinti értékét. Beszerzés előtti művelet feladásakor a tárgyi eszköz állapota **Beszerzett** értékre módosul. A **Beszerzett** állapotú tárgyi eszközök nem használhatók fel értékcsökkenésben. Beszerzés feladásakor ellenben a tárgyi eszköz állapota **Nyitva** értékre módosul, és így felhasználható értékcsökkenésben.

## <a name="set-up-pre-acquisitions"></a>Beszerzési előzmények beállítása
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

  > [!NOTE]
  > A beszerzési/beszerzés-helyesbítési javaslat paramétereiben a beszerzés előtti tranzakciók kiválasztásának dátumáig beállíthatja a **Céldátum** mezőben a dátumot.
  > Ez a funkció a 10.0.17-es és későbbi verziókban áll rendelkezésre.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]