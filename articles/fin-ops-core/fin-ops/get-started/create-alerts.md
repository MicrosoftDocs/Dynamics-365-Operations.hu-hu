---
title: Figyelmeztetési szabályok létrehozása
description: Ez a témakör a figyelmeztetések kapcsolatban tartalmaz tájékoztatást, és ismerteti, hogyan kell létrehozni egy figyelmeztetésszabályt, hogy értesítést kapjon például az olyan eseményekről, mint az elérkező dátumok vagy bizonyos módosítások.
author: tjvass
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: c37ddc52ef576a15dd35cc155e99821c74631a46
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180714"
---
# <a name="create-alert-rules"></a>Figyelmeztetési szabályok létrehozása

[!include [banner](../includes/banner.md)]

## <a name="getting-started"></a>Első lépések

Mielőtt figyelmeztetési szabályokat állítana be, döntse el, mikor vagy milyen helyzetben szeretne figyelmeztetést kapni. Ha tudja, mely eseményről szeretne értesítést kapni, keresse meg azt az oldalt, amelyen az eseményt előidéző adat megtalálható. Az esemény lehet egy elérkező dátum vagy egy bizonyos módosítás. Ezért meg kell találni a lapot, ahol a dátum meg van adva, vagy ahol megjelenik a módosuló mező vagy a létrehozott új rekord. Amint birtokában van ennek az adatnak, létrehozhatja az értesítési szabályt.

Egy figyelmeztetési szabály létrehozása esetén meg kell adni a feltételeket, amelyek teljesülése esetén figyelmeztetés jelenik meg. A feltételek tulajdonképpen nem mások, mint meghatározott körülmények között mindig bekövetkező események. Ha egy esemény bekövetkezik, a rendszer a megadott feltételek szerint megkezdi az ellenőrzést.

## <a name="events"></a>Események

A figyelmeztetési szabályt kiváltó esemény lehet egy elérkező dátum vagy egy bizonyos módosítás. Az események kiváltói meghatározhatók a **Figyelmeztetés feltétele** gyorslapján a **Figyelmeztetési szabály létrehozása** párbeszédpanelnek. Az adott mezőhöz rendelkezésre álló események a kiválasztott kiváltótól függően változnak.

Ha például egy figyelmeztetési szabályt állít be a **Kezdő dátum** mezőhöz, a határidős események megfelelőek. Emiatt **a határidő** eseménytípus elérhető a mező esetében. Azonban a **Költséghely** és hasonló mezőkhöz a határidős események nem megfelelők. Emiatt **a határidő** eseménytípus nem érhető el. Ehelyett a **megváltozott** eseménytípus érhető el.

## <a name="event-types"></a>Eseménytípusok

Három típusú esemény fordulhat elő:

- **Létrehozás típusú és törlés típusú események** – ezeket az események figyelmeztetést váltanak ki, ha a rekord létrehozása vagy törlése történik.
- **Frissítés típusú események** – Ezek az események figyelmeztetést generálnak, ha egy adott mezőben lévő adat megváltozik.
- **Határidő típusú események** – Ezek az események riasztást indítanak, amikor dátum érkezik.
    
A bekövetkező változásokat a felhasználó kezdeményezheti. Például egy felhasználó módosítja a beszerzési rendelés szállítási dátumát. Alternatívaként a változások folyamatok részeként is előfordulhatnak. Például az **Állapot** mező egy oldalon a rendszerben folyó különféle műveletek életciklusát tükrözi.

## <a name="conditions"></a>Feltételek

A **Figyelmeztetés időszaka** gyorslapján a **Riasztási szabály létrehozása** párbeszédpanelnek használhat feltételeket, amelyek megszabják, mikor kap riasztást az eseményekről.

Megadhatja például, hogy a rendszer figyelmeztesse, amikor a beszerzési rendelések állapota megváltozik, de csak akkor, ha az állapot megfelel bizonyos feltételeknek. Különösen az a fontos, hogy figyelmeztetést szeretne kapni, ha egy beszerzési rendelés állapota átvált **Bevételezett** állapotra. Ez az állapotmódosítás a figyelmeztetést kiváltó esemény.

Ezután el kell döntenie, mely beszerzési rendelésekről szeretne figyelmeztetést kapni. Például a következő lehetőségek egyikét választhatja: Ezek a beállítások adják meg a figyelmeztetési szabályhoz tartozó feltételeket.

- **Aktuális kiválasztott rekord** – megjelenik egy figyelmeztetés, ha egy adott beszerzési rendelés állapota átvált **Beérkezett** értékre.
- **Összes rekord** – Figyelmeztetés érkezik, amikor a beszerzési rendelés állapota az aktív oldalnézet egy elemére módosul. Használhatja a speciális szűrést, amely elérhető az oldalon, meghatározott rekordkészletre vonatkozó szabályok létrehozásához. Például létre tud hozni egy figyelmeztetést, amelyet egy adott vevőcsoportba tartozó vevők minden beszerzési rendelése kivált.
    
## <a name="expiry-of-rule"></a>Szabály lejárata

A **Figyelmeztetés vége** gyorslapján a **Riasztási szabály létrehozása** párbeszédpanelnek megadhatja, hogy meddig legyen aktív a figyelmeztetési szabály.

## <a name="alert-contents"></a>Figyelmeztetés tartalma

A **Figyelmeztetés módja** gyorslapján a **Figyelmeztetési szabály létrehozása** párbeszédpanelnek megadhatja a figyelmeztető üzenetek által használandó tárgy szövegét és üzenet szövegét.

## <a name="user-id"></a>Felhasználói azonosító

A **Figyelmeztetés módja** gyorslapján a **Figyelmeztetési szabály** létrehozása párbeszédpanelnek megadhatja, hogy melyik felhasználó kapja meg a figyelmeztető üzeneteket. A felhasználói azonosító alapértelmezés szerint be van jelölve. Ez a beállítás a szervezeti rendszergazdákra korlátozódik.

## <a name="create-an-alert-rule"></a>Figyelmeztetési szabály létrehozása

1. Nyissa meg a figyelni szándékozott adatot tartalmazó oldalt.
2. A műveleti ablakban a **Beállítások** lapon a **Megosztás** csoportban válassza az **Figyelmeztetési szabály létrehozása** lehetőséget.
3. A **Figyelmeztetési szabály létrehozása** párbeszédablak **Mező** mezőjében válassza ki a megfigyelni kívánt mezőt.
4. Az **Esemény** mezőben jelölje ki az esemény típusát.
5. A **Figyelmeztetés időszaka** gyorslapon válasszon egy beállítást.
6. Ha azt szeretné, hogy egy figyelmeztetési szabály egy megadott dátumon érvényét veszítse, válasszon ki egy befejezési dátumot a **Figyelmeztetés vége** gyorslapon.
7. A **Figyelmeztetés módja** gyorslapon a **Tárgy** mezőben fogadja el az e-mail üzenet alapértelmezett tárgyát, vagy adjon meg egy új tárgyat. A szöveg a figyelmeztetés kezdeményezése esetén küldött e-mail üzenet tárgya lesz.
8. Az **Üzenet** mezőbe beírható egy üzenet, ez azonban nem kötelező. Ez az az üzenet, amely megjelenik egy figyelmeztetés kezdeményezése esetén.
9. Kattintson az **OK** gombra a beállítások mentéséhez és a figyelmeztetési szabály létrehozásához.