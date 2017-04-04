---
title: "Tárgyieszköz-tranzakciók feladási rétegekbe feladása"
description: "Ez a cikk a tárgyi-eszköztranzakciók feladási réteg funkciójába nyújt betekintést."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 4b112eee303604149c7609972a60c2014d4be423
ms.lasthandoff: 03/31/2017


---

# <a name="post-fixed-asset-transactions-to-posting-layers"></a>Tárgyieszköz-tranzakciók feladási rétegekbe feladása

Ez a cikk a tárgyi-eszköztranzakciók feladási réteg funkciójába nyújt betekintést.

Egy tárgyi eszköz különböző célokat szolgáló értékcsökkenése gyakran különböző módszereket kíván. Az adózási célú értékcsökkenés kiszámítása az érvényes adótörvények szerint történik, hogy adózás előtt a legmagasabb lehetséges értékcsökkenést lehessen elérni, ellenben a jelentés céljából készített értékcsökkenés a könyvelési törvények és szabályok szerint történik. Az értékcsökkenés különböző fajtáinak kiszámítása és rögzítése külön feladási rétegekben történik.

A tárgyi eszközhöz csatolt valamennyi könyv egy meghatározott feladási réteghez tartozik, amelynek saját átfogó értékcsökkenési célkitűzése van. Tíz feladási réteg létezik: Aktuális, Műveletek, Adó és hét Egyéni réteg. Letilthatja a főkönyvbe történő feladást is a könyvnél, ha a Feladás a főkönyvbe mezőt Nem értékre állítja. A Feladási réteg mező értéke automatikusan Nincs lesz. Általában könyveket, amelyek nem a főkönyvi könyvelést adóbevallási célokra használják. Ez a megközelítés a további rugalmasságot biztosít az eszközkönyv történelmi tranzakciók törlése, mert azok nem követtek el a főkönyvbe.

A tárgyieszköz-naplókat a Naplónevek lapon a Főkönyv > Napló beállítása > Naplónevek pontban határozhatja meg. A naplónév csak egy feladási réteghez kapcsolja az összes olyan naplót, amelybe fel lehet adni értékcsökkenést. A napló feladási rétege nem módosítható. Ezen korlátozás segítségével garantálható, hogy az egyes feladási rétegek tranzakciói külön legyenek tárolva. Legalább egy naplónevet minden egyes feladási réteghez létre kell hozni. Könyveket, amelyek nem a főkönyvi könyvelést használatakor is létre kell hoznia egy naplót, ahol a feladási réteg beállítása nincs.

Kijelölhet főkönyvi számlákat tárgyieszköz-tranzakciókhoz a Tárgyieszköz-feladási profilok lapon. Minden feladási profilnál jelölje ki a megfelelő tranzakciótípust és a könyvet, majd jelölje ki a főkönyvi számlákat. Hozzon létre feladási profil rekordot minden, a főkönyvbe feladott könyvre.

> [!NOTE] 
> Származtatott könyvek használatával egyszerre több feladási rétegre tranzakciókat adhatnak fel. Az elsődleges könyv tranzakcióit egy olyan naplóban kell létrehozni, amelynek a feladási rétege megegyezik a könyv feladási rétegével. Feladás során a származtatott könyvtranzakciókat a program feladja a megfelelő feladási rétegekre.

A további tudnivalókat lásd [származtatott könyvek](derived-books.md) és [feladás származtatott könyvek](post-derived-value-models.md).


