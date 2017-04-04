---
title: "A tárgyi eszköz beszerzés előtti feladása"
description: "Ez a témakör bemutatja, hogyan állíthatja be és könyvelje a befektetett eszköz beszerzés előtti műveletek."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264704
ms.assetid: 89218666-7c5e-45ca-aead-a87853d05928
ms.search.region: Czech Republic, Hungary
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: c51f041a8287b4623bb8f49bb016c08f7de5b9ae
ms.lasthandoff: 03/31/2017


---

# <a name="post-the-pre-acquisition-of-a-fixed-asset"></a>A tárgyi eszköz beszerzés előtti feladása

Ez a témakör bemutatja, hogyan állíthatja be és könyvelje a befektetett eszköz beszerzés előtti műveletek.

**Megjegyzés:** a funkciót a tárgyieszköz-beszerzés előtti műveletek feladási Magyarország és Csehország elsődleges címe jogalanyokat érhető el. Beszerzés előtti, a befektetett eszköz ÉCS nem, és a beszerzési költségek vagy a tárgyi eszköz nettó könyv szerinti értéke nem változik. Előzetes beszerzés könyvelésekor az a tárgyi eszköz állapota a **szerzett**. A befektetett eszköz, amely a **szerzett** állapota nem értékcsökkenthető. Ezzel szemben, amikor könyveli a beszerzési költséget, az állapota a **nyitott**, és a befektetett eszköz ÉCS.

## <a name="set-up-preacquisitions"></a>Preacquisitions beállítása
Előzetes beszerzés könyvelése előtt meg kell adnia a következő beállítást:

-   A a **tárgyi eszközök paraméterei** oldalon, és állítsa a **beszerzés előtti műveletek engedélyezése** be **Igen**.
-   A a **tárgyieszköz-feladási profilok** lapon állítsa be a befektetett eszköz könyvelési profil a beszerzés előtti feladási típus.

## <a name="post-a-preacquisition-of-a-fixed-asset"></a>Könyvelje a befektetett eszköz preacquisition
1.  A a **tárgyi eszközök** lap, hozzon létre egy új naplót és adja meg a vonatkozó információkat, szükség szerint.
2.  Kattintson az imént létrehozott napló, **vonalak** megnyitása a **Naplóbizonylat** oldalon.
3.  Új sor létrehozásához kattintson az **Új** elemre.
4.  A a **tranzakciótípus** mezőben, válasszon ki egy tranzakciót, amelynek a **a beszerzés előtti** tranzakció típusát.
5.  Adja meg szükség szerint a többi mező értékeit.
6.  Kattintson a **ellenőrzi a** a napló sorok ellenőrzéséhez.
7.  Kattintson a **javaslatok**&gt;**a beszerzés előtti javaslat**.
8.  Kattintson a **válassza a** a kiválasztási szempontoknak, és kattintson a **OK**.
9.  Kattintson a **OK** zárja be a **beszerzés előtti javaslat** oldalon.
10. Kattintson a **feladása**&gt;**feladása** a beszerzés előtti tranzakciók. A a **könyvek** lap, a tárgyi eszköz állapotát kell **szerzett**.



