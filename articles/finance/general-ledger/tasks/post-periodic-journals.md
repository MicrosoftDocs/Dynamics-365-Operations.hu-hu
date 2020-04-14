---
title: Időszaki naplók közzététele
description: Az időszaki naplókat olykor ismétlődő naplónak is nevezik, mivel az összeg, a szöveg és más adatok az időszaki napló beolvasásákor minden alkalommal megismétlődnek.
author: aprilolson
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransPeriodic, LedgerJournalTransDaily
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7f721a05c8b74f1cfcf43177b73129751483650e
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144936"
---
# <a name="post-periodic-journals"></a>Időszaki naplók közzététele

[!include [banner](../../includes/banner.md)]

Az időszaki naplókat olykor ismétlődő naplónak is nevezik, mivel az összeg, a szöveg és más adatok az időszaki napló beolvasásákor minden alkalommal megismétlődnek. Időszaki napló létrehozásakor határozza meg az ismétlődéshez tartozó időszakot (pl. nap vagy hónap). Ez a feladat útmutató havi ismétlődés időszaki naplót hoz létre.

1. Nyissa meg a **Navigációs ablakban a Modulok > Főkönyv > Időszakos feladatok > Időszaki naplók** elemet.
2. Kattintson az **Új** elemre.
3. A **Név** mezőben adjon meg vagy válasszon ki egy értéket.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Írjon egy értéket a **Leírás** mezőbe. A leírás a későbbi előhíváskor az Időszaki napló neve lesz, ezért adjon neki megfelelő nevet.
6. A **Művelet ablaktáblán** kattintson a **Sorok** elemre. Egy Időszaki napló általában több naplósort tartalmaz. Ez az útmutató azonban most csak egy sort ad hozzá.
7. Adja meg a dátumot a **Dátum** mezőben. A **Dátum** mező a napi naplóba történő következő átvitel feladási dátumát tartalmazza. A naplókhoz, amelyeket havonta előhív, ajánlott a feladás dátumának használata az adott hónapban, általában az időszak első vagy utolsó dátuma. A Dátum mezőt üresen is hagyhatja, és megadhatja a napló visszaolvasásának dátumát, az Üres dátum mező használatával. A mező automatikusan frissül a következő ismétlődő dátumra, amikor a tranzakciókat előhívják. 
8. A **Számla** mezőben adja meg a kívánt értékeket.
9. A **Leírás** mezőben adjon meg vagy válasszon ki egy értéket.
10. Zárja be a lapot.
11. Adjon meg egy számot a **Tartozik** mezőben.
12. Az **Ellenszámla** mezőben adja meg a kívánt értékeket.
13. Válassza a 'Hónapok' lehetőséget az **Egység** mezőben.
14. Az **Egységek száma** mezőben írja be az 1-es számot.
15. Adja meg a dátumot az **Utolsó dátum** mezőben. Az utolsó dátum megadása az előző időszakban megakadályozza, hogy az ismétlődő napló tévedésből a helytelen kezdőidőszakban jöjjön létre. Az utolsó dátum később minden alkalommal frissül, valahányszor az időszaki naplót a program beolvassa. 
16. Kattintson a **Mentés** gombra.
17. Nyissa meg a **Navigációs ablak > Modulok > Főkönyv > Naplóbejegyzések > Általános naplók** elemet.
18. Kattintson az **Új** elemre.
19. A **Név** mezőben adjon meg vagy válasszon ki egy értéket.
20. Keresse meg és jelölje ki a kívánt rekordot a listán.
21. A listában kattintson a kijelölt sorban lévő hivatkozásra.
22. Írjon egy értéket a **Leírás** mezőbe.
23. A **Művelet ablaktáblán** kattintson a **Sorok** elemre.
24. A **Műveleti ablaktáblán** kattintson az **Időszaknapló** elemre.
25. Kattintson a **Napló beolvasása** menüpontra.
26. Adjon meg egy dátumot a **Záró dátum** mezőben. A **Záró dátum** az időszakos bizonylatsor fordulónapjaként szolgál. Az ismétlődés beállításától függően, az Utolsó dátum és a Záró dátum ugyanabban a sorban többször is benne lehet a keletkező naplóban. A Záró dátum automatikusan frissül attól függően, hogy az időszaki sor mikor került utoljára át a naplóba. 
27. Az **Időszaki naplószám mezőben** adjon meg, vagy válasszon ki egy értéket.
28. A listában kattintson a kijelölt sorban lévő hivatkozásra.
29. Kattintson az **OK** gombra. Az időszaknapló készen áll a felülvizsgálatra, jóváhagyás vagy az elküldésre a követelményektől vagy a beállítástól függően.   
