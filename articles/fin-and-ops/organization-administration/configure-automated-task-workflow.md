---
title: "Automatikus feladat konfigurálása munkafolyamatban"
description: "Ez a témakör bemutatja, hogyan kell konfigurálni az automatizált feladat tulajdonságait."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e8189f8d16e9b6dcbc339a23c1af5402c0316ce3
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="configure-an-automated-task-in-a-workflow"></a>Automatikus feladat konfigurálása munkafolyamatban

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan kell konfigurálni az automatizált feladat tulajdonságait.

A munkafolyamat-szerkesztő automatizált feladatának konfigurálásához, kattintson a jobb gombbal a feladatra, és kattintson **Tulajdonságok** oldal megnyitásához a **Tulajdonságok** lehetőségre. Ezt követően a következő eljárások segítségével állítsa be az automatizált feladat tulajdonságait.

## <a name="name-the-task"></a>A feladat elnevezése
A következő lépések segítségével elnevezheti az automatizált feladatot.

1.  A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2.  Adja meg a feladat egyedi nevét a **Név** mezőben.

## <a name="specify-when-notifications-are-sent"></a>Az értesítések küldési idejének meghatározása
Értesítéseket küldhet a felhasználóknak az automatizált feladat futtatásakor, vagy visszavonásakor. Végezze el a következő lépéseket, annak meghatározása érdekében, hogy mikor és kinek küldje el a rendszer az értesítéseket.

1.  A bal oldali panelen kattintson az **Értesítések** gombra.
2.  Jelölje be a jelölőnégyzetet azon eseményekhez, amelyekhez ki kell küldeni az értesítéseket:
    -   **Végrehajtás** – A rendszer értesítéseket küld a feladat futtatásakor.
    -   **Érvénytelenítve** – A rendszer értesítéseket küld a feladat érvénytelenítésekor.

3.  Jelölje ki a sort a 2. lépésben választott eseményhez.
4.  Írja be az értesítés szövegét az **Értesítési szöveg** lapon lévő szövegdobozba.
5.  Az értesítések személyre szabásához, helyőrzőket szúrhat be. A helyőrzők helyére a megfelelő adatok kerülnek, amikor az értesítés megjelenik a felhasználók számára. Végezze el a következő lépéseket a helyőrzők beillesztéséhez:
    1.  Kattintson oda a szövegdobozban, ahol meg szeretné jeleníteni a helyőrzőt.
    2.  Kattintson a **Helyőrző beszúrása** lehetőségre.
    3.  A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.
    4.  Kattintson a **Beszúrás** lehetőségre.

6.  Az értesítések fordításainak hozzáadásához, végezze el a következő lépéseket:
    1.  Kattintson a **Fordítások** lehetőségre.
    2.  A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.
    3.  A megjelenő listában válassza ki az éppen begépelt szöveg nyelvét.
    4.  Írja be a szöveget a **Lefordított szöveg** mezőbe.
    5.  A szöveg személyre szabásához, helyőrzőket illeszthet be a 5. lépésben leírtak szerint.
    6.  Kattintson a **Bezárás** gombra.

7.  Adja meg azokat a személyeket, akik értesítéseket kapnak a **Címzett** lapon. Válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 8. lépésre.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Lehetőség</th>
    <th>Értesítés címzettjei</th>
    <th>További lépések</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Résztvevő</td>
    <td>Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</td>
    <td><ol>
    <li>Miután kiválasztotta <strong>Résztvevő</strong> lehetőséget a <strong>Szerepkör-alapú</strong> lapon, a <strong>Résztvevő típusa</strong> listán jelölje ki azon csoport vagy a szerepkör típusát, amely számára az értesítéseket el kívánja küldeni.</li>
    <li>A <strong>Résztvevő</strong> listáján jelölje ki a csoportot vagy szerepkört, amely számára értesítést kíván küldeni.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Munkafolyamat felhasználója</td>
    <td>Az aktuális munkafolyamatban részt vevő felhasználók</td>
    <td><ul>
    <li>Miután kijelölte <strong>Munkafolyamat-felhasználó</strong> lehetőséget a <strong>Munkafolyamat-felhasználó</strong> lapon a <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki egy felhasználót, aki részt vesz a munkafolyamatban.</li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td>Felhasználó</td>
    <td>Konkrét Microsoft Dynamics 365 for Finance and Operations-felhasználók</td>
    <td><ol>
    <li>Miután kijelölte <strong>Felhasználó</strong> lehetőséget, kattintson a <strong>Felhasználó</strong> fülre.</li>
    <li>A <strong>Rendelkezésre álló felhasználók</strong> lista az összes Finance and Operations-felhasználót tartalmazza. Válassza ki azokat a felhasználókat, akik számára értesítéseket kíván küldeni, majd helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  Ismételje meg a 3 – 7. lépést a 2. lépésben kiválasztott összes eseményhez.





