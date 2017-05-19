---
title: "Könyvelési források böngészője"
description: "A cikk információt biztosít a Könyvelés forrás felfedezőről, aminek segítségével részletes elemzést végezhet a főkönyvi könyvelés bejegyzései mögötti forrásinformációról."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 03da3887ff114dece179f732da380170b85cf53d
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="accounting-source-explorer"></a>Könyvelési források böngészője

[!include[banner](../includes/banner.md)]


A cikk információt biztosít a Könyvelés forrás felfedezőről, aminek segítségével részletes elemzést végezhet a főkönyvi könyvelés bejegyzései mögötti forrásinformációról.

A számlázási forrás megtekintő egy új oldal, amely megjeleníti a forrásinformációt. A Könyvelési források böngészője önálló eszközként vagy főkönyvi könyvelési tételek mögötti részletek elemzésére használható. Például a Könyvelési források böngészőjével lehívhatók a legrészletesebb forrásinformációk ellenőrzési egyenlegeket vagy bizonylati tranzakciókat illetően. Ezután az Exportálás MS Excelbe funkció használatával, majd a Microsoft Excel programot használhatja az adatok további feldolgozására (például a Pivot táblával vagy Pivot tábla kimutatással).

Könyvelési források böngészője mindig ugyan azt a teljes összeget mutatja főkönyvi számlánként amelyet a Főkönyv (például a főkönyvi kivonat). A főkönyvi kivonatban, megjelenítheti a szegmenseket külön oszlopokban. Csak válassza ki a megfelelő pénzügyi dimenzió készletet. 

Paraméterek segítségével meghatározhatja za elemzési időszakot. Ez a funkció hasonlít a Főkönyvi kivonat funkciójára.

A forrásdokumentum-keretet használó valamennyi dokumentumnál a Könyvelési források böngészője további információkat jeleníti meg könyvelési felosztások és adott esetben projektszintű könyvelési felosztások alapján. Ezek az információk többek között: a pénzben kifejezett összeg típusa, projekt, tevékenység, kategória és sortulajdonság. Következzék pár példa az elvégezhető elemzésekre:

-   A beszerzési rendelés és szállítói számla közötti különbségek, mert minden eltérést egy pénzösszeg típus jelez, például költségeltérés
-   Számlázható és a nem számlázható órák és kiadások projekt, üzleti egység és a fő számla

Azokhoz a forrásbizonylatokhoz, amelyek a forrásbizonylat hivatkozás identitáskoncepciót használják, a Könyvelési források böngészője még több információt mutat, például vevő, szállító, dolgozó, termék, egységszöveg, és leírások. Következzék pár példa az elvégezhető elemzésekre:

-   A szállodai költségek üzleti egységre bontva és a szálloda márka a pénzügyi időszakra, költségjelentések alapján
-   Engedmény szállítókra, termékre, részletre bontva

Ezek a dokumentumoknál navigálhat a tényleges forrásbizonylathoz a Könyvelési források böngészőjéből.




