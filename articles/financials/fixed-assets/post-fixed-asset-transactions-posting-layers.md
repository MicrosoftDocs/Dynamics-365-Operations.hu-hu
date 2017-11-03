---
title: "Tárgyieszköz-tranzakciók feladása a feladási rétegekbe"
description: "Ez a cikk a tárgyi-eszköztranzakciók feladási réteg funkciójába nyújt betekintést."
author: twheeloc
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 10e7fc67f8f13a6363b4359fd1b7684f1b80675e
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="post-fixed-asset-transactions-to-posting-layers"></a>Tárgyieszköz-tranzakciók feladása a feladási rétegekbe

[!include[banner](../includes/banner.md)]


Ez a cikk a tárgyi-eszköztranzakciók feladási réteg funkciójába nyújt betekintést.

Egy tárgyi eszköz különböző célokat szolgáló értékcsökkenése gyakran különböző módszereket kíván. Az adózási célú értékcsökkenés kiszámítása az érvényes adótörvények szerint történik, hogy adózás előtt a legmagasabb lehetséges értékcsökkenést lehessen elérni, ellenben a jelentés céljából készített értékcsökkenés a könyvelési törvények és szabályok szerint történik. Az értékcsökkenés különböző fajtáinak kiszámítása és rögzítése külön feladási rétegekben történik.

A tárgyi eszközhöz csatolt valamennyi könyv egy meghatározott feladási réteghez tartozik, amelynek saját átfogó értékcsökkenési célkitűzése van. Tíz feladási réteg létezik: Aktuális, Műveletek, Adó és hét Egyéni réteg. Letilthatja a főkönyvbe történő feladást is a könyvnél, ha a Feladás a főkönyvbe mezőt Nem értékre állítja. A Feladási réteg mező értéke automatikusan Nincs lesz. A nem a főkönyvbe feladott könyveket általában adóbevallási célokra használják. Ez a megközelítés további rugalmasságot biztosít az eszközkönyv előzménytranzakcióinak törléséhez, mivel ezek így nem kerültek rögzítésre a főkönyvbe.

A tárgyieszköz-naplókat a Naplónevek lapon a Főkönyv > Napló beállítása > Naplónevek pontban határozhatja meg. A naplónév csak egy feladási réteghez kapcsolja az összes olyan naplót, amelybe fel lehet adni értékcsökkenést. A napló feladási rétege nem módosítható. Ezen korlátozás segítségével garantálható, hogy az egyes feladási rétegek tranzakciói külön legyenek tárolva. Legalább egy naplónevet minden egyes feladási réteghez létre kell hozni. Ha nem a főkönyvbe feladott könyveket használ, létre kell hoznia egy naplót, ahol a feladási réteg értéke Nincs.

Kijelölhet főkönyvi számlákat tárgyieszköz-tranzakciókhoz a Tárgyieszköz-feladási profilok lapon. Minden feladási profilnál jelölje ki a megfelelő tranzakciótípust és a könyvet, majd jelölje ki a főkönyvi számlákat. Hozzon létre feladási profil rekordot minden, a főkönyvbe feladott könyvre.

> [!NOTE] 
> A származtatott könyvek használatával egyszerre több feladási rétegre is fel lehet adni a tranzakciókat. Az elsődleges könyv tranzakcióit egy olyan naplóban kell létrehozni, amelynek a feladási rétege megegyezik a könyv feladási rétegével. Feladás során a származtatott könyvtranzakciókat a program feladja a megfelelő feladási rétegekre.

A további tudnivalókat lásd [Származtatott könyvek](derived-books.md) és [Feladás származtatott könyvekbe](post-derived-value-models.md).




