---
title: "SEPA beszedési megbízás beállítása"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: bb835f8dad16938b56365c7b06d4a0228f9aba66
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-sepa-direct-debit-mandate"></a>SEPA beszedési megbízás beállítása



Az egységes eurófizetési térség (SEPA) beszedési megbízással a hitelező pénzt szedhet be a vevő bankszámlájáról, feltéve , ha a vevő aláírt meghatalmazást adott a hitelezőnek. A rendelet, amit a vevő aláírás engedélyez egy hitelezőnek, hogy gyűjtse össze a fizetéstést és utasítja a vevő bankját a beszedés kifizetésére. Ez a témakör a folyamat SEPA típusú beszedési megbízások beállításának megjelenítése vannak rendezve.

## <a name="prerequisites"></a>Előfeltételek
Az alábbi táblázat bemutatja a munka megkezdése előtt biztosítandó előfeltételeket.

| Kategória       | Előfeltételek                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ország/régió | A jogi személy elsődleges címének a következő ország/régió valamelyikében kell lennie: Ausztria, Belgium, Németország, Spanyolország, Franciaország, Olaszország vagy Hollandia. |

1. Állítsa be egy számsorozatot a beszedési megbízások minden beszedési megbízás egyedi számmal kell rendelkeznie. A **Számsorozatok** oldalon a beszedési megbízási meghatalmazások számára számsorozatot hozhat létre. Ezzel az azonosítóval rendelheti hozzá a számsorozatot a beszedési megbízási felhatalmazás rendszeréhez a **Fiók Kinnlevőségek paraméterei** képernyőn.

2. Kinnlevőségek paraméterei beszedési megbízások használatának beállítása a **Kinnlevőségek paraméterei** oldalra beszedési megbízások paramétereinek beállítása. A paraméterek beállítása a a **beszedési** lap, van szükség szerint változtassa meg az alapértelmezés szerinti paramétereket. Ezután a a **Number sequences** lap, a frissítés a **közvetlen terhelési megbízás azonosítója** című állíthatja be a Számsorozat mezőbe.

3. Beszedési arra, hogy a fizetési mód beállítva be kell állítania egy beszedési megbízás fizetési módot. Ezt a fizetési módot használhatja azon számlák lekérdezéseihez, amelyekhez beszedési megbízásos kifizetést kíván létrehozni. Hasznélja a **Fizetési módszerek** lapot a fizetési módszerek beállításához. A beszedési megbízási felhatalmazások fizetési mód beállításához be kell tartani a fizetési mód következő lépéseit:

-   A **Fizetés típus** mezőben válassza ki az **Elektronikus fizetés** lehetőséget.
-   Választható lehetőség: Ha azt szeretné, hogy a vevők több arra, és a **időszak** mezőjében válassza az **számla**. Minden számla külön fizetést hoz létre, és minden egyes kifizetés a megbízás megadott fogja használni a számlához.
-   Válassza ki a **Felhatalmazás igénylése** lehetőséget a beszedési megbízási felhatalmazások használata által a kifizetések létrehozásához. A **Felhatalmazás igénylése** lehetőség csak akkor érhető el, ha az **Elektronikus fizetés** be van jelölve a **Fizetés típusa** mezőben.

Lásd még: [beszedési – áttekintés](sepa-direct-debit-overview.md) 

