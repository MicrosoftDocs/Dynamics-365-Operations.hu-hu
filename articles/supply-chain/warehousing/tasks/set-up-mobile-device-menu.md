--- 
title: "Mobileszköz-menüelem beállítása a beszerzési rendelés munkájának befejezéséhez"
description: "Ez az eljárás bemutatja, hogy hogyan kerül sor a mobileszköz menüelemeinek beállítására."
author: ShylaThompson
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b80c258d6a779a8fc5bb6c846abd3af7e69d5e06
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-mobile-device-menu-item-for-completing-work-in-a-purchase-order"></a>Mobileszköz-menüelem beállítása a beszerzési rendelés munkájának befejezéséhez

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogy hogyan kerül sor a mobileszköz menüelemeinek beállítására. Ebben a példában, ez a menüpont a Beszerzési rendelés típusú munkák végrehajtásához használatos. A menüponthoz társított munkaosztály határozza meg, hogy melyik munka érvényes. Ezt az útmutatót használhatja az USMF bemutatócégen. Ezt az eljárást általában a raktárvezető követi nyomon.


## <a name="create-a-mobile-device-menu-item"></a>Mobileszköz-menüpont létrehozása
1. Ugrás a Mobileszköz menüpontokhoz.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Menüelem neve mezőbe.
    * Egyedi érték megadása. Ha például beírhatja a „Beszerzési rendelés áthelyezés” kifejezést. Jegyezze meg az értéket, később szüksége lesz rá.  
4. Érték beírása a Címmezőbe.
    * Ez az a cím, amely a felhasználók mobileszközein a jelenik meg. Ha például beírhatja a „Beszerzési rendelés áthelyezés” kifejezést.  
5. A Mód mezőben válassza ki a „Munka” lehetőséget.
6. A Meglévő munka használata mezőben válassza az Igen lehetőséget.
    * A mobileszköz-menüpont meglévő munkához használatos. Ezért ennek az értéknek Igennek kell lennie.  
    * A Készletállapot megjelenítése mező meghatározza, hogy az aktuális készlet készletállapota megjelenjen raktári dolgozó mobileszközén.  
7. Az Irányítja mezőben válassza a „Rendszercsoportosítás” lehetőséget.
    * Ha valamit kijelöl az Irányítja mezőben, további mezők jelennek meg ezen a lapon az Általános szakaszban. A megjelenő mezők attól függenek, hogy Ön mit jelölt ki. A Rendszercsoportosítás kijelölésekor 2 új mező kerül hozzáadásra. Ezek magyarázata alább látható.  
8. Írja be a Rendszer-csoportosítás mezőbe a „WorkPoolId” szöveget.
    * Amikor a raktári dolgozók megnyitják a menüpontot, a munkagyűjtő azonosító ellenőrzése szükséges lesz. Minden, ehhez a menüponthoz rendelt munkarendelés ezzel a Munkagyűjtő azonosítóval és minden Megnyitott munkarendeléssor munkaosztálya a felhasználóhoz kerül.  
9. Írjon be egy értéket a Rendszer-csoportosítási címke mezőbe.
    * Ez a szöveg jelenik meg a mobileszköz-felhasználó számára. Például beírhatja a „Munkagyűjtő” kifejezést.  
10. Válassza az Igen lehetőséget az Azonosítótábla felülbírálása betároláskor mezőben.
    * Ez a beállítás lehetővé teszi, hogy a raktárosok felülírják a cél azonosítótáblát, amikor azonosítótáblás szabályozású helyre kerülnek elemek.  
11. Válassza az Igen lehetőséget a Csoportos betárolás mezőben.
    * Ha a betárolási sorok a munkarendelésen ugyanazon a helyen találhatók, a felhasználó egy összevont Elhelyezési utasítást fog kapni az összes sorhoz.  
    * Vizsgálati sablon azonosítója: Egy munkavizsgálati sablon lehetővé teszi egy menüpont munkafolyamatának megszakítását más művelet végrehajtásához. Például ha ez a menüpont a bejövő munkához áll rendelkezésre, a vizsgálati sablon megkövetelheti, hogy a dolgozó ellenőrizze a hőmérsékletet. A vizsgálati sablonban van megadva az a pont ahol a folyamat megszakad – ez lehet például a munka kezdése vagy befejezése, illetve az állapot megváltozása.  
12. Bontsa ki a Munkaosztályok szakaszt.
13. Kattintson az Új lehetőségre.
14. Írja be a Munkaosztály azonosítója mezőbe a „Beszerzés” szöveget.
    * A munkagyűjtő korlátozza a munkát, amelyre a menüelem használható. Ebben az esetben a Munkaosztály azonosító beszerzése ponttal rendelkező megnyitott munkarendeléssorok fogják használni.  
15. Kattintson a Mentés gombra.

## <a name="set-up-work-confirmation"></a>Munkamegerősítés beállítása
1. Kattintson a Munka-visszaigazolás beállítására.
2. A Munkatípus mezőben válassza a „Kitárolás” lehetőséget.
3. Válassza ki az Automatikus megerősítés jelölőnégyzetet.
    * A Kitárolás munkatípusú munkautasítás automatikus megerősítésre kerül. A felhasználónak ez az utasítás nem fog megjelenni.  
4. Kattintson az Új lehetőségre.
5. A Munkatípus mezőben válassza a „Betárolás” lehetőséget.
6. Válassza ki a Helymegerősítés jelölőnégyzetet.
    * A cikk elhelyezése előtt a raktári dolgozónak meg kell erősítenie a hely átvizsgálását.  
7. Kattintson a Mentés gombra.
8. Zárja be a lapot.
9. Zárja be a lapot.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>A menüelem hozzáadása a mobileszköz menühöz
1. Ugrás a Mobileszköz menübe.
2. Kattintson a Szerkesztés lehetőségre.
3. Rekordok kereséséhez használja a gyorsszűrőt. Például szűkítsen a „Név” mezővel a „bejövő” szót beírva.
    * Szeretné megtalálni bejövő menüpontokhoz használt menüt. Az USMF rendszerben ennek a mezőnek a neve: Bejövő.  
4. A fában válassza ki az „egy érték” lehetőséget.
5. Kattintson a jobbra mutató nyílra.
6. Kattintson a Mentés gombra.
7. Zárja be a lapot.


