---
title: A munkaidő és a jelenlét-nyilvántartás kezelése a Retail alkalmazásban
description: Ez a témakör ismerteti az olyan helyzeteket, amelyek kezeléséhez használhatja a kiskereskedelmi munkaidő- és jelenlét-nyilvántartás kezelését a Dynamics 365 Commerce rendszerben.
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: cca5e3232450e75f931a621b278c134129fc745c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412980"
---
# <a name="time-and-attendance-management-in-retail"></a>A munkaidő és a jelenlét-nyilvántartás kezelése a Retail alkalmazásban

[!include [banner](includes/banner.md)]

Ez a témakör ismerteti az olyan helyzeteket, amelyek kezeléséhez használhatja a kiskereskedelmi munkaidő- és jelenlét-nyilvántartás kezelését a Dynamics 365 Commerce rendszerben.

## <a name="manage-worker-setup-and-scheduling"></a>Dolgozók elhelyezésének és ütemezésének kezelése

### <a name="initial-configuration"></a> Induló konfiguráció

- Futtassa a konfigurációs varázslót.
- Regisztrálja a dolgozókat időregisztrációs dolgozókként.

### <a name="plan-worker-schedules"></a>Tervezze meg a dolgozói beosztásokat

- Alkalmazzon profilokat a munkatervező segítségével. További információ: [Profil alkalmazása a munkatervezővel](https://technet.microsoft.com/library/aa551234.aspx).

A konfiguráció lépéseivel kapcsolatos további információért, lásd: [Munkaidő és jelenlét beállítása](https://technet.microsoft.com/library/aa496971.aspx).

### <a name="commerce-specific-configuration"></a>Kereskedelemspecifikus konfigurálás

- Engedélyezzen egy funkcionális profilt a Blokkolóórához azon dolgozók számára, akiknek lehetővé kívánja tenni az időregisztrációt. Kattintson a **Pénztár-funkcióprofilok** &gt; **Funkciók** &gt; **Pénztár idő regisztrációk** &gt; **Időregisztrációk engedélyezése** lehetőségre.
- Állítsa át a Pénztár (POS) engedélycsoportokat, hogy elérhetővé tegye a blokkolóóra bejegyzések megtekintése engedélyt. Ez az engedély lehetővé teszi, hogy a felhasználó megtekintse a bolt (Illetve más, a címjegyzék alapján a felhasználóhoz társítható boltok) dolgozóinak blokkolóóra regisztrációit. Ezt az engedélyt a vezető szerepkörű dolgozók számára ajánlott engedélyezni. Kattintson a **Pénztár-engedélycsoportok** &gt; **Blokkolóóra bejegyzéseinek megtekintése** gombra.

## <a name="register-time"></a>Idő regisztrálása

### <a name="cashier-and-non-cashier-time-registrations"></a>Pénztáros és nem a pénztáros időregisztrációk

- A Pénztáron:

    - Belépési műveletek:

        - Lépjen be egy nem pénztárgép-fiókkal kapcsolatos művelettel vagy új műszakkal.
        - Válassza ki a Blokkolóóra műveletet.
        - Válassza ki a kívánt műveletet:

            - Érkezéskori blokkolás
            - Pihenő
            - Ebédszünet
            - Távozáskori blokkolás

        <table>
        <thead>
        <tr>
        <th>Jelenlegi állapot:</th>
        <th>Elérhető műveletek</th>
        </tr>
        </thead>
        <tbody>
        <tr>
        <td>Érkezéskori blokkolás</td>
        <td>
        <ul>
        <li>Pihenő</li>
        <li>Ebédszünet</li>
        <li>Távozáskori blokkolás</li>
        </ul>
        </td>
        </tr>
        <tr>
        <td>Pihenő</td>
        <td>Érkezéskori blokkolás</td>
        </tr>
        <tr>
        <td>Ebédszünet</td>
        <td>Érkezéskori blokkolás</td>
        </tr>
        <tr>
        <td>Távozáskori blokkolás</td>
        <td>Érkezéskori blokkolás</td>
        </tr>
        </tbody>
        </table>

        [![Blokkolóóra állapotai](./media/timeclockstates.png)](./media/timeclockstates.png)

- Tekintse meg a konfigurációs üzenetet és igazolja, hogy a pillanatnyi tevékenység idő korrekt.
- Napló:

    - Kattintson a **Napló** gombra a blokkolóóra tevékenység megtekintéséhez.
    - Alkalmazzon időszűrőket a különböző időablakok kiválasztásához.
    - Ha több tárolási helyen dolgozik, az összes helyszínen rögzített időregisztrációját megtekintheti. Az üzletszűrő segítségével kiválaszthatja melyik üzlet időregisztrációit kívánja megtekinteni.

- Eltérő időzónák:

    - Ha az időt egy másik helyről nézi meg (a pénztáros naplóhoz vagy vezetői pozíció esetén a **Blokkolóóra bejegyzések megtekintése** opciót használva) és az adott hely másik időzónába esik, a megjelenített időpontok automatikusan az ön időzónájához igazodnak. Például, ön két üzlet vezetője. Az egyik Arizónában, a másik Nevadában található. Az arizonai üzlet pénztárosa beregisztrál a blokkolóórán reggel 9 órakor. Az adott időpontban Nevadában, reggel 8 óra van. Tehát, ha ön a nevadai üzletben tartózkodik és megnézi az időregisztrációkat, a regisztrált idő reggel 8 óraként lesz mutatva.

## <a name="view-worker-time-registrations"></a>Dolgozói munkaidő-nyilvántartás megtekintése

### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a>Dolgozói időregisztrációk megtekintése és szűrés üzlet vagy tevékenységtípus alapján

A Pénztáron:

- Válassza ki a **Blokkolóóra bejegyzéseinek megtekintése** opciót.
- Az összes olyan dolgozó időregisztrációját láthatja akik önnel azonos üzlethez vannak hozzárendelve.
- Az időregisztrációk szűréséhez használhatja a tevékenységtípus szerinti és az üzlet szerinti szűrőket.

## <a name="process-and-manage-time-registrations"></a>Időregisztrációk feldolgozása és kezelése

A Commerce felhasználója követi a munkafolyamatot, hogy kiszámolja, jóváhagyja, valamint áthelyezze az időregisztrációkat a bérlistára.

### <a name="primary-operations"></a>Elsődleges műveletek

- Számítás
- Jóváhagy
- Benyújtás a bérlistára

### <a name="other-common-operations"></a>Egyéb általános műveletek

- Szállítmány kicsekkolás
- Távollét regisztrálása

Az Idő és jelenlét regisztrációkkal kapcsolatos további tudnivalókat lásd: [Feldolgozási idő és jelenlét nyilvántartása](https://technet.microsoft.com/library/aa573180.aspx).


[!INCLUDE[footer-include](../includes/footer-banner.md)]