---
title: Mobileszköz menüelemének beállítása beszerzési rendelés típusú munka befejezéséhez
description: Ez a témakör azt mutatja be, hogyan kerül sor a mobileszköz menüelemeinek beállítására.
author: ShylaThompson
manager: tfehr
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFAutoConfirm, WHSRFMenu
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 905094ae4e76fadbebea1892ec20427f32e3e71d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216827"
---
# <a name="set-up-a-mobile-device-menu-item-for-completing-work-of-type-purchase-order"></a>Mobileszköz menüelemének beállítása beszerzési rendelés típusú munka befejezéséhez

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan kerül sor a mobileszköz menüelemeinek beállítására. Ebben a példában, ez a menüpont a Beszerzési rendelés típusú munkák végrehajtásához használatos. A menüponthoz társított munkaosztály határozza meg, hogy melyik munka érvényes. Ezt az útmutatót használhatja az USMF bemutatócégen. Ezt az eljárást általában a raktárvezető követi nyomon.


## <a name="create-a-mobile-device-menu-item"></a>Mobileszköz-menüpont létrehozása
1. A keresősávba beírva ugorjon a **Mobileszköz menüpontjai** elemre.
2. Válassza az **Új** lehetőséget.
3. Írjon be egy értéket a **Menüelem neve** mezőbe. Egyedi érték megadása. Például megadhatja a `POMove` kifejezést. Jegyezze meg az értéket, később szüksége lesz rá.  
4. Érték beírása a **Cím** mezőbe. Ez az a cím, amely a felhasználók mobileszközein a jelenik meg. Például megadhatja a `PO Move` kifejezést.  
5. A **Mód** mezőben válassza ki a **Munka** lehetőséget.
6. A **Meglévő munka használata** mezőben válassza az **Igen** lehetőséget.
    - A mobileszköz-menüpont meglévő munkához használatos. Ezért ezt **Igen** értékre kell állítania.  
    - A **Készletállapot megjelenítése** mező meghatározza, hogy az aktuális készlet készletállapota megjelenjen a raktári dolgozó mobileszközén.  
7. Az **Irányítja** mezőben válassza ki a **Rendszer-csoportosítás** lehetőséget. Ha valamit kijelöl az **Irányítja** mezőben, további mezők jelennek meg ezen a lapon az **Általános** szakaszban. A megjelenő mezők attól függenek, hogy Ön mit jelölt ki. A **Rendszer-csoportosítás** kiválasztásakor két új mezővel bővül. Ezek magyarázata alább látható.  
8. A **Rendszer-csoportosítás** mezőben válassza ki a **WorkPoolId** szöveget. Amikor a raktári dolgozók megnyitják a menüpontot, a munkagyűjtő azonosító ellenőrzése szükséges lesz. Minden, ehhez a menüponthoz rendelt munkarendelés ezzel a Munkagyűjtő azonosítóval és minden Megnyitott munkarendeléssor munkaosztálya a felhasználóhoz kerül.  
9. Adjon meg egy értéket a **Rendszer-csoportosítási címke** mezőben. Ez a szöveg jelenik meg a mobileszköz-felhasználó számára. Például beírhatja a **Munkagyűjtő** kifejezést.  
10. Válassza az **Igen** lehetőséget az **Azonosítótábla felülbírálása betároláskor** mezőben. Ez a beállítás lehetővé teszi, hogy a raktárosok felülírják a cél azonosítótáblát, amikor azonosítótáblás szabályozású helyre kerülnek elemek.  
11. Válassza az **Igen** lehetőséget a **Csoportos betárolás** mezőben.
    - Ha a betárolási sorok a munkarendelésen ugyanazon a helyen találhatók, a felhasználó egy összevont Elhelyezési utasítást fog kapni az összes sorhoz. 
    - Vizsgálati sablon azonosítója: Egy munkavizsgálati sablon lehetővé teszi egy menüpont munkafolyamatának megszakítását más művelet végrehajtásához. Például ha ez a menüpont a bejövő munkához áll rendelkezésre, a vizsgálati sablon megkövetelheti, hogy a dolgozó ellenőrizze a hőmérsékletet. A vizsgálati sablonban van megadva az a pont ahol a folyamat megszakad – ez lehet például a munka kezdése vagy befejezése, illetve az állapot megváltozása.  
12. Bontsa ki a **Munkaosztályok** szakaszt.
13. Válassza az **Új** lehetőséget.
14. Írja be, hogy `Purchase` a **Munkagyűjtő-azonosító** mezőbe. A munkagyűjtő korlátozza a munkát, amelyre a menüelem használható. Ebben az esetben a Munkaosztály azonosító beszerzése ponttal rendelkező megnyitott munkarendeléssorok fogják használni.  
15. Válassza a **Mentés** lehetőséget.

## <a name="set-up-work-confirmation"></a>Munkamegerősítés beállítása
1. Válassza ki **Munka-visszaigazolás beállítása** lehetőséget.
2. A **Munkatípus** mezőben válassza a **Kitárolás** lehetőséget.
3. Válassza ki az **Automatikus megerősítés** jelölőnégyzetet. A Kitárolás munkatípusú munkautasítás automatikus megerősítésre kerül. A felhasználónak ez az utasítás nem fog megjelenni.  
4. Válassza az **Új** lehetőséget.
5. A **Munkatípus** mezőben válassza ki a „Betárolás” lehetőséget.
6. Válassza ki a **Helymegerősítés** jelölőnégyzetet. A cikk elhelyezése előtt a raktári dolgozónak meg kell erősítenie a hely átvizsgálását.  
7. Válassza a **Mentés** lehetőséget.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>A menüelem hozzáadása a mobileszköz menühöz
1. A keresősávba beírva ugorjon a **Mobileszköz** menüre.
2. Válassza ki a **Szerkesztés** opciót.
3. Rekordok kereséséhez használja a gyorsszűrőt. Például végezzen szűrést a **Név** mezőre a **bejövő** kifejezést beírva. Szeretné megtalálni bejövő menüpontokhoz használt menüt. Az USMF rendszerben ennek a mezőnek a neve: **Bejövő**.  
4. A fán válassza ki az **egy érték** lehetőséget.
5. Kattintson a jobbra mutató nyílra.
6. Válassza a **Mentés** lehetőséget.
7. Zárja be a lapot.
