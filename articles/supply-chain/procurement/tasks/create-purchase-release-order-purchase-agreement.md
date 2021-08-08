---
title: Beszerzési megállapodás alkalmazása beszerzési rendelés létrehozásakor
description: Ez az eljárás bemutatja, hogyan lehet használni egy beszerzési szerződést, amikor beszerzési rendelést hoz létre.
author: kamaybac
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 341d3f37936bcca8d8b273894b4a12debfe6eced
ms.sourcegitcommit: 787c94b35f343f4c38fc8efaaa0cfaf20a846368
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/21/2021
ms.locfileid: "6647182"
---
# <a name="apply-a-purchase-agreement-when-creating-a-purchase-order"></a>Beszerzési megállapodás alkalmazása beszerzési rendelés létrehozásakor

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet használni egy beszerzési szerződést, amikor beszerzési rendelést hoz létre. A beszerzési szerződést a beszerzési rendelés létrehozásakor kell alkalmazni, mivel az általános feltételeket át kell másolni a beszerzési rendelés fejlécébe. Általában ez a feladatot egy beszerzési ügynök végzi el. Az útmutató előfeltétele a szállító és a cikkek hatályos beszerzési megállapodása egy termékmennyiségi kötelezettséggel. Ugyanezt az eljárást akkor is használhatja, ha a beszerzési szerződés más típusú kötelezettségvállalásokra vonatkozik.

## <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása

1. Ugrás a **Termelés és beszerzés \> Munkaterületek \> Beszerzési rendelés előkészítése** helyre.
1. Kattintson a Műveleti panelen az **Új beszerzési rendelés** lehetőségre.
1. Megjelenik a **Beszerzési rendelés létrehozása** párbeszédpanel. Válasszon ki egy **Szállítói számlát**. Vizsgálja meg és módosítsa a többi címmezőt, ahogy szükséges.
1. Bontsa ki az **Általános** gyorslapot.
1. A **Beszerzési szerződés** mezőben keresse meg és válassza ki a használni kívánt hatályos szerződést. A szállítóhoz rendelt összes rendelkezésre álló megállapodás itt van felsorolva.  
1. Válassza ki az **Igen** lehetőséget.
1. Válassza ki az **OK** lehetőséget.

## <a name="add-a-line"></a>Sor hozzáadása

1. A **Cikkszám** mezőbe írjon egy értéket. Ha adott készlet vagy a helydimenziók vannak a kötelezettségvállaláson, akkor meg kell adni ugyanazokat az értékeket a beszerzésirendelés-soron a megállapodás használatához.
1. A **Telephely** mezőben válassza a legördítő nyilat a keresőlista megnyitásához. A hely már ki lehet töltve az alapértelmezett értékekkel a rendelésből, vagy a szállítótól. Ha ez a helyzet, hagyja ki ezt a lépést.  
1. Keresse meg és jelölje ki a kívánt rekordot a listán.
1. A listában válassza ki a kiválasztott sorból a hivatkozást.
1. Adjon meg egy számot a **Mennyiség** mezőben. Ellenőrizze, hogy az árat átmásolta-e a kötelezettségvállalásból.  

## <a name="look-up-the-commitment"></a>A kötelezettségvállalás megkeresése

1. Válassza ki a **Sor frissítése** lehetőséget.
1. Válassza a **Mellékelve** elemet. Itt kaphat részleteket a beszerzési szerződésről. Például láthatja az árat, és azt, hogy az ár és engedmény rögzített-e, azaz ha az árat és az engedményt a beszerzési rendelésen egy másik értékre módosítja, mint a kötelezettségvállaláson, a rendszer eltávolítja a hivatkozást, hogy a beszerzésirendelés-sor ne feleljen meg a kötelezettségvállalásnak. Látható az is, hogy a Maximum betartatása beállítás meg van-e adva, ami azt jelenti, hogy a kötelezettségvállaláson szereplő mennyiség nem lépheti túl a kötelezettségvállalást teljesítő beszerzések összegét.  
1. Zárja be a lapot.

## <a name="look-up-the-purchase-agreement"></a>Beszerzési szerződés megkeresése

1. A **Műveleti ablaktáblán** válassza ki az **Általános** elemet.
1. Válassza **Beszerzési szerződés** lehetőséget.
1. Zárja be a lapot.
1. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]