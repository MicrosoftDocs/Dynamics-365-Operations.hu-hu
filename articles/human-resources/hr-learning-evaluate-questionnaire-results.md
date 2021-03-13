---
title: A kérdőívek eredményeinek megtekintése és kiértékelése
description: Ez a cikk ismerteti, hogyan tudja megtekinteni és elemezni a kitöltött kérdőívek válaszait.
author: andreabichsel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: ff2136e1f0a87b7d77968ca1163e64f8838b234b
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2021
ms.locfileid: "5116116"
---
# <a name="view-and-evaluate-the-results-of-questionnaires"></a>A kérdőívek eredményeinek megtekintése és kiértékelése

Ez a cikk ismerteti, hogyan tudja megtekinteni és elemezni a kitöltött kérdőívek válaszait. 

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

> [!NOTE]
> Az **Eredmények** jelentés csak akkor érhető el, ha válaszcsoportokat használt a kérdőívben, valamint ha kiválasztotta az **Eredményeket bemutató oldal** lehetőséget a **Kérdőívek** oldalon. A **Válasz** jelentés és a **Helytelen válaszok** jelentés csak akkor érhető el, ha kiválasztotta a **Válaszjelentés** lehetőséget a **Kérdőívek** oldalon.

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