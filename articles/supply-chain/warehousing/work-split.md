---
title: Felosztott munka
description: Ez a témakör a munkafelosztási funkcióval kapcsolatban tartalmaz információkat. Ez a funkció lehetővé teszi, hogy a nagy munkarendeléseket több kisebb munkarendelésre ossza fel, amelyeket azután több raktári dolgozóhoz rendelhet. Ily módon ugyanazt a munkát egyszerre több raktári dolgozó is kiválaszthatja.
author: mirzaab
ms.date: 10/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: WHSWorkTableListPage
ms.author: mirzaab
ms.search.validFrom: 2020-10-15
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: e3f14dd25a60f8d185f0e58a0612a322c5175ab2
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579880"
---
# <a name="work-split"></a>Felosztott munka

[!include [banner](../includes/banner.md)]

A munkafelosztás lehetővé teszi, hogy a nagy munkaazonosítókat (azaz több soros munkarendeléseket) több kisebb munkarendelésazonosítóra ossza fel, amelyeket azután több raktári dolgozóhoz rendelhet. Ily módon ugyanazt a munkátlétrehozási számot egyszerre több raktári dolgozó is kiválaszthatja.

> [!IMPORTANT]
> Csak a *Nyitott* vagy *Folyamatban lévő* állapotú munkarendeléseket oszthatja fel.

## <a name="turn-on-the-work-split-functionality"></a>A munkafelosztási funkció bekapcsolása

A munkafelosztási funkció használata előtt be kell kapcsolnia a funkciót és az annak előfeltételként szolgáló funkciót a rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkciók állapotának ellenőrzéséhez, és szükség esetén bekapcsolásukhoz.

Először kapcsolja be a *Szervezet szintű munkazárolás* előfeltétel funkciót, ha még nincs bekapcsolva. A **Funkció kezelése** munkaterületen ez a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Szervezeti szintű munkazárolás*

> [!NOTE]
> Ha ez a funkció aktiválva van, az adatfrissítés automatikusan érvénybe lép, miután a szolgáltatás be lett kapcsolva az összes jogi személynél.

Ezután kapcsolja be a *Munkafelosztás* funkciót, amely a következőképpen jelenik meg:

- **Modul:** *Raktárkezelés*
- **Szolgáltatás neve:** *Munkafelosztás*

## <a name="enhancements-to-the-work-details-and-all-work-pages"></a>A Munka részleteinek és az Összes munkaoldalnak a továbbfejlesztései

A *Munkafelosztás* funkció a következő két gombot adja hozzá a **Munka részletei** és az **Összes munka** oldalak munkatábla **Munka** füléhez:

- **Munkafelosztás** – Ossza fel a munkaazonosítót több kisebb munkaazonosítóra, amelyet különböző dolgozók feldolgozhatnak.
- **Munkafelosztási munkamenet megszakítása** – A munkafelosztási munkamenet megszakítása és a munka feldolgozásra való elérhetővé tétele.

![Munkafelosztás és Munkafelosztási munkamenet megszakítási gombok.](media/Work_split_buttons.png "Munkafelosztás és Munkafelosztási munkamenet megszakítási gombok")

> [!IMPORTANT]
> A **Munkafelosztás** gomb nem érhető el, ha az alábbi feltételek bármelyike teljesül:
>
> - A munka állapota nem *Nyitott* vagy *Folyamatban lévő*.
> - A munkaazonosítóhoz tárolóazonosító van társítva. (A tároló nem osztható fel szisztematikusan, mert fizikai műveleteket igényel.)
> - A munka fürthöz van társítva.
> - A munkarendelés típusa eltér az alábbi típusoktól:
>
>    - Értékesítési rendelés
>    - Nyersanyag kitárolása
>    - Átmozgatási probléma
>
> - A munkát jelenleg egy másik felhasználó osztja fel. Ha megpróbálja megnyitni a felosztási lapot egy másik felhasználó által már felosztott munkához, a következő hibaüzenet jelenik meg: „A(z) \#\#\#\# azonosítójú munkát jelenleg felosztják. Próbálja meg újra néhány perc múlva. Ha továbbra is ezt az üzenetet kapja, forduljon a feletteséhez.”

Egy új munkazárolási ok, a *Munkafelosztás* azt jelzi, hogy a munkaazonosító éppen felosztási folyamatban van. A **Munkafelosztás** lapon és a Raktárkezelés mobilalkalmazásban is megjelenik, ha a felhasználó megpróbálja futtatni a munkát. Zárolási okok esetén a Munkaazonosítóban lévő **Zárolt hullám** mező neve a **Zárolt** értékre változik.

## <a name="initiate-a-work-split"></a>Munkafelosztás kezdeményezése

A funkció hozzáad egy új **Munkafelosztás** oldalt, amely lehetővé teszi a felhasználók számára, hogy felosszák a munkasorokat a munkaazonosítóból. Az oldal első megnyitásakor olyan sorok jelennek meg, amelyek munkaállapota *Nyitott* és amelyek feloszthatók. A Művelet panelen válassza a **Munkafelosztás** lehetőséget a kijelölt munka feldolgozásához.

A munka felosztásához kövesse az alábbi lépéseket.

1. Nyissa meg az alábbiak közül valamelyik lapot:

    - **Munka részletei** (**Raktárkezelés \> Munka \> Munka részletei**)
    - **Összes munka** (**Raktárkezelés \> Munka \> Összes munka**)

1. A rácsban válassza ki a felosztandó munkaazonosítót. A **Munkarendelés típusa** mezőt a következő értékek egyikére kell beállítani:

    - Értékesítési rendelés
    - Nyersanyag kitárolása
    - Átmozgatási probléma

1. A Művelet ablaktábla **Munka** lapjának **Munka** csoportjában válassza a **Munkafelosztás** elemet.

    Megjelenik a **Munkafelosztás** lap, amely a megnyitott és felosztható munkasorokat tartalmaz. Alapértelmezés szerint csak az elérhető munkasorok jelennek meg. A munkaazonosító összes sorának megtekintéséhez (például olyan sorok, amelyek *Eltárolás* munkatípusúak), jelölje be az **Összes sor megjelenítése** jelölőnégyzetet a rács felett.

    A következő üzenet jelenik meg: „A felhasználók nem tudják feldolgozni a munka sorait, amíg be nem fejezi a felosztást és be nem zárja ezt az oldalt.”

    Az aktuális munka **Munkazárolási ok** mezője a *Munkafelosztás* értékre lesz állítva, és a munka zárolva lesz.

    ![Zárolás oka.](media/Blocking_reason.png "Zárolás oka")

1. Jelölje ki azokat a sorokat, amelyeket el szeretne távolítani az aktuális munkaazonosítóból, és hozzá szeretné adni egy új munkaazonosítóhoz. A következő események zajlanak le:

    - A munka felosztásakor a kijelölt sor vagy sorok az eredeti munkaazonosítóból megszakadnak, majd átmásolódnak egy új munkaazonosítóba.
    - A meglévő munkasablon-szerkezete és az eltárolási helye (és a jövőbeli kitárolási/betárolási párok) megmarad. A következő munkaazonosító-mezők értékeit a program az eredeti munkából az új munkába másolja:

        - Rakományazonosító
        - Szállítmány azonosítója
        - Munkarendelés típusa
        - Rendelésszám
        - Hely
        - Raktár
        - Munka prioritása
        - Munkagyűjtő azonosítója
        - Hullámazonosító
        - Munka létrehozási száma

    - A következő mezők nem lesznek átmásolva az új munkaazonosítóba:

        - **Munkaazonosító** – A megfelelő számsorozatból új munkaazonosító jön létre.
        - **Munka állapota** – Ez a mező *Nyitott* értékre van állítva.
        - **Zárolta:** – Ez a mező kezdetben üresre van állítva.
        - **Cél azonosítótábla-azonosító** – Ez a mező üresen marad.
        - **Létrehozott dátum és idő** – Ez a mező az aktuális dátumra és időre van beállítva.
        - **Zárolt hullám/befagyasztva** – Ez a mező újra kiszámításra kerül az eredeti és az új munkaazonosítóhoz.

1. A Műveleti ablaktáblán kattintson a **Munkafelosztás** elemre.

A munka felosztása közben a következő üzenet jelenik meg: „Feldolgozási művelet – Munka felosztása”. Amíg ez az üzenet látható, a műveletet az üzenetmezőben a **Mégse** lehetőség kiválasztásával szakíthatja meg.

Ha az **Összes sor megjelenítése** jelölőnégyzet nincs bejelölve, a felosztott és megszakított sor a továbbiakban nem jelenik meg a rácsban. Ha a jelölőnégyzet be van jelölve, látnia kell, hogy a sor **Munkaállapot** mezője *Érvénytelenítve* értékre változott.

A következő értesítés jelzi, hogy az új munkaazonosító létrejött: „A(z) \#\#\#\# munka az eredeti \#\#\#\# munkától való leválasztással jött létre."

Az eredeti munkaazonosító egyéb munkasorai (például *Kitárolás* sorok) szükség szerint módosulnak, hogy tükrözzék az érvénytelenített munkasorokat. Ha például az eredeti munkaazonosító *Eltárolás* 15-ös mennyiségre vonatkozó *Kitárolás* sorral rendelkezett, és a 10 teljes mennyiséggel rendelkező érvénytelenített sorokat visszavonták, akkor az eredeti munkaazonosító új *Eltárolás* mennyisége mostantól 5 lesz.

Az új munka nem lesz azonnal hozzárendelve egyetlen felhasználóhoz sem. A **Munka részletei** lap standard funkciójával azonban most már hozzárendelheti egy felhasználóhoz.

> [!IMPORTANT]
> Csak két vagy több elérhető munkasort tartalmazó munkaazonosítókat oszthat fel. Ha a **Munkafelosztás** lehetőséget választja, amikor csak egy munkasor van, a következő hibaüzenet jelenik meg: „Legalább egy munkasornak a kezdeti munkában kell maradnia.” Ebben az esetben nem történik felosztás.

## <a name="finish-a-work-split"></a>Munkafelosztás befejezése

A *Munkafelosztás* befejezéséhez el kell távolítani a felosztási munka zárolási okát. Ezt a lépést kétféleképpen lehet befejezeni:

- Az a felhasználó, aki felosztja a munkát, a jobb felső sarokban lévő **Bezárás** gombbal (**X**) zárja be a **Munkafelosztás** oldalt. Amikor az oldal be van zárva, a *Munkafelosztás* zárolási ok törlődik. A munka *Zárolt* állapota a újra lesz számítva, és ha nincs több zárolási oka ennek a munkának, akkor a munka fel lesz oldva.
- Bármely felhasználó megnyithatja a munkaazonosítót, és kiválaszthatja a **Munkafelosztási munkamenet megszakítása** gombot a Művelet panelen. A *Munkafelosztás* zárolásának oka eltávolításra kerül, és a munka *Zárolt* állapota újraszámításra kerül, ugyanúgy, mint amikor a **Munkafelosztás** oldal bezárul.

A *Munkafelosztás* zárolási okának eltávolítása után a munka futtatható a mobileszközön, feltéve, hogy a **Zárolt** állapot *Nem* értékre van állítva a munkaazonosítón.

## <a name="user-blocking-on-the-warehouse-management-mobile-app"></a>Felhasználó letiltása a Raktárkezelés mobilalkalmazásban

Ha megpróbálja használni a Raktárkezelés mobilalkalmazást a kitárolási munka felosztott munkával való összevetéséhez, a következő hibaüzenet jelenik meg: „A(z) \#\#\#\# azonosítójú munkát jelenleg felosztják.” Ha ez az üzenet jelenik meg, válassza a **Mégse** gombot. Ezután folytathatja más munka feldolgozását.

## <a name="other-blocked-operations"></a>Egyéb zárolt műveletek

A munkasorokat, a munkakészlet-tranzakciókat vagy a felosztott munkához kapcsolódó feltöltési hivatkozásokat módosító műveletek sikertelenek lesznek, és a következő hibaüzenet jelenik meg: „A(z) \#\#\#\# azonosítóval végzett munka jelenleg felosztás alatt áll."


[!INCLUDE[footer-include](../../includes/footer-banner.md)]