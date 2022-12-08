---
title: Időszaki naplók közzététele
description: Az időszaki naplókat olykor ismétlődő naplónak is nevezik, mivel az összeg, a szöveg és más adatok az időszaki napló beolvasásákor minden alkalommal megismétlődnek.
author: aprilolson
ms.date: 11/21/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransPeriodic, LedgerJournalTransDaily
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bdc1d9f67a515e3cdc45e173b88982feceb0ebfd
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799386"
---
# <a name="post-periodic-journals"></a>Időszaki naplók közzététele

[!include [banner](../../includes/banner.md)]

Az időszaki naplókat olykor ismétlődő naplónak is nevezik, mivel az összeg, a szöveg és más adatok az időszaki napló beolvasásákor minden alkalommal megismétlődnek. Időszaki napló létrehozásakor határozza meg az ismétlődéshez tartozó időszakot (pl. nap vagy hónap). Ez a feladat útmutató havi ismétlődés időszaki naplót hoz létre.

1. Nyissa meg a **Navigációs ablakban a Modulok > Főkönyv > Időszakos feladatok > Időszaki naplók** elemet.
2. Kattintson az **Új** elemre.
3. A **Név** mezőben adjon meg vagy válasszon ki egy értéket.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Írjon egy értéket a **Leírás** mezőbe. A leírás a későbbi előhíváskor az Időszaki napló neve lesz, ezért adjon neki megfelelő nevet.
6. A **Művelet ablaktáblán** kattintson a **Sorok** elemre. Egy Időszaki napló általában több naplósort tartalmaz. Ez a feladat-útmutató azonban csak egy sort ad hozzá.
7. Adja meg a dátumot a **Dátum** mezőben. A **Dátum** mező a napi naplóba történő következő átvitel feladási dátumát tartalmazza. Az egyes hónapokat beolvassa naplók esetén ajánlott a feladás hónapjában használni. Ez általában az időszak első vagy utolsó dátuma. Az Üres **dátum mező** használatával a Dátum mező üresen hagyható, **és** meg lehet adni a napló beolvasásának dátumát. A mező a tranzakciók beolvasásakor a következő ismétlődő dátumra frissül. 
8. A **Számla** mezőben adja meg a kívánt értékeket.
9. A **Leírás** mezőben adjon meg vagy válasszon ki egy értéket.
10. Zárja be a lapot.
11. Adjon meg egy számot a **Tartozik** mezőben.
12. Az **Ellenszámla** mezőben adja meg a kívánt értékeket.
13. Válassza ki az **Egység** mezőben a **Hónapok** lehetőséget.
14. Az Egységek **száma mezőbe** írjon **1-et**.
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
26. Adjon meg egy dátumot a **Záró dátum** mezőben. A **Záró dátum** az időszakos bizonylatsor fordulónapjaként szolgál. Az ismétlődési beállítás, a **·**  **Legutóbbi** dátum és a Cél dátum alapján előfordulhat, hogy ugyanaz a sor egynél többet tartalmaz az eredményül kapott naplóban. A **program automatikusan frissíti** a dátumot annak a munkamenetnek a dátuma alapján, amikor az időszaki sor utoljára átkerült a naplóba. 
27. Az **Időszaki naplószám mezőben** adjon meg, vagy válasszon ki egy értéket.
28. A listában kattintson a kijelölt sorban lévő hivatkozásra.
29. Kattintson az **OK** gombra. Az időszaknapló készen áll a felülvizsgálatra, jóváhagyás vagy az elküldésre a követelményektől vagy a beállítástól függően.   


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
