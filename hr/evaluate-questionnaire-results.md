---
title: "A kérdőív megtekintése, és az eredmények kiértékelése"
description: "Ez a témakör ismerteti, hogyan tekintheti meg és értékeljék az eredményeket, hogy a válaszadók kérdőívek."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: a76ec0cd86bcc810b42ae3cd8efd8a584e6c4da3
ms.openlocfilehash: bcf59ea8862280675c9fb711d2aab1e8dff18806
ms.lasthandoff: 03/31/2017


---

# <a name="view-and-evaluate-the-results-of-a-questionnaire"></a>A kérdőív megtekintése, és az eredmények kiértékelése

Ez a témakör ismerteti, hogyan tekintheti meg és értékeljék az eredményeket, hogy a válaszadók kérdőívek. 

Ha a válaszadók kitöltötték a kérdőívet, megtekintheti, valamint kiértékelheti a kérdőív eredményét az alábbi módokon:

-   **Befejezett válaszmunkamenetek** – A válaszadók által kitöltött kérdőívek részleteinek megtekintése, valamint a válaszok és elért pontok összesítésére szolgáló jelentés létrehozása.
-   **Eredmény csoportok** – A kérdőív eredménycsoportjainak és statisztikájának megtekintése. Az eredménycsoport statisztikája létrehozható a kérdőív egyetlen válaszmunkamenetéhez, illetve az összes válaszmunkamenethez.
-   **Kérdőív-statisztika** – A válaszadók bizonyos csoportjához tartozó statisztika kiszámítási feltételeinek megadása.

Létrehozhat az eredmények megtekintéséhez személy, válaszmunkamenet vagy eredménycsoport alapján rendezett jelentéseket. Az alábbi jelentések érhetőek el a kitöltött kérdőívekhez:

-   Válaszok
-   Válaszok kérdőívenként
-   Válaszok személyenként
-   Visszajelzés elemzése

## <a name="answer-session-results"></a>Válaszmunkamenet eredményei
Miután a válaszadók kitöltötték a kérdőívet, megtekintheti a befejezett válaszmunkamenetek eredményeit. A válaszmunkamenet egy adott felhasználó válasza a kérdőívre. A **Válaszok** oldalon megtekintheti a befejezett válaszmunkamenetekhez kapcsolódó részleteket. Az a válaszmunkamenet, ami a **Válaszok** oldalon megjelenik, különböző szűrőkkel van ellátva, attól függően, hogy miként nyitja meg az oldalt.

-   Összes kérdőív
-   Adott kérdőív
-   Adott személy

A **Válaszok** oldalon megtekinthet részleteket a válaszokról, az elért pontokról, a válaszadó minden eredménycsoportban adott válaszairól, valamint a kérdőívben használt kérdéshierarchiáról, ha volt használva kérdéshierarchia. Létrehozhatja és kinyomtathatja az alábbi jelentéseket:

-   **Eredmény jelentés** – Ez a jelentés grafikusan ábrázolja az eredménycsoportonként elért pontjait a kiválasztott válaszmunkamenetnek.
-   **Válasz jelentés** – Ez a jelentés a válaszadó kérdésenkénti válaszait mutatja.
-   **Helytelen válaszok** – Ez a jelentés a válaszadó által adott helytelen válaszokhoz kapcsolódó információkat mutatja.

**Megjegyzés:** Az **Eredmények** jelentés csak akkor érhető el, ha válaszcsoportokat használt a kérdőívben, valamint ha kiválasztotta az **Eredményoldal** lehetőséget a **Kérdőívek** oldalon. A **Válasz** jelentés és a **Helytelen válaszok** jelentés csak akkor érhető el, ha kiválasztotta a **Válaszjelentés** lehetőséget a **Kérdőívek** oldalon.

## <a name="questionnaire-statistics"></a>Kérdőív-statisztika
Használhat kérdőív statisztikákat a kitöltött kérdőívek eredményének kiértékeléséhez, az Ön által megszabott számítások alapján. A számítások megadásához az alábbi feladatokat kell elvégeznie:

-   Válassza ki a statisztikák megjelenítésének és kiszámításának feltételeit.
    -   Megjelenítheti a kérdőív, a kérdések, a kérdés sorok, illetve az eredménycsoportok statisztikáit.
    -   Válassza ki az eredmények megtekintéséhez használatos diagram típusát.
    -   Válassza ki a személyek típusát, akik válaszát bele szeretné foglalni a statisztikába, mint például alkalmazottak, kapcsolattartók vagy pályázók. Olyan kérdőívek válaszait is belefoglalhat a statisztikába, amiket névtelenül töltöttek ki.
    -   Az eredmények kiértékeléséhez állítsa be kor vagy szolgálati idő alapján az intervallumokat.
-   Válassza ki, vagy ellenőrizze meg a statisztikák tárgyának finomítására szolgáló beállításokat. Például irányítószám megadásával az adott földrajzi terület válaszadóinak eredményeit elemezheti.
-   Válassza ki, vagy ellenőrizze az eredmények kiértékelésének feltételeit, válaszadó vagy a kérdői jellemzője alapján. Például az **Irányítószám** kiválasztásával kiértékelheti a válaszadó helye és helyes válaszai közti korrelációt.

A program menti a megadott beállításokat, így ezek az eredmények ismételt újraszámításakor felhasználhatók.

<a name="see-also"></a>Lásd még
--------

[Kérdőívek tervezése](design-questionnaires.md)

[Kérdőívek használata](questionnaires.md)

[Kérdőívek kiosztása és kitöltése](distribute-questionnaires.md)


