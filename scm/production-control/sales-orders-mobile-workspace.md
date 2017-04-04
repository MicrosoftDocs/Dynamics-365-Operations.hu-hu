---
title: "Értékesítési rendelések mobil munkaterület Microsoft Dynamics 365 műveletek app"
description: "Az értékesítési rendelések mobil munkaterület maradhat, ha naprakész bárhol a eladási rendeléseken és bármikor."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267134
ms.assetid: dbc6dc39-b535-42d3-9fbd-4724597388ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 851c53e1c53fb37488ed86e25e3ede83ca0541db
ms.lasthandoff: 03/31/2017


---

# <a name="sales-orders-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Értékesítési rendelések mobil munkaterület Microsoft Dynamics 365 műveletek app

Az értékesítési rendelések mobil munkaterület maradhat, ha naprakész bárhol a eladási rendeléseken és bármikor. 

<a name="prerequisites"></a>Előfeltételek
-------------

| Előfeltételek                                                         | Leírás                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Olvassa el a Microsoft Dynamics 365 műveletek mobil platform | [365 Dynamics műveletek mobil platform](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| 365 Dynamics műveletek                                          | Győződjön meg arról, hogy olyan környezetben, amely rendelkezik a Microsoft Dynamics 365 műveletek verzió 1611 használ, és a Microsoft Dynamics műveletek platform frissítése (November 2016) 3. |
| A gyorsjavítás KB 3215650                                                    | A gyorsjavítást a Microsoft Dynamics 365 műveletekhez biztosított munkaterületek engedélyezése.                                                                       |
| Mobil eszköz, amely a Dynamics 365 a műveletek alkalmazás telepítve van | Töltse le a mobil app store app műveletek esetében a Dynamics 365.                                                                                                      |

## <a name="overview"></a>Áttekintés
A mobil munkaterület éri el a Dynamics 365 műveletek alkalmazás, és lehetővé teszi minden eladási rendeléshez például rendelés állapota, a vevők kapcsolattartói adatainak és a rendelés elfogadója kapcsolati információkat kapcsolatos részletes információk megtekintése. A mobil munkaterületet biztosít azonnali információkra az értékesítési rendeléseket. Vevő, értékesítési rendelések megtekintése vagy az összes értékesítési rendelés megjelenítése, vagy egy meghatározott értékesítési rendelés adatainak megtekintése. A mobil munkaterület két ablakokban eladási rendelések mély elemzéséhez.

### <a name="view-all-sales-orders"></a>Összes értékesítési rendelés megjelenítése

Ebben a nézetben az összes értékesítési rendelések listájának megjelenítése.

-   A következő szűrők segítségével válassza ki a megtekinteni kívánt értékesítési rendelésekkel.
    -   Értékesítési rendelés keresése
    -   Vevői számla a kereséshez
    -   Vevő név szerinti keresés
    -   Keresési állapot szerint
    -   A kiadás állapot szerinti keresés
    -   Keresés létrehozásának dátuma és időpontja

<!-- -->

-   Miután kiválasztotta az értékesítési rendelések, bizonyos típusú rendelések adatait tekintheti meg. Pontosabban tekintheti meg:
    -   Vevő neve és címe adatai
    -   Különböző eladási rendelés dátumok, például a kért szállítási dátum és visszaigazolt szállítási dátum
    -   Rendelés elfogadója kapcsolattartási adatok
    -   Vevő kapcsolattartási adatai
    -   Rendeléssorok
    -   Hogyan és mikor szállított egy értékesítési rendelés megjelenítése szállítások

### <a name="view-orders-for-a-customer-"></a>A vevő ** rendelések megtekintése **

Ez a nézet vevőnként értékesítési rendelések listájának megjelenítése.

-   A következő szűrők segítségével megtekintheti a vevő rendeléseit.
    -   Keresés név alapján
    -   Partner keresése

<!-- -->

-   Miután kiválasztotta a vevő, tekintheti meg:
    -   Vevő neve és csoport
    -   Vevő kapcsolattartási adatai
    -   Vevői megrendelések és az értékesítési rendelések részletei:
        -   Vevő neve és címe adatai
        -   Különböző eladási rendelés dátuma
        -   Rendelés elfogadója kapcsolattartási adatok
        -   Vevő kapcsolattartási adatai
        -   Rendeléssorok
        -   Hogyan és mikor szállított értékesítési rendelések megjelenítése szállítások

## <a name="get-started"></a>Első lépések
Kövesse az alábbi lépéseket a mobileszközön a Mobil eladási rendelések munkaterület használatának megkezdéséhez.

1.  A mobil app-tárolóban töltse le és telepítse a Microsoft Dynamics 365 app műveletek esetében.
2.  Az alkalmazás indításához az eszközön.
3.  A Dynamics 365 URL-CÍMÉT adja meg.
4.  Adja meg a vállalat a bejelentkezéshez. Például, adja meg az **USMF**.
5.  Az első bejelentkezéskor kéri a felhasználónevet és jelszót a Microsoft Dynamics 365 költségszámla esetében. Adja meg hitelesítő adatait. A bejelentkezést követően a vállalat jelennek meg a rendelkezésre álló munkaterületek.

A mobil app munkaterületek megtekintéséhez először a kívánt munkaterületet kell közzétenni a vonatkozó műveletek app a Dynamics 365.

1.  Indítsa el a Dynamics 365 műveletekhez.
2.  Ugrás a **rendszer felügyeleti**&gt;**a telepítő**&gt;**Rendszerparaméterek**.
3.  Válassza ki **mobile alkalmazás kezelése**.
4.  Válassza ki a munkaterületen való közzétételéhez a mobil platform.
5.  Válassza ki **közzététele a munkaterület**.
6.  Frissítse az eszközt, és ellenőrizze a közzétett munkaterületek.

## <a name="view-information-about-sales-orders-for-a-customer"></a>A vevőhöz tartozó értékesítési rendelésekkel kapcsolatos információk megtekintése
1.  A mobileszközön válassza ki a **értékesítési rendelések** munkaterület.
2.  Válassza ki **a vevői rendelések megtekintése**.
3.  Használata ** fiók ** vagy ** Vevőnév ** keresse meg a kívánt vevőt az információt.
4.  Válassza ki a vevőt.
5.  Válassza ki **elérhetőségi adatok** vagy **értékesítési rendelések**.
6.  Ha **értékesítési rendelések** van jelölve, a vevőhöz tartozó értékesítési rendelések listája fog megjelenni.
7.  Válassza ki **az eladási rendelés**.
8.  Itt megtekintheti értékesítésirendelés-sorok, szállítások, vevők kapcsolattartói adatainak és rendelés elfogadója elérhetőségi adatait.




