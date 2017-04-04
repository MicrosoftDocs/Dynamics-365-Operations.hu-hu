---
title: "Készlet aktuális mobil munkaterület Microsoft Dynamics 365 műveletek app"
description: "A készlet aktuális mobil munkaterület segítségével szerezhet a fenntartott és a rendelkezésre álló készlet mobil végértékeket bármikor és bárhol."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267094
ms.assetid: 85058f55-e566-40e2-9234-42d3e4fe5ff6
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 2ad48765528e1d1c6e7c90417b54a248ec79f546
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-on-hand-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Készlet aktuális mobil munkaterület Microsoft Dynamics 365 műveletek app

A készlet aktuális mobil munkaterület segítségével szerezhet a fenntartott és a rendelkezésre álló készlet mobil végértékeket bármikor és bárhol. 

<a name="prerequisites"></a>Előfeltételek
-------------

| Előfeltételek                                                         | Leírás                                                                                                                                        |
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Olvassa el a Microsoft Dynamics 365 műveletek mobil platform | [365 Dynamics műveletek mobil platform](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                   |
| 365 Dynamics műveletek                                          | Olyan környezetben, amely a Microsoft Dynamics 365 1611 műveletek verziójához és a Microsoft Dynamics műveletek platform frissítése (November 2016) 3 |
| A gyorsjavítás KB 3215650                                                    | Telepítse a gyorsjavítást a munkaterületek, amelyeket a Microsoft Dynamics 365 műveletek engedélyezéséhez.                                       |
| Mobil eszköz, amely a Dynamics 365 a műveletek alkalmazás telepítve van | Töltse le a mobil app store app műveletek esetében a Dynamics 365.                                                                           |

## <a name="introduction"></a>Bevezetés
Általában cégek még több szállítások és bevételezések készlet minden nap. Ezeket a mozgásokat folyamatosan a raktárkészlet állapotának módosítása. A készlet aktuális mobil munkaterület lehetővé teszi a több vállalatot érintő aktuális készlet állapota látható, hogy kaphatnak a tetszés szerinti a mobileszközön szereplő adatok a legújabb végértékeket. Függetlenül attól, hogy a raktár, beszerzési, értékesítési, gyártási vagy kezelés működik, vagy más szerepkörökkel rendelkeznek bárhol és bármikor elérheti az aktuális készlet adatokat. A mobil munkaterület létesítmények lehetővé teszi az azonnali információkra az aktuális állapotát, és lehetővé teszi az aktuális készlet létesítmények, anyagi aktuális foglalások és korlátozás nélküli kijelentést az aktuális készlet megtekintése. Adjon meg a cikkszámok és lekérdezés az aktuális készlet, és végre keresést szűrt készleten levő termékek vagy változatok is. A mobil munkaterület, az alábbi szolgáltatásokat nyújtja:

-   Kereshet terméktípus és termék neve termékek keresése a raktárkészlet állapotának megtekintése.
-   A kijelölt termékek a következő információkat tekintheti meg:
    -   Egy webhely aktuális készlet
    -   Az aktuális készlet raktáranként
    -   Az aktuális készlet raktár szerint
    -   Az aktuális készlet tételenként (a kötegelt által szabályozott termékek)
    -   Az aktuális készlet készlet állapot szerint

<!-- -->

-   Termék készlet az alábbi módon jelenik meg:
    -   Által a fizikai készlet (Ez a nézet a teljes munkamennyiségre vonatkozik.)
    -   Által lefoglalt fizikai (ebben a nézetben a fenntartott összeg jelöli.)
    -   Által elérhető fizikai (a nézet jelöli rendelkezésre álló összeg fenntartások nem rendelkezik.)

## <a name="get-started"></a>Első lépések
Ismerkedés a mobileszközön:

1.  A mobil app-tárolóból töltse le és telepítse a Microsoft Dynamics 365 app műveletek esetében.
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

## <a name="view-the-onhand-inventory-for-a-product"></a>A termék onhand készletének megjelenítése
1.  A mobileszközön válassza ki a **– az aktuális készlet** munkaterület.
2.  Válassza ki **ellenőrizze az aktuális cikk**. A kapcsolat nélküli használatra app betöltött termékek listájának megtekintéséhez. Alapértelmezés szerint 50 elemeket tölti be, de módosíthatja ezt a számot. További tudnivalókért tanulmányozza a előre olvasási kézikönyvet.
3.  Ha a cikk nem szerepel a listán, jelölje be a **keres több** 365 Dynamics online keres műveletek végrehajtásához. Terméktípus keresés, vagy térjünk át a keresés terméknév.
4.  Válasszon ki egy terméket. Ha a cikk egy képet, a kép jelenik meg.
5.  A raktárkészlet állapotának megjelenítéséhez a következő lehetőségek közül választhat:
    -   Aktuális készlet megtekintése helyenként
    -   Aktuális készlet megjelenítése raktáranként
    -   Aktuális készlet megtekintése raktár szerint
    -   Aktuális készlet megtekintése tételenként (a kötegelt által szabályozott termékek)
    -   Nézet az aktuális készlet állapot szerint

    Termék készlet az alábbi módon jelenik meg:
    -   Által a fizikai készlet (Ez a nézet a teljes munkamennyiségre vonatkozik.)
    -   Által lefoglalt fizikai (ebben a nézetben a fenntartott összeg jelöli.)
    -   Által elérhető fizikai (ebben a nézetben a rendelkezésre álló összeget, amelynek fenntartások jelöli.)




