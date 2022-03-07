---
title: Karbantartás állapota
description: Ez a témakör azt mutatja be, hogyan lehet kiszámítani a karbantartási állapotot az Eszközkezelés modulban.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetStatusCalculate, EntAssetStatus
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 138e2e72fbf761d209d288c2bd778c08519b9c69b0715f4466d4838255a2a31e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752009"
---
# <a name="maintenance-status"></a>Karbantartás állapota

[!include [banner](../../includes/banner.md)]

 

Az Eszközkezelésben számítást végezhet, hogy egy adott időszakra vonatkozóan áttekintést kapjon az új, az aktív és a befejezett karbantartási kérésekről, munkarendelésekről és karbantartás miatti üzemkimaradásokról. Az időszakra vonatkozóan megtekintheti az elvégzett állapotfelmérések számát is. A számítással áttekintést kaphat a beérkező és a teljesített karbantartási kérésekre és munkarendelésekre vonatkozó terhelésekről.

## <a name="make-a-maintenance-status-calculation"></a>Karbantartási állapot számításának elkészítése

1. Kattintson az **Eszközkezelő** > **Lekérdezések** > **Karbantartás állapota** elemre.

2. Az **Állapot kiszámítása** párbeszédpanel **Kezdő dátum** és **Záró dátum** mezőjében válassza ki azt az időtartományt, amelyhez el szeretné végezni a számítást.

3. A **Szint** mezőben megadhatja, hogy a karbantartási sorok milyen részletesen jelenítsék meg a munkavégzési helyszíneket. 

  Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a munkavégzési helyszínekhez tartozó karbantartási sorok a legfelső szinten jelenik meg, így a sorban szereplő állapot hozzáadható az alacsonyabb szinten található munkavégzési helyszínekből. 
  
  Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely minden karbantartási sort megjelenít az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.

4. Kattintson az **OK** gombra az számítás indításához.

5. Kattintson a **Csoportosítási szempont...** gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez. A kiválasztott **Csoportosítási szempont…** ablaktáblacsoport gombjai ki vannak emelve. A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.

6. Ne felejtsen a **Frissítés** gombra kattintani frissíteni a számítást, amikor a **Csoportosítás alapja...** gombok aktiválásával vagy inaktiválásával módosítást végez, vagy új időszakhoz végez számítást.

7. Ha új karbantartási állapothoz szeretne számítást végezni, kattintson az **Állapot** elemre.

>[!NOTE]
>A **Karbantartás állapota** részen látható eredmények csak a tényleges kezdési dátummal és idővel rendelkező karbantartási kéréseket és munkarendeléseket tartalmazzák. A záró dátum és időpont üres is lehet.

## <a name="example-1"></a>1. példa

Az alábbi képernyőfotón az **Év** és a **Hónap** gomb aktiválva látható. Ezen **Csoportosítási szempot…** beállítások kiválasztásával havi szinten általános áttekintést kaphat a karbantartási kérésekhez és a munkarendelésekhez kapcsolódó terhelésről és teljesítményről. 

![Példa a havi terhelésre.](media/13-controlling-and-reporting.png)

## <a name="example-2"></a>2. példa

Az alábbi képernyőfotón a munkavégzési helyszínekkel kapcsolatos információk is hozzá lettek adva. Most összehasonlíthatja a többek között földrajzi helyeket, gyárakat vagy munkaterületeket jelölő munkavégzési helyszínek terhelését és teljesítményét. 

![Példa a munkavégzési helyszíneket tartalmazó havi terhelésre.](media/14-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]