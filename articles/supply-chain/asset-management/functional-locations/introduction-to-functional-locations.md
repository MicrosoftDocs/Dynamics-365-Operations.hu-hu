---
title: A munkavégzési helyszínek bemutatása
description: Ez a cikk áttekintést nyújt az eszközkezelés működési helyéről.
author: johanhoffmann
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationEditSubLocations, EntAssetFunctionalLocationLookup, EntAssetFunctionalLocationRename, EntAssetFunctionalLocation
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2214"
- intro-internal
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a94b366dc725db3af01c156ae517a241213f7d52
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016043"
---
# <a name="introduction-to-functional-locations"></a>A munkavégzési helyszínek bemutatása

[!include [banner](../../includes/banner.md)]

 

Ez a cikk áttekintést nyújt az eszközkezelés működési helyéről. A munkavégzési helyszínek a technikai struktúra elemei (pl. egy rendszer funkcionális egységei). A munkavégzési helyszínek létrehozása hierarchikusan történik, és eszközök telepíthetők rájuk. A cég munkavégzési helyszíneinek beállítása a cég követelményeitől függ.

A munkavégzési helyszínek például a következőképpen használhatók:

- **Funkcionálisan** – A munkavégzési helyszínek lehetnek felhasználóalapúak, és használhatók a hasonló viselkedésű eszközök kezelésére.
- **Folyamathoz kapcsolódóan** – A munkavégzési helyszínek lehetnek munkafolyamat-alapúak.
- **Térbeli megoldásként** – A munkavégzési helyszín jelezhetnek földrajzi helyeket és helyszíneket.

Az Eszközkezelés minden munkavégzési helyszínt külön kezel. A munkavégzési helyszínek hasznos funkciókat kínálnak:

- Beállíthatók a munkavégzési helyszínek részletei.
- Beállíthatók az eszközök specifikációs követelményei.
- Beállíthatók a preventív és a reaktív karbantartás szekvenciái.
- Kezelhetők a telepített eszközök.
- Nyomon követhetők a telepített eszközökkel összekapcsolt aktív kérések és munkarendelések.
- Nyomon követhetők az eszközökön regisztrált hibák.
- Bármikor nyomon követhetők a munkavégzési helyszínnel összekapcsolt eszközök karbantartási költségei.

A munkavégzési helyszínekkel nyomon követhetők az eszközök kérelmekkel, a munkarendelésekkel, a hibaregisztrációkkal, a feltételek értékeléseivel, a termelésleállások regisztrálásával és az eszközszámláló regisztrálásával kapcsolatos részletei.

> [!NOTE]
> A költségek akkor is összekapcsolhatók minden hellyel, ha egy eszköz az életciklusa során különböző munkavégzési helyszíneken van telepítve. Ez azt jelenti, hogy az eszköz költségei mindig össze vannak kapcsolva azzal a munkavégzési helyszínnel, amelyen az eszköz az adott időpontban telepítve volt.

A munkavégzési helyszínek **nem** rugalmasak. Ez azt jelenti, hogy a helyek nem helyezhetők át a munkavégzési helyszín hierarchiájának beállítása után. 

A munkavégzési helyszínek hierarchiájának kialakítása után az eszközök telepítése a következő lépés. További információ: [Eszközök telepítése munkavégzési helyszínekre](../functional-locations/install-objects-on-functional-locations.md).

## <a name="all-functional-locations"></a>Összes munkavégzési helyszín

Válassza ki **az Eszközkezelés** \> **működési helyei** \> **minden funkcionális helyet,** hogy megnyíljön az Összes **funkcionális hely** listaoldal. Ezen az oldalon az össze munkavégzési helyszín, bizonyos rájuk vonatkozó információk láthatók. Ha csak az aktív munkavégzési helyszíneket szeretné megtekinteni, válassza az **Aktív munkavégzési helyszínek** lehetőséget. Ha csak azokat a munkavégzési helyszíneket szeretné megtekinteni, amelyekkel Önt dolgozóként kapcsolták össze, válassza a **Saját aktív munkavégzési helyszínek** lehetőséget. (Ez a kapcsolat a **Dolgozók** oldalon állítható be. További információ: [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md).)

A kiválasztott rekord részleteinek megtekintéséhez az **Összes munkavégzési helyszín** listaoldalon válasszon ki egy hivatkozást **Munkavégzési helyszín** oszlopban. A munkavégzési helyszín szerkesztéséhez kattintson a **Szerkesztés** gombra. A részletes nézetben a hellyel kapcsolatos részletes adatok láthatók. Ezenkívül a jobb oldalon elérhető a **Kapcsolódó információ** ablaktábla. Ezen az ablaktáblán a munkavégzési helyszín hierarchiája látható. A **Kapcsolódó információ** ablaktábla kinyitható és összecsukható.

A műveleti ablak gombjai lapokon vannak rendezve. A következő táblázat röviden leírja azokat a gombokat, amelyek az Eszközkezeléshez kötődnek.

| Gomb neve                         | Leírás                                                                                                                                  |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Szerkesztés                                | Váltás az oldal szerkesztésére és megtekintésére szolgáló üzemmód között.                                                                                         |
| Új                                 | Új munkavégzési helyszín létrehozása.                                                                                                            |
| Eltávolítás                              | A kijelölt munkavégzési helyszín törlése.                                                                                                     |
| Átnevezés                              | A kijelölt munkavégzési helyszín átnevezése.                                                                                                     |
| Munkavégzési helyszín szerkezetének másolása  | Átmásolja a munkavégzési helyszín hierarchiáját.                                                                                                      |
| Eszköz telepítése                       | Eszköz (alárendelt eszközökkel együttes) telepítése a munkavégzési helyszínen.                                                                        |
| Eszköz cseréje                       | Az eszközhierarchiát a munkavégzési helyszín másik eszközhierarchiájára cseréli.                                                         |
| Költségkontroll                        | A **Munkavégzési helyszín költségellenőrzése** oldal megnyitása, ahol költségszámítások végezhetők a kijelölt munkavégzési helyszínhez.                |
| Órakontroll                        | A **Munkavégzési helyszín órakontrollja** oldal megnyitása, ahol költségszámítások végezhetők a kijelölt munkavégzési helyszínhez.                |
| Eszközök                              | A **Minden eszköz** oldal megnyitása, ahol megtekinthető a kijelölt munkavégzési helyszínnel összekapcsolt eszközök listája.                      |
| Kérelmek                            | Az **Aktív kérelmek** oldal megnyitása, ahol megtekinthető a kijelölt munkavégzési helyszínnel összekapcsolt kérelmek listája.               |
| Munkarendelések                         | Az **Aktív munkarendelések** oldal megnyitása, ahol megtekinthető a kijelölt munkavégzési helyszínnel összekapcsolt munkarendelések listája.         |
| Hibák                              | A **Eszközhibák** oldal megnyitása, ahol megtekinthető a kijelölt munkavégzési helyszínnel összekapcsolt eszközhiba-regisztrációk listája. |
| Munkavégzési helyszín állapotának frissítése    | A kijelölt munkavégzési helyszín állapotának frissítése.                                                                                        |
| Életciklus-állapot naplója                 | A kijelölt munkavégzési helyszín állapotait megjelenítő napló megtekintése.                                                                        |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]