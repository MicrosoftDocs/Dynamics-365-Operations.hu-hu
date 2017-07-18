---
title: "Köteg és azonosítótábla megerősítése"
description: "Ez a témakör a kötegalkalmazás és az azonosítótábla-megerősítés mobileszközről való beállítását és alkalmazását mutatja be."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 70a8c18560f0cfc7a44625520f2f035a6004618a
ms.contentlocale: hu-hu
ms.lasthandoff: 06/20/2017

---

# <a name="batch-and-license-plate-confirmation"></a>Köteg és azonosítótábla megerősítése

[!include[banner](../includes/banner.md)]

A kötegelés megerősítésével meggyőződhet arról, hogy a helyes tételt tárolta ki a mobileszközről. A csak a fenti tételek kitárolásánál, amennyiben a *fentiek kötegelése* azt jelzi, hogy a köteg tartománya magasabb, mint a hely a keresési hierarchiában, így ellenőriznie kell, hogy a kitárolt köteg egyezik a munkasoron lévő köteggel. 

Az azonosítótábla megerősítésével meggyőződhet arról, hogy a helyes azonosítótáblát tárolta ki a mobileszközről. Amikor egy betervezett helyről tárol ki munkát, ellenőriznie kell, hogy a kitárolni kívánt azonosítótábla egyezik-e a munkához kapcsolódó azonosítótáblával. Ha a munka azonosítótábla leolvasásával kezdődik, akkor ezt a megerősítő lépést átugorja a rendszer.

## <a name="where-it-applies"></a>Alkalmazási kör
A visszaigazolás az alábbi esetekben alkalmazandó:

- A kötegelés megerősítése a fenti cikkek munkáinak kezdeti kitárolására vonatkozik.
- Az azonosítótábla megerősítése az előkészítési helyeknél lévő kitárolásokra érvényes.

## <a name="set-up-batch-and-license-plate-confirmation"></a>Köteg és azonosítótábla beállításának megerősítése
Ez a témakör a kötegalkalmazás és az azonosítótábla-megerősítés mobileszközről való beállítását és alkalmazását mutatja be.  
1.  Lépjen be a munka-visszaigazolás beállításához a mobileszköz menüelemeitől.  
2.  Válassza ki, hogy kötegelést vagy azonosítótábla-megerősítést szeretne végezni. Mindkét lehetőség rendelkezésre áll azoknál a munkatípus-kitárolásoknál, amelyeknél nincs engedélyezve az automatikus visszaigazolás.  

