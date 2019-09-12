---
title: Munkarendelés-gyűjtők
description: Ez a témakör bemutatja a munkarendelés-gyűjtők használatát az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 069fa02073808fd7bbaac9bc1603e49ce4d450eb
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875694"
---
# <a name="work-order-pools"></a>Munkarendelés-gyűjtők


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


A munkarendelés-gyűjtőkkel csoportosíthatja a valamiben egyeztő munkarendeléseket. Létrehozhat például munkarendelés-gyűjtőket a következőhöz:

- munkaszemélyzet, például A karbantartási személyzet, B karbantartási személyzet  

- szakmához kapcsolódó szakértelmek, például villanyszerelők vagy vízvezeték-szerelők  

- tényleges helyek  

- időbeosztások, például hetek vagy más időszakok  


Szükség esetén egy munkarendelés számos munkarendelés-gyűjtőbe elhelyezhető.


## <a name="create-work-order-pool"></a>Munkarendelés-gyűjtő létrehozása

Az **Összes munkarendelés-gyűjtő** vagy **Aktív munkarendelés-gyűjtők** pontokban áttekintést kaphat saját munkarendelés-gyűjtőiről, és új gyűjtőket hozhat létre.

1. Kattintson az **Eszközkezelés** > **Általános** > **Munkarendelés-gyűjtők** > **Összes munkarendelés-gyűjtő** vagy **Aktív munkarendelés-gyűjtők** elemre.

2. Kattintson az **Új** elemre.

3. Szúrjon be egy munkarendelés-gyűjtőhöz tartozó azonosítót a **Gyűjtő** mezőbe és írjon be egy nevet a **Név** mezőbe.

4. Válassza az „Igen” beállítást az **Aktív** választógombon, amellyel jelezheti, hogy a munkarendelés-gyűjtő aktív.

5. Válassza az „Igen” beállítást a **Munkarendelés kapcsolatainak törlése** választógombon, ha szeretne automatikusan eltávolítani munkarendeléseket a munkarendelés-gyűjtőből.

6. Az **Életciklus-állapot törlése** mezőben válassza a munkarendelés életciklus-állapotát. Például a munkarendelés befejezéséhez tartozó munkarendelési életciklus-állapotot beállíthatja, hogy automatikusan törölje a kapcsolatokat a munkarendelés-gyűjtőkből.

7. A munkarendelés-gyűjtőhöz azonnal hozzáadhat munkarendeléseket. A **Munkarendelések** gyorslapon kattintson a **Sor hozzáadása** parancsra.

8. A **Munkarendelés** mezőben válasszon ki egy munkarendelést. A kapcsolódó mezők frissítése automatikusan történik.

9. Ha több munkarendelést szeretne hozzáadni, ismételje meg a 7-8. lépést.

10. A **Rendezési sorrend** mezőben jelezheti, hogy a munkarendeléseket meghatározott sorrendben kell-e végrehajtani. A kiválasztott munkarendelések megadott sorrendjét az 1, 2, 3 stb. számok megadásával határozhatja meg.

11. **A munkarendelések** gombra kattintva megtekintheti a munkarendelés-gyűjtőben szereplő munkarendelések listáját.

12. Kattintson a **Kapacitásterhelés** gombra a **Kapacitásterhelés** pont megnyitásához a karbantartási ütemezéshez, a nem ütemezett munkarendelésekhez és az ütemezett munkarendelésekhez kapcsolódó kapacitásterhelés kiszámításához és megtekintéséhez.

13. A **Cikkelőrejelzés** gombra kattintva megnyílik a **Cikkelőrejelzés**, ahol cikkekkel (pótalkatrészekkel és egyéb szükséges cikkekkel) kapcsolatos előrejelzéseket számíthat ki és tekinthet meg a karbantartási ütemezéshez, nem ütemezett munkarendelésekhez és ütemezett munkarendelésekhez kapcsolódóan.

14. Kattintson a **Munkarendelés beszerzési igénylése** gombbal a **Munkarendelés beszerzési igénylése** lista megnyitásához, ahol a munkarendelésgyűjtőben szereplő munkarendelésekhez kapcsolódó beszerzési igénylések listája látható.

15. Kattintson a **Munkarendelés-beszerzés** gombra a **Munkarendelés-beszerzés** lista megnyitásához, ahol a munkarendelés-gyűjtőben szereplő munkarendelésekhez kapcsolódó beszerzési rendelések listája látható.

>[!NOTE]
>Ha egy munkarendelés-gyűjtő már nem releváns a munkatervezéshez, akkor a gyűjtő **Aktív** jelölőnégyzetét állítsa „Nem” értékre a **Munkarendelés-gyűjtő** listanézetében.

Jelölje be a **Munkarendelés-kapcsolatok törlése** jelölőnégyzetet, ha az összes munkarendelési sort törölni szeretné, például azért, hogy üres gyűjtőt hozzon létre, amelyet később más munkarendelésekhez használhat. Ne felejtse el törölni a **Munkarendelés-kapcsolatok törlése** jelölőnégyzetet, ha a munkarendelés-gyűjtőt szeretné használni a későbbiekben új munkarendelés-kapcsolatok létrehozásához.


![1. ábra](media/22-work-orders.png)


## <a name="add-work-order-to-a-work-order-pool"></a>Munkarendelés hozzáadása egy munkarendelés-gyűjtőhöz

A fenti szakaszban leírt módon munkarendeléseket adhat hozzá a munkarendelés-gyűjtőhöz, amikor létrehozza a gyűjtőt. Munkarendeléseket az **Összes munkarendelés** listából is hozzáadhat egy munkarendelés-gyűjtőhöz.

1. Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.

2. Válassza ki a munkarendelést a listán, majd kattintson a **Munkarendelés-gyűjtő** elemre.

3. Válassza a „Hozzáadás” lehetőséget a **Hozzáadás/eltávolítás** mezőben.

4. Válassza a munkarendelés-gyűjtőt a **Gyűjtő** mezőben.

5. Kattintson az **OK** gombra.

6. Miután a munkarendelést a munkarendelés-gyűjtőhöz adta, ha szeretné a munkarendelést a gyűjtőben meghatározott sorrendbe tenni: Nyissa meg a munkarendelés-gyűjtő egyik listaoldalát, válassza ki a gyűjtőt, majd kattintson a **Szerkesztés** lehetőségre, és rendezze a gyűjtőben található munkarendelések rendezési sorrendjét a **Munkarendelés-gyűjtő** űrlap > **Munkarendelések** gyorslap > **Rendezési sorrend** mezőben.

Ha egy munkarendelési gyűjtőből szeretné eltávolítani a kiválasztott munkarendelést, válassza a 3. lépésben az „Eltávolítás” lehetőséget.

