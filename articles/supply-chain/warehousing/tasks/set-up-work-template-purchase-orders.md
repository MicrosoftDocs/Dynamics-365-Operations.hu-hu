--- 
title: "A beszerzési rendelések munkasablonjának beállítása"
description: "Ez az eljárás egy olyan, egyszerű munkasablon beállítására összpontosít, amelyet a bevételezett cikkek betárolásakor alkalmaznak majd."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fbbe019bdca2d5182466a20370418a14032fe63d
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-work-template-for-purchase-orders"></a>A beszerzési rendelések munkasablonjának beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás egy olyan, egyszerű munkasablon beállítására összpontosít, amelyet a bevételezett cikkek betárolásakor alkalmaznak majd. A munkasablonok határozzák meg a raktári dolgozó számára mobilkészüléken biztosított utasításkészletet, amikor cikkeket helyez át a bevételezési területről. Használhatja ezt az eljárást a USMF bemutatócégnél említett adatokkal. Mielőtt belekezdene ebbe az útmutatóba, hozzon létre egy munkagyűjtő-azonosítót. Ebben a példában egy a Bejövőben meghívott munkagyűjtő-azonosítót használunk. Ezt az eljárást a raktári vezető használja.

1. Ugrás a Raktárkezelés > Beállítás > Munka > Munkasablonokra.
2. A Munka rendeléstípus mezőben válassza ki a „Beszerzési rendelések” elemet.

## <a name="create-a-work-template-header"></a>Munkasablonfejléc létrehozása
1. Kattintson az Új lehetőségre.
2. Adjon meg egy számot a Sorozatszám mezőben.
    * A munkasablonok kiértékelése ebben a sorrendben történik. A sorrendet módosíthatja ha szükséges.  
3. Írjon be egy értéket a Munkasablon mezőbe.
    * Ez ennek a sablonnak az egyedi azonosítója.  
4. Írjon be egy értéket a Munkasablon leírása mezőbe.
    * Amíg nem töltött ki a sablonhoz szüksége minden információt, és kattintott ezután a Mentés gombra, az Érvényes lehetőség nem lesz bejelölve.  
    * Egy Beszerzési rendelés típusú munkarendelést nem lehet automatikusan feldolgozni, ezért az Automatikus feldolgozás lehetőségnél meg kell tartani a Nem beállítást.  
5. Írjon be egy értéket a Munkagyűjtő-azonosító mezőbe.
    * A munkagyűjtők azonosítói segítségével a munkát csoportokba rendezheti. Az itt beállított érték lesz az alapértelmezett érték minden ezzel a sablonnal létrehozott munka esetében.  
6. Írja be az „1” értéket a Munkaprioritás mezőbe.
    * Ez a munka fontosságát jelzi, és az itt beállított érték lesz az alapértelmezett minden ezzel a sablonnal létrehozott munka esetében.  
7. Kattintson a Mentés gombra.
    * El kell menteni a munkasablon fejlécét, mielőtt a Lekérdezés szerkesztése gomb elérhetővé válna.  

## <a name="set-up-the-query-for-the-work-template"></a>A munkasablonhoz használt lekérdezés beállítása
1. Kattintson A lekérdezés szerkesztése elemre.
    * Be fogunk állítani egy korlátozást, amely következtében a sablon csak egy konkrét raktárban lesz használható.  
2. Kattintson a Hozzáadás gombra.
3. A listában jelölje meg a kiválasztott sort.
4. A Mező mezőbe írja be, hogy „raktár”.
5. Érték beírása a Feltétel mezőbe.
6. Kattintson az OK gombra.
7. Kattintson az Igen gombra.

## <a name="set-work-template-details"></a>Munkasablonrészletek beállítása
1. Kattintson az Új lehetőségre.
2. A Munkatípus mezőben válassza a „Kitárolás” lehetőséget.
3. Írja be, hogy „beszerzés” a Munkagyűjtő-azonosító mezőbe.
    * Az itt beállított munkaosztály lesz az alapértelmezett minden olyan Kitárolás típusú munkasor esetében, amelyet ezzel a sablonnal hoztak létre. A munkaosztályt nem lehet felülbírálni a munka rendeléssorokból. A munkaosztályokkal irányítható és/vagy korlátozható azon munkarendeléssorok típusa, amelyeket egy raktári dolgozó feldolgozhat egy mobileszközön.  
4. Kattintson az Új lehetőségre.
5. A Munkatípus mezőben válassza a „Betárolás” lehetőséget.
6. Írjon be egy értéket a Munkaosztály azonosítója mezőbe.
    * A kitárolási és a betárolási utasítások egy készletet alkotnak. Minden kitárolás/betárolás-készletnek ugyanabba a munkaosztályba kell tartoznia. Ugyanazt a munkaosztályt használja, amelyet megadott a kitárolási utasításhoz.  
7. Kattintson a Mentés gombra.
    * Az érvényes jelölőnégyzet most már be van jelölve.  


