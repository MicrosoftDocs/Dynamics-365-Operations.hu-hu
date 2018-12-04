---
title: "A keresztárfolyam megadása"
description: "Ez a témakör a Microsoft Dynamics 365 for Finance and Operations keresztárfolyamairól nyújt információkat."
author: abruer
manager: AnnBe
ms.date: 05/16/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cf531c3a8f3bdb17314d1de436b98249169f82a3
ms.openlocfilehash: 112f77738b33aae94babe0cf8e9e61ff2ea3d004
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="specify-the-cross-rate"></a>A keresztárfolyam megadása

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja a keresztárfolyam, és a keresztárfolyam megadása, amikor egy kifizetést számlát célját. A keresztárfolyam akkor kell használni, amikor az összes, a következő feltételek vonatkoznak: 
-   A kifizetési számlát egyenlít ki. 
-   A számlasor és a számlasor használja a különféle pénznemekben. 
-   Sem pénzneme nem az alapértelmezett pénznemben. 

A keresztárfolyam nem használatos a fizetési tranzakció devizaátváltásának kiszámítására a kifizetés könyvelési pénznemhez. Az árfolyamok beolvasására az árfolyamtáblákból azért kerül sor, hogy kiszámítsák a fizetési tranzakció pénznemének összegét és a fizetés könyvelési pénznemének összegét. 

Például a könyvelési pénznemben USD, számla pénzneme CAD, pedig a kifizetés pénznemében EUR. A keresztárfolyam segítségével fordításához CAD és euró közötti közvetlen átváltási árfolyam megadása, és nem kell lefordítani USD keresztül. Amikor kiválaszt egy számlát és egy elsődleges kifizetést, a számla sorához keresztárfolyamot adhat meg. A keresztárfolyam az ilyen tranzakciók pénznemeinek a kiegyenlítés napján érvényes átváltási árfolyama.

1.  Lépjen az alábbiak közül valamelyik lapra:
- **Kinnlevőségek > Közös > Vevők > Minden vevő** 
- **Kötelezettségek > Közös > Szállítók > Minden szállító** 
- **Beszerzés és forrás > Közös > Szállítók > Minden szállító**
2.  Válassza ki a vevőt vagy szállítót, amelynek nyitott tranzakcióit elszámolja. 
3.  Egy adott vevő esetében a **Minden vevő** listaoldalon lépjen ide: **Beszedés > Nyitott tranzakciók kiegyenlítése**. Egy adott szállító esetében a **Minden szállító** listaoldalon lépjen ide: **Számla > Nyitott tranzakciók kiegyenlítése**. 
4.  Válassza ki az elsődleges kifizetést jelentő tranzakciót, majd kattintson a **Kifizetés megjelölése** gombra. A **Megjelölés** oszlopban található jelölőnégyzet be lesz jelölve, és egy információs ikon jelenik meg az **Elsődleges kifizetés** oszlopban. 
5.  A **Keresztárfolyam** mezőbe írja be a számla és a kifizetés pénzneme közötti átváltási árfolyam szorzóját a kifizetés napján érvényes értékkel. 

