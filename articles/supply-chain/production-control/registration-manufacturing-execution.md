---
title: Gyártásvégrehajtás regisztrációja
description: Ez a témakör olyan alapvető fogalmakat és feltételeket ír le, amelyek alapján a gyártásvégrehajtás konfigurálása és használata szükséges.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgRegistration
audience: Application User
ms.reviewer: kamaybac
ms.custom: 70103
ms.assetid: 52ba1cdd-767f-4edd-896f-61adce8479d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c43a9d847045f2c029f232d6317268d91ee0129a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907203"
---
# <a name="registration-for-manufacturing-execution"></a>Gyártásvégrehajtás regisztrációja

[!include [banner](../includes/banner.md)]

Ez a témakör olyan alapvető fogalmakat és feltételeket ír le, amelyek alapján a gyártásvégrehajtás konfigurálása és használata szükséges. 

A gyártás-végrehajtás elsősorban gyártó vállalatok általi használatra készült. A dolgozók a **Feladatregisztrálás** oldalon regisztrálhatják a termelési folyamatok idő- és cikkfelhasználását. Minden regisztrációt jóváhagynak, és később átkerülnek a megfelelő modulokba. A regisztrációk folyamatos jóváhagyása és továbbítása lehetővé teszi, hogy a vezetők könnyen nyomon követhessék a termelési rendelések tényleges költségeit.

## <a name="manufacturing-execution-and-registration-terminology"></a>A Gyártásvégrehajtással és regisztrációval kapcsolatos fogalmak
Az alábbi táblázat a gyártásvégrehajtáshoz és a kapcsolódó regisztrációs feladatokhoz kötődő kifejezéseket tartalmazza.

| Időszak                          | Leírás                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Gyártásvégrehajtás       | A függvény a következők regisztrálására használatos: idő, anyagfelhasználás, termelési feladatok költségei, projektek és közvetett tevékenységek. A regisztráció egy gyártásvégrehajtás-regisztráló ügyfélben történik.                                                                                                                                                                                                                                                                                                                                                                                                   |
| Feladatlista                      | A **Feladatregisztrálás** oldalon a dolgozók azoknak a feladatoknak a listájával együtt jelennek meg, amelyeket egy meghatározott erőforráson (például gépen) el kell végezniük. Dolgozó minden egyes feladathoz vagy munkához az idő és a cikkfelhasználásra lehet regisztrálni, a feladatlistában található.                                                                                                                                                                                                                                                                                                                                                                           |
| Kötegelés feladat                  | Feladat kötegelésének nevezzük, ha egy dolgozó a **Feladatregisztrálás** oldalon egy időpontban egynél több feladatot indít el. A kötegelt feladatokra fordított idő felosztási kulcsok segítségével többféle módon felosztható az egyes feladatok között.                                                                                                                                                                                                                                                                                                                                                         |
| A regisztrációk irányító-asszisztens | A dolgozók regisztrálhatnak erőforrás asszisztenseként, továbbá kis csapatokat hozhatnak létre, amelyekben a dolgozók ugyanazon a termelési feladaton dolgoznak. Dolgozók kapcsolódik, asszisztensek nevezi irányítók típusú erőforrások. A regisztrációt csak az irányító erőforrásnak kell elvégeznie. Az összes asszisztens automatikusan megkapja ugyanazokat a regisztrációkat. Ha például egy gép működik irányítóként, azok a dolgozók, akik a gép asszisztenseiként regisztráltak, a **Feladatregisztrálás** oldalon regisztrációkat hajthatnak végre, és mind a gép, mind az asszisztensként kapcsolódó dolgozók megkapják ugyanazokat a regisztrációkat. |
| Közvetett tevékenység             | Olyan tevékenység vagy feladat, amely nem kapcsolódik közvetlenül termelési feladathoz vagy projekthez, például osztályértekezlet, tisztítási vagy karbantartási feladat az üzemben. A dolgozók a termelési feladatokhoz és projektekhez hasonló módon regisztrálhatnak közvetett tevékenységeket.                                                                                                                                                                                                                                                                                                |

## <a name="registrations-in-manufacturing-execution"></a>Regisztrációk készítése a Gyártásvégrehajtás modulban
A dolgozók számára a regisztrációk számos különféle típusa áll rendelkezésre a termelési feladatokban elvégzett munka gyártásvégrehajtása során. A rendszer beállításától függően a dolgozók még projekttevékenységekre és nem termelékeny feladatokra (például szünetek, távollétek és közvetett tevékenységek) is létrehozhatnak regisztrációkat. A regisztráció típusai a következők:

-   **Érkezéskori/távozáskori blokkolás** (munkaidő-nyilvántartással együtt is elérhető) – A dolgozók érkezéskori blokkolása a munkahelyre való érkezéskor, távozáskori blokkolása pedig hazamenetelkor történik.
-   **Termelési feladatok regisztrálása** – A dolgozók a feladatlistájukon szereplő feladatokra regisztrációkat (például feladat elindítása, visszajelzés feladatról) hozhatnak létre. A dolgozók egy időpontban több feladatot is elindíthatnak. Ezt feladatok kötegelésének nevezzük.
-   **Készlet regisztrálása** – A dolgozók létrehozhatnak üzemben használt, de termelési feladatokhoz közvetlenül nem kapcsolódó anyagokra vonatkozó regisztrációkat. Ilyenek például: zsír, kenőanyagok és más, a gépek folyamatos üzemeltetéséhez szükséges anyagok. Készletnapló regisztrálása történik.
-   **Projektek regisztrálása** (munkaidő-nyilvántartással együtt is elérhető) – A dolgozók létrehozhatnak a feladatlistájukban megjelenő projektekre és projekttevékenységekre vonatkozó regisztrációkat (például munka elkezdése, befejezése).
-   **Projektdíjak és projektcikkek regisztrálása** (munkaidő-nyilvántartással együtt is elérhető) – A dolgozók regisztrálhatnak projektdíjnaplóban szereplő projekthez kapcsolódó díjakat (költségeket). Emellett regisztrálhatják projektek cikkfelhasználását. Ez egy projektcikknaplóban történik.
-   **Regisztrálás másik dolgozó asszisztenseként** – Ha egy projektben vagy termelési feladatban két vagy több dolgozó együttműködik, a dolgozók egy gép vagy egy másik dolgozó asszisztenseként regisztrálhatnak, aki ezután az irányító szerepét tölti be. Ha szükséges, az irányító választhat másik dolgozót irányítónak.
-   **Távollét regisztrálása** (munkaidő-nyilvántartással együtt is elérhető) – A dolgozók regisztrálhatják a különféle beállított távollétkódokhoz tartozó időket. Távollét jelezhető, ha a dolgozó későn érkezik, a munkanap folyamán hiányzik, vagy a szokásos munkaidőprofil alapján tervezettnél korábban távozik.
-   **Szünetek regisztrálására** (munkaidő-nyilvántartással érhető el) – A munkanap során a dolgozók regisztrálhatják, hogy elhagyják a munkaállomásukat és szünetet tartanak. Több töréspont beállítható. Amikor a dolgozó visszatér és újra bejelentkezik, a rendszer regisztrálja, hogy a dolgozó ismét jelen van, és a szünet regisztrációja leáll.
-   **Közvetett tevékenységek regisztrálása** (munkaidő-nyilvántartással érhető el) – A közvetett tevékenységek a dolgozók által egy munkanap során végezhető nem termelékeny tevékenységek (például osztályértekezlet, csapatértekezlet vagy karbantartási feladat az üzemben). Adja meg a dolgozók közvetett tevékenységekhez való regisztrációjával kapcsolatos adatokat.
-   **Túlóra regisztrálása** (munkaidő-nyilvántartással érhető el) – A hosszabb munkanapot elvégző dolgozók választhatnak, hogy a szokásos munkaidőn túli órák rugalmas munkaidőként legyenek-e regisztrálva, vagy túlóraként.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]