---
title: Manuális döntések konfigurálása munkafolyamatban
description: Ez a témakör bemutatja, hogy hogyan kell konfigurálni a manuális döntés tulajdonságait.
author: ChrisGarty
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1c9cecabb7923e86e8aa09eed7bd3b1ba5ee0bd8
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694861"
---
# <a name="configure-manual-decisions-in-a-workflow"></a>Manuális döntések konfigurálása munkafolyamatban

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogy hogyan kell konfigurálni a manuális döntés tulajdonságait.

A munkafolyamat-szerkesztő manuális döntésének konfigurálásához, kattintson a jobb gombbal a manuális döntésre, és kattintson **Tulajdonságok** oldal megnyitásához a **Tulajdonságok** lehetőségre. Ezt követően a következő eljárások segítségével állítsa be a manuális döntés tulajdonságait.

## <a name="name-the-decision"></a>A döntés elnevezése

A következő lépések segítségével elnevezheti a manuális döntést.

1. A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2. Adja meg a manuális döntés egyedi nevét az **Név** mezőben.

## <a name="enter-a-subject-line-and-instructions"></a>A tárgysor és az utasítások megadása

Meg kell adnia egy tárgysort, illetve utasításokat a manuális döntéshez hozzárendelt felhasználók számára. Például, ha a beszerzési igénylések döntését konfigurálja, a döntéshez hozzárendelt felhasználó látja a tárgysort és az utasításokat a **Beszerzési igénylések** oldalon. A tárgysor az oldal egy üzenetsorán jelenik meg. A felhasználó ezt követően rákattinthat az üzenetsoron található ikonra az útmutatás megtekintéséhez. Kövesse a következő lépéseket a tárgysor és az utasítások megadásához.

1. A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2. Írja be a tárgysort a **Munkatétel tárgya** oldalon található **Munkatétel tárgya** mezőbe.
3. A tárgysor személyre szabásához helyőrzőket illeszthet be. A helyőrzők helyére a megfelelő adatok kerülnek, amikor a tárgysor megjelenik a felhasználók számára. Végezze el a következő lépéseket a helyőrzők beillesztéséhez:

    1. Kattintson oda a szövegdobozban, ahol meg szeretné jeleníteni a helyőrzőt.
    2. Kattintson a **Helyőrző beszúrása** lehetőségre.
    3. A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.
    4. Kattintson a **Beszúrás** lehetőségre.

4. A tárgysor fordításai hozzáadásához, végezze el a következő lépéseket:

    1. Kattintson a **Fordítások** lehetőségre.
    2. A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.
    3. A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.
    4. Írja be a szöveget a **Lefordított szöveg** mezőbe.
    5. A szöveg személyre szabásához, helyőrzőket illeszthet be a 3. lépésben leírtak szerint.
    6. Kattintson a **Bezárás** gombra.

5. Írja be az utasításokat a **Munkatétel utasításai** mezőbe.
6. Az utasítások testreszabásához, helyőrzőket illeszthet be. A helyőrzők helyére a megfelelő adatok kerülnek, amikor az utasítások megjelennek a felhasználók számára. Végezze el a következő lépéseket a helyőrzők beillesztéséhez:

    1. Kattintson oda a szövegdobozban, ahol meg szeretné jeleníteni a helyőrzőt.
    2. Kattintson a **Helyőrző beszúrása** lehetőségre.
    3. A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.
    4. Kattintson a **Beszúrás** lehetőségre.

7. Az utasítások fordításainak hozzáadásához, végezze el a következő lépéseket:

    1. Kattintson a **Fordítások** lehetőségre.
    2. A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.
    3. A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.
    4. Írja be a szöveget a **Lefordított szöveg** mezőbe.
    5. A szöveg személyre szabásához, helyőrzőket illeszthet be a 6. lépésben leírtak szerint.
    6. Kattintson a **Bezárás** gombra.

## <a name="specify-the-possible-outcomes-of-a-decision"></a>A döntés lehetséges kimeneteinek meghatározása

Általában, amikor a rendszer hozzárendeli a dokumentumot a döntéshozóhoz, a döntéshozónak meg kell válaszolnia egy kérdést. A válasz a kérdésre általában **Igen** vagy **Nem**, vagy **Igaz** vagy **Hamis**. Végezze el a következő lépéseket a manuális döntés lehetséges kimeneteinek meghatározásához.

1. A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2. Írja be az eredmény vagy a beállítás nevét az **Eredmények** oldalon található **1. Eredmény** mezőbe.
3. Az eredmény fordításainak hozzáadásához, végezze el a következő lépéseket:

    1. Kattintson a **Fordítások** lehetőségre.
    2. A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.
    3. A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.
    4. Írja be a szöveget a **Lefordított szöveg** mezőbe.
    5. Kattintson a **Bezárás** gombra.

4. Írja be az eredmény vagy a beállítás nevét az **2. Eredmény** mezőbe.
5. Az eredmény fordításainak hozzáadásához, végezze el a következő lépéseket:

    1. Kattintson a **Fordítások** lehetőségre.
    2. A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.
    3. A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.
    4. Írja be a szöveget a **Lefordított szöveg** mezőbe.
    5. Kattintson a **Bezárás** gombra.

## <a name="specify-when-notifications-are-sent"></a>Az értesítések küldési idejének meghatározása

Értesítéseket küldhet a felhasználók számára, amikor a döntés meghozatalakor, delegálásakor, vagy eszkalálásakor. Végezze el a következő lépéseket, annak meghatározása érdekében, hogy mikor és kinek küldje el a rendszer az értesítéseket.

1. A bal oldali panelen kattintson az **Értesítések** gombra.
2. Jelölje be a jelölőnégyzetet azon eseményekhez, amelyekhez ki kell küldeni az értesítéseket:

    - **\[Választható 1\]** – A hozzárendelt felhasználó a **\[Választható 1\]** lehetőséget választotta.
    - **\[Választható 2\]** – A hozzárendelt felhasználó a **\[Választható 2\]** lehetőséget választotta.
    - **Delegált** – A hozzárendelt felhasználó hozzárendelte a döntést egy másik felhasználóhoz.
    - **Eszkaláció** – A hozzárendelt felhasználó nem végezte el a döntést a kijelölt időn belül.

3. Jelölje ki a sort a 2. lépésben választott eseményhez.
4. Írja be az értesítés szövegét az **Értesítési szöveg** lapon lévő szövegdobozba.
5. Az értesítések személyre szabásához, helyőrzőket szúrhat be. A helyőrzők helyére a megfelelő adatok kerülnek, amikor az értesítés megjelenik a felhasználók számára. Végezze el a következő lépéseket a helyőrzők beillesztéséhez:

    1. Kattintson oda a szövegdobozban, ahol meg szeretné jeleníteni a helyőrzőt.
    2. Kattintson a **Helyőrző beszúrása** lehetőségre.
    3. A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.
    4. Kattintson a **Beszúrás** lehetőségre.

6. Az értesítések fordításainak hozzáadásához, végezze el a következő lépéseket:

    1. Kattintson a **Fordítások** lehetőségre.
    2. A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.
    3. A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.
    4. Írja be a szöveget a **Lefordított szöveg** mezőbe.
    5. A szöveg személyre szabásához, helyőrzőket illeszthet be a 5. lépésben leírtak szerint.
    6. Kattintson a **Bezárás** gombra.

7. Adja meg azokat a személyeket, akik értesítéseket kapnak a **Címzett** lapon. Válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 8. lépésre.

    <table>
    <thead>
    <tr>
    <th>Lehetőség</th>
    <th>Értesítés címzettjei</th>
    <th>További lépések</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Résztvevő</td>
    <td>Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</td>
    <td>
    <ol>
    <li>Miután kiválasztotta <strong>Résztvevő</strong> lehetőséget a <strong>Szerepkör-alapú</strong> lapon, a <strong>Résztvevő típusa</strong> listán jelölje ki azon csoport vagy a szerepkör típusát, amely számára az értesítéseket el kívánja küldeni.</li>
    <li>A <strong>Résztvevő</strong> listán jelölje ki a csoportot vagy szerepkört, amely számára értesítést kíván küldeni.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Munkafolyamat felhasználója</td>
    <td>Az aktuális munkafolyamatban szereplő felhasználó</td>
    <td>
    <ul>
    <li>Miután kijelölte <strong>Munkafolyamat-felhasználó</strong> lehetőséget a <strong>Munkafolyamat-felhasználó</strong> lapon a <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki egy felhasználót, aki részt vesz a munkafolyamatban.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Felhasználó</td>
    <td>Meghatározott felhasználók</td>
    <td>
    <ol>
    <li>Miután kijelölte <strong>Felhasználó</strong> lehetőséget, kattintson a <strong>Felhasználó</strong> fülre.</li>
    <li>A <strong>Rendelkezésre álló felhasználók</strong> listája az összes felhasználót tartalmazza. Válassza ki azokat a felhasználókat, akik számára értesítéseket kíván küldeni, majd helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. Ismételje meg a 3 – 7. lépést a 2. lépésben kiválasztott összes eseményhez.

## <a name="assign-a-decision"></a>Döntés hozzárendelése

Végezze el ezeket a lépéseket azon személyek meghatározásához, akiket a manuális döntéshez hozzá kell rendelni.

1. A bal oldali panelen kattintson a **Hozzárendelés** gombra.
2. A **Hozzárendelés-típus** lapon válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 3. lépésre.

    <table>
    <thead>
    <tr>
    <th>Lehetőség</th>
    <th>A döntéshez hozzárendelt felhasználók</th>
    <th>További lépések</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Résztvevő</td>
    <td>Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</td>
    <td>
    <ol>
    <li>Miután kiválasztotta <strong>Résztvevő</strong> lehetőséget a <strong>Szerepkör-alapú</strong> lapon, a <strong>Résztvevő típusa</strong> listán jelölje ki a döntéshez hozzárendelni kívánt csoport vagy a szerepkör típusát.</li>
    <li>A <strong>Résztvevő</strong> listán jelölje ki a döntéshez hozzárendelni kívánt csoportot vagy szerepkört.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Hierarchia</td>
    <td>A meghatározott szervezeti hierarchiában lévő felhasználók.</td>
    <td>
    <ol>
    <li>Miután kiválasztotta <strong>Hierarchia</strong> lehetőséget a <strong>Hierarchia kiválasztása</strong> lapon, a <strong>Hierarchia típusa</strong> listán, jelölje ki a döntéshez hozzárendelni kívánt hierarchia típusát.</li>
    <li>A rendszernek be kell olvasnia az felhasználó névtartományát a hierarchiából. Ezek a nevek a döntéshez hozzárendelhető felhasználókat jelölik. Végezze el a következő lépéseket azon felhasználók névtartományának kezdő- és végpontját, amelyet a rendszer beolvas: <ol>
    <li>A kezdő pont megadásához válasszon ki egy személyt a <strong>Kezdet</strong> listából.</li>
    <li>A végpont megadásához kattintson a <strong>Feltétel létrehozása</strong> lehetőségre. Ezt követően adja meg azt a feltételt, amely meghatározza, hogy a rendszer hol állítsa meg a hierarchiában a nevek beolvasását.</li>
    </ol>
    </li>
    <li>A <strong>Hierarchia beállításai</strong> lapon adja meg, hogy mely, a tartományban szereplő felhasználók számára kell a döntést hozzárendelni: <ul>
    <li><strong>Minden lekért felhasználó hozzárendelése</strong> – A tartományban szereplő összes felhasználóhoz hozzá van rendelve a döntés.</li>
    <li><strong>Csak a legutóbb lekért felhasználó hozzárendelése</strong> – Csak a tartományban szereplő utolsó felhasználóhoz van hozzárendelve a döntés.</li>
    <li><strong>A következő feltételnek megfelelő felhasználók kihagyása</strong> – A döntés nincs hozzárendelve a tartomány minden olyan felhasználójához, akik megfelelnek egy adott feltételnek. Kattintson a <strong>Feltétel hozzáadása</strong> lehetőségre, ha meg szeretné adni a feltételt.</li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Munkafolyamat felhasználója</td>
    <td>Az aktuális munkafolyamatban szereplő felhasználó</td>
    <td>
    <ul>
    <li>Miután kijelölte <strong>Munkafolyamat-felhasználó</strong> lehetőséget a <strong>Munkafolyamat-felhasználó</strong> lapon a <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki egy felhasználót, aki részt vesz a munkafolyamatban.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Felhasználó</td>
    <td>Meghatározott felhasználók</td>
    <td>
    <ol>
    <li>Miután kijelölte <strong>Felhasználó</strong> lehetőséget, kattintson a <strong>Felhasználó</strong> fülre.</li>
    <li>A <strong>Rendelkezésre álló felhasználók</strong> listája az összes felhasználót tartalmazza. Válassza ki a döntéshez hozzárendelni kívánt felhasználókat, majd ezt követően helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. A **Határidő** lapon az **Időtartam** mezőben adja meg, hogy mennyi idő kell a felhasználónak a döntéshozatalhoz. Válasszon a következő lehetőségek közül:

    - **Órák** – Adja meg azon órák számát, amely alatt a felhasználónak meg kell hoznia a döntést. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Napok** – Adja meg azon napok számát, amely alatt a felhasználónak meg kell hoznia a döntést. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Hetek** – Adja meg azon hetek számát, amely alatt a felhasználónak meg kell hoznia a döntést.
    - **Hónapok** – Válassza ki, hogy melyik hét mely napjáig kell a felhasználónak meghoznia a döntést. Kérheti például, hogy a felhasználó a hónap harmadik hetének péntekéig hozza meg a döntést.
    - **Évek** – Válassza ki, hogy melyik hónap mely hetéig kell a felhasználónak meghoznia a döntést. Kérheti például, hogy a felhasználó december harmadik hetének péntekéig hozza meg a döntést.

    Ha a felhasználó nem hozza meg a döntést a megadott idő alatt, lejár a döntés. A lejárt döntés eszkalált, amely az **Eszkaláció** terület lapján kiválasztott beállításokon alapul.

## <a name="specify-what-happens-when-a-decision-is-overdue"></a>Annak megadása, hogy mi történjen, amikor lejár a döntés

Ha a felhasználó nem hozza meg a döntést a megadott idő alatt, lejár a döntés. A lejárt döntést eszkalálhatja, illetve automatikusan egy másik felhasználóhoz rendelheti jóváhagyás céljából. Kövesse az alábbi lépéseket a döntés eszkalálásához ha lejárt a döntés.

1. A bal oldali panelen kattintson az **Eszkalálás** gombra.
2. Válassza ki az **Eszkalációs útvonal használata** jelölőnégyzetet egy eszkalációs útvonal létrehozásához. A rendszer automatikusan hozzárendeli a döntést az eszkalációs útvonalon felsorolt felhasználókhoz. Például az alábbi táblázat egy eszkalációs útvonalat jelent.

    | Sorozat | Eszkalációs útvonal            |
    |----------|----------------------------|
    | 1        | Hozzárendelés a következőhöz: Dóra           |
    | 2        | Hozzárendelés a következőhöz: Ervin            |
    | 3        | Végső művelet: \[Választható 1\] |

    Ebben a példában a rendszer Dórához rendeli a lejárt döntést. Ha Dóra nem hozza meg a döntést a kijelölt időkereten belül, a rendszer Ervinhez rendeli hozzá. Ha Ervin nem hozza meg a döntést a kijelölt időkereten belül, a rendszer a **\[Választható 1\]** lehetőséget választja ki döntésként.

3. A felhasználó eszkalációs útvonalhoz történő hozzáadásához, kattintson az **Újabb eszkalációs lépés** lehetőségre. Válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 4. lépésre.

    <table>
    <thead>
    <tr>
    <th>Lehetőség</th>
    <th>A döntéshez eszkalált felhasználók</th>
    <th>További lépések</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Hierarchia</td>
    <td>A meghatározott szervezeti hierarchiában lévő felhasználók.</td>
    <td>
    <ol>
    <li>Miután kiválasztotta <strong>Hierarchia</strong> lehetőséget a <strong>Hierarchia kiválasztása</strong> lapon, a <strong>Hierarchia típusa</strong> listán, jelölje ki a döntéshez eszkalálni hierarchia típusát.</li>
    <li>A rendszernek be kell olvasnia az felhasználó névtartományát a hierarchiából. Ezek a nevek a döntéshez eszkalálható felhasználókat jelölik. Végezze el a következő lépéseket azon felhasználók névtartományának kezdő- és végpontját, amelyet a rendszer beolvas: <ol>
    <li>A kezdő pont megadásához válasszon ki egy személyt a <strong>Kezdet</strong> listából.</li>
    <li>A végpont megadásához kattintson a <strong>Feltétel létrehozása</strong> lehetőségre. Ezt követően adja meg azt a feltételt, amely meghatározza, hogy a rendszer hol állítsa meg a hierarchiában a nevek beolvasását.</li>
    </ol>
    </li>
    <li>A <strong>Hierarchia beállításai</strong> lapon adja meg, hogy mely, a tartományban szereplő felhasználókhoz kell a döntést eszkalálni: <ul>
    <li><strong>Minden lekért felhasználó hozzárendelése</strong> – A tartományban szereplő összes felhasználóhoz eszkalálva van a döntés.</li>
    <li><strong>Csak a legutóbb lekért felhasználó hozzárendelése</strong> – Csak a tartományban szereplő utolsó felhasználóhoz van eszkalálva a döntés.</li>
    <li><strong>A következő feltételnek megfelelő felhasználók kihagyása</strong> – A döntés nincs eszkalálva a tartomány minden olyan felhasználójához, akik megfelelnek egy adott feltételnek. Kattintson a <strong>Feltétel hozzáadása</strong> lehetőségre, ha meg szeretné adni a feltételt.</li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Munkafolyamat felhasználója</td>
    <td>Az aktuális munkafolyamatban szereplő felhasználó</td>
    <td>
    <ul>
    <li>Miután kijelölte <strong>Munkafolyamat-felhasználó</strong> lehetőséget a <strong>Munkafolyamat-felhasználó</strong> lapon a <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki egy felhasználót, aki részt vesz a munkafolyamatban.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Felhasználó</td>
    <td>Meghatározott felhasználók</td>
    <td>
    <ol>
    <li>Miután kijelölte <strong>Felhasználó</strong> lehetőséget, kattintson a <strong>Felhasználó</strong> fülre.</li>
    <li>A <strong>Rendelkezésre álló felhasználók</strong> listája az összes felhasználót tartalmazza. Válassza ki a döntéshez eszkalálni kívánt felhasználókat, majd ezt követően helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. A **Határidő** lapon az **Időtartam** mezőben adja meg, hogy mennyi idő kell a felhasználónak a döntéshozatalhoz. Válasszon a következő lehetőségek közül:

    - **Órák** – Adja meg azon órák számát, amely alatt a felhasználónak meg kell hoznia a döntést. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Napok** – Adja meg azon napok számát, amely alatt a felhasználónak meg kell hoznia a döntést. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Hetek** – Adja meg azon hetek számát, amely alatt a felhasználónak meg kell hoznia a döntést.
    - **Hónapok** – Válassza ki, hogy melyik hét mely napjáig kell a felhasználónak meghoznia a döntést. Kérheti például, hogy a felhasználó a hónap harmadik hetének péntekéig hozza meg a döntést.
    - **Évek** – Válassza ki, hogy melyik hónap mely hetéig kell a felhasználónak meghoznia a döntést. Kérheti például, hogy a felhasználó december harmadik hetének péntekéig hozza meg a döntést.

5. Ismételje meg a 3 – 4. lépést minden egyes olyan felhasználóra vonatkozóan, akiket hozzá kell adni az eszkalációs útvonalhoz. A felhasználók sorrendje módosítható.
6. Ha az eszkalációs útvonalban szereplő felhasználók nem hozzák meg a döntést a megadott időn belül, a rendszer hozza meg a döntést. A rendszer által kijelölt beállítás meghatározásához, válassza ki a **Művelet** sort, majd a **Művelet lezárása** fülön válasszon ki egy beállítást.

## <a name="set-a-time-limit"></a>Időkorlát beállítása

Kövesse az alábbi lépéseket, ha a döntést egy megadott időn belül kell meghozni.

> [!NOTE]
> Az eljárásban kijelölt beállítások felülbírálják az oldal **Hozzárendelés** és **Eszkaláció** területén kijelölt beállításokat.

1. A bal oldali panelen kattintson az **Speciális beállítások** gombra.
2. Válassza ki a **A munkafolyamat-elem időkorlátjának beállítása** jelölőnégyzetet.
3. Az **Időtartam** mezőbe adja meg, hogy mikor kell meghozni a döntést. Válasszon a következő lehetőségek közül:

    - **Órák** – Adja meg az órák számát. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Napok** – Adja meg a napok számát. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Hetek** – Adja meg a hetek számát.
    - **Hónapok** – Válassza ki, hogy melyik hét mely napjáig kell a döntést meghozni. Kérheti például, hogy a döntést a hónap harmadik hetének péntekéig kell meghozni.
    - **Évek** – Válassza ki, hogy mely hónap, mely hét, mely napjáig kell a döntést meghozni. Kérheti például, hogy a döntést december harmadik hetének péntekéig kell meghozni.

4. Ha lejár az időkorlát, a rendszer hozza meg a döntést. Válassza ki a **Művelet** listából, hogy milyen beállítást kell a rendszernek kiválasztania.
