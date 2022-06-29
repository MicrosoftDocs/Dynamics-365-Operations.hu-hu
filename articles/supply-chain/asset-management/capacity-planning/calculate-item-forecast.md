---
title: Cikkelőrejelzés kiszámítása
description: Ez a cikk bemutatja a cikk-előrejelzés kiszámítását az Eszközkezelésben.
author: johanhoffmann
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetItemForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 25e9b00533fb183b27c1bbe616cf6f414b44b5e7
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016101"
---
# <a name="calculate-item-forecast"></a>Cikkelőrejelzés kiszámítása

[!include [banner](../../includes/banner.md)]

 

Csakúgy, mint a kapacitásterhelési számításoknál, amelyek leírása az előző részben szerepel, a cikkek előrejelzési számításait is megteheti:

- karbantartási ütemezési sorok  
- még nem ütemezett munkarendelések  
- ütemezett munkarendelések

Ez akkor lehet hasznos, ha egy adott időszakra vonatkozóan áttekintést szeretne kapni a várható cikkfelhasználásról (pótalkatrészek, valamint a munkarendelések befejezéséhez szükséges egyéb cikkek). A kapacitás terhelésének számítása a cikkelőrejelzéseknél minden eszközön vagy a kiválasztott eszközökön végezhető el. Számítás végezhető a karbantartási állásidővel kapcsolatos tevékenységekről (**Összes karbantartási állásidő tevékenység** vagy **Aktív karbantartási állásidő tevékenységek**), vagy egy munkarendelési gyűjtőkről (**Minden munkarendelési gyűjtő** vagy **Aktív munkavégzési gyűjtők**).

1. Kattintson az Eszközkezelés – Lekérdezések cikk-előrejelzésre **vagy** > **·** > **·** **az Eszközkezelés munkarendelési > Minden munkarendelés-> munkarendelési készletet a cikk-előrejelzési listában,** > **·** > **·** / **·** **vagy >** **Tárgyieszköz-karbantartás - leállási tevékenységek mind karbantartási leállási tevékenység aktív karbantartási leállási tevékenységei > válassza ki a karbantartási leállási tevékenységeket a lista >** > **Cikk-előrejelzés** > **gombjával.** / **·** **·**

2. A **Cikkelőrejelzés kiszámítása** párbeszédablakban válasszon ki egy időszakot a számításhoz a **Kezdő dátum/idő** és a **Záró dátum/idő** mezőben.

3. Ha az előrejelzési számításban szerepeltetni szeretné a karbantartási ütemezés sorait, válassza az „Igen” beállítást a **Karbantartási ütemezés befoglalása** gombbal.

4. Ha az előrejelzési számításban szerepeltetni szeretné a munkarendelés feladatokat, válassza az „Igen” beállítást a **Munkarendelés befoglalása** gombbal.

5. A **Szint** mezőben adhatja meg, hogy a cikkelőrejelzési sorok milyen részletesen jelenítse meg a munkavégzési helyszíneket. 

      Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a karbantartási ütemezés minden munkavégzési helyszínhez tartozó sora és munkarendelése a legfelső szinten jelenik meg, így a sorban szereplő óraszámok hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből. 
  
      Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely a karbantartási ütemezési minden sorát és minden munkarendelést megjelenít az összes olyan munkavégzési helyszín szintnél, amelyhez a sor kapcsolódik.

6. Kattintson az **OK** gombra az számítás indításához.

7. A **Csoportosítási szempont...** csoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez. A lenti képen a kiválasztott **Csoportosítási szempont** gombokat kék színnel kiemeli a program. A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.

8. Kattintson a **Dimenziók megjelenítése** gombra, ha meg szeretné tekinteni a cikkekhez kapcsolódó terméket, tárolóhelyet vagy nyomon követési dimenziókat. Jelölje be a megfelelő jelölőmezőket, és kattintson az **OK** gombra.

![1. ábra](media/02-capacity-planning.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]