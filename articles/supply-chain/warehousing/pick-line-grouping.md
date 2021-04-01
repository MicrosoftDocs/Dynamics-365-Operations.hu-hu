---
title: Kitárolási sor csoportosítása
description: Ez a témakör a kitárolási sor csoportosításáról nyújt áttekintést.
author: Mirzaab
manager: tfehr
ms.date: 12/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 7ab8cdd7cad5420aca0de53e59220da9e230d411
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234633"
---
# <a name="pick-line-grouping"></a>Kitárolási sor csoportosítása

[!include [banner](../includes/banner.md)]

A kitárolási sor csoportosításával ugyanazzal a cikkel és hellyel rendelkező több munka összevonható egyetlen kitárolássá, amelyet a felhasználó mobileszközön kap meg. A raktári dolgozók így a lehető leghatékonyabb utasításokat kapják, de továbbra is fenntartható a rendszerben (például különböző tárolókban és rendeléseknél) a sorok szükséges elválasztása.

## <a name="turn-on-the-pick-line-grouping-feature"></a>A kitárolási sor csoportosítása funkció bekapcsolása

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [Funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterület a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Kitárolási sor csoportosítása*

## <a name="set-up-pick-line-grouping"></a>Kitárolási sor csoportosításának beállítása

### <a name="create-a-mobile-device-menu-item"></a>Mobileszköz-menüpont létrehozása

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Menüelem neve** mezőbe írja be az *Értékesítési csoport sorának kitárolása* értéket.
1. A **Cím** mezőbe írja be az *Értékesítési csoport sorának kitárolása* értéket. Ez a cím jelenik meg a mobileszköz menüjén.
1. A **Mód** mezőben válassza ki a *Munka* lehetőséget.
1. A **Meglévő munka használata** lehetőséget állítsa *Igen* értékre.
1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - Az **Irányítja** mezőben válassza a *Felhasználó által irányított* lehetőséget.
    - Állítsa az **Azonosítótábla előállítása** beállítást *Igen* értékűre.
    - Állítsa a **Kitárolás csoportosítása** beállítást *Igen* értékre.
    - A fennmaradó opcióknál hagyja meg az alapértelmezett értékeket.

1. A következő lépések végrehajtásával állíthatja be a mobileszköz menüelemének érvényes munkaosztályait:

    1. A **Munkaosztályok** gyorslapon válassza az **Új** elemet.
    2. A **Munkaosztály azonosítója** mezőben kiválaszthatja az *Értékesítés* vagy az *SO kitárolás* lehetőséget attól függően, hogy milyen raktárt fog használni. Erre az esetre válassza az *SO kitárolás* lehetőséget.

        A **Munkarendelés típusa** mező automatikusan a *Beszerzési rendelések* értékre áll.

### <a name="set-up-a-mobile-device-menu"></a>Mobileszköz-menü beállítása

A következő lépések szerint hozzáadhatja az előbb létrehozott menüelemet a **Kimenő** menühöz.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A listaablak az összes meglévő mobileszköz-menüt mutatja. Jelölje ki a *Kimenő* elemet a listán.
1. A **Rendelkezésre álló menük és menüelemek** listában keresse meg és válassza ki a létrehozott *Értékesítési csoport sorának kitárolása* menüelemet.
1. Válassza a jobbra mutató nyílgombot a *Értékesítési csoport sorának kitárolása* menüelem **Menüstruktúra** listában való elhelyezéséhez.
1. A felfelé és lefelé mutató nyíllal a menüben mozgathatja a menüelemet a kívánt struktúrában.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

### <a name="set-up-a-work-template"></a>Munkasablon beállítása

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.
1. A **Munkarendelés típusa** mezőben válassza ki az *Értékesítési rendelések* elemet.
1. Az  **Áttekintés** rácsban keresse meg és válassza ki az ezzel a funkcióval használni kívánt munkasablont. Ehhez a helyzethez válassza az *51 Kitárolás szakaszhoz* sablont.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezés szerkesztőpanel **Rendezés** lapján válassza a **Hozzáadás** parancsot az új sorhoz, majd állítsa be a következő értékeket:

    - A **Táblázat** oszlopban válassza az *Ideiglenes munkatranzakciók* opciót.
    - A **Származtatott tábla** oszlopban válassza az *Ideiglenes munkatranzakciók* opciót.
    - A **Mező** oszlopban válassza ki a *Cikkszám* lehetőséget.
    - A **Keresés iránya** oszlopban válassza a *Növekvő* értéket.

1. Az **OK** gombra kattintva zárja be a párbeszédpanelt, és mentse a beállításokat.
1. A következő üzenet jelenik meg: „A csoportosítás alaphelyzetbe kerül, folytatja?” A folytatáshoz kattintson az **Igen** gombra.

> [!IMPORTANT]
> A kitárolási sor csoportosítása funkcióhoz működéséhez a munkasorokat cikkazonosító szerint kell rendezni. Ha az azonos tételeket tartalmazó sorok nem egymás után lesznek sorba rendezve, a csoportosítás nem történik meg.

## <a name="example"></a>Példa

### <a name="create-picking-work"></a>Kitárolási munka létrehozása

A kitárolási sor csoportosításának beállítása előtt létre kell hoznia néhány alkalmas kimenő munkát.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Új értékesítési rendelés létrehozásához kattintson az **Új** elemre.
1. A **Vevői számla** mezőben válassza a következőt: *US-004*.
1. Az **Általános** gyorslap **Raktár** mezőjében válassza ki a *51* értéket.
1. Válassza ki az **OK** lehetőséget.
1. Az **Értékesítési rendelés sorai** gyorslapon adja hozzá a következő hat sort:

    - **1. sor:** A **Cikkszám** mezőben válassza az *M9200* értéket. Írja be a *3* értéket a **Mennyiség** mezőbe.
    - **2. sor:** A **Cikkszám** mezőben válassza az *M9201* értéket. Írja be a *3* értéket a **Mennyiség** mezőbe.
    - **3. sor:** A **Cikkszám** mezőben válassza az *M9202* értéket. Írja be a *2* értéket a **Mennyiség** mezőbe.
    - **4. sor:** A **Cikkszám** mezőben válassza az *M9200* értéket. Írja be a *1* értéket a **Mennyiség** mezőbe.
    - **5. sor:** A **Cikkszám** mezőben válassza az *M9200* értéket. Írja be a *3* értéket a **Mennyiség** mezőbe.
    - **6. sor:** A **Cikkszám** mezőben válassza az *M9202* értéket. Írja be a *7* értéket a **Mennyiség** mezőbe.

    Az egyes cikkek teljes mennyiségének összegzése:

    - **M9200 cikk:** *7* egyenként
    - **M9201 cikk:** *3* egyenként
    - **M9202 cikk:** *9* egyenként

1. Mielőtt kiadja a rendeléseket a raktárba, meg kell győződnie arról, hogy a kitárolási helyek elegendő készlettel rendelkeznek az összes rendelés minden cikkéhez. A **Helyutasítás** beállítás áttekintésével határozza meg, hogy melyik kitárolási helyeket használja az értékesítési rendelések kitároláshoz. Ha a Contoso bemutató adatkörnyezetét használja az *51-es* raktárhoz, erősítse meg, hogy van-e elérhető készlet.

    A készletet minden sorhoz le kell foglalnia.

1. Válassza ki a lefoglalni kívánt sorok egyikét az **Értékesítési rendelési sorok** gyorslapon.
1. A rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.
1. A **Foglalás** oldalon, a műveleti panelen válassza az **Adag foglalása** elemet a foglalás alkalmazásához. Ezután zárja be az oldalt.
1. Ismételje meg a 8–10. lépést a fennmaradó foglalandó sorokkal.

    Most ki kell adnia az értékesítési rendelést a raktárnak.

1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.

    Egy üzenet jelenik meg, amely szerint létrejött egy szállítmány és egy hullám, és a hullám egy kötegben való futtatásra lett elküldve.

    Ha a hullám és az összes lefelé irányuló feladat befejeződött, egy munkaazonosító jön létre a hat sorból álló munkához. A sorok cikkszám szerint vannak rendezve.

1. Ugorjon a **Raktárkezelés \> Munka \> Minden munka** elemre a létrehozott munka megtekintéséhez. Jegyezze fel a **Munkaazonosító** értékét, mert a következő eljárásban is szüksége lesz rá.

### <a name="initiate-picking-from-the-mobile-device"></a>Kitárolás kezdeményezése mobileszközről

1. Jelentkezzen be a mobileszközbe olyan felhasználóként, aki a *51*. raktárban be van állítva.
1. A mobileszközön válassza ki azt a menüt, amely az új mobileszköz-menüelemet tartalmazza. Erre az esetre válassza a **Kimenő** lehetőséget.
1. Válassza az **Értékesítési csoport sorának kitárolása** menüelemet a kitárolás kezdeményezéséhez.
1. Adja meg annak a **Munkaazonosítónak** az értékét, amelyről megjegyzést tett az előző eljárás során.

    Olyan kitárolási lépést kell látnia, ahol az *M9200* cikk minden kiválasztósora csoportosítva van, és utasítást kell kapnia arra, hogy az *M9200* cikkből egyenként *7-et* kell kitárolnia.

    > [!IMPORTANT]
    > A mobileszközön a három kitárolási munkasor kitárolási munkája egyetlen kitárolási lépésben lett összesítve a felhasználó számára.

1. Erősítse meg a kitárolási lépést.
1. Lépjen a folyamatban lévő munka oldalára a munkaazonosítóért, és figyelje meg, hogy az *M9200* számú cikk mindhárom kitárolási sora egyszerre lett lezárva.
1. Menjen vissza a mobileszközhöz, és folytassa a kitárolással. Az *M9201 cikk* 4. munkasorának kell megjelennie. Mivel a rendelésen csak egy munkasor volt, nincs mit összesíteni.
1. Erősítse meg a kitárolási lépést.
1. A mobileszközön az utolsó kitárolási lépés a munkarendelésből származó utolsó két kitárolási sort összesíti.
1. Hajtsa végre az egyenként *9* darab *M9202* számú cikkhez tartozó kitárolási lépést.
1. Erősítse meg a betárolási lépést, valamint minden további kitárolás/betárolás párt a munka befejezéséhez.

> [!IMPORTANT]
>
> - A munkasorokat csak akkor lehet csoportosítani, ha azok sorrendben vannak.
> - A következő funkciók nem támogatottak:
>
>   - Tényleges súllyal rendelkező cikkek
>
>    Ha a munkán vannak tényleges súlyú cikkek, hibaüzenet jelenik meg a kitárolás megkezdése előtt.
>
>   - Darab kitárolása
>   - Befejezetlen feltöltési munkával rendelkező munkasorok
>   - Előírtnál nagyobb mennyiség kitárolása
>   - Rövid kitárolás cikkek újbóli felosztásával


[!INCLUDE[footer-include](../../includes/footer-banner.md)]