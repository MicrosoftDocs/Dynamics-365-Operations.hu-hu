---
title: Munkarendelés-gyűjtők
description: Ez a témakör bemutatja a munkarendelés-gyűjtők használatát az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTablePoolPart, EntAssetWorkOrderPoolReferenceInfoPart, EntAssetWorkOrderPool, EntAssetWorkOrderPoolPreviewPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3e95a4fdfaf4817867f3d2df7774df6a27ee6599
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429813"
---
# <a name="work-order-pools"></a>Munkarendelés-gyűjtők

[!include [banner](../../includes/banner.md)]


A munkarendelés-gyűjtőkkel csoportosíthatja a valamiben egyeztő munkarendeléseket. Íme néhány példa olyan dolgokra, amelyekhez létrehozhat munkarendelés-gyűjtőket:

- Munkaszemélyzet, például A karbantartási személyzet vagy B karbantartási személyzet  

- Szakmához kapcsolódó szakértelmek, például villanyszerelők vagy vízvezeték-szerelők  

- Fizikai helyek  

- Időbeosztások, például hetek vagy más időszakok  

A szükséges módon egyetlen munkarendelést is beállíthat több munkarendelés-gyűjtőben.


## <a name="create-a-work-order-pool"></a>Egy munkarendelés-gyűjtő létrehozása

Az **Összes munkarendelés-gyűjtő** vagy **Aktív munkarendelés-gyűjtők** listaoldalon áttekintést kaphat saját munkarendelés-gyűjtőiről, és új gyűjtőket hozhat létre.

1. Válassza az **Eszközkezelés** > **Általános** > **Munkarendelés-gyűjtők** > **Összes munkarendelés-gyűjtő** vagy **Aktív munkarendelés-gyűjtők** elemet.

2. Válassza az **Új** lehetőséget.

3. A **Gyűjtő** mezőben adja meg a munkarendelés-gyűjtő azonosítóját.

4. A **Név** mezőben adjon meg egy nevet.

5. Válassza az **Igen** lehetőséget az **Aktív** beállításnál, amellyel jelezheti, hogy a munkarendelés-gyűjtő aktív.

6. Állítsa **Igen** értékre a **Munkarendelés kapcsolatainak törlése** beállítást, ha szeretne automatikusan eltávolítani munkarendeléseket a munkarendelés-gyűjtőből.

7. Az **Életciklus-állapot törlése** mezőben válassza a munkarendelés életciklus-állapotát. Például a munkarendelés befejezéséhez tartozó munkarendelési életciklus-állapotot beállíthatja, hogy automatikusan törölje a kapcsolatokat a munkarendelés-gyűjtőkből.

    A munkarendelés-gyűjtőhöz azonnal hozzáadhat munkarendeléseket.

8. A **Munkarendelések** gyorslapon válassza a **Sor hozzáadása** parancsot.

9. A **Munkarendelés** mezőben válasszon ki egy munkarendelést. A kapcsolódó mezők frissítése automatikusan történik.

10. További munkarendelések hozzáadásához ismételje meg a 8–9. lépéseket.

11. Ha a hozzáadott munkarendeléseket meghatározott sorrendben kell végrehajtani, akkor a **Rendezési sorrend** mezőbe írja be az **1**, **2**, **3**, és így tovább értékeket a sorrend meghatározásához.

12. A munkarendelési gyűjtőben lévő összes munkarendelés listájának megtekintéséhez kattintson a Művelet ablaktáblán a **Munkarendelési gyűjtő** lapon a **Munkarendelési gyűjtőhöz kapcsolódó** csoportra, válassza a **Munkarendelések** elemet az **Összes munkarendelés** listaoldal megnyitásához.

13. A karbantartási ütemezés, nem ütemezett munkarendelések és az ütemezett munkarendelések kapacitásterhelésének kiszámításához és megjelenítéséhez kattintson a Művelet panel **Munkarendelés** lapján a **Munkarendelési gyűjtőhöz kapcsolódó** csoportra, válassza ki a **Kapacitásterhelés** lehetőséget a **Kapacitásterhelés kiszámítása** párbeszédpanel megnyitásához.

14. A karbantartási ütemezés, nem ütemezett munkarendelések és az ütemezett munkarendelések cikkelőrejelzéseinek (cserealkatrészek és más szükséges elemek) kiszámításához és megjelenítéséhez kattintson a Művelet panel **Munkarendelés** lapján a **Munkarendelési gyűjtőhöz kapcsolódó** csoportra, válassza ki a **Cikkelőrejelzés** lehetőséget a **Cikkelőrejelzés kiszámítása** párbeszédpanel megnyitásához.

15. A munkarendelési gyűjtőben lévő munkarendelésekhez kapcsolódó beszerzési igénylések megtekintéséhez kattintson a Művelet ablaktáblán a **Munkarendelési gyűjtő** lapon a **Bezserzés** csoportra, válassza a **Munkarendelés beszerzési igénylései** elemre az **A Munkarendelés beszerzési rendelései** listaoldal megnyitásához.

16. A munkarendelési gyűjtőben lévő munkarendelésekhez kapcsolódó beszerzési rendelései megtekintéséhez kattintson a Művelet ablaktáblán a **Munkarendelési gyűjtő** lapon a **Bezserzés** csoportra, válassza a **Munkarendelés beszerzési igénylései** elemre az **A Munkarendelés beszerzései** listaoldal megnyitásához.

>[!NOTE]
>Ha egy munkarendelés-gyűjtő már nem releváns a munkatervezéshez, akkor a gyűjtő **Aktív** lehetőségét állítsa be **Nem** értékre a **Munkarendelés-gyűjtő** oldalának listanézetében.

Az összes alkdolgozó rendelési sor törléséhez állítsa a **Munkarendelés- kapcsolatok törlése** beállítást **Igen** értékre. Ez a beállítás például akkor hasznos, ha egy üres gyűjtőt szeretne létrehozni, amelyet később más munkarendelésekhez használhat. Ha elkészült, ne felejtse a **Munkarendelés-kapcsolatok törlése** lehetőséget **Nem** értékre állítani, ha a munkarendelés-gyűjtőt szeretné használni a későbbiekben új munkarendelés-kapcsolatok létrehozásához.

Az alábbi ábra a **Munkarendelés-gyűjtő létrehozása** listaoldal egy példáját mutatja be.

![1. ábra](media/22-work-orders.png)


## <a name="add-a-work-order-to-a-work-order-pool"></a>Egy munkarendelés hozzáadása egy munkarendelés-gyűjtőhöz

Az előző szakaszban leírt módon munkarendeléseket adhat hozzá a munkarendelés-gyűjtőhöz, amikor létrehozza azt a gyűjtőt. Az **Összes munkarendelések** vagy **Aktív munkarendelések** listaoldalon is hozzáadhat munkarendeléseket a munkarendelés-gyűjtőkhöz.

1. Válassza ki a munkarendelést, majd a Művelet panel **Munkarendelés** lapján a **Karbantartás** csoportban válassz a **Munkarendelés-gyűjtő** pontot.

2. Válassza ki a munkarendelést a listán, majd kattintson a **Munkarendelés-gyűjtő** elemre.

3. A **Munkarendelés-gyűjtő karbantartása** párbeszédablakban a **Hozzáadás /eltávolítás** mezőben válassza a **Hozzáadás** elemet.

4. Válassza a munkarendelés-gyűjtőt a **Gyűjtő** mezőben.

5. Válassza ki az **OK** lehetőséget.

6. Ha azt szeretné a hozzáadott munkarendelést egy meghatározott sorrendbe helyezze a munkarendelés-gyűjtőben, az **Összes munkarendelés-gyűjtő** vagy az **Aktív munkarendelés-gyűjtők** listaoldalán válassza ki a gyűjtőt majd válassza a **Szerkesztés** parancsot. Ezt követően a **Munkarendelési gyűjtő** lap **Munkarendelések** gyorslapján a **Rendezési sorrend** mező segítségével módosíthatja a gyűjtőbe foglalt munkarendelések rendezési sorrendjét.

A munkarendelési gyűjtőből egy kiválasztott munkarendelés eltávolításához, válassza a 3. lépésben az **Eltávolítás** lehetőséget.

