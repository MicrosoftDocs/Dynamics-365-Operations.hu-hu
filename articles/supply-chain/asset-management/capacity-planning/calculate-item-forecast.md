---
title: Cikkelőrejelzés kiszámítása
description: Ez a témakör azt mutatja be, hogyan lehet kiszámítani a cikkelőrejelzést az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 08/16/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9091ff7a394cd08b68e78c8f668d7cd962003e6d
ms.sourcegitcommit: 109a6ef2d20758dc4a25c51b11e22dd2214a1cc4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1886770"
---
# <a name="calculate-item-forecast"></a>Cikkelőrejelzés kiszámítása

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Csakúgy, mint a kapacitásterhelési számításoknál, amelyek leírása az előző részben szerepel, a cikkek előrejelzési számításait is megteheti.

- Karbantartási ütemezési sorok  
- Még nem ütemezett munkarendelések  
- Ütemezett munkarendelések

Ez akkor lehet hasznos, ha egy adott időszakra vonatkozóan áttekintést szeretne kapni a várható cikkfelhasználásról (pótalkatrészek, valamint a munkarendelések befejezéséhez szükséges egyéb cikkek). A kapacitás terhelésének számítása a cikkelőrejelzéseknél minden eszközön vagy a kiválasztott eszközökön végezhető el. Számítás végezhető a karbantartási állásidővel kapcsolatos tevékenységekről (**Összes karbantartási állásidő tevékenység** vagy **Aktív karbantartási állásidő tevékenységek**), vagy egy munkarendelési gyűjtőkről (**Minden munkarendelési gyűjtő** vagy **Aktív munkavégzési gyűjtők**).

1. Kattintson az **Eszközkezelés** > **Lekérdezések** > **Cikkelőrejelzés**, vagy az **Eszközkezelés** > **Közös** > **Munkavégzési gyűjtők** > **Összes munkarendelési gyűjtő** / **Aktív munkarendelés-gyűjtők** > válassza a munkarendelés-gyűjtőt a listában > **Cikkelőrejelzés** gomb, vagy **Eszközkezelés** > **Közös** > **Karbantartás miatti üzemkimaradás tevékenységek** > **Minden karbantartás miatti üzemkimaradás tevékenység** / **Aktív karbantartás miatti üzemkimaradás tevékenységek** > a karbantartás miatti üzemkimaradás tevékenység kiválasztása a listában > **Cikkelőrejelzés** gomb.

2. A **Cikkelőrejelzés kiszámítása** párbeszédablakban válasszon ki egy időszakot a számításhoz a **Kezdő dátum/idő** és a **Záró dátum/idő** mezőben.

3. Ha az előrejelzési számításban szerepeltetni szeretné a karbantartási ütemezés sorait, válassza az „Igen” beállítást a **Karbantartási ütemezés befoglalása** gombbal.

4. Ha az előrejelzési számításban szerepeltetni szeretné a munkarendelés feladatokat, válassza az „Igen” beállítást a **Munkarendelés befoglalása** gombbal.

5. A **Szint** mezőben adhatja meg, hogy a cikkelőrejelzési sorok milyen részletesen jelenítse meg a munkavégzési helyszíneket. Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a karbantartási ütemezés minden munkavégzési helyszínhez tartozó sora és munkarendelése a legfelső szinten jelenik meg, így a sorban szereplő óraszámok hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből. Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely a karbantartási ütemezési minden sorát és minden munkarendelést megjelenít az összes olyan munkavégzési helyszín szintnél, amelyhez a sor kapcsolódik.

6. Kattintson az **OK** gombra az számítás indításához.

7. Az Eszközórák ellenőrzése lapon a **Csoportosítási szempont...** műveleti ablaktáblacsoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez. A kiválasztott műveleti ablaktáblacsoport gombjai kék színnel vannak kiemelve. A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.

8. Kattintson a **Dimenziók megjelenítése** gombra, ha meg szeretné tekinteni a cikkekhez kapcsolódó terméket, tárolóhelyet vagy nyomon követési dimenziókat. Jelölje be a megfelelő jelölőmezőket, és kattintson az **OK** gombra.

Az alábbi képernyőfotó egy példát mutat a felületre.

![1. ábra](media/02-capacity-planning.png)
