---
title: Átmeneti helyesbítési naplóbejegyzések feladása az Eszközlízingben
description: Ez a témakör azokat a funkciókat ismerteti, amelyek lehetővé teszik a lízingportfólió átváltását az új lízingkönyvelési standardokra, a Könyvelési standardok kodifikációs témakör 842-re (ASC 842) és a Nemzetközi pénzügyi jelentési standard 16-ra (IFRS 16).
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ea61a0d6e30695a2ef6b93529fcf3d21882c9cd2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819770"
---
# <a name="post-transition-adjustment-journal-entries-in-asset-leasing"></a>Átmeneti helyesbítési naplóbejegyzések feladása az Eszközlízingben

[!include [banner](../includes/banner.md)]

Ez a témakör azokat a funkciókat ismerteti, amelyek lehetővé teszik a lízingportfólió új lízingkönyvelési standardokra való átváltását: Könyvelési standardok kodifikációs témakör 842 (ASC 842), amely az Egyesült Államok általánosan elfogadott könyvelési elveinek (US GAAP) és a Nemzetközi pénzügyi jelentési standard 16 (IFRS 16) standardja.

A könyv új standardokra való átváltásához való beállításáról a [Lízingkönyvek beállítása](set-up-lease-books.md) című témakörben talál további információt.

Átmeneti helyesbítési naplóbejegyzés létrehozásakor naplóbejegyzés jön létre. Ez a bejegyzés a lízingnek az adott napon az új standardok szerinti elszámolásának mérlegre gyakorolt hatását tükrözi. A megfelelő eszközszámlát az adott napon megterhelik a könyv szerinti értékkel, és a kötelezettségszámlát jóváírják. A különbözetet vagy megterhelik, vagy jóváírják a visszatartott keresetekre.

Az új könyvelési standardoknak megfelelő átmeneti kiigazítás könyveléséhez kövesse az alábbi lépéseket.

1. A **Lízing összegzése** lapon válassza ki a lízinget, majd válassza a **Könyvek** lehetőséget.
2. A könyvben válassza a **Fizetési ütemezés** lehetőséget.
3. A **Fizetési ütemezés** párbeszédpanelen válassza a **Megerősítés** lehetőséget. Majd zárja be a párbeszédpanelt.
4. Válassza az **Átváltás beállítása** lehetőséget.

    > [!NOTE]
    > Átmeneti kiigazítás csak olyan lízingkönyvekhez hozható létre, amelyek olyan könyvhöz vannak rendelve, ahol az **Átváltási könyv** mező elérhető. Ha a **Lízing kezdete** mező értéke későbbi az átmeneti dátumnál, akkor az **Átmeneti kiigazítás** mező értéke nem frissül.

5. A naplóbejegyzés megtekintéséhez válassza ki az **Eszköz lízingnaplók** lehetőséget.
6. Jelölje ki az új naplót, majd válassza a **Feladás** lehetőséget.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]