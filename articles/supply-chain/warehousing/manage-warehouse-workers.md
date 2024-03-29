---
title: Raktári dolgozók kezelése
description: Ez a cikk leírja, hogyan használható a Raktárkezelés mobilalkalmazás az alkalmazottak által a raktárakban elvégzett munka felügyeletére és irányítására.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorker, InventLocation, WHSLaborStandards, WHSWorker, WHSWorkTable, WHSWorkTableListPage, WHSResetUserPassword
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72891
ms.assetid: feaa6f15-49d2-41f5-9b87-453463c52e4e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a3261571f7ba43a79ee42afd8cdfe9b69cb83c01de3e4b2b89d2b0aae668ea2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757518"
---
# <a name="manage-warehouse-workers"></a>Raktári dolgozók kezelése

[!include [banner](../includes/banner.md)]

Ez a cikk leírja, hogyan használható a Raktárkezelés mobilalkalmazás az alkalmazottak által a raktárakban elvégzett munka felügyeletére és irányítására.

A funkció használatakor a raktárkezelésben minden, raktári dolgozó által elvégzett művelet *munka*. Az munkákat, mint a kitárolás, áthelyezés és az aktuális készlet leltározása, mobilkészülékek segítségével rögzítik. Mielőtt egy raktári dolgozó munkát végezhetne, társítani kell őt egy dolgozóval a Human resourcesban. Minden egyes **Dolgozó** fiókhoz több raktárimunka-felhasználó társítható. Ezek a munkafelhasználók dolgozhatnak különböző raktárakban, és különböző szintű hozzáféréssel rendelkezhetnek a különféle mobilkészülékmenükhöz. A raktárimunka-felhasználókra úgy lehet tekinteni, mint egy adott dolgozó többszörös bejelentkezéseire. Minden egyes munkafelhasználó rendelkezik egy alapértelmezett raktárral, és a menüelemek jelenítik meg a konkrét munkafolyamatokat, amelyek elérhetők az adott munkafelhasználó számára. 

Egy új munka felhasználó létrehozásához a **Dolgozók** oldalon az **Általános** lapon a **Raktárak** szakaszban kattintson a **Dolgozó** lehetőségre. Meg kell adni egy felhasználói azonosítót, egy felhasználónevet, egy alapértelmezett raktárat és egy menünevet. Ez a menü akkor töltődik be, amikor a felhasználó bejelentkezik az a raktári mobileszközportálon, illetve lehetővé teszi a felhasználó számára elérhető menüelemek definiálását. 

Az egyes munkafelhasználók esetében elvégzett beállítás részeként definiálhatók a konkrét munkafolyamatok is. A **Ciklikusleltár-felügyelő** mező használatával például megadható, hogy a felhasználó feldolgozhat-e ciklusleltározási eltérésekre vonatkozó módosításokat egy leltározási művelet során, vagy előbb meg kell-e vizsgálnia ezeket a módosításokat egy másik személynek.

## <a name="defining-labor-standards"></a>Munkavégzési szabályok meghatározása
A **Munkavégzési szabályok** oldalon megadhatja a számítási módszereket, amelyekkel a rendszer kiszámítja egy adott típusú munkához szükséges becsült időt. Ez a meghatározás beállítható általános vagy konkrét szinten. Például megadható egy értékesítési rendelés kitárolásának feldolgozásához várhatóan szükséges idő a súly függvényében egy konkrét egységdefinícióra vonatkozóan egy adott kitárolási folyamat alkalmazása esetén. Ezzel egyidőben rögzítheti a kitárolt aktuális készlethez tartozó betárolási művelet idejét, amely egy másik számítási módszerből származik. 

A definiált munkavégzési szabályok engedélyezéséhez be kell jelölnie a **Munkavégzési szabályok engedélyezése** lehetőséget minden egyes raktárnál, amelynél alkalmazni kívánja a munkavégzési szabályokat.

## <a name="monitoring-and-controlling-warehouse-work"></a>A raktári munka felügyelete és irányítása
A **Minden munka** oldal segítségével figyelemmel kísérheti és karbantarthatja a tervezett, folyamatban lévő és befejezett munkákat. Ezen az oldalon frissítheti a különféle raktári folyamatokat, mint a raktári munkával kapcsolatos felhasználói hozzárendelések és a munkaprioritás. Részletekbe menően megvizsgálhatja a munkafejléceket és a munkasorokat, hogy megértse az elvárt és a befejezett munkafolyamatokat. 

Ha engedélyezi a **Munkavégzési szabályok** a lehetőséget, akkor láthatja a munka számított becsült idejét. Ezt követően a munka feldolgozása után ténylegesen idő is megjelennek az egyes munkaműveleteknél. Ezzel a módszerrel összehasonlítható a becsült idő a tényleges idővel 

A becsült idő ezenkívül használható szabályokban is a munka automatikus darabolására a munka létrehozásakor. Ez lehetőséget ad a munka terhelésegyensúlyozására a feladat befejezéséhez szükséges várható idő alapján. 

A munkatételek feldolgozásához felhasznált idő elemzése segíthet javítani a raktári dolgozók hatékonyságát. Az elemzésben segítséget nyújthatnak a következő jelentések:

-   **Felhasználói munkavégzési** – Ez a jelentés mutatja a dolgozói termelékenységet, a tényleges és az elvárt idők összehasonlítása alapján.
-   **Munka a munkatranzakció típusa szerint** – Ezen jelentés segítségével kivizsgálhatja a hatékonysággal kapcsolatos hiányokat adott raktári folyamatok esetében. Például észreveszi, hogy az átmozgatási rendelésekhez tartozó kitárolások tovább tartanak ezen a héten, mint az előző hetek folyamán. Ez az információ hasznos lehet e további vizsgálat során.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]