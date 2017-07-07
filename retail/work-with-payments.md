---
title: "Fizetési módszerek hívásközpontnál"
description: "Ez a témakör bemutatja a Dynamics 365 for Retail rendszer hívásközpontjaiban használható fizetési módokat."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 92163
ms.assetid: 8e738907-870b-466c-ab0c-07f4a4aa47f3
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 07cb1bcb3870b96e34f7f6725fe5b7da32628fde
ms.contentlocale: hu-hu
ms.lasthandoff: 06/20/2017


---

# <a name="payment-methods-in-a-call-center"></a>Fizetési módszerek hívásközpontnál

[!include[banner](includes/banner.md)]


Ez a témakör bemutatja a Dynamics 365 for Retail rendszer hívásközpontjaiban használható fizetési módokat.

Az egyéb csatornákban használt fizetési módok, például: készpénz, csekk, hitelkártya és ajándékutalvány is használható telefonos ügyfélszolgálatnál. A telefonos ügyfélszolgálatra történő fizetési mód beállítása után a telefonos ügyfélszolgálat felhasználóinak a **Fizetések** képernyő **Értékesítési rendelés** részében az egyik választható beállításként jelenik meg. Továbbá utalványokat állíthat be, amelyek kedvezményeket biztosítanak azon vásárlók részére, akik a rendeléseiket a szervezet hívásközpontjában adták le. Az utalványok lehetnek fix összegűek, illetve egy termék árának vagy a teljes rendelésnek egy bizonyos százaléka. Például az összeg alapú utalvány adhat 75,00 értékű kedvezményt, ha a vásárló legalább 750,00 értékben költ. Létrehozhat különböző utalványokat, felállíthat alá- és fölérendelt utalványokat, valamint másolhatja és érvénytelenítheti is őket. Használja az alábbi táblázatban szereplő beállításokat az utalvány létrehozásához.

|                           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Attribútum**             | A **Beváltási arány** mezőben adja meg a várható beváltási arányt százalékban, majd válassza ki, hogy az utalvány egyszer használható legyen-e, ki legyen--e adva újra automatikusan, vagy pedig egy adott vevőre vonatkozzon-e.                                                                                                                                                                                                                                                                                                                                                                                       |
| **Érvényes**                 | A **Kezdő dátum** és a **Záró dátum** mezőkben adja meg azt a kezdő és befejező dátumot, amelyek között az utalvány érvényes.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Szabályokkal/szabályok nélkül** | A **Katalógusok** és a **Cikkek** mezőkben adja meg, hogy melyik katalógust vagy cikket foglalja, illetve nem foglalja magában az utalvány. Ha kiválasztja a **Felvétel** vagy **Kihagyás** lehetőséget, kattintson a **Beállítás** lehetőségre, majd válassza **Katalógusok felvétele/kihagyása** vagy a **Termékek felvétele/kihagyása** lehetőséget, hogy adatokat adhasson meg a katalógusról vagy cikkről. Ha az **Egyik sem** lehetőséget választja, akkor az összes cikket és katalógust magában foglalja az utalvány.                                                                                                                                                                                                                          |
| **Vegyes**         | Ha nem szeretné, hogy ezt az utalványt további kedvezményekkel is igénybe vegyék, jelölje be a **Kizárólagos** jelölőnégyzetet. Ezután az **Eredet** mezőben válassza ki, hogy hol lehet használni az utalványt. Ha ez egy gyártói utalvány, válassza a **Gyártó kupon** jelölőnégyzetet.                                                                                                                                                                                                                                                                                                                                                                |
| **Jövőbeni utalvány**         | Ha ez az utalvány más kuponok fölé van rendelve, válassza a **Fölérendelt kupon** jelölőnégyzetet. Ha az imént említett utalványt más utalvány alá szeretné rendelni, válassza ki a fölérendelt kupont a **Fölérendelt utalvány azonosítója** mezőben. Például Ön létrehoz egy utalványt a közelgő tavaszi katalógushoz. Az összes többi utalvány, amit a továbbiakban létrehoz a tavaszi katalógus alárendelt utalványa lesz. Az alárendelt utalvány nyújthat egy 20 százalékos kedvezményt az új vevői rendelésekre, egy 10 százalékos kedvezményt egy újonnan megjelent cikkre, vagy egy 95,00 értékű kedvezményt 1000,00 érték feletti vásárlásnál. |

Egy elküld egy bankkártyás fizetést az **Értékesítési rendelés** lapon, majd kap egy üzenetet, hogy a kártya nincs engedélyezve, akkor engedélyezheti azt manuálisan. Engedélyezhet, elutasíthat, vagy újraküldhet egy bankkártyás tranzakciót az **Engedély kezelése** lapon. A további fizetés feldolgozási opciók beállításához használja a hívásközpont-paraméterek lapot:

-   A csekkvárakoztatások, mivel csekkel volt fizetve, várakoztatásba helyezte a pénzügyi személyzet feldolgozásokat, valamint a csekkvárakoztatás küszöbértéke meg lett haladva. A várakoztatásokat ki lehet adni manuálisan, vagy automatikusan lejár a beállítási időszak végén.
-   Megadhatja azokat a küszöbértékeket, amely felett a csekkes vagy hitelkártyás visszatérítést manuálisan kell jóváhagyni. A küszöbértéket meghaladó visszatérítés a jóváhagyási várólistára kerül. A visszatérítés jóváhagyása után számlázható a visszárurendelés.





