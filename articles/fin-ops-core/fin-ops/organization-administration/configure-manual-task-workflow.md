---
title: Manuális feladatok konfigurálása munkafolyamatban
description: Ez a témakör bemutatja, hogyan kell konfigurálni a manuális feladat tulajdonságait.
author: ChrisGarty
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192191
ms.assetid: 27f1afde-ff26-4b6f-8c11-27ec49130bbb
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4be7f0ee5e487185033b7ccb9a2b0a91eb4a36c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747855"
---
# <a name="configure-manual-tasks-in-a-workflow"></a>Manuális feladatok konfigurálása munkafolyamatban

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan kell konfigurálni a manuális feladat tulajdonságait.

A munkafolyamat-szerkesztő manuális feladatának konfigurálásához, kattintson a jobb gombbal a feladatra, és kattintson **Tulajdonságok** oldal megnyitásához a **Tulajdonságok** lehetőségre. Ezt követően a következő eljárások segítségével állítsa be a manuális feladat tulajdonságait.

## <a name="name-the-task"></a>A feladat elnevezése

A következő lépések segítségével elnevezheti a manuális feladatot.

1. A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2. Adja meg a feladat egyedi nevét a **Név** mezőben.

## <a name="enter-a-subject-line-and-instructions"></a>A tárgysor és az utasítások megadása

Meg kell adnia egy tárgysort, illetve utasításokat a feladathoz hozzárendelt felhasználók számára. Például, ha a beszerzési igénylések feladatát konfigurálja, a feladathoz hozzárendelt felhasználó látja a tárgysort és az utasításokat a **Beszerzési igénylések** oldalon. A tárgysor az oldal egy üzenetsorán jelenik meg. A felhasználó ezt követően rákattinthat az üzenetsoron található ikonra az útmutatás megtekintéséhez. Kövesse a következő lépéseket a tárgysor és az utasítások megadásához.

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

## <a name="assign-the-task"></a>A feladat hozzárendelése

Végezze el ezeket a lépéseket azon személyek meghatározásához, akiket a manuális feladathoz hozzá kell rendelni.

1. A bal oldali panelen kattintson a **Hozzárendelés** gombra.
2. A **Hozzárendelés-típus** lapon válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 3. lépésre.

    <table>
    <thead>
    <tr>
    <th>Lehetőség</th>
    <th>A feladathoz hozzárendelt felhasználók</th>
    <th>További lépések</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Résztvevő</td>
    <td>Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</td>
    <td>
    <ol>
    <li>Miután kiválasztotta <strong>Résztvevő</strong> lehetőséget a <strong>Szerepkör-alapú</strong> lapon, a <strong>Résztvevő típusa</strong> listán jelölje ki a feladathoz hozzárendelni kívánt csoport vagy a szerepkör típusát.</li>
    <li>A <strong>Résztvevő</strong> listáján jelölje ki a feladathoz hozzárendelni kívánt csoportot vagy szerepkört.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Hierarchia</td>
    <td>A meghatározott szervezeti hierarchiában lévő felhasználók.</td>
    <td>
    <ol>
    <li>Miután kiválasztotta <strong>Hierarchia</strong> lehetőséget a <strong>Hierarchia kiválasztása</strong> lapon, a <strong>Hierarchia típusa</strong> listán, jelölje ki a feladathoz hozzárendelni kívánt hierarchia típusát.</li>
    <li>A rendszernek be kell olvasnia az felhasználó névtartományát a hierarchiából. Ezek a nevek a feladatokhoz hozzárendelhető felhasználókat jelölik. Végezze el a következő lépéseket azon felhasználók névtartományának kezdő- és végpontját, amelyet a rendszer beolvas: <ol>
    <li>A kezdő pont megadásához válasszon ki egy személyt a <strong>Kezdet</strong> listából.</li>
    <li>A végpont megadásához kattintson a <strong>Feltétel létrehozása</strong> lehetőségre. Ezt követően adja meg azt a feltételt, amely meghatározza, hogy a rendszer hol állítsa meg a hierarchiában a nevek beolvasását.</li>
    </ol>
    </li>
    <li>A <strong>Hierarchia beállításai</strong> lapon adja meg, hogy mely, a tartományban szereplő felhasználók számára kell a feladatot hozzárendelni: <ul>
    <li><strong>Minden lekért felhasználó hozzárendelése</strong> – A tartományban szereplő összes felhasználóhoz hozzá van rendelve a feladat.</li>
    <li><strong>Csak a legutóbb lekért felhasználó hozzárendelése</strong> – Csak a tartományban szereplő utolsó felhasználóhoz van hozzárendelve a feladat.</li>
    <li><strong>A következő feltételnek megfelelő felhasználók kihagyása</strong> – A feladat nincs hozzárendelve a tartomány minden olyan felhasználójához, akik megfelelnek egy adott feltételnek. Kattintson a <strong>Feltétel hozzáadása</strong> lehetőségre, ha meg szeretné adni a feltételt.</li>
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
    <li>A <strong>Rendelkezésre álló felhasználók</strong> listája az összes felhasználót tartalmazza. Válassza ki a feladathoz hozzárendelni kívánt felhasználókat, majd ezt követően helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Várakozási sor</td>
    <td>Munkatétel-várólista</td>
    <td>
    <ol>
    <li>Miután kijelölte <strong>Várólista</strong> lehetőséget, kattintson a <strong>Várólistán alapuló</strong> fülre.</li>
    <li>A feladat egy specifikus várólistához történő hozzárendeléséhez, kövesse az alábbi lépéseket: <ol>
    <li>A <strong>Várólista típusa</strong> listán, válassza ki a <strong>Munkatétel-várólisták</strong> lehetőséget.</li>
    <li>A <strong>Várólista neve</strong> listán jelölje ki a várólistát.</li>
    </ol>
    </li>
    <li>Ha egy adott feltételnek meg kell határozni, hogy melyik várólistához rendeljék hozzá a feladatot, végezze el a következő lépéseket: <ol>
    <li>A <strong>Várólista típusa</strong> listán, válassza ki a <strong>Feltételes munkatétel-várólisták</strong> lehetőséget.</li>
    <li>A <strong>Várólista neve</strong> listán jelölje ki a <strong>Feltételes várólista</strong> lehetőséget.</li>
    </ol>
    </li>
    </ol>
    <blockquote>[!NOTE] Ezt a beállítást csak néhány munkafolyamatnál használják, például Esetkezelésnél.</blockquote>
    </td>
    </tr>
    </tbody>
    </table>

3. A **Határidő** lapon az **Időtartam** mezőben adja meg, hogy mennyi idő kell a felhasználónak a feladat elvégzéséhez. Válasszon a következő lehetőségek közül:

    - **Órák** – Adja meg azon órák számát, amely alatt a felhasználónak be kell fejeznie a feladatot. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Napok** – Adja meg azon napok számát, amely alatt a felhasználónak be kell fejeznie a feladatot. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Hetek** – Adja meg azon hetek számát, amely alatt a felhasználónak be kell fejeznie a feladatot.
    - **Hónapok** – Válassza ki, hogy melyik hét mely napjáig kell a felhasználónak befejeznie a feladatot. Kérheti például, hogy a felhasználó a hónap harmadik hetének péntekéig hajtsa végre a feladatot.
    - **Évek** – Válassza ki, hogy mely hónap, mely hét, mely napjáig kell a felhasználónak befejeznie a feladatot. Kérheti például, hogy a felhasználó december harmadik hetének péntekéig hajtsa végre a feladatot.

    Ha a felhasználó nem hajtja végre a feladatot a megadott idő alatt, lejár a feladat. A lejárt feladatot eszkalálni lehet, amely az **Eszkaláció** terület lapján kiválasztott beállításokon alapul.

## <a name="specify-what-happens-when-the-task-is-overdue"></a>Annak megadása, hogy mi történjen, amikor lejár a feladat

Ha a felhasználó nem hajtja végre a manuális feladatot a megadott idő alatt, lejár a feladat. A lejárt feladatot eszkalálhatja, illetve automatikusan egy másik felhasználóhoz rendelheti jóváhagyás céljából. Kövesse az alábbi lépéseket a feladat eszkalálásához, ha lejárt a feladat.

1. A bal oldali panelen kattintson az **Eszkalálás** gombra.
2. Válassza ki az **Eszkalációs útvonal használata** jelölőnégyzetet egy eszkalációs útvonal létrehozásához. A rendszer automatikusan hozzárendeli a feladatot az eszkalációs útvonalon felsorolt felhasználókhoz. Például az alábbi táblázat egy eszkalációs útvonalat jelent.

    | Sorozat | Eszkalációs útvonal      |
    |----------|----------------------|
    | 1        | Hozzárendelés a következőhöz: Dóra     |
    | 2        | Hozzárendelés a következőhöz: Ervin      |
    | 3        | Utolsó művelet: Elutasítás |

    Ebben a példában a rendszer Dórához rendeli a lejárt feladatot. Ha Dóra nem fejezi be a feladatot a kijelölt időkereten belül, a rendszer Ervinhez rendeli hozzá. Ha Ervin nem hajtja végre a feladatot a kijelölt időkereten belül, a rendszer elutasítja a feldolgozásra elküldött dokumentumot.

3. A felhasználó eszkalációs útvonalhoz történő hozzáadásához, kattintson az **Újabb eszkalációs lépés** lehetőségre. A **Hozzárendelés-típus** lapon válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 4. lépésre.

    <table>
    <thead>
    <tr>
    <th>Lehetőség</th>
    <th>A feladathoz eszkalált felhasználók</th>
    <th>További lépések</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Hierarchia</td>
    <td>A meghatározott szervezeti hierarchiában lévő felhasználók.</td>
    <td>
    <ol>
    <li>Miután kiválasztotta <strong>Hierarchia</strong> lehetőséget a <strong>Hierarchia kiválasztása</strong> lapon, a <strong>Hierarchia típusa</strong> listán, jelölje ki a feladathoz eszkalálni kívánt hierarchia típusát.</li>
    <li>A rendszernek be kell olvasnia az felhasználó névtartományát a hierarchiából. Ezek a nevek a feladathoz eszkalálható felhasználókat jelölik. Végezze el a következő lépéseket azon felhasználók névtartományának kezdő- és végpontját, amelyet a rendszer beolvas: <ol>
    <li>A kezdő pont megadásához válasszon ki egy személyt a <strong>Kezdet</strong> listából.</li>
    <li>A végpont megadásához kattintson a <strong>Feltétel létrehozása</strong> lehetőségre. Ezt követően adja meg azt a feltételt, amely meghatározza, hogy a rendszer hol állítsa meg a hierarchiában a nevek beolvasását.</li>
    </ol>
    </li>
    <li>A <strong>Hierarchia beállításai</strong> lapon adja meg, hogy mely, a tartományban szereplő felhasználók számára kell a feladatot eszkalálni: <ul>
    <li><strong>Minden lekért felhasználó hozzárendelése</strong> – A tartományban szereplő összes felhasználóhoz eszkalálva van a feladat.</li>
    <li><strong>Csak a legutóbb lekért felhasználó hozzárendelése</strong> – Csak a tartományban szereplő utolsó felhasználóhoz van eszkalálva a feladat.</li>
    <li><strong>A következő feltételnek megfelelő felhasználók kihagyása</strong> – Ez a feladat nincs eszkalálva a tartomány minden olyan felhasználójához, akik megfelelnek egy adott feltételnek. Kattintson a <strong>Feltétel hozzáadása</strong> lehetőségre, ha meg szeretné adni a feltételt.</li>
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
    <li>A <strong>Rendelkezésre álló felhasználók</strong> listája az összes felhasználót tartalmazza. Válassza ki a feladathoz eszkalálni kívánt felhasználókat, majd ezt követően helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. A **Határidő** lapon az **Időtartam** mezőben adja meg, hogy mennyi idő kell a felhasználónak a feladat elvégzéséhez. Válasszon a következő lehetőségek közül:

    - **Órák** – Adja meg azon órák számát, amely alatt a felhasználónak be kell fejeznie a feladatot. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Napok** – Adja meg azon napok számát, amely alatt a felhasználónak be kell fejeznie a feladatot. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Hetek** – Adja meg azon hetek számát, amely alatt a felhasználónak be kell fejeznie a feladatot.
    - **Hónapok** – Válassza ki, hogy melyik hét mely napjáig kell a felhasználónak befejeznie a feladatot. Kérheti például, hogy a felhasználó a hónap harmadik hetének péntekéig hajtsa végre a feladatot.
    - **Évek** – Válassza ki, hogy mely hónap, mely hét, mely napjáig kell a felhasználónak befejeznie a feladatot. Kérheti például, hogy a felhasználó december harmadik hetének péntekéig hajtsa végre a feladatot.

5. Ismételje meg a 3 – 4. lépést minden egyes olyan felhasználóra vonatkozóan, akiket hozzá kell adni az eszkalációs útvonalhoz. A felhasználók sorrendje módosítható.
6. Ha az eszkalációs útvonalban szereplő felhasználók nem fejezik be a feladatot a megadott időn belül, a rendszer automatikusan végrehajtja a feladatot. A rendszer által végzett művelet meghatározásához, válassza ki a **Művelet** sort, majd a **Művelet lezárása** fülön válasszon ki egy műveletet.

## <a name="specify-when-the-system-automatically-acts-on-the-task"></a>Adja meg, hogy mikor végzi a rendszer automatikusan a feladatot

Beállíthatja a rendszert egy manuális művelet végrehajtására, ha bizonyos feltételek teljesülésnek. Például, egy feladathoz szükséges lehet, hogy a költség-jelentések részleg egyik tagja átvizsgálja azokat a bevételezéseket, amelyeket a költségjelentéssel együtt elküldtek. A cég irányelvei szerint ezt a feladatot akkor kell elvégezni, ha a költségjelentés teljes összege meghaladja a 100 USD-t. Ebben az esetben állítsa be a rendszert, hogy automatikusan jelölje meg a feladatot **Készként**, ha a teljes összeg 100-nál kisebb. Végezze el az alábbi lépéseket a manuális feladat végrehajtásának idejének meghatározásához.

1. A bal oldali panelen kattintson az **Automatikus műveletek** gombra.
2. Jelölje ki az **Automatikus műveletek engedélyezése** jelölőnégyzetet.
3. Kattintson a **Feltétel hozzáadása** parancsra.
4. Feltétel megadása.
5. Adja meg a további szükséges feltételeket.
6. Ha ellenőrizni szeretné, hogy a megadott feltételek helyesen vannak-e konfigurálva, végezze el a következő lépéseket:

    1. Kattintson a **Teszt** gombra.
    2. A **Munkafolyamati feltétel tesztelése** oldalon, a **Feltétel érvényesítése** területen válasszon ki egy rekordot.
    3. Kattintson a **Teszt** gombra. A rendszer értékeli a bejegyzést, annak érdekében, hogy meghatározza, hogy a meghatározott feltételeknek megfeleljen-e.
    4. Kattintson az **OK** vagy a **Mégse** lehetőségre a **Tulajdonságok** lapra történő visszalépéshez.

7. Válassza ki **Automatikus befejezési művelet** listából, hogy milyen feladatokat kell a rendszernek végrehajtania.

## <a name="specify-when-notifications-are-sent"></a>Az értesítések küldési idejének meghatározása

Értesítéseket küldhet a felhasználóknak a manuális feladat delegálása, eszkalálása, illetve befejezése vagy visszautasítása, illetve változás kérése esetén. Végezze el a következő lépéseket, annak meghatározása érdekében, hogy mikor és kinek küldje el a rendszer az értesítéseket.

1. A bal oldali panelen kattintson az **Értesítések** gombra.
2. Jelölje be a jelölőnégyzetet azon eseményekhez, amelyekhez ki kell küldeni az értesítéseket:

    - **Delegálás** – A feladat egy másik felhasználóhoz van rendelve.
    - **Eszkaláció** – A hozzárendelt felhasználó nem fejezte be a feladatot a kijelölt időn belül.
    - **Teljes** – A hozzárendelt felhasználó befejezte a feladatot.
    - **Elutasítás** – A hozzárendelt felhasználó elutasította az elküldött dokumentumot.
    - **Változtatás kérése** – A hozzárendelt felhasználó kérte az elküldött dokumentum módosítását.

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
    <li>A <strong>Résztvevő</strong> listáján jelölje ki a csoportot vagy szerepkört, amely számára értesítést kíván küldeni.</li>
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

## <a name="set-a-time-limit"></a>Időkorlát beállítása

Kövesse az alábbi lépéseket, ha a kézi tevékenységet be kell fejezni egy megadott időn belül.

> [!NOTE]
> Az eljárásban kijelölt beállítások felülbírálják az oldal **Hozzárendelés** és **Eszkaláció** területén kijelölt beállításokat.

1. A bal oldali panelen kattintson az **Speciális beállítások** gombra.
2. Válassza ki a **A munkafolyamat-elem időkorlátjának beállítása** jelölőnégyzetet.
3. Az **Időtartam** mezőbe adja meg, hogy mikor kell végrehajtani a feladatot. Válasszon a következő lehetőségek közül:

    - **Órák** – Adja meg azon órák számát, amely alatt be kell fejezni a feladatot. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Napok** – Adja meg azon napok számát, amely alatt be kell fejezni a feladatot. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Hetek** – Adja meg azon hetek számát, amely alatt be kell fejezni a feladatot.
    - **Hónapok** – Válassza ki, hogy melyik hét mely napjáig kell a feladatot befejezni. Kérheti például, hogy a feladatot a hónap harmadik hetének péntekéig kell elvégezni.
    - **Évek** – Válassza ki, hogy mely hónap, mely hét, mely napjáig kell a feladatot elvégezni. Kérheti például, hogy a feladatot december harmadik hetének péntekéig kell elvégezni.

4. Ha lejár az időkorlát, a rendszer intézkedik a feladatról. Válassza ki a **Művelet** listából, hogy milyen műveletet kell a rendszernek végrehajtania.

## <a name="specify-which-actions-are-available-to-the-user"></a>Annak megadása, hogy mely műveletek érhetők el a felhasználó számára.

Amikor hozzárendelik a manuális feladatot egy felhasználóhoz, annak intézkednie kell a feladatról. Végezze el az alábbi lépéseket, annak meghatározásához, hogy mely műveleteket lehet elvégeznie a felhasználónak a feladaton.

> [!NOTE]
> Az elérhető műveletek változhatnak a feladat tervezetétől függően.

1. A bal oldali panelen kattintson az **Speciális beállítások** gombra.
2. Jelölje be a **Kész** jelölőnégyzetet, ha a felhasználónak a feladatot **Kész** állapotúnak kell minősítenie.
3. Jelölje be az **Elutasítás** jelölőnégyzetet, ha felhasználónak el kell utasítania az elküldött dokumentumot.
4. Jelölje be a **Változtatás kérése** jelölőnégyzetet, ha a felhasználónak a benyújtott dokumentum módosítását kell kérnie.
5. Jelölje be a **Delegálás** jelölőnégyzetet, ha a felhasználónak hozzá kell rendelnie a feladatot egy másik felhasználóhoz.
6. Jelölje be a **Ismételt hozzárendelés** jelölőnégyzetet, ha a felhasználónak hozzá kell rendelnie ismét a feladatot a munkatétel-várólistán szereplő felhasználóhoz.
7. Jelölje be a **Kiadás** jelölőnégyzetet, ha a felhasználónak hozzá kell rendelnie ismét a feladatot a munkatétel-várólistához. Ezt követően a másik felhasználó hajthatja végre a feladatot.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]