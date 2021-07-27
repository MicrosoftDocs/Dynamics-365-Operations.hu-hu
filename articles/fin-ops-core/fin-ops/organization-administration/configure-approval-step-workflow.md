---
title: Jóváhagyási lépések konfigurálása munkafolyamatban
description: Ez a témakör bemutatja, hogyan kell konfigurálni a jóváhagyási lépés tulajdonságait.
author: ChrisGarty
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192161
ms.assetid: 8b478e3d-d6b4-403b-aae0-f639a71ca36c
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 988340d9e5fc12c9329a587c7401fe039c8e5722
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6350694"
---
# <a name="configure-approval-steps-in-a-workflow"></a>Jóváhagyási lépések konfigurálása munkafolyamatban

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan kell konfigurálni a jóváhagyási lépés tulajdonságait.

A munkafolyamat-szerkesztő jóváhagyási lépésének beállításához kattintson a jobb gombbal a jóváhagyási lépésre, és kattintson **Tulajdonságok** oldalon a **Tulajdonságok** lehetőségre. Ezt követően a következő eljárások segítségével állítsa be a jóváhagyási lépés tulajdonságait.

## <a name="name-the-step"></a>A lépés neve
A következő lépések segítségével elnevezheti a jóváhagyási lépést.

1. A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2. Írja be a jóváhagyási lépés egyedi nevét a **Név** mezőbe.

## <a name="enter-a-subject-line-and-instructions"></a>A tárgysor és az utasítások megadása

Meg kell adnia egy tárgysort, illetve utasításokat a jóváhagyási lépéshez hozzárendelt felhasználók számára. Például, ha a beszerzésiigénylések jóváhagyásilépését állítja be, a lépéshez hozzárendelt felhasználó látja a tárgysort és az utasításokat a **Beszerzési igénylések** oldalon. A tárgysor az oldal egy üzenetsorán jelenik meg. A felhasználó ezt követően rákattinthat az üzenetsoron található ikonra az útmutatás megtekintéséhez. Kövesse a következő lépéseket a tárgysor és az utasítások megadásához.

1. A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2. Írja be a tárgysort a **Munkatétel tárgya** mezőbe.
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

## <a name="assign-the-approval-step"></a>A jóváhagyási lépés hozzárendelése

Végezze el ezeket a lépéseket azon személyek meghatározásához, akiket jóváhagyási lépéshez hozzá kell rendelni.

1. A bal oldali panelen kattintson a **Hozzárendelés** gombra.
2. A **Hozzárendelés-típus** lapon válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 3. lépésre.

    <table>
    <thead>
    <tr>
    <th>Lehetőség</th>
    <th>A jóváhagyási lépéshez hozzárendelt felhasználók</th>
    <th>További lépések</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Résztvevő</td>
    <td>Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</td>
    <td>
    <ol>
    <li>Miután kiválasztotta <strong>Résztvevő</strong> lehetőséget a <strong>Szerepkör-alapú</strong> lapon, a <strong>Résztvevő típusa</strong> listán jelölje ki a lépéshez hozzárendelni kívánt csoport vagy a szerepkör típusát.</li>
    <li>A <strong>Résztvevő</strong> listáján jelölje ki a lépéshez hozzárendelni kívánt csoportot vagy szerepkört.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Hierarchia</td>
    <td>A meghatározott szervezeti hierarchiában lévő felhasználók.</td>
    <td>
    <ol>
    <li>Miután kiválasztotta <strong>Hierarchia</strong> lehetőséget a <strong>Hierarchia kiválasztása</strong> lapon, a <strong>Hierarchia típusa</strong> listán, jelölje ki a lépéshez hozzárendelni kívánt hierarchia típusát.</li>
    <li>A rendszernek be kell olvasnia az felhasználó névtartományát a hierarchiából. Ezek a nevek a lépéshez hozzárendelhető felhasználókat jelölik. Végezze el a következő lépéseket azon felhasználók névtartományának kezdő- és végpontját, amelyet a rendszer beolvas: <ol>
    <li>A kezdő pont megadásához válasszon ki egy személyt a <strong>Kezdet</strong> listából.</li>
    <li>A végpont megadásához kattintson a <strong>Feltétel létrehozása</strong> lehetőségre. Ezt követően adja meg azt a feltételt, amely meghatározza, hogy a rendszer hol állítsa meg a hierarchiában a nevek beolvasását.</li>
    </ol>
    </li>
    <li>A <strong>Hierarchia beállításai</strong> lapon adja meg, hogy mely, a tartományban szereplő felhasználók számára kell a lépést hozzárendelni: <ul>
    <li><strong>Minden lekért felhasználó hozzárendelése</strong> – A tartományban szereplő összes felhasználóhoz hozzá van rendelve a lépés.</li>
    <li><strong>Csak a legutóbb lekért felhasználó hozzárendelése</strong> – Csak a tartományban szereplő utolsó felhasználóhoz van hozzárendelve a lépés.</li>
    <li><strong>A következő feltételnek megfelelő felhasználók kihagyása</strong> – A lépés nincs hozzárendelve a tartomány minden olyan felhasználójához, akik megfelelnek egy adott feltételnek. Kattintson a <strong>Feltétel hozzáadása</strong> lehetőségre, ha meg szeretné adni a feltételt.</li>
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
    <li>A <strong>Rendelkezésre álló felhasználók</strong> listája az összes rendszerfelhasználót tartalmazza. Válassza ki a lépéshez hozzárendelni kívánt felhasználókat, majd ezt követően helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. A **Határidő** lapon az **Időtartam** mezőben adja meg, hogy mennyi idő kell a felhasználónak azon dokumentumok végrehajtásához, vagy a válaszolásához, amelyek érvényesek a jóváhagyási lépésre. Válasszon a következő lehetőségek közül:

    - **Órák** – Adja meg azon órák számát, amely alatt a felhasználónak reagálnia kell. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Napok** – Adja meg azon napok számát, amely alatt a felhasználónak reagálnia kell. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Hetek** – Adja meg azon hetek számát, amely alatt a felhasználónak reagálnia kell.
    - **Hónapok** – Válassza ki, hogy melyik hét mely napjáig kell a felhasználónak reagálnia. Például meg lehet adni, hogy a felhasználó a hónap harmadik hetének pénteki napjáig kelljen reagálnia.
    - **Évek** – Válassza ki, hogy melyik napon és melyik héten kell a felhasználónak reagálnia. Például meg lehet adni, hogy a felhasználónak december harmadik hetének pénteki napjáig kelljen reagálnia.

    Ha a felhasználó nem hajtja végre a dokumentum műveletét a megadott idő alatt, lejár a dokumentum. A lejárt dokumentum eszkalált, amely az **Eszkaláció** terület lapján kiválasztott beállításokon alapul.

4. Ha a jóváhagyási lépéshez több felhasználót vagy felhasználói csoportot rendel, a **Befejezési irányelv** fülön válasszon ki egyet a következő lehetőségek közül:

    - **Egyedi jóváhagyó** – A dokumentumhoz kapcsolódó műveletet az elsőként válaszoló személy határozza meg. Például, Balázs egy 15 000 USA-dolláros költségjelentést küldött el. A költségjelentés jelenleg Zsuzsannához, Jankához és Vilmoshoz van hozzárendelve. Ha elsőként Zsuzsanna válaszol a dokumentumra, az általa végzett művelet érvényes a dokumentumra. Ha Zsuzsanna visszautasítja a dokumentumot, akkor a visszautasított dokumentum visszakerül Balázshoz. Ha Zsuzsanna jóváhagyja a dokumentumot, akkor a dokumentum Annához kerül jóváhagyásra.

        ![Jóváhagyási folyamattal rendelkező munkafolyamat.](./media/workflow_multipleusersinstep.gif)

    - **A jóváhagyók többsége** – A dokumentumhoz rendelt művelet meg van határozva, ha a jóváhagyók többsége válaszol. Például, Balázs egy 15 000 USA-dolláros költségjelentést küldött el. A költségjelentés jelenleg Zsuzsannához, Jankához és Vilmoshoz van hozzárendelve. Ha Zsuzsanna és Janka az első két választ adó jóváhagyó, a rendszer hozzárendeli az általuk végzett műveletet a dokumentumhoz.

        - Ha Zsuzsanna jóváhagyja a dokumentumot, viszont Janka visszautasítja azt, akkor a dokumentum visszautasításra kerül, és visszaküldik Balázs részére.
        - Ha Zsuzsanna és Janka jóváhagyja a dokumentumot, akkor a dokumentum Annához kerül jóváhagyásra.

    - **A jóváhagyók százaléka** – A rendszer meghatározza a dokumentumhoz kapcsolódó műveletet, ha válaszol a jóváhagyók meghatározott százaléka. Például, Balázs egy 15 000 USA-dolláros költségjelentést küldött el. A költségjelentés jelenleg Zsuzsannához, Jankához és Vilmoshoz van hozzárendelve, **50** értéket adott meg százalékos értékként. Ha Zsuzsanna és Janka az első két jóváhagyó, aki válaszol, az általuk végzett művelet hozzá van rendelve a dokumentumhoz, mert azok megfelelnek a jóváhagyók 50%-os követelményének.

        - Ha Zsuzsanna jóváhagyja a dokumentumot, viszont Janka visszautasítja azt, akkor a dokumentum visszautasításra kerül, és visszaküldik Balázs részére.
        - Ha Zsuzsanna és Janka jóváhagyja a dokumentumot, akkor a dokumentum Annához kerül jóváhagyásra.

    - **Minden jóváhagyó** – Minden jóváhagyónak jóvá kell hagynia a dokumentumot. Máskülönben a munkafolyamat nem folytatható. Például, Balázs egy 15 000 USA-dolláros költségjelentést küldött el. A költségjelentés jelenleg Zsuzsannához, Jankához és Vilmoshoz van hozzárendelve. Ha Zsuzsanna és Janka jóváhagyja a dokumentumot, viszont Vilmos visszautasítja azt, akkor a dokumentum visszautasításra kerül, és visszaküldik Balázs részére. Ha Zsuzsanna, Janka és Vilmos jóváhagyja a dokumentumot, akkor a dokumentum Annához kerül jóváhagyásra.

## <a name="specify-when-the-approval-step-is-required"></a>Határozza meg, hogy mikor van szükség a jóváhagyási lépésre.

Meghatározhatja, hogy mikor van szükség a jóváhagyási lépésre. A jóváhagyási lépésre minden esetben szükség lehet, vagy csak akkor lehet szükséges, ha bizonyos feltételek teljesülnek.

### <a name="the-approval-step-is-always-required"></a>A jóhagyási lépés mindig szükséges.

Végezze el a következő lépéseket, ha a jóváhagyási lépés mindig szükséges.

1. A bal oldali panelen kattintson a **Feltétel** gombra.
2. Válassza az **Ez a lépés mindig legyen végrehajtva** lehetőséget.

### <a name="the-approval-step-is-required-in-specific-conditions"></a>A bizonyos feltételek fennállása esetén szükséges jóváhagyási lépés

Lehet, hogy az éppen konfigurált lépést csak akkor szükséges megadni, ha bizonyos feltételek teljesülnek. Például, ha egy beszerzési igénylési munkafolyamat egyik jóváhagyási lépését konfigurálja, csak akkor érdemes elvégezni a jóváhagyási lépést, ha a beszerzési igénylés összege nagyobb 10 000 USA-dollárnál. Végezze el a következő lépéseket, amikor szükséges a jóváhagyási lépés.

1. A bal oldali panelen kattintson a **Feltétel** gombra.
2. Jelölje be a **Csak akkor fusson ez a lépés, ha teljesül a következő feltétel** lehetőséget.
3. Feltétel megadása.
4. Adja meg a további szükséges feltételeket.
5. Ha ellenőrizni szeretné, hogy a megadott feltételek helyesen vannak-e konfigurálva, végezze el a következő lépéseket:

    1. Kattintson a **Teszt** gombra.
    2. A **Munkafolyamati feltétel tesztelése** oldalon, a **Feltétel érvényesítése** területen válasszon ki egy rekordot.
    3. Kattintson a **Teszt** gombra. A rendszer értékeli a bejegyzést, annak érdekében, hogy meghatározza, hogy a meghatározott feltételeknek megfeleljen-e.
    4. Kattintson az **OK** vagy a **Mégse** lehetőségre a **Tulajdonságok** lapra történő visszalépéshez.

## <a name="specify-what-happens-when-the-document-is-overdue"></a>Határozza meg, hogy mi történjen a dokumentum lejárata esetén

Ha egy felhasználó nem hajtja végre a dokumentum műveletét a megadott idő alatt, lejár a dokumentum. A lejárt dokumentumot eszkalálhatja, illetve automatikusan egy másik felhasználóhoz rendelheti jóváhagyás céljából. Kövesse az alábbi lépéseket a dokumentum eszkalálásához ha lejárt a dokumentum.

1. A bal oldali panelen kattintson az **Eszkalálás** gombra.
2. Válassza ki az **Eszkalációs útvonal használata** jelölőnégyzetet egy eszkalációs útvonal létrehozásához. A rendszer automatikusan hozzárendeli a dokumentumot az eszkalációs útvonalon felsorolt felhasználókhoz. Például az alábbi táblázat egy eszkalációs útvonalat jelent.

    | Sorozat | Eszkalációs útvonal      |
    |----------|----------------------|
    | 1        | Hozzárendelés a következőhöz: Dóra     |
    | 2        | Hozzárendelés a következőhöz: Ervin      |
    | 3        | Utolsó művelet: Elutasítás |

    Ebben a példában a rendszer Dórához rendeli a lejárt dokumentumot. Ha Dóra nem válaszol a megadott idő alatt, a rendszer Ervinhez rendeli a dokumentumot. Ha Ervin nem válaszol a megadott idő alatt, a rendszer visszautasítja a dokumentumot.

3. A felhasználó eszkalációs útvonalhoz történő hozzáadásához, kattintson az **Újabb eszkalációs lépés** lehetőségre. A **Hozzárendelés-típus** lapon válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 4. lépésre.

    <table>
    <thead>
    <tr>
    <th>Lehetőség</th>
    <th>A dokumentumhoz eszkalált felhasználók</th>
    <th>További lépések</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Hierarchia</td>
    <td>A meghatározott szervezeti hierarchiában lévő felhasználók.</td>
    <td>
    <ol>
    <li>Miután kiválasztotta <strong>Hierarchia</strong> lehetőséget a <strong>Hierarchia kiválasztása</strong> lapon, a <strong>Hierarchia típusa</strong> listán, jelölje ki a dokumentumhoz eszkalálni hierarchia típusát.</li>
    <li>A rendszernek be kell olvasnia az felhasználó névtartományát a hierarchiából. Ezek a nevek a dokumentumhoz eszkalálható felhasználókat jelölik. Végezze el a következő lépéseket azon felhasználók névtartományának kezdő- és végpontját, amelyet a rendszer beolvas: <ol>
    <li>A kezdő pont megadásához válasszon ki egy személyt a <strong>Kezdet</strong> listából.</li>
    <li>A végpont megadásához kattintson a <strong>Feltétel létrehozása</strong> lehetőségre. Ezt követően adja meg azt a feltételt, amely meghatározza, hogy a rendszer hol állítsa meg a hierarchiában a nevek beolvasását.</li>
    </ol>
    </li>
    <li>A <strong>Hierarchia beállításai</strong> lapon adja meg, hogy mely, a tartományban szereplő felhasználókhoz kell a dokumentumot eszkalálni: <ul>
    <li><strong>Minden lekért felhasználó hozzárendelése</strong> – A tartományban szereplő összes felhasználóhoz eszkalálva van a dokumentum.</li>
    <li><strong>Csak a legutóbb lekért felhasználó hozzárendelése</strong> – Csak a tartományban szereplő utolsó felhasználóhoz van eszkalálva a dokumentum.</li>
    <li><strong>A következő feltételnek megfelelő felhasználók kihagyása</strong> – A dokumentum nincs eszkalálva a tartomány összes olyan felhasználójához, akik megfelelnek egy adott feltételnek. Kattintson a <strong>Feltétel hozzáadása</strong> lehetőségre, ha meg szeretné adni a feltételt.</li>
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
    <li>A <strong>Rendelkezésre álló felhasználók</strong> listája az összes felhasználót tartalmazza. Válassza ki a dokumentumhoz eszkalálni kívánt felhasználókat, majd ezt követően helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. A **Határidő** lapon az **Időtartam** mezőben adja meg, hogy mennyi idő kell a felhasználónak azon dokumentumok végrehajtásához, vagy a válaszolásához, amelyek érvényesek a jóváhagyási lépésre. Válasszon a következő lehetőségek közül:

    - **Órák** – Adja meg azon órák számát, amely alatt a felhasználónak reagálnia kell. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Napok** – Adja meg azon napok számát, amely alatt a felhasználónak reagálnia kell. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Hetek** – Adja meg azon hetek számát, amely alatt a felhasználónak reagálnia kell.
    - **Hónapok** – Válassza ki, hogy melyik hét mely napjáig kell a felhasználónak reagálnia. Például meg lehet adni, hogy a felhasználó a hónap harmadik hetének pénteki napjáig kelljen reagálnia.
    - **Évek** – Válassza ki, hogy melyik napon és melyik héten kell a felhasználónak reagálnia. Például meg lehet adni, hogy a felhasználónak december harmadik hetének pénteki napjáig kelljen reagálnia.

5. Ismételje meg a 3 – 4. lépést minden egyes olyan felhasználóra vonatkozóan, akiket hozzá kell adni az eszkalációs útvonalhoz. A felhasználók sorrendje módosítható.
6. Ha az eszkalációs útvonalban szereplő felhasználók nem válaszolnak a megadott időn belül, a rendszer automatikusan végrehajtja a dokumentumot. A rendszer által végzett művelet meghatározásához, válassza ki a **Művelet** sort, majd a **Művelet lezárása** fülön válasszon ki egy műveletet.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]