---
title: Munkasablon beállítása beszerzési rendelésekhez
description: Ez a témakör a bevételezett cikkek betárolásakor alkalmazandó egyszerű munkasablon beállítását ismerteti.
author: ShylaThompson
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkTemplateTable, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6628936a56619de255ca7dc7b332b5819918c310
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429729"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a>Munkasablon beállítása beszerzési rendelésekhez

[!include [banner](../../includes/banner.md)]

Ez a témakör a bevételezett cikkek betárolásakor alkalmazandó egyszerű munkasablon beállítását ismerteti. A munkasablonok határozzák meg a raktári dolgozó számára mobilkészüléken biztosított utasításkészletet, amikor cikkeket helyez át a bevételezési területről. Használhatja ezt az eljárást a USMF bemutatócégnél említett adatokkal. Mielőtt belekezdene ebbe az útmutatóba, hozzon létre egy munkagyűjtő-azonosítót. Ebben a példában egy a Bejövőben meghívott munkagyűjtő-azonosítót használunk. Ezt az eljárást a raktári vezető használja.

1. A navigációs ablaktáblán ugorjon a **Modulok > Raktárkezelés > Beállítás > Munka > Munkasablonok** lehetőségre.
2. A **Munka rendeléstípusa** mezőben válassza ki a **Beszerzési rendelések** elemet.

## <a name="create-a-work-template-header"></a>Munkasablonfejléc létrehozása
1. Válassza az **Új** lehetőséget.
2. Adjon meg egy számot a **Sorozatszám** mezőben. A munkasablonok kiértékelése ebben a sorrendben történik. A sorrendet módosíthatja ha szükséges.  
3. Írjon be egy értéket a **Munkasablon** mezőbe. Ez ennek a sablonnak az egyedi azonosítója.  
4. Írjon be egy értéket a **Munkasablon leírása** mezőbe.
    - Amíg nem töltött ki a sablonhoz szükséges minden információt, és nem kattintott a **Mentés** gombra, az **Érvényes** lehetőség nem lesz bejelölve.  
    - Egy **Beszerzési rendelés** típusú munkarendelést nem lehet automatikusan feldolgozni, ezért az **Automatikus feldolgozás** lehetőségnél meg kell tartani a **Nem** beállítást.  
5. Írjon be egy értéket a **Munkagyűjtő azonosítója** mezőbe. A munkagyűjtők azonosítói segítségével a munkát csoportokba rendezheti. Az itt beállított érték lesz az alapértelmezett érték minden ezzel a sablonnal létrehozott munka esetében.  
6. Írja be az `1` értéket a **Munkaprioritás** mezőbe. Ez a munka fontosságát jelzi, és az itt beállított érték lesz az alapértelmezett minden ezzel a sablonnal létrehozott munka esetében.  
7. Válassza a **Mentés** lehetőséget. El kell menteni a munkasablon fejlécét, mielőtt a **Lekérdezés szerkesztése** gomb elérhetővé válna.  

## <a name="set-up-the-query-for-the-work-template"></a>A munkasablonhoz használt lekérdezés beállítása
1. Válassza ki a **Lekérdezés szerkesztése** lehetőséget. Be fogunk állítani egy korlátozást, amely következtében a sablon csak egy konkrét raktárban lesz használható.  
2. Válassza a **Hozzáadás** lehetőséget.
3. Az új sor **Mező** mezőjében adja meg a `warehouse` értéket.
4. Adjon meg egy értéket a **Feltétel** mezőben.
5. Válassza ki az **OK** lehetőséget.
6. Válassza ki az **Igen** lehetőséget.

## <a name="set-work-template-details"></a>Munkasablonrészletek beállítása
1. Válassza az **Új** lehetőséget.
2. A **Munkatípus** mezőben válassza a **Kitárolás** lehetőséget.
3. Írja be, hogy `purchase` a **Munkagyűjtő-azonosító** mezőbe. Az itt beállított munkaosztály lesz az alapértelmezett minden olyan Kitárolás típusú munkasor esetében, amelyet ezzel a sablonnal hoztak létre. A munkaosztályt nem lehet felülbírálni a munka rendeléssorokból. A munkaosztályokkal irányítható és/vagy korlátozható azon munkarendeléssorok típusa, amelyeket egy raktári dolgozó feldolgozhat egy mobileszközön.  
4. Válassza az **Új** lehetőséget.
5. A **Munkatípus** mezőben válassza a **Betárolás** lehetőséget.
6. Írjon be egy értéket a **Munkaosztály** azonosítója mezőbe. A kitárolási és a betárolási utasítások egy készletet alkotnak. Minden kitárolás/betárolás-készletnek ugyanabba a munkaosztályba kell tartoznia. Ugyanazt a munkaosztályt használja, amelyet megadott a kitárolási utasításhoz.  
7. Válassza a **Mentés** lehetőséget. Az **Érvényes** jelölőnégyzet most már be van jelölve.  

