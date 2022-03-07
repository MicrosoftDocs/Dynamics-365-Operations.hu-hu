---
title: Figyelmeztetések és hibák a főkönyvi időszaki állapot készlet zárása nélküli módosítása esetén
description: Figyelmeztetések és hibák a főkönyvi időszaki állapot készlet zárása nélküli módosítása esetén
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 05851753e29da75f014d2cc77e2b8df259620eee
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476538"
---
# <a name="warnings-or-errors-on-changing-ledger-period-status-without-closing-inventory"></a>Figyelmeztetések és hibák a főkönyvi időszaki állapot készlet zárása nélküli módosítása esetén

A Microsoft a következő ellenőrzéseket vezette be annak érdekében, hogy megakadályozza a nem megfelelő időszakvégi feldolgozást a költségszámítással kapcsolatban. Ha a következő hibaüzenetek valamelyikét észleli, akkor a problémák megoldásával kapcsolatos további tudnivalókat lásd a [KB 4561987](https://fix.lcs.dynamics.com/Issue/Details?kb=4561987&bugId=445351&dbType=3&qc=f514f2adcddcddceec43af58c26ae8a9020effdc7cdfe085d9d0deeb8cc7b6a3) részben.

- Újraszámítást készül végrehajtani %1 (2019.02.10.). A rendszer az utolsó regisztrált újraszámítást egy előző időszakban, %2 (2019.01.20.) dátummal futtatta. Az %3 (2019.01.31.) egyeztetési időszak végén nem sikerült lezárni egy készlet végrehajtását. Ne felejtse el az %3 (2019.01.31.) időszak végének megfelelő készletet lezárni. A készletekre, az eladott áruk beszerzési értékére és az eltérésekre vonatkozó becslések nem lehetnek helyesek az alfőkönyv vagy a főkönyv modulban mindaddig, amíg nem történt meg a végrehajtás.

- A főkönyvi időszak állapotának módosítása erről: %1 erre: %2. Az %3 egyeztetési időszak végén nem sikerült lezárni a készlet végrehajtását. Az állapot módosítása előtt végre kell hajtania egy készletlezárást, amely az %3 időszak végével való egyeztetés előtt van. A készletekre, az eladott áruk beszerzési értékére és az eltérésekre vonatkozó becslések nem lehetnek helyesek az alfőkönyv vagy a főkönyv modulban mindaddig, amíg nem történt meg a végrehajtás. Jogi személy jelentette %4. Egyelőre ez csak tájékoztatási jellegű, de a jövőben ilyen műveletet kell végrehajtania.

- A %1 számlastruktúra módosult. Egy vagy több fő számla már %2 nem létezik. Ezeket a fő számlákat a %3 dátumra %4 dátummal van szükség. A %3 feladat folytatása előtt adja hozzá ezeket a fő számlákat a %1 számlastruktúrába. Egyelőre ez csak tájékoztatási jellegű, de a jövőben ilyen műveletet kell végrehajtania.

- Készletzárást készül végrehajtani %1 (2019.01.31.). Az %2 (2019.01.31.) egyeztetési időszak végén nem sikerült visszavezetéses költségelszámolás kiszámítását végrehajtani. Ne felejtse el végrehajtani az %3 (2019.01.31.) egyeztetési időszak végén végrehajtani a visszavezetéses költségelszámolás kiszámítását. A készletekre, az eladott áruk beszerzési értékére és az eltérésekre vonatkozó becslések nem lehetnek helyesek az alfőkönyv vagy a főkönyv modulban mindaddig, amíg nem történt meg a végrehajtás.

- Egy visszavezetéses költségelszámolás kiszámítását készül elvégezni %1 (2019.02.28.). A rendszer az utolsó regisztrált visszavezetéses költségelszámolási kiszámítást egy előző időszakban, %2 (2019.01.31.) dátummal futtatta. Az %3 (2019.01.31.) egyeztetési időszak végén nem sikerült lezárni egy készlet végrehajtását.

Ne felejtsen el egy %3 (2019.01.31.) időszak végének megfelelő készletet lezárni. A készletekre, az eladott áruk beszerzési értékére és az eltérésekre vonatkozó becslések nem lehetnek helyesek az alfőkönyv vagy a főkönyv modulban mindaddig, amíg nem történt meg a készletzárás.