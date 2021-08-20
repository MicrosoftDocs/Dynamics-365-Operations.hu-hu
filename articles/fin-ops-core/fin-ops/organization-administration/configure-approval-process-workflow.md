---
title: Jóváhagyási folyamatok konfigurálása munkafolyamatban
description: A következő eljárás segítségével állítsa be a jóváhagyási folyamat tulajdonságait.
author: ChrisGarty
ms.date: 01/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 998ee15d828feefb0a9691138ae8001331283d5b866386500f5cf5de48291b43
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756321"
---
# <a name="configure-approval-processes-in-a-workflow"></a>Jóváhagyási folyamatok konfigurálása munkafolyamatban

[!include [banner](../includes/banner.md)]

A következő eljárás segítségével állítsa be a jóváhagyási folyamat tulajdonságait.

A munkafolyamat-szerkesztő jóváhagyási folyamatának beállításához kattintson a jobb gombbal a jóváhagyási elemre, és kattintson **Tulajdonságok** lapon a **Tulajdonságok** űrlap megnyitásához.

## <a name="name-the-approval-process"></a>A jóváhagyási munkafolyamat elnevezése

Kövesse ezeket a lépéseket annak érdekében, hogy nevet adjon a jóváhagyási munkafolyamatnak.

1. A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2. Írja be a jóváhagyási munkafolyamat egyedi nevét a **Név** mezőbe.

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a>Adja meg, hogy mikor intézkedjen a rendszer automatikusan a dokumentum tekintetében

Beállíthatja, hogy a rendszer automatikusan intézkedjen arról a dokumentumról, amely megfelel a megadott feltételeknek. A rendszer például 100 USD értéknél kisebb végösszeggel rendelkező költségjelentések jóváhagyására jogosult. Végezze el az alábbi lépéseket a dokumentum tekintetében történő intézkedés idejének meghatározásához.

1. A bal oldali panelen kattintson az **Automatikus műveletek** gombra.
2. Jelölje ki az **Automatikus műveletek engedélyezése** jelölőnégyzetet.
3. Kattintson a **Feltétel hozzáadása** parancsra.
4. Feltétel megadása.
5. Ha szükséges, adjon meg további feltételeket.
6. Ha ellenőrizni szeretné, hogy a megadott feltételek helyesen vannak-e konfigurálva, végezze el a következő lépéseket:

    1. Kattintson a **Teszt** elemre a **Munkafolyamati feltétel tesztelése** űrlap megnyitásához.
    2. Válasszon ki egy bejegyzést a képernyő **Feltétel érvényesítése** területén.
    3. Kattintson a **Teszt** gombra. A rendszer értékeli a bejegyzést, annak érdekében, hogy meghatározza, hogy a meghatározott feltételeknek megfeleljen-e.
    4. Kattintson az **OK** vagy a **Mégse** lehetőségre a **Tulajdonságok** űrlapra történő visszalépéshez.

7. Válassza ki az **Automatikus befejezési művelet** listából, hogy milyen intézkedéseket kell a rendszernek végrehajtania a dokumentum tekintetében.

## <a name="specify-when-notifications-are-sent"></a>Az értesítések küldési idejének meghatározása

Értesítéseket küldhet a felhasználóknak a dokumentum jóváhagyása, elutasítása, delegálása vagy eszkalálása, illetve változás kérése esetén. Végezze el a következő lépéseket, annak meghatározása érdekében, hogy mikor és kinek küldje el a rendszer az értesítéseket.

1. A bal oldali panelen kattintson az **Értesítések** gombra.
2. Jelölje be a jelölőnégyzetet azon eseményekhez, amelyekhez ki kell küldeni az értesítéseket:

    - **Delegálás** – amikor jóváhagyás céljából a dokumentumot egy másik felhasználóhoz rendelték hozzá.
    - **Eszkalálás** – Ha a kijelölt felhasználó nem intézkedett a dokumentummal kapcsolatban a megadott idő alatt.
    - **Jóváhagyás** – amikor egy dokumentumot jóváhagytak.
    - **Elutasítás** – amikor egy dokumentumot elutasítottak.
    - **Változtatás kérése** – amikor a hozzárendelt felhasználó kérte egy már elküldött dokumentum módosítását.

3. Jelölje ki a sort a 2. lépésben választott eseményhez.
4. Kattintson az **Értesítés szövege** lapra.
5. A szövegmezőbe írja be az értesítés szövegét.
6. Ha személyre szeretné szabni a szöveget, illesszen be helyőrzőket, amelyek helyére a megfelelő adatok kerülnek akkor, amikor azok megjelennek a felhasználók számára. Végezze el a következő lépéseket a helyőrzők beillesztéséhez:

    1. Jelölje ki az egérrel azt a helyet a szövegmezőben, ahol meg szeretné jeleníteni a helyőrzőt.
    2. Kattintson a **Helyőrző beszúrása** lehetőségre.
    3. A megjelenő listában válassza ki a beilleszteni kívánt helyőrzőt.
    4. Kattintson a **Beszúrás** lehetőségre.

7. Az értesítések fordításainak hozzáadásához kattintson a **Fordítások** lehetőségre. A megjelenő űrlapon tegye a következőket:

    1. Kattintson a **Hozzáadás** parancsra.
    2. A megjelenő listában válassza ki a megírandó szöveg nyelvét.
    3. Írja be a szöveget az **Lefordított szöveg** mezőbe.
    4. A szöveg testreszabásához illesszen be helyőrzőket.
    5. Kattintson a **Bezárás** gombra.

8. Kattintson az **Átvevő** lapra.
9. Határozza meg az értesítések címzettjeit. Válasszon ki egy lehetőséget a következő táblázatban, majd ezt követően végezze el a további lépéseket a beállításhoz, mielőtt továbblép a 10. lépésre.

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
    <td><strong>Résztvevő</strong></td>
    <td>Egy adott csoporthoz vagy szerephez hozzárendelt felhasználók</td>
    <td>
    <ol>
    <li>Miután kijelölte a <strong>Résztvevő</strong> lehetőséget, kattintson a <strong>Szerepköralapú</strong> lapra.</li>
    <li>A <strong>Résztvevő típusa</strong> listában jelölje ki azt a csoport- vagy szerepkörtípust, amely számára értesítést kíván küldeni.</li>
    <li>A <strong>Résztvevő</strong> listáján jelölje ki a csoportot vagy szerepkört, amely számára értesítést kíván küldeni.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>Munkafolyamat felhasználója</strong></td>
    <td>Az aktuális munkafolyamatban részt vevő felhasználók</td>
    <td>
    <ol>
    <li>Miután kijelölte a <strong>Munkafolyamat felhasználója</strong> lehetőséget, kattintson a <strong>Munkafolyamat felhasználója</strong> lapra.</li>
    <li>A <strong>Munkafolyamat felhasználója</strong> listában jelölje ki a munkafolyamatban részt vevő felhasználót.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>Felhasználó</strong></td>
    <td>Meghatározott felhasználók</td>
    <td>
    <ol>
    <li>Miután kijelölte <strong>Felhasználó</strong> lehetőséget, kattintson a <strong>Felhasználó</strong> fülre.</li>
    <li>Válassza ki azokat a felhasználókat, akik számára értesítéseket kíván küldeni, majd helyezze át ezeket a felhasználókat a <strong>Kijelölt felhasználók</strong> listába.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

10. Ismételje meg a 3–9. lépést a 2. lépésben kiválasztott összes eseményhez.

## <a name="specify-a-final-approver"></a> A végső jóváhagyó megadása

A végső jóváhagyó kijelölhető olyan esetekre, amikor a jóváhagyó az a személy, aki a dokumentumot jóváhagyásra elküldte, és a „feladó általi jóváhagyás tiltása” van használatban. Kövesse az alábbi lépéseket a végső jóváhagyó megadásához.

1. A munkafolyamat-szerkesztőben kattintson a jobb gombbal a jóváhagyási elemre, és válassza a **Tulajdonságok** lapon a **Tulajdonságok** űrlap megnyitásához.
2. A bal oldali panelen kattintson az **Speciális beállítások** gombra.
3. Jelölje be a **Végső jóváhagyó használata** jelölőnégyzetet.
4. Válassza ki a listából, hogy ki legyen a végső jóváhagyó.

## <a name="set-a-time-limit"></a>Időkorlát beállítása

Kövesse az alábbi lépéseket, ha a jóváhagyási folyamatot egy megadott időn belül be kell fejezni.

> [!NOTE]
> Az ezen lépésekben kiválasztott beállítások felülbírálják az egyes jóváhagyási lépések esetében a **Hozzárendelés** és az **Eszkaláció** pontokban megadottakat.

1. A bal oldali panelen kattintson az **Speciális beállítások** gombra.
2. Válassza ki a **A munkafolyamat-elem időkorlátjának beállítása** **elem** jelölőnégyzetet.
3. Az **Időtartam** mezőben adja meg, hogy mikor kell végrehajtani a jóváhagyási folyamatot. Válasszon a következő lehetőségek közül:

    - **Óra** – Adja meg, hogy hány órán belül kell végrehajtani a jóváhagyási folyamatot. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Nap** – Adja meg, hogy hány napon belül kell végrehajtani a jóváhagyási folyamatot. Ezt követően válassza ki a szervezet által használt naptárat, majd adja meg a szervezet munkahetének adatait.
    - **Hét** – Adja meg, hogy hány héten belül kell végrehajtani a jóváhagyási folyamatot.
    - **Hónap** – Válassza ki, hogy melyik hét mely napjáig kell befejezni a jóváhagyási folyamatot. Kérheti például, hogy a hónap harmadik péntekéig végre kelljen hajtani a jóváhagyási folyamatot.
    - **Év** – Válassza ki, hogy melyik hónap melyik hetének mely napjáig kell befejezni a jóváhagyási folyamatot. Kérheti például, hogy december harmadik hetének péntekéig végre kelljen hajtani a jóváhagyási folyamatot.

4. Ha lejár az időkorlát, a rendszer intézkedik a dokumentummal kapcsolatban. Válassza ki a **Művelet** listából, hogy milyen műveletet kell a rendszernek végrehajtania.

## <a name="specify-which-actions-are-available-to-the-user"></a>Annak megadása, hogy mely műveletek érhetők el a felhasználó számára.

Ha egy dokumentum hozzá van rendelve egy felhasználóhoz jóváhagyásra, a felhasználónak intézkednie kell a dokumentumról. Végezze el az alábbi lépéseket annak meghatározásához, hogy mely műveleteket végezhet el a felhasználó az elküldött dokumentumon.

1. A bal oldali panelen kattintson az **Speciális beállítások** gombra.
2. Ha azt szeretné, hogy a felhasználó jóváhagyhassa a dokumentumot, jelölje be a **Jóváhagyás** jelölőnégyzetet.
3. Ha azt szeretné, hogy a felhasználó elutasíthassa a dokumentumot, jelölje be az **Elutasítás** jelölőnégyzetet.
4. Ha azt szeretné, hogy a felhasználó kérhesse a dokumentum módosítását, jelölje be a **Változtatás kérése** jelölőnégyzetet.
5. Jelölje be a **Delegálás** jelölőnégyzetet, ha a felhasználó jóváhagyásra hozzárendelheti a dokumentumot egy másik felhasználóhoz.

> [!NOTE]
> A **Műveletek végrehajtásának engedélyezése az Enterprise Portalon** munkalistájából jelölőnégyzet elavult.

## <a name="configure-the-approval-steps"></a> Jóváhagyási lépések konfigurálása

Egy jóváhagyási eljárás jóváhagyási lépésekből áll. Az alábbi eljárással lépéseket adhat hozzá a jóváhagyási folyamathoz, valamint beállíthatja a lépéseket.

1. A munkafolyamat-szerkesztőben kattintson duplán a jóváhagyási folyamatra. A munkafolyamat-szerkesztő megjeleníti a jóváhagyási eljárás lépéseit.
2. Jóváhagyási lépés hozzáadásához húzza a **Munkafolyamat-elemek** lehetőséget a vászonra.
3. A jóváhagyási lépés konfigurálása: [Jóváhagyási lépések konfigurálása munkafolyamatban](configure-approval-step-workflow.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]