---
title: Felhasználási jelentések létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet felhasználási jelentéseket létrehozni az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 08/21/2019
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
ms.openlocfilehash: eecfb101af9a91f515aab221181c54d53e358a68
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652425"
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

