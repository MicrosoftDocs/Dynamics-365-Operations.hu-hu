---
title: Munkafolyamat-tulajdonságok konfigurálása
description: Ez a témakör bemutatja, hogyan kell konfigurálni a munkafolyamat különböző tulajdonságait.
author: ChrisGarty
manager: AnnBe
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3cb5dc59373b7af76fffa1b1c59728c84dfb5fb
ms.sourcegitcommit: fd62ab3d399b0d6ea0d362f1d403a300e84a576d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "5067623"
---
# <a name="configure-workflow-properties"></a>Munkafolyamat-tulajdonságok konfigurálása

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan kell konfigurálni a munkafolyamat különböző tulajdonságait.

A munkafolyamat tulajdonságainak beállítására, a munkafolyamat-szerkesztő megnyitása a munkafolyamat. Kattintson a munkafolyamat-szerkesztő vásznára, majd ezt követően kattintson a **Tulajdonságok** megnyitásához a **Tulajdonságok** képernyőn. A következő eljárások segítségével beállíthatja a munkafolyamat különféle tulajdonságait.

## <a name="name-the-workflow"></a>A munkafolyamat elnevezése

A következő lépések segítségével elnevezheti a munkafolyamatot.

1. A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2. A **Név** mezőbe írja be a munkafolyamat egyedi nevét. Például, ha létrehoz egy beszerzési igénylési munkafolyamatot minden működési országhoz/régióhoz, a beszerzési igénylés munkafolyamatának a **Beszerzési igénylések Dánia** vagy **Beszerzési igénylések Spanyolország** nevet adhatja.

## <a name="specify-the-workflow-owner"></a>A munkafolyamat tulajdonosának meghatározása

A munkafolyamat tulajdonosa az a személy, aki az adott munkafolyamatot kezeli és karbantartja. A következő lépések segítségével megadhatja a munkafolyamat tulajdonosát.

1. A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2. Válassza ki a munkafolyamatot kezelő személy nevét a **Tulajdonos** listából.

## <a name="select-an-email-template"></a>E-mail sablon kiválasztása

Végezze el az alábbi lépéseket azon e-mail sablon kiválasztásához, amelyet a munkafolyamattal kapcsolatos értesítések létrehozására használ.

1. A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2. Válasszak ki a sablont az **E-mail sablon munkafolyamat-értesítésekhez** listáján.

## <a name="enter-instructions-for-users"></a>Utasítások megadása felhasználók számára

Utasításokat adhat meg azon felhasználók számára, akik a dokumentumokat feldolgozásra és jóváhagyásra továbbítják. Ezeket a felhasználókat *létrehozók* néven is nevezik. Például, ha Ön egy beszerzési igénylési munkafolyamatot hoz létre, akkor utasításokat ad meg. Ezeket az utasításokat azok a felhasználók tekinthetik meg, akik a **Beszerzési igénylések** képernyőn beszerzési igényléseket adnak meg. Az útmutatás megtekintéséhez, a létrehozó a munkafolyamat üzenetsorán található ikonra kattint. A következő lépések segítségével utasításokat adhat meg a felhasználók számára.

1. A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2. Írja be az utasításokat a **Küldési utasítások** mezőbe.
3. Az utasítások testreszabásához, helyőrzőket illeszthet be. A helyőrzők helyére a megfelelő adatok kerülnek, amikor az utasítások megjelennek a felhasználók számára. Végezze el a következő lépéseket a helyőrzők beillesztéséhez:

    1. Kattintson a **Küldési utasítások** mezőre a helyőrző helyének meghatározásához.
    2. Kattintson a **Helyőrző beszúrása** lehetőségre.
    3. A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.
    4. Kattintson a **Beszúrás** lehetőségre.

4. Az utasítások fordításainak hozzáadásához, végezze el a következő lépéseket:

    1. Kattintson a **Fordítások** lehetőségre.
    2. A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.
    3. A megjelenő listában válassza ki a szöveg nyelvét, amelyen írni fogja azt.
    4. Írja be a szöveget a **Lefordított szöveg** mezőbe.
    5. A szöveg testreszabásához, illesszen be helyőrzőket. A helyőrző megadásával kapcsolatos további tudnivalókért lásd a 3. lépést.
    6. Kattintson a **Bezárás** gombra.

> [!NOTE]
> A helyőrzőket nem lehet másolás és beillesztés segítségével hozzáadni, mert a célinformációk nem megfelelően lesznek beillesztve. Helyőrzők hozzáadására használja a felületet.

## <a name="specify-when-this-workflow-is-used-through-activation-conditions"></a>Adja meg, hogy mikor használja ezt a munkafolyamatot aktiválási feltételeken keresztül

Több, ugyanazon a munkafolyamat-típuson alapuló munkafolyamatot is megadhat. Ha több olyan munkafolyamata van, amelyeknek alapja ugyanaz a típus, az aktiválási feltételekkel meg kell adnia, hogy mikor szeretné a munkafolyamatot használni. Ha az aktiválási feltételek nem teljesülnek, akkor a rendszer az alapértelmezett munkafolyamatot használja. Hasonlóképpen, ha egy munkafolyamat-típushoz csak egy munkafolyamat-konfiguráció van definiálva, akkor a munkafolyamat-konfiguráció az aktiválási feltételektől függetlenül használva lesz.

Például, ha létrehoz egy beszerzési igénylési munkafolyamatot minden működési országhoz/régióhoz, például a beszerzési igénylés Beszerzési igénylések Dánia vagy Beszerzési igénylések Spanyolország munkafolyamatot a következő feltételekkel:

- A Beszerzési igénylés Dánia akkor használandó, amikor: ország/régió = DK.
- A Beszerzési igénylés Spanyolország akkor használandó, amikor: az ország/régió = ES.

A következő lépések segítségével megadhatja, hogy mikor szeretné használni az éppen konfigurált munkafolyamatot.

1. A bal oldali panelen kattintson az **Aktiválás** gombra.
2. Válassza ki a **A munkafolyamat futtatási feltételeinek beállítása** jelölőnégyzetet.
3. Kattintson a **Feltétel hozzáadása** parancsra.
4. Feltétel megadása.
5. Adja meg a további szükséges feltételeket.
6. Futtassa végig a munkafolyamaton keresztül néhány célrekord használatával, és ellenőrizheti, hogy a feltétel helyesen szerepel-e, és ki vannak-e zárva a rekordok.

## <a name="specify-when-notifications-are-sent"></a>Az értesítések küldési idejének meghatározása

Amikor elküldenek egy dokumentumot feldolgozásra, létrejön egy munkafolyamat-példány. Értesítést a felhasználóknak olyankor küldhet, amikor a munkafolyamat-példányok (melyeknek alapja a munkafolyamat) elkezdődtek, elkészültek, megszakították őket, vagy hiba miatt leálltak. A következő lépések segítségével megadhatja, hogy mikor küldjön a rendszer értesítéseket.

1. A bal oldali panelen kattintson az **Értesítések** gombra.
2. Jelölje be a jelölőnégyzetet minden olyan eseményhez, amely az előidézi értesítéseket:

    - **Elindítva** – Értesítések küldése, ha a rendszer elkezdi a munkafolyamat-példányt.
    - **Leállítva** – Értesítések küldése, ha hiba miatt leáll a munkafolyamat-példány.
    - **Befejeződött** – Értesítések küldése, ha befejeződött a munkafolyamat-példány.
    - **Helyreállíthatatlan** – Értesítések küldése, ha helyreállíthatatlan hiba miatt leáll a munkafolyamat-példány.
    - **Megszakítva** – Értesítések küldése, ha megszakították a munkafolyamat-példányt.

3. Jelölje ki a sort a 2. lépésben választott eseményhez.
4. Az **Értesítési szöveg** lapon, írja be az értesítés szövegét.
5. A szöveg testreszabásához, illesszen be helyőrzőket. A helyőrzők helyére a megfelelő adatok kerülnek, amikor a szöveg megjelenik a felhasználók számára. Végezze el a következő lépéseket a helyőrzők beillesztéséhez:

    1. Kattintson a mezőben oda, ahol meg szeretné jeleníteni a helyőrzőt.
    2. Kattintson a **Helyőrző beszúrása** lehetőségre.
    3. A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.
    4. Kattintson a **Beszúrás** lehetőségre.
    5. Egy gyakori **Értesítés szövege** helyőrző, melyet létrehoznak: „Utolsó jegyzetek: %Workflow.Last note%”, melly az előző lépés megjegyzéseit jelenít meg.

6. A szöveg fordításainak hozzáadásához, végezze el a következő lépéseket:

    1. Kattintson a **Fordítások** lehetőségre.
    2. A megjelenő oldalon kattintson a **Hozzáadás** lehetőségre.
    3. A megjelenő listában válassza ki a szöveg nyelvét, amelyen írni fogja azt.
    4. Írja be a szöveget a **Lefordított szöveg** mezőbe.
    5. A szöveg testreszabásához, illesszen be helyőrzőket. A helyőrző megadásával kapcsolatos további tudnivalókért lásd a 5. lépést.
    6. Kattintson a **Bezárás** gombra.

7. A **Címzett** lapon, a következő beállításokkal adja meg, határozza meg, hogy kik kaphatnak értesítéseket.

    <table>
    <thead>
    <tr>
    <th>Lehetőség</th>
    <th>Ezeknek a felhasználóknak küldött értesítések</th>
    <th>Az értesítések küldéséhez, végezze el a következő lépéseket</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Résztvevő</td>
    <td>Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</td>
    <td>
    <ol>
    <li>A <strong>Címzett</strong> lapon, kattintson a <strong>Résztvevő</strong> lehetőségre.</li>
    <li>A <strong>Szerepköralapú</strong> lapon, a <strong>Résztvevő típusa</strong> listán, válassza ki a csoport vagy a szerep típusát, amely számára értesítéseket kíván küldeni.</li>
    <li>A <strong>Résztvevő</strong> listáján jelölje ki a csoportot vagy szerepkört, amely számára értesítést kíván küldeni.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Munkafolyamat felhasználója</td>
    <td>A munkafolyamatban résztvevő felhasználók</td>
    <td>
    <ol>
    <li>A <strong>Címzett</strong> lapon, kattintson a <strong>Munkafolyamat felhasználója</strong> lehetőségre.</li>
    <li>A <strong>Munkafolyamat-felhasználó</strong> lapon található <strong>Munkafolyamat-felhasználó</strong> listából, jelöljön ki a munkafolyamat egy résztevevőjét.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Felhasználó</td>
    <td>Meghatározott felhasználók</td>
    <td>
    <ol>
    <li>A <strong>Címzett</strong> lapon, kattintson a <strong>Felhasználó</strong> lehetőségre.</li>
    <li>A <strong>Felhasználók</strong> lapon található <strong>Rendelkezésre álló felhasználók</strong> lista az összes felhasználót tartalmazza. Válassza ki azokat a felhasználókat, akik számára értesítéseket kíván küldeni, majd helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listájára.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. Ismételje meg a 3 – 7. lépést a 2. lépésben kiválasztott összes eseményhez.

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a>Írjon megjegyzéseket a munkafolyamathoz az elvégzett változtatásokkal kapcsolatban.

Ha megjegyzéseket szeretne fűzni a munkafolyamathoz az elvégzett változtatásokkal kapcsolatban, kövesse az alábbi lépéseket.

1. A bal oldali panelen kattintson a **Megjegyzések** gombra.
2. Írja be a megjegyzéseit az **Adja meg a munkafolyamatra vonatkozó megjegyzéseket** mezőbe.
3. Megjegyzések áttekintése. Miután hozzáadta a megjegyzéseket, nem módosíthatja azokat.
4. Kattintson a **Hozzáadás** gombra a megjegyzések az **Előző megjegyzések** területre történő hozzáadásához.
