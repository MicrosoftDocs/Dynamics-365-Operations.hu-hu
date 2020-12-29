---
title: Kitárolási sor csoportosítása
description: Ez a témakör a kitárolási sor csoportosításáról nyújt áttekintést.
author: Mirzaab
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: b3497d43a500898207ed5154721ee0e3a327fb93
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4429852"
---
# <a name="pick-line-grouping"></a>Kitárolási sor csoportosítása

[!include [banner](../includes/banner.md)]

A kitárolási sor csoportosításával ugyanazzal a cikkel és hellyel rendelkező több munka összevonható egyetlen kitárolássá, amelyet a felhasználó mobileszközön kap meg. A raktári dolgozók így a lehető leghatékonyabb utasításokat kapják, de továbbra is fennmarad a rendszerben a sorok szükséges elválasztása (például különböző tárolókban és rendeléseknél).

## <a name="set-up-pick-line-grouping"></a>Kitárolási sor csoportosításának beállítása

### <a name="create-a-mobile-device-menu-item"></a>Mobileszköz-menüpont létrehozása

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menüpontjai** területre, és hozzon létre egy új menüelemet **Értékesítési csoport sorkitárolása – Felhasználó által irányított** névvel.
2. A **Mobileszköz menüpontjai** alatt állítsa be a következő értékeket:

    - A **Menüelem neve** mezőbe írja be az **Értékesítési kitárolás – Sor csoportosítása** értéket.
    - A **Cím** mezőbe írja be az **Értékesítési kitárolás – Sor csoportosítása** értéket.
    - A **Mód** mezőben válassza ki a **Munka** lehetőséget.
    - A **Meglévő munka használata** lehetőséget állítsa **Igen** értékre.

3. Az **Általános** gyorslapon beállíthatja a következő értékeket:

    - Az **Irányítja** mezőben válassza a **Felhasználó által irányított** lehetőséget.
    - Állítsa az **Azonosítótábla előállítása** beállítást **Igen** értékűre.
    - Állítsa a **Kitárolás csoportosítása** beállítást **Igen** értékre.

4. A **Munkaosztályok** gyorslapon a következő lépések végrehajtásával állíthatja be a mobileszköz menüelemének érvényes munkaosztályait:

    1. Válassza az **Új** lehetőséget.
    2. A **Munkaosztály azonosítója** mezőben válassza az **Értékesítés** vagy az **SO kitárolás** lehetőséget attól függően, hogy milyen raktárt fog használni.
    3. A **Munkarendelés típusa** mezőben válassza ki az **Értékesítési rendelések** elemet.

### <a name="set-up-a-mobile-device-menu"></a>Mobileszköz-menü beállítása

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre. 
1. Adja hozzá az imént létrehozott menüelemet a kívánt menühöz.

### <a name="set-up-a-work-template"></a>Munkasablon beállítása

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.
1. Keresse meg a függvényhez használandó munkasablont. Ebben a példában válassza ki az **51 Kitárolás szakaszhoz** Contoso munkasablont.
1. A menüben válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A **Rendezés** lapon jelölje be a **Hozzáadás** lehetőséget, majd állítsa be a következő értékeket:

    - A **Táblázat** mezőben válassza az **Ideiglenes munkatranzakciók** opciót.
    - A **Származtatott tábla** mezőben válassza az **Ideiglenes munkatranzakciók** opciót.
    - A **Mező** mezőben válassza ki a **Cikkszám** lehetőséget.
    - A **Keresés iránya** mezőben válassza a **Növekvő** értéket.

> [!NOTE]
> A kitárolási sor csoportosítása funkcióhoz működéséhez a munkasorokat cikkazonosító szerint kell rendezni. Ha az azonos tételeket tartalmazó sorok nem egymás után lesznek sorba rendezve, a csoportosítás nem történik meg.

## <a name="example"></a>Példa

### <a name="create-picking-work"></a>Kitárolási munka létrehozása

A kitárolási sor csoportosításának beállítása előtt létre kell hoznia néhány alkalmas kimenő munkát.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
2. Új értékesítési rendelés létrehozásához kattintson az **Új** elemre. 
3. Válasszon ki egy tetszőleges vevőt a **Vevői számla** mezőben. 
4. Az **Általános** gyorslap **Raktár** mezőjében válassza ki a **51** értéket. Majd kattintson az **OK** lehetőségre.
5. Az **Értékesítési rendelés sorai** területen adja hozzá a következő hat sort:

    - **1. sor:** A **Cikkszám** mezőben válassza az **M9200** értéket. Írja be a **3** értéket a **Mennyiség** mezőbe.
    - **2. sor:** A **Cikkszám** mezőben válassza az **M9201** értéket. Írja be a **3** értéket a **Mennyiség** mezőbe. 
    - **3. sor:** A **Cikkszám** mezőben válassza az **M9202** értéket. Írja be a **2** értéket a **Mennyiség** mezőbe. 
    - **4. sor:** A **Cikkszám** mezőben válassza az **M9200** értéket. Írja be a **1** értéket a **Mennyiség** mezőbe. 
    - **5. sor:** A **Cikkszám** mezőben válassza az **M9200** értéket. Írja be a **3** értéket a **Mennyiség** mezőbe.
    - **6. sor:** A **Cikkszám** mezőben válassza az **M9202** értéket. Írja be a **7** értéket a **Mennyiség** mezőbe. 

    Az egyes cikkek teljes mennyiségének összegzése:

    - **M9200 cikk:** egyenként 7
    - **M9201 cikk:** egyenként 3
    - **M9202 cikk:** egyenként 9

6. Mielőtt kiadja a rendeléseket a raktárba, meg kell győződnie arról, hogy a kitárolási helyek elegendő készlettel rendelkeznek az összes rendelés minden cikkéhez. A **Helyutasítás** beállítás áttekintésével határozza meg, hogy melyik kitárolási helyeket használja az értékesítési rendelések kitároláshoz.
7. Foglalja le a készletet, és adja ki a raktárba. Létrejön egy hat sort tartalmazó munkaazonosító. A sorok cikkszám szerint vannak rendezve.

### <a name="run-the-mobile-device-flow"></a>Futtassa a mobileszközön a folyamatot

1. A mobileszközön válassza ki azt a menüt, amely az új mobileszköz-menüelemet tartalmazza.
1. Válassza az **Értékesítési kitárolás – Sor csoportosítása** menüelemet, és kezdeményezzen egy kitárolást.

    Miután kiválasztotta a menüt, és beírta a munkaazonosítót, a kitárolási lépést láthatja, amelyben a M9200 cikk összes kitárolási sora csoportosítva van. Utasítást kap, hogy tároljon ki egyenként 7 darabot az M9200 számú cikkből.

1. Erősítse meg a kitárolási lépést. 
1. Lépjen a folyamatban lévő munka ügyfélképernyőjére, és figyelje meg, hogy az M9200 számú cikk mindhárom kitárolási sora egyszerre lett lezárva.

    Megjelenik a 4. munkasor.

1. Erősítse meg a kitárolási lépést.

    A mobileszközön az utolsó kitárolási lépés a munkarendelésből származó utolsó két kitárolási sort összesíti.

1. Hajtsa végre az egyenként 9 darab M9202 számú cikkhez tartozó kitárolási lépést.
1. Erősítse meg a betárolási lépést, valamint minden további kitárolás/betárolás párt a munka befejezéséhez.

> [!NOTE]
> - A munkasorokat csak akkor lehet csoportosítani, ha azok sorrendben vannak.
> - A következő funkciók nem támogatottak:
>
>    - Tényleges súllyal rendelkező cikkek. Ha a munkán vannak tényleges súlyú cikkek, hibaüzenet jelenik meg a kitárolás megkezdése előtt.
>    - Darab kitárolása.
>    - Befejezetlen feltöltési munkával rendelkező munkasorok.
>    - Előírtnál nagyobb mennyiség kitárolása.
>    - Rövid kitárolás cikkek újbóli felosztásával
