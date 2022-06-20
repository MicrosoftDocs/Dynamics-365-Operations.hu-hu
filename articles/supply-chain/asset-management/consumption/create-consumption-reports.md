---
title: Felhasználási jelentések létrehozása
description: Ez a cikk bemutatja, hogyan lehet felhasználási jelentéseket létrehozni az eszközkezelésben.
author: johanhoffmann
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 136d6248db8012e5870e0627ddbd3703aa63703b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852900"
---
# <a name="create-consumption-reports"></a>Felhasználási jelentések létrehozása

[!include [banner](../../includes/banner.md)]

 

Amikor létrehozta és feladta a felhasználási regisztrációkat a munkarendelésekre az Eszközkezelőben, két jelentés használható a felhasználás adatainak megjelenítésére.


## <a name="asset-consumption-report"></a>Eszközfelhasználási jelentés

A felhasználás munkarendelésekre való feladásakor kinyomtathatja az eszközfelhasználási jelentést. A jelentés megjeleníti az eszközökre feladott órákat, óraköltségeket, cikk-költségeket és költségeket.

1. Kattintson az **Eszközkezelés** > **Jelentések** > **Eszközök** > **Eszközfelhasználás** elemre.

2. Az **Eszközfelhasználás** párbeszédpaneljén válassza ki azokat a paramétereket és részletességi szintet, amelyet meg szeretne jeleníteni az **Igen** gombra kattintva a megfelelő gombsoron, és beadva a munkavégzési helyszín szintjét a **Megjelenítés** szakaszba.
    - A **Szintek** mezőben megadhatja, hogy az eszközsorok milyen részletesen jelenítsék meg a munkavégzési helyszíneket. 
    
        Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor minden munkavégzési helyszínhez tartozó eszköz a legfelső szinten jelenik meg, így a sorban hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből. 
        
        Ha a „0” értéket adja meg a **Szintek** mezőben, akkor részletes eredmény jelenik meg, amely minden eszközt megjeleníti az összes olyan munkavégzési helyszín szintnél, amelyhez a sor kapcsolódik. 
        
    - Válassza az **Igen** beállítást az **Összes aleszköz összegei** átváltási gombján, ha a jelentésben szereplő minden egyes aleszköz összegeit meg szeretné tekinteni.

3. Válassza ki a dátumtartomány értékét a **Dátumok** részben.

4. A **Cél** gyorslapon válassza ki, hogy a jelentést a képernyőn szeretné megjeleníteni, nyomtatni szeretné, vagy fájlként vagy e-mailben menteni.

5. Szükség esetén kiválaszthatja a jelentésben megjelenítendő eszközöket is. A **Szerepeltetni kívánt rekordok** gyorslapján kattintson a **Szűrő** elemre, és adja hozzá a jelentésben szerepeltetni kívánt eszközöket.

6. A jelentés előállításához kattintson az **OK** gombra.


## <a name="work-order-consumption-report"></a>Munkarendelés felhasználási jelentése

A felhasználás munkarendelésekre való feladásakor kinyomtathatja a munkarendelés-felhasználási jelentést. A jelentés megjeleníti a munkarendelésekre feladott órákat, óraköltségeket, cikk-költségeket és költségeket.

1. Kattintson az **Eszközkezelés** > **Jelentések** > **Munkarendelések** > **Munkarendelés felhasználás** pontra.

2. A **Munkarendelési felhasználási** párbeszédpaneljén válassza ki azokat a paramétereket, amelyeket bele szeretne foglalni a jelentésbe, az **Igen** lehetőséget kiválasztásával a megfelelő gombokon a **Megjelenítés** szakaszban.

3. Válassza ki a dátumtartomány értékét a **Dátumok** részben.

4. A **Cél** gyorslapon válassza ki, hogy a jelentést a képernyőn szeretné megjeleníteni, nyomtatni szeretné, vagy fájlként vagy e-mailben menteni.

5. Szükség esetén kiválaszthatja a jelentésben megjelenítendő munkarendeléseket is. A **Szerepeltetni kívánt rekordok** gyorslapján kattintson a **Szűrő** elemre, és adja hozzá a jelentésben szerepeltetni kívánt munkarendeléseket.

6. A jelentés előállításához kattintson az **OK** gombra.


>[!NOTE]
>Létrehozhat egy [munkarendelési jelentést](../work-orders/work-order-report.md) is, amely több munkarendelési adatot tartalmaz.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]