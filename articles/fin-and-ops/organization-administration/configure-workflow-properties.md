---
title: "Munkafolyamat-tulajdonságok konfigurálása"
description: "Ez a témakör bemutatja, hogyan kell konfigurálni a munkafolyamat különböző tulajdonságait."
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
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 19cc8f92b5bb6d9ddfdc77785e48de17ed005703
ms.openlocfilehash: 7ea35d851613a19889392400e31cf8492d5dc799
ms.contentlocale: hu-hu
ms.lasthandoff: 03/23/2018

---

# <a name="configure-workflow-properties"></a>Munkafolyamat-tulajdonságok konfigurálása

[!include[banner](../includes/banner.md)]


Ez a témakör bemutatja, hogyan kell konfigurálni a munkafolyamat különböző tulajdonságait.

A munkafolyamat tulajdonságainak beállítására, a munkafolyamat-szerkesztő megnyitása a munkafolyamat. Kattintson a munkafolyamat-szerkesztő vásznára, majd ezt követően kattintson a **Tulajdonságok** megnyitásához a **Tulajdonságok** képernyőn. A következő eljárások segítségével beállíthatja a munkafolyamat különféle tulajdonságait.

## <a name="name-the-workflow"></a>A munkafolyamat elnevezése
A következő lépések segítségével elnevezheti a munkafolyamatot.

1.  A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2.  A **Név** mezőbe írja be a munkafolyamat egyedi nevét. Például, ha létrehoz egy beszerzési igénylési munkafolyamatot minden működési országhoz/régióhoz, a beszerzési igénylés munkafolyamatának a **Beszerzési igénylések Dánia** vagy **Beszerzési igénylések Spanyolország** nevet adhatja.

## <a name="specify-the-workflow-owner"></a>A munkafolyamat tulajdonosának meghatározása
A munkafolyamat tulajdonosa az a személy, aki az adott munkafolyamatot kezeli és karbantartja. A következő lépések segítségével megadhatja a munkafolyamat tulajdonosát.

1.  A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2.  Válassza ki a munkafolyamatot kezelő személy nevét a **Tulajdonos** listából.

## <a name="select-an-email-template"></a>E-mail sablon kiválasztása
Végezze el az alábbi lépéseket azon e-mail sablon kiválasztásához, amelyet a munkafolyamattal kapcsolatos értesítések létrehozására használ.

1.  A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2.  Válasszak ki a sablont az **E-mail sablon munkafolyamat-értesítésekhez** listáján.

## <a name="enter-instructions-for-users"></a>Utasítások megadása felhasználók számára
Utasításokat adhat meg azon felhasználók számára, akik a dokumentumokat feldolgozásra és jóváhagyásra továbbítják. Ezeket a felhasználókat *létrehozók* néven is nevezik. Például, ha Ön egy beszerzési igénylési munkafolyamatot hoz létre, akkor utasításokat ad meg. Ezeket az utasításokat azok a felhasználók tekinthetik meg, akik a **Beszerzési igénylések** képernyőn beszerzési igényléseket adnak meg. Az útmutatás megtekintéséhez, a létrehozó a munkafolyamat üzenetsorán található ikonra kattint. A következő lépések segítségével utasításokat adhat meg a felhasználók számára.

1.  A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2.  Írja be az utasításokat a **Küldési utasítások** mezőbe.
3.  Az utasítások testreszabásához, helyőrzőket illeszthet be. A helyőrzők helyére a megfelelő adatok kerülnek, amikor az utasítások megjelennek a felhasználók számára. Végezze el a következő lépéseket a helyőrzők beillesztéséhez:
    1.  Kattintson a **Küldési utasítások** mezőre a helyőrző helyének meghatározásához.
    2.  Kattintson a **Helyőrző beszúrása** lehetőségre.
    3.  A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.
    4.  Kattintson a **Beszúrás** lehetőségre.

4.  Az utasítások fordításainak hozzáadásához, végezze el a következő lépéseket:
    1.  Kattintson a **Fordítások** lehetőségre.
    2.  A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.
    3.  A megjelenő listában válassza ki a szöveg nyelvét, amelyen írni fogja azt.
    4.  Írja be a szöveget a **Lefordított szöveg** mezőbe.
    5.  A szöveg testreszabásához, illesszen be helyőrzőket. A helyőrző megadásával kapcsolatos további tudnivalókért lásd a 3. lépést.
    6.  Kattintson a **Bezárás** gombra.

## <a name="specify-when-this-workflow-is-used"></a>A munkafolyamat használati idejének meghatározása.
Több, ugyanazon a típuson alapuló munkafolyamatot is megadhat. Például, ha létrehoz egy beszerzési igénylési munkafolyamatot minden működési országhoz/régióhoz, például a beszerzési igénylés munkafolyamatának a Beszerzési igénylések Dánia vagy Beszerzési igénylések Spanyolország nevet adhatja. Ha több olyan munkafolyamata van, amelyeknek alapja ugyanaz a típus, meg kell adnia, hogy mikor szeretné a munkafolyamtot használni. Az előző példához adja meg a következő feltételeket:

-   A Beszerzési igénylés Dánia akkor használandó, amikor: ország/terület = DK.
-   A Beszerzési igénylés Spanyolország akkor használandó, amikor: az ország/terület = ES.

A következő lépések segítségével megadhatja, hogy mikor szeretné használni az éppen konfigurált munkafolyamatot.

1.  A bal oldali panelen kattintson az **Aktiválás** gombra.
2.  Válassza ki a **A munkafolyamat futtatási feltételeinek beállítása** jelölőnégyzetet.
3.  Kattintson a **Feltétel hozzáadása** parancsra.
4.  Feltétel megadása.
5.  Adja meg a további szükséges feltételeket.
6.  Ha ellenőrizni szeretné, hogy a megadott feltételek helyesen vannak-e beállítva, végezze el a következő lépéseket:
    1.  Kattintson a **Teszt** gombra.
    2.  A **Munkafolyamati feltétel tesztelése** oldalon, a **Feltétel érvényesítése** területen válasszon ki egy rekordot.
    3.  Kattintson a **Teszt** gombra. A rendszer értékeli a bejegyzést, annak érdekében, hogy meghatározza, hogy az megfeleljen-e a meghatározott feltételeknek. Ha például Spanyolországhoz egy beszerzési igénylési munkafolyamatot hoz létre az oldal **Feltétel érvényesítése** területe megjeleníti a beszerzési igénylések listáját. Ha a **Teszt** parancsra kattint, a rendszer kiértékeli a kijelölt beszerzési igénylést annak érdekében, hogy meghatározza, hogy az ország/terület ES vagy sem.
    4.  Kattintson az **OK** vagy a **Mégse** lehetőségre a **Tulajdonságok** lapra történő visszalépéshez.

## <a name="specify-when-notifications-are-sent"></a>Az értesítések küldési idejének meghatározása
Amikor elküldenek egy dokumentumot feldolgozásra, létrejön egy munkafolyamat-példány. Értesítést a felhasználóknak olyankor küldhet, amikor a munkafolyamat-példányok (melyeknek alapja a munkafolyamat) elkezdődtek, elkészültek, megszakították őket, vagy hiba miatt leálltak. A következő lépések segítségével megadhatja, hogy mikor küldjön a rendszer értesítéseket.

1.  A bal oldali panelen kattintson az **Értesítések** gombra.
2.  Jelölje be a jelölőnégyzetet minden olyan eseményhez, amely az előidézi értesítéseket:
    -   **Elindítva** – Értesítések küldése, ha a rendszer elkezdi a munkafolyamat-példányt.
    -   **Leállítva** – Értesítések küldése, ha hiba miatt leáll a munkafolyamat-példány.
    -   **Befejeződött** – Értesítések küldése, ha befejeződött a munkafolyamat-példány.
    -   **Helyreállíthatatlan** – Értesítések küldése, ha helyreállíthatatlan hiba miatt leáll a munkafolyamat-példány.
    -   **Megszakítva** – Értesítések küldése, ha megszakították a munkafolyamat-példányt.

3.  Jelölje ki a sort a 2. lépésben választott eseményhez.
4.  Az **Értesítési szöveg** lapon, írja be az értesítés szövegét.
5.  A szöveg testreszabásához, illesszen be helyőrzőket. A helyőrzők helyére a megfelelő adatok kerülnek, amikor a szöveg megjelenik a felhasználók számára. Végezze el a következő lépéseket a helyőrzők beillesztéséhez:
    1.  Kattintson a mezőben oda, ahol meg szeretné jeleníteni a helyőrzőt.
    2.  Kattintson a **Helyőrző beszúrása** lehetőségre.
    3.  A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.
    4.  Kattintson a **Beszúrás** lehetőségre.

6.  A szöveg fordításainak hozzáadásához, végezze el a következő lépéseket:
    1.  Kattintson a **Fordítások** lehetőségre.
    2.  A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.
    3.  A megjelenő listában válassza ki a szöveg nyelvét, amelyen írni fogja azt.
    4.  Írja be a szöveget a **Lefordított szöveg** mezőbe.
    5.  A szöveg testreszabásához, illesszen be helyőrzőket. A helyőrző megadásával kapcsolatos további tudnivalókért lásd a 5. lépést.
    6.  Kattintson a **Bezárás** gombra.

7.  A **Címzett** lapon, a következő beállításokkal adja meg, határozza meg, hogy kik kaphatnak értesítéseket.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Lehetőség</th>
    <th>Ezeknek a felhasználóknak küldött értesítések</th>
    <th>Az értesítések küldéséhez, végezze el a következő lépéseket</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Résztvevő</td>
    <td>Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</td>
    <td><ol>
    <li>A <strong>Címzett</strong> lapon, kattintson a <strong>Résztvevő</strong> lehetőségre.</li>
    <li>A <strong>Szerepköralapú</strong> lapon, a <strong>Résztvevő típusa</strong> listán, válassza ki a csoport vagy a szerep típusát, amely számára értesítéseket kíván küldeni.</li>
    <li>A <strong>Résztvevő</strong> listáján jelölje ki a csoportot vagy szerepkört, amely számára értesítést kíván küldeni.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Munkafolyamat felhasználója</td>
    <td>A munkafolyamatban résztvevő felhasználók</td>
    <td><ol>
    <li>A <strong>Címzett</strong> lapon, kattintson a <strong>Munkafolyamat felhasználója</strong> lehetőségre.</li>
    <li>A <strong>Munkafolyamat-felhasználó</strong> lapon található <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki a munkafolyamat egy résztevevőjét.</li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td>Felhasználó</td>
    <td>Adott Finance and Operations-felhasználók</td>
    <td><ol>
    <li>A <strong>Címzett</strong> lapon, kattintson a <strong>Felhasználó</strong> lehetőségre.</li>
    <li>A <strong>Felhasználó</strong> lap <strong>Rendelkezésre álló felhasználók</strong> listája az összes Finance and Operations-felhasználót tartalmazza. Válassza ki azokat a felhasználókat, akik számára értesítéseket kíván küldeni, majd helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  Ismételje meg a 3 – 7. lépést a 2. lépésben kiválasztott összes eseményhez.

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a>Írjon megjegyzéseket a munkafolyamathoz az elvégzett változtatásokkal kapcsolatban.
Ha megjegyzéseket szeretne fűzni a munkafolyamathoz az elvégzett változtatásokkal kapcsolatban, kövesse az alábbi lépéseket.

1.  A bal oldali panelen kattintson a **Megjegyzések** gombra.
2.  Írja be a megjegyzéseit az **Adja meg a munkafolyamatra vonatkozó megjegyzéseket** mezőbe.
3.  Megjegyzések áttekintése. Miután hozzáadta a megjegyzéseket, nem módosíthatja azokat.
4.  Kattintson a **Hozzáadás** gombra a megjegyzések az **Előző megjegyzések** területre történő hozzáadásához.





